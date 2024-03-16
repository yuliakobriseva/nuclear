# nuclear
import random

class RadioactiveSubstance:
    def __init__(self, initial_atoms, half_life):
        self.atoms = initial_atoms
        self.half_life = half_life

    def decay(self):
        decayed_atoms = 0
        for i in range(self.atoms):
            if random.random() < 0.5:
                decayed_atoms += 1
        self.atoms -= decayed_atoms
        return decayed_atoms

# Example usage
if __name__ == "__main__":
    radioactive_sample = RadioactiveSubstance(initial_atoms=1000, half_life=10)

    print("Initial number of atoms:", radioactive_sample.atoms)

    for i in range(10):
        decayed = radioactive_sample.decay()
        print(f"Decay after {i+1} time units:", decayed, "atoms")

    print("Final number of atoms:", radioactive_sample.atoms)
