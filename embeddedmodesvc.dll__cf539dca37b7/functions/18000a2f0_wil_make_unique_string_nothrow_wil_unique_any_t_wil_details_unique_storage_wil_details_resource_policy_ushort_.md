# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000a2f0`
- end: `0x18000a3a6`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `182`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a2ac`

## callees

- `0x18000352a`
- `0x1800035a0`
- `0x18000a2f0`
- `0x18000c3d4`
- `0x180018760`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a37d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a37d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a34b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a34b`

## string_xrefs

- `0x18000a310`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rcx
  char *v7; // rax
  size_t v8; // rbx
  size_t v9; // rbp
  char *v10; // rax
  char *v11; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = 0x7FFFFFFF;
  v7 = a2;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 += 2;
    --v6;
  }
  while ( v6 );
  v8 = 2 * ((v7 - a2) >> 1);
  v9 = v8 + 2;
  v10 = (char *)CoTaskMemAlloc(v8 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( v8 )
    {
      if ( v9 < v8 )
      {
        memset_0(v10, 0, v9);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v10, a2, v8);
      }
    }
    *(_WORD *)&v11[v8] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x18000a2f0  push    rbx
0x18000a2f2  push    rbp
0x18000a2f3  push    rsi
0x18000a2f4  push    rdi
0x18000a2f5  push    r14
0x18000a2f7  push    r15
0x18000a2f9  sub     rsp, 28h
0x18000a2fd  xor     r15d, r15d
0x18000a300  mov     rsi, rdx
0x18000a303  mov     r14, rcx
0x18000a306  test    rdx, rdx
0x18000a309  jnz     short loc_18000A322
0x18000a30b  mov     rcx, [rsp+58h]; this
0x18000a310  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a317  mov     edx, 0F89h; void *
0x18000a31c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000a322  mov     ecx, 7FFFFFFFh
0x18000a327  mov     rax, rsi
0x18000a32a  cmp     [rax], r15w
0x18000a32e  jz      short loc_18000A33A
0x18000a330  add     rax, 2
0x18000a334  sub     rcx, 1
0x18000a338  jnz     short loc_18000A32A
0x18000a33a  sub     rax, rsi
0x18000a33d  sar     rax, 1
0x18000a340  lea     rbx, [rax+rax]
0x18000a344  lea     rbp, [rbx+2]
0x18000a348  mov     rcx, rbp; cb
0x18000a34b  call    cs:__imp_CoTaskMemAlloc
0x18000a351  mov     rdi, rax
0x18000a354  test    rax, rax
0x18000a357  jz      short loc_18000A393
0x18000a359  test    rbx, rbx
0x18000a35c  jz      short loc_18000A38E
0x18000a35e  mov     rcx, rax; void *
0x18000a361  cmp     rbp, rbx
0x18000a364  jb      short loc_18000A373
0x18000a366  mov     r8, rbx; Size
0x18000a369  mov     rdx, rsi; Src
0x18000a36c  call    memcpy_0
0x18000a371  jmp     short loc_18000A38E
0x18000a373  mov     r8, rbp; Size
0x18000a376  xor     edx, edx; Val
0x18000a378  call    memset_0
0x18000a37d  call    cs:__imp__o__errno
0x18000a383  mov     dword ptr [rax], 22h ; '"'
0x18000a389  call    _invalid_parameter_noinfo
0x18000a38e  mov     [rbx+rdi], r15w
0x18000a393  mov     [r14], rdi
0x18000a396  mov     rax, r14
0x18000a399  add     rsp, 28h
0x18000a39d  pop     r15
0x18000a39f  pop     r14
0x18000a3a1  pop     rdi
0x18000a3a2  pop     rsi
0x18000a3a3  pop     rbp
0x18000a3a4  pop     rbx
0x18000a3a5  retn
```
