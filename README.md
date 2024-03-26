# Cr-a-Cuisine-Sommelier-Virtuel-par-IA-G-n-rative
Créa-Cuisine utilise l'IA générative pour proposer des accords mets-vins personnalisés en fonction des préférences gustatives des utilisateurs et du menu choisi, offrant une expérience culinaire rehaussée.
# Créa-Cuisine: Sommelier Virtuel par IA Générative - Demo Code

# Mock Database of Wine Pairings
wine_database = {
    "beef": ["Cabernet Sauvignon", "Bordeaux", "Merlot"],
    "fish": ["Chardonnay", "Sauvignon Blanc", "Pinot Grigio"],
    "vegetarian": ["Grenache", "Beaujolais", "Pinot Noir"],
    "cheese": ["Port", "Sauternes", "Chianti"],
    "chocolate": ["Zinfandel", "Syrah", "Port"]
}

def get_user_preferences():
    """
    Simulate gathering user's taste preferences.
    """
    print("Please enter your preferred wine type (red, white, sweet):")
    wine_pref = input().lower()
    print("What type of dish will you be having? (beef, fish, vegetarian, cheese, chocolate):")
    dish_type = input().lower()
    return wine_pref, dish_type

def suggest_wine(wine_pref, dish_type):
    """
    Suggest a wine based on the user's preferences and the chosen dish.
    """
    suggestions = wine_database.get(dish_type, [])
    # Filter suggestions based on wine preference (basic simulation of AI personalization)
    if wine_pref != "sweet":  # Sweet wines are more specific, so we only filter if not chosen
        suggestions = [wine for wine in suggestions if wine_pref in wine.lower()]
    return suggestions

def main():
    """
    Main function to run the virtual sommelier demo.
    """
    wine_pref, dish_type = get_user_preferences()
    suggestions = suggest_wine(wine_pref, dish_type)
    if suggestions:
        print(f"Based on your preferences, we suggest the following wine(s): {', '.join(suggestions)}")
    else:
        print("Sorry, we couldn't find a perfect match. How about trying something new today?")

if __name__ == "__main__":
    main()
