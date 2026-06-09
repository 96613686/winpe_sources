# OpenPrimaryOSProductRegistryKey(HKEY__ *,ulong,ulong,HKEY__ * *)

- ea: `0x18010ca80`
- end: `0x18010cebd`
- name: `?OpenPrimaryOSProductRegistryKey@@YAJPEAUHKEY__@@KKPEAPEAU1@@Z`
- size: `1085`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801c3b48`

## callees

- `0x180010cc0`
- `0x180013250`
- `0x18003330c`
- `0x180059160`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1801073fc`
- `0x18010ca80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18010cc78`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18010cc78`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010cd8b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18010cd8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010cb5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010ce2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010cb5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010ce2a`

## string_xrefs

- `0x18010cabb`: `Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\Installed`
- `0x18010cdb1`: `Failed opening key with backup/restore: {}`
- `0x18010cb9e`: `Failed opening key {}`
- `0x18010ce4c`: `Failed opening key {}`

## pseudocode

```c
__int64 __fastcall OpenPrimaryOSProductRegistryKey(HKEY hKey, char a2, __int64 a3, HKEY *a4)
{
  unsigned int v7; // ebx
  int v8; // edx
  __int64 v9; // rdx
  HKEY *InitPointer; // rax
  LSTATUS v11; // eax
  LSTATUS v12; // ebx
  int v13; // edx
  DWORD v14; // eax
  __int64 v15; // rdx
  DWORD v16; // ebx
  DWORD i; // edx
  int v18; // edx
  HKEY *v20; // rax
  int v21; // edx
  int v22; // r8d
  int v23; // edx
  unsigned int v24; // eax
  HKEY *v25; // rax
  int v26; // edx
  int v27; // r8d
  int v28; // edx
  unsigned int v29; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int v32[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v33; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v36[2]; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKeya; // [rsp+80h] [rbp-80h] BYREF
  HKEY v39; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[256]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  cchName = 255;
  hKeya = 0;
  v39 = 0;
  v33 = 0;
  lpSubKey = L"Microsoft\\Windows NT\\CurrentVersion\\Update\\TargetingInfo\\Installed";
  if ( a4 )
  {
    *a4 = 0;
    InitPointer = (HKEY *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&hKeya);
    v11 = RegOpenKeyExW(hKey, lpSubKey, 0, 8u, InitPointer);
    v12 = v11;
    if ( (a2 & 1) != 0 || v11 != 2 )
    {
      if ( v11 )
      {
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed opening key {}",
            (__int64)&lpSubKey);
          if ( v12 > 0 )
            v14 = (unsigned __int16)v12 | 0x80070000;
          else
            v14 = v12;
          dwDisposition = v14;
          LOBYTE(v13) = 1;
          *(_QWORD *)v36 = &dwDisposition;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v13,
            3,
            (unsigned int)": {0}",
            (__int64)v36);
        }
        v15 = 1468;
        goto LABEL_15;
      }
      v16 = 0;
      for ( i = 0; ; i = v16 )
      {
        if ( RegEnumKeyExW(hKeya, i, Name, &cchName, 0, 0, 0, 0) )
        {
          v7 = -2147023728;
          if ( (a2 & 1) != 0 )
            goto LABEL_25;
          v36[0] = -2147023728;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "primary product not found");
            *(_QWORD *)v32 = v36;
            LOBYTE(v18) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v18,
              3,
              (unsigned int)": {}",
              (__int64)v32);
          }
          v9 = 1503;
          goto LABEL_24;
        }
        if ( (int)CbsRegQueryStringValue(hKeya, Name, 1u, L"PrimaryOSProduct", &v33) >= 0 )
          break;
        ++v16;
        cchName = 255;
      }
      if ( (a2 & 0x20) != 0 )
      {
        dwDisposition = 0;
        v20 = (HKEY *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v39);
        v12 = RegCreateKeyExW(hKeya, Name, 0, 0, 4u, 0x20006u, 0, v20, &dwDisposition);
        if ( v12 )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t [256]>(
              (_DWORD)LogAdapter::g_Logger,
              v21,
              v22,
              (unsigned int)"Failed opening key with backup/restore: {}",
              (__int64)Name);
            if ( v12 > 0 )
              v24 = (unsigned __int16)v12 | 0x80070000;
            else
              v24 = v12;
            v36[0] = v24;
            LOBYTE(v23) = 1;
            *(_QWORD *)v32 = v36;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v23,
              3,
              (unsigned int)": {0}",
              (__int64)v32);
          }
          v15 = 1485;
          goto LABEL_15;
        }
LABEL_41:
        v7 = 0;
        *a4 = v39;
        v39 = 0;
        goto LABEL_25;
      }
      v25 = (HKEY *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v39);
      v12 = RegOpenKeyExW(hKeya, Name, 0, 0x20006u, v25);
      if ( !v12 )
        goto LABEL_41;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t [256]>(
          (_DWORD)LogAdapter::g_Logger,
          v26,
          v27,
          (unsigned int)"Failed opening key {}",
          (__int64)Name);
        if ( v12 > 0 )
          v29 = (unsigned __int16)v12 | 0x80070000;
        else
          v29 = v12;
        v36[0] = v29;
        LOBYTE(v28) = 1;
        *(_QWORD *)v32 = v36;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v28,
          3,
          (unsigned int)": {0}",
          (__int64)v32);
      }
      v15 = 1490;
LABEL_15:
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v15,
             (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
             (const char *)(unsigned int)v12,
             phkResulta);
    }
    else
    {
      v7 = -2147024894;
    }
  }
  else
  {
    v7 = -2147467261;
    dwDisposition = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No product key result specified");
      *(_QWORD *)v36 = &dwDisposition;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)v36);
    }
    v9 = 1460;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsutil.cpp",
      (const char *)v7,
      phkResult);
  }
LABEL_25:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v33);
  Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&v39);
  Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKeya);
  return v7;
}

```

## disassembly

```asm
0x18010ca80  mov     [rsp-8+arg_8], rbx
0x18010ca85  push    rbp
0x18010ca86  push    rsi
0x18010ca87  push    rdi
0x18010ca88  push    r14
0x18010ca8a  push    r15
0x18010ca8c  lea     rbp, [rsp-1A0h]
0x18010ca94  sub     rsp, 2A0h
0x18010ca9b  mov     rax, cs:__security_cookie
0x18010caa2  xor     rax, rsp
0x18010caa5  mov     [rbp+1C0h+var_30], rax
0x18010caac  xor     r15d, r15d
0x18010caaf  mov     [rsp+2C0h+cchName], 0FFh
0x18010cab7  mov     [rbp+1C0h+hKey], r15
0x18010cabb  lea     rax, aMicrosoftWindo_26; "Microsoft\\Windows NT\\CurrentVersion\\"...
0x18010cac2  mov     [rbp+1C0h+var_238], r15
0x18010cac6  mov     rdi, r9
0x18010cac9  mov     [rsp+2C0h+var_268], r15
0x18010cace  mov     esi, edx
0x18010cad0  mov     [rsp+2C0h+lpSubKey], rax
0x18010cad5  mov     rbx, rcx
0x18010cad8  test    r9, r9
0x18010cadb  jnz     short loc_18010CB3B
0x18010cadd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010cae4  mov     ebx, 80004003h
0x18010cae9  mov     [rsp+2C0h+dwDisposition], ebx
0x18010caed  test    rcx, rcx
0x18010caf0  jz      short loc_18010CB31
0x18010caf2  lea     r9, aNoProductKeyRe; "No product key result specified"
0x18010caf9  xor     edx, edx
0x18010cafb  lea     r8d, [rdi+3]
0x18010caff  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010cb04  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010cb0b  lea     rax, [rsp+2C0h+dwDisposition]
0x18010cb10  mov     qword ptr [rsp+2C0h+var_250], rax
0x18010cb15  lea     r9, asc_1802EE7AC; ": {}"
0x18010cb1c  lea     rax, [rsp+2C0h+var_250]
0x18010cb21  mov     dl, 1
0x18010cb23  lea     r8d, [rdi+3]
0x18010cb27  mov     [rsp+2C0h+phkResult], rax
0x18010cb2c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010cb31  mov     edx, 5B4h
0x18010cb36  jmp     loc_18010CCE6
0x18010cb3b  lea     rcx, [rbp+1C0h+hKey]
0x18010cb3f  mov     [r9], r15
0x18010cb42  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18010cb47  mov     rdx, [rsp+2C0h+lpSubKey]; lpSubKey
0x18010cb4c  mov     r9d, 8; samDesired
0x18010cb52  xor     r8d, r8d; ulOptions
0x18010cb55  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18010cb5a  mov     rcx, rbx; hKey
0x18010cb5d  call    cs:__imp_RegOpenKeyExW
0x18010cb64  nop     dword ptr [rax+rax+00h]
0x18010cb69  mov     r14d, esi
0x18010cb6c  mov     ebx, eax
0x18010cb6e  and     r14d, 1
0x18010cb72  jnz     short loc_18010CB83
0x18010cb74  cmp     eax, 2
0x18010cb77  jnz     short loc_18010CB83
0x18010cb79  mov     ebx, 80070002h
0x18010cb7e  jmp     loc_18010CCFC
0x18010cb83  test    ebx, ebx
0x18010cb85  jz      loc_18010CC18
0x18010cb8b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010cb92  test    rcx, rcx
0x18010cb95  jz      short loc_18010CBF6
0x18010cb97  xor     edx, edx
0x18010cb99  lea     rax, [rsp+2C0h+lpSubKey]
0x18010cb9e  lea     r9, aFailedOpeningK; "Failed opening key {}"
0x18010cba5  mov     [rsp+2C0h+phkResult], rax
0x18010cbaa  lea     r8d, [rdx+3]
0x18010cbae  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18010cbb3  test    ebx, ebx
0x18010cbb5  jg      short loc_18010CBBB
0x18010cbb7  mov     eax, ebx
0x18010cbb9  jmp     short loc_18010CBC3
0x18010cbbb  movzx   eax, bx
0x18010cbbe  or      eax, 80070000h
0x18010cbc3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010cbca  lea     r9, a0; ": {0}"
0x18010cbd1  mov     [rsp+2C0h+dwDisposition], eax
0x18010cbd5  mov     r8d, 3
0x18010cbdb  lea     rax, [rsp+2C0h+dwDisposition]
0x18010cbe0  mov     dl, 1
0x18010cbe2  mov     qword ptr [rsp+2C0h+var_250], rax
0x18010cbe7  lea     rax, [rsp+2C0h+var_250]
0x18010cbec  mov     [rsp+2C0h+phkResult], rax; unsigned int
0x18010cbf1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010cbf6  mov     edx, 5BCh; void *
0x18010cbfb  mov     rcx, [rbp+1C8h]; this
0x18010cc02  lea     r8, aOnecoreBaseCbs_88; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x18010cc09  mov     r9d, ebx; char *
0x18010cc0c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010cc11  mov     ebx, eax
0x18010cc13  jmp     loc_18010CCFC
0x18010cc18  mov     ebx, r15d
0x18010cc1b  xor     edx, edx
0x18010cc1d  jmp     short loc_18010CC57
0x18010cc1f  mov     rcx, [rbp+1C0h+hKey]; hKey
0x18010cc23  lea     rax, [rsp+2C0h+var_268]
0x18010cc28  lea     r9, aPrimaryosprodu; "PrimaryOSProduct"
0x18010cc2f  mov     [rsp+2C0h+phkResult], rax; wchar_t **
0x18010cc34  mov     r8d, 1; unsigned int
0x18010cc3a  lea     rdx, [rbp+1C0h+Name]; wchar_t *
0x18010cc3e  call    ?CbsRegQueryStringValue@@YAJPEAUHKEY__@@PEB_WK1PEAPEA_W@Z; CbsRegQueryStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t * *)
0x18010cc43  test    eax, eax
0x18010cc45  jns     loc_18010CD41
0x18010cc4b  inc     ebx
0x18010cc4d  mov     [rsp+2C0h+cchName], 0FFh
0x18010cc55  mov     edx, ebx; dwIndex
0x18010cc57  mov     rcx, [rbp+1C0h+hKey]; hKey
0x18010cc5b  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x18010cc60  mov     [rsp+2C0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18010cc65  lea     r8, [rbp+1C0h+Name]; lpName
0x18010cc69  mov     [rsp+2C0h+lpcchClass], r15; lpcchClass
0x18010cc6e  mov     [rsp+2C0h+lpClass], r15; lpClass
0x18010cc73  mov     [rsp+2C0h+phkResult], r15; lpReserved
0x18010cc78  call    cs:__imp_RegEnumKeyExW
0x18010cc7f  nop     dword ptr [rax+rax+00h]
0x18010cc84  test    eax, eax
0x18010cc86  jz      short loc_18010CC1F
0x18010cc88  mov     ebx, 80070490h
0x18010cc8d  test    r14d, r14d
0x18010cc90  jnz     short loc_18010CCFC
0x18010cc92  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010cc99  mov     [rsp+2C0h+var_250], ebx
0x18010cc9d  test    rcx, rcx
0x18010cca0  jz      short loc_18010CCE1
0x18010cca2  lea     r9, aPrimaryProduct; "primary product not found"
0x18010cca9  xor     edx, edx
0x18010ccab  lea     r8d, [r14+3]
0x18010ccaf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010ccb4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ccbb  lea     rax, [rsp+2C0h+var_250]
0x18010ccc0  mov     qword ptr [rsp+2C0h+var_270], rax
0x18010ccc5  lea     r9, asc_1802EE7AC; ": {}"
0x18010cccc  lea     rax, [rsp+2C0h+var_270]
0x18010ccd1  mov     dl, 1
0x18010ccd3  lea     r8d, [r14+3]
0x18010ccd7  mov     [rsp+2C0h+phkResult], rax; int
0x18010ccdc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010cce1  mov     edx, 5DFh; void *
0x18010cce6  mov     rcx, [rbp+1C8h]; this
0x18010cced  lea     r8, aOnecoreBaseCbs_88; "onecore\\base\\cbs\\util\\cbsutil.cpp"
0x18010ccf4  mov     r9d, ebx; char *
0x18010ccf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ccfc  lea     rcx, [rsp+2C0h+var_268]
0x18010cd01  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18010cd06  lea     rcx, [rbp+1C0h+var_238]
0x18010cd0a  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x18010cd0f  lea     rcx, [rbp+1C0h+hKey]
0x18010cd13  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x18010cd18  mov     eax, ebx
0x18010cd1a  mov     rcx, [rbp+1C0h+var_30]
0x18010cd21  xor     rcx, rsp; StackCookie
0x18010cd24  call    __security_check_cookie
0x18010cd29  mov     rbx, [rsp+2C0h+arg_8]
0x18010cd31  add     rsp, 2A0h
0x18010cd38  pop     r15
0x18010cd3a  pop     r14
0x18010cd3c  pop     rdi
0x18010cd3d  pop     rsi
0x18010cd3e  pop     rbp
0x18010cd3f  retn
0x18010cd41  lea     rcx, [rbp+1C0h+var_238]
0x18010cd45  test    sil, 20h
0x18010cd49  jz      loc_18010CE0F
0x18010cd4f  mov     [rsp+2C0h+dwDisposition], r15d
0x18010cd54  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18010cd59  lea     rcx, [rsp+2C0h+dwDisposition]
0x18010cd5e  xor     r9d, r9d; lpClass
0x18010cd61  mov     [rsp+2C0h+lpdwDisposition], rcx; lpdwDisposition
0x18010cd66  lea     rdx, [rbp+1C0h+Name]; lpSubKey
0x18010cd6a  mov     rcx, [rbp+1C0h+hKey]; hKey
0x18010cd6e  xor     r8d, r8d; Reserved
0x18010cd71  mov     [rsp+2C0h+lpftLastWriteTime], rax; phkResult
0x18010cd76  mov     [rsp+2C0h+lpcchClass], r15; lpSecurityAttributes
0x18010cd7b  mov     dword ptr [rsp+2C0h+lpClass], 20006h; samDesired
0x18010cd83  mov     dword ptr [rsp+2C0h+phkResult], 4; dwOptions
0x18010cd8b  call    cs:__imp_RegCreateKeyExW
0x18010cd92  nop     dword ptr [rax+rax+00h]
0x18010cd97  mov     ebx, eax
0x18010cd99  test    eax, eax
0x18010cd9b  jz      loc_18010CEAA
0x18010cda1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010cda8  test    rcx, rcx
0x18010cdab  jz      short loc_18010CE05
0x18010cdad  lea     rax, [rbp+1C0h+Name]
0x18010cdb1  lea     r9, aFailedOpeningK_0; "Failed opening key with backup/restore:"...
0x18010cdb8  mov     [rsp+2C0h+phkResult], rax
0x18010cdbd  call    ??$LogNumObjects@$$BY0BAA@_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEAY0BAA@$$CB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t [256]>(bool,LogAdapter::LogLevel,char const * const,wchar_t const (&)[256])
0x18010cdc2  test    ebx, ebx
0x18010cdc4  jg      short loc_18010CDCA
0x18010cdc6  mov     eax, ebx
0x18010cdc8  jmp     short loc_18010CDD2
0x18010cdca  movzx   eax, bx
0x18010cdcd  or      eax, 80070000h
0x18010cdd2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010cdd9  lea     r9, a0; ": {0}"
0x18010cde0  mov     [rsp+2C0h+var_250], eax
0x18010cde4  mov     r8d, 3
0x18010cdea  lea     rax, [rsp+2C0h+var_250]
0x18010cdef  mov     dl, 1
0x18010cdf1  mov     qword ptr [rsp+2C0h+var_270], rax
0x18010cdf6  lea     rax, [rsp+2C0h+var_270]
0x18010cdfb  mov     [rsp+2C0h+phkResult], rax
0x18010ce00  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010ce05  mov     edx, 5CDh
0x18010ce0a  jmp     loc_18010CBFB
0x18010ce0f  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18010ce14  mov     rcx, [rbp+1C0h+hKey]; hKey
0x18010ce18  lea     rdx, [rbp+1C0h+Name]; lpSubKey
0x18010ce1c  mov     r9d, 20006h; samDesired
0x18010ce22  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18010ce27  xor     r8d, r8d; ulOptions
0x18010ce2a  call    cs:__imp_RegOpenKeyExW
0x18010ce31  nop     dword ptr [rax+rax+00h]
0x18010ce36  mov     ebx, eax
0x18010ce38  test    eax, eax
0x18010ce3a  jz      short loc_18010CEAA
0x18010ce3c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ce43  test    rcx, rcx
0x18010ce46  jz      short loc_18010CEA0
0x18010ce48  lea     rax, [rbp+1C0h+Name]
0x18010ce4c  lea     r9, aFailedOpeningK; "Failed opening key {}"
0x18010ce53  mov     [rsp+2C0h+phkResult], rax
0x18010ce58  call    ??$LogNumObjects@$$BY0BAA@_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEAY0BAA@$$CB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t [256]>(bool,LogAdapter::LogLevel,char const * const,wchar_t const (&)[256])
0x18010ce5d  test    ebx, ebx
0x18010ce5f  jg      short loc_18010CE65
0x18010ce61  mov     eax, ebx
0x18010ce63  jmp     short loc_18010CE6D
0x18010ce65  movzx   eax, bx
0x18010ce68  or      eax, 80070000h
0x18010ce6d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ce74  lea     r9, a0; ": {0}"
0x18010ce7b  mov     [rsp+2C0h+var_250], eax
0x18010ce7f  mov     r8d, 3
0x18010ce85  lea     rax, [rsp+2C0h+var_250]
0x18010ce8a  mov     dl, 1
0x18010ce8c  mov     qword ptr [rsp+2C0h+var_270], rax
0x18010ce91  lea     rax, [rsp+2C0h+var_270]
0x18010ce96  mov     [rsp+2C0h+phkResult], rax
0x18010ce9b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010cea0  mov     edx, 5D2h
0x18010cea5  jmp     loc_18010CBFB
0x18010ceaa  mov     rax, [rbp+1C0h+var_238]
0x18010ceae  mov     ebx, r15d
0x18010ceb1  mov     [rdi], rax
0x18010ceb4  mov     [rbp+1C0h+var_238], r15
0x18010ceb8  jmp     loc_18010CCFC
```
