# RealtimeProtection::CRtpDlpEngine::CheckAccessForBrowsers(wchar_t const *,std::optional<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &,wchar_t const *,ulong,PPID const &,_MP_KNOWN_PROCESS_TYPE,std::optional<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>> const &,ulong,EndpointDlp::Client::ExtendedAttributes const &,DlpEnforcementLevel &,_DlpAuthGroupInfo &,bool &,bool &,RealtimeProtection::MpDlpPolicyTraceInfo &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,bool &,_DLPEVENT_EXTRAINFO &,std::optional<std::basic_string<char,std::char_traits<char>,std::allocator<char>>> &,bool)

- ea: `0x180186bd4`
- end: `0x1801888c7`
- name: `?CheckAccessForBrowsers@CRtpDlpEngine@RealtimeProtection@@AEAAJPEB_WAEBV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@0KAEBUPPID@@W4_MP_KNOWN_PROCESS_TYPE@@1KAEBUExtendedAttributes@Client@EndpointDlp@@AEAW4DlpEnforcementLevel@@AEAU_DlpAuthGroupInfo@@AEA_N7AEAUMpDlpPolicyTraceInfo@2@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@97AEAU_DLPEVENT_EXTRAINFO@@AEAV?$optional@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@4@_N@Z`
- size: `7411`
- prototype: `__int64 __fastcall(__int64, wchar_t *, struct _FILETIME, wchar_t *, wchar_t *, __int64, unsigned int, __int64, unsigned int, __int64, _DWORD *, void *, _BYTE *, _BYTE *, void *, void *, void *, _BYTE *, _OWORD *, __int64, char)`
- caller_count: `2`
- callee_count: `63`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18018d9f0`
- `0x18019e604`

## callees

- `0x18001a444`
- `0x1800249f0`
- `0x180026460`
- `0x180029290`
- `0x180029590`
- `0x18002c150`
- `0x18002e728`
- `0x180033520`
- `0x180034420`
- `0x180038450`
- `0x1800398a0`
- `0x1800399c0`
- `0x18003cafc`
- `0x18003db1c`
- `0x18003df30`
- `0x180046354`
- `0x1800463b8`
- `0x1800489dc`
- `0x180049b34`
- `0x18004b3bc`
- `0x18004e000`
- `0x1800542d0`
- `0x180054490`
- `0x180069470`
- `0x18006aa2c`
- `0x18006af4c`
- `0x18006b998`
- `0x180079b8c`
- `0x18007fb5c`
- `0x180080030`
- `0x1800809d0`
- `0x1800853e0`
- `0x180089fa0`
- `0x18008c840`
- `0x1800924e8`
- `0x180092850`
- `0x18009351c`
- `0x18009f730`
- `0x1800a0e60`
- `0x1800a4c30`
- `0x1800a8c80`
- `0x1800adb0c`
- `0x1800ae33c`
- `0x1800ba7a8`
- `0x1800c2020`
- `0x1800c8180`
- `0x180105f50`
- `0x18010674c`
- `0x18010cb40`
- `0x18010d700`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x180186e3b`
- `MpClient!MpFreeMemory` at `0x180186e3b`
- `KERNEL32!GetFileSize` at `0x18018727f`
- `KERNEL32!GetFileSize` at `0x18018727f`
- `KERNEL32!CloseHandle` at `0x180187162`
- `KERNEL32!CloseHandle` at `0x18018723f`
- `KERNEL32!CloseHandle` at `0x1801872a3`
- `KERNEL32!CloseHandle` at `0x180187380`
- `KERNEL32!CloseHandle` at `0x18018741c`
- `KERNEL32!CloseHandle` at `0x1801878bd`
- `KERNEL32!CloseHandle` at `0x180187b08`
- `KERNEL32!CloseHandle` at `0x180187cad`
- `KERNEL32!CloseHandle` at `0x180188793`
- `KERNEL32!CloseHandle` at `0x180187162`
- `KERNEL32!CloseHandle` at `0x18018723f`
- `KERNEL32!CloseHandle` at `0x1801872a3`
- `KERNEL32!CloseHandle` at `0x180187380`
- `KERNEL32!CloseHandle` at `0x18018741c`
- `KERNEL32!CloseHandle` at `0x1801878bd`
- `KERNEL32!CloseHandle` at `0x180187b08`
- `KERNEL32!CloseHandle` at `0x180187cad`
- `KERNEL32!CloseHandle` at `0x180188793`
- `KERNEL32!DebugBreak` at `0x180186da7`
- `KERNEL32!DebugBreak` at `0x180186da7`
- `ADVAPI32!RevertToSelf` at `0x1801871a2`
- `ADVAPI32!RevertToSelf` at `0x1801871a2`

## string_xrefs

- `0x180186d43`: `MpDlp_DebugCheckAccessForBrowsersPath`

## pseudocode

```c

```
