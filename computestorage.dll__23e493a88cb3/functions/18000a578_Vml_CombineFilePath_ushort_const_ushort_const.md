# Vml::CombineFilePath(ushort const *,ushort const *)

- ea: `0x18000a578`
- end: `0x18000a671`
- name: `?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z`
- size: `249`
- prototype: `_QWORD *__fastcall(_QWORD *Src, PCWSTR pszPathIn, PCWSTR pszMore)`
- caller_count: `20`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180009ad8`
- `0x18000e530`
- `0x180014400`
- `0x180014510`
- `0x1800146e0`
- `0x1800152d0`
- `0x1800154a0`
- `0x18001c3d0`
- `0x18001c5d4`
- `0x18001db70`
- `0x18001dfe4`
- `0x18001ea88`
- `0x180020880`
- `0x180020b40`
- `0x1800247e4`
- `0x180024f88`
- `0x180027668`
- `0x180027ac4`
- `0x180027c64`
- `0x180027e8c`

## callees

- `0x18000a578`
- `0x1800127bc`
- `0x180013cb4`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18000a60a`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18000a60a`

## string_xrefs

- `0x18000a65f`: `onecore\vm\inc\CommonUtilities.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall Vml::CombineFilePath(_QWORD *Src, PCWSTR pszPathIn, PCWSTR pszMore)
{
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rsi
  WCHAR *v10; // rcx
  HRESULT v11; // eax
  _QWORD *v12; // rax
  ULONG dwFlags; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_OWORD *)Src = 0;
  Src[2] = 0;
  Src[3] = 7;
  *(_WORD *)Src = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( pszPathIn[v7] );
  v8 = -1;
  do
    ++v8;
  while ( pszMore[v8] );
  v9 = v8 + v7;
  std::wstring::resize(Src);
  if ( Src[3] <= 7u )
    v10 = (WCHAR *)Src;
  else
    v10 = (WCHAR *)*Src;
  v11 = PathCchCombineEx(v10, v9 + 10, pszPathIn, pszMore, 1u);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE4,
      (unsigned int)"onecore\\vm\\inc\\CommonUtilities.h",
      (const char *)(unsigned int)v11,
      dwFlags);
  if ( Src[3] <= 7u )
    v12 = Src;
  else
    v12 = (_QWORD *)*Src;
  do
    ++v6;
  while ( *((_WORD *)v12 + v6) );
  std::wstring::resize(Src);
  return Src;
}

```

## disassembly

```asm
0x18000a578  mov     rax, rsp
0x18000a57b  mov     [rax+20h], rbx
0x18000a57f  push    rbp
0x18000a580  push    rsi
0x18000a581  push    rdi
0x18000a582  push    r14
0x18000a584  push    r15
0x18000a586  sub     rsp, 40h
0x18000a58a  mov     r14, r8
0x18000a58d  mov     rbp, rdx
0x18000a590  mov     rbx, rcx
0x18000a593  mov     [rax-30h], rcx
0x18000a597  xor     r15d, r15d
0x18000a59a  mov     [rax-38h], r15d
0x18000a59e  xorps   xmm0, xmm0
0x18000a5a1  movups  xmmword ptr [rcx], xmm0
0x18000a5a4  mov     [rcx+10h], r15
0x18000a5a8  mov     qword ptr [rcx+18h], 7
0x18000a5b0  mov     [rcx], r15w
0x18000a5b4  mov     dword ptr [rax-38h], 2
0x18000a5bb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a5bf  mov     rcx, rdi
0x18000a5c2  inc     rcx
0x18000a5c5  cmp     [rdx+rcx*2], r15w
0x18000a5ca  jnz     short loc_18000A5C2
0x18000a5cc  mov     rax, rdi
0x18000a5cf  inc     rax
0x18000a5d2  cmp     [r8+rax*2], r15w
0x18000a5d7  jnz     short loc_18000A5CF
0x18000a5d9  lea     rsi, [rax+rcx]
0x18000a5dd  lea     rdx, [rsi+0Ah]
0x18000a5e1  mov     rcx, rbx; Src
0x18000a5e4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000a5e9  cmp     qword ptr [rbx+18h], 7
0x18000a5ee  jbe     short loc_18000A5F5
0x18000a5f0  mov     rcx, [rbx]
0x18000a5f3  jmp     short loc_18000A5F8
0x18000a5f5  mov     rcx, rbx; pszPathOut
0x18000a5f8  mov     [rsp+68h+dwFlags], 1; int
0x18000a600  mov     r9, r14; pszMore
0x18000a603  mov     r8, rbp; pszPathIn
0x18000a606  lea     rdx, [rsi+0Ah]; cchPathOut
0x18000a60a  call    cs:__imp_PathCchCombineEx
0x18000a611  nop     dword ptr [rax+rax+00h]
0x18000a616  mov     rcx, [rsp+68h]; this
0x18000a61b  test    eax, eax
0x18000a61d  js      short loc_18000A65C
0x18000a61f  cmp     qword ptr [rbx+18h], 7
0x18000a624  jbe     short loc_18000A62B
0x18000a626  mov     rax, [rbx]
0x18000a629  jmp     short loc_18000A62E
0x18000a62b  mov     rax, rbx
0x18000a62e  inc     rdi
0x18000a631  cmp     [rax+rdi*2], r15w
0x18000a636  jnz     short loc_18000A62E
0x18000a638  mov     rdx, rdi
0x18000a63b  mov     rcx, rbx; Src
0x18000a63e  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18000a643  nop
0x18000a644  mov     rax, rbx
0x18000a647  mov     rbx, [rsp+68h+arg_18]
0x18000a64f  add     rsp, 40h
0x18000a653  pop     r15
0x18000a655  pop     r14
0x18000a657  pop     rdi
0x18000a658  pop     rsi
0x18000a659  pop     rbp
0x18000a65a  retn
0x18000a65c  mov     r9d, eax; char *
0x18000a65f  lea     r8, aOnecoreVmIncCo; "onecore\\vm\\inc\\CommonUtilities.h"
0x18000a666  mov     edx, 0E4h; void *
0x18000a66b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
