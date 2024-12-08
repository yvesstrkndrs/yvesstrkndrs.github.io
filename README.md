import java.util.Scanner;

public class RamenReinigenCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // Informatie tonen aan de gebruiker
        System.out.println("Bereken de kosten voor het reinigen van je ramen");
        
        // Vraag om het aantal ramen
        System.out.print("Aantal ramen: ");
        int numberOfWindows = scanner.nextInt();
        
        // Vraag om de frequentie van reiniging
        System.out.println("Frequentie van reiniging:");
        System.out.println("1. Om de 4 weken (€1,60 per raam)");
        System.out.println("2. Om de 8 weken (€2,60 per raam)");
        System.out.print("Kies een optie (1 of 2): ");
        int frequencyOption = scanner.nextInt();
        
        // Basisprijs en prijs per raam afhankelijk van de frequentie
        double costPerWindow = 0;
        
        if (frequencyOption == 1) {
            costPerWindow = 1.60;
        } else if (frequencyOption == 2) {
            costPerWindow = 2.60;
        } else {
            System.out.println("Ongeldige keuze. Programma stopt.");
            return;
        }
        
        // Basisminimum kosten
        double minimumCost = 15.00;
        
        // Bereken de kosten
        double totalCost = numberOfWindows * costPerWindow;
        
        // De kosten moeten minimaal €15 zijn
        if (totalCost < minimumCost) {
            totalCost = minimumCost;
        }
        
        // Resultaat tonen
        System.out.printf("De kosten voor het reinigen van %d raam(s) om de %d weken is €%.2f.%n", 
                          numberOfWindows, (frequencyOption == 1 ? 4 : 8), totalCost);
        
        scanner.close();
    }
}
