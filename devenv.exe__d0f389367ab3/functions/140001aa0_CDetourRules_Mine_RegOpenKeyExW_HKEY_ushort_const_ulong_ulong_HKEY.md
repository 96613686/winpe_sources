# CDetourRules::Mine_RegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x140001aa0`
- end: `0x140001d5f`
- name: `?Mine_RegOpenKeyExW@CDetourRules@@CAJPEAUHKEY__@@PEBGKKPEAPEAU2@@Z`
- size: `703`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, HKEY *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400023f0`

## callees

- `0x140001020`
- `0x140001040`
- `0x140001070`
- `0x140001130`
- `0x1400011f0`
- `0x14000126c`
- `0x1400013a0`
- `0x140001428`
- `0x140001aa0`
- `0x140001f90`
- `0x140002270`
- `0x140013f00`
- `0x140033ab0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140001c39`
- `KERNEL32!EnterCriticalSection` at `0x140001c39`
- `KERNEL32!LeaveCriticalSection` at `0x140001c9f`
- `KERNEL32!LeaveCriticalSection` at `0x140001c9f`
- `VCRUNTIME140!wcsstr` at `0x140001b1d`
- `VCRUNTIME140!wcsstr` at `0x140001b1d`

## string_xrefs

- `0x140001d14`: `D:\dbs\el\ddvsm\src\vscommon\RegistryDetouring\VsDetour.cpp`
- `0x140001d02`: `VSRegDetour_RegOpenKeyEx`

## pseudocode

```c

```
