# SetEnvvar(void * *,ushort const *,ushort const *,int)

- ea: `0x1800452e8`
- end: `0x1800453dc`
- name: `?SetEnvvar@@YAJPEAPEAXPEBG1H@Z`
- size: `244`
- prototype: `int(void **, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180027a14`
- `0x18002cba8`

## callees

- `0x1800212a0`
- `0x180024e34`
- `0x18003a730`
- `0x1800452e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180045353`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180045353`
- `ntdll!RtlSetEnvironmentVar` at `0x1800453ac`
- `ntdll!RtlSetEnvironmentVar` at `0x1800453ac`

## pseudocode

```c

```
