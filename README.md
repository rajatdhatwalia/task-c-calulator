#include <iostream>
#include <cmath>
#include <stdexcept>

// Function to perform addition
double add(double num1, double num2) {
    return num1 + num2;
}

// Function to perform subtraction
double subtract(double num1, double num2) {
    return num1 - num2;
}

// Function to perform multiplication
double multiply(double num1, double num2) {
    return num1 * num2;
}

// Function to perform division
double divide(double num1, double num2) {
    if (num2 == 0) {
        throw std::runtime_error("Error: Division by zero!");
    }
    return num1 / num2;
}

// Function to calculate square root
double sqrt(double num) {
    if (num < 0) {
        throw std::runtime_error("Error: Square root of negative number!");
    }
    return std::sqrt(num);
}

// Function to perform exponentiation
double pow(double num1, double num2) {
    return std::pow(num1, num2);
}

// Function to perform trigonometric functions
double sin(double num) {
    return std::sin(num);
}

double cos(double num) {
    return std::cos(num);
}

double tan(double num) {
    return std::tan(num);
}

int main() {
    std::cout << "Welcome to the Digital Calculator!" << std::endl;
    std::cout << "Enter 'quit' to exit." << std::endl;

    while (true) {
        std::cout << "Enter an operation (+, -, *, /, sqrt, pow, sin, cos, tan): ";
        std::string operation;
        std::cin >> operation;

        if (operation == "quit") {
            break;
        }

        double num1, num2;
        std::cout << "Enter the first number: ";
        std::cin >> num1;

        if (operation!= "sqrt" && operation!= "sin" && operation!= "cos" && operation!= "tan") {
            std::cout << "Enter the second number: ";
            std::cin >> num2;
        }

        try {
            if (operation == "+") {
                std::cout << "Result: " << add(num1, num2) << std::endl;
            } else if (operation == "-") {
                std::cout << "Result: " << subtract(num1, num2) << std::endl;
            } else if (operation == "*") {
                std::cout << "Result: " << multiply(num1, num2) << std::endl;
            } else if (operation == "/") {
                std::cout << "Result: " << divide(num1, num2) << std::endl;
            } else if (operation == "sqrt") {
                std::cout << "Result: " << sqrt(num1) << std::endl;
            } else if (operation == "pow") {
                std::cout << "Result: " << pow(num1, num2) << std::endl;
            } else if (operation == "sin") {
                std::cout << "Result: " << sin(num1) << std::endl;
            } else if (operation == "cos") {
                std::cout << "Result: " << cos(num1) << std::endl;
            } else if (operation == "tan") {
                std::cout << "Result: " << tan(num1) << std::endl;
            } else {
                std::cout << "Error: Invalid operation!" << std::endl;
            }
        } catch (const std::exception& e) {
            std::cout << "Error: " << e.what() << std::endl;
        }
    }

    return 0;
}
