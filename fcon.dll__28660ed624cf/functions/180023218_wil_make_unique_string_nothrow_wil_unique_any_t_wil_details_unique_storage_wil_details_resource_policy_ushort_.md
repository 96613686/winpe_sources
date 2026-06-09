# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180023218`
- end: `0x1800232e6`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `206`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026690`
- `0x180077a4c`
- `0x180079d20`

## callees

- `0x180006ae8`
- `0x18000b298`
- `0x180023218`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002329a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002329a`

## string_xrefs

- `0x180023243`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180023218  push    rbx
0x18002321a  push    rbp
0x18002321b  push    rsi
0x18002321c  push    rdi
0x18002321d  push    r12
0x18002321f  push    r14
0x180023221  push    r15
0x180023223  sub     rsp, 20h
0x180023227  xor     r12d, r12d
0x18002322a  mov     rdi, r8
0x18002322d  mov     rbp, rdx
0x180023230  mov     r14, rcx
0x180023233  test    rdx, rdx
0x180023236  jnz     short loc_18002325A
0x180023238  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18002323c  jnz     short loc_180023255
0x18002323e  mov     rcx, [rsp+58h]; this
0x180023243  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002324a  mov     edx, 0F89h; void *
0x18002324f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180023255  mov     rbx, rdi
0x180023258  jmp     short loc_18002328F
0x18002325a  mov     ecx, 7FFFFFFFh
0x18002325f  mov     rax, rdi
0x180023262  cmp     rdi, rcx
0x180023265  mov     rbx, rbp
0x180023268  cmovnb  rax, rcx
0x18002326c  test    rax, rax
0x18002326f  jz      short loc_180023281
0x180023271  cmp     [rbx], r12w
0x180023275  jz      short loc_180023281
0x180023277  add     rbx, 2
0x18002327b  sub     rax, 1
0x18002327f  jnz     short loc_180023271
0x180023281  sub     rbx, rbp
0x180023284  sar     rbx, 1
0x180023287  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002328b  cmovz   rdi, rbx
0x18002328f  lea     r15, ds:2[rdi*2]
0x180023297  mov     rcx, r15; cb
0x18002329a  call    cs:__imp_CoTaskMemAlloc
0x1800232a0  mov     rsi, rax
0x1800232a3  test    rax, rax
0x1800232a6  jz      short loc_1800232D1
0x1800232a8  test    rbp, rbp
0x1800232ab  jz      short loc_1800232C8
0x1800232ad  add     rbx, rbx
0x1800232b0  mov     r8, rbp; Source
0x1800232b3  mov     r9, rbx; SourceSize
0x1800232b6  mov     rdx, r15; DestinationSize
0x1800232b9  mov     rcx, rax; Destination
0x1800232bc  call    memcpy_s
0x1800232c1  mov     [rbx+rsi], r12w
0x1800232c6  jmp     short loc_1800232CC
0x1800232c8  mov     [rax], r12w
0x1800232cc  mov     [rsi+rdi*2], r12w
0x1800232d1  mov     [r14], rsi
0x1800232d4  mov     rax, r14
0x1800232d7  add     rsp, 20h
0x1800232db  pop     r15
0x1800232dd  pop     r14
0x1800232df  pop     r12
0x1800232e1  pop     rdi
0x1800232e2  pop     rsi
0x1800232e3  pop     rbp
0x1800232e4  pop     rbx
0x1800232e5  retn
```
