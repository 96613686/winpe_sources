# wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)

- ea: `0x180008420`
- end: `0x1800084cd`
- name: `??$make_unique_ansistring@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z`
- size: `173`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180010600`
- `0x1800107e0`
- `0x180011030`
- `0x180011540`

## callees

- `0x1800079b8`
- `0x180008420`
- `0x18000fbdc`
- `0x18000fc00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008461`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008461`

## string_xrefs

- `0x1800084bb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_ansistring<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        _BYTE *a2,
        __int64 a3,
        const char *a4)
{
  rsize_t v6; // rbx
  _BYTE *v7; // rax
  unsigned int v8; // r8d
  const char *v9; // r9
  _BYTE *v10; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xFBD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = LocalAlloc(0, v6 + 1);
  v10 = v7;
  if ( v7 )
  {
    memcpy_s(v7, v6 + 1, a2, v6);
    v10[v6] = 0;
  }
  *a1 = v10;
  if ( !v10 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x1003, v8, v9);
  return a1;
}

```

## disassembly

```asm
0x180008420  mov     rax, rsp
0x180008423  mov     [rax+10h], rbx
0x180008427  mov     [rax+18h], rbp
0x18000842b  mov     [rax+8], rcx
0x18000842f  push    rsi
0x180008430  push    rdi
0x180008431  push    r14
0x180008433  sub     rsp, 30h
0x180008437  mov     rbp, rdx
0x18000843a  mov     rsi, rcx
0x18000843d  mov     dword ptr [rax-28h], 0
0x180008444  mov     rcx, [rsp+48h]; this
0x180008449  test    rdx, rdx
0x18000844c  jz      short loc_1800084BB
0x18000844e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180008452  inc     rbx
0x180008455  cmp     byte ptr [rbx+rdx], 0
0x180008459  jnz     short loc_180008452
0x18000845b  lea     rdx, [rbx+1]; uBytes
0x18000845f  xor     ecx, ecx; uFlags
0x180008461  call    cs:__imp_LocalAlloc
0x180008467  mov     rdi, rax
0x18000846a  test    rax, rax
0x18000846d  jz      short loc_180008485
0x18000846f  mov     r9, rbx; SourceSize
0x180008472  mov     r8, rbp; Source
0x180008475  lea     rdx, [rbx+1]; DestinationSize
0x180008479  mov     rcx, rax; Destination
0x18000847c  call    memcpy_s
0x180008481  mov     byte ptr [rbx+rdi], 0
0x180008485  mov     [rsi], rdi
0x180008488  mov     [rsp+48h+var_28], 1
0x180008490  mov     rcx, [rsp+48h]; this
0x180008495  test    rdi, rdi
0x180008498  jz      short loc_1800084B0
0x18000849a  mov     rax, rsi
0x18000849d  mov     rbx, [rsp+48h+arg_8]
0x1800084a2  mov     rbp, [rsp+48h+arg_10]
0x1800084a7  add     rsp, 30h
0x1800084ab  pop     r14
0x1800084ad  pop     rdi
0x1800084ae  pop     rsi
0x1800084af  retn
0x1800084b0  mov     edx, 1003h; void *
0x1800084b5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800084bb  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800084c2  mov     edx, 0FBDh; void *
0x1800084c7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
