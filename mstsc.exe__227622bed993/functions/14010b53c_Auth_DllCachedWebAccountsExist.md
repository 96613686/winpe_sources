# Auth_DllCachedWebAccountsExist

- ea: `0x14010b53c`
- end: `0x14010b74f`
- name: `Auth_DllCachedWebAccountsExist`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400b64e0`

## callees

- `0x1400026b0`
- `0x140004703`
- `0x140008a78`
- `0x14010b53c`
- `0x140111220`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14010b658`
- `ADVAPI32!RegOpenKeyExW` at `0x14010b658`
- `ADVAPI32!RegCloseKey` at `0x14010b669`
- `ADVAPI32!RegCloseKey` at `0x14010b669`

## string_xrefs

- `0x14010b6a9`: `Failed to open Web accounts storage in registry`
- `0x14010b5e6`: `clientcore\termsrv\common\rdadalclient\lib\tokenhandler.aadj.cpp`
- `0x14010b6d4`: `clientcore\termsrv\common\rdadalclient\lib\tokenhandler.aadj.cpp`
- `0x14010b5d6`: `Auth_DllCachedWebAccountsExist`
- `0x14010b6c4`: `Auth_DllCachedWebAccountsExist`

## pseudocode

```c
__int64 Auth_DllCachedWebAccountsExist()
{
  unsigned int v0; // ebx
  int v1; // ecx
  int v2; // r8d
  int v3; // r9d
  LSTATUS v4; // eax
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // ecx
  bool v8; // sf
  int v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+54h] [rbp-ACh] BYREF
  const char *v12; // [rsp+58h] [rbp-A8h] BYREF
  const char *v13; // [rsp+60h] [rbp-A0h] BYREF
  const char *v14; // [rsp+68h] [rbp-98h] BYREF
  const char *v15; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  v0 = 0;
  memset_0(SubKey, 0, 0x208u);
  hKey = 0;
  v1 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", g_pszRefreshTokenRootKey, L"5177bc73-fd99-4c77-a90c-76844c9b6999");
  if ( v1 >= 0 )
  {
    v4 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20019u, &hKey);
    v7 = v4;
    if ( v4 )
    {
      if ( (unsigned int)(v4 - 2) > 1 )
      {
        v8 = v4 < 0;
        if ( v4 > 0 )
        {
          v7 = (unsigned __int16)v4 | 0x80070000;
          v8 = 1;
        }
        if ( v8 && (unsigned int)dword_140150118 > 2 )
        {
          v11 = 146;
          v15 = "Failed to open Web accounts storage in registry";
          v10 = v7;
          v14 = "Auth_DllCachedWebAccountsExist";
          v13 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\tokenhandler.aadj.cpp";
          v12 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v7,
            (unsigned int)&byte_1401447CF,
            v5,
            v6,
            (__int64)&v12,
            (__int64)&v10,
            (__int64)&v13,
            (__int64)&v11,
            (__int64)&v14,
            (__int64)&v15);
        }
      }
    }
    else
    {
      RegCloseKey(hKey);
      return 1;
    }
  }
  else if ( (unsigned int)dword_140150118 > 2 )
  {
    v10 = 129;
    v12 = "StringCchPrintf failed";
    v11 = v1;
    v13 = "Auth_DllCachedWebAccountsExist";
    v14 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\tokenhandler.aadj.cpp";
    v15 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v1,
      (unsigned int)word_140144782,
      v2,
      v3,
      (__int64)&v15,
      (__int64)&v11,
      (__int64)&v14,
      (__int64)&v10,
      (__int64)&v13,
      (__int64)&v12);
  }
  return v0;
}

```

## disassembly

```asm
0x14010b53c  mov     [rsp-8+arg_0], rbx
0x14010b541  push    rbp
0x14010b542  lea     rbp, [rsp-1A0h]
0x14010b54a  sub     rsp, 2A0h
0x14010b551  mov     rax, cs:__security_cookie
0x14010b558  xor     rax, rsp
0x14010b55b  mov     [rbp+1A0h+var_10], rax
0x14010b562  xor     edx, edx; Val
0x14010b564  lea     rcx, [rbp+1A0h+SubKey]; void *
0x14010b568  mov     r8d, 208h; Size
0x14010b56e  xor     ebx, ebx
0x14010b570  call    memset_0
0x14010b575  mov     r9, cs:?g_pszRefreshTokenRootKey@@3PEBGEB; ushort const * const g_pszRefreshTokenRootKey
0x14010b57c  lea     rax, a5177bc73Fd994c; "5177bc73-fd99-4c77-a90c-76844c9b6999"
0x14010b583  lea     r8, aSS_0; "%s\\%s"
0x14010b58a  mov     [rsp+2A0h+phkResult], rax
0x14010b58f  mov     edx, 104h; unsigned __int64
0x14010b594  mov     [rsp+2A0h+hKey], rbx
0x14010b599  lea     rcx, [rbp+1A0h+SubKey]; unsigned __int16 *
0x14010b59d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14010b5a2  mov     ecx, eax
0x14010b5a4  test    eax, eax
0x14010b5a6  jns     loc_14010B63A
0x14010b5ac  mov     eax, cs:dword_140150118
0x14010b5b2  cmp     eax, 2
0x14010b5b5  jbe     loc_14010B72D
0x14010b5bb  lea     rax, aStringcchprint_0; "StringCchPrintf failed"
0x14010b5c2  mov     [rsp+2A0h+var_250], 81h
0x14010b5ca  mov     [rsp+2A0h+var_248], rax
0x14010b5cf  lea     rdx, word_140144782
0x14010b5d6  lea     rax, aAuthDllcachedw; "Auth_DllCachedWebAccountsExist"
0x14010b5dd  mov     [rsp+2A0h+var_24C], ecx
0x14010b5e1  mov     [rsp+2A0h+var_240], rax
0x14010b5e6  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\common\\rdadalclie"...
0x14010b5ed  mov     [rsp+2A0h+var_238], rax
0x14010b5f2  lea     rax, aErrorHresultFa; "Error HResult failed"
0x14010b5f9  mov     [rsp+2A0h+var_230], rax
0x14010b5fe  lea     rax, [rsp+2A0h+var_248]
0x14010b603  mov     [rsp+2A0h+var_258], rax
0x14010b608  lea     rax, [rsp+2A0h+var_240]
0x14010b60d  mov     [rsp+2A0h+var_260], rax
0x14010b612  lea     rax, [rsp+2A0h+var_250]
0x14010b617  mov     [rsp+2A0h+var_268], rax
0x14010b61c  lea     rax, [rsp+2A0h+var_238]
0x14010b621  mov     [rsp+2A0h+var_270], rax
0x14010b626  lea     rax, [rsp+2A0h+var_24C]
0x14010b62b  mov     [rsp+2A0h+var_278], rax
0x14010b630  lea     rax, [rsp+2A0h+var_230]
0x14010b635  jmp     loc_14010B723
0x14010b63a  lea     rax, [rsp+2A0h+hKey]
0x14010b63f  mov     r9d, 20019h; samDesired
0x14010b645  xor     r8d, r8d; ulOptions
0x14010b648  mov     [rsp+2A0h+phkResult], rax; phkResult
0x14010b64d  lea     rdx, [rbp+1A0h+SubKey]; lpSubKey
0x14010b651  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14010b658  call    cs:__imp_RegOpenKeyExW
0x14010b65e  mov     ecx, eax
0x14010b660  test    eax, eax
0x14010b662  jnz     short loc_14010B679
0x14010b664  mov     rcx, [rsp+2A0h+hKey]; hKey
0x14010b669  call    cs:__imp_RegCloseKey
0x14010b66f  mov     ebx, 1
0x14010b674  jmp     loc_14010B72D
0x14010b679  add     eax, 0FFFFFFFEh
0x14010b67c  cmp     eax, 1
0x14010b67f  jbe     loc_14010B72D
0x14010b685  test    ecx, ecx
0x14010b687  jle     short loc_14010B694
0x14010b689  movzx   ecx, cx
0x14010b68c  or      ecx, 80070000h
0x14010b692  test    ecx, ecx
0x14010b694  jns     loc_14010B72D
0x14010b69a  mov     eax, cs:dword_140150118
0x14010b6a0  cmp     eax, 2
0x14010b6a3  jbe     loc_14010B72D
0x14010b6a9  lea     rax, aFailedToOpenWe; "Failed to open Web accounts storage in "...
0x14010b6b0  mov     [rsp+2A0h+var_24C], 92h
0x14010b6b8  mov     [rsp+2A0h+var_230], rax
0x14010b6bd  lea     rdx, byte_1401447CF
0x14010b6c4  lea     rax, aAuthDllcachedw; "Auth_DllCachedWebAccountsExist"
0x14010b6cb  mov     [rsp+2A0h+var_250], ecx
0x14010b6cf  mov     [rsp+2A0h+var_238], rax
0x14010b6d4  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\common\\rdadalclie"...
0x14010b6db  mov     [rsp+2A0h+var_240], rax
0x14010b6e0  lea     rax, aErrorHresultFa; "Error HResult failed"
0x14010b6e7  mov     [rsp+2A0h+var_248], rax
0x14010b6ec  lea     rax, [rsp+2A0h+var_230]
0x14010b6f1  mov     [rsp+2A0h+var_258], rax
0x14010b6f6  lea     rax, [rsp+2A0h+var_238]
0x14010b6fb  mov     [rsp+2A0h+var_260], rax
0x14010b700  lea     rax, [rsp+2A0h+var_24C]
0x14010b705  mov     [rsp+2A0h+var_268], rax
0x14010b70a  lea     rax, [rsp+2A0h+var_240]
0x14010b70f  mov     [rsp+2A0h+var_270], rax
0x14010b714  lea     rax, [rsp+2A0h+var_250]
0x14010b719  mov     [rsp+2A0h+var_278], rax
0x14010b71e  lea     rax, [rsp+2A0h+var_248]
0x14010b723  mov     [rsp+2A0h+phkResult], rax
0x14010b728  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14010b72d  mov     eax, ebx
0x14010b72f  mov     rcx, [rbp+1A0h+var_10]
0x14010b736  xor     rcx, rsp; StackCookie
0x14010b739  call    __security_check_cookie
0x14010b73e  mov     rbx, [rsp+2A0h+arg_0]
0x14010b746  add     rsp, 2A0h
0x14010b74d  pop     rbp
0x14010b74e  retn
```
