# CDetourDis::CopyVex2(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x1400036c0`
- end: `0x1400036df`
- name: `?CopyVex2@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `31`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003740`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyVex2(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  *a3 = *a4;
  a3[1] = a4[1];
  return CDetourDis::CopyVexCommon(this, 1, a3 + 2, a4 + 2);
}

```

## disassembly

```asm
0x1400036c0  movzx   eax, byte ptr [r9]
0x1400036c4  mov     dl, 1; unsigned __int8
0x1400036c6  mov     [r8], al
0x1400036c9  movzx   eax, byte ptr [r9+1]
0x1400036ce  add     r9, 2; unsigned __int8 *
0x1400036d2  mov     [r8+1], al
0x1400036d6  add     r8, 2; unsigned __int8 *
0x1400036da  jmp     ?CopyVexCommon@CDetourDis@@IEAAPEAEEPEAE0@Z; CDetourDis::CopyVexCommon(uchar,uchar *,uchar *)
```
