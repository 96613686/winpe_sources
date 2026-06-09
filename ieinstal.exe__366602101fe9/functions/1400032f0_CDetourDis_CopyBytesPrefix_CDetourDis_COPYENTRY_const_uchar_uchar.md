# CDetourDis::CopyBytesPrefix(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x1400032f0`
- end: `0x140003321`
- name: `?CopyBytesPrefix@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `49`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140011010`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyBytesPrefix(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  const struct CDetourDis::COPYENTRY near *const *v4; // rdx

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
0x1400032f0  sub     rsp, 38h
0x1400032f4  movzx   eax, byte ptr [r9]
0x1400032f8  lea     rdx, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B; CDetourDis::COPYENTRY const near * const CDetourDis::s_rceCopyTable
0x1400032ff  mov     [r8], al
0x140003302  inc     r9
0x140003305  movzx   eax, byte ptr [r9]
0x140003309  shl     rax, 4
0x14000330d  add     rdx, rax
0x140003310  inc     r8
0x140003313  mov     rax, [rdx+8]
0x140003317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000331c  add     rsp, 38h
0x140003320  retn
```
