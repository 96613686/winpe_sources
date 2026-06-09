# CSecurityFilterHelper::CSecurityFilterHelper(void)

- ea: `0x18039a8d0`
- end: `0x18039abb7`
- name: `??0CSecurityFilterHelper@@QEAA@XZ`
- size: `743`
- prototype: `CSecurityFilterHelper *__fastcall(CSecurityFilterHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1803230b4`

## callees

- `0x180001e8c`
- `0x18039a8d0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18039a91f`
- `KERNEL32!LoadLibraryW` at `0x18039aadd`
- `KERNEL32!LoadLibraryW` at `0x18039a91f`
- `KERNEL32!LoadLibraryW` at `0x18039aadd`
- `KERNEL32!GetLastError` at `0x18039a93d`
- `KERNEL32!GetLastError` at `0x18039a9d9`
- `KERNEL32!GetLastError` at `0x18039aa6a`
- `KERNEL32!GetLastError` at `0x18039aafb`
- `KERNEL32!GetLastError` at `0x18039ab3f`
- `KERNEL32!GetLastError` at `0x18039a93d`
- `KERNEL32!GetLastError` at `0x18039a9d9`
- `KERNEL32!GetLastError` at `0x18039aa6a`
- `KERNEL32!GetLastError` at `0x18039aafb`
- `KERNEL32!GetLastError` at `0x18039ab3f`
- `KERNEL32!GetProcAddress` at `0x18039a9b1`
- `KERNEL32!GetProcAddress` at `0x18039aa50`
- `KERNEL32!GetProcAddress` at `0x18039ab25`
- `KERNEL32!GetProcAddress` at `0x18039a9b1`
- `KERNEL32!GetProcAddress` at `0x18039aa50`
- `KERNEL32!GetProcAddress` at `0x18039ab25`

## string_xrefs

- `0x18039a95b`: `Failed to load sspicli.dll! error = %d`
- `0x18039a943`: `onecore\termsrv\rdp\win\security\securityfilterhelper.cpp`
- `0x18039a9c2`: `onecore\termsrv\rdp\win\security\securityfilterhelper.cpp`
- `0x18039a954`: `CSecurityFilterHelper`
- `0x18039a9bb`: `CSecurityFilterHelper`
- `0x18039a918`: `sspicli.dll`
- `0x18039ab12`: `Failed to load Secur32.dll! error = %d`
- `0x18039aad6`: `Secur32.dll`

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
    if ( !ProcAddress && (unsigned int)dword_1808B5850 > 2 )
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
        (unsigned int)byte_180873821,
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
    if ( !v14 && (unsigned int)dword_1808B5850 > 2 )
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
        (unsigned int)word_180873722,
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
      if ( v22 || (unsigned int)dword_1808B5850 <= 2 )
        return this;
      v23 = GetLastError();
      v29 = 51;
      v7 = byte_1808736CD;
      v28 = v23;
      v21 = "Failed to obtain address for SetCredentialsAttributesW! error = %d";
    }
    else
    {
      if ( (unsigned int)dword_1808B5850 <= 2 )
        return this;
      v20 = GetLastError();
      v29 = 44;
      v7 = &byte_180873777;
      v28 = v20;
      v21 = "Failed to load Secur32.dll! error = %d";
    }
    v26 = v21;
    v25 = (const char **)v27;
    v8 = &v26;
    v27[0] = "onecore\\termsrv\\rdp\\win\\security\\securityfilterhelper.cpp";
    goto LABEL_17;
  }
  if ( (unsigned int)dword_1808B5850 > 2 )
  {
    v3 = GetLastError();
    v29 = 25;
    v28 = v3;
    v26 = "onecore\\termsrv\\rdp\\win\\security\\securityfilterhelper.cpp";
    v27[0] = "Failed to load sspicli.dll! error = %d";
    v7 = (char *)&dword_1808737CC;
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
0x18039a8d0  push    rbp
0x18039a8d2  push    rbx
0x18039a8d3  push    rsi
0x18039a8d4  push    rdi
0x18039a8d5  mov     rbp, rsp
0x18039a8d8  sub     rsp, 68h
0x18039a8dc  mov     qword ptr [rcx+8], 0
0x18039a8e4  lea     rax, ??_7CSecurityFilterHelper@@6B@; const CSecurityFilterHelper::`vftable'
0x18039a8eb  mov     [rcx], rax
0x18039a8ee  mov     rbx, rcx
0x18039a8f1  mov     qword ptr [rcx+10h], 0
0x18039a8f9  mov     qword ptr [rcx+18h], 0
0x18039a901  mov     qword ptr [rcx+20h], 0
0x18039a909  mov     qword ptr [rcx+28h], 0
0x18039a911  mov     dword ptr [rcx+30h], 0
0x18039a918  lea     rcx, aSspicliDll; "sspicli.dll"
0x18039a91f  call    cs:__imp_LoadLibraryW
0x18039a925  mov     [rbx+8], rax
0x18039a929  test    rax, rax
0x18039a92c  jnz     short loc_18039A9A7
0x18039a92e  mov     eax, cs:dword_1808B5850
0x18039a934  cmp     eax, 2
0x18039a937  jbe     loc_18039ABAB
0x18039a93d  call    cs:__imp_GetLastError
0x18039a943  lea     rsi, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\s"...
0x18039a94a  mov     [rbp+arg_8], 19h
0x18039a951  mov     [rbp+arg_0], eax
0x18039a954  lea     rdi, aCsecurityfilte; "CSecurityFilterHelper"
0x18039a95b  lea     rax, aFailedToLoadSs; "Failed to load sspicli.dll! error = %d"
0x18039a962  mov     [rbp+var_18], rsi
0x18039a966  mov     [rbp+var_10], rax
0x18039a96a  lea     rdx, dword_1808737CC
0x18039a971  lea     rax, [rbp+arg_0]
0x18039a975  mov     [rsp+68h+var_20], rax
0x18039a97a  lea     rax, [rbp+arg_18]
0x18039a97e  mov     [rsp+68h+var_28], rax
0x18039a983  lea     rax, [rbp+arg_8]
0x18039a987  mov     [rsp+68h+var_30], rax
0x18039a98c  lea     rax, [rbp+var_18]
0x18039a990  mov     [rsp+68h+var_38], rax
0x18039a995  lea     rax, [rbp+arg_10]
0x18039a999  mov     [rsp+68h+var_40], rax
0x18039a99e  lea     rax, [rbp+var_10]
0x18039a9a2  jmp     loc_18039AB96
0x18039a9a7  lea     rdx, aSspimarshalaut; "SspiMarshalAuthIdentity"
0x18039a9ae  mov     rcx, rax; hModule
0x18039a9b1  call    cs:__imp_GetProcAddress
0x18039a9b7  mov     [rbx+20h], rax
0x18039a9bb  lea     rdi, aCsecurityfilte; "CSecurityFilterHelper"
0x18039a9c2  lea     rsi, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\s"...
0x18039a9c9  test    rax, rax
0x18039a9cc  jnz     short loc_18039AA45
0x18039a9ce  mov     eax, cs:dword_1808B5850
0x18039a9d4  cmp     eax, 2
0x18039a9d7  jbe     short loc_18039AA45
0x18039a9d9  call    cs:__imp_GetLastError
0x18039a9df  lea     rdx, byte_180873821
0x18039a9e6  mov     [rbp+arg_18], rdi
0x18039a9ea  mov     [rbp+arg_0], eax
0x18039a9ed  lea     rax, aFailedToObtain_4; "Failed to obtain address for SspiMarsha"...
0x18039a9f4  mov     [rbp+var_18], rax
0x18039a9f8  lea     rax, [rbp+arg_0]
0x18039a9fc  mov     [rsp+68h+var_20], rax
0x18039aa01  lea     rax, [rbp+arg_18]
0x18039aa05  mov     [rsp+68h+var_28], rax
0x18039aa0a  lea     rax, [rbp+arg_8]
0x18039aa0e  mov     [rsp+68h+var_30], rax
0x18039aa13  lea     rax, [rbp+var_10]
0x18039aa17  mov     [rsp+68h+var_38], rax
0x18039aa1c  lea     rax, [rbp+arg_10]
0x18039aa20  mov     [rsp+68h+var_40], rax
0x18039aa25  lea     rax, [rbp+var_18]
0x18039aa29  mov     [rsp+68h+var_48], rax
0x18039aa2e  mov     [rbp+arg_8], 20h ; ' '
0x18039aa35  mov     [rbp+var_10], rsi
0x18039aa39  mov     [rbp+arg_10], 80004005h
0x18039aa40  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18039aa45  mov     rcx, [rbx+8]; hModule
0x18039aa49  lea     rdx, aSspilocalfree; "SspiLocalFree"
0x18039aa50  call    cs:__imp_GetProcAddress
0x18039aa56  mov     [rbx+28h], rax
0x18039aa5a  test    rax, rax
0x18039aa5d  jnz     short loc_18039AAD6
0x18039aa5f  mov     eax, cs:dword_1808B5850
0x18039aa65  cmp     eax, 2
0x18039aa68  jbe     short loc_18039AAD6
0x18039aa6a  call    cs:__imp_GetLastError
0x18039aa70  lea     rdx, word_180873722
0x18039aa77  mov     [rbp+arg_18], rdi
0x18039aa7b  mov     [rbp+arg_0], eax
0x18039aa7e  lea     rax, aFailedToObtain_2; "Failed to obtain address for SspiLocalF"...
0x18039aa85  mov     [rbp+var_18], rax
0x18039aa89  lea     rax, [rbp+arg_0]
0x18039aa8d  mov     [rsp+68h+var_20], rax
0x18039aa92  lea     rax, [rbp+arg_18]
0x18039aa96  mov     [rsp+68h+var_28], rax
0x18039aa9b  lea     rax, [rbp+arg_8]
0x18039aa9f  mov     [rsp+68h+var_30], rax
0x18039aaa4  lea     rax, [rbp+var_10]
0x18039aaa8  mov     [rsp+68h+var_38], rax
0x18039aaad  lea     rax, [rbp+arg_10]
0x18039aab1  mov     [rsp+68h+var_40], rax
0x18039aab6  lea     rax, [rbp+var_18]
0x18039aaba  mov     [rsp+68h+var_48], rax
0x18039aabf  mov     [rbp+arg_8], 26h ; '&'
0x18039aac6  mov     [rbp+var_10], rsi
0x18039aaca  mov     [rbp+arg_10], 80004005h
0x18039aad1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18039aad6  lea     rcx, aSecur32Dll_0; "Secur32.dll"
0x18039aadd  call    cs:__imp_LoadLibraryW
0x18039aae3  mov     [rbx+10h], rax
0x18039aae7  test    rax, rax
0x18039aaea  jnz     short loc_18039AB1B
0x18039aaec  mov     eax, cs:dword_1808B5850
0x18039aaf2  cmp     eax, 2
0x18039aaf5  jbe     loc_18039ABAB
0x18039aafb  call    cs:__imp_GetLastError
0x18039ab01  mov     [rbp+arg_8], 2Ch ; ','
0x18039ab08  lea     rdx, byte_180873777
0x18039ab0f  mov     [rbp+arg_0], eax
0x18039ab12  lea     rax, aFailedToLoadSe_0; "Failed to load Secur32.dll! error = %d"
0x18039ab19  jmp     short loc_18039AB5D
0x18039ab1b  lea     rdx, aSetcredentials; "SetCredentialsAttributesW"
0x18039ab22  mov     rcx, rax; hModule
0x18039ab25  call    cs:__imp_GetProcAddress
0x18039ab2b  mov     [rbx+18h], rax
0x18039ab2f  test    rax, rax
0x18039ab32  jnz     short loc_18039ABAB
0x18039ab34  mov     eax, cs:dword_1808B5850
0x18039ab3a  cmp     eax, 2
0x18039ab3d  jbe     short loc_18039ABAB
0x18039ab3f  call    cs:__imp_GetLastError
0x18039ab45  mov     [rbp+arg_8], 33h ; '3'
0x18039ab4c  lea     rdx, byte_1808736CD
0x18039ab53  mov     [rbp+arg_0], eax
0x18039ab56  lea     rax, aFailedToObtain_0; "Failed to obtain address for SetCredent"...
0x18039ab5d  mov     [rbp+var_18], rax
0x18039ab61  lea     rax, [rbp+arg_0]
0x18039ab65  mov     [rsp+68h+var_20], rax
0x18039ab6a  lea     rax, [rbp+arg_18]
0x18039ab6e  mov     [rsp+68h+var_28], rax
0x18039ab73  lea     rax, [rbp+arg_8]
0x18039ab77  mov     [rsp+68h+var_30], rax
0x18039ab7c  lea     rax, [rbp+var_10]
0x18039ab80  mov     [rsp+68h+var_38], rax
0x18039ab85  lea     rax, [rbp+arg_10]
0x18039ab89  mov     [rsp+68h+var_40], rax
0x18039ab8e  lea     rax, [rbp+var_18]
0x18039ab92  mov     [rbp+var_10], rsi
0x18039ab96  mov     [rsp+68h+var_48], rax
0x18039ab9b  mov     [rbp+arg_18], rdi
0x18039ab9f  mov     [rbp+arg_10], 80004005h
0x18039aba6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18039abab  mov     rax, rbx
0x18039abae  add     rsp, 68h
0x18039abb2  pop     rdi
0x18039abb3  pop     rsi
0x18039abb4  pop     rbx
0x18039abb5  pop     rbp
0x18039abb6  retn
```
