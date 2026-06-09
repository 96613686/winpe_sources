# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)

- ea: `0x1800099ac`
- end: `0x1800099e6`
- name: `?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z`
- size: `58`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009674`
- `0x18001fce0`
- `0x1800304a4`

## callees

- `0x1800042e8`
- `0x1800099ac`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare(
        unsigned __int16 **a1,
        __int64 a2)
{
  unsigned __int16 *v2; // rax
  __int64 v3; // rdx
  unsigned __int16 v4; // cx

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  v2 = *a1;
  v3 = a2 - (_QWORD)*a1;
  while ( 1 )
  {
    v4 = *v2;
    if ( *v2 != *(unsigned __int16 *)((char *)v2 + v3) )
      break;
    ++v2;
    if ( !v4 )
      return 0;
  }
  return v4 < *(unsigned __int16 *)((char *)v2 + v3) ? -1 : 1;
}

```

## disassembly

```asm
0x1800099ac  sub     rsp, 28h
0x1800099b0  test    rdx, rdx
0x1800099b3  jnz     short loc_1800099C0
0x1800099b5  mov     ecx, 80004005h; int
0x1800099ba  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800099c0  mov     rax, [rcx]
0x1800099c3  sub     rdx, rax
0x1800099c6  movzx   ecx, word ptr [rax]
0x1800099c9  cmp     cx, [rax+rdx]
0x1800099cd  jnz     short loc_1800099DC
0x1800099cf  add     rax, 2
0x1800099d3  test    cx, cx
0x1800099d6  jnz     short loc_1800099C6
0x1800099d8  xor     eax, eax
0x1800099da  jmp     short loc_1800099E1
0x1800099dc  sbb     eax, eax
0x1800099de  or      eax, 1
0x1800099e1  add     rsp, 28h
0x1800099e5  retn
```
