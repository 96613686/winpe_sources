# GetRegistryString(HKEY__ *,ushort const *,CWxString *)

- ea: `0x1800acfdc`
- end: `0x1800ad1bf`
- name: `?GetRegistryString@@YAJPEAUHKEY__@@PEBGPEAVCWxString@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, struct CWxString *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800841bc`
- `0x1800abc38`

## callees

- `0x18003f8c4`
- `0x18004148c`
- `0x1800414fc`
- `0x180057930`
- `0x18008b5f0`
- `0x1800acfdc`
- `0x1800d6814`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ad0ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ad122`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ad0ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ad122`

## pseudocode

```c

```
