# wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)

- ea: `0x180016a54`
- end: `0x180016bc4`
- name: `??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z`
- size: `368`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800163c4`
- `0x1800164dc`
- `0x1800165a4`
- `0x1800166a8`

## callees

- `0x18000c444`
- `0x18000c9c4`
- `0x18000ca20`
- `0x180016a54`
- `0x180017988`
- `0x18002d848`
- `0x18003c6f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016abd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016abd`

## string_xrefs

- `0x180016aa3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180016b3d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180016b90`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v4; // rdi
  __int64 v5; // rsi
  __int64 v7; // rax
  __int64 v8; // r14
  _WORD *v9; // rax
  unsigned __int16 *v10; // rbx
  wchar_t *v11; // r15
  wchar_t *v12; // rcx
  int v13; // eax
  unsigned int v14; // edi
  int v16; // [rsp+20h] [rbp-20h]
  int v17; // [rsp+20h] [rbp-20h]
  unsigned __int64 *v18; // [rsp+28h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  STRSAFE_LPWSTR pszDest; // [rsp+78h] [rbp+38h] BYREF
  unsigned __int16 *v21; // [rsp+80h] [rbp+40h] BYREF

  v4 = 0;
  v5 = a2;
  v7 = a2;
  v8 = a2 + 16 * a3;
  if ( a2 != v8 )
  {
    do
    {
      v4 += *(_QWORD *)(v7 + 8);
      v7 += 16;
    }
    while ( v7 != v8 );
  }
  pszDest = 0;
  if ( v4 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v9 = CoTaskMemAlloc(2 * v4 + 2);
  if ( v9 )
  {
    *v9 = 0;
    v9[v4] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszDest,
    v9);
  v10 = pszDest;
  if ( pszDest )
  {
    v21 = pszDest;
    v11 = &pszDest[v4 + 1];
    v12 = pszDest;
    while ( v5 != v8 )
    {
      if ( *(_QWORD *)v5 )
      {
        v13 = StringCchCopyNExW(v12, v11 - v12, *(const unsigned __int16 **)v5, *(_QWORD *)(v5 + 8), &v21, v18, 0x100u);
        v14 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x791,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v13,
            v17);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszDest);
          return v14;
        }
        v12 = v21;
      }
      v5 += 16;
    }
    v21 = v10;
    pszDest = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      a1,
      &v21);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v21);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszDest);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v16);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180016a54  mov     [rsp-28h+arg_0], rbx
0x180016a59  mov     [rsp-28h+arg_18], rsi
0x180016a5e  push    rbp
0x180016a5f  push    rdi
0x180016a60  push    r12
0x180016a62  push    r14
0x180016a64  push    r15
0x180016a66  mov     rbp, rsp
0x180016a69  sub     rsp, 40h
0x180016a6d  add     r8, r8
0x180016a70  xor     edi, edi
0x180016a72  mov     rsi, rdx
0x180016a75  mov     r12, rcx
0x180016a78  mov     rax, rdx
0x180016a7b  lea     r14, [rdx+r8*8]
0x180016a7f  cmp     rdx, r14
0x180016a82  jz      short loc_180016A91
0x180016a84  add     rdi, [rax+8]
0x180016a88  add     rax, 10h
0x180016a8c  cmp     rax, r14
0x180016a8f  jnz     short loc_180016A84
0x180016a91  mov     [rbp+pszDest], 0
0x180016a99  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180016a9d  jnz     short loc_180016AB5
0x180016a9f  mov     rcx, [rbp+28h]; this
0x180016aa3  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016aaa  mov     edx, 0F89h; void *
0x180016aaf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016ab5  lea     rcx, ds:2[rdi*2]; cb
0x180016abd  call    cs:__imp_CoTaskMemAlloc
0x180016ac3  test    rax, rax
0x180016ac6  jz      short loc_180016AD1
0x180016ac8  xor     ecx, ecx
0x180016aca  mov     [rax], cx
0x180016acd  mov     [rax+rdi*2], cx
0x180016ad1  mov     rdx, rax
0x180016ad4  lea     rcx, [rbp+pszDest]
0x180016ad8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180016add  mov     rbx, [rbp+pszDest]
0x180016ae1  test    rbx, rbx
0x180016ae4  jz      loc_180016B8C
0x180016aea  lea     r15, [rbx+2]
0x180016aee  mov     [rbp+arg_10], rbx
0x180016af2  lea     r15, [r15+rdi*2]
0x180016af6  mov     rcx, rbx; pszDest
0x180016af9  cmp     rsi, r14
0x180016afc  jz      short loc_180016B5E
0x180016afe  mov     r8, [rsi]; unsigned __int16 *
0x180016b01  test    r8, r8
0x180016b04  jz      short loc_180016B33
0x180016b06  mov     r9, [rsi+8]; unsigned __int64
0x180016b0a  lea     rax, [rbp+arg_10]
0x180016b0e  mov     rdx, r15
0x180016b11  mov     [rsp+40h+var_10], 100h; unsigned int
0x180016b19  sub     rdx, rcx
0x180016b1c  mov     [rsp+40h+var_20], rax; int
0x180016b21  sar     rdx, 1; unsigned __int64
0x180016b24  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180016b29  mov     edi, eax
0x180016b2b  test    eax, eax
0x180016b2d  js      short loc_180016B39
0x180016b2f  mov     rcx, [rbp+arg_10]
0x180016b33  add     rsi, 10h
0x180016b37  jmp     short loc_180016AF9
0x180016b39  mov     rcx, [rbp+28h]; this
0x180016b3d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016b44  mov     r9d, edi; char *
0x180016b47  mov     edx, 791h; void *
0x180016b4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b51  lea     rcx, [rbp+pszDest]
0x180016b55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180016b5a  mov     eax, edi
0x180016b5c  jmp     short loc_180016BAB
0x180016b5e  lea     rdx, [rbp+arg_10]
0x180016b62  mov     [rbp+arg_10], rbx
0x180016b66  mov     rcx, r12
0x180016b69  mov     [rbp+pszDest], 0
0x180016b71  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180016b76  lea     rcx, [rbp+arg_10]
0x180016b7a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180016b7f  lea     rcx, [rbp+pszDest]
0x180016b83  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180016b88  xor     eax, eax
0x180016b8a  jmp     short loc_180016BAB
0x180016b8c  mov     rcx, [rbp+28h]; this
0x180016b90  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016b97  mov     ebx, 8007000Eh
0x180016b9c  mov     edx, 788h; void *
0x180016ba1  mov     r9d, ebx; char *
0x180016ba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016ba9  mov     eax, ebx
0x180016bab  lea     r11, [rsp+40h+var_s0]
0x180016bb0  mov     rbx, [r11+30h]
0x180016bb4  mov     rsi, [r11+48h]
0x180016bb8  mov     rsp, r11
0x180016bbb  pop     r15
0x180016bbd  pop     r14
0x180016bbf  pop     r12
0x180016bc1  pop     rdi
0x180016bc2  pop     rbp
0x180016bc3  retn
```
