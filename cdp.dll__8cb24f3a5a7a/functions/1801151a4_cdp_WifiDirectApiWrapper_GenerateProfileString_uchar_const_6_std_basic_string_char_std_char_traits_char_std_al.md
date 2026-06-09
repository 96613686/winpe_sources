# cdp::WifiDirectApiWrapper::GenerateProfileString(uchar const (&)[6],std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,cdp::WifiDirectRole,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1801151a4`
- end: `0x18011559f`
- name: `?GenerateProfileString@WifiDirectApiWrapper@cdp@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAY05$$CBEAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@W4WifiDirectRole@2@AEBV?$vector@EV?$allocator@E@std@@@4@@Z`
- size: `1019`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180115070`
- `0x180295b48`
- `0x1802c7740`

## callees

- `0x1800046cc`
- `0x180005bcc`
- `0x18000aec4`
- `0x18000b724`
- `0x18000d098`
- `0x18000f8d0`
- `0x180010fb4`
- `0x180011058`
- `0x1800113bc`
- `0x18001ee70`
- `0x180030190`
- `0x1800624cc`
- `0x18008c438`
- `0x1800a11bc`
- `0x1800fcd40`
- `0x18011374c`
- `0x180114c58`
- `0x1801151a4`
- `0x1801155a8`
- `0x18017b1d4`
- `0x1801f6fb0`
- `0x1801fca2c`
- `0x1801fcbe0`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18011529f`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18011529f`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18011523d`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180115262`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18011523d`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180115262`
- `msvcp_win!?fill@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAADD@Z` at `0x180115252`
- `msvcp_win!?fill@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAADD@Z` at `0x180115252`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x180115288`
- `msvcp_win!?setw@std@@YA?AU?$_Smanip@_J@1@_J@Z` at `0x180115288`

## string_xrefs

- `0x18011542a`: `<?xml version="1.0"?><WFDProfile xmlns="http://www.microsoft.com/networking/WiFiDirect/profile/v1"><groupName>%S</groupName><groupID><deviceAddress>%.2X:%.2X:%.2X:%.2X:%.2X:%.2X</deviceAddress><SSID>%S</SSID></groupID><persistent>true</persistent><localSettings><role>%s</role><deviceAddress>%.2X:%.2X:%.2X:%.2X:%.2X:%.2X</deviceAddress></localSettings><security><groupKey><keyType>networkKey</keyType><protected>false</protected><keyMaterial>%s</keyMaterial></groupKey></security></WFDProfile>`

## pseudocode

```c

```
