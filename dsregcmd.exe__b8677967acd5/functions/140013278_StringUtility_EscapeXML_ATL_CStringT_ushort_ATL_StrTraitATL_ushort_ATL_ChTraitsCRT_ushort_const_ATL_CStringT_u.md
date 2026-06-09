# StringUtility::EscapeXML(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x140013278`
- end: `0x140013335`
- name: `?EscapeXML@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV23@@Z`
- size: `189`
- prototype: `__int64 __fastcall(const unsigned __int16 **, char **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140017104`
- `0x140017238`

## callees

- `0x140005c58`
- `0x140005ea0`
- `0x1400060c4`
- `0x140012f2c`
- `0x140013278`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StringUtility::EscapeXML(const unsigned __int16 **a1, char **a2)
{
  unsigned int v4; // eax
  int v5; // edi
  unsigned int v6; // edx
  __int64 result; // rax
  __int64 v8; // rcx

  ATL::CSimpleStringT<unsigned short,0>::Empty(a2);
  v4 = ATL::EscapeXML(*a1, *((_DWORD *)*a1 - 4), 0, 0);
  v5 = v4;
  v6 = *((_DWORD *)*a2 - 3) - v4;
  if ( ((v6 | (1 - *((_DWORD *)*a2 - 2))) & 0x80000000) != 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2, v4, *a2, v6 | (1 - *((_DWORD *)*a2 - 2)));
  result = ATL::EscapeXML(*a1, *((_DWORD *)*a1 - 4), *a2, v5);
  v8 = -1;
  if ( (_DWORD)result == -1 )
  {
    if ( *a2 )
    {
      do
        ++v8;
      while ( *(_WORD *)&(*a2)[2 * v8] );
      result = v8;
    }
    else
    {
      result = 0;
    }
  }
  if ( (int)result < 0 || (int)result > *((_DWORD *)*a2 - 3) )
    ATL::AtlThrowImpl(0x80070057);
  *((_DWORD *)*a2 - 4) = result;
  *(_WORD *)&(*a2)[2 * (int)result] = 0;
  return result;
}

```

## disassembly

```asm
0x140013278  mov     [rsp+arg_0], rbx
0x14001327d  mov     [rsp+arg_8], rsi
0x140013282  push    rdi
0x140013283  sub     rsp, 30h
0x140013287  mov     rsi, rcx
0x14001328a  mov     rbx, rdx
0x14001328d  mov     rcx, rdx
0x140013290  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140013295  mov     rcx, [rsi]; unsigned __int16 *
0x140013298  xor     r9d, r9d; int
0x14001329b  xor     r8d, r8d; unsigned __int16 *
0x14001329e  mov     edx, [rcx-10h]; int
0x1400132a1  call    ?EscapeXML@ATL@@YAHPEBGHPEAGHK@Z; ATL::EscapeXML(ushort const *,int,ushort *,int,ulong)
0x1400132a6  mov     r8, [rbx]
0x1400132a9  mov     r9d, 1
0x1400132af  mov     edi, eax
0x1400132b1  mov     edx, [r8-0Ch]
0x1400132b5  sub     r9d, [r8-8]
0x1400132b9  sub     edx, eax
0x1400132bb  or      r9d, edx
0x1400132be  jge     short loc_1400132CA
0x1400132c0  mov     edx, eax
0x1400132c2  mov     rcx, rbx
0x1400132c5  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400132ca  mov     rcx, [rsi]; unsigned __int16 *
0x1400132cd  mov     r9d, edi; int
0x1400132d0  mov     r8, [rbx]; unsigned __int16 *
0x1400132d3  mov     edx, [rcx-10h]; int
0x1400132d6  call    ?EscapeXML@ATL@@YAHPEBGHPEAGHK@Z; ATL::EscapeXML(ushort const *,int,ushort *,int,ulong)
0x1400132db  xor     r8d, r8d
0x1400132de  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400132e2  cmp     eax, ecx
0x1400132e4  jnz     short loc_140013300
0x1400132e6  mov     rax, [rbx]
0x1400132e9  test    rax, rax
0x1400132ec  jnz     short loc_1400132F3
0x1400132ee  mov     eax, r8d
0x1400132f1  jmp     short loc_140013300
0x1400132f3  inc     rcx
0x1400132f6  cmp     [rax+rcx*2], r8w
0x1400132fb  jnz     short loc_1400132F3
0x1400132fd  mov     rax, rcx
0x140013300  test    eax, eax
0x140013302  js      short loc_14001332A
0x140013304  mov     rcx, [rbx]
0x140013307  cmp     eax, [rcx-0Ch]
0x14001330a  jg      short loc_14001332A
0x14001330c  mov     rsi, [rsp+38h+arg_8]
0x140013311  mov     [rcx-10h], eax
0x140013314  mov     rcx, [rbx]
0x140013317  mov     rbx, [rsp+38h+arg_0]
0x14001331c  movsxd  rdx, eax
0x14001331f  mov     [rcx+rdx*2], r8w
0x140013324  add     rsp, 30h
0x140013328  pop     rdi
0x140013329  retn
0x14001332a  mov     ecx, 80070057h; unsigned int
0x14001332f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
