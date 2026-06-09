# CDetourDis::CopyVex3(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x1400036f0`
- end: `0x14000372c`
- name: `?CopyVex3@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `60`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003740`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyVex3(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  *a3 = *a4;
  a3[1] = a4[1];
  a3[2] = a4[2];
  *((_DWORD *)this + 2) |= a4[2] >> 7;
  return CDetourDis::CopyVexCommon(this, a4[1] & 0x1F, a3 + 3, a4 + 3);
}

```

## disassembly

```asm
0x1400036f0  movzx   eax, byte ptr [r9]
0x1400036f4  mov     r10, r9
0x1400036f7  mov     [r8], al
0x1400036fa  movzx   eax, byte ptr [r9+1]
0x1400036ff  mov     [r8+1], al
0x140003703  movzx   eax, byte ptr [r9+2]
0x140003708  mov     [r8+2], al
0x14000370c  add     r8, 3; unsigned __int8 *
0x140003710  movzx   eax, byte ptr [r9+2]
0x140003715  add     r9, 3; unsigned __int8 *
0x140003719  shr     eax, 7
0x14000371c  or      [rcx+8], eax
0x14000371f  movzx   edx, byte ptr [r10+1]
0x140003724  and     dl, 1Fh; unsigned __int8
0x140003727  jmp     ?CopyVexCommon@CDetourDis@@IEAAPEAEEPEAE0@Z; CDetourDis::CopyVexCommon(uchar,uchar *,uchar *)
```
