# IsPluginDisabled(HKEY__ *,int *)

- ea: `0x1800304f4`
- end: `0x180030558`
- name: `?IsPluginDisabled@@YAJPEAUHKEY__@@PEAH@Z`
- size: `100`
- prototype: `__int64 __fastcall(HKEY, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d4b0`

## callees

- `0x1800304f4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18003052c`
- `ADVAPI32!RegQueryValueExW` at `0x18003052c`

## pseudocode

```c

```
