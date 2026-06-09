# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180016c24`
- end: `0x180016cf2`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `206`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019670`
- `0x1800196b4`
- `0x180037378`
- `0x180044d8c`
- `0x180047b68`

## callees

- `0x180009070`
- `0x180016c24`
- `0x1800194d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016ca6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016ca6`

## string_xrefs

- `0x180016c4f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rsi
  rsize_t v12; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v8 = a3;
    v9 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v7;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = v7;
      memcpy_s(v10, 2 * v4 + 2, a2, v12 * 2);
      v11[v12] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x180016c24  push    rbx
0x180016c26  push    rbp
0x180016c27  push    rsi
0x180016c28  push    rdi
0x180016c29  push    r12
0x180016c2b  push    r14
0x180016c2d  push    r15
0x180016c2f  sub     rsp, 20h
0x180016c33  xor     r12d, r12d
0x180016c36  mov     rdi, r8
0x180016c39  mov     rbp, rdx
0x180016c3c  mov     r14, rcx
0x180016c3f  test    rdx, rdx
0x180016c42  jnz     short loc_180016C66
0x180016c44  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180016c48  jnz     short loc_180016C61
0x180016c4a  mov     rcx, [rsp+58h]; this
0x180016c4f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180016c56  mov     edx, 0F89h; void *
0x180016c5b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180016c61  mov     rbx, rdi
0x180016c64  jmp     short loc_180016C9B
0x180016c66  mov     ecx, 7FFFFFFFh
0x180016c6b  mov     rax, rdi
0x180016c6e  cmp     rdi, rcx
0x180016c71  mov     rbx, rbp
0x180016c74  cmovnb  rax, rcx
0x180016c78  test    rax, rax
0x180016c7b  jz      short loc_180016C8D
0x180016c7d  cmp     [rbx], r12w
0x180016c81  jz      short loc_180016C8D
0x180016c83  add     rbx, 2
0x180016c87  sub     rax, 1
0x180016c8b  jnz     short loc_180016C7D
0x180016c8d  sub     rbx, rbp
0x180016c90  sar     rbx, 1
0x180016c93  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180016c97  cmovz   rdi, rbx
0x180016c9b  lea     r15, ds:2[rdi*2]
0x180016ca3  mov     rcx, r15; cb
0x180016ca6  call    cs:__imp_CoTaskMemAlloc
0x180016cac  mov     rsi, rax
0x180016caf  test    rax, rax
0x180016cb2  jz      short loc_180016CDD
0x180016cb4  test    rbp, rbp
0x180016cb7  jz      short loc_180016CD4
0x180016cb9  add     rbx, rbx
0x180016cbc  mov     r8, rbp; Source
0x180016cbf  mov     r9, rbx; SourceSize
0x180016cc2  mov     rdx, r15; DestinationSize
0x180016cc5  mov     rcx, rax; Destination
0x180016cc8  call    memcpy_s
0x180016ccd  mov     [rbx+rsi], r12w
0x180016cd2  jmp     short loc_180016CD8
0x180016cd4  mov     [rax], r12w
0x180016cd8  mov     [rsi+rdi*2], r12w
0x180016cdd  mov     [r14], rsi
0x180016ce0  mov     rax, r14
0x180016ce3  add     rsp, 20h
0x180016ce7  pop     r15
0x180016ce9  pop     r14
0x180016ceb  pop     r12
0x180016ced  pop     rdi
0x180016cee  pop     rsi
0x180016cef  pop     rbp
0x180016cf0  pop     rbx
0x180016cf1  retn
```
