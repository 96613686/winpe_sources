# CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)

- ea: `0x140017b80`
- end: `0x140017eab`
- name: `?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z`
- size: `811`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, __int64, const wchar_t *, unsigned int *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x140013288`
- `0x140015890`
- `0x1400237c0`
- `0x140023880`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006984`
- `0x140006c50`
- `0x14000952c`
- `0x140012a2c`
- `0x140017af0`
- `0x140017b80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140017d89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140017d89`

## string_xrefs

- `0x140017ce4`: `Failed to open the registry root: n/a, key: {}.`
- `0x140017db7`: `Failed to query registry value: {}`
- `0x140017e28`: `Registry value is not a DWORD type.`

## pseudocode

```c
__int64 __fastcall CbsRegQueryDWORDValue(HKEY a1, const wchar_t *a2, __int64 a3, const wchar_t *a4, unsigned int *a5)
{
  const WCHAR *v5; // rax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  HKEY v10; // rcx
  LSTATUS v11; // eax
  LSTATUS v12; // ebx
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rdx
  int lpData; // [rsp+20h] [rbp-60h]
  unsigned int lpDataa; // [rsp+20h] [rbp-60h]
  int v22[2]; // [rsp+30h] [rbp-50h] BYREF
  const wchar_t *v23; // [rsp+38h] [rbp-48h] BYREF
  const wchar_t *v24; // [rsp+40h] [rbp-40h] BYREF
  int v25; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v26[2]; // [rsp+50h] [rbp-30h] BYREF
  DWORD Type; // [rsp+58h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-24h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v5 = a4;
  v23 = a4;
  v24 = a2;
  if ( a4 )
  {
    if ( !a5 )
    {
      v6 = -2147467261;
      v25 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value result specified");
        *(_QWORD *)v26 = &v25;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v9,
          3,
          (__int64)": {}",
          (__int64)v26);
      }
      v8 = 355;
      goto LABEL_5;
    }
    hKey = 0;
    v10 = HKEY_LOCAL_MACHINE;
    if ( a2 )
    {
      v11 = CbsRegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, a3, 0x20019u, &hKey);
      v12 = v11;
      if ( v11 == 2 || v11 == 3 )
      {
        v6 = (unsigned __int16)v11 | 0x80070000;
LABEL_37:
        Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
        return v6;
      }
      if ( v11 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to open the registry root: n/a, key: {}.",
            (__int64)&v24);
          if ( v12 > 0 )
            v14 = (unsigned __int16)v12 | 0x80070000;
          else
            v14 = v12;
          v25 = v14;
          *(_QWORD *)v26 = &v25;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v13,
            3,
            (__int64)": {0}",
            (__int64)v26);
        }
        v15 = 367;
LABEL_21:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v15,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
               (const char *)(unsigned int)v12,
               lpDataa);
        goto LABEL_37;
      }
      v10 = hKey;
      v5 = v23;
    }
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    v12 = RegQueryValueExW(v10, v5, 0, &Type, Data, &cbData);
    if ( v12 == 2 )
    {
      v6 = -2147024894;
      goto LABEL_37;
    }
    if ( !v12 )
    {
      if ( Type == 4 )
      {
        v6 = 0;
        *a5 = *(_DWORD *)Data;
      }
      else
      {
        v6 = -2147024883;
        v26[0] = -2147024883;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Registry value is not a DWORD type.");
          *(_QWORD *)v22 = v26;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v18,
            3,
            (__int64)": {}",
            (__int64)v22);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17E,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
          (const char *)0x8007000DLL,
          lpDataa);
      }
      goto LABEL_37;
    }
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to query registry value: {}",
        (__int64)&v23);
      if ( v12 > 0 )
        v17 = (unsigned __int16)v12 | 0x80070000;
      else
        v17 = v12;
      v25 = v17;
      *(_QWORD *)v22 = &v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v16,
        3,
        (__int64)": {0}",
        (__int64)v22);
    }
    v15 = 380;
    goto LABEL_21;
  }
  v6 = -2147024809;
  v25 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value name specified");
    *(_QWORD *)v26 = &v25;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v7,
      3,
      (__int64)": {}",
      (__int64)v26);
  }
  v8 = 354;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
    (const char *)v6,
    lpData);
  return v6;
}

```

## disassembly

```asm
0x140017b80  mov     [rsp-18h+arg_0], rbx
0x140017b85  push    rbp
0x140017b86  push    rsi
0x140017b87  push    rdi
0x140017b88  mov     rbp, rsp
0x140017b8b  sub     rsp, 80h
0x140017b92  mov     rax, cs:__security_cookie
0x140017b99  xor     rax, rsp
0x140017b9c  mov     [rbp+var_10], rax
0x140017ba0  mov     rsi, [rbp+arg_20]
0x140017ba4  mov     rax, r9
0x140017ba7  mov     [rbp+var_48], rax
0x140017bab  mov     [rbp+var_40], rdx
0x140017baf  test    r9, r9
0x140017bb2  jnz     short loc_140017C20
0x140017bb4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017bbb  mov     ebx, 80070057h
0x140017bc0  mov     [rbp+var_38], ebx
0x140017bc3  test    rcx, rcx
0x140017bc6  jz      short loc_140017C03
0x140017bc8  lea     edi, [rax+3]
0x140017bcb  xor     edx, edx
0x140017bcd  mov     r8d, edi
0x140017bd0  lea     r9, aNoValueNameSpe; "No value name specified"
0x140017bd7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017bdc  lea     rcx, [rbp+var_30]
0x140017be0  mov     r8d, edi
0x140017be3  mov     [rsp+80h+lpData], rcx; int
0x140017be8  lea     rax, [rbp+var_38]
0x140017bec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017bf3  lea     r9, asc_14002D4FC; ": {}"
0x140017bfa  mov     qword ptr [rbp+var_30], rax
0x140017bfe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017c03  mov     edx, 162h; void *
0x140017c08  mov     rcx, [rbp+18h]; this
0x140017c0c  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140017c13  mov     r9d, ebx; char *
0x140017c16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017c1b  jmp     loc_140017E8A
0x140017c20  test    rsi, rsi
0x140017c23  jnz     short loc_140017C7B
0x140017c25  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017c2c  mov     ebx, 80004003h
0x140017c31  mov     [rbp+var_38], ebx
0x140017c34  test    rcx, rcx
0x140017c37  jz      short loc_140017C74
0x140017c39  lea     edi, [rsi+3]
0x140017c3c  xor     edx, edx
0x140017c3e  mov     r8d, edi
0x140017c41  lea     r9, aNoValueResultS; "No value result specified"
0x140017c48  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017c4d  lea     rcx, [rbp+var_30]
0x140017c51  mov     r8d, edi
0x140017c54  mov     [rsp+80h+lpData], rcx
0x140017c59  lea     rax, [rbp+var_38]
0x140017c5d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017c64  lea     r9, asc_14002D4FC; ": {}"
0x140017c6b  mov     qword ptr [rbp+var_30], rax
0x140017c6f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017c74  mov     edx, 163h; wchar_t *
0x140017c79  jmp     short loc_140017C08
0x140017c7b  mov     [rbp+hKey], 0
0x140017c83  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x140017c8a  mov     edi, 3
0x140017c8f  test    rdx, rdx
0x140017c92  jz      loc_140017D58
0x140017c98  lea     rax, [rbp+hKey]
0x140017c9c  mov     r9d, 20019h; unsigned int
0x140017ca2  mov     [rsp+80h+lpData], rax; HKEY *
0x140017ca7  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x140017cac  mov     ebx, eax
0x140017cae  cmp     eax, 2
0x140017cb1  jz      short loc_140017CBF
0x140017cb3  cmp     eax, edi
0x140017cb5  jnz     short loc_140017CCD
0x140017cb7  test    eax, eax
0x140017cb9  jle     loc_140017E81
0x140017cbf  movzx   ebx, bx
0x140017cc2  or      ebx, 80070000h
0x140017cc8  jmp     loc_140017E81
0x140017ccd  test    ebx, ebx
0x140017ccf  jz      short loc_140017D50
0x140017cd1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017cd8  test    rcx, rcx
0x140017cdb  jz      short loc_140017D31
0x140017cdd  lea     rax, [rbp+var_40]
0x140017ce1  mov     r8d, edi
0x140017ce4  lea     r9, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x140017ceb  mov     [rsp+80h+lpData], rax
0x140017cf0  xor     edx, edx
0x140017cf2  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140017cf7  test    ebx, ebx
0x140017cf9  jg      short loc_140017CFF
0x140017cfb  mov     eax, ebx
0x140017cfd  jmp     short loc_140017D07
0x140017cff  movzx   eax, bx
0x140017d02  or      eax, 80070000h
0x140017d07  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017d0e  lea     r9, a0; ": {0}"
0x140017d15  mov     [rbp+var_38], eax
0x140017d18  mov     r8d, edi
0x140017d1b  lea     rax, [rbp+var_38]
0x140017d1f  mov     qword ptr [rbp+var_30], rax
0x140017d23  lea     rax, [rbp+var_30]
0x140017d27  mov     [rsp+80h+lpData], rax; unsigned int
0x140017d2c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017d31  mov     edx, 16Fh; void *
0x140017d36  mov     rcx, [rbp+18h]; this
0x140017d3a  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140017d41  mov     r9d, ebx; char *
0x140017d44  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140017d49  mov     ebx, eax
0x140017d4b  jmp     loc_140017E81
0x140017d50  mov     rcx, [rbp+hKey]; hKey
0x140017d54  mov     rax, [rbp+var_48]
0x140017d58  lea     rdx, [rbp+cbData]
0x140017d5c  mov     [rbp+Type], 0
0x140017d63  mov     [rsp+80h+lpcbData], rdx; lpcbData
0x140017d68  lea     r9, [rbp+Type]; lpType
0x140017d6c  lea     rdx, [rbp+Data]
0x140017d70  mov     dword ptr [rbp+Data], 0
0x140017d77  mov     [rsp+80h+lpData], rdx; lpData
0x140017d7c  xor     r8d, r8d; lpReserved
0x140017d7f  mov     rdx, rax; lpValueName
0x140017d82  mov     [rbp+cbData], 4
0x140017d89  call    cs:__imp_RegQueryValueExW
0x140017d8f  mov     ebx, eax
0x140017d91  cmp     eax, 2
0x140017d94  jnz     short loc_140017DA0
0x140017d96  mov     ebx, 80070002h
0x140017d9b  jmp     loc_140017E81
0x140017da0  test    ebx, ebx
0x140017da2  jz      short loc_140017E0E
0x140017da4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017dab  test    rcx, rcx
0x140017dae  jz      short loc_140017E04
0x140017db0  lea     rax, [rbp+var_48]
0x140017db4  mov     r8d, edi
0x140017db7  lea     r9, aFailedToQueryR; "Failed to query registry value: {}"
0x140017dbe  mov     [rsp+80h+lpData], rax
0x140017dc3  xor     edx, edx
0x140017dc5  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140017dca  test    ebx, ebx
0x140017dcc  jg      short loc_140017DD2
0x140017dce  mov     eax, ebx
0x140017dd0  jmp     short loc_140017DDA
0x140017dd2  movzx   eax, bx
0x140017dd5  or      eax, 80070000h
0x140017dda  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017de1  lea     r9, a0; ": {0}"
0x140017de8  mov     [rbp+var_38], eax
0x140017deb  mov     r8d, edi
0x140017dee  lea     rax, [rbp+var_38]
0x140017df2  mov     qword ptr [rbp+var_50], rax
0x140017df6  lea     rax, [rbp+var_50]
0x140017dfa  mov     [rsp+80h+lpData], rax
0x140017dff  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017e04  mov     edx, 17Ch
0x140017e09  jmp     loc_140017D36
0x140017e0e  cmp     [rbp+Type], 4
0x140017e12  jz      short loc_140017E7A
0x140017e14  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017e1b  mov     ebx, 8007000Dh
0x140017e20  mov     [rbp+var_30], ebx
0x140017e23  test    rcx, rcx
0x140017e26  jz      short loc_140017E60
0x140017e28  lea     r9, aRegistryValueI_0; "Registry value is not a DWORD type."
0x140017e2f  mov     r8d, edi
0x140017e32  xor     edx, edx
0x140017e34  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017e39  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017e40  lea     rax, [rbp+var_30]
0x140017e44  mov     qword ptr [rbp+var_50], rax
0x140017e48  lea     r9, asc_14002D4FC; ": {}"
0x140017e4f  lea     rax, [rbp+var_50]
0x140017e53  mov     r8d, edi
0x140017e56  mov     [rsp+80h+lpData], rax; int
0x140017e5b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017e60  mov     rcx, [rbp+18h]; this
0x140017e64  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140017e6b  mov     r9d, ebx; char *
0x140017e6e  mov     edx, 17Eh; void *
0x140017e73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017e78  jmp     short loc_140017E81
0x140017e7a  mov     eax, dword ptr [rbp+Data]
0x140017e7d  xor     ebx, ebx
0x140017e7f  mov     [rsi], eax
0x140017e81  lea     rcx, [rbp+hKey]
0x140017e85  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x140017e8a  mov     eax, ebx
0x140017e8c  mov     rcx, [rbp+var_10]
0x140017e90  xor     rcx, rsp; StackCookie
0x140017e93  call    __security_check_cookie
0x140017e98  mov     rbx, [rsp+80h+arg_0]
0x140017ea0  add     rsp, 80h
0x140017ea7  pop     rdi
0x140017ea8  pop     rsi
0x140017ea9  pop     rbp
0x140017eaa  retn
```
