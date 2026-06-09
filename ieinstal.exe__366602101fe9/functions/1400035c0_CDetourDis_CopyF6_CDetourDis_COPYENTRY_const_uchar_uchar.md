# CDetourDis::CopyF6(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x1400035c0`
- end: `0x1400035dc`
- name: `?CopyF6@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `28`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400030a0`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyF6(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  __int64 *v4; // rdx

  v4 = &qword_14001B140;
  if ( (a4[1] & 0x38) != 0 )
    v4 = &qword_14001B150;
  return CDetourDis::CopyBytes(this, (const struct CDetourDis::COPYENTRY *)v4, a3, a4);
}

```

## disassembly

```asm
0x1400035c0  test    byte ptr [r9+1], 38h
0x1400035c5  lea     rax, qword_14001B150
0x1400035cc  lea     rdx, qword_14001B140
0x1400035d3  cmovnz  rdx, rax; struct CDetourDis::COPYENTRY *
0x1400035d7  jmp     ?CopyBytes@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z; CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)
```
