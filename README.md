```cpp
#include <iostream>
#include <map>
#include <vector>

using namespace std;

int main() {
    // Aktuelle Woche eingeben
    int currentWeek;
    cout << "Aktuelle Woche eingeben (0-10): ";
    cin >> currentWeek;

    // Wassermenge eingeben
    cout << "Wassermenge in Millilitern: ";
    int waterAmount;
    cin >> waterAmount;

    // Düngemittel auswählen
    vector<string> fertilizers = {"Root-Juice", "BioGrow", "BioBloom", "BioHeaven", "Top-Max", "ActiVera"};
    map<string, vector<int>> fertilizerSchedule = {
        {"Root-Juice", {4, 0, 0, 0, 0, 0, 0, 0, 0, 0}},
        {"BioGrow", {0, 1, 1, 1, 1, 1, 1, 1, 1, 0}},
        {"BioBloom", {0, 1, 2, 2, 3, 3, 4, 4, 4, 0}},
        {"BioHeaven", {2, 0, 0, 0, 0, 0, 0, 0, 0, 0}},
        {"Top-Max", {0, 1, 1, 1, 1, 4, 4, 4, 4, 0}},
        {"ActiVera", {2, 2, 2, 3, 4, 4, 5, 5, 5, 0}}
    };

    cout << "BioBizz Dünger: MiliLiter: \n";
    // Düngemittelmenge berechnen
    for (const auto& fertilizer : fertilizers) {
        int fertilizerAmount = 0;
        if (currentWeek < fertilizerSchedule[fertilizer].size()) {
            fertilizerAmount = fertilizerSchedule[fertilizer][currentWeek];
        }
        cout << fertilizer << ": \t" << fertilizerAmount * waterAmount / 1000.0 << " mL" << endl;
    }

    return 0;
}
````
