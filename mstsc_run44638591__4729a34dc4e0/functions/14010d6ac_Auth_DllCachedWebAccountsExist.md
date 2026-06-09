# Auth_DllCachedWebAccountsExist

- ea: `0x14010d6ac`
- end: `0x14010d8bf`
- name: `Auth_DllCachedWebAccountsExist`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400b8650`

## callees

- `0x1400026b0`
- `0x140004703`
- `0x140008a78`
- `0x14010d6ac`
- `0x140113390`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14010d7c8`
- `ADVAPI32!RegOpenKeyExW` at `0x14010d7c8`
- `ADVAPI32!RegCloseKey` at `0x14010d7d9`
- `ADVAPI32!RegCloseKey` at `0x14010d7d9`

## string_xrefs

- `0x14010d746`: `Auth_DllCachedWebAccountsExist`
- `0x14010d834`: `Auth_DllCachedWebAccountsExist`
- `0x14010d819`: `Failed to open Web accounts storage in registry`
- `0x14010d756`: `clientcore\termsrv\common\rdadalclient\lib\tokenhandler.aadj.cpp`
- `0x14010d844`: `clientcore\termsrv\common\rdadalclient\lib\tokenhandler.aadj.cpp`

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
  v1 = StringCchPrintfW(
         SubKey,
         0x104u,
         (size_t *)L"%s\\%s",
         g_pszRefreshTokenRootKey,
         L"5177bc73-fd99-4c77-a90c-76844c9b6999");
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
        if ( v8 && (unsigned int)dword_140152118 > 2 )
        {
          v11 = 146;
          v15 = "Failed to open Web accounts storage in registry";
          v10 = v7;
          v14 = "Auth_DllCachedWebAccountsExist";
          v13 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\tokenhandler.aadj.cpp";
          v12 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v7,
            (unsigned int)qword_140146820,
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
  else if ( (unsigned int)dword_140152118 > 2 )
  {
    v10 = 129;
    v12 = "StringCchPrintf failed";
    v11 = v1;
    v13 = "Auth_DllCachedWebAccountsExist";
    v14 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\tokenhandler.aadj.cpp";
    v15 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v1,
      (unsigned int)byte_1401467D3,
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
0x14010d6ac  mov     [rsp-8+arg_0], rbx
0x14010d6b1  push    rbp
0x14010d6b2  lea     rbp, [rsp-1A0h]
0x14010d6ba  sub     rsp, 2A0h
0x14010d6c1  mov     rax, cs:__security_cookie
0x14010d6c8  xor     rax, rsp
0x14010d6cb  mov     [rbp+1A0h+var_10], rax
0x14010d6d2  xor     edx, edx; Val
0x14010d6d4  lea     rcx, [rbp+1A0h+SubKey]; void *
0x14010d6d8  mov     r8d, 208h; Size
0x14010d6de  xor     ebx, ebx
0x14010d6e0  call    memset_0
0x14010d6e5  mov     r9, cs:?g_pszRefreshTokenRootKey@@3PEBGEB; ushort const * const g_pszRefreshTokenRootKey
0x14010d6ec  lea     rax, a5177bc73Fd994c; "5177bc73-fd99-4c77-a90c-76844c9b6999"
0x14010d6f3  lea     r8, aSS_0; "%s\\%s"
0x14010d6fa  mov     [rsp+2A0h+phkResult], rax
0x14010d6ff  mov     edx, 104h; unsigned __int64
0x14010d704  mov     [rsp+2A0h+hKey], rbx
0x14010d709  lea     rcx, [rbp+1A0h+SubKey]; unsigned __int16 *
0x14010d70d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14010d712  mov     ecx, eax
0x14010d714  test    eax, eax
0x14010d716  jns     loc_14010D7AA
0x14010d71c  mov     eax, cs:dword_140152118
0x14010d722  cmp     eax, 2
0x14010d725  jbe     loc_14010D89D
0x14010d72b  lea     rax, aStringcchprint_0; "StringCchPrintf failed"
0x14010d732  mov     [rsp+2A0h+var_250], 81h
0x14010d73a  mov     [rsp+2A0h+var_248], rax
0x14010d73f  lea     rdx, byte_1401467D3
0x14010d746  lea     rax, aAuthDllcachedw; "Auth_DllCachedWebAccountsExist"
0x14010d74d  mov     [rsp+2A0h+var_24C], ecx
0x14010d751  mov     [rsp+2A0h+var_240], rax
0x14010d756  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\common\\rdadalclie"...
0x14010d75d  mov     [rsp+2A0h+var_238], rax
0x14010d762  lea     rax, aErrorHresultFa; "Error HResult failed"
0x14010d769  mov     [rsp+2A0h+var_230], rax
0x14010d76e  lea     rax, [rsp+2A0h+var_248]
0x14010d773  mov     [rsp+2A0h+var_258], rax
0x14010d778  lea     rax, [rsp+2A0h+var_240]
0x14010d77d  mov     [rsp+2A0h+var_260], rax
0x14010d782  lea     rax, [rsp+2A0h+var_250]
0x14010d787  mov     [rsp+2A0h+var_268], rax
0x14010d78c  lea     rax, [rsp+2A0h+var_238]
0x14010d791  mov     [rsp+2A0h+var_270], rax
0x14010d796  lea     rax, [rsp+2A0h+var_24C]
0x14010d79b  mov     [rsp+2A0h+var_278], rax
0x14010d7a0  lea     rax, [rsp+2A0h+var_230]
0x14010d7a5  jmp     loc_14010D893
0x14010d7aa  lea     rax, [rsp+2A0h+hKey]
0x14010d7af  mov     r9d, 20019h; samDesired
0x14010d7b5  xor     r8d, r8d; ulOptions
0x14010d7b8  mov     [rsp+2A0h+phkResult], rax; phkResult
0x14010d7bd  lea     rdx, [rbp+1A0h+SubKey]; lpSubKey
0x14010d7c1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14010d7c8  call    cs:__imp_RegOpenKeyExW
0x14010d7ce  mov     ecx, eax
0x14010d7d0  test    eax, eax
0x14010d7d2  jnz     short loc_14010D7E9
0x14010d7d4  mov     rcx, [rsp+2A0h+hKey]; hKey
0x14010d7d9  call    cs:__imp_RegCloseKey
0x14010d7df  mov     ebx, 1
0x14010d7e4  jmp     loc_14010D89D
0x14010d7e9  add     eax, 0FFFFFFFEh
0x14010d7ec  cmp     eax, 1
0x14010d7ef  jbe     loc_14010D89D
0x14010d7f5  test    ecx, ecx
0x14010d7f7  jle     short loc_14010D804
0x14010d7f9  movzx   ecx, cx
0x14010d7fc  or      ecx, 80070000h
0x14010d802  test    ecx, ecx
0x14010d804  jns     loc_14010D89D
0x14010d80a  mov     eax, cs:dword_140152118
0x14010d810  cmp     eax, 2
0x14010d813  jbe     loc_14010D89D
0x14010d819  lea     rax, aFailedToOpenWe; "Failed to open Web accounts storage in "...
0x14010d820  mov     [rsp+2A0h+var_24C], 92h
0x14010d828  mov     [rsp+2A0h+var_230], rax
0x14010d82d  lea     rdx, qword_140146820
0x14010d834  lea     rax, aAuthDllcachedw; "Auth_DllCachedWebAccountsExist"
0x14010d83b  mov     [rsp+2A0h+var_250], ecx
0x14010d83f  mov     [rsp+2A0h+var_238], rax
0x14010d844  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\common\\rdadalclie"...
0x14010d84b  mov     [rsp+2A0h+var_240], rax
0x14010d850  lea     rax, aErrorHresultFa; "Error HResult failed"
0x14010d857  mov     [rsp+2A0h+var_248], rax
0x14010d85c  lea     rax, [rsp+2A0h+var_230]
0x14010d861  mov     [rsp+2A0h+var_258], rax
0x14010d866  lea     rax, [rsp+2A0h+var_238]
0x14010d86b  mov     [rsp+2A0h+var_260], rax
0x14010d870  lea     rax, [rsp+2A0h+var_24C]
0x14010d875  mov     [rsp+2A0h+var_268], rax
0x14010d87a  lea     rax, [rsp+2A0h+var_240]
0x14010d87f  mov     [rsp+2A0h+var_270], rax
0x14010d884  lea     rax, [rsp+2A0h+var_250]
0x14010d889  mov     [rsp+2A0h+var_278], rax
0x14010d88e  lea     rax, [rsp+2A0h+var_248]
0x14010d893  mov     [rsp+2A0h+phkResult], rax
0x14010d898  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14010d89d  mov     eax, ebx
0x14010d89f  mov     rcx, [rbp+1A0h+var_10]
0x14010d8a6  xor     rcx, rsp; StackCookie
0x14010d8a9  call    __security_check_cookie
0x14010d8ae  mov     rbx, [rsp+2A0h+arg_0]
0x14010d8b6  add     rsp, 2A0h
0x14010d8bd  pop     rbp
0x14010d8be  retn
```
