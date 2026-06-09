# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800080fc`
- end: `0x1800081e3`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `231`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ab88`
- `0x18000cc90`
- `0x18000ce20`
- `0x18000cf60`

## callees

- `0x180002916`
- `0x18000296c`
- `0x1800080fc`
- `0x18000a448`
- `0x18000d5b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800081a2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800081a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000816b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000816b`

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
      wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
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
0x1800080fc  push    rbx
0x1800080fe  push    rbp
0x1800080ff  push    rsi
0x180008100  push    rdi
0x180008101  push    r12
0x180008103  push    r14
0x180008105  push    r15
0x180008107  sub     rsp, 20h
0x18000810b  xor     r12d, r12d
0x18000810e  mov     rbx, r8
0x180008111  mov     rbp, rdx
0x180008114  mov     r15, rcx
0x180008117  test    rdx, rdx
0x18000811a  jnz     short loc_18000812B
0x18000811c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180008120  jz      loc_1800081D8
0x180008126  mov     rdi, rbx
0x180008129  jmp     short loc_180008160
0x18000812b  mov     ecx, 7FFFFFFFh
0x180008130  mov     rax, rbx
0x180008133  cmp     rbx, rcx
0x180008136  mov     rdi, rbp
0x180008139  cmovnb  rax, rcx
0x18000813d  test    rax, rax
0x180008140  jz      short loc_180008152
0x180008142  cmp     [rdi], r12w
0x180008146  jz      short loc_180008152
0x180008148  add     rdi, 2
0x18000814c  sub     rax, 1
0x180008150  jnz     short loc_180008142
0x180008152  sub     rdi, rbp
0x180008155  sar     rdi, 1
0x180008158  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000815c  cmovz   rbx, rdi
0x180008160  lea     r14, ds:2[rbx*2]
0x180008168  mov     rcx, r14; cb
0x18000816b  call    cs:__imp_CoTaskMemAlloc
0x180008171  mov     rsi, rax
0x180008174  test    rax, rax
0x180008177  jz      short loc_1800081C3
0x180008179  test    rbp, rbp
0x18000817c  jz      short loc_1800081BA
0x18000817e  add     rdi, rdi
0x180008181  jz      short loc_1800081B3
0x180008183  mov     rcx, rax; void *
0x180008186  cmp     r14, rdi
0x180008189  jb      short loc_180008198
0x18000818b  mov     r8, rdi; Size
0x18000818e  mov     rdx, rbp; Src
0x180008191  call    memcpy_0
0x180008196  jmp     short loc_1800081B3
0x180008198  mov     r8, r14; Size
0x18000819b  xor     edx, edx; Val
0x18000819d  call    memset_0
0x1800081a2  call    cs:__imp__o__errno
0x1800081a8  mov     dword ptr [rax], 22h ; '"'
0x1800081ae  call    _invalid_parameter_noinfo
0x1800081b3  mov     [rdi+rsi], r12w
0x1800081b8  jmp     short loc_1800081BE
0x1800081ba  mov     [rax], r12w
0x1800081be  mov     [rsi+rbx*2], r12w
0x1800081c3  mov     [r15], rsi
0x1800081c6  mov     rax, r15
0x1800081c9  add     rsp, 20h
0x1800081cd  pop     r15
0x1800081cf  pop     r14
0x1800081d1  pop     r12
0x1800081d3  pop     rdi
0x1800081d4  pop     rsi
0x1800081d5  pop     rbp
0x1800081d6  pop     rbx
0x1800081d7  retn
0x1800081d8  mov     rcx, [rsp+58h]; this
0x1800081dd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
