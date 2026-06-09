# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180027440`
- end: `0x1800274d2`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800273fc`

## callees

- `0x180002310`
- `0x180027440`
- `0x180038af0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002749a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002749a`

## string_xrefs

- `0x180027460`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rcx
  char *v7; // rax
  rsize_t v8; // r14
  char *v9; // rax
  char *v10; // rdi
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
  v9 = (char *)LocalAlloc(0, v8 + 2);
  v10 = v9;
  if ( v9 )
  {
    memcpy_s(v9, v8 + 2, a2, v8);
    *(_WORD *)&v10[v8] = 0;
  }
  *a1 = v10;
  return a1;
}

```

## disassembly

```asm
0x180027440  push    rbx
0x180027442  push    rbp
0x180027443  push    rsi
0x180027444  push    rdi
0x180027445  push    r14
0x180027447  push    r15
0x180027449  sub     rsp, 28h
0x18002744d  xor     r15d, r15d
0x180027450  mov     rbx, rdx
0x180027453  mov     rsi, rcx
0x180027456  test    rdx, rdx
0x180027459  jnz     short loc_180027472
0x18002745b  mov     rcx, [rsp+58h]; this
0x180027460  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180027467  mov     edx, 0F89h; void *
0x18002746c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180027472  mov     ecx, 7FFFFFFFh
0x180027477  mov     rax, rbx
0x18002747a  cmp     [rax], r15w
0x18002747e  jz      short loc_18002748A
0x180027480  add     rax, 2
0x180027484  sub     rcx, 1
0x180027488  jnz     short loc_18002747A
0x18002748a  sub     rax, rbx
0x18002748d  xor     ecx, ecx; uFlags
0x18002748f  sar     rax, 1
0x180027492  lea     r14, [rax+rax]
0x180027496  lea     rdx, [r14+2]; uBytes
0x18002749a  call    cs:__imp_LocalAlloc
0x1800274a0  mov     rdi, rax
0x1800274a3  test    rax, rax
0x1800274a6  jz      short loc_1800274BF
0x1800274a8  mov     r9, r14; SourceSize
0x1800274ab  lea     rdx, [r14+2]; DestinationSize
0x1800274af  mov     r8, rbx; Source
0x1800274b2  mov     rcx, rax; Destination
0x1800274b5  call    memcpy_s
0x1800274ba  mov     [r14+rdi], r15w
0x1800274bf  mov     [rsi], rdi
0x1800274c2  mov     rax, rsi
0x1800274c5  add     rsp, 28h
0x1800274c9  pop     r15
0x1800274cb  pop     r14
0x1800274cd  pop     rdi
0x1800274ce  pop     rsi
0x1800274cf  pop     rbp
0x1800274d0  pop     rbx
0x1800274d1  retn
```
