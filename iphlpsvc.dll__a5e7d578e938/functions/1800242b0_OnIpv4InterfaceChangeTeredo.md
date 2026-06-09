# OnIpv4InterfaceChangeTeredo

- ea: `0x1800242b0`
- end: `0x1800247fe`
- name: `OnIpv4InterfaceChangeTeredo`
- size: `1358`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009010`
- `0x18000a704`
- `0x18000d7c0`
- `0x1800242b0`
- `0x180024bf8`
- `0x180024ce0`
- `0x180025298`
- `0x180025640`
- `0x1800256a0`
- `0x18004b5f0`
- `0x18004c188`
- `0x180083010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18002439b`
- `ntdll!EtwEventActivityIdControl` at `0x18002439b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180024538`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180024538`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002433e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002433e`
- `NSI!NsiFreeTable` at `0x1800244e1`
- `NSI!NsiFreeTable` at `0x1800244e1`
- `NSI!NsiGetAllParameters` at `0x18002462b`
- `NSI!NsiGetAllParameters` at `0x18002468f`
- `NSI!NsiGetAllParameters` at `0x18002462b`
- `NSI!NsiGetAllParameters` at `0x18002468f`
- `NSI!NsiAllocateAndGetTable` at `0x180024469`
- `NSI!NsiAllocateAndGetTable` at `0x180024469`

## string_xrefs

- `0x180024313`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x180024356`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x180024548`: `onecoreuap\net\netio\iphlpsvc\service\teredo.c`
- `0x1800246da`: `UpdateInterface: Luid: %I64x Compartment: %d`
- `0x18002478e`: `UpdateInterface: Luid: %I64x is WFD interface. Skipping...`
- `0x1800247ba`: `Leaving: Common: OnIpv4InterfaceChange`

## pseudocode

```c

```
