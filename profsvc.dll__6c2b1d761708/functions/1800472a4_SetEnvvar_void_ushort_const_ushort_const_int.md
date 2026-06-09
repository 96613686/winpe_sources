# SetEnvvar(void * *,ushort const *,ushort const *,int)

- ea: `0x1800472a4`
- end: `0x1800473a9`
- name: `?SetEnvvar@@YAJPEAPEAXPEBG1H@Z`
- size: `261`
- prototype: `int(void **, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180029908`
- `0x18004fcbc`

## callees

- `0x18001e658`
- `0x180024260`
- `0x18003bc70`
- `0x1800472a4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180047313`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x180047313`
- `ntdll!RtlSetEnvironmentVar` at `0x180047372`
- `ntdll!RtlSetEnvironmentVar` at `0x180047372`

## pseudocode

```c

```
