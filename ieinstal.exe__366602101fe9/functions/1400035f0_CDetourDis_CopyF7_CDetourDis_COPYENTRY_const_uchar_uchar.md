# CDetourDis::CopyF7(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x1400035f0`
- end: `0x14000360c`
- name: `?CopyF7@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `28`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400030a0`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyF7(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  __int64 *v4; // rdx

  v4 = &qword_14001B160;
  if ( (a4[1] & 0x38) != 0 )
    v4 = &qword_14001B170;
  return CDetourDis::CopyBytes(this, (const struct CDetourDis::COPYENTRY *)v4, a3, a4);
}

```

## disassembly

```asm
0x1400035f0  test    byte ptr [r9+1], 38h
0x1400035f5  lea     rax, qword_14001B170
0x1400035fc  lea     rdx, qword_14001B160
0x140003603  cmovnz  rdx, rax; struct CDetourDis::COPYENTRY *
0x140003607  jmp     ?CopyBytes@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z; CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)
```
