# CTSScpRegister::GetScpAttributes(ushort *,ulong *,_ads_attr_info * *)

- ea: `0x18007a960`
- end: `0x18007aaf0`
- name: `?GetScpAttributes@CTSScpRegister@@UEAAJPEAGPEAKPEAPEAU_ads_attr_info@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(CTSScpRegister *__hidden this, unsigned __int16 *, unsigned int *, struct _ads_attr_info **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180005665`
- `0x18001ae3c`
- `0x18001aea4`
- `0x18007a544`
- `0x18007a960`
- `0x18007ab8c`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18007a98a`
- `ole32!CoInitializeEx` at `0x18007a98a`
- `ole32!CoUninitialize` at `0x18007aacb`
- `ole32!CoUninitialize` at `0x18007aacb`
- `KERNEL32!LocalAlloc` at `0x18007aa46`
- `KERNEL32!LocalAlloc` at `0x18007aa46`
- `KERNEL32!LocalFree` at `0x18007aabf`
- `KERNEL32!LocalFree` at `0x18007aabf`

## string_xrefs

- `0x18007aa1f`: `"GetScpLdapBindPathFromRegistry"`

## pseudocode

```c

```
