# SetTetheringMaxSupportedDevices(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const &,std::unique_ptr<Wcmutil,std::default_delete<Wcmutil>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001f5c8`
- end: `0x18001f7e4`
- name: `?SetTetheringMaxSupportedDevices@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBU_GUID@@AEBV?$unique_ptr@VWcmutil@@U?$default_delete@VWcmutil@@@std@@@2@AEAV12@@Z`
- size: `540`
- prototype: `bool __fastcall(const std::wstring *TetheringMaxDevicesStr, const std::wstring *DefaultProfileName, const _GUID *InterfaceGuid, const std::unique_ptr<Wcmutil> *Wcm, std::wstring *TetheringMaxDevicesXml)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x18001df00`

## callees

- `0x180002790`
- `0x1800032dc`
- `0x18000af94`
- `0x18000b8c0`
- `0x180011844`
- `0x180011cfc`
- `0x180012618`
- `0x180012770`
- `0x18001c340`
- `0x18001c61c`
- `0x18001d304`
- `0x18001d608`
- `0x18001f2e4`
- `0x18001f5c8`
- `0x180020e70`
- `0x18002108c`
- `0x1800211e0`
- `0x18004083c`

## import_xrefs

- `TetheringClient!TetheringSettingsSaveSettingWithGuid` at `0x18001f6dd`
- `TetheringClient!TetheringSettingsSaveSettingWithGuid` at `0x18001f6dd`

## pseudocode

```c

```
