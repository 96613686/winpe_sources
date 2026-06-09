# CMsiRegKey::RemoveValue(ushort const *,IMsiString const *)

- ea: `0x18007c8e0`
- end: `0x18007ccc6`
- name: `?RemoveValue@CMsiRegKey@@UEAAPEAVIMsiRecord@@PEBGPEBVIMsiString@@@Z`
- size: `998`
- prototype: `struct IMsiRecord *(CMsiRegKey *__hidden this, const unsigned __int16 *, const struct IMsiString *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callees

- `0x180061334`
- `0x1800620e4`
- `0x18007c8e0`
- `0x18007cccc`
- `0x18007d0b4`
- `0x18007d184`
- `0x18007d334`
- `0x18007e604`
- `0x18007ea4c`
- `0x18013a830`
- `0x18014e5fc`
- `0x18017c7c4`
- `0x180211cf4`
- `0x18025ab1e`
- `0x18025ab80`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x18007c9ed`
- `ADVAPI32!RegDeleteValueW` at `0x18007c9ed`
- `ADVAPI32!RegCloseKey` at `0x18007ca07`
- `ADVAPI32!RegCloseKey` at `0x18007ca07`
- `KERNEL32!lstrlenW` at `0x18007cbe7`
- `KERNEL32!lstrlenW` at `0x18007cc09`
- `KERNEL32!lstrlenW` at `0x18007cc49`
- `KERNEL32!lstrlenW` at `0x18007cbe7`
- `KERNEL32!lstrlenW` at `0x18007cc09`
- `KERNEL32!lstrlenW` at `0x18007cc49`
- `KERNEL32!lstrcmpiW` at `0x18007cbda`
- `KERNEL32!lstrcmpiW` at `0x18007cbda`

## pseudocode

```c

```
