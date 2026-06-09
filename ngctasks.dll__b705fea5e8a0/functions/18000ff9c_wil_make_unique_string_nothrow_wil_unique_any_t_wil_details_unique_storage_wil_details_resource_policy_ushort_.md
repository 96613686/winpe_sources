# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000ff9c`
- end: `0x1800100bc`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `288`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800103f8`
- `0x180011a80`
- `0x180012438`
- `0x180015748`
- `0x180016850`
- `0x18001c754`
- `0x18001c8bc`

## callees

- `0x180006e1a`
- `0x180006e9c`
- `0x180007351`
- `0x18000ff9c`
- `0x180014b80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010075`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180010075`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001003e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001003e`

## string_xrefs

- `0x18000ffe0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
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
  _WORD *v12; // rdi
  size_t v13; // rbx
  __int64 v14; // rcx
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
  v11 = LocalAlloc(0, 2 * v4 + 2);
  v12 = v11;
  if ( v11 )
  {
    if ( a2 )
    {
      v13 = 2 * v10;
      if ( v13 )
      {
        if ( 2 * v4 + 2 < v13 )
        {
          memset_0(v11, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno(v14) = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v11, a2, v13);
        }
      }
      v12[v13 / 2] = 0;
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
0x18000ff9c  mov     rax, rsp
0x18000ff9f  mov     [rax+10h], rbx
0x18000ffa3  mov     [rax+18h], rbp
0x18000ffa7  mov     [rax+8], rcx
0x18000ffab  push    rsi
0x18000ffac  push    rdi
0x18000ffad  push    r12
0x18000ffaf  push    r14
0x18000ffb1  push    r15
0x18000ffb3  sub     rsp, 30h
0x18000ffb7  mov     rsi, r8
0x18000ffba  mov     rbp, rdx
0x18000ffbd  mov     r14, rcx
0x18000ffc0  xor     r12d, r12d
0x18000ffc3  mov     [rax-38h], r12d
0x18000ffc7  test    rdx, rdx
0x18000ffca  jnz     short loc_18000FFD4
0x18000ffcc  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000ffd0  mov     al, 1
0x18000ffd2  jz      short loc_18000FFD7
0x18000ffd4  mov     al, r12b
0x18000ffd7  mov     rcx, [rsp+58h]; this
0x18000ffdc  test    al, al
0x18000ffde  jz      short loc_18000FFF2
0x18000ffe0  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ffe7  mov     edx, 0F89h; void *
0x18000ffec  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000fff2  test    rbp, rbp
0x18000fff5  jz      short loc_180010026
0x18000fff7  mov     rax, rsi
0x18000fffa  mov     ecx, 7FFFFFFFh
0x18000ffff  cmp     rsi, rcx
0x180010002  cmovnb  rax, rcx
0x180010006  mov     rbx, rbp
0x180010009  test    rax, rax
0x18001000c  jz      short loc_18001001E
0x18001000e  cmp     [rbx], r12w
0x180010012  jz      short loc_18001001E
0x180010014  add     rbx, 2
0x180010018  sub     rax, 1
0x18001001c  jnz     short loc_18001000E
0x18001001e  sub     rbx, rbp
0x180010021  sar     rbx, 1
0x180010024  jmp     short loc_180010029
0x180010026  mov     rbx, rsi
0x180010029  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001002d  cmovz   rsi, rbx
0x180010031  lea     r15, ds:2[rsi*2]
0x180010039  mov     rdx, r15; uBytes
0x18001003c  xor     ecx, ecx; uFlags
0x18001003e  call    cs:__imp_LocalAlloc
0x180010044  mov     rdi, rax
0x180010047  test    rax, rax
0x18001004a  jz      short loc_180010096
0x18001004c  test    rbp, rbp
0x18001004f  jz      short loc_18001008D
0x180010051  add     rbx, rbx
0x180010054  jz      short loc_180010086
0x180010056  mov     rcx, rax; void *
0x180010059  cmp     r15, rbx
0x18001005c  jb      short loc_18001006B
0x18001005e  mov     r8, rbx; Size
0x180010061  mov     rdx, rbp; Src
0x180010064  call    memcpy_0
0x180010069  jmp     short loc_180010086
0x18001006b  mov     r8, r15; Size
0x18001006e  xor     edx, edx; Val
0x180010070  call    memset_0
0x180010075  call    cs:__imp__o__errno
0x18001007b  mov     dword ptr [rax], 22h ; '"'
0x180010081  call    _invalid_parameter_noinfo
0x180010086  mov     [rbx+rdi], r12w
0x18001008b  jmp     short loc_180010091
0x18001008d  mov     [rax], r12w
0x180010091  mov     [rdi+rsi*2], r12w
0x180010096  mov     [r14], rdi
0x180010099  mov     [rsp+58h+var_38], 1
0x1800100a1  mov     rax, r14
0x1800100a4  mov     rbx, [rsp+58h+arg_8]
0x1800100a9  mov     rbp, [rsp+58h+arg_10]
0x1800100ae  add     rsp, 30h
0x1800100b2  pop     r15
0x1800100b4  pop     r14
0x1800100b6  pop     r12
0x1800100b8  pop     rdi
0x1800100b9  pop     rsi
0x1800100ba  retn
```
