#include <stdio.h>

// Function to calculate the area using Trapezoidal Rule for discrete points
double trapezoidal_rule(double *x, double *y, int n) {
    double area = 0.0;
    
    // Iterate through pairs of points to sum up trapezoid areas
    for (int i = 0; i < n - 1; i++) {
        double h = x[i+1] - x[i];
        area += (h * (y[i] + y[i+1]) / 2.0);
    }

    return area;
}

int main() {
    int n;

    // Input the number of data points
    printf("Enter the number of data points: ");
    scanf("%d", &n);

    double x[n], y[n];

    // Input x and y values
    printf("Enter the x and y values:\n");
    for (int i = 0; i < n; i++) {
        printf("x[%d] y[%d]: ", i, i);
        scanf("%lf %lf", &x[i], &y[i]);
    }

    // Calculate the integral using the Trapezoidal Rule
    double result = trapezoidal_rule(x, y, n);

    // Output the result
    printf("The approximate integral using the Trapezoidal Rule is: %.6f\n", result);

    return 0;
}
