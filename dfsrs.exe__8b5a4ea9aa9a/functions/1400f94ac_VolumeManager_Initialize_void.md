# VolumeManager::Initialize(void)

- ea: `0x1400f94ac`
- end: `0x1400fab08`
- name: `?Initialize@VolumeManager@@IEAAXXZ`
- size: `5724`
- prototype: `void __fastcall(VolumeManager *__hidden this)`
- caller_count: `1`
- callee_count: `89`
- tags: `installer_update`

## callers

- `0x1400ffb20`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x14000c910`
- `0x14000d980`
- `0x14000daa0`
- `0x14000dcc0`
- `0x14000e34c`
- `0x14000ee94`
- `0x14001a344`
- `0x14001b620`
- `0x14001cfa0`
- `0x1400216e0`
- `0x140022ce4`
- `0x140022d1c`
- `0x1400248f4`
- `0x14002c2f4`
- `0x140035304`
- `0x140035378`
- `0x1400370bc`
- `0x140037110`
- `0x1400391c4`
- `0x140047e14`
- `0x140055db4`
- `0x14005603c`
- `0x140058888`
- `0x140069684`
- `0x14006a550`
- `0x1400727e8`
- `0x14007c880`
- `0x14007f9f4`
- `0x140082280`
- `0x140083f8c`
- `0x1400842dc`
- `0x140086194`
- `0x14008e7c4`
- `0x14008e9d0`
- `0x140092818`
- `0x140096884`
- `0x1400984c4`
- `0x14009fe84`
- `0x1400c30e4`
- `0x1400ed468`
- `0x1400f1088`
- `0x1400f1628`
- `0x1400f16e4`
- `0x1400f17b4`
- `0x1400f27e8`
- `0x1400f3508`
- `0x1400f37d4`
- `0x1400f3898`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400fa376`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400fa376`
- `KERNEL32!LeaveCriticalSection` at `0x1400f9826`
- `KERNEL32!LeaveCriticalSection` at `0x1400f9fb3`
- `KERNEL32!LeaveCriticalSection` at `0x1400fa3bb`
- `KERNEL32!LeaveCriticalSection` at `0x1400f9826`
- `KERNEL32!LeaveCriticalSection` at `0x1400f9fb3`
- `KERNEL32!LeaveCriticalSection` at `0x1400fa3bb`
- `KERNEL32!EnterCriticalSection` at `0x1400f9844`
- `KERNEL32!EnterCriticalSection` at `0x1400f9eda`
- `KERNEL32!EnterCriticalSection` at `0x1400fa2f8`
- `KERNEL32!EnterCriticalSection` at `0x1400f9844`
- `KERNEL32!EnterCriticalSection` at `0x1400f9eda`
- `KERNEL32!EnterCriticalSection` at `0x1400fa2f8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400fa77a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400fa77a`

## string_xrefs

- `0x1400f9f38`: `Update volumeInfoHistory`
- `0x1400fa34b`: `Update volumeInfoHistory`
- `0x1400f955d`: ` volId:%? volPath:%? volState:%?`
- `0x1400fa85d`: `Changed state. volId:%? volPath:%? volState:%?`
- `0x1400fa578`: `SSR restored SYSVOL but there is no SYSVOL content set on this volume. ssrId:%? auth:%? volId:%? volPath:%? volState:%?`
- `0x1400fa8f3`: `Failed to purge ghosted content sets. volId:%? volPath:%? volState:%? Error:%?`
- `0x1400fa6db`: `Failed to update SSR ID in DB. volId:%? volPath:%? volState:%?`
- `0x1400fa25d`: `Failed to initialize volume. volId:%? volPath:%? volState:%? Error:%?`

## pseudocode

```c

```
