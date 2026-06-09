# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000f0c8`
- end: `0x18000f1dc`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `276`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `14`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800141f4`
- `0x18002b36c`
- `0x18002c7b0`
- `0x18002ee74`
- `0x1800303a0`
- `0x180030944`
- `0x1800319dc`
- `0x180032c70`
- `0x180032cec`
- `0x180033924`
- `0x180034430`
- `0x180036c88`
- `0x18004f6e8`
- `0x18005087c`

## callees

- `0x180003c82`
- `0x180003cf0`
- `0x18000b5c8`
- `0x18000f0c8`
- `0x1800570b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f188`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000f188`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f14b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f14b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f134`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f134`

## string_xrefs

- `0x18000f1ca`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  HANDLE ProcessHeap; // rax
  _WORD *v11; // rax
  _WORD *v12; // rsi
  size_t v13; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

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
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, 2 * v4 + 2);
  v12 = v11;
  if ( v11 )
  {
    if ( a2 )
    {
      v13 = 2 * v7;
      if ( v13 )
      {
        if ( 2 * v4 + 2 < v13 )
        {
          memset_0(v11, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
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
0x18000f0c8  push    rbx
0x18000f0ca  push    rbp
0x18000f0cb  push    rsi
0x18000f0cc  push    rdi
0x18000f0cd  push    r12
0x18000f0cf  push    r14
0x18000f0d1  push    r15
0x18000f0d3  sub     rsp, 20h
0x18000f0d7  xor     r12d, r12d
0x18000f0da  mov     rdi, r8
0x18000f0dd  mov     rbp, rdx
0x18000f0e0  mov     r14, rcx
0x18000f0e3  test    rdx, rdx
0x18000f0e6  jnz     short loc_18000F0F7
0x18000f0e8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000f0ec  jz      loc_18000F1C5
0x18000f0f2  mov     rbx, r8
0x18000f0f5  jmp     short loc_18000F12C
0x18000f0f7  mov     ecx, 7FFFFFFFh
0x18000f0fc  mov     rax, rdi
0x18000f0ff  cmp     rdi, rcx
0x18000f102  mov     rbx, rbp
0x18000f105  cmovnb  rax, rcx
0x18000f109  test    rax, rax
0x18000f10c  jz      short loc_18000F11E
0x18000f10e  cmp     [rbx], r12w
0x18000f112  jz      short loc_18000F11E
0x18000f114  add     rbx, 2
0x18000f118  sub     rax, 1
0x18000f11c  jnz     short loc_18000F10E
0x18000f11e  sub     rbx, rbp
0x18000f121  sar     rbx, 1
0x18000f124  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000f128  cmovz   rdi, rbx
0x18000f12c  lea     r15, ds:2[rdi*2]
0x18000f134  call    cs:__imp_GetProcessHeap
0x18000f13b  nop     dword ptr [rax+rax+00h]
0x18000f140  mov     r8, r15; dwBytes
0x18000f143  mov     edx, 8; dwFlags
0x18000f148  mov     rcx, rax; hHeap
0x18000f14b  call    cs:__imp_HeapAlloc
0x18000f152  nop     dword ptr [rax+rax+00h]
0x18000f157  mov     rsi, rax
0x18000f15a  test    rax, rax
0x18000f15d  jz      short loc_18000F1AF
0x18000f15f  test    rbp, rbp
0x18000f162  jz      short loc_18000F1A6
0x18000f164  add     rbx, rbx
0x18000f167  jz      short loc_18000F19F
0x18000f169  mov     rcx, rax; void *
0x18000f16c  cmp     r15, rbx
0x18000f16f  jb      short loc_18000F17E
0x18000f171  mov     r8, rbx; Size
0x18000f174  mov     rdx, rbp; Src
0x18000f177  call    memcpy_0
0x18000f17c  jmp     short loc_18000F19F
0x18000f17e  mov     r8, r15; Size
0x18000f181  xor     edx, edx; Val
0x18000f183  call    memset_0
0x18000f188  call    cs:__imp__o__errno
0x18000f18f  nop     dword ptr [rax+rax+00h]
0x18000f194  mov     dword ptr [rax], 22h ; '"'
0x18000f19a  call    _invalid_parameter_noinfo
0x18000f19f  mov     [rbx+rsi], r12w
0x18000f1a4  jmp     short loc_18000F1AA
0x18000f1a6  mov     [rax], r12w
0x18000f1aa  mov     [rsi+rdi*2], r12w
0x18000f1af  mov     [r14], rsi
0x18000f1b2  mov     rax, r14
0x18000f1b5  add     rsp, 20h
0x18000f1b9  pop     r15
0x18000f1bb  pop     r14
0x18000f1bd  pop     r12
0x18000f1bf  pop     rdi
0x18000f1c0  pop     rsi
0x18000f1c1  pop     rbp
0x18000f1c2  pop     rbx
0x18000f1c3  retn
0x18000f1c5  mov     rcx, [rsp+58h]; this
0x18000f1ca  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f1d1  mov     edx, 0F89h; void *
0x18000f1d6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
