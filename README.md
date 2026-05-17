#include <iostream>
#include <iomanip>
using namespace std;

const int NUM_EXPERIMENTS = 4;  
const int NUM_READINGS = 3;

int main() {  
    double readingValue, total, average;

    cout << "=== Experiment Data Collection ===\n";
    cout << "You will enter " << NUM_READINGS 
         << " readings for each of " << NUM_EXPERIMENTS 
         << " experiments.\n\n";

    for (int i = 1; i <= NUM_EXPERIMENTS; i++) {
        total = 0;
        cout << "EXPERIMENT " << i << "\n";
        cout << "-----------------\n";

        for (int j = 1; j <= NUM_READINGS; j++) {
            cout << "Enter value for reading " << j << ": ";
            cin >> readingValue;
            total += readingValue;  
        }

        average = total / NUM_READINGS;  
        
        cout << fixed << setprecision(2);
        cout << "Average for Experiment " << i << ": " << average << " → ";

        if (average < 100) {
            cout << "Below acceptable range\n";
        } else if (average <= 300) {
            cout << "Within acceptable range\n";
        } else { 
            cout << "Above acceptable range\n";
        }

        cout << endl;
    }

    cout << "=== End of Experiments ===\n";
    return 0;
}
