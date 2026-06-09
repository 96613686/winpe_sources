# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1801085fc`
- end: `0x1801086f8`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180112880`

## callees

- `0x180019f92`
- `0x18001a03c`
- `0x18001a054`
- `0x1800ef204`
- `0x1801085fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801086bb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801086bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010867e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010867e`

## string_xrefs

- `0x180108627`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  char *v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rdi
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
0x1801085fc  push    rbx
0x1801085fe  push    rbp
0x1801085ff  push    rsi
0x180108600  push    rdi
0x180108601  push    r12
0x180108603  push    r14
0x180108605  push    r15
0x180108607  sub     rsp, 20h
0x18010860b  xor     r12d, r12d
0x18010860e  mov     rbx, r8
0x180108611  mov     rbp, rdx
0x180108614  mov     r15, rcx
0x180108617  test    rdx, rdx
0x18010861a  jnz     short loc_18010863E
0x18010861c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180108620  jnz     short loc_180108639
0x180108622  mov     rcx, [rsp+58h]; this
0x180108627  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18010862e  mov     edx, 0F89h; void *
0x180108633  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180108639  mov     rdi, rbx
0x18010863c  jmp     short loc_180108673
0x18010863e  mov     ecx, 7FFFFFFFh
0x180108643  mov     rax, rbx
0x180108646  cmp     rbx, rcx
0x180108649  mov     rdi, rbp
0x18010864c  cmovnb  rax, rcx
0x180108650  test    rax, rax
0x180108653  jz      short loc_180108665
0x180108655  cmp     [rdi], r12w
0x180108659  jz      short loc_180108665
0x18010865b  add     rdi, 2
0x18010865f  sub     rax, 1
0x180108663  jnz     short loc_180108655
0x180108665  sub     rdi, rbp
0x180108668  sar     rdi, 1
0x18010866b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18010866f  cmovz   rbx, rdi
0x180108673  lea     r14, ds:2[rbx*2]
0x18010867b  mov     rcx, r14; cb
0x18010867e  call    cs:__imp_CoTaskMemAlloc
0x180108685  nop     dword ptr [rax+rax+00h]
0x18010868a  mov     rsi, rax
0x18010868d  test    rax, rax
0x180108690  jz      short loc_1801086E2
0x180108692  test    rbp, rbp
0x180108695  jz      short loc_1801086D9
0x180108697  add     rdi, rdi
0x18010869a  jz      short loc_1801086D2
0x18010869c  mov     rcx, rax; void *
0x18010869f  cmp     r14, rdi
0x1801086a2  jb      short loc_1801086B1
0x1801086a4  mov     r8, rdi; Size
0x1801086a7  mov     rdx, rbp; Src
0x1801086aa  call    memcpy_0
0x1801086af  jmp     short loc_1801086D2
0x1801086b1  mov     r8, r14; Size
0x1801086b4  xor     edx, edx; Val
0x1801086b6  call    memset_0
0x1801086bb  call    cs:__imp__o__errno
0x1801086c2  nop     dword ptr [rax+rax+00h]
0x1801086c7  mov     dword ptr [rax], 22h ; '"'
0x1801086cd  call    _invalid_parameter_noinfo
0x1801086d2  mov     [rdi+rsi], r12w
0x1801086d7  jmp     short loc_1801086DD
0x1801086d9  mov     [rax], r12w
0x1801086dd  mov     [rsi+rbx*2], r12w
0x1801086e2  mov     [r15], rsi
0x1801086e5  mov     rax, r15
0x1801086e8  add     rsp, 20h
0x1801086ec  pop     r15
0x1801086ee  pop     r14
0x1801086f0  pop     r12
0x1801086f2  pop     rdi
0x1801086f3  pop     rsi
0x1801086f4  pop     rbp
0x1801086f5  pop     rbx
0x1801086f6  retn
```
