# CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)

- ea: `0x140017eb4`
- end: `0x14001838d`
- name: `?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z`
- size: `1241`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, __int64, const wchar_t *, wchar_t **)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140013200`
- `0x140013288`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006984`
- `0x140006c50`
- `0x14000952c`
- `0x14000955c`
- `0x140010b3c`
- `0x140011e8c`
- `0x140012a2c`
- `0x140017af0`
- `0x140017eb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400180e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400181f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400182cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400180e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400181f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400182cd`

## string_xrefs

- `0x140017fc8`: `Failed to open the registry root: n/a, key: {}.`
- `0x14001817f`: `Failed initial query of value to get type, size, and value of registry value: {}`
- `0x140018226`: `Failed to query value to get type and size of registry root: n/a, value: {}`
- `0x14001810c`: `Registry value is not a string type.`
- `0x1400182ec`: `Failed to query registry value: {}`

## pseudocode

```c
__int64 __fastcall CbsRegQueryStringValue(HKEY a1, const wchar_t *a2, __int64 a3, const wchar_t *a4, wchar_t **a5)
{
  const WCHAR *v5; // rax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HKEY v8; // r15
  LSTATUS v9; // eax
  int v10; // ebx
  __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  LPBYTE v15; // rcx
  unsigned __int64 v16; // rbx
  int v17; // r12d
  int v18; // eax
  int v19; // esi
  __int64 v20; // rdx
  LSTATUS v21; // esi
  __int64 v22; // rdx
  __int64 v23; // rdx
  unsigned int v24; // eax
  LSTATUS v25; // esi
  __int64 v26; // rdx
  unsigned int v27; // eax
  LSTATUS v28; // esi
  __int64 v29; // rdx
  unsigned int v30; // eax
  unsigned int lpData; // [rsp+20h] [rbp-60h]
  unsigned int v33[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int *v34; // [rsp+38h] [rbp-48h] BYREF
  int *v35; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-38h] BYREF
  const wchar_t *v37; // [rsp+50h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-28h] BYREF
  int v39; // [rsp+5Ch] [rbp-24h] BYREF
  DWORD Type; // [rsp+60h] [rbp-20h] BYREF
  HKEY v41; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v5 = a4;
  v37 = a2;
  lpValueName = a4;
  if ( a5 )
  {
    v41 = 0;
    v8 = HKEY_LOCAL_MACHINE;
    if ( a2 )
    {
      v9 = CbsRegOpenKeyExW(a1, a2, a3, 0x20019u, &v41);
      v10 = v9;
      if ( v9 == 2 || v9 == 3 )
      {
        v6 = (unsigned __int16)v9 | 0x80070000;
LABEL_59:
        Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v41);
        return v6;
      }
      if ( v9 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to open the registry root: n/a, key: {}.",
            (__int64)&v37);
          if ( v10 > 0 )
            v12 = (unsigned __int16)v10 | 0x80070000;
          else
            v12 = v10;
          v39 = v12;
          *(_QWORD *)v33 = &v39;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v11,
            3,
            (__int64)": {0}",
            (__int64)v33);
        }
        v13 = (unsigned int)v10;
        v14 = 182;
LABEL_16:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v14,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
               (const char *)v13,
               lpData);
        goto LABEL_59;
      }
      v8 = v41;
      v5 = lpValueName;
    }
    v15 = (LPBYTE)*a5;
    v16 = 0;
    v17 = 0;
    *(_QWORD *)v33 = 0;
    Type = 0;
    cbData = 0;
    if ( v15 )
    {
      v18 = SczSize(v15, v33);
      v6 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
          (const char *)(unsigned int)v18,
          lpData);
        goto LABEL_59;
      }
      v16 = *(_QWORD *)v33;
      if ( *(_QWORD *)v33 >= 2u )
      {
        v19 = ULongLongToULong(2LL * *(_QWORD *)v33 - 4, &cbData);
        if ( v19 < 0 )
        {
          v20 = 199;
LABEL_24:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
            (const char *)(unsigned int)v19,
            lpData);
          v6 = v19;
          goto LABEL_59;
        }
      }
      v21 = RegQueryValueExW(v8, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
      if ( !v21 )
      {
        v17 = 1;
        goto LABEL_27;
      }
      if ( v21 != 234 )
      {
        if ( v21 != 2 )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed initial query of value to get type, size, and value of registry value: {}",
              (__int64)&lpValueName);
            if ( v21 > 0 )
              v24 = (unsigned __int16)v21 | 0x80070000;
            else
              v24 = v21;
            v39 = v24;
            v35 = &v39;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v23,
              3,
              (__int64)": {0}",
              (__int64)&v35);
          }
          v13 = (unsigned int)v21;
          v14 = 224;
          goto LABEL_16;
        }
LABEL_40:
        v6 = -2147024894;
        goto LABEL_59;
      }
    }
    else
    {
      v25 = RegQueryValueExW(v8, v5, 0, &Type, 0, &cbData);
      if ( v25 == 2 )
        goto LABEL_40;
      if ( v25 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to query value to get type and size of registry root: n/a, value: {}",
            (__int64)&lpValueName);
          if ( v25 > 0 )
            v27 = (unsigned __int16)v25 | 0x80070000;
          else
            v27 = v25;
          v33[0] = v27;
          v34 = v33;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v26,
            3,
            (__int64)": {0}",
            (__int64)&v34);
        }
        v13 = (unsigned int)v25;
        v14 = 240;
        goto LABEL_16;
      }
    }
LABEL_27:
    if ( Type - 1 > 1 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Registry value is not a string type.");
        v34 = v33;
        v33[0] = -2147024883;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v22,
          3,
          (__int64)": {0}",
          (__int64)&v34);
      }
      v13 = 13;
      v14 = 246;
      goto LABEL_16;
    }
    if ( !v17 )
    {
      v16 = ((unsigned __int64)cbData >> 1) + 2;
      v19 = SczAlloc(a5, v16);
      if ( v19 < 0 )
      {
        v20 = 255;
        goto LABEL_24;
      }
      v28 = RegQueryValueExW(v8, lpValueName, 0, &Type, (LPBYTE)*a5, &cbData);
      if ( v28 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to query registry value: {}",
            (__int64)&lpValueName);
          if ( v28 > 0 )
            v30 = (unsigned __int16)v28 | 0x80070000;
          else
            v30 = v28;
          v33[0] = v30;
          v34 = v33;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            v29,
            3,
            (__int64)": {0}",
            (__int64)&v34);
        }
        v13 = (unsigned int)v28;
        v14 = 266;
        goto LABEL_16;
      }
    }
    (*a5)[v16 - 2] = 0;
    (*a5)[v16 - 1] = 0;
    v6 = 0;
    goto LABEL_59;
  }
  v6 = -2147467261;
  v39 = -2147467261;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value result specified");
    *(_QWORD *)v33 = &v39;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      v7,
      3,
      (__int64)": {}",
      (__int64)v33);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA7,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
    (const char *)0x80004003LL,
    lpData);
  return v6;
}

```

## disassembly

```asm
0x140017eb4  mov     [rsp-28h+arg_0], rbx
0x140017eb9  mov     [rsp-28h+arg_10], rsi
0x140017ebe  push    rbp
0x140017ebf  push    rdi
0x140017ec0  push    r12
0x140017ec2  push    r14
0x140017ec4  push    r15
0x140017ec6  mov     rbp, rsp
0x140017ec9  sub     rsp, 80h
0x140017ed0  mov     rax, cs:__security_cookie
0x140017ed7  xor     rax, rsp
0x140017eda  mov     [rbp+var_10], rax
0x140017ede  mov     r14, [rbp+arg_20]
0x140017ee2  mov     rax, r9
0x140017ee5  mov     [rbp+var_30], rdx
0x140017ee9  mov     [rbp+lpValueName], rax
0x140017eed  test    r14, r14
0x140017ef0  jnz     short loc_140017F5F
0x140017ef2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017ef9  mov     ebx, 80004003h
0x140017efe  mov     [rbp+var_24], ebx
0x140017f01  test    rcx, rcx
0x140017f04  jz      short loc_140017F42
0x140017f06  lea     edi, [r14+3]
0x140017f0a  xor     edx, edx
0x140017f0c  mov     r8d, edi
0x140017f0f  lea     r9, aNoValueResultS; "No value result specified"
0x140017f16  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017f1b  lea     rcx, [rbp+var_50]
0x140017f1f  mov     r8d, edi
0x140017f22  mov     [rsp+80h+lpData], rcx; int
0x140017f27  lea     rax, [rbp+var_24]
0x140017f2b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017f32  lea     r9, asc_14002D4FC; ": {}"
0x140017f39  mov     qword ptr [rbp+var_50], rax
0x140017f3d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017f42  mov     rcx, [rbp+28h]; this
0x140017f46  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140017f4d  mov     r9d, ebx; char *
0x140017f50  mov     edx, 0A7h; void *
0x140017f55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017f5a  jmp     loc_140018363
0x140017f5f  mov     [rbp+var_18], 0
0x140017f67  mov     edi, 3
0x140017f6c  mov     r15, 0FFFFFFFF80000002h
0x140017f73  test    rdx, rdx
0x140017f76  jz      loc_14001803C
0x140017f7c  lea     rax, [rbp+var_18]
0x140017f80  mov     r9d, 20019h; unsigned int
0x140017f86  mov     [rsp+80h+lpData], rax; int
0x140017f8b  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x140017f90  mov     ebx, eax
0x140017f92  cmp     eax, 2
0x140017f95  jz      short loc_140017FA3
0x140017f97  cmp     eax, edi
0x140017f99  jnz     short loc_140017FB1
0x140017f9b  test    eax, eax
0x140017f9d  jle     loc_14001835A
0x140017fa3  movzx   ebx, bx
0x140017fa6  or      ebx, 80070000h
0x140017fac  jmp     loc_14001835A
0x140017fb1  test    ebx, ebx
0x140017fb3  jz      short loc_140018034
0x140017fb5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017fbc  test    rcx, rcx
0x140017fbf  jz      short loc_140018015
0x140017fc1  lea     rax, [rbp+var_30]
0x140017fc5  mov     r8d, edi
0x140017fc8  lea     r9, aFailedToOpenTh; "Failed to open the registry root: n/a, "...
0x140017fcf  mov     [rsp+80h+lpData], rax
0x140017fd4  xor     edx, edx
0x140017fd6  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140017fdb  test    ebx, ebx
0x140017fdd  jg      short loc_140017FE3
0x140017fdf  mov     eax, ebx
0x140017fe1  jmp     short loc_140017FEB
0x140017fe3  movzx   eax, bx
0x140017fe6  or      eax, 80070000h
0x140017feb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017ff2  lea     r9, a0; ": {0}"
0x140017ff9  mov     [rbp+var_24], eax
0x140017ffc  mov     r8d, edi
0x140017fff  lea     rax, [rbp+var_24]
0x140018003  mov     qword ptr [rbp+var_50], rax
0x140018007  lea     rax, [rbp+var_50]
0x14001800b  mov     [rsp+80h+lpData], rax; unsigned int
0x140018010  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018015  mov     r9d, ebx; char *
0x140018018  mov     edx, 0B6h; void *
0x14001801d  mov     rcx, [rbp+28h]; this
0x140018021  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140018028  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001802d  mov     ebx, eax
0x14001802f  jmp     loc_14001835A
0x140018034  mov     r15, [rbp+var_18]
0x140018038  mov     rax, [rbp+lpValueName]
0x14001803c  mov     rcx, [r14]
0x14001803f  xor     ebx, ebx
0x140018041  xor     r12d, r12d
0x140018044  mov     qword ptr [rbp+var_50], rbx
0x140018048  mov     [rbp+Type], ebx
0x14001804b  mov     [rbp+cbData], ebx
0x14001804e  test    rcx, rcx
0x140018051  jz      loc_1400181D9
0x140018057  lea     rdx, [rbp+var_50]
0x14001805b  call    SczSize
0x140018060  mov     ebx, eax
0x140018062  test    eax, eax
0x140018064  jns     short loc_140018083
0x140018066  mov     rcx, [rbp+28h]; this
0x14001806a  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x140018071  mov     r9d, eax; char *
0x140018074  mov     edx, 0C2h; void *
0x140018079  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001807e  jmp     loc_14001835A
0x140018083  mov     rbx, qword ptr [rbp+var_50]
0x140018087  cmp     rbx, 2
0x14001808b  jb      short loc_1400180C3
0x14001808d  lea     rcx, ds:0FFFFFFFFFFFFFFFCh[rbx*2]; unsigned __int64
0x140018095  lea     rdx, [rbp+cbData]; unsigned int *
0x140018099  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14001809e  mov     esi, eax
0x1400180a0  test    eax, eax
0x1400180a2  jns     short loc_1400180C3
0x1400180a4  mov     edx, 0C7h; void *
0x1400180a9  mov     rcx, [rbp+28h]; this
0x1400180ad  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x1400180b4  mov     r9d, esi; char *
0x1400180b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400180bc  mov     ebx, esi
0x1400180be  jmp     loc_14001835A
0x1400180c3  mov     rdx, [rbp+lpValueName]; lpValueName
0x1400180c7  lea     rax, [rbp+cbData]
0x1400180cb  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1400180d0  lea     r9, [rbp+Type]; lpType
0x1400180d4  mov     rax, [r14]
0x1400180d7  xor     r8d, r8d; lpReserved
0x1400180da  mov     rcx, r15; hKey
0x1400180dd  mov     [rsp+80h+lpData], rax; lpData
0x1400180e2  call    cs:__imp_RegQueryValueExW
0x1400180e8  mov     esi, eax
0x1400180ea  test    eax, eax
0x1400180ec  jnz     short loc_14001815B
0x1400180ee  lea     r12d, [rax+1]
0x1400180f2  mov     eax, [rbp+Type]
0x1400180f5  dec     eax
0x1400180f7  cmp     eax, 1
0x1400180fa  jbe     loc_140018280
0x140018100  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018107  test    rcx, rcx
0x14001810a  jz      short loc_14001814B
0x14001810c  lea     r9, aRegistryValueI; "Registry value is not a string type."
0x140018113  mov     r8d, edi
0x140018116  xor     edx, edx
0x140018118  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001811d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018124  lea     rax, [rbp+var_50]
0x140018128  mov     [rbp+var_48], rax
0x14001812c  lea     r9, a0; ": {0}"
0x140018133  lea     rax, [rbp+var_48]
0x140018137  mov     [rbp+var_50], 8007000Dh
0x14001813e  mov     r8d, edi
0x140018141  mov     [rsp+80h+lpData], rax
0x140018146  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001814b  mov     r9d, 0Dh
0x140018151  mov     edx, 0F6h
0x140018156  jmp     loc_14001801D
0x14001815b  cmp     esi, 0EAh
0x140018161  jz      short loc_1400180F2
0x140018163  cmp     esi, 2
0x140018166  jz      loc_140018201
0x14001816c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018173  test    rcx, rcx
0x140018176  jz      short loc_1400181CC
0x140018178  lea     rax, [rbp+lpValueName]
0x14001817c  mov     r8d, edi
0x14001817f  lea     r9, aFailedInitialQ; "Failed initial query of value to get ty"...
0x140018186  mov     [rsp+80h+lpData], rax
0x14001818b  xor     edx, edx
0x14001818d  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140018192  test    esi, esi
0x140018194  jg      short loc_14001819A
0x140018196  mov     eax, esi
0x140018198  jmp     short loc_1400181A2
0x14001819a  movzx   eax, si
0x14001819d  or      eax, 80070000h
0x1400181a2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400181a9  lea     r9, a0; ": {0}"
0x1400181b0  mov     [rbp+var_24], eax
0x1400181b3  mov     r8d, edi
0x1400181b6  lea     rax, [rbp+var_24]
0x1400181ba  mov     [rbp+var_40], rax
0x1400181be  lea     rax, [rbp+var_40]
0x1400181c2  mov     [rsp+80h+lpData], rax
0x1400181c7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400181cc  mov     r9d, esi
0x1400181cf  mov     edx, 0E0h
0x1400181d4  jmp     loc_14001801D
0x1400181d9  lea     rcx, [rbp+cbData]
0x1400181dd  xor     r8d, r8d; lpReserved
0x1400181e0  mov     [rsp+80h+lpcbData], rcx; lpcbData
0x1400181e5  lea     r9, [rbp+Type]; lpType
0x1400181e9  mov     rcx, r15; hKey
0x1400181ec  mov     [rsp+80h+lpData], rbx; lpData
0x1400181f1  mov     rdx, rax; lpValueName
0x1400181f4  call    cs:__imp_RegQueryValueExW
0x1400181fa  mov     esi, eax
0x1400181fc  cmp     eax, 2
0x1400181ff  jnz     short loc_14001820B
0x140018201  mov     ebx, 80070002h
0x140018206  jmp     loc_14001835A
0x14001820b  test    esi, esi
0x14001820d  jz      loc_1400180F2
0x140018213  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001821a  test    rcx, rcx
0x14001821d  jz      short loc_140018273
0x14001821f  lea     rax, [rbp+lpValueName]
0x140018223  mov     r8d, edi
0x140018226  lea     r9, aFailedToQueryV; "Failed to query value to get type and s"...
0x14001822d  mov     [rsp+80h+lpData], rax
0x140018232  xor     edx, edx
0x140018234  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140018239  test    esi, esi
0x14001823b  jg      short loc_140018241
0x14001823d  mov     eax, esi
0x14001823f  jmp     short loc_140018249
0x140018241  movzx   eax, si
0x140018244  or      eax, 80070000h
0x140018249  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018250  lea     r9, a0; ": {0}"
0x140018257  mov     [rbp+var_50], eax
0x14001825a  mov     r8d, edi
0x14001825d  lea     rax, [rbp+var_50]
0x140018261  mov     [rbp+var_48], rax
0x140018265  lea     rax, [rbp+var_48]
0x140018269  mov     [rsp+80h+lpData], rax
0x14001826e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018273  mov     r9d, esi
0x140018276  mov     edx, 0F0h
0x14001827b  jmp     loc_14001801D
0x140018280  test    r12d, r12d
0x140018283  jnz     loc_140018346
0x140018289  mov     ebx, [rbp+cbData]
0x14001828c  mov     rcx, r14
0x14001828f  shr     rbx, 1
0x140018292  add     rbx, 2
0x140018296  mov     rdx, rbx
0x140018299  call    SczAlloc
0x14001829e  mov     esi, eax
0x1400182a0  test    eax, eax
0x1400182a2  jns     short loc_1400182AE
0x1400182a4  mov     edx, 0FFh
0x1400182a9  jmp     loc_1400180A9
0x1400182ae  mov     rdx, [rbp+lpValueName]; lpValueName
0x1400182b2  lea     rax, [rbp+cbData]
0x1400182b6  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1400182bb  lea     r9, [rbp+Type]; lpType
0x1400182bf  mov     rax, [r14]
0x1400182c2  xor     r8d, r8d; lpReserved
0x1400182c5  mov     rcx, r15; hKey
0x1400182c8  mov     [rsp+80h+lpData], rax; lpData
0x1400182cd  call    cs:__imp_RegQueryValueExW
0x1400182d3  mov     esi, eax
0x1400182d5  test    eax, eax
0x1400182d7  jz      short loc_140018346
0x1400182d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400182e0  test    rcx, rcx
0x1400182e3  jz      short loc_140018339
0x1400182e5  lea     rax, [rbp+lpValueName]
0x1400182e9  mov     r8d, edi
0x1400182ec  lea     r9, aFailedToQueryR; "Failed to query registry value: {}"
0x1400182f3  mov     [rsp+80h+lpData], rax
0x1400182f8  xor     edx, edx
0x1400182fa  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1400182ff  test    esi, esi
0x140018301  jg      short loc_140018307
0x140018303  mov     eax, esi
0x140018305  jmp     short loc_14001830F
0x140018307  movzx   eax, si
0x14001830a  or      eax, 80070000h
0x14001830f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018316  lea     r9, a0; ": {0}"
0x14001831d  mov     [rbp+var_50], eax
0x140018320  mov     r8d, edi
0x140018323  lea     rax, [rbp+var_50]
0x140018327  mov     [rbp+var_48], rax
0x14001832b  lea     rax, [rbp+var_48]
0x14001832f  mov     [rsp+80h+lpData], rax
0x140018334  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018339  mov     r9d, esi
0x14001833c  mov     edx, 10Ah
0x140018341  jmp     loc_14001801D
0x140018346  mov     rcx, [r14]
0x140018349  xor     eax, eax
0x14001834b  mov     [rcx+rbx*2-4], ax
0x140018350  mov     rcx, [r14]
0x140018353  mov     [rcx+rbx*2-2], ax
0x140018358  xor     ebx, ebx
0x14001835a  lea     rcx, [rbp+var_18]
0x14001835e  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
  ... truncated ...
```
