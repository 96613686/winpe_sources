# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1400194c8`
- end: `0x1400195ca`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `258`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001d5b0`
- `0x140054b10`
- `0x140057788`

## callees

- `0x140003df2`
- `0x140003eb4`
- `0x14000597e`
- `0x14000ceb8`
- `0x1400194c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140019576`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140019576`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140019539`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140019539`

## string_xrefs

- `0x1400195b8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  size_t v12; // rbx
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
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
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
0x1400194c8  push    rbx
0x1400194ca  push    rbp
0x1400194cb  push    rsi
0x1400194cc  push    rdi
0x1400194cd  push    r12
0x1400194cf  push    r14
0x1400194d1  push    r15
0x1400194d3  sub     rsp, 20h
0x1400194d7  xor     r12d, r12d
0x1400194da  mov     rdi, r8
0x1400194dd  mov     rbp, rdx
0x1400194e0  mov     r15, rcx
0x1400194e3  test    rdx, rdx
0x1400194e6  jnz     short loc_1400194F7
0x1400194e8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400194ec  jz      loc_1400195B3
0x1400194f2  mov     rbx, r8
0x1400194f5  jmp     short loc_14001952C
0x1400194f7  mov     ecx, 7FFFFFFFh
0x1400194fc  mov     rax, rdi
0x1400194ff  cmp     rdi, rcx
0x140019502  mov     rbx, rbp
0x140019505  cmovnb  rax, rcx
0x140019509  test    rax, rax
0x14001950c  jz      short loc_14001951E
0x14001950e  cmp     [rbx], r12w
0x140019512  jz      short loc_14001951E
0x140019514  add     rbx, 2
0x140019518  sub     rax, 1
0x14001951c  jnz     short loc_14001950E
0x14001951e  sub     rbx, rbp
0x140019521  sar     rbx, 1
0x140019524  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140019528  cmovz   rdi, rbx
0x14001952c  lea     r14, ds:2[rdi*2]
0x140019534  xor     ecx, ecx; uFlags
0x140019536  mov     rdx, r14; uBytes
0x140019539  call    cs:__imp_LocalAlloc
0x140019540  nop     dword ptr [rax+rax+00h]
0x140019545  mov     rsi, rax
0x140019548  test    rax, rax
0x14001954b  jz      short loc_14001959D
0x14001954d  test    rbp, rbp
0x140019550  jz      short loc_140019594
0x140019552  add     rbx, rbx
0x140019555  jz      short loc_14001958D
0x140019557  mov     rcx, rax; void *
0x14001955a  cmp     r14, rbx
0x14001955d  jb      short loc_14001956C
0x14001955f  mov     r8, rbx; Size
0x140019562  mov     rdx, rbp; Src
0x140019565  call    memcpy_0
0x14001956a  jmp     short loc_14001958D
0x14001956c  mov     r8, r14; Size
0x14001956f  xor     edx, edx; Val
0x140019571  call    memset_0
0x140019576  call    cs:__imp__o__errno
0x14001957d  nop     dword ptr [rax+rax+00h]
0x140019582  mov     dword ptr [rax], 22h ; '"'
0x140019588  call    _invalid_parameter_noinfo
0x14001958d  mov     [rbx+rsi], r12w
0x140019592  jmp     short loc_140019598
0x140019594  mov     [rax], r12w
0x140019598  mov     [rsi+rdi*2], r12w
0x14001959d  mov     [r15], rsi
0x1400195a0  mov     rax, r15
0x1400195a3  add     rsp, 20h
0x1400195a7  pop     r15
0x1400195a9  pop     r14
0x1400195ab  pop     r12
0x1400195ad  pop     rdi
0x1400195ae  pop     rsi
0x1400195af  pop     rbp
0x1400195b0  pop     rbx
0x1400195b1  retn
0x1400195b3  mov     rcx, [rsp+58h]; this
0x1400195b8  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400195bf  mov     edx, 0F89h; void *
0x1400195c4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
