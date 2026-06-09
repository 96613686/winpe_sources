# CSecurityFilterHelper::CSecurityFilterHelper(void)

- ea: `0x18008e7f0`
- end: `0x18008ead7`
- name: `??0CSecurityFilterHelper@@QEAA@XZ`
- size: `743`
- prototype: `CSecurityFilterHelper *__fastcall(CSecurityFilterHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180087498`

## callees

- `0x180004970`
- `0x18008e7f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e8d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e970`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ea45`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e8d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e970`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ea45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e85d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e8f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e98a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ea1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ea5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e85d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e8f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e98a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ea1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008ea5f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008e83f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008e9fd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008e83f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008e9fd`

## string_xrefs

- `0x18008e838`: `sspicli.dll`
- `0x18008e874`: `CSecurityFilterHelper`
- `0x18008e8db`: `CSecurityFilterHelper`
- `0x18008e863`: `onecore\termsrv\rdp\win\security\securityfilterhelper.cpp`
- `0x18008e8e2`: `onecore\termsrv\rdp\win\security\securityfilterhelper.cpp`
- `0x18008e87b`: `Failed to load sspicli.dll! error = %d`
- `0x18008e9f6`: `Secur32.dll`
- `0x18008ea32`: `Failed to load Secur32.dll! error = %d`

## pseudocode

```c
CSecurityFilterHelper *__fastcall CSecurityFilterHelper::CSecurityFilterHelper(CSecurityFilterHelper *this)
{
  HMODULE LibraryW; // rax
  DWORD v3; // eax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  char *v7; // rdx
  const char **v8; // rax
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  FARPROC v14; // rax
  DWORD v15; // eax
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  HMODULE v19; // rax
  DWORD v20; // eax
  const char *v21; // rax
  FARPROC v22; // rax
  DWORD v23; // eax
  const char **v25; // [rsp+30h] [rbp-38h]
  const char *v26; // [rsp+50h] [rbp-18h] BYREF
  _QWORD v27[2]; // [rsp+58h] [rbp-10h] BYREF
  DWORD v28; // [rsp+90h] [rbp+28h] BYREF
  int v29; // [rsp+98h] [rbp+30h] BYREF
  int v30; // [rsp+A0h] [rbp+38h] BYREF
  const char *v31; // [rsp+A8h] [rbp+40h] BYREF

  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &CSecurityFilterHelper::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  LibraryW = LoadLibraryW(L"sspicli.dll");
  *((_QWORD *)this + 1) = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "SspiMarshalAuthIdentity");
    *((_QWORD *)this + 4) = ProcAddress;
    if ( !ProcAddress && (unsigned int)CallbackContext > 2 )
    {
      LastError = GetLastError();
      v31 = "CSecurityFilterHelper";
      v28 = LastError;
      v26 = "Failed to obtain address for SspiMarshalAuthIdentity! error = %d";
      v29 = 32;
      v27[0] = "onecore\\termsrv\\rdp\\win\\security\\securityfilterhelper.cpp";
      v30 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)qword_1801AE740,
        v12,
        v13,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)v27,
        (__int64)&v29,
        (__int64)&v31,
        (__int64)&v28);
    }
    v14 = GetProcAddress(*((HMODULE *)this + 1), "SspiLocalFree");
    *((_QWORD *)this + 5) = v14;
    if ( !v14 && (unsigned int)CallbackContext > 2 )
    {
      v15 = GetLastError();
      v31 = "CSecurityFilterHelper";
      v28 = v15;
      v26 = "Failed to obtain address for SspiLocalFree! error = %d";
      v29 = 38;
      v27[0] = "onecore\\termsrv\\rdp\\win\\security\\securityfilterhelper.cpp";
      v30 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v16,
        (unsigned int)byte_1801AE6EB,
        v17,
        v18,
        (__int64)&v26,
        (__int64)&v30,
        (__int64)v27,
        (__int64)&v29,
        (__int64)&v31,
        (__int64)&v28);
    }
    v19 = LoadLibraryW(L"Secur32.dll");
    *((_QWORD *)this + 2) = v19;
    if ( v19 )
    {
      v22 = GetProcAddress(v19, "SetCredentialsAttributesW");
      *((_QWORD *)this + 3) = v22;
      if ( v22 || (unsigned int)CallbackContext <= 2 )
        return this;
      v23 = GetLastError();
      v29 = 51;
      v7 = byte_1801AE641;
      v28 = v23;
      v21 = "Failed to obtain address for SetCredentialsAttributesW! error = %d";
    }
    else
    {
      if ( (unsigned int)CallbackContext <= 2 )
        return this;
      v20 = GetLastError();
      v29 = 44;
      v7 = (char *)&word_1801AE696;
      v28 = v20;
      v21 = "Failed to load Secur32.dll! error = %d";
    }
    v26 = v21;
    v25 = (const char **)v27;
    v8 = &v26;
    v27[0] = "onecore\\termsrv\\rdp\\win\\security\\securityfilterhelper.cpp";
    goto LABEL_17;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v3 = GetLastError();
    v29 = 25;
    v28 = v3;
    v26 = "onecore\\termsrv\\rdp\\win\\security\\securityfilterhelper.cpp";
    v27[0] = "Failed to load sspicli.dll! error = %d";
    v7 = byte_1801AE795;
    v25 = &v26;
    v8 = (const char **)v27;
LABEL_17:
    v31 = "CSecurityFilterHelper";
    v30 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v4,
      (_DWORD)v7,
      v5,
      v6,
      (__int64)v8,
      (__int64)&v30,
      (__int64)v25,
      (__int64)&v29,
      (__int64)&v31,
      (__int64)&v28);
  }
  return this;
}

```

## disassembly

```asm
0x18008e7f0  push    rbp
0x18008e7f2  push    rbx
0x18008e7f3  push    rsi
0x18008e7f4  push    rdi
0x18008e7f5  mov     rbp, rsp
0x18008e7f8  sub     rsp, 68h
0x18008e7fc  mov     qword ptr [rcx+8], 0
0x18008e804  lea     rax, ??_7CSecurityFilterHelper@@6B@; const CSecurityFilterHelper::`vftable'
0x18008e80b  mov     [rcx], rax
0x18008e80e  mov     rbx, rcx
0x18008e811  mov     qword ptr [rcx+10h], 0
0x18008e819  mov     qword ptr [rcx+18h], 0
0x18008e821  mov     qword ptr [rcx+20h], 0
0x18008e829  mov     qword ptr [rcx+28h], 0
0x18008e831  mov     dword ptr [rcx+30h], 0
0x18008e838  lea     rcx, aSspicliDll_0; "sspicli.dll"
0x18008e83f  call    cs:__imp_LoadLibraryW
0x18008e845  mov     [rbx+8], rax
0x18008e849  test    rax, rax
0x18008e84c  jnz     short loc_18008E8C7
0x18008e84e  mov     eax, cs:CallbackContext
0x18008e854  cmp     eax, 2
0x18008e857  jbe     loc_18008EACB
0x18008e85d  call    cs:__imp_GetLastError
0x18008e863  lea     rsi, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\s"...
0x18008e86a  mov     [rbp+arg_8], 19h
0x18008e871  mov     [rbp+arg_0], eax
0x18008e874  lea     rdi, aCsecurityfilte; "CSecurityFilterHelper"
0x18008e87b  lea     rax, aFailedToLoadSs; "Failed to load sspicli.dll! error = %d"
0x18008e882  mov     [rbp+var_18], rsi
0x18008e886  mov     [rbp+var_10], rax
0x18008e88a  lea     rdx, byte_1801AE795
0x18008e891  lea     rax, [rbp+arg_0]
0x18008e895  mov     [rsp+68h+var_20], rax
0x18008e89a  lea     rax, [rbp+arg_18]
0x18008e89e  mov     [rsp+68h+var_28], rax
0x18008e8a3  lea     rax, [rbp+arg_8]
0x18008e8a7  mov     [rsp+68h+var_30], rax
0x18008e8ac  lea     rax, [rbp+var_18]
0x18008e8b0  mov     [rsp+68h+var_38], rax
0x18008e8b5  lea     rax, [rbp+arg_10]
0x18008e8b9  mov     [rsp+68h+var_40], rax
0x18008e8be  lea     rax, [rbp+var_10]
0x18008e8c2  jmp     loc_18008EAB6
0x18008e8c7  lea     rdx, aSspimarshalaut; "SspiMarshalAuthIdentity"
0x18008e8ce  mov     rcx, rax; hModule
0x18008e8d1  call    cs:__imp_GetProcAddress
0x18008e8d7  mov     [rbx+20h], rax
0x18008e8db  lea     rdi, aCsecurityfilte; "CSecurityFilterHelper"
0x18008e8e2  lea     rsi, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\s"...
0x18008e8e9  test    rax, rax
0x18008e8ec  jnz     short loc_18008E965
0x18008e8ee  mov     eax, cs:CallbackContext
0x18008e8f4  cmp     eax, 2
0x18008e8f7  jbe     short loc_18008E965
0x18008e8f9  call    cs:__imp_GetLastError
0x18008e8ff  lea     rdx, qword_1801AE740
0x18008e906  mov     [rbp+arg_18], rdi
0x18008e90a  mov     [rbp+arg_0], eax
0x18008e90d  lea     rax, aFailedToObtain_1; "Failed to obtain address for SspiMarsha"...
0x18008e914  mov     [rbp+var_18], rax
0x18008e918  lea     rax, [rbp+arg_0]
0x18008e91c  mov     [rsp+68h+var_20], rax
0x18008e921  lea     rax, [rbp+arg_18]
0x18008e925  mov     [rsp+68h+var_28], rax
0x18008e92a  lea     rax, [rbp+arg_8]
0x18008e92e  mov     [rsp+68h+var_30], rax
0x18008e933  lea     rax, [rbp+var_10]
0x18008e937  mov     [rsp+68h+var_38], rax
0x18008e93c  lea     rax, [rbp+arg_10]
0x18008e940  mov     [rsp+68h+var_40], rax
0x18008e945  lea     rax, [rbp+var_18]
0x18008e949  mov     [rsp+68h+var_48], rax
0x18008e94e  mov     [rbp+arg_8], 20h ; ' '
0x18008e955  mov     [rbp+var_10], rsi
0x18008e959  mov     [rbp+arg_10], 80004005h
0x18008e960  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008e965  mov     rcx, [rbx+8]; hModule
0x18008e969  lea     rdx, aSspilocalfree; "SspiLocalFree"
0x18008e970  call    cs:__imp_GetProcAddress
0x18008e976  mov     [rbx+28h], rax
0x18008e97a  test    rax, rax
0x18008e97d  jnz     short loc_18008E9F6
0x18008e97f  mov     eax, cs:CallbackContext
0x18008e985  cmp     eax, 2
0x18008e988  jbe     short loc_18008E9F6
0x18008e98a  call    cs:__imp_GetLastError
0x18008e990  lea     rdx, byte_1801AE6EB
0x18008e997  mov     [rbp+arg_18], rdi
0x18008e99b  mov     [rbp+arg_0], eax
0x18008e99e  lea     rax, aFailedToObtain_0; "Failed to obtain address for SspiLocalF"...
0x18008e9a5  mov     [rbp+var_18], rax
0x18008e9a9  lea     rax, [rbp+arg_0]
0x18008e9ad  mov     [rsp+68h+var_20], rax
0x18008e9b2  lea     rax, [rbp+arg_18]
0x18008e9b6  mov     [rsp+68h+var_28], rax
0x18008e9bb  lea     rax, [rbp+arg_8]
0x18008e9bf  mov     [rsp+68h+var_30], rax
0x18008e9c4  lea     rax, [rbp+var_10]
0x18008e9c8  mov     [rsp+68h+var_38], rax
0x18008e9cd  lea     rax, [rbp+arg_10]
0x18008e9d1  mov     [rsp+68h+var_40], rax
0x18008e9d6  lea     rax, [rbp+var_18]
0x18008e9da  mov     [rsp+68h+var_48], rax
0x18008e9df  mov     [rbp+arg_8], 26h ; '&'
0x18008e9e6  mov     [rbp+var_10], rsi
0x18008e9ea  mov     [rbp+arg_10], 80004005h
0x18008e9f1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008e9f6  lea     rcx, aSecur32Dll; "Secur32.dll"
0x18008e9fd  call    cs:__imp_LoadLibraryW
0x18008ea03  mov     [rbx+10h], rax
0x18008ea07  test    rax, rax
0x18008ea0a  jnz     short loc_18008EA3B
0x18008ea0c  mov     eax, cs:CallbackContext
0x18008ea12  cmp     eax, 2
0x18008ea15  jbe     loc_18008EACB
0x18008ea1b  call    cs:__imp_GetLastError
0x18008ea21  mov     [rbp+arg_8], 2Ch ; ','
0x18008ea28  lea     rdx, word_1801AE696
0x18008ea2f  mov     [rbp+arg_0], eax
0x18008ea32  lea     rax, aFailedToLoadSe; "Failed to load Secur32.dll! error = %d"
0x18008ea39  jmp     short loc_18008EA7D
0x18008ea3b  lea     rdx, aSetcredentials; "SetCredentialsAttributesW"
0x18008ea42  mov     rcx, rax; hModule
0x18008ea45  call    cs:__imp_GetProcAddress
0x18008ea4b  mov     [rbx+18h], rax
0x18008ea4f  test    rax, rax
0x18008ea52  jnz     short loc_18008EACB
0x18008ea54  mov     eax, cs:CallbackContext
0x18008ea5a  cmp     eax, 2
0x18008ea5d  jbe     short loc_18008EACB
0x18008ea5f  call    cs:__imp_GetLastError
0x18008ea65  mov     [rbp+arg_8], 33h ; '3'
0x18008ea6c  lea     rdx, byte_1801AE641
0x18008ea73  mov     [rbp+arg_0], eax
0x18008ea76  lea     rax, aFailedToObtain; "Failed to obtain address for SetCredent"...
0x18008ea7d  mov     [rbp+var_18], rax
0x18008ea81  lea     rax, [rbp+arg_0]
0x18008ea85  mov     [rsp+68h+var_20], rax
0x18008ea8a  lea     rax, [rbp+arg_18]
0x18008ea8e  mov     [rsp+68h+var_28], rax
0x18008ea93  lea     rax, [rbp+arg_8]
0x18008ea97  mov     [rsp+68h+var_30], rax
0x18008ea9c  lea     rax, [rbp+var_10]
0x18008eaa0  mov     [rsp+68h+var_38], rax
0x18008eaa5  lea     rax, [rbp+arg_10]
0x18008eaa9  mov     [rsp+68h+var_40], rax
0x18008eaae  lea     rax, [rbp+var_18]
0x18008eab2  mov     [rbp+var_10], rsi
0x18008eab6  mov     [rsp+68h+var_48], rax
0x18008eabb  mov     [rbp+arg_18], rdi
0x18008eabf  mov     [rbp+arg_10], 80004005h
0x18008eac6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008eacb  mov     rax, rbx
0x18008eace  add     rsp, 68h
0x18008ead2  pop     rdi
0x18008ead3  pop     rsi
0x18008ead4  pop     rbx
0x18008ead5  pop     rbp
0x18008ead6  retn
```
