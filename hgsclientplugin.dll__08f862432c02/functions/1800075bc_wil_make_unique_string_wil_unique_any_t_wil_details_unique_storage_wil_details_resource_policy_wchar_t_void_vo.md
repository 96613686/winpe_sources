# wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)

- ea: `0x1800075bc`
- end: `0x1800076e6`
- name: `??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z`
- size: `298`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007c80`
- `0x180007f80`

## callees

- `0x180001f56`
- `0x180001f9e`
- `0x1800075bc`
- `0x1800083b8`
- `0x1800083d4`
- `0x18000a8a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007685`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180007685`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000764e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000764e`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  char v7; // al
  __int64 v8; // rax
  char *i; // rbx
  __int64 v10; // rbx
  _WORD *v11; // rax
  void *v12; // rdx
  unsigned int v13; // r8d
  const char *v14; // r9
  _WORD *v15; // rdi
  size_t v16; // rbx
  __int64 v17; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 || (v7 = 1, a3 != -1) )
    v7 = 0;
  if ( v7 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, (void *)0xF89, a3, a4);
  if ( a2 )
  {
    v8 = a3;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( i = a2; v8; --v8 )
    {
      if ( !*(_WORD *)i )
        break;
      i += 2;
    }
    v10 = (i - a2) >> 1;
  }
  else
  {
    v10 = a3;
  }
  if ( a3 == -1 )
    v4 = v10;
  v11 = CoTaskMemAlloc(2 * v4 + 2);
  v15 = v11;
  if ( v11 )
  {
    if ( a2 )
    {
      v16 = 2 * v10;
      if ( v16 )
      {
        if ( 2 * v4 + 2 < v16 )
        {
          memset_0(v11, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno(v17) = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v11, a2, v16);
        }
      }
      v15[v16 / 2] = 0;
    }
    else
    {
      *v11 = 0;
    }
    v15[v4] = 0;
  }
  *a1 = v15;
  if ( !v15 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v12, v13, v14);
  return a1;
}

```

## disassembly

```asm
0x1800075bc  mov     rax, rsp
0x1800075bf  mov     [rax+10h], rbx
0x1800075c3  mov     [rax+18h], rbp
0x1800075c7  mov     [rax+8], rcx
0x1800075cb  push    rsi
0x1800075cc  push    rdi
0x1800075cd  push    r12
0x1800075cf  push    r14
0x1800075d1  push    r15
0x1800075d3  sub     rsp, 30h
0x1800075d7  mov     rsi, r8
0x1800075da  mov     rbp, rdx
0x1800075dd  mov     r14, rcx
0x1800075e0  xor     r12d, r12d
0x1800075e3  mov     [rax-38h], r12d
0x1800075e7  test    rdx, rdx
0x1800075ea  jnz     short loc_1800075F4
0x1800075ec  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800075f0  mov     al, 1
0x1800075f2  jz      short loc_1800075F7
0x1800075f4  mov     al, r12b
0x1800075f7  mov     rcx, [rsp+58h]; this
0x1800075fc  test    al, al
0x1800075fe  jnz     loc_1800076D5
0x180007604  test    rbp, rbp
0x180007607  jz      short loc_180007638
0x180007609  mov     rax, rsi
0x18000760c  mov     ecx, 7FFFFFFFh
0x180007611  cmp     rsi, rcx
0x180007614  cmovnb  rax, rcx
0x180007618  mov     rbx, rbp
0x18000761b  test    rax, rax
0x18000761e  jz      short loc_180007630
0x180007620  cmp     [rbx], r12w
0x180007624  jz      short loc_180007630
0x180007626  add     rbx, 2
0x18000762a  sub     rax, 1
0x18000762e  jnz     short loc_180007620
0x180007630  sub     rbx, rbp
0x180007633  sar     rbx, 1
0x180007636  jmp     short loc_18000763B
0x180007638  mov     rbx, rsi
0x18000763b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000763f  cmovz   rsi, rbx
0x180007643  lea     r15, ds:2[rsi*2]
0x18000764b  mov     rcx, r15; cb
0x18000764e  call    cs:__imp_CoTaskMemAlloc
0x180007654  mov     rdi, rax
0x180007657  test    rax, rax
0x18000765a  jz      short loc_1800076A6
0x18000765c  test    rbp, rbp
0x18000765f  jz      short loc_18000769D
0x180007661  add     rbx, rbx
0x180007664  jz      short loc_180007696
0x180007666  mov     rcx, rax; void *
0x180007669  cmp     r15, rbx
0x18000766c  jb      short loc_18000767B
0x18000766e  mov     r8, rbx; Size
0x180007671  mov     rdx, rbp; Src
0x180007674  call    memcpy_0
0x180007679  jmp     short loc_180007696
0x18000767b  mov     r8, r15; Size
0x18000767e  xor     edx, edx; Val
0x180007680  call    memset_0
0x180007685  call    cs:__imp__o__errno
0x18000768b  mov     dword ptr [rax], 22h ; '"'
0x180007691  call    _invalid_parameter_noinfo
0x180007696  mov     [rbx+rdi], r12w
0x18000769b  jmp     short loc_1800076A1
0x18000769d  mov     [rax], r12w
0x1800076a1  mov     [rdi+rsi*2], r12w
0x1800076a6  mov     [r14], rdi
0x1800076a9  mov     [rsp+58h+var_38], 1
0x1800076b1  mov     rcx, [rsp+58h]; this
0x1800076b6  test    rdi, rdi
0x1800076b9  jz      short loc_1800076E0
0x1800076bb  mov     rax, r14
0x1800076be  mov     rbx, [rsp+58h+arg_8]
0x1800076c3  mov     rbp, [rsp+58h+arg_10]
0x1800076c8  add     rsp, 30h
0x1800076cc  pop     r15
0x1800076ce  pop     r14
0x1800076d0  pop     r12
0x1800076d2  pop     rdi
0x1800076d3  pop     rsi
0x1800076d4  retn
0x1800076d5  mov     edx, 0F89h; void *
0x1800076da  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800076e0  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
