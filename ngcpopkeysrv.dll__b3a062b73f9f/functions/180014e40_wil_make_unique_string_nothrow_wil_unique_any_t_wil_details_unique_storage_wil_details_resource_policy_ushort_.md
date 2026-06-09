# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180014e40`
- end: `0x180014f31`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `241`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180015030`
- `0x180015194`
- `0x180015288`
- `0x1800169e0`
- `0x1800177f4`
- `0x18001aae8`
- `0x18001ca98`
- `0x18001e1a4`
- `0x18001e4f0`

## callees

- `0x1800057ce`
- `0x180005858`
- `0x180006415`
- `0x18000c5c0`
- `0x180014e40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014efb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180014efb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014ec4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014ec4`

## string_xrefs

- `0x180014e6b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *i; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
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
    v7 = (i - a2) >> 1;
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
  v10 = LocalAlloc(0, 2 * v4 + 2);
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
0x180014e40  push    rbx
0x180014e42  push    rbp
0x180014e43  push    rsi
0x180014e44  push    rdi
0x180014e45  push    r12
0x180014e47  push    r14
0x180014e49  push    r15
0x180014e4b  sub     rsp, 20h
0x180014e4f  mov     rdi, r8
0x180014e52  mov     rbp, rdx
0x180014e55  mov     r15, rcx
0x180014e58  xor     r12d, r12d
0x180014e5b  test    rdx, rdx
0x180014e5e  jnz     short loc_180014E82
0x180014e60  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180014e64  jnz     short loc_180014E7D
0x180014e66  mov     rcx, [rsp+58h]; this
0x180014e6b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014e72  mov     edx, 0F89h; void *
0x180014e77  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180014e7d  mov     rbx, rdi
0x180014e80  jmp     short loc_180014EB7
0x180014e82  mov     rax, rdi
0x180014e85  mov     ecx, 7FFFFFFFh
0x180014e8a  cmp     rdi, rcx
0x180014e8d  cmovnb  rax, rcx
0x180014e91  mov     rbx, rbp
0x180014e94  test    rax, rax
0x180014e97  jz      short loc_180014EA9
0x180014e99  cmp     [rbx], r12w
0x180014e9d  jz      short loc_180014EA9
0x180014e9f  add     rbx, 2
0x180014ea3  sub     rax, 1
0x180014ea7  jnz     short loc_180014E99
0x180014ea9  sub     rbx, rbp
0x180014eac  sar     rbx, 1
0x180014eaf  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180014eb3  cmovz   rdi, rbx
0x180014eb7  lea     r14, ds:2[rdi*2]
0x180014ebf  mov     rdx, r14; uBytes
0x180014ec2  xor     ecx, ecx; uFlags
0x180014ec4  call    cs:__imp_LocalAlloc
0x180014eca  mov     rsi, rax
0x180014ecd  test    rax, rax
0x180014ed0  jz      short loc_180014F1C
0x180014ed2  test    rbp, rbp
0x180014ed5  jz      short loc_180014F13
0x180014ed7  add     rbx, rbx
0x180014eda  jz      short loc_180014F0C
0x180014edc  mov     rcx, rax; void *
0x180014edf  cmp     r14, rbx
0x180014ee2  jb      short loc_180014EF1
0x180014ee4  mov     r8, rbx; Size
0x180014ee7  mov     rdx, rbp; Src
0x180014eea  call    memcpy_0
0x180014eef  jmp     short loc_180014F0C
0x180014ef1  mov     r8, r14; Size
0x180014ef4  xor     edx, edx; Val
0x180014ef6  call    memset_0
0x180014efb  call    cs:__imp__o__errno
0x180014f01  mov     dword ptr [rax], 22h ; '"'
0x180014f07  call    _invalid_parameter_noinfo
0x180014f0c  mov     [rbx+rsi], r12w
0x180014f11  jmp     short loc_180014F17
0x180014f13  mov     [rax], r12w
0x180014f17  mov     [rsi+rdi*2], r12w
0x180014f1c  mov     [r15], rsi
0x180014f1f  mov     rax, r15
0x180014f22  add     rsp, 20h
0x180014f26  pop     r15
0x180014f28  pop     r14
0x180014f2a  pop     r12
0x180014f2c  pop     rdi
0x180014f2d  pop     rsi
0x180014f2e  pop     rbp
0x180014f2f  pop     rbx
0x180014f30  retn
```
