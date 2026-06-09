# LCIETabManagerWinProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1801bbdc0`
- end: `0x1801bc1dc`
- name: `?LCIETabManagerWinProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1052`
- prototype: `__int64(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x18001b970`
- `0x1800eadc4`
- `0x1801bbc74`
- `0x1801bbdc0`
- `0x1801c7f84`
- `0x180213a0c`
- `0x180550010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1801bc141`
- `KERNEL32!CreateThread` at `0x1801bc141`
- `KERNEL32!HeapSetInformation` at `0x1801bc113`
- `KERNEL32!HeapSetInformation` at `0x1801bc113`
- `iertutil!__imp_?ClearNegativeKeyCache@SettingStore@@YAXXZ` at `0x1801bc02b`
- `iertutil!__imp_?ClearNegativeKeyCache@SettingStore@@YAXXZ` at `0x1801bc02b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bc01d`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bc01d`
- `WININET!InternetSetOptionW` at `0x1801bbf83`
- `WININET!InternetSetOptionW` at `0x1801bbf83`
- `MSHTML!__imp_CreatePrivacIEDatabase` at `0x1801bbef8`
- `MSHTML!__imp_CreatePrivacIEDatabase` at `0x1801bbef8`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferOtherProcess@@YAJAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x1801bbf24`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferOtherProcess@@YAJAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x1801bbf24`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x1801bbf46`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x1801bbf46`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1801bbdec`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x1801bbdec`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1801bbedd`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x1801bbedd`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801bbe12`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801bc094`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801bbe12`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x1801bc094`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1801bbf53`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1801bc1bb`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1801bbf53`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x1801bc1bb`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x1801bbeab`
- `msIso!__imp_?IsoReferenceDefaultScope@@YAJKPEAPEAUIsoScope@@@Z` at `0x1801bbeab`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801bc1ad`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801bc1ad`
- `msIso!__imp_?IsoProcessManagerMessages@@YAJHKPEAU_IsoMessage@@PEAUIsoScope@@@Z` at `0x1801bc000`
- `msIso!__imp_?IsoProcessManagerMessages@@YAJHKPEAU_IsoMessage@@PEAUIsoScope@@@Z` at `0x1801bc000`
- `msIso!__imp_?IsoAddEntanglementLock@@YAJXZ` at `0x1801bc0f9`
- `msIso!__imp_?IsoAddEntanglementLock@@YAJXZ` at `0x1801bc0f9`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x1801bc119`
- `msIso!__imp_?IsoReleaseEntanglementLock@@YAJXZ` at `0x1801bc119`
- `ieapfltr!GetUrlBlockClient` at `0x1801bc046`
- `ieapfltr!GetUrlBlockClient` at `0x1801bc046`

## pseudocode

```c

```
