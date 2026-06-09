# Com::Catalog::Win32Registry::OpenClsidKey(Com::Catalog::Win32Registry::WhichHive,_GUID const &,ulong,HKEY__ * *)

- ea: `0x18008f978`
- end: `0x18008fbce`
- name: `?OpenClsidKey@Win32Registry@Catalog@Com@@YAJW4WhichHive@123@AEBU_GUID@@KPEAPEAUHKEY__@@@Z`
- size: `598`
- prototype: `int __high(enum Com::Catalog::Win32Registry::WhichHive, const struct _GUID *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008fe60`

## callees

- `0x180004f70`
- `0x18000e074`
- `0x18000ff24`
- `0x18001eeb8`
- `0x18002107c`
- `0x18002109c`
- `0x18008f978`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008fa10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008fa97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008fb0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008fa10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008fa97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008fb0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fa5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008faca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fb2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fb44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fa5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008faca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fb2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008fb44`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008fae8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008fae8`

## string_xrefs

- `0x18008fb76`: `onecore\internal\com\inc\combase\ComGuid.hpp`
- `0x18008fa24`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008fa42`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008fab0`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008fb96`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008fbb9`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008fa90`: `CLSID`

## pseudocode

```c
__int64 __fastcall Com::Catalog::Win32Registry::OpenClsidKey(unsigned int a1, const GUID *a2, __int64 a3, HKEY *a4)
{
  const WCHAR *v6; // rdx
  unsigned __int64 v7; // rcx
  unsigned int v8; // ecx
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int v13; // eax
  __int64 v14; // rdx
  const char *v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // eax
  int phkResult; // [rsp+20h] [rbp-39h]
  unsigned int phkResulta; // [rsp+20h] [rbp-39h]
  int phkResultb; // [rsp+20h] [rbp-39h]
  unsigned int phkResultc; // [rsp+20h] [rbp-39h]
  HKEY hKey; // [rsp+30h] [rbp-29h] BYREF
  HKEY v23; // [rsp+38h] [rbp-21h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a4 = 0;
  hKey = 0;
  if ( a1 < 2 )
  {
    v6 = L"Software\\Classes";
    if ( !a1 )
    {
      v7 = -2147483646;
      goto LABEL_11;
    }
    v8 = a1 - 1;
    if ( !v8 )
    {
      v7 = -2147483647;
      goto LABEL_11;
    }
    if ( v8 != 1 )
    {
      v16 = wil::verify_hresult(2147549183LL);
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
        (const char *)v16,
        phkResult);
    }
  }
  else
  {
    if ( a1 != 2 )
    {
      v17 = wil::verify_hresult(2147549183LL);
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
        (const char *)v17,
        phkResult);
    }
    v6 = &String1;
  }
  v7 = 0xFFFFFFFF80000000uLL;
LABEL_11:
  v9 = RegOpenKeyExW((HKEY)v7, v6, 0, 0x20019u, &hKey);
  if ( v9 )
  {
    v10 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x9F,
            (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
            (const char *)v9,
            phkResulta);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
        (const char *)(unsigned int)v10,
        phkResultb);
LABEL_14:
      if ( hKey )
        RegCloseKey(hKey);
      return v11;
    }
  }
  v23 = 0;
  v13 = RegOpenKeyExW(hKey, L"CLSID", 0, 0x20019u, &v23);
  if ( v13 )
  {
    v14 = 171;
    goto LABEL_19;
  }
  if ( StringFromGUID2(a2, sz, 39) != 39 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\internal\\com\\inc\\combase\\ComGuid.hpp",
      v15);
  v13 = RegOpenKeyExW(v23, sz, 0, 0x20019u, a4);
  if ( v13 )
  {
    v14 = 173;
LABEL_19:
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\private\\com\\inc\\combase\\ComRegistryCatalogFunctions.hpp",
            (const char *)v13,
            phkResultc);
    if ( v23 )
      RegCloseKey(v23);
    goto LABEL_14;
  }
  if ( v23 )
    RegCloseKey(v23);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18008f978  mov     [rsp-8+arg_0], rbx
0x18008f97d  push    rbp
0x18008f97e  push    rsi
0x18008f97f  push    rdi
0x18008f980  lea     rbp, [rsp-47h]
0x18008f985  sub     rsp, 0A0h
0x18008f98c  mov     rax, cs:__security_cookie
0x18008f993  xor     rax, rsp
0x18008f996  mov     [rbp+57h+var_20], rax
0x18008f99a  mov     qword ptr [r9], 0
0x18008f9a1  mov     rsi, rdx
0x18008f9a4  mov     [rbp+57h+hKey], 0
0x18008f9ac  mov     edx, ecx
0x18008f9ae  mov     rdi, r9
0x18008f9b1  test    ecx, ecx
0x18008f9b3  jz      short loc_18008F9D3
0x18008f9b5  sub     edx, 1
0x18008f9b8  jz      short loc_18008F9D3
0x18008f9ba  cmp     edx, 1
0x18008f9bd  jnz     loc_18008FBAB
0x18008f9c3  lea     rdx, String1
0x18008f9ca  mov     rcx, 0FFFFFFFF80000000h
0x18008f9d1  jmp     short loc_18008F9FE
0x18008f9d3  lea     rdx, aSoftwareClasse_1; "Software\\Classes"
0x18008f9da  test    ecx, ecx
0x18008f9dc  jz      short loc_18008F9F7
0x18008f9de  sub     ecx, 1
0x18008f9e1  jz      short loc_18008F9EE
0x18008f9e3  cmp     ecx, 1
0x18008f9e6  jnz     loc_18008FB88
0x18008f9ec  jmp     short loc_18008F9CA
0x18008f9ee  mov     rcx, 0FFFFFFFF80000001h
0x18008f9f5  jmp     short loc_18008F9FE
0x18008f9f7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008f9fe  lea     rax, [rbp+57h+hKey]
0x18008fa02  mov     r9d, 20019h; samDesired
0x18008fa08  xor     r8d, r8d; ulOptions
0x18008fa0b  mov     qword ptr [rsp+0B0h+phkResult], rax; int
0x18008fa10  call    cs:__imp_RegOpenKeyExW
0x18008fa17  nop     dword ptr [rax+rax+00h]
0x18008fa1c  test    eax, eax
0x18008fa1e  jz      short loc_18008FA72
0x18008fa20  mov     rcx, [rbp+5Fh]; this
0x18008fa24  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008fa2b  mov     r9d, eax; char *
0x18008fa2e  mov     edx, 9Fh; void *
0x18008fa33  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008fa38  mov     ebx, eax
0x18008fa3a  test    eax, eax
0x18008fa3c  jns     short loc_18008FA72
0x18008fa3e  mov     rcx, [rbp+5Fh]; this
0x18008fa42  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008fa49  mov     r9d, eax; char *
0x18008fa4c  mov     edx, 0A8h; void *
0x18008fa51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008fa56  mov     rcx, [rbp+57h+hKey]; hKey
0x18008fa5a  test    rcx, rcx
0x18008fa5d  jz      short loc_18008FA6B
0x18008fa5f  call    cs:__imp_RegCloseKey
0x18008fa66  nop     dword ptr [rax+rax+00h]
0x18008fa6b  mov     eax, ebx
0x18008fa6d  jmp     loc_18008FB52
0x18008fa72  mov     rcx, [rbp+57h+hKey]; hKey
0x18008fa76  lea     rax, [rbp+57h+var_78]
0x18008fa7a  mov     r9d, 20019h; samDesired
0x18008fa80  mov     qword ptr [rsp+0B0h+phkResult], rax; unsigned int
0x18008fa85  xor     r8d, r8d; ulOptions
0x18008fa88  mov     [rbp+57h+var_78], 0
0x18008fa90  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; "CLSID"
0x18008fa97  call    cs:__imp_RegOpenKeyExW
0x18008fa9e  nop     dword ptr [rax+rax+00h]
0x18008faa3  test    eax, eax
0x18008faa5  jz      short loc_18008FADB
0x18008faa7  mov     edx, 0ABh; void *
0x18008faac  mov     rcx, [rbp+5Fh]; this
0x18008fab0  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008fab7  mov     r9d, eax; char *
0x18008faba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008fabf  mov     rcx, [rbp+57h+var_78]; hKey
0x18008fac3  mov     ebx, eax
0x18008fac5  test    rcx, rcx
0x18008fac8  jz      short loc_18008FA56
0x18008faca  call    cs:__imp_RegCloseKey
0x18008fad1  nop     dword ptr [rax+rax+00h]
0x18008fad6  jmp     loc_18008FA56
0x18008fadb  mov     r8d, 27h ; '''; cchMax
0x18008fae1  lea     rdx, [rbp+57h+sz]; lpsz
0x18008fae5  mov     rcx, rsi; rguid
0x18008fae8  call    cs:__imp_StringFromGUID2
0x18008faef  nop     dword ptr [rax+rax+00h]
0x18008faf4  cmp     eax, 27h ; '''
0x18008faf7  jnz     short loc_18008FB72
0x18008faf9  mov     rcx, [rbp+57h+var_78]; hKey
0x18008fafd  lea     rdx, [rbp+57h+sz]; lpSubKey
0x18008fb01  mov     r9d, 20019h; samDesired
0x18008fb07  mov     qword ptr [rsp+0B0h+phkResult], rdi; phkResult
0x18008fb0c  xor     r8d, r8d; ulOptions
0x18008fb0f  call    cs:__imp_RegOpenKeyExW
0x18008fb16  nop     dword ptr [rax+rax+00h]
0x18008fb1b  test    eax, eax
0x18008fb1d  jz      short loc_18008FB26
0x18008fb1f  mov     edx, 0ADh
0x18008fb24  jmp     short loc_18008FAAC
0x18008fb26  mov     rcx, [rbp+57h+var_78]; hKey
0x18008fb2a  test    rcx, rcx
0x18008fb2d  jz      short loc_18008FB3B
0x18008fb2f  call    cs:__imp_RegCloseKey
0x18008fb36  nop     dword ptr [rax+rax+00h]
0x18008fb3b  mov     rcx, [rbp+57h+hKey]; hKey
0x18008fb3f  test    rcx, rcx
0x18008fb42  jz      short loc_18008FB50
0x18008fb44  call    cs:__imp_RegCloseKey
0x18008fb4b  nop     dword ptr [rax+rax+00h]
0x18008fb50  xor     eax, eax
0x18008fb52  mov     rcx, [rbp+57h+var_20]
0x18008fb56  xor     rcx, rsp; StackCookie
0x18008fb59  call    __security_check_cookie
0x18008fb5e  mov     rbx, [rsp+0B0h+arg_0]
0x18008fb66  add     rsp, 0A0h
0x18008fb6d  pop     rdi
0x18008fb6e  pop     rsi
0x18008fb6f  pop     rbp
0x18008fb70  retn
0x18008fb72  mov     rcx, [rbp+5Fh]; this
0x18008fb76  lea     r8, aOnecoreInterna_5; "onecore\\internal\\com\\inc\\combase\\C"...
0x18008fb7d  mov     edx, 19h; void *
0x18008fb82  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18008fb88  mov     ecx, 8000FFFFh
0x18008fb8d  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18008fb92  mov     rcx, [rbp+5Fh]; this
0x18008fb96  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008fb9d  mov     r9d, eax; char *
0x18008fba0  mov     edx, 85h; void *
0x18008fba5  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008fbab  mov     ecx, 8000FFFFh
0x18008fbb0  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18008fbb5  mov     rcx, [rbp+5Fh]; this
0x18008fbb9  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008fbc0  mov     r9d, eax; char *
0x18008fbc3  mov     edx, 96h; void *
0x18008fbc8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
