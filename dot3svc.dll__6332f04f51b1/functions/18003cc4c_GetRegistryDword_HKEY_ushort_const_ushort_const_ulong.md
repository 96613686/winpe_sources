# GetRegistryDword(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x18003cc4c`
- end: `0x18003cd40`
- name: `?GetRegistryDword@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `244`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003525c`
- `0x180038480`
- `0x18003cff4`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x1800128ec`
- `0x18003cc4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ccc3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ccc3`

## pseudocode

```c

```
