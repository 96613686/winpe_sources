# Auth_DllClearCachedWebAccounts

- ea: `0x14010d8c8`
- end: `0x14010dbb2`
- name: `Auth_DllClearCachedWebAccounts`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400b6d84`

## callees

- `0x1400026b0`
- `0x140004703`
- `0x140008a78`
- `0x14010d8c8`
- `0x14010f4cc`
- `0x140113390`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14010d90b`
- `OLEAUT32!__imp_SysAllocString` at `0x14010d9c0`
- `OLEAUT32!__imp_SysAllocString` at `0x14010d90b`
- `OLEAUT32!__imp_SysAllocString` at `0x14010d9c0`
- `OLEAUT32!__imp_SysFreeString` at `0x14010db7a`
- `OLEAUT32!__imp_SysFreeString` at `0x14010db88`
- `OLEAUT32!__imp_SysFreeString` at `0x14010db7a`
- `OLEAUT32!__imp_SysFreeString` at `0x14010db88`
- `ADVAPI32!RegDeleteTreeW` at `0x14010dac7`
- `ADVAPI32!RegDeleteTreeW` at `0x14010dac7`

## string_xrefs

- `0x14010d95b`: `clientcore\termsrv\common\rdadalclient\lib\tokenhandler.aadj.cpp`
- `0x14010da0c`: `clientcore\termsrv\common\rdadalclient\lib\tokenhandler.aadj.cpp`
- `0x14010db1e`: `clientcore\termsrv\common\rdadalclient\lib\tokenhandler.aadj.cpp`
- `0x14010da4f`: `ClearCachedWebAccounts failed`
- `0x14010d947`: `Auth_DllClearCachedWebAccounts`
- `0x14010d9f8`: `Auth_DllClearCachedWebAccounts`
- `0x14010db12`: `Auth_DllClearCachedWebAccounts`
- `0x14010daf3`: `Failed to delete Web accounts storage from registry`

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
    if ( (unsigned int)dword_140152118 > 2 )
    {
      v15 = 187;
      v17 = "SysAllocString returned NULL";
      v16 = -2147024882;
      v18 = "Auth_DllClearCachedWebAccounts";
      v19 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\tokenhandler.aadj.cpp";
      v20[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v0,
        (unsigned int)word_1401468BA,
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
        if ( v8 >= 0 || (unsigned int)dword_140152118 <= 2 )
          goto LABEL_20;
        v12 = "Failed to delete Web accounts storage from registry";
        v16 = 217;
        v15 = v8;
        v9 = byte_140146739;
      }
      else
      {
        v8 = dword_140152118;
        if ( (unsigned int)dword_140152118 <= 2 )
          goto LABEL_20;
        v15 = v13;
        v12 = "StringCchPrintf failed";
        v9 = (char *)&word_140146786;
        v16 = 213;
      }
    }
    else
    {
      v8 = dword_140152118;
      if ( (unsigned int)dword_140152118 <= 2 )
        goto LABEL_20;
      v15 = v11;
      v12 = "ClearCachedWebAccounts failed";
      v9 = byte_14014686D;
      v16 = 207;
    }
    v20[0] = v12;
    v19 = "Auth_DllClearCachedWebAccounts";
    v18 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\tokenhandler.aadj.cpp";
    v10 = "Error HResult failed";
  }
  else
  {
    v8 = dword_140152118;
    if ( (unsigned int)dword_140152118 <= 2 )
      goto LABEL_20;
    v16 = 197;
    v20[0] = "SysAllocString returned NULL";
    v9 = &byte_140146907;
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
0x14010d8c8  mov     [rsp-8+arg_0], rbx
0x14010d8cd  mov     [rsp-8+arg_8], rdi
0x14010d8d2  push    rbp
0x14010d8d3  lea     rbp, [rsp-1A0h]
0x14010d8db  sub     rsp, 2A0h
0x14010d8e2  mov     rax, cs:__security_cookie
0x14010d8e9  xor     rax, rsp
0x14010d8ec  mov     [rbp+1A0h+var_10], rax
0x14010d8f3  xor     edx, edx; Val
0x14010d8f5  lea     rcx, [rbp+1A0h+SubKey]; void *
0x14010d8f9  mov     r8d, 208h; Size
0x14010d8ff  call    memset_0
0x14010d904  lea     rcx, a5177bc73Fd994c; "5177bc73-fd99-4c77-a90c-76844c9b6999"
0x14010d90b  call    cs:__imp_SysAllocString
0x14010d911  mov     rdi, rax
0x14010d914  test    rax, rax
0x14010d917  jnz     loc_14010D9B9
0x14010d91d  mov     eax, cs:dword_140152118
0x14010d923  cmp     eax, 2
0x14010d926  jbe     loc_14010DB8E
0x14010d92c  lea     rax, aSysallocstring; "SysAllocString returned NULL"
0x14010d933  mov     [rsp+2A0h+var_250], 0BBh
0x14010d93b  mov     [rsp+2A0h+var_248], rax
0x14010d940  lea     rdx, word_1401468BA
0x14010d947  lea     rax, aAuthDllclearca; "Auth_DllClearCachedWebAccounts"
0x14010d94e  mov     [rsp+2A0h+var_24C], 8007000Eh
0x14010d956  mov     [rsp+2A0h+var_240], rax
0x14010d95b  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\common\\rdadalclie"...
0x14010d962  mov     [rsp+2A0h+var_238], rax
0x14010d967  lea     rax, aErrorCondition; "Error condition failed"
0x14010d96e  mov     [rsp+2A0h+var_230], rax
0x14010d973  lea     rax, [rsp+2A0h+var_248]
0x14010d978  mov     [rsp+2A0h+var_258], rax
0x14010d97d  lea     rax, [rsp+2A0h+var_240]
0x14010d982  mov     [rsp+2A0h+var_260], rax
0x14010d987  lea     rax, [rsp+2A0h+var_250]
0x14010d98c  mov     [rsp+2A0h+var_268], rax
0x14010d991  lea     rax, [rsp+2A0h+var_238]
0x14010d996  mov     [rsp+2A0h+var_270], rax
0x14010d99b  lea     rax, [rsp+2A0h+var_24C]
0x14010d9a0  mov     [rsp+2A0h+var_278], rax
0x14010d9a5  lea     rax, [rsp+2A0h+var_230]
0x14010d9aa  mov     [rsp+2A0h+var_280], rax
0x14010d9af  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14010d9b4  jmp     loc_14010DB8E
0x14010d9b9  lea     rcx, aOrganizations; "organizations"
0x14010d9c0  call    cs:__imp_SysAllocString
0x14010d9c6  mov     rbx, rax
0x14010d9c9  test    rax, rax
0x14010d9cc  jnz     short loc_14010DA24
0x14010d9ce  mov     ecx, cs:dword_140152118
0x14010d9d4  cmp     ecx, 2
0x14010d9d7  jbe     loc_14010DB77
0x14010d9dd  lea     rax, aSysallocstring; "SysAllocString returned NULL"
0x14010d9e4  mov     [rsp+2A0h+var_24C], 0C5h
0x14010d9ec  mov     [rsp+2A0h+var_230], rax
0x14010d9f1  lea     rdx, byte_140146907
0x14010d9f8  lea     rax, aAuthDllclearca; "Auth_DllClearCachedWebAccounts"
0x14010d9ff  mov     [rsp+2A0h+var_250], 8007000Eh
0x14010da07  mov     [rsp+2A0h+var_238], rax
0x14010da0c  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\common\\rdadalclie"...
0x14010da13  mov     [rsp+2A0h+var_240], rax
0x14010da18  lea     rax, aErrorCondition; "Error condition failed"
0x14010da1f  jmp     loc_14010DB31
0x14010da24  mov     r8, rbx; unsigned __int16 *
0x14010da27  lea     rcx, ?g_WAMHandler@@3VCWAMTokenHandler@@A; this
0x14010da2e  mov     rdx, rdi; unsigned __int16 *
0x14010da31  call    ?ClearCachedWebAccounts@CWAMTokenHandler@@QEAAJPEAG0@Z; CWAMTokenHandler::ClearCachedWebAccounts(ushort *,ushort *)
0x14010da36  mov     edx, eax
0x14010da38  test    eax, eax
0x14010da3a  jns     short loc_14010DA6A
0x14010da3c  mov     ecx, cs:dword_140152118
0x14010da42  cmp     ecx, 2
0x14010da45  jbe     loc_14010DB77
0x14010da4b  mov     [rsp+2A0h+var_250], edx
0x14010da4f  lea     rax, aClearcachedweb_0; "ClearCachedWebAccounts failed"
0x14010da56  lea     rdx, byte_14014686D
0x14010da5d  mov     [rsp+2A0h+var_24C], 0CFh
0x14010da65  jmp     loc_14010DB0D
0x14010da6a  mov     r9, cs:?g_pszRefreshTokenRootKey@@3PEBGEB; ushort const * const g_pszRefreshTokenRootKey
0x14010da71  lea     r8, aSS_0; "%s\\%s"
0x14010da78  mov     edx, 104h; unsigned __int64
0x14010da7d  mov     [rsp+2A0h+var_280], rdi
0x14010da82  lea     rcx, [rbp+1A0h+SubKey]; unsigned __int16 *
0x14010da86  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14010da8b  mov     edx, eax
0x14010da8d  test    eax, eax
0x14010da8f  jns     short loc_14010DABC
0x14010da91  mov     ecx, cs:dword_140152118
0x14010da97  cmp     ecx, 2
0x14010da9a  jbe     loc_14010DB77
0x14010daa0  mov     [rsp+2A0h+var_250], edx
0x14010daa4  lea     rax, aStringcchprint_0; "StringCchPrintf failed"
0x14010daab  lea     rdx, word_140146786
0x14010dab2  mov     [rsp+2A0h+var_24C], 0D5h
0x14010daba  jmp     short loc_14010DB0D
0x14010dabc  lea     rdx, [rbp+1A0h+SubKey]; lpSubKey
0x14010dac0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14010dac7  call    cs:__imp_RegDeleteTreeW
0x14010dacd  mov     ecx, eax
0x14010dacf  test    eax, eax
0x14010dad1  jle     short loc_14010DADC
0x14010dad3  movzx   ecx, ax
0x14010dad6  or      ecx, 80070000h
0x14010dadc  test    ecx, ecx
0x14010dade  jns     loc_14010DB77
0x14010dae4  mov     eax, cs:dword_140152118
0x14010daea  cmp     eax, 2
0x14010daed  jbe     loc_14010DB77
0x14010daf3  lea     rax, aFailedToDelete; "Failed to delete Web accounts storage f"...
0x14010dafa  mov     [rsp+2A0h+var_24C], 0D9h
0x14010db02  mov     [rsp+2A0h+var_250], ecx
0x14010db06  lea     rdx, byte_140146739
0x14010db0d  mov     [rsp+2A0h+var_230], rax
0x14010db12  lea     rax, aAuthDllclearca; "Auth_DllClearCachedWebAccounts"
0x14010db19  mov     [rsp+2A0h+var_238], rax
0x14010db1e  lea     rax, aClientcoreTerm_3; "clientcore\\termsrv\\common\\rdadalclie"...
0x14010db25  mov     [rsp+2A0h+var_240], rax
0x14010db2a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x14010db31  mov     [rsp+2A0h+var_248], rax
0x14010db36  lea     rax, [rsp+2A0h+var_230]
0x14010db3b  mov     [rsp+2A0h+var_258], rax
0x14010db40  lea     rax, [rsp+2A0h+var_238]
0x14010db45  mov     [rsp+2A0h+var_260], rax
0x14010db4a  lea     rax, [rsp+2A0h+var_24C]
0x14010db4f  mov     [rsp+2A0h+var_268], rax
0x14010db54  lea     rax, [rsp+2A0h+var_240]
0x14010db59  mov     [rsp+2A0h+var_270], rax
0x14010db5e  lea     rax, [rsp+2A0h+var_250]
0x14010db63  mov     [rsp+2A0h+var_278], rax
0x14010db68  lea     rax, [rsp+2A0h+var_248]
0x14010db6d  mov     [rsp+2A0h+var_280], rax
0x14010db72  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x14010db77  mov     rcx, rdi; bstrString
0x14010db7a  call    cs:__imp_SysFreeString
0x14010db80  test    rbx, rbx
0x14010db83  jz      short loc_14010DB8E
0x14010db85  mov     rcx, rbx; bstrString
0x14010db88  call    cs:__imp_SysFreeString
0x14010db8e  mov     rcx, [rbp+1A0h+var_10]
0x14010db95  xor     rcx, rsp; StackCookie
0x14010db98  call    __security_check_cookie
0x14010db9d  lea     r11, [rsp+2A0h+var_s0]
0x14010dba5  mov     rbx, [r11+10h]
0x14010dba9  mov     rdi, [r11+18h]
0x14010dbad  mov     rsp, r11
0x14010dbb0  pop     rbp
0x14010dbb1  retn
```
