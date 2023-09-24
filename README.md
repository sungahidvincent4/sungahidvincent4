





//Jes Vincent A. Sungahid BSIT 2A 
import java.util.Scanner;
public class Temp{
    static String[] Nmonths = {"January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"};
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int months = 12;
        double[][] temperatureData = new double[months][2];

        for (int i = 0; i < months; i++) {
            System.out.print("Highest Temp. month of " + (Nmonths[i]) + ": ");
            temperatureData[i][0] = sc.nextDouble();
            System.out.print("Lowest Temp. month of " + (Nmonths[i]) + ": ");
            temperatureData[i][1] = sc.nextDouble();
            System.out.println(); 
        }
        // Display
        getData(temperatureData);
        System.out.println();
        High(temperatureData);
        Low(temperatureData);
        System.out.println();
        indexHigh(temperatureData);
        indexLow(temperatureData);
    }// main

    // getData method
    public static void getData(double[][] temperatureData) {
        System.out.println("Temperature Data:");
        int i = 0;
        for (double[] monthTemperatures : temperatureData) {
            System.out.println(Nmonths[i] + ": High - " + monthTemperatures[0] + " Low - " + monthTemperatures[1]);
            i++;
        }
    }

    // averageHigh method
    public static void High(double[][] temperatureData) {
        double sum = 0;
        for (int i = 0; i < temperatureData.length; i++) {
            sum += temperatureData[i][0];
        }
        double average = sum / temperatureData.length;
        System.out.println("The Average High Temperature: " + average);
    }

   // averageLow method
    public static void Low(double[][] temperatureData) {
        double sum = 0;
        for (int i = 0; i < temperatureData.length; i++) {
            sum += temperatureData[i][1];
        }
        double average = sum / temperatureData.length;
        System.out.println("The Average Low Temperature: " + average);
    }

   // indexHighTemp method
    public static void indexHigh(double[][] temperatureData) {
        double maxHigh = temperatureData[0][0];
        int index = 0;

        for (int i = 1; i < temperatureData.length; i++) {
            if (temperatureData[i][0] > maxHigh) {
                maxHigh = temperatureData[i][0];
                index = i;
            }
        }

        System.out.println("Highest Temperature Month of: " + Nmonths[index]);
    }

   // indexLowTemp method
    public static void indexLow(double[][] temperatureData) {
        double minLow = temperatureData[0][1];
        int index = 0;

        for (int i = 1; i < temperatureData.length; i++) {
            if (temperatureData[i][1] < minLow) {
                minLow = temperatureData[i][1];
                index = i;
            }
        }

        System.out.println("Lowest Temperature Month of: " + Nmonths[index]);
    }
    
}
