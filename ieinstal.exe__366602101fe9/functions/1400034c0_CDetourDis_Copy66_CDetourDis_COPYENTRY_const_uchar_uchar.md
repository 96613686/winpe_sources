# CDetourDis::Copy66(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x1400034c0`
- end: `0x1400034f7`
- name: `?Copy66@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `55`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140011010`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::Copy66(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  const struct CDetourDis::COPYENTRY near *const *v4; // rdx

  *(_DWORD *)this = 1;
  *a3 = *a4;
  v4 = &CDetourDis::s_rceCopyTable + 2 * a4[1];
  return (unsigned __int8 *)(*((__int64 (__fastcall **)(CDetourDis *, const struct CDetourDis::COPYENTRY near *const *, unsigned __int8 *))v4
                             + 1))(
                              this,
                              v4,
                              a3 + 1);
}

```

## disassembly

```asm
0x1400034c0  sub     rsp, 38h
0x1400034c4  mov     dword ptr [rcx], 1
0x1400034ca  lea     rdx, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B; CDetourDis::COPYENTRY const near * const CDetourDis::s_rceCopyTable
0x1400034d1  movzx   eax, byte ptr [r9]
0x1400034d5  inc     r9
0x1400034d8  mov     [r8], al
0x1400034db  movzx   eax, byte ptr [r9]
0x1400034df  shl     rax, 4
0x1400034e3  add     rdx, rax
0x1400034e6  inc     r8
0x1400034e9  mov     rax, [rdx+8]
0x1400034ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034f2  add     rsp, 38h
0x1400034f6  retn
```
