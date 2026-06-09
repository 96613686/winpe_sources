# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x140015164`
- end: `0x14001522b`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140015a6c`

## callees

- `0x140015164`
- `0x140015a28`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400151f5`
- `msvcrt!memcpy_s` at `0x1400151f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400151d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400151d3`

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
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
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
0x140015164  push    rbx
0x140015166  push    rbp
0x140015167  push    rsi
0x140015168  push    rdi
0x140015169  push    r12
0x14001516b  push    r14
0x14001516d  push    r15
0x14001516f  sub     rsp, 20h
0x140015173  xor     r12d, r12d
0x140015176  mov     rdi, r8
0x140015179  mov     rbp, rdx
0x14001517c  mov     r14, rcx
0x14001517f  test    rdx, rdx
0x140015182  jnz     short loc_140015193
0x140015184  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140015188  jz      loc_140015220
0x14001518e  mov     rbx, r8
0x140015191  jmp     short loc_1400151C8
0x140015193  mov     ecx, 7FFFFFFFh
0x140015198  mov     rax, rdi
0x14001519b  cmp     rdi, rcx
0x14001519e  mov     rbx, rbp
0x1400151a1  cmovnb  rax, rcx
0x1400151a5  test    rax, rax
0x1400151a8  jz      short loc_1400151BA
0x1400151aa  cmp     [rbx], r12w
0x1400151ae  jz      short loc_1400151BA
0x1400151b0  add     rbx, 2
0x1400151b4  sub     rax, 1
0x1400151b8  jnz     short loc_1400151AA
0x1400151ba  sub     rbx, rbp
0x1400151bd  sar     rbx, 1
0x1400151c0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400151c4  cmovz   rdi, rbx
0x1400151c8  lea     r15, ds:2[rdi*2]
0x1400151d0  mov     rcx, r15; cb
0x1400151d3  call    cs:__imp_CoTaskMemAlloc
0x1400151d9  mov     rsi, rax
0x1400151dc  test    rax, rax
0x1400151df  jz      short loc_14001520B
0x1400151e1  test    rbp, rbp
0x1400151e4  jz      short loc_140015202
0x1400151e6  add     rbx, rbx
0x1400151e9  mov     r8, rbp; Source
0x1400151ec  mov     r9, rbx; SourceSize
0x1400151ef  mov     rdx, r15; DestinationSize
0x1400151f2  mov     rcx, rax; Destination
0x1400151f5  call    cs:__imp_memcpy_s
0x1400151fb  mov     [rbx+rsi], r12w
0x140015200  jmp     short loc_140015206
0x140015202  mov     [rax], r12w
0x140015206  mov     [rsi+rdi*2], r12w
0x14001520b  mov     [r14], rsi
0x14001520e  mov     rax, r14
0x140015211  add     rsp, 20h
0x140015215  pop     r15
0x140015217  pop     r14
0x140015219  pop     r12
0x14001521b  pop     rdi
0x14001521c  pop     rsi
0x14001521d  pop     rbp
0x14001521e  pop     rbx
0x14001521f  retn
0x140015220  mov     rcx, [rsp+58h]; this
0x140015225  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
