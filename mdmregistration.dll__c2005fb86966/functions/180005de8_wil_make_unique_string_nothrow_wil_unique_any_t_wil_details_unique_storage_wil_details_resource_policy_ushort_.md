# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180005de8`
- end: `0x180005ec3`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `219`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005ecc`
- `0x1800198a0`
- `0x180045358`

## callees

- `0x180005de8`
- `0x18000cc1c`
- `0x180013bfc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005e59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005e59`

## string_xrefs

- `0x180005eb1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
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
0x180005de8  push    rbx
0x180005dea  push    rbp
0x180005deb  push    rsi
0x180005dec  push    rdi
0x180005ded  push    r12
0x180005def  push    r14
0x180005df1  push    r15
0x180005df3  sub     rsp, 20h
0x180005df7  xor     r12d, r12d
0x180005dfa  mov     rdi, r8
0x180005dfd  mov     rbp, rdx
0x180005e00  mov     r14, rcx
0x180005e03  test    rdx, rdx
0x180005e06  jnz     short loc_180005E17
0x180005e08  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180005e0c  jz      loc_180005EAC
0x180005e12  mov     rbx, r8
0x180005e15  jmp     short loc_180005E4C
0x180005e17  mov     ecx, 7FFFFFFFh
0x180005e1c  mov     rax, rdi
0x180005e1f  cmp     rdi, rcx
0x180005e22  mov     rbx, rbp
0x180005e25  cmovnb  rax, rcx
0x180005e29  test    rax, rax
0x180005e2c  jz      short loc_180005E3E
0x180005e2e  cmp     [rbx], r12w
0x180005e32  jz      short loc_180005E3E
0x180005e34  add     rbx, 2
0x180005e38  sub     rax, 1
0x180005e3c  jnz     short loc_180005E2E
0x180005e3e  sub     rbx, rbp
0x180005e41  sar     rbx, 1
0x180005e44  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180005e48  cmovz   rdi, rbx
0x180005e4c  lea     r15, ds:2[rdi*2]
0x180005e54  xor     ecx, ecx; uFlags
0x180005e56  mov     rdx, r15; uBytes
0x180005e59  call    cs:__imp_LocalAlloc
0x180005e60  nop     dword ptr [rax+rax+00h]
0x180005e65  mov     rsi, rax
0x180005e68  test    rax, rax
0x180005e6b  jz      short loc_180005E96
0x180005e6d  test    rbp, rbp
0x180005e70  jz      short loc_180005E8D
0x180005e72  add     rbx, rbx
0x180005e75  mov     r8, rbp; Source
0x180005e78  mov     r9, rbx; SourceSize
0x180005e7b  mov     rdx, r15; DestinationSize
0x180005e7e  mov     rcx, rax; Destination
0x180005e81  call    memcpy_s
0x180005e86  mov     [rbx+rsi], r12w
0x180005e8b  jmp     short loc_180005E91
0x180005e8d  mov     [rax], r12w
0x180005e91  mov     [rsi+rdi*2], r12w
0x180005e96  mov     [r14], rsi
0x180005e99  mov     rax, r14
0x180005e9c  add     rsp, 20h
0x180005ea0  pop     r15
0x180005ea2  pop     r14
0x180005ea4  pop     r12
0x180005ea6  pop     rdi
0x180005ea7  pop     rsi
0x180005ea8  pop     rbp
0x180005ea9  pop     rbx
0x180005eaa  retn
0x180005eac  mov     rcx, [rsp+58h]; this
0x180005eb1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005eb8  mov     edx, 0F89h; void *
0x180005ebd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
