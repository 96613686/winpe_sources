# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18001b850`
- end: `0x18001b92c`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `220`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b934`
- `0x18001baf4`

## callees

- `0x18000fb00`
- `0x180014b80`
- `0x18001b850`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b8e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b8e0`

## string_xrefs

- `0x18001b884`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rdi
  char v7; // al
  __int64 v8; // rax
  char *i; // rbx
  __int64 v10; // rbx
  _WORD *v11; // rax
  _WORD *v12; // rsi
  rsize_t v13; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 || (v7 = 1, a3 != -1) )
    v7 = 0;
  if ( v7 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
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
  v12 = v11;
  if ( v11 )
  {
    if ( a2 )
    {
      v13 = v10;
      memcpy_s(v11, 2 * v4 + 2, a2, v13 * 2);
      v12[v13] = 0;
    }
    else
    {
      *v11 = 0;
    }
    v12[v4] = 0;
  }
  *a1 = v12;
  return a1;
}

```

## disassembly

```asm
0x18001b850  push    rbx
0x18001b852  push    rbp
0x18001b853  push    rsi
0x18001b854  push    rdi
0x18001b855  push    r12
0x18001b857  push    r14
0x18001b859  push    r15
0x18001b85b  sub     rsp, 20h
0x18001b85f  mov     rdi, r8
0x18001b862  mov     rbp, rdx
0x18001b865  mov     r14, rcx
0x18001b868  xor     r12d, r12d
0x18001b86b  test    rdx, rdx
0x18001b86e  jnz     short loc_18001B878
0x18001b870  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18001b874  mov     al, 1
0x18001b876  jz      short loc_18001B87B
0x18001b878  mov     al, r12b
0x18001b87b  mov     rcx, [rsp+58h]; this
0x18001b880  test    al, al
0x18001b882  jz      short loc_18001B896
0x18001b884  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001b88b  mov     edx, 0F89h; void *
0x18001b890  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001b896  test    rbp, rbp
0x18001b899  jz      short loc_18001B8CA
0x18001b89b  mov     rax, rdi
0x18001b89e  mov     ecx, 7FFFFFFFh
0x18001b8a3  cmp     rdi, rcx
0x18001b8a6  cmovnb  rax, rcx
0x18001b8aa  mov     rbx, rbp
0x18001b8ad  test    rax, rax
0x18001b8b0  jz      short loc_18001B8C2
0x18001b8b2  cmp     [rbx], r12w
0x18001b8b6  jz      short loc_18001B8C2
0x18001b8b8  add     rbx, 2
0x18001b8bc  sub     rax, 1
0x18001b8c0  jnz     short loc_18001B8B2
0x18001b8c2  sub     rbx, rbp
0x18001b8c5  sar     rbx, 1
0x18001b8c8  jmp     short loc_18001B8CD
0x18001b8ca  mov     rbx, rdi
0x18001b8cd  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001b8d1  cmovz   rdi, rbx
0x18001b8d5  lea     r15, ds:2[rdi*2]
0x18001b8dd  mov     rcx, r15; cb
0x18001b8e0  call    cs:__imp_CoTaskMemAlloc
0x18001b8e6  mov     rsi, rax
0x18001b8e9  test    rax, rax
0x18001b8ec  jz      short loc_18001B917
0x18001b8ee  test    rbp, rbp
0x18001b8f1  jz      short loc_18001B90E
0x18001b8f3  add     rbx, rbx
0x18001b8f6  mov     r9, rbx; SourceSize
0x18001b8f9  mov     r8, rbp; Source
0x18001b8fc  mov     rdx, r15; DestinationSize
0x18001b8ff  mov     rcx, rax; Destination
0x18001b902  call    memcpy_s
0x18001b907  mov     [rbx+rsi], r12w
0x18001b90c  jmp     short loc_18001B912
0x18001b90e  mov     [rax], r12w
0x18001b912  mov     [rsi+rdi*2], r12w
0x18001b917  mov     [r14], rsi
0x18001b91a  mov     rax, r14
0x18001b91d  add     rsp, 20h
0x18001b921  pop     r15
0x18001b923  pop     r14
0x18001b925  pop     r12
0x18001b927  pop     rdi
0x18001b928  pop     rsi
0x18001b929  pop     rbp
0x18001b92a  pop     rbx
0x18001b92b  retn
```
