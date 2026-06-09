# DsrCmdStatusHelper::GetIEProxyConfig(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG &)

- ea: `0x180043480`
- end: `0x18004369e`
- name: `?GetIEProxyConfig@DsrCmdStatusHelper@@CAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a7e8`
- `0x1800a523c`

## callees

- `0x18001378c`
- `0x180016190`
- `0x180016ae0`
- `0x180016b90`
- `0x1800292ac`
- `0x180029554`
- `0x18002b9b4`
- `0x18002b9f4`
- `0x18002deec`
- `0x180043480`
- `0x180044300`
- `0x1800a1f4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800435eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800435eb`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18004362a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18004362a`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x180043635`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z` at `0x180043635`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800434bc`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800434bc`

## string_xrefs

- `0x180043600`: `Failed trying to get Current User IE proxy config with error code: `
- `0x180043518`: `Auto-Configuration URL`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DsrCmdStatusHelper::GetIEProxyConfig(__int64 a1, WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *a2)
{
  unsigned int v4; // edi
  bool fAutoDetect; // bl
  __int64 v6; // r8
  _QWORD *MsgRow; // rax
  LPWSTR lpszAutoConfigUrl; // rbx
  _QWORD *v9; // rax
  LPWSTR lpszProxy; // rbx
  _QWORD *v11; // rax
  LPWSTR lpszProxyBypass; // rbx
  _QWORD *v13; // rax
  signed int LastError; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  _BYTE v20[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[232]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v22[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v23[32]; // [rsp+140h] [rbp+40h] BYREF

  std::basic_ostringstream<unsigned short>::basic_ostringstream<unsigned short>((__int64)v20);
  if ( WinHttpGetIEProxyConfigForCurrentUser(a2) )
  {
    v4 = 0;
    fAutoDetect = a2->fAutoDetect;
    std::wstring::wstring((__int64)v22, (__int64)L"Auto Detect Settings");
    LOBYTE(v6) = fAutoDetect;
    MsgRow = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v23, v22, v6);
    std::operator<<<unsigned short>((__int64)v20, MsgRow);
    std::wstring::_Tidy_deallocate((__int64)v23);
    std::wstring::_Tidy_deallocate((__int64)v22);
    lpszAutoConfigUrl = a2->lpszAutoConfigUrl;
    std::wstring::wstring((__int64)v22, (__int64)L"Auto-Configuration URL");
    v9 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v23, v22, lpszAutoConfigUrl);
    std::operator<<<unsigned short>((__int64)v20, v9);
    std::wstring::_Tidy_deallocate((__int64)v23);
    std::wstring::_Tidy_deallocate((__int64)v22);
    lpszProxy = a2->lpszProxy;
    std::wstring::wstring((__int64)v22, (__int64)L"Proxy Server List");
    v11 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v23, v22, lpszProxy);
    std::operator<<<unsigned short>((__int64)v20, v11);
    std::wstring::_Tidy_deallocate((__int64)v23);
    std::wstring::_Tidy_deallocate((__int64)v22);
    lpszProxyBypass = a2->lpszProxyBypass;
    std::wstring::wstring((__int64)v22, (__int64)L"Proxy Bypass List");
    v13 = (_QWORD *)DsrCmdStatusHelper::CreateMsgRow(v23, v22, lpszProxyBypass);
    std::operator<<<unsigned short>((__int64)v20, v13);
    std::wstring::_Tidy_deallocate((__int64)v23);
    std::wstring::_Tidy_deallocate((__int64)v22);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v15 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
            (__int64)v20,
            (__int64)L"Failed trying to get Current User IE proxy config with error code: ");
    v16 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, (__int64)L"0x");
    v17 = std::basic_ostream<unsigned short>::operator<<(v16, std::hex);
    v18 = std::basic_ostream<unsigned short>::operator<<(v17, v4);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v18, (__int64)L"\n");
  }
  std::basic_stringbuf<unsigned short>::str(v21, v22);
  std::wstring::operator=(a1, (__int64)v22);
  std::wstring::_Tidy_deallocate((__int64)v22);
  std::basic_ostringstream<unsigned short>::`vbase destructor'((__int64)v20);
  return v4;
}

```

## disassembly

```asm
0x180043480  mov     [rsp-8+arg_10], rbx
0x180043485  mov     [rsp-8+arg_18], rsi
0x18004348a  push    rbp
0x18004348b  push    rdi
0x18004348c  push    r14
0x18004348e  lea     rbp, [rsp-70h]
0x180043493  sub     rsp, 170h
0x18004349a  mov     rax, cs:__security_cookie
0x1800434a1  xor     rax, rsp
0x1800434a4  mov     [rbp+80h+var_20], rax
0x1800434a8  mov     rsi, rdx
0x1800434ab  mov     r14, rcx
0x1800434ae  lea     rcx, [rsp+180h+var_150]
0x1800434b3  call    ??0?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_ostringstream<ushort>::basic_ostringstream<ushort>(void)
0x1800434b8  nop
0x1800434b9  mov     rcx, rsi; pProxyConfig
0x1800434bc  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800434c2  test    eax, eax
0x1800434c4  jz      loc_1800435EB
0x1800434ca  xor     edi, edi
0x1800434cc  cmp     [rsi], edi
0x1800434ce  setnz   bl
0x1800434d1  lea     rdx, aAutoDetectSett; "Auto Detect Settings"
0x1800434d8  lea     rcx, [rbp+80h+var_60]
0x1800434dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800434e1  nop
0x1800434e2  mov     r8b, bl
0x1800434e5  lea     rdx, [rbp+80h+var_60]
0x1800434e9  lea     rcx, [rbp+80h+var_40]
0x1800434ed  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@_N@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,bool)
0x1800434f2  nop
0x1800434f3  mov     rdx, rax
0x1800434f6  lea     rcx, [rsp+180h+var_150]
0x1800434fb  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180043500  nop
0x180043501  lea     rcx, [rbp+80h+var_40]
0x180043505  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004350a  nop
0x18004350b  lea     rcx, [rbp+80h+var_60]
0x18004350f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043514  mov     rbx, [rsi+8]
0x180043518  lea     rdx, aAutoConfigurat; "Auto-Configuration URL"
0x18004351f  lea     rcx, [rbp+80h+var_60]
0x180043523  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043528  nop
0x180043529  mov     r8, rbx
0x18004352c  lea     rdx, [rbp+80h+var_60]
0x180043530  lea     rcx, [rbp+80h+var_40]
0x180043534  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180043539  nop
0x18004353a  mov     rdx, rax
0x18004353d  lea     rcx, [rsp+180h+var_150]
0x180043542  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x180043547  nop
0x180043548  lea     rcx, [rbp+80h+var_40]
0x18004354c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043551  nop
0x180043552  lea     rcx, [rbp+80h+var_60]
0x180043556  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004355b  mov     rbx, [rsi+10h]
0x18004355f  lea     rdx, aProxyServerLis; "Proxy Server List"
0x180043566  lea     rcx, [rbp+80h+var_60]
0x18004356a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004356f  nop
0x180043570  mov     r8, rbx
0x180043573  lea     rdx, [rbp+80h+var_60]
0x180043577  lea     rcx, [rbp+80h+var_40]
0x18004357b  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x180043580  nop
0x180043581  mov     rdx, rax
0x180043584  lea     rcx, [rsp+180h+var_150]
0x180043589  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x18004358e  nop
0x18004358f  lea     rcx, [rbp+80h+var_40]
0x180043593  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043598  nop
0x180043599  lea     rcx, [rbp+80h+var_60]
0x18004359d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800435a2  mov     rbx, [rsi+18h]
0x1800435a6  lea     rdx, aProxyBypassLis; "Proxy Bypass List"
0x1800435ad  lea     rcx, [rbp+80h+var_60]
0x1800435b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800435b6  nop
0x1800435b7  mov     r8, rbx
0x1800435ba  lea     rdx, [rbp+80h+var_60]
0x1800435be  lea     rcx, [rbp+80h+var_40]
0x1800435c2  call    ?CreateMsgRow@DsrCmdStatusHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@PEBG@Z; DsrCmdStatusHelper::CreateMsgRow(std::wstring const &,ushort const *)
0x1800435c7  nop
0x1800435c8  mov     rdx, rax
0x1800435cb  lea     rcx, [rsp+180h+var_150]
0x1800435d0  call    ??$?6GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::operator<<<ushort>(std::basic_ostream<ushort> &,std::wstring const &)
0x1800435d5  nop
0x1800435d6  lea     rcx, [rbp+80h+var_40]
0x1800435da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800435df  nop
0x1800435e0  lea     rcx, [rbp+80h+var_60]
0x1800435e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800435e9  jmp     short loc_18004364A
0x1800435eb  call    cs:__imp_GetLastError
0x1800435f1  mov     edi, eax
0x1800435f3  test    eax, eax
0x1800435f5  jle     short loc_180043600
0x1800435f7  movzx   edi, ax
0x1800435fa  or      edi, 80070000h
0x180043600  lea     rdx, aFailedTryingTo_2; "Failed trying to get Current User IE pr"...
0x180043607  lea     rcx, [rsp+180h+var_150]
0x18004360c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180043611  mov     rcx, rax
0x180043614  lea     rdx, a0x; "0x"
0x18004361b  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180043620  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180043627  mov     rcx, rax
0x18004362a  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x180043630  mov     edx, edi
0x180043632  mov     rcx, rax
0x180043635  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@J@Z; std::basic_ostream<ushort>::operator<<(long)
0x18004363b  mov     rcx, rax
0x18004363e  lea     rdx, asc_1800C6838; "\n"
0x180043645  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18004364a  lea     rdx, [rbp+80h+var_60]
0x18004364e  lea     rcx, [rsp+180h+var_148]
0x180043653  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180043658  lea     rdx, [rbp+80h+var_60]
0x18004365c  mov     rcx, r14
0x18004365f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180043664  lea     rcx, [rbp+80h+var_60]
0x180043668  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004366d  nop
0x18004366e  lea     rcx, [rsp+180h+var_150]
0x180043673  call    ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
0x180043678  mov     eax, edi
0x18004367a  mov     rcx, [rbp+80h+var_20]
0x18004367e  xor     rcx, rsp; StackCookie
0x180043681  call    __security_check_cookie
0x180043686  lea     r11, [rsp+180h+var_10]
0x18004368e  mov     rbx, [r11+30h]
0x180043692  mov     rsi, [r11+38h]
0x180043696  mov     rsp, r11
0x180043699  pop     r14
0x18004369b  pop     rdi
0x18004369c  pop     rbp
0x18004369d  retn
```
