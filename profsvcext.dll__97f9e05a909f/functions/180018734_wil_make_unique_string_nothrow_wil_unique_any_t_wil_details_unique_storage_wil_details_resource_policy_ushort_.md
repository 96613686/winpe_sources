# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180018734`
- end: `0x1800187ec`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `184`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800186f0`

## callees

- `0x18000ae6a`
- `0x18000aef8`
- `0x180016134`
- `0x180018734`
- `0x18001e580`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800187c3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800187c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018791`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018791`

## string_xrefs

- `0x180018754`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  v10 = (char *)LocalAlloc(0, v8 + 2);
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
0x180018734  push    rbx
0x180018736  push    rbp
0x180018737  push    rsi
0x180018738  push    rdi
0x180018739  push    r14
0x18001873b  push    r15
0x18001873d  sub     rsp, 28h
0x180018741  xor     r15d, r15d
0x180018744  mov     rsi, rdx
0x180018747  mov     r14, rcx
0x18001874a  test    rdx, rdx
0x18001874d  jnz     short loc_180018766
0x18001874f  mov     rcx, [rsp+58h]; this
0x180018754  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001875b  mov     edx, 0F89h; void *
0x180018760  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180018766  mov     ecx, 7FFFFFFFh
0x18001876b  mov     rax, rsi
0x18001876e  cmp     [rax], r15w
0x180018772  jz      short loc_18001877E
0x180018774  add     rax, 2
0x180018778  sub     rcx, 1
0x18001877c  jnz     short loc_18001876E
0x18001877e  sub     rax, rsi
0x180018781  xor     ecx, ecx; uFlags
0x180018783  sar     rax, 1
0x180018786  lea     rbx, [rax+rax]
0x18001878a  lea     rbp, [rbx+2]
0x18001878e  mov     rdx, rbp; uBytes
0x180018791  call    cs:__imp_LocalAlloc
0x180018797  mov     rdi, rax
0x18001879a  test    rax, rax
0x18001879d  jz      short loc_1800187D9
0x18001879f  test    rbx, rbx
0x1800187a2  jz      short loc_1800187D4
0x1800187a4  mov     rcx, rax; void *
0x1800187a7  cmp     rbp, rbx
0x1800187aa  jb      short loc_1800187B9
0x1800187ac  mov     r8, rbx; Size
0x1800187af  mov     rdx, rsi; Src
0x1800187b2  call    memcpy_0
0x1800187b7  jmp     short loc_1800187D4
0x1800187b9  mov     r8, rbp; Size
0x1800187bc  xor     edx, edx; Val
0x1800187be  call    memset_0
0x1800187c3  call    cs:__imp__o__errno
0x1800187c9  mov     dword ptr [rax], 22h ; '"'
0x1800187cf  call    _invalid_parameter_noinfo
0x1800187d4  mov     [rbx+rdi], r15w
0x1800187d9  mov     [r14], rdi
0x1800187dc  mov     rax, r14
0x1800187df  add     rsp, 28h
0x1800187e3  pop     r15
0x1800187e5  pop     r14
0x1800187e7  pop     rdi
0x1800187e8  pop     rsi
0x1800187e9  pop     rbp
0x1800187ea  pop     rbx
0x1800187eb  retn
```
