# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)

- ea: `0x18001957c`
- end: `0x1800195b7`
- name: `?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z`
- size: `59`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a090`
- `0x180021acc`
- `0x180021e00`
- `0x180021f0c`

## callees

- `0x180008044`
- `0x18001957c`

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
0x18001957c  sub     rsp, 28h
0x180019580  test    rdx, rdx
0x180019583  jnz     short loc_180019590
0x180019585  mov     ecx, 80004005h; int
0x18001958a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180019590  mov     rax, [rcx]
0x180019593  sub     rdx, rax
0x180019596  movzx   ecx, word ptr [rax]
0x180019599  cmp     cx, [rax+rdx]
0x18001959d  jnz     short loc_1800195AC
0x18001959f  add     rax, 2
0x1800195a3  test    cx, cx
0x1800195a6  jnz     short loc_180019596
0x1800195a8  xor     eax, eax
0x1800195aa  jmp     short loc_1800195B1
0x1800195ac  sbb     eax, eax
0x1800195ae  or      eax, 1
0x1800195b1  add     rsp, 28h
0x1800195b5  retn
```
