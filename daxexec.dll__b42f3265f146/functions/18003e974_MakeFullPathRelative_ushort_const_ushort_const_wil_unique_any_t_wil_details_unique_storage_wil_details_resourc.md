# MakeFullPathRelative(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18003e974`
- end: `0x18003eb3c`
- name: `?MakeFullPathRelative@@YA_NPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18003dfe4`

## callees

- `0x180004f70`
- `0x180012fb8`
- `0x180013510`
- `0x180014edc`
- `0x18002b6a8`
- `0x180035e2c`
- `0x18003e974`
- `0x18005bdc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003eac0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003eac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eaa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eaa1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e9e3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e9e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eadd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eab2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003eadd`

## string_xrefs

- `0x18003eb24`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall MakeFullPathRelative(LPCWSTR lpFileName, const WCHAR *a2, LPVOID *a3)
{
  const WCHAR *v5; // r8
  const WCHAR *v6; // rcx
  __int64 v8; // rcx
  __int64 v9; // r8
  LPCWCH *v10; // rax
  __int128 *v11; // rdx
  const char *v12; // r9
  void *v13; // rbx
  void *v14; // r14
  DWORD LastError; // edi
  LPVOID pv; // [rsp+38h] [rbp-41h] BYREF
  LPCWCH lpString1[2]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int64 v18; // [rsp+50h] [rbp-29h]
  unsigned __int64 v19; // [rsp+58h] [rbp-21h]
  LPCWCH lpString2[2]; // [rsp+60h] [rbp-19h] BYREF
  int cchCount2[2]; // [rsp+70h] [rbp-9h]
  unsigned __int64 v22; // [rsp+78h] [rbp-1h]
  __int128 v23; // [rsp+80h] [rbp+7h] BYREF
  __int128 v24; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  GetFinalPath((DWORD *)lpString2, a2);
  GetFinalPath((DWORD *)lpString1, lpFileName);
  v5 = (const WCHAR *)lpString2;
  if ( v22 > 7 )
    v5 = lpString2[0];
  v6 = (const WCHAR *)lpString1;
  if ( v19 > 7 )
    v6 = lpString1[0];
  if ( CompareStringOrdinal(v6, cchCount2[0], v5, cchCount2[0], 1) == 2 )
  {
    v8 = *(_QWORD *)cchCount2 + 1LL;
    v23 = 0;
    v24 = 0;
    if ( v18 < *(_QWORD *)cchCount2 + 1LL )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      JUMPOUT(0x18003EB3BLL);
    }
    v9 = -1;
    if ( v18 - v8 != -1 )
      v9 = v18 - v8;
    v10 = lpString1;
    if ( v19 > 7 )
      v10 = (LPCWCH *)lpString1[0];
    std::wstring::_Construct<1,unsigned short const *>(&v23, (char *)v10 + 2 * v8, v9);
    v11 = &v23;
    if ( *((_QWORD *)&v24 + 1) > 7u )
      v11 = (__int128 *)v23;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &pv,
      v11,
      -1);
    v13 = pv;
    if ( !pv )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xFF8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v12);
    if ( a3 != &pv )
    {
      v14 = *a3;
      if ( *a3 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v14);
        SetLastError(LastError);
      }
      *a3 = v13;
      v13 = 0;
      pv = 0;
    }
    if ( v13 )
      CoTaskMemFree(v13);
    std::wstring::~wstring(&v23);
    std::wstring::~wstring(lpString1);
    std::wstring::~wstring(lpString2);
    return 1;
  }
  else
  {
    std::wstring::~wstring(lpString1);
    std::wstring::~wstring(lpString2);
    return 0;
  }
}

```

## disassembly

```asm
0x18003e974  push    rbp
0x18003e976  push    rbx
0x18003e977  push    rsi
0x18003e978  push    rdi
0x18003e979  push    r14
0x18003e97b  lea     rbp, [rsp-37h]
0x18003e980  sub     rsp, 0B0h
0x18003e987  mov     rax, cs:__security_cookie
0x18003e98e  xor     rax, rsp
0x18003e991  mov     [rbp+57h+var_30], rax
0x18003e995  mov     rsi, r8
0x18003e998  mov     rbx, rcx
0x18003e99b  mov     [rbp+57h+var_A0], 0
0x18003e9a2  lea     rcx, [rbp+57h+lpString2]; Src
0x18003e9a6  call    ?GetFinalPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetFinalPath(ushort const *)
0x18003e9ab  nop
0x18003e9ac  mov     rdx, rbx; lpFileName
0x18003e9af  lea     rcx, [rbp+57h+lpString1]; Src
0x18003e9b3  call    ?GetFinalPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetFinalPath(ushort const *)
0x18003e9b8  nop
0x18003e9b9  mov     edx, [rbp+57h+cchCount2]; cchCount1
0x18003e9bc  lea     r8, [rbp+57h+lpString2]
0x18003e9c0  cmp     [rbp+57h+var_58], 7
0x18003e9c5  cmova   r8, [rbp+57h+lpString2]; lpString2
0x18003e9ca  lea     rcx, [rbp+57h+lpString1]
0x18003e9ce  cmp     [rbp+57h+var_78], 7
0x18003e9d3  cmova   rcx, [rbp+57h+lpString1]; lpString1
0x18003e9d8  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18003e9e0  mov     r9d, edx; cchCount2
0x18003e9e3  call    cs:__imp_CompareStringOrdinal
0x18003e9ea  nop     dword ptr [rax+rax+00h]
0x18003e9ef  cmp     eax, 2
0x18003e9f2  jz      short loc_18003EA0E
0x18003e9f4  lea     rcx, [rbp+57h+lpString1]; void *
0x18003e9f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e9fd  nop
0x18003e9fe  lea     rcx, [rbp+57h+lpString2]; void *
0x18003ea02  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ea07  xor     al, al
0x18003ea09  jmp     loc_18003EB09
0x18003ea0e  mov     rcx, qword ptr [rbp+57h+cchCount2]
0x18003ea12  inc     rcx
0x18003ea15  xorps   xmm0, xmm0
0x18003ea18  movups  [rbp+57h+var_50], xmm0
0x18003ea1c  xorps   xmm1, xmm1
0x18003ea1f  movdqu  [rbp+57h+var_40], xmm1
0x18003ea24  mov     rax, [rbp+57h+var_80]
0x18003ea28  cmp     rax, rcx
0x18003ea2b  jb      loc_18003EB36
0x18003ea31  sub     rax, rcx
0x18003ea34  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003ea38  mov     r8, rbx
0x18003ea3b  cmp     rax, rbx
0x18003ea3e  cmovb   r8, rax
0x18003ea42  lea     rax, [rbp+57h+lpString1]
0x18003ea46  cmp     [rbp+57h+var_78], 7
0x18003ea4b  cmova   rax, [rbp+57h+lpString1]
0x18003ea50  lea     rdx, [rax+rcx*2]
0x18003ea54  lea     rcx, [rbp+57h+var_50]
0x18003ea58  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003ea5d  nop
0x18003ea5e  lea     rdx, [rbp+57h+var_50]
0x18003ea62  cmp     qword ptr [rbp+57h+var_40+8], 7
0x18003ea67  cmova   rdx, qword ptr [rbp+57h+var_50]
0x18003ea6c  mov     r8, rbx
0x18003ea6f  lea     rcx, [rbp+57h+pv]
0x18003ea73  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18003ea78  mov     [rbp+57h+var_A0], 5
0x18003ea7f  mov     rcx, [rbp+5Fh]; this
0x18003ea83  mov     rbx, [rbp+57h+pv]
0x18003ea87  test    rbx, rbx
0x18003ea8a  jz      loc_18003EB24
0x18003ea90  lea     rax, [rbp+57h+pv]
0x18003ea94  cmp     rsi, rax
0x18003ea97  jz      short loc_18003EAD5
0x18003ea99  mov     r14, [rsi]
0x18003ea9c  test    r14, r14
0x18003ea9f  jz      short loc_18003EACC
0x18003eaa1  call    cs:__imp_GetLastError
0x18003eaa8  nop     dword ptr [rax+rax+00h]
0x18003eaad  mov     edi, eax
0x18003eaaf  mov     rcx, r14; pv
0x18003eab2  call    cs:__imp_CoTaskMemFree
0x18003eab9  nop     dword ptr [rax+rax+00h]
0x18003eabe  mov     ecx, edi; dwErrCode
0x18003eac0  call    cs:__imp_SetLastError
0x18003eac7  nop     dword ptr [rax+rax+00h]
0x18003eacc  mov     [rsi], rbx
0x18003eacf  xor     ebx, ebx
0x18003ead1  mov     [rbp+57h+pv], rbx
0x18003ead5  test    rbx, rbx
0x18003ead8  jz      short loc_18003EAEA
0x18003eada  mov     rcx, rbx; pv
0x18003eadd  call    cs:__imp_CoTaskMemFree
0x18003eae4  nop     dword ptr [rax+rax+00h]
0x18003eae9  nop
0x18003eaea  lea     rcx, [rbp+57h+var_50]; void *
0x18003eaee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003eaf3  nop
0x18003eaf4  lea     rcx, [rbp+57h+lpString1]; void *
0x18003eaf8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003eafd  nop
0x18003eafe  lea     rcx, [rbp+57h+lpString2]; void *
0x18003eb02  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003eb07  mov     al, 1
0x18003eb09  mov     rcx, [rbp+57h+var_30]
0x18003eb0d  xor     rcx, rsp; StackCookie
0x18003eb10  call    __security_check_cookie
0x18003eb15  add     rsp, 0B0h
0x18003eb1c  pop     r14
0x18003eb1e  pop     rdi
0x18003eb1f  pop     rsi
0x18003eb20  pop     rbx
0x18003eb21  pop     rbp
0x18003eb22  retn
0x18003eb24  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003eb2b  mov     edx, 0FF8h; void *
0x18003eb30  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18003eb36  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
