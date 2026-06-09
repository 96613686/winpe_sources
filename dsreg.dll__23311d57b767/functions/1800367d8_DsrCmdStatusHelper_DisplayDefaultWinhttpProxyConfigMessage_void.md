# DsrCmdStatusHelper::DisplayDefaultWinhttpProxyConfigMessage(void)

- ea: `0x1800367d8`
- end: `0x180036adf`
- name: `?DisplayDefaultWinhttpProxyConfigMessage@DsrCmdStatusHelper@@CAXXZ`
- size: `775`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1800a523c`

## callees

- `0x180012c7c`
- `0x18001378c`
- `0x180015f3c`
- `0x180016190`
- `0x180016ae0`
- `0x18002927c`
- `0x1800292ac`
- `0x180029554`
- `0x18002b9b4`
- `0x18002b9f4`
- `0x18002deec`
- `0x1800367d8`
- `0x180044300`
- `0x180046ae8`
- `0x180046b3c`
- `0x1800a1dd8`
- `0x1800a23d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800369c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800369c5`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180036a04`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180036a04`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x180036a0f`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x180036a0f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003696d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800369bd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003696d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800369bd`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800368a7`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800368a7`

## string_xrefs

- `0x1800369da`: `Failed trying to get default WinHTTP proxy config with error code: `
- `0x1800368c5`: `Access Type`
- `0x180036822`: `WinHttp Default Proxy Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void DsrCmdStatusHelper::DisplayDefaultWinhttpProxyConfigMessage(void)
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v3; // rdx
  _QWORD *v4; // rax
  __int64 v5; // rdx
  const wchar_t *v6; // rbx
  __int64 v7; // rax
  const wchar_t *v8; // rcx
  __int64 v9; // rbx
  _QWORD *MsgRow; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  signed int LastError; // eax
  unsigned int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  const wchar_t *v25; // rbx
  __int64 v26; // rax
  const wchar_t *v27; // rcx
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v29[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[232]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v31[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v32; // [rsp+148h] [rbp+48h]
  wchar_t *Format[3]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v34; // [rsp+168h] [rbp+68h]
  _BYTE v35[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v36[32]; // [rsp+190h] [rbp+90h] BYREF

  std::wstring::wstring((__int64)Format);
  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v29);
  memset(&pProxyInfo, 0, sizeof(pProxyInfo));
  std::wstring::wstring((__int64)v31, (__int64)L"WinHttp Default Proxy Config");
  DsrCmdStatusHelper::GetDisplayHeader(v31, Format);
  std::wstring::_Tidy_deallocate((__int64)v31);
  CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v1, v0);
  if ( *(_BYTE *)(*CurrentRef + 12LL) )
  {
    v4 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v3);
    if ( *(_QWORD *)(*v4 + 184LL) )
    {
      v6 = (const wchar_t *)Format;
      if ( v34 > 7 )
        v6 = Format[0];
      v7 = CmdOptions::GetCurrentRef(*v4, v5);
      fwprintf_s(*(FILE *const *)(*(_QWORD *)v7 + 184LL), v6);
    }
  }
  v8 = (const wchar_t *)Format;
  if ( v34 > 7 )
    v8 = Format[0];
  wprintf(v8);
  if ( WinHttpGetDefaultProxyConfiguration(&pProxyInfo) )
  {
    v9 = AccessTypeToString(v35, pProxyInfo.dwAccessType);
    std::wstring::wstring((__int64)v31, (__int64)L"Access Type");
    MsgRow = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v36, v31, v9);
    std::operator<<<unsigned short>((__int64)v29, MsgRow);
    std::wstring::_Tidy_deallocate((__int64)v36);
    std::wstring::_Tidy_deallocate((__int64)v31);
    std::wstring::_Tidy_deallocate((__int64)v35);
    if ( pProxyInfo.dwAccessType != 1 )
    {
      std::wstring::wstring((__int64)v31, (__int64)L"Proxy Server List");
      v13 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v35, v31, pProxyInfo.lpszProxy);
      std::operator<<<unsigned short>((__int64)v29, v13);
      std::wstring::_Tidy_deallocate((__int64)v35);
      std::wstring::_Tidy_deallocate((__int64)v31);
      GlobalFree(pProxyInfo.lpszProxy);
      std::wstring::wstring((__int64)v31, (__int64)L"Proxy Bypass List");
      v14 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v35, v31, pProxyInfo.lpszProxyBypass);
      std::operator<<<unsigned short>((__int64)v29, v14);
      std::wstring::_Tidy_deallocate((__int64)v35);
      std::wstring::_Tidy_deallocate((__int64)v31);
      GlobalFree(pProxyInfo.lpszProxyBypass);
    }
  }
  else
  {
    LastError = GetLastError();
    v16 = LastError;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    v17 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64)v29,
            (__int64)L"Failed trying to get default WinHTTP proxy config with error code: ");
    v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, (__int64)L"0x");
    v19 = std::basic_ostream<unsigned short>::operator<<(v18, std::hex);
    v20 = std::basic_ostream<unsigned short>::operator<<(v19, v16);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v20, (__int64)L"\n");
  }
  v21 = (_QWORD *)CmdOptions::GetCurrentRef(v12, v11);
  if ( *(_BYTE *)(*v21 + 12LL) && *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v21, v22) + 184LL) )
  {
    std::basic_stringbuf<unsigned short>::str(v30, v31);
    v25 = (const wchar_t *)v31;
    if ( v32 > 7 )
      v25 = v31[0];
    v26 = CmdOptions::GetCurrentRef(v24, v23);
    fwprintf_s(*(FILE *const *)(*(_QWORD *)v26 + 184LL), v25);
    std::wstring::_Tidy_deallocate((__int64)v31);
  }
  std::basic_stringbuf<unsigned short>::str(v30, v31);
  v27 = (const wchar_t *)v31;
  if ( v32 > 7 )
    v27 = v31[0];
  wprintf(v27);
  std::wstring::_Tidy_deallocate((__int64)v31);
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v29);
  std::wstring::_Tidy_deallocate((__int64)Format);
}

```

## disassembly

```asm
0x1800367d8  mov     [rsp-8+arg_0], rbx
0x1800367dd  push    rbp
0x1800367de  lea     rbp, [rsp-0C0h]
0x1800367e6  sub     rsp, 1C0h
0x1800367ed  mov     rax, cs:__security_cookie
0x1800367f4  xor     rax, rsp
0x1800367f7  mov     [rbp+0C0h+var_10], rax
0x1800367fe  lea     rcx, [rbp+0C0h+Format]
0x180036802  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180036807  nop
0x180036808  lea     rcx, [rsp+1C0h+var_180]
0x18003680d  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x180036812  nop
0x180036813  xorps   xmm0, xmm0
0x180036816  xor     eax, eax
0x180036818  movups  xmmword ptr [rsp+1C0h+pProxyInfo.dwAccessType], xmm0
0x18003681d  mov     [rsp+1C0h+pProxyInfo.lpszProxyBypass], rax
0x180036822  lea     rdx, aWinhttpDefault; "WinHttp Default Proxy Config"
0x180036829  lea     rcx, [rbp+0C0h+var_90]
0x18003682d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180036832  nop
0x180036833  lea     rdx, [rbp+0C0h+Format]
0x180036837  lea     rcx, [rbp+0C0h+var_90]
0x18003683b  call    ?GetDisplayHeader@DsrCmdStatusHelper@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; DsrCmdStatusHelper::GetDisplayHeader(std::wstring const &,std::wstring &)
0x180036840  nop
0x180036841  lea     rcx, [rbp+0C0h+var_90]
0x180036845  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003684a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003684f  mov     rcx, [rax]
0x180036852  cmp     byte ptr [rcx+0Ch], 0
0x180036856  jz      short loc_18003688F
0x180036858  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003685d  mov     rcx, [rax]
0x180036860  cmp     qword ptr [rcx+0B8h], 0
0x180036868  jz      short loc_18003688F
0x18003686a  lea     rbx, [rbp+0C0h+Format]
0x18003686e  cmp     [rbp+0C0h+var_58], 7
0x180036873  cmova   rbx, [rbp+0C0h+Format]
0x180036878  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003687d  mov     rcx, [rax]
0x180036880  mov     rdx, rbx; Format
0x180036883  mov     rcx, [rcx+0B8h]; Stream
0x18003688a  call    fwprintf_s
0x18003688f  lea     rcx, [rbp+0C0h+Format]
0x180036893  cmp     [rbp+0C0h+var_58], 7
0x180036898  cmova   rcx, [rbp+0C0h+Format]; Format
0x18003689d  call    wprintf
0x1800368a2  lea     rcx, [rsp+1C0h+pProxyInfo]; pProxyInfo
0x1800368a7  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x1800368ad  test    eax, eax
0x1800368af  jz      loc_1800369C5
0x1800368b5  mov     edx, [rsp+1C0h+pProxyInfo.dwAccessType]
0x1800368b9  lea     rcx, [rbp+0C0h+var_50]
0x1800368bd  call    AccessTypeToString
0x1800368c2  mov     rbx, rax
0x1800368c5  lea     rdx, aAccessType; "Access Type"
0x1800368cc  lea     rcx, [rbp+0C0h+var_90]
0x1800368d0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800368d5  nop
0x1800368d6  mov     r8, rbx
0x1800368d9  lea     rdx, [rbp+0C0h+var_90]
0x1800368dd  lea     rcx, [rbp+0C0h+var_30]
0x1800368e4  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@0@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,std::wstring const &)
0x1800368e9  nop
0x1800368ea  mov     rdx, rax
0x1800368ed  lea     rcx, [rsp+1C0h+var_180]
0x1800368f2  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800368f7  nop
0x1800368f8  lea     rcx, [rbp+0C0h+var_30]
0x1800368ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036904  nop
0x180036905  lea     rcx, [rbp+0C0h+var_90]
0x180036909  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003690e  nop
0x18003690f  lea     rcx, [rbp+0C0h+var_50]
0x180036913  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036918  cmp     [rsp+1C0h+pProxyInfo.dwAccessType], 1
0x18003691d  jz      loc_180036A24
0x180036923  lea     rdx, aProxyServerLis; "Proxy Server List"
0x18003692a  lea     rcx, [rbp+0C0h+var_90]
0x18003692e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180036933  nop
0x180036934  mov     r8, [rsp+1C0h+pProxyInfo.lpszProxy]
0x180036939  lea     rdx, [rbp+0C0h+var_90]
0x18003693d  lea     rcx, [rbp+0C0h+var_50]
0x180036941  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180036946  nop
0x180036947  mov     rdx, rax
0x18003694a  lea     rcx, [rsp+1C0h+var_180]
0x18003694f  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180036954  nop
0x180036955  lea     rcx, [rbp+0C0h+var_50]
0x180036959  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003695e  nop
0x18003695f  lea     rcx, [rbp+0C0h+var_90]
0x180036963  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036968  mov     rcx, [rsp+1C0h+pProxyInfo.lpszProxy]; hMem
0x18003696d  call    cs:__imp_GlobalFree
0x180036973  lea     rdx, aProxyBypassLis; "Proxy Bypass List"
0x18003697a  lea     rcx, [rbp+0C0h+var_90]
0x18003697e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180036983  nop
0x180036984  mov     r8, [rsp+1C0h+pProxyInfo.lpszProxyBypass]
0x180036989  lea     rdx, [rbp+0C0h+var_90]
0x18003698d  lea     rcx, [rbp+0C0h+var_50]
0x180036991  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180036996  nop
0x180036997  mov     rdx, rax
0x18003699a  lea     rcx, [rsp+1C0h+var_180]
0x18003699f  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800369a4  nop
0x1800369a5  lea     rcx, [rbp+0C0h+var_50]
0x1800369a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800369ae  nop
0x1800369af  lea     rcx, [rbp+0C0h+var_90]
0x1800369b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800369b8  mov     rcx, [rsp+1C0h+pProxyInfo.lpszProxyBypass]; hMem
0x1800369bd  call    cs:__imp_GlobalFree
0x1800369c3  jmp     short loc_180036A24
0x1800369c5  call    cs:__imp_GetLastError
0x1800369cb  mov     ebx, eax
0x1800369cd  test    eax, eax
0x1800369cf  jle     short loc_1800369DA
0x1800369d1  movzx   ebx, ax
0x1800369d4  or      ebx, 80070000h
0x1800369da  lea     rdx, aFailedTryingTo; "Failed trying to get default WinHTTP pr"...
0x1800369e1  lea     rcx, [rsp+1C0h+var_180]
0x1800369e6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800369eb  mov     rcx, rax
0x1800369ee  lea     rdx, a0x; "0x"
0x1800369f5  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800369fa  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180036a01  mov     rcx, rax
0x180036a04  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x180036a0a  mov     edx, ebx
0x180036a0c  mov     rcx, rax
0x180036a0f  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x180036a15  mov     rcx, rax
0x180036a18  lea     rdx, asc_1800C6838; "\n"
0x180036a1f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180036a24  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180036a29  mov     rcx, [rax]
0x180036a2c  cmp     byte ptr [rcx+0Ch], 0
0x180036a30  jz      short loc_180036A80
0x180036a32  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180036a37  mov     rax, [rax]
0x180036a3a  cmp     qword ptr [rax+0B8h], 0
0x180036a42  jz      short loc_180036A80
0x180036a44  lea     rdx, [rbp+0C0h+var_90]
0x180036a48  lea     rcx, [rsp+1C0h+var_178]
0x180036a4d  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180036a52  lea     rbx, [rbp+0C0h+var_90]
0x180036a56  cmp     [rbp+0C0h+var_78], 7
0x180036a5b  cmova   rbx, [rbp+0C0h+var_90]
0x180036a60  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180036a65  mov     rcx, [rax]
0x180036a68  mov     rdx, rbx; Format
0x180036a6b  mov     rcx, [rcx+0B8h]; Stream
0x180036a72  call    fwprintf_s
0x180036a77  lea     rcx, [rbp+0C0h+var_90]
0x180036a7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036a80  lea     rdx, [rbp+0C0h+var_90]
0x180036a84  lea     rcx, [rsp+1C0h+var_178]
0x180036a89  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180036a8e  lea     rcx, [rbp+0C0h+var_90]
0x180036a92  cmp     [rbp+0C0h+var_78], 7
0x180036a97  cmova   rcx, [rbp+0C0h+var_90]; Format
0x180036a9c  call    wprintf
0x180036aa1  lea     rcx, [rbp+0C0h+var_90]
0x180036aa5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036aaa  nop
0x180036aab  lea     rcx, [rsp+1C0h+var_180]
0x180036ab0  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x180036ab5  nop
0x180036ab6  lea     rcx, [rbp+0C0h+Format]
0x180036aba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036abf  mov     rcx, [rbp+0C0h+var_10]
0x180036ac6  xor     rcx, rsp; StackCookie
0x180036ac9  call    __security_check_cookie
0x180036ace  mov     rbx, [rsp+1C0h+arg_0]
0x180036ad6  add     rsp, 1C0h
0x180036add  pop     rbp
0x180036ade  retn
```
