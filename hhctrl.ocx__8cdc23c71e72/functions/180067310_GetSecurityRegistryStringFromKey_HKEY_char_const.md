# GetSecurityRegistryStringFromKey(HKEY__ * *,char const *)

- ea: `0x180067310`
- end: `0x1800673db`
- name: `?GetSecurityRegistryStringFromKey@@YAPEADPEAPEAUHKEY__@@PEBD@Z`
- size: `203`
- prototype: `char *__fastcall(HKEY *, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180067290`

## callees

- `0x180067310`
- `0x18006a7ac`

## import_xrefs

- `msvcrt!malloc` at `0x180067365`
- `msvcrt!malloc` at `0x18006737d`
- `msvcrt!malloc` at `0x180067365`
- `msvcrt!malloc` at `0x18006737d`
- `msvcrt!free` at `0x1800673c8`
- `msvcrt!free` at `0x1800673c8`
- `ADVAPI32!RegQueryValueExA` at `0x180067342`
- `ADVAPI32!RegQueryValueExA` at `0x1800673b0`
- `ADVAPI32!RegQueryValueExA` at `0x180067342`
- `ADVAPI32!RegQueryValueExA` at `0x1800673b0`

## pseudocode

```c

```
