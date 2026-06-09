# CDetourDis::Invalid(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x140003430`
- end: `0x140003435`
- name: `?Invalid@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `5`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::Invalid(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  return a4 + 1;
}

```

## disassembly

```asm
0x140003430  lea     rax, [r9+1]
0x140003434  retn
```
