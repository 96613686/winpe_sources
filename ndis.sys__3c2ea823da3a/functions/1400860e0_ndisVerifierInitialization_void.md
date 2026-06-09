# ndisVerifierInitialization(void)

- ea: `0x1400860e0`
- end: `0x1400861b9`
- name: `?ndisVerifierInitialization@@YAEXZ`
- size: `217`
- prototype: `unsigned __int8(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x14004f3d0`
- `0x14018b240`

## callees

- `0x1400860e0`

## import_xrefs

- `ntoskrnl!DifRegisterClassDriverPlugin` at `0x1400860f9`
- `ntoskrnl!DifRegisterClassDriverPlugin` at `0x1400860f9`
- `ntoskrnl!VfQueryDispatchTable` at `0x140086114`
- `ntoskrnl!VfQueryDispatchTable` at `0x14008613a`
- `ntoskrnl!VfQueryDispatchTable` at `0x140086114`
- `ntoskrnl!VfQueryDispatchTable` at `0x14008613a`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400861a1`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400861a1`

## pseudocode

```c

```
