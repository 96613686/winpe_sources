# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000c538`
- end: `0x18000c60d`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `213`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009a8c`
- `0x1800161e4`
- `0x18002490c`

## callees

- `0x180005bb8`
- `0x18000c538`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c5cb`
- `msvcrt!memcpy_s` at `0x18000c5cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c5a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c5a9`

## string_xrefs

- `0x18000c5fb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
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
  v10 = LocalAlloc(0, 2 * v4 + 2);
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
0x18000c538  push    rbx
0x18000c53a  push    rbp
0x18000c53b  push    rsi
0x18000c53c  push    rdi
0x18000c53d  push    r12
0x18000c53f  push    r14
0x18000c541  push    r15
0x18000c543  sub     rsp, 20h
0x18000c547  xor     r12d, r12d
0x18000c54a  mov     rdi, r8
0x18000c54d  mov     rbp, rdx
0x18000c550  mov     r14, rcx
0x18000c553  test    rdx, rdx
0x18000c556  jnz     short loc_18000C567
0x18000c558  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000c55c  jz      loc_18000C5F6
0x18000c562  mov     rbx, r8
0x18000c565  jmp     short loc_18000C59C
0x18000c567  mov     ecx, 7FFFFFFFh
0x18000c56c  mov     rax, rdi
0x18000c56f  cmp     rdi, rcx
0x18000c572  mov     rbx, rbp
0x18000c575  cmovnb  rax, rcx
0x18000c579  test    rax, rax
0x18000c57c  jz      short loc_18000C58E
0x18000c57e  cmp     [rbx], r12w
0x18000c582  jz      short loc_18000C58E
0x18000c584  add     rbx, 2
0x18000c588  sub     rax, 1
0x18000c58c  jnz     short loc_18000C57E
0x18000c58e  sub     rbx, rbp
0x18000c591  sar     rbx, 1
0x18000c594  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000c598  cmovz   rdi, rbx
0x18000c59c  lea     r15, ds:2[rdi*2]
0x18000c5a4  xor     ecx, ecx; uFlags
0x18000c5a6  mov     rdx, r15; uBytes
0x18000c5a9  call    cs:__imp_LocalAlloc
0x18000c5af  mov     rsi, rax
0x18000c5b2  test    rax, rax
0x18000c5b5  jz      short loc_18000C5E1
0x18000c5b7  test    rbp, rbp
0x18000c5ba  jz      short loc_18000C5D8
0x18000c5bc  add     rbx, rbx
0x18000c5bf  mov     r8, rbp; Source
0x18000c5c2  mov     r9, rbx; SourceSize
0x18000c5c5  mov     rdx, r15; DestinationSize
0x18000c5c8  mov     rcx, rax; Destination
0x18000c5cb  call    cs:__imp_memcpy_s
0x18000c5d1  mov     [rbx+rsi], r12w
0x18000c5d6  jmp     short loc_18000C5DC
0x18000c5d8  mov     [rax], r12w
0x18000c5dc  mov     [rsi+rdi*2], r12w
0x18000c5e1  mov     [r14], rsi
0x18000c5e4  mov     rax, r14
0x18000c5e7  add     rsp, 20h
0x18000c5eb  pop     r15
0x18000c5ed  pop     r14
0x18000c5ef  pop     r12
0x18000c5f1  pop     rdi
0x18000c5f2  pop     rsi
0x18000c5f3  pop     rbp
0x18000c5f4  pop     rbx
0x18000c5f5  retn
0x18000c5f6  mov     rcx, [rsp+58h]; this
0x18000c5fb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c602  mov     edx, 0F89h; void *
0x18000c607  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
