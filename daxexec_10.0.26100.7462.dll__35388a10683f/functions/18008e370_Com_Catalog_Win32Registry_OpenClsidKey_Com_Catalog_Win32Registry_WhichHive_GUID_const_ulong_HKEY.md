# Com::Catalog::Win32Registry::OpenClsidKey(Com::Catalog::Win32Registry::WhichHive,_GUID const &,ulong,HKEY__ * *)

- ea: `0x18008e370`
- end: `0x18008e5ba`
- name: `?OpenClsidKey@Win32Registry@Catalog@Com@@YAJW4WhichHive@123@AEBU_GUID@@KPEAPEAUHKEY__@@@Z`
- size: `586`
- prototype: `int __high(enum Com::Catalog::Win32Registry::WhichHive, const struct _GUID *, unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008e820`

## callees

- `0x1800053a0`
- `0x18000c37c`
- `0x18000e234`
- `0x18001e32c`
- `0x18002029c`
- `0x1800202bc`
- `0x18008e370`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e451`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e4b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e51b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e530`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e451`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e4b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e51b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008e530`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e486`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e4fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e402`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e486`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008e4fb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008e4d4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18008e4d4`

## string_xrefs

- `0x18008e562`: `onecore\internal\com\inc\combase\ComGuid.hpp`
- `0x18008e471`: `CLSID`
- `0x18008e416`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008e434`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008e49f`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008e582`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`
- `0x18008e5a5`: `onecore\private\com\inc\combase\ComRegistryCatalogFunctions.hpp`

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
0x18008e370  mov     [rsp-8+arg_0], rbx
0x18008e375  push    rbp
0x18008e376  push    rsi
0x18008e377  push    rdi
0x18008e378  lea     rbp, [rsp-47h]
0x18008e37d  sub     rsp, 0A0h
0x18008e384  mov     rax, cs:__security_cookie
0x18008e38b  xor     rax, rsp
0x18008e38e  mov     [rbp+57h+var_20], rax
0x18008e392  and     qword ptr [r9], 0
0x18008e396  mov     rsi, rdx
0x18008e399  and     [rbp+57h+hKey], 0
0x18008e39e  mov     rdi, r9
0x18008e3a1  mov     edx, ecx
0x18008e3a3  test    ecx, ecx
0x18008e3a5  jz      short loc_18008E3C5
0x18008e3a7  sub     edx, 1
0x18008e3aa  jz      short loc_18008E3C5
0x18008e3ac  cmp     edx, 1
0x18008e3af  jnz     loc_18008E597
0x18008e3b5  lea     rdx, String1
0x18008e3bc  mov     rcx, 0FFFFFFFF80000000h
0x18008e3c3  jmp     short loc_18008E3F0
0x18008e3c5  lea     rdx, aSoftwareClasse_1; "Software\\Classes"
0x18008e3cc  test    ecx, ecx
0x18008e3ce  jz      short loc_18008E3E9
0x18008e3d0  sub     ecx, 1
0x18008e3d3  jz      short loc_18008E3E0
0x18008e3d5  cmp     ecx, 1
0x18008e3d8  jnz     loc_18008E574
0x18008e3de  jmp     short loc_18008E3BC
0x18008e3e0  mov     rcx, 0FFFFFFFF80000001h
0x18008e3e7  jmp     short loc_18008E3F0
0x18008e3e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008e3f0  lea     rax, [rbp+57h+hKey]
0x18008e3f4  mov     r9d, 20019h; samDesired
0x18008e3fa  xor     r8d, r8d; ulOptions
0x18008e3fd  mov     qword ptr [rsp+0B0h+phkResult], rax; int
0x18008e402  call    cs:__imp_RegOpenKeyExW
0x18008e409  nop     dword ptr [rax+rax+00h]
0x18008e40e  test    eax, eax
0x18008e410  jz      short loc_18008E464
0x18008e412  mov     rcx, [rbp+5Fh]; this
0x18008e416  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008e41d  mov     r9d, eax; char *
0x18008e420  mov     edx, 9Fh; void *
0x18008e425  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008e42a  mov     ebx, eax
0x18008e42c  test    eax, eax
0x18008e42e  jns     short loc_18008E464
0x18008e430  mov     rcx, [rbp+5Fh]; this
0x18008e434  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008e43b  mov     r9d, eax; char *
0x18008e43e  mov     edx, 0A8h; void *
0x18008e443  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e448  mov     rcx, [rbp+57h+hKey]; hKey
0x18008e44c  test    rcx, rcx
0x18008e44f  jz      short loc_18008E45D
0x18008e451  call    cs:__imp_RegCloseKey
0x18008e458  nop     dword ptr [rax+rax+00h]
0x18008e45d  mov     eax, ebx
0x18008e45f  jmp     loc_18008E53E
0x18008e464  mov     rcx, [rbp+57h+hKey]; hKey
0x18008e468  lea     rax, [rbp+57h+var_78]
0x18008e46c  and     [rbp+57h+var_78], 0
0x18008e471  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; "CLSID"
0x18008e478  mov     r9d, 20019h; samDesired
0x18008e47e  mov     qword ptr [rsp+0B0h+phkResult], rax; unsigned int
0x18008e483  xor     r8d, r8d; ulOptions
0x18008e486  call    cs:__imp_RegOpenKeyExW
0x18008e48d  nop     dword ptr [rax+rax+00h]
0x18008e492  test    eax, eax
0x18008e494  jz      short loc_18008E4C7
0x18008e496  mov     edx, 0ABh; void *
0x18008e49b  mov     rcx, [rbp+5Fh]; this
0x18008e49f  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008e4a6  mov     r9d, eax; char *
0x18008e4a9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008e4ae  mov     rcx, [rbp+57h+var_78]; hKey
0x18008e4b2  mov     ebx, eax
0x18008e4b4  test    rcx, rcx
0x18008e4b7  jz      short loc_18008E448
0x18008e4b9  call    cs:__imp_RegCloseKey
0x18008e4c0  nop     dword ptr [rax+rax+00h]
0x18008e4c5  jmp     short loc_18008E448
0x18008e4c7  mov     r8d, 27h ; '''; cchMax
0x18008e4cd  lea     rdx, [rbp+57h+sz]; lpsz
0x18008e4d1  mov     rcx, rsi; rguid
0x18008e4d4  call    cs:__imp_StringFromGUID2
0x18008e4db  nop     dword ptr [rax+rax+00h]
0x18008e4e0  cmp     eax, 27h ; '''
0x18008e4e3  jnz     short loc_18008E55E
0x18008e4e5  mov     rcx, [rbp+57h+var_78]; hKey
0x18008e4e9  lea     rdx, [rbp+57h+sz]; lpSubKey
0x18008e4ed  mov     r9d, 20019h; samDesired
0x18008e4f3  mov     qword ptr [rsp+0B0h+phkResult], rdi; phkResult
0x18008e4f8  xor     r8d, r8d; ulOptions
0x18008e4fb  call    cs:__imp_RegOpenKeyExW
0x18008e502  nop     dword ptr [rax+rax+00h]
0x18008e507  test    eax, eax
0x18008e509  jz      short loc_18008E512
0x18008e50b  mov     edx, 0ADh
0x18008e510  jmp     short loc_18008E49B
0x18008e512  mov     rcx, [rbp+57h+var_78]; hKey
0x18008e516  test    rcx, rcx
0x18008e519  jz      short loc_18008E527
0x18008e51b  call    cs:__imp_RegCloseKey
0x18008e522  nop     dword ptr [rax+rax+00h]
0x18008e527  mov     rcx, [rbp+57h+hKey]; hKey
0x18008e52b  test    rcx, rcx
0x18008e52e  jz      short loc_18008E53C
0x18008e530  call    cs:__imp_RegCloseKey
0x18008e537  nop     dword ptr [rax+rax+00h]
0x18008e53c  xor     eax, eax
0x18008e53e  mov     rcx, [rbp+57h+var_20]
0x18008e542  xor     rcx, rsp; StackCookie
0x18008e545  call    __security_check_cookie
0x18008e54a  mov     rbx, [rsp+0B0h+arg_0]
0x18008e552  add     rsp, 0A0h
0x18008e559  pop     rdi
0x18008e55a  pop     rsi
0x18008e55b  pop     rbp
0x18008e55c  retn
0x18008e55e  mov     rcx, [rbp+5Fh]; this
0x18008e562  lea     r8, aOnecoreInterna_5; "onecore\\internal\\com\\inc\\combase\\C"...
0x18008e569  mov     edx, 19h; void *
0x18008e56e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18008e574  mov     ecx, 8000FFFFh
0x18008e579  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18008e57e  mov     rcx, [rbp+5Fh]; this
0x18008e582  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008e589  mov     r9d, eax; char *
0x18008e58c  mov     edx, 85h; void *
0x18008e591  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008e597  mov     ecx, 8000FFFFh
0x18008e59c  call    ?verify_hresult@wil@@YAJUhresult@winrt@@@Z; wil::verify_hresult(winrt::hresult)
0x18008e5a1  mov     rcx, [rbp+5Fh]; this
0x18008e5a5  lea     r8, aOnecorePrivate_6; "onecore\\private\\com\\inc\\combase\\Co"...
0x18008e5ac  mov     r9d, eax; char *
0x18008e5af  mov     edx, 96h; void *
0x18008e5b4  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
