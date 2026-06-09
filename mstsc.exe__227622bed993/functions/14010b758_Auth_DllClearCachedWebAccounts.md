# Auth_DllClearCachedWebAccounts

- ea: `0x14010b758`
- end: `0x14010ba42`
- name: `Auth_DllClearCachedWebAccounts`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400b4c14`

## callees

- `0x1400026b0`
- `0x140004703`
- `0x140008a78`
- `0x14010b758`
- `0x14010d35c`
- `0x140111220`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14010b79b`
- `OLEAUT32!__imp_SysAllocString` at `0x14010b850`
- `OLEAUT32!__imp_SysAllocString` at `0x14010b79b`
- `OLEAUT32!__imp_SysAllocString` at `0x14010b850`
- `OLEAUT32!__imp_SysFreeString` at `0x14010ba0a`
- `OLEAUT32!__imp_SysFreeString` at `0x14010ba18`
- `OLEAUT32!__imp_SysFreeString` at `0x14010ba0a`
- `OLEAUT32!__imp_SysFreeString` at `0x14010ba18`
- `ADVAPI32!RegDeleteTreeW` at `0x14010b957`
- `ADVAPI32!RegDeleteTreeW` at `0x14010b957`

## string_xrefs

- `0x14010b8df`: `ClearCachedWebAccounts failed`
- `0x14010b7d7`: `Auth_DllClearCachedWebAccounts`
- `0x14010b888`: `Auth_DllClearCachedWebAccounts`
- `0x14010b9a2`: `Auth_DllClearCachedWebAccounts`
- `0x14010b7eb`: `clientcore\termsrv\common\rdadalclient\lib\tokenhandler.aadj.cpp`
- `0x14010b89c`: `clientcore\termsrv\common\rdadalclient\lib\tokenhandler.aadj.cpp`
- `0x14010b9ae`: `clientcore\termsrv\common\rdadalclient\lib\tokenhandler.aadj.cpp`
- `0x14010b983`: `Failed to delete Web accounts storage from registry`

## pseudocode

```c
void Auth_DllClearCachedWebAccounts()
{
  int v0; // ecx
  unsigned __int16 *v1; // rdi
  int v2; // r8d
  int v3; // r9d
  unsigned __int16 *v4; // rax
  int v5; // r8d
  int v6; // r9d
  OLECHAR *v7; // rbx
  signed int v8; // ecx
  char *v9; // rdx
  const char *v10; // rax
  int v11; // edx
  const char *v12; // rax
  int v13; // edx
  LSTATUS v14; // eax
  int v15; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+54h] [rbp-ACh] BYREF
  const char *v17; // [rsp+58h] [rbp-A8h] BYREF
  const char *v18; // [rsp+60h] [rbp-A0h] BYREF
  const char *v19; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v20[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  memset_0(SubKey, 0, 0x208u);
  v1 = SysAllocString(L"5177bc73-fd99-4c77-a90c-76844c9b6999");
  if ( !v1 )
  {
    if ( (unsigned int)dword_140150118 > 2 )
    {
      v15 = 187;
      v17 = "SysAllocString returned NULL";
      v16 = -2147024882;
      v18 = "Auth_DllClearCachedWebAccounts";
      v19 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\tokenhandler.aadj.cpp";
      v20[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v0,
        (unsigned int)qword_1401446E8,
        v2,
        v3,
        (__int64)v20,
        (__int64)&v16,
        (__int64)&v19,
        (__int64)&v15,
        (__int64)&v18,
        (__int64)&v17);
    }
    return;
  }
  v4 = SysAllocString(L"organizations");
  v7 = v4;
  if ( v4 )
  {
    v11 = CWAMTokenHandler::ClearCachedWebAccounts((CWAMTokenHandler *)&g_WAMHandler, v1, v4);
    if ( v11 >= 0 )
    {
      v13 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", g_pszRefreshTokenRootKey, v1);
      if ( v13 >= 0 )
      {
        v14 = RegDeleteTreeW(HKEY_CURRENT_USER, SubKey);
        v8 = v14;
        if ( v14 > 0 )
          v8 = (unsigned __int16)v14 | 0x80070000;
        if ( v8 >= 0 || (unsigned int)dword_140150118 <= 2 )
          goto LABEL_20;
        v12 = "Failed to delete Web accounts storage from registry";
        v16 = 217;
        v15 = v8;
        v9 = byte_14014469B;
      }
      else
      {
        v8 = dword_140150118;
        if ( (unsigned int)dword_140150118 <= 2 )
          goto LABEL_20;
        v15 = v13;
        v12 = "StringCchPrintf failed";
        v9 = byte_140144601;
        v16 = 213;
      }
    }
    else
    {
      v8 = dword_140150118;
      if ( (unsigned int)dword_140150118 <= 2 )
        goto LABEL_20;
      v15 = v11;
      v12 = "ClearCachedWebAccounts failed";
      v9 = (char *)&word_14014464E;
      v16 = 207;
    }
    v20[0] = v12;
    v19 = "Auth_DllClearCachedWebAccounts";
    v18 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\tokenhandler.aadj.cpp";
    v10 = "Error HResult failed";
  }
  else
  {
    v8 = dword_140150118;
    if ( (unsigned int)dword_140150118 <= 2 )
      goto LABEL_20;
    v16 = 197;
    v20[0] = "SysAllocString returned NULL";
    v9 = byte_140144735;
    v15 = -2147024882;
    v19 = "Auth_DllClearCachedWebAccounts";
    v18 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\tokenhandler.aadj.cpp";
    v10 = "Error condition failed";
  }
  v17 = v10;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
    v8,
    (_DWORD)v9,
    v5,
    v6,
    (__int64)&v17,
    (__int64)&v15,
    (__int64)&v18,
    (__int64)&v16,
    (__int64)&v19,
    (__int64)v20);
LABEL_20:
  SysFreeString(v1);
  if ( v7 )
    SysFreeString(v7);
}

```

## disassembly

```asm
0x14010b758  mov     [rsp-8+arg_0], rbx
0x14010b75d  mov     [rsp-8+arg_8], rdi
0x14010b762  push    rbp
0x14010b763  lea     rbp, [rsp-1A0h]
0x14010b76b  sub     rsp, 2A0h
0x14010b772  mov     rax, cs:__security_cookie
0x14010b779  xor     rax, rsp
0x14010b77c  mov     [rbp+1A0h+var_10], rax
0x14010b783  xor     edx, edx; Val
0x14010b785  lea     rcx, [rbp+1A0h+SubKey]; void *
0x14010b789  mov     r8d, 208h; Size
0x14010b78f  call    memset_0
0x14010b794  lea     rcx, a5177bc73Fd994c; "5177bc73-fd99-4c77-a90c-76844c9b6999"
0x14010b79b  call    cs:__imp_SysAllocString
0x14010b7a1  mov     rdi, rax
0x14010b7a4  test    rax, rax
0x14010b7a7  jnz     loc_14010B849
0x14010b7ad  mov     eax, cs:dword_140150118
0x14010b7b3  cmp     eax, 2
0x14010b7b6  jbe     loc_14010BA1E
0x14010b7bc  lea     rax, aSysallocstring; "SysAllocString returned NULL"
0x14010b7c3  mov     [rsp+2A0h+var_250], 0BBh
0x14010b7cb  mov     [rsp+2A0h+var_248], rax
0x14010b7d0  lea     rdx, qword_1401446E8
0x14010b7d7  lea     rax, aAuthDllclearca; "Auth_DllClearCachedWebAccounts"
0x14010b7de  mov     [rsp+2A0h+var_24C], 8007000Eh
0x14010b7e6  mov     [rsp+2A0h+var_240], rax
0x14010b7eb  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\common\\rdadalclie"...
0x14010b7f2  mov     [rsp+2A0h+var_238], rax
0x14010b7f7  lea     rax, aErrorCondition; "Error condition failed"
0x14010b7fe  mov     [rsp+2A0h+var_230], rax
0x14010b803  lea     rax, [rsp+2A0h+var_248]
0x14010b808  mov     [rsp+2A0h+var_258], rax
0x14010b80d  lea     rax, [rsp+2A0h+var_240]
0x14010b812  mov     [rsp+2A0h+var_260], rax
0x14010b817  lea     rax, [rsp+2A0h+var_250]
0x14010b81c  mov     [rsp+2A0h+var_268], rax
0x14010b821  lea     rax, [rsp+2A0h+var_238]
0x14010b826  mov     [rsp+2A0h+var_270], rax
0x14010b82b  lea     rax, [rsp+2A0h+var_24C]
0x14010b830  mov     [rsp+2A0h+var_278], rax
0x14010b835  lea     rax, [rsp+2A0h+var_230]
0x14010b83a  mov     [rsp+2A0h+var_280], rax
0x14010b83f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14010b844  jmp     loc_14010BA1E
0x14010b849  lea     rcx, aOrganizations; "organizations"
0x14010b850  call    cs:__imp_SysAllocString
0x14010b856  mov     rbx, rax
0x14010b859  test    rax, rax
0x14010b85c  jnz     short loc_14010B8B4
0x14010b85e  mov     ecx, cs:dword_140150118
0x14010b864  cmp     ecx, 2
0x14010b867  jbe     loc_14010BA07
0x14010b86d  lea     rax, aSysallocstring; "SysAllocString returned NULL"
0x14010b874  mov     [rsp+2A0h+var_24C], 0C5h
0x14010b87c  mov     [rsp+2A0h+var_230], rax
0x14010b881  lea     rdx, byte_140144735
0x14010b888  lea     rax, aAuthDllclearca; "Auth_DllClearCachedWebAccounts"
0x14010b88f  mov     [rsp+2A0h+var_250], 8007000Eh
0x14010b897  mov     [rsp+2A0h+var_238], rax
0x14010b89c  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\common\\rdadalclie"...
0x14010b8a3  mov     [rsp+2A0h+var_240], rax
0x14010b8a8  lea     rax, aErrorCondition; "Error condition failed"
0x14010b8af  jmp     loc_14010B9C1
0x14010b8b4  mov     r8, rbx; unsigned __int16 *
0x14010b8b7  lea     rcx, ?g_WAMHandler@@3VCWAMTokenHandler@@A; this
0x14010b8be  mov     rdx, rdi; unsigned __int16 *
0x14010b8c1  call    ?ClearCachedWebAccounts@CWAMTokenHandler@@QEAAJPEAG0@Z; CWAMTokenHandler::ClearCachedWebAccounts(ushort *,ushort *)
0x14010b8c6  mov     edx, eax
0x14010b8c8  test    eax, eax
0x14010b8ca  jns     short loc_14010B8FA
0x14010b8cc  mov     ecx, cs:dword_140150118
0x14010b8d2  cmp     ecx, 2
0x14010b8d5  jbe     loc_14010BA07
0x14010b8db  mov     [rsp+2A0h+var_250], edx
0x14010b8df  lea     rax, aClearcachedweb_0; "ClearCachedWebAccounts failed"
0x14010b8e6  lea     rdx, word_14014464E
0x14010b8ed  mov     [rsp+2A0h+var_24C], 0CFh
0x14010b8f5  jmp     loc_14010B99D
0x14010b8fa  mov     r9, cs:?g_pszRefreshTokenRootKey@@3PEBGEB; ushort const * const g_pszRefreshTokenRootKey
0x14010b901  lea     r8, aSS_0; "%s\\%s"
0x14010b908  mov     edx, 104h; unsigned __int64
0x14010b90d  mov     [rsp+2A0h+var_280], rdi
0x14010b912  lea     rcx, [rbp+1A0h+SubKey]; unsigned __int16 *
0x14010b916  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14010b91b  mov     edx, eax
0x14010b91d  test    eax, eax
0x14010b91f  jns     short loc_14010B94C
0x14010b921  mov     ecx, cs:dword_140150118
0x14010b927  cmp     ecx, 2
0x14010b92a  jbe     loc_14010BA07
0x14010b930  mov     [rsp+2A0h+var_250], edx
0x14010b934  lea     rax, aStringcchprint_0; "StringCchPrintf failed"
0x14010b93b  lea     rdx, byte_140144601
0x14010b942  mov     [rsp+2A0h+var_24C], 0D5h
0x14010b94a  jmp     short loc_14010B99D
0x14010b94c  lea     rdx, [rbp+1A0h+SubKey]; lpSubKey
0x14010b950  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14010b957  call    cs:__imp_RegDeleteTreeW
0x14010b95d  mov     ecx, eax
0x14010b95f  test    eax, eax
0x14010b961  jle     short loc_14010B96C
0x14010b963  movzx   ecx, ax
0x14010b966  or      ecx, 80070000h
0x14010b96c  test    ecx, ecx
0x14010b96e  jns     loc_14010BA07
0x14010b974  mov     eax, cs:dword_140150118
0x14010b97a  cmp     eax, 2
0x14010b97d  jbe     loc_14010BA07
0x14010b983  lea     rax, aFailedToDelete; "Failed to delete Web accounts storage f"...
0x14010b98a  mov     [rsp+2A0h+var_24C], 0D9h
0x14010b992  mov     [rsp+2A0h+var_250], ecx
0x14010b996  lea     rdx, byte_14014469B
0x14010b99d  mov     [rsp+2A0h+var_230], rax
0x14010b9a2  lea     rax, aAuthDllclearca; "Auth_DllClearCachedWebAccounts"
0x14010b9a9  mov     [rsp+2A0h+var_238], rax
0x14010b9ae  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\common\\rdadalclie"...
0x14010b9b5  mov     [rsp+2A0h+var_240], rax
0x14010b9ba  lea     rax, aErrorHresultFa; "Error HResult failed"
0x14010b9c1  mov     [rsp+2A0h+var_248], rax
0x14010b9c6  lea     rax, [rsp+2A0h+var_230]
0x14010b9cb  mov     [rsp+2A0h+var_258], rax
0x14010b9d0  lea     rax, [rsp+2A0h+var_238]
0x14010b9d5  mov     [rsp+2A0h+var_260], rax
0x14010b9da  lea     rax, [rsp+2A0h+var_24C]
0x14010b9df  mov     [rsp+2A0h+var_268], rax
0x14010b9e4  lea     rax, [rsp+2A0h+var_240]
0x14010b9e9  mov     [rsp+2A0h+var_270], rax
0x14010b9ee  lea     rax, [rsp+2A0h+var_250]
0x14010b9f3  mov     [rsp+2A0h+var_278], rax
0x14010b9f8  lea     rax, [rsp+2A0h+var_248]
0x14010b9fd  mov     [rsp+2A0h+var_280], rax
0x14010ba02  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14010ba07  mov     rcx, rdi; bstrString
0x14010ba0a  call    cs:__imp_SysFreeString
0x14010ba10  test    rbx, rbx
0x14010ba13  jz      short loc_14010BA1E
0x14010ba15  mov     rcx, rbx; bstrString
0x14010ba18  call    cs:__imp_SysFreeString
0x14010ba1e  mov     rcx, [rbp+1A0h+var_10]
0x14010ba25  xor     rcx, rsp; StackCookie
0x14010ba28  call    __security_check_cookie
0x14010ba2d  lea     r11, [rsp+2A0h+var_s0]
0x14010ba35  mov     rbx, [r11+10h]
0x14010ba39  mov     rdi, [r11+18h]
0x14010ba3d  mov     rsp, r11
0x14010ba40  pop     rbp
0x14010ba41  retn
```
