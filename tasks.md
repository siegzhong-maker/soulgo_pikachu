# Tasks

- [ ] **State Machine Refactoring** <!-- id: 0 -->
    - Update `PET_STATES` in `index.html` to include `MOVING`.
    - Modify `setPetState` to handle entry/exit logic for `MOVING` state (e.g., clearing timers).
    - Ensure `MOVING` state prevents accidental inactivity resets.

- [ ] **Animation & Movement Logic Enhancement** <!-- id: 1 -->
    - Refactor `walkPetAlongPath` to return a `Promise`.
    - Implement dynamic start point logic (start from current `bottom/left`).
    - Add "flip" logic (CSS `transform: scaleX(-1)`) based on movement direction.
    - Update `playPetAnimation` to support a `moving` animation (using `interact` or high-speed `idle_breath` as placeholder if no dedicated sprite).

- [ ] **Behavior Sequence Engine** <!-- id: 2 -->
    - Implement `runBehaviorSequence(sequence)` function to execute steps like `{ type: 'move', ... }`, `{ type: 'anim', ... }`, `{ type: 'wait', ... }`.
    - Replace existing `setTimeout` chains in `applyBehaviorDecision` with this new async engine.

- [ ] **Update "Let AI Decide" Logic** <!-- id: 3 -->
    - Update `applyBehaviorDecision` to use `runBehaviorSequence`.
    - Define rich behavior chains for common decisions (e.g., "Go to Bed" = Think -> Walk to Bed -> Sleep).
    - Ensure the "Thinking" bubble/status is cleared correctly after the sequence starts.

- [ ] **Verification** <!-- id: 4 -->
    - Test "Let AI Decide" button for all 4 main outcomes (Bed, Pot, Door, Wander).
    - Verify animation smoothness and correct orientation (flip).
    - Verify that user interaction (touch) correctly interrupts or co-exists with the new logic.
