# Util::ProvisionDefaultPrinter(ushort const *)

- ea: `0x1400111bc`
- end: `0x140011300`
- name: `?ProvisionDefaultPrinter@Util@@YAJPEBG@Z`
- size: `324`
- prototype: `__int64 __fastcall(Util *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000d064`

## callees

- `0x140002600`
- `0x1400034f8`
- `0x140004e30`
- `0x14000b470`
- `0x140010f8c`
- `0x1400111bc`
- `0x140011308`
- `0x140011450`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14001125b`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z` at `0x14001125b`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1400111f5`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14001126b`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x1400111f5`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14001126b`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x1400111df`
- `msvcp_win!?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A` at `0x140011243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011299`
- `CFGMGR32!CMP_WaitNoPendingInstallEvents` at `0x140011200`
- `CFGMGR32!CMP_WaitNoPendingInstallEvents` at `0x140011200`
- `ext-ms-win-printer-winspool-l1-1-4!SetDefaultPrinterW` at `0x14001128f`
- `ext-ms-win-printer-winspool-l1-1-4!SetDefaultPrinterW` at `0x14001128f`

## string_xrefs

- `0x1400111d8`: `Waiting for pending installations to complete...`
- `0x14001124a`: `CMP_WaitNoPendingInstallEvents failed with CONFIGRET=%u.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Util::ProvisionDefaultPrinter(Util *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  void *v4; // rdx
  DWORD v5; // ebx
  unsigned int v6; // r8d
  const char *v7; // r9
  __int64 v8; // rax
  __int64 v9; // rax
  const WCHAR *v10; // rcx
  DWORD LastError; // eax
  LPCWSTR *v12; // rdx
  unsigned int LastErrorMsg; // ebx
  int v15; // [rsp+20h] [rbp-48h]
  LPCWSTR pszPrinter[3]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int64 v17; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
         std::wcout,
         L"Waiting for pending installations to complete...");
  std::basic_ostream<unsigned short>::operator<<(v3, std::endl<unsigned short,std::char_traits<unsigned short>>);
  v5 = CMP_WaitNoPendingInstallEvents(0x1D4C0u);
  switch ( v5 )
  {
    case 0xFFFFFFFF:
      wil::details::in1diag3::_Log_GetLastError(retaddr, v4, v6, v7);
      break;
    case 0x102u:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\util.cpp",
        (const char *)0x800705B4LL,
        v15);
      break;
    case 0u:
      goto LABEL_7;
  }
  v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
         std::wcout,
         L"CMP_WaitNoPendingInstallEvents failed with CONFIGRET=%u.");
  v9 = std::basic_ostream<unsigned short>::operator<<(v8, v5);
  std::basic_ostream<unsigned short>::operator<<(v9, std::endl<unsigned short,std::char_traits<unsigned short>>);
LABEL_7:
  Util::GetPrintQueueName(pszPrinter, this);
  v10 = (const WCHAR *)pszPrinter;
  if ( v17 > 7 )
    v10 = pszPrinter[0];
  if ( SetDefaultPrinterW(v10) )
  {
    LastErrorMsg = 0;
  }
  else
  {
    LastError = GetLastError();
    v12 = pszPrinter;
    if ( v17 > 7 )
      v12 = (LPCWSTR *)pszPrinter[0];
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x60,
                     (unsigned int)"onecoreuap\\printscan\\print\\edu\\printprov\\util.cpp",
                     "SetDefaultPrinter failed for %ws, GLE = %u",
                     (const char *)v12,
                     LastError);
  }
  std::wstring::~wstring(pszPrinter);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x1400111bc  mov     [rsp+arg_8], rbx
0x1400111c1  push    rdi
0x1400111c2  sub     rsp, 60h
0x1400111c6  mov     rax, cs:__security_cookie
0x1400111cd  xor     rax, rsp
0x1400111d0  mov     [rsp+68h+var_18], rax
0x1400111d5  mov     rdi, rcx
0x1400111d8  lea     rdx, aWaitingForPend; "Waiting for pending installations to co"...
0x1400111df  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x1400111e6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1400111eb  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x1400111f2  mov     rcx, rax
0x1400111f5  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x1400111fb  mov     ecx, 1D4C0h; dwTimeout
0x140011200  call    cs:__imp_CMP_WaitNoPendingInstallEvents
0x140011206  mov     ebx, eax
0x140011208  cmp     eax, 0FFFFFFFFh
0x14001120b  jnz     short loc_140011219
0x14001120d  mov     rcx, [rsp+68h]; this
0x140011212  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140011217  jmp     short loc_140011243
0x140011219  cmp     ebx, 102h
0x14001121f  jnz     short loc_14001123F
0x140011221  mov     rcx, [rsp+68h]; this
0x140011226  lea     r8, aOnecoreuapPrin_2; "onecoreuap\\printscan\\print\\edu\\prin"...
0x14001122d  mov     r9d, 800705B4h; char *
0x140011233  mov     edx, 58h ; 'X'; void *
0x140011238  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001123d  jmp     short loc_140011243
0x14001123f  test    ebx, ebx
0x140011241  jz      short loc_140011271
0x140011243  mov     rcx, cs:__imp_?wcout@std@@3V?$basic_ostream@GU?$char_traits@G@std@@@1@A; std::basic_ostream<ushort> std::wcout
0x14001124a  lea     rdx, aCmpWaitnopendi; "CMP_WaitNoPendingInstallEvents failed w"...
0x140011251  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140011256  mov     edx, ebx
0x140011258  mov     rcx, rax
0x14001125b  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@K@Z; std::basic_ostream<ushort>::operator<<(ulong)
0x140011261  mov     rcx, rax
0x140011264  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14001126b  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x140011271  mov     rdx, rdi
0x140011274  lea     rcx, [rsp+68h+pszPrinter]
0x140011279  call    ?GetPrintQueueName@Util@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Util::GetPrintQueueName(ushort const *)
0x14001127e  cmp     [rsp+68h+var_20], 7
0x140011284  lea     rcx, [rsp+68h+pszPrinter]
0x140011289  cmova   rcx, [rsp+68h+pszPrinter]; pszPrinter
0x14001128f  call    cs:__imp_SetDefaultPrinterW
0x140011295  test    eax, eax
0x140011297  jnz     short loc_1400112DA
0x140011299  call    cs:__imp_GetLastError
0x14001129f  cmp     [rsp+68h+var_20], 7
0x1400112a5  lea     rdx, [rsp+68h+pszPrinter]
0x1400112aa  mov     rcx, [rsp+68h]; this
0x1400112af  lea     r9, aSetdefaultprin_0; "SetDefaultPrinter failed for %ws, GLE ="...
0x1400112b6  cmova   rdx, [rsp+68h+pszPrinter]
0x1400112bc  lea     r8, aOnecoreuapPrin_2; "onecoreuap\\printscan\\print\\edu\\prin"...
0x1400112c3  mov     [rsp+68h+var_40], eax
0x1400112c7  mov     [rsp+68h+var_48], rdx; char *
0x1400112cc  mov     edx, 60h ; '`'; void *
0x1400112d1  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1400112d6  mov     ebx, eax
0x1400112d8  jmp     short loc_1400112DC
0x1400112da  xor     ebx, ebx
0x1400112dc  lea     rcx, [rsp+68h+pszPrinter]
0x1400112e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400112e6  mov     eax, ebx
0x1400112e8  mov     rcx, [rsp+68h+var_18]
0x1400112ed  xor     rcx, rsp; StackCookie
0x1400112f0  call    __security_check_cookie
0x1400112f5  mov     rbx, [rsp+68h+arg_8]
0x1400112fa  add     rsp, 60h
0x1400112fe  pop     rdi
0x1400112ff  retn
```
