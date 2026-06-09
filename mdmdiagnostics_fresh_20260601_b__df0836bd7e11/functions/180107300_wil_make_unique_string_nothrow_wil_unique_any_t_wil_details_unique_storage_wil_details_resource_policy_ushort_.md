# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180107300`
- end: `0x1801073ef`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801113dc`

## callees

- `0x180019f02`
- `0x180019fac`
- `0x180019fc4`
- `0x1800eeb68`
- `0x180107300`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801073b9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1801073b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180107382`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180107382`

## string_xrefs

- `0x18010732b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180107300  push    rbx
0x180107302  push    rbp
0x180107303  push    rsi
0x180107304  push    rdi
0x180107305  push    r12
0x180107307  push    r14
0x180107309  push    r15
0x18010730b  sub     rsp, 20h
0x18010730f  xor     r12d, r12d
0x180107312  mov     rbx, r8
0x180107315  mov     rbp, rdx
0x180107318  mov     r15, rcx
0x18010731b  test    rdx, rdx
0x18010731e  jnz     short loc_180107342
0x180107320  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180107324  jnz     short loc_18010733D
0x180107326  mov     rcx, [rsp+58h]; this
0x18010732b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180107332  mov     edx, 0F89h; void *
0x180107337  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18010733d  mov     rdi, rbx
0x180107340  jmp     short loc_180107377
0x180107342  mov     ecx, 7FFFFFFFh
0x180107347  mov     rax, rbx
0x18010734a  cmp     rbx, rcx
0x18010734d  mov     rdi, rbp
0x180107350  cmovnb  rax, rcx
0x180107354  test    rax, rax
0x180107357  jz      short loc_180107369
0x180107359  cmp     [rdi], r12w
0x18010735d  jz      short loc_180107369
0x18010735f  add     rdi, 2
0x180107363  sub     rax, 1
0x180107367  jnz     short loc_180107359
0x180107369  sub     rdi, rbp
0x18010736c  sar     rdi, 1
0x18010736f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180107373  cmovz   rbx, rdi
0x180107377  lea     r14, ds:2[rbx*2]
0x18010737f  mov     rcx, r14; cb
0x180107382  call    cs:__imp_CoTaskMemAlloc
0x180107388  mov     rsi, rax
0x18010738b  test    rax, rax
0x18010738e  jz      short loc_1801073DA
0x180107390  test    rbp, rbp
0x180107393  jz      short loc_1801073D1
0x180107395  add     rdi, rdi
0x180107398  jz      short loc_1801073CA
0x18010739a  mov     rcx, rax; void *
0x18010739d  cmp     r14, rdi
0x1801073a0  jb      short loc_1801073AF
0x1801073a2  mov     r8, rdi; Size
0x1801073a5  mov     rdx, rbp; Src
0x1801073a8  call    memcpy_0
0x1801073ad  jmp     short loc_1801073CA
0x1801073af  mov     r8, r14; Size
0x1801073b2  xor     edx, edx; Val
0x1801073b4  call    memset_0
0x1801073b9  call    cs:__imp__o__errno
0x1801073bf  mov     dword ptr [rax], 22h ; '"'
0x1801073c5  call    _invalid_parameter_noinfo
0x1801073ca  mov     [rdi+rsi], r12w
0x1801073cf  jmp     short loc_1801073D5
0x1801073d1  mov     [rax], r12w
0x1801073d5  mov     [rsi+rbx*2], r12w
0x1801073da  mov     [r15], rsi
0x1801073dd  mov     rax, r15
0x1801073e0  add     rsp, 20h
0x1801073e4  pop     r15
0x1801073e6  pop     r14
0x1801073e8  pop     r12
0x1801073ea  pop     rdi
0x1801073eb  pop     rsi
0x1801073ec  pop     rbp
0x1801073ed  pop     rbx
0x1801073ee  retn
```
