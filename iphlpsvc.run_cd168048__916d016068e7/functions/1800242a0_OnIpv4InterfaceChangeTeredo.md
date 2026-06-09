# OnIpv4InterfaceChangeTeredo

- ea: `0x1800242a0`
- end: `0x1800247ee`
- name: `OnIpv4InterfaceChangeTeredo`
- size: `1358`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009000`
- `0x18000a6f4`
- `0x18000d7b0`
- `0x1800242a0`
- `0x180024be8`
- `0x180024cd0`
- `0x180025288`
- `0x180025630`
- `0x180025690`
- `0x18004b630`
- `0x18004c1c8`
- `0x180083010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18002438b`
- `ntdll!EtwEventActivityIdControl` at `0x18002438b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180024528`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180024528`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002432e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002432e`
- `NSI!NsiFreeTable` at `0x1800244d1`
- `NSI!NsiFreeTable` at `0x1800244d1`
- `NSI!NsiGetAllParameters` at `0x18002461b`
- `NSI!NsiGetAllParameters` at `0x18002467f`
- `NSI!NsiGetAllParameters` at `0x18002461b`
- `NSI!NsiGetAllParameters` at `0x18002467f`
- `NSI!NsiAllocateAndGetTable` at `0x180024459`
- `NSI!NsiAllocateAndGetTable` at `0x180024459`

## string_xrefs

- `0x180024303`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x180024346`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x180024538`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x1800246ca`: `UpdateInterface: Luid: %I64x Compartment: %d`
- `0x18002477e`: `UpdateInterface: Luid: %I64x is WFD interface. Skipping...`
- `0x1800247aa`: `Leaving: Common: OnIpv4InterfaceChange`

## pseudocode

```c

```
