# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000f280`
- end: `0x18000f390`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `272`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f238`
- `0x1800188e0`
- `0x1800341d0`
- `0x1800345a8`
- `0x180039f9c`
- `0x1800430ec`

## callees

- `0x18000f280`
- `0x18002e7a6`
- `0x18002e850`
- `0x18002f7db`
- `0x180031894`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f37d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f37d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f2e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f2e8`

## string_xrefs

- `0x18000f361`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rbp
  __int64 v7; // rax
  char *v8; // rbx
  __int64 v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  _QWORD *result; // rax
  size_t v13; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v7 = a3;
    v8 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v7 = 0x7FFFFFFF;
    for ( ; v7; --v7 )
    {
      if ( !*(_WORD *)v8 )
        break;
      v8 += 2;
    }
    v9 = (v8 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v9;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        a4);
    v9 = a3;
  }
  v10 = LocalAlloc(0, 2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v13 = 2 * v9;
      if ( v13 )
      {
        if ( 2 * v4 + 2 >= v13 )
        {
          memcpy_0(v10, a2, v13);
          v11[v13 / 2] = 0;
          v11[v4] = 0;
          goto LABEL_10;
        }
        memset_0(v10, 0, 2 * v4 + 2);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      v11[v13 / 2] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
LABEL_10:
  result = a1;
  *a1 = v11;
  return result;
}

```

## disassembly

```asm
0x18000f280  mov     [rsp+arg_10], rbx
0x18000f285  push    rbp
0x18000f286  push    r14
0x18000f288  push    r15
0x18000f28a  sub     rsp, 20h
0x18000f28e  mov     rbp, r8
0x18000f291  mov     r15, rdx
0x18000f294  mov     r14, rcx
0x18000f297  test    rdx, rdx
0x18000f29a  jz      short loc_18000F315
0x18000f29c  mov     ecx, 7FFFFFFFh
0x18000f2a1  mov     rax, r8
0x18000f2a4  cmp     r8, rcx
0x18000f2a7  mov     rbx, rdx
0x18000f2aa  cmovnb  rax, rcx
0x18000f2ae  test    rax, rax
0x18000f2b1  jz      short loc_18000F2C3
0x18000f2b3  cmp     word ptr [rbx], 0
0x18000f2b7  jz      short loc_18000F2C3
0x18000f2b9  add     rbx, 2
0x18000f2bd  sub     rax, 1
0x18000f2c1  jnz     short loc_18000F2B3
0x18000f2c3  sub     rbx, r15
0x18000f2c6  sar     rbx, 1
0x18000f2c9  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18000f2cd  cmovz   rbp, rbx
0x18000f2d1  mov     [rsp+38h+arg_0], rsi
0x18000f2d6  xor     ecx, ecx; uFlags
0x18000f2d8  lea     rsi, ds:2[rbp*2]
0x18000f2e0  mov     [rsp+38h+arg_8], rdi
0x18000f2e5  mov     rdx, rsi; uBytes
0x18000f2e8  call    cs:__imp_LocalAlloc
0x18000f2ee  mov     rdi, rax
0x18000f2f1  test    rax, rax
0x18000f2f4  jnz     short loc_18000F320
0x18000f2f6  mov     rsi, [rsp+38h+arg_0]
0x18000f2fb  mov     rax, r14
0x18000f2fe  mov     rbx, [rsp+38h+arg_10]
0x18000f303  mov     [r14], rdi
0x18000f306  mov     rdi, [rsp+38h+arg_8]
0x18000f30b  add     rsp, 20h
0x18000f30f  pop     r15
0x18000f311  pop     r14
0x18000f313  pop     rbp
0x18000f314  retn
0x18000f315  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18000f319  jz      short loc_18000F35C
0x18000f31b  mov     rbx, rbp
0x18000f31e  jmp     short loc_18000F2D1
0x18000f320  test    r15, r15
0x18000f323  jz      short loc_18000F336
0x18000f325  add     rbx, rbx
0x18000f328  jnz     short loc_18000F33D
0x18000f32a  xor     eax, eax
0x18000f32c  mov     [rbx+rdi], ax
0x18000f330  mov     [rdi+rbp*2], ax
0x18000f334  jmp     short loc_18000F2F6
0x18000f336  xor     eax, eax
0x18000f338  mov     [rdi], ax
0x18000f33b  jmp     short loc_18000F330
0x18000f33d  mov     rcx, rdi; void *
0x18000f340  cmp     rsi, rbx
0x18000f343  jb      short loc_18000F373
0x18000f345  mov     r8, rbx; Size
0x18000f348  mov     rdx, r15; Src
0x18000f34b  call    memcpy_0
0x18000f350  xor     eax, eax
0x18000f352  mov     [rbx+rdi], ax
0x18000f356  mov     [rdi+rbp*2], ax
0x18000f35a  jmp     short loc_18000F2F6
0x18000f35c  mov     rcx, [rsp+38h]; this
0x18000f361  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f368  mov     edx, 0F89h; void *
0x18000f36d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000f373  mov     r8, rsi; Size
0x18000f376  xor     edx, edx; Val
0x18000f378  call    memset_0
0x18000f37d  call    cs:__imp__o__errno
0x18000f383  mov     dword ptr [rax], 22h ; '"'
0x18000f389  call    _invalid_parameter_noinfo
0x18000f38e  jmp     short loc_18000F32A
```
