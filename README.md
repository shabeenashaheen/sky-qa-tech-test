# sky-qa-tech-test
Shabeena
Scenario: Regular numbers
    * I have entered 3 into the calculator
    * I press divide
    * I have entered 2 into the calculator
    * I press equal
    * The result should be 1.5 on the screen
Scenario Outline: Add two numbers
    Given I have entered <input_1> into the calculator
    And I have entered <input_2> into the calculator
    When I press <button>
    Then the result should be <output> on the screen

  Examples:
    | input_1 | input_2 | button | output |
    | 20      | 30      | add    | 50     |
    | 2       | 5       | add    | 7      |
    | 0       | 40      | add    | 40     |
Scenario Outline: Subtract two numbers
    Given I just turned on the calculator
    When I press <button1>
    And I press subtract
    And I press <button2>
    And I press calculate
    Then the display should show <result>

  Examples:
    | button1 | button2 | result |
    | 2       | 3       | -1     |
    | 7       | 5       | 2      |
    | 9       | 1       | 8      |
Scenario Outline: Multiply two numbers
    Given I enter "<num1>","<num2>"
    When I multiply those two numbers together
    Then the multiplication is "<result>"

    @int_multiply
    Scenarios: As integers
      | num1 | num2 | result |
      | 10   | 20   | 200    |
      | 3    | 34   | 102    |

    @float_multiply
    Scenarios: As float
      | num1 | num2  | result |
      | 10.0 | 20.0  | 200.0  |
      | 0.1  | 210.0 | 21.0   |

    @negative_multiply
    Scenarios: negative numbers
      | num1 | num2 | result |
      | -10  | 20   | -200   |
      | 20   | -30  | -600   |
      | -20  | -30  | 600    
