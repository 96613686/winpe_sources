# CDetourDis::Copy0F78(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x140003480`
- end: `0x1400034ae`
- name: `?Copy0F78@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `46`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003480`
- `0x140011010`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::Copy0F78(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  __int64 *v4; // rax

  if ( *((_DWORD *)this + 4) || (v4 = &qword_14001B120, *(_DWORD *)this) )
    v4 = &qword_14001B130;
  return (unsigned __int8 *)((__int64 (__fastcall *)(CDetourDis *, __int64 *, unsigned __int8 *, unsigned __int8 *))v4[1])(
                              this,
                              v4,
                              a3,
                              a4);
}

```

## disassembly

```asm
0x140003480  sub     rsp, 38h
0x140003484  cmp     dword ptr [rcx+10h], 0
0x140003488  jnz     short loc_140003496
0x14000348a  cmp     dword ptr [rcx], 0
0x14000348d  lea     rax, qword_14001B120
0x140003494  jz      short loc_14000349D
0x140003496  lea     rax, qword_14001B130
0x14000349d  mov     rdx, rax
0x1400034a0  mov     rax, [rax+8]
0x1400034a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034a9  add     rsp, 38h
0x1400034ad  retn
```
