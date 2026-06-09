# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000dbf0`
- end: `0x18000dcce`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `222`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b970`
- `0x18001bcec`
- `0x18001beec`
- `0x180029d98`
- `0x180050ffc`
- `0x180079e20`
- `0x18007edb0`
- `0x180080aec`

## callees

- `0x18000dbf0`
- `0x180011a2c`
- `0x18002d848`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dc23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dc23`

## string_xrefs

- `0x18000dc62`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  __int64 v6; // rdi
  __int64 v7; // r14
  _WORD *v8; // rax
  _WORD *v9; // rsi
  _QWORD *result; // rax
  __int64 v11; // rax
  char *v12; // rdi
  rsize_t v13; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 )
  {
    v11 = a3;
    v12 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v11 = 0x7FFFFFFF;
    for ( ; v11; --v11 )
    {
      if ( !*(_WORD *)v12 )
        break;
      v12 += 2;
    }
    v6 = (v12 - a2) >> 1;
    if ( a3 == -1 )
      a3 = v6;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v6 = a3;
  }
  v7 = a3;
  v8 = CoTaskMemAlloc(2 * a3 + 2);
  v9 = v8;
  if ( v8 )
  {
    if ( a2 )
    {
      v13 = v6;
      memcpy_s_1(v8, v7 * 2 + 2, a2, v13 * 2);
      v9[v13] = 0;
    }
    else
    {
      *v8 = 0;
    }
    v9[v7] = 0;
  }
  result = a1;
  *a1 = v9;
  return result;
}

```

## disassembly

```asm
0x18000dbf0  push    rbx
0x18000dbf2  push    rbp
0x18000dbf3  push    rdi
0x18000dbf4  sub     rsp, 20h
0x18000dbf8  mov     rbp, rdx
0x18000dbfb  mov     rbx, rcx
0x18000dbfe  test    rdx, rdx
0x18000dc01  jnz     short loc_18000DC74
0x18000dc03  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000dc07  jz      short loc_18000DC5D
0x18000dc09  mov     rdi, r8
0x18000dc0c  mov     [rsp+38h+arg_0], rsi
0x18000dc11  mov     [rsp+38h+arg_8], r14
0x18000dc16  lea     r14, [r8+r8]
0x18000dc1a  lea     rcx, [r14+2]; cb
0x18000dc1e  mov     [rsp+38h+arg_10], r15
0x18000dc23  call    cs:__imp_CoTaskMemAlloc
0x18000dc29  mov     rsi, rax
0x18000dc2c  test    rax, rax
0x18000dc2f  jz      short loc_18000DC40
0x18000dc31  test    rbp, rbp
0x18000dc34  jnz     short loc_18000DCAE
0x18000dc36  xor     eax, eax
0x18000dc38  mov     [rsi], ax
0x18000dc3b  mov     [r14+rsi], ax
0x18000dc40  mov     r15, [rsp+38h+arg_10]
0x18000dc45  mov     rax, rbx
0x18000dc48  mov     r14, [rsp+38h+arg_8]
0x18000dc4d  mov     [rbx], rsi
0x18000dc50  mov     rsi, [rsp+38h+arg_0]
0x18000dc55  add     rsp, 20h
0x18000dc59  pop     rdi
0x18000dc5a  pop     rbp
0x18000dc5b  pop     rbx
0x18000dc5c  retn
0x18000dc5d  mov     rcx, [rsp+38h]; this
0x18000dc62  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000dc69  mov     edx, 0F89h; void *
0x18000dc6e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000dc74  mov     ecx, 7FFFFFFFh
0x18000dc79  mov     rax, r8
0x18000dc7c  cmp     r8, rcx
0x18000dc7f  mov     rdi, rbp
0x18000dc82  cmovnb  rax, rcx
0x18000dc86  test    rax, rax
0x18000dc89  jz      short loc_18000DC9B
0x18000dc8b  cmp     word ptr [rdi], 0
0x18000dc8f  jz      short loc_18000DC9B
0x18000dc91  add     rdi, 2
0x18000dc95  sub     rax, 1
0x18000dc99  jnz     short loc_18000DC8B
0x18000dc9b  sub     rdi, rbp
0x18000dc9e  sar     rdi, 1
0x18000dca1  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000dca5  cmovz   r8, rdi
0x18000dca9  jmp     loc_18000DC0C
0x18000dcae  add     rdi, rdi
0x18000dcb1  lea     rdx, [r14+2]; DestinationSize
0x18000dcb5  mov     r9, rdi; SourceSize
0x18000dcb8  mov     r8, rbp; Source
0x18000dcbb  mov     rcx, rsi; Destination
0x18000dcbe  call    memcpy_s_1
0x18000dcc3  xor     eax, eax
0x18000dcc5  mov     [rdi+rsi], ax
0x18000dcc9  jmp     loc_18000DC3B
```
