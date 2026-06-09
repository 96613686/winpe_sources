# ndisVerifierInitialization(void)

- ea: `0x14008b360`
- end: `0x14008b439`
- name: `?ndisVerifierInitialization@@YAEXZ`
- size: `217`
- prototype: `unsigned __int8(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x140054ac0`
- `0x140191240`

## callees

- `0x14008b360`

## import_xrefs

- `ntoskrnl!DifRegisterClassDriverPlugin` at `0x14008b379`
- `ntoskrnl!DifRegisterClassDriverPlugin` at `0x14008b379`
- `ntoskrnl!VfQueryDispatchTable` at `0x14008b394`
- `ntoskrnl!VfQueryDispatchTable` at `0x14008b3ba`
- `ntoskrnl!VfQueryDispatchTable` at `0x14008b394`
- `ntoskrnl!VfQueryDispatchTable` at `0x14008b3ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x14008b421`
- `ntoskrnl!KeInitializeSpinLock` at `0x14008b421`

## pseudocode

```c

```
