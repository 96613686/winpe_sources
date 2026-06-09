# CMsiRegKey::RemoveValue(ushort const *,IMsiString const *)

- ea: `0x18007a980`
- end: `0x18007ad8b`
- name: `?RemoveValue@CMsiRegKey@@UEAAPEAVIMsiRecord@@PEBGPEBVIMsiString@@@Z`
- size: `1035`
- prototype: `struct IMsiRecord *(CMsiRegKey *__hidden this, const unsigned __int16 *, const struct IMsiString *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callees

- `0x180018ee0`
- `0x180019cc0`
- `0x18007a980`
- `0x18007ad94`
- `0x18007b194`
- `0x18007b274`
- `0x18007b430`
- `0x18007c788`
- `0x18007cbec`
- `0x18013fa30`
- `0x180153f90`
- `0x180182d58`
- `0x18021b584`
- `0x1802651de`
- `0x180265240`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x18007aa8e`
- `ADVAPI32!RegDeleteValueW` at `0x18007aa8e`
- `ADVAPI32!RegCloseKey` at `0x18007aaae`
- `ADVAPI32!RegCloseKey` at `0x18007aaae`
- `KERNEL32!lstrlenW` at `0x18007ac9a`
- `KERNEL32!lstrlenW` at `0x18007acc2`
- `KERNEL32!lstrlenW` at `0x18007ad08`
- `KERNEL32!lstrlenW` at `0x18007ac9a`
- `KERNEL32!lstrlenW` at `0x18007acc2`
- `KERNEL32!lstrlenW` at `0x18007ad08`
- `KERNEL32!lstrcmpiW` at `0x18007ac87`
- `KERNEL32!lstrcmpiW` at `0x18007ac87`

## pseudocode

```c

```
