# WxGetRegistryString(HKEY__ *,ushort const *,CWxString *)

- ea: `0x1800c3efc`
- end: `0x1800c40ef`
- name: `?WxGetRegistryString@@YAJPEAUHKEY__@@PEBGPEAVCWxString@@@Z`
- size: `499`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, struct CWxString *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18005c2ac`
- `0x1800c49ec`
- `0x1800c59e4`

## callees

- `0x18003f8c4`
- `0x18004148c`
- `0x1800414fc`
- `0x180057930`
- `0x18008b5f0`
- `0x1800c3efc`
- `0x1800d6814`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c3fcd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c4052`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c3fcd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c4052`

## pseudocode

```c

```
