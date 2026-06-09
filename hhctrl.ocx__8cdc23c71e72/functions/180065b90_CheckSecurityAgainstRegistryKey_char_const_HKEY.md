# CheckSecurityAgainstRegistryKey(char const *,HKEY__ * *)

- ea: `0x180065b90`
- end: `0x180065cd5`
- name: `?CheckSecurityAgainstRegistryKey@@YAJPEBDPEAPEAUHKEY__@@@Z`
- size: `325`
- prototype: `__int64 __fastcall(LPCSTR lpString2, HKEY *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180069550`

## callees

- `0x18004f794`
- `0x180065b90`

## import_xrefs

- `msvcrt!malloc` at `0x180065bf2`
- `msvcrt!malloc` at `0x180065bf2`
- `msvcrt!free` at `0x180065cc1`
- `msvcrt!free` at `0x180065cc1`
- `KERNEL32!lstrcmpiA` at `0x180065caa`
- `KERNEL32!lstrcmpiA` at `0x180065caa`
- `USER32!CharNextA` at `0x180065c61`
- `USER32!CharNextA` at `0x180065c61`
- `ADVAPI32!RegQueryValueExA` at `0x180065bd0`
- `ADVAPI32!RegQueryValueExA` at `0x180065c3d`
- `ADVAPI32!RegQueryValueExA` at `0x180065bd0`
- `ADVAPI32!RegQueryValueExA` at `0x180065c3d`

## pseudocode

```c

```
