# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180028fdc`
- end: `0x180029075`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180028f98`

## callees

- `0x180002360`
- `0x180028fdc`
- `0x18003b7a4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029036`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029036`

## string_xrefs

- `0x180028ffc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180028fdc  push    rbx
0x180028fde  push    rbp
0x180028fdf  push    rsi
0x180028fe0  push    rdi
0x180028fe1  push    r14
0x180028fe3  push    r15
0x180028fe5  sub     rsp, 28h
0x180028fe9  xor     r15d, r15d
0x180028fec  mov     rbx, rdx
0x180028fef  mov     rsi, rcx
0x180028ff2  test    rdx, rdx
0x180028ff5  jnz     short loc_18002900E
0x180028ff7  mov     rcx, [rsp+58h]; this
0x180028ffc  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180029003  mov     edx, 0F89h; void *
0x180029008  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002900e  mov     ecx, 7FFFFFFFh
0x180029013  mov     rax, rbx
0x180029016  cmp     [rax], r15w
0x18002901a  jz      short loc_180029026
0x18002901c  add     rax, 2
0x180029020  sub     rcx, 1
0x180029024  jnz     short loc_180029016
0x180029026  sub     rax, rbx
0x180029029  xor     ecx, ecx; uFlags
0x18002902b  sar     rax, 1
0x18002902e  lea     r14, [rax+rax]
0x180029032  lea     rdx, [r14+2]; uBytes
0x180029036  call    cs:__imp_LocalAlloc
0x18002903d  nop     dword ptr [rax+rax+00h]
0x180029042  mov     rdi, rax
0x180029045  test    rax, rax
0x180029048  jz      short loc_180029061
0x18002904a  mov     r9, r14; SourceSize
0x18002904d  lea     rdx, [r14+2]; DestinationSize
0x180029051  mov     r8, rbx; Source
0x180029054  mov     rcx, rax; Destination
0x180029057  call    memcpy_s
0x18002905c  mov     [r14+rdi], r15w
0x180029061  mov     [rsi], rdi
0x180029064  mov     rax, rsi
0x180029067  add     rsp, 28h
0x18002906b  pop     r15
0x18002906d  pop     r14
0x18002906f  pop     rdi
0x180029070  pop     rsi
0x180029071  pop     rbp
0x180029072  pop     rbx
0x180029073  retn
```
