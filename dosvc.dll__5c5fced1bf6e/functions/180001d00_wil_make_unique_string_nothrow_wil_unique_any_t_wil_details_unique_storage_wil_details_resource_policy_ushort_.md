# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180001d00`
- end: `0x180001dd2`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `210`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180001a70`
- `0x180001c20`
- `0x180002f50`

## callees

- `0x180001d00`
- `0x180001e80`
- `0x180009f98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001d7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180001d7b`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // r15
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rsi
  rsize_t v12; // rbx
  _QWORD *result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

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
  result = a1;
  *a1 = v11;
  return result;
}

```

## disassembly

```asm
0x180001d00  mov     [rsp+arg_10], rbx
0x180001d05  push    rbp
0x180001d06  push    rdi
0x180001d07  push    r15
0x180001d09  sub     rsp, 20h
0x180001d0d  mov     r15, r8
0x180001d10  mov     rbp, rdx
0x180001d13  mov     rdi, rcx
0x180001d16  test    rdx, rdx
0x180001d19  jnz     short loc_180001D31
0x180001d1b  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180001d1f  jnz     short loc_180001D2C
0x180001d21  mov     rcx, [rsp+38h]; this
0x180001d26  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180001d2c  mov     rbx, r15
0x180001d2f  jmp     short loc_180001D66
0x180001d31  mov     ecx, 7FFFFFFFh
0x180001d36  mov     rax, r15
0x180001d39  cmp     r15, rcx
0x180001d3c  mov     rbx, rbp
0x180001d3f  cmovnb  rax, rcx
0x180001d43  test    rax, rax
0x180001d46  jz      short loc_180001D58
0x180001d48  cmp     word ptr [rbx], 0
0x180001d4c  jz      short loc_180001D58
0x180001d4e  add     rbx, 2
0x180001d52  sub     rax, 1
0x180001d56  jnz     short loc_180001D48
0x180001d58  sub     rbx, rbp
0x180001d5b  sar     rbx, 1
0x180001d5e  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180001d62  cmovz   r15, rbx
0x180001d66  mov     [rsp+38h+arg_0], rsi
0x180001d6b  mov     [rsp+38h+arg_8], r14
0x180001d70  lea     r14, ds:2[r15*2]
0x180001d78  mov     rcx, r14; cb
0x180001d7b  call    cs:__imp_CoTaskMemAlloc
0x180001d81  mov     rsi, rax
0x180001d84  test    rax, rax
0x180001d87  jz      short loc_180001DB4
0x180001d89  test    rbp, rbp
0x180001d8c  jz      short loc_180001DAA
0x180001d8e  add     rbx, rbx
0x180001d91  mov     r8, rbp; Source
0x180001d94  mov     r9, rbx; SourceSize
0x180001d97  mov     rdx, r14; DestinationSize
0x180001d9a  mov     rcx, rax; Destination
0x180001d9d  call    memcpy_s
0x180001da2  xor     eax, eax
0x180001da4  mov     [rbx+rsi], ax
0x180001da8  jmp     short loc_180001DAF
0x180001daa  xor     eax, eax
0x180001dac  mov     [rsi], ax
0x180001daf  mov     [rsi+r15*2], ax
0x180001db4  mov     r14, [rsp+38h+arg_8]
0x180001db9  mov     rax, rdi
0x180001dbc  mov     rbx, [rsp+38h+arg_10]
0x180001dc1  mov     [rdi], rsi
0x180001dc4  mov     rsi, [rsp+38h+arg_0]
0x180001dc9  add     rsp, 20h
0x180001dcd  pop     r15
0x180001dcf  pop     rdi
0x180001dd0  pop     rbp
0x180001dd1  retn
```
