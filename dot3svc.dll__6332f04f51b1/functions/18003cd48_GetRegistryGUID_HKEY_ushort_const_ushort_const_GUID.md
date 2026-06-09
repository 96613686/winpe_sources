# GetRegistryGUID(HKEY__ *,ushort const *,ushort const *,_GUID *)

- ea: `0x18003cd48`
- end: `0x18003ce53`
- name: `?GetRegistryGUID@@YAJPEAUHKEY__@@PEBG1PEAU_GUID@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18003cff4`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x1800128ec`
- `0x18003cd48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cdcb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003cdcb`

## pseudocode

```c

```
