# CDetourDis::Copy67(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x140003500`
- end: `0x140003538`
- name: `?Copy67@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `56`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140011010`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::Copy67(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  const struct CDetourDis::COPYENTRY near *const *v4; // rdx

  *((_DWORD *)this + 1) = 1;
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
0x140003500  sub     rsp, 38h
0x140003504  mov     dword ptr [rcx+4], 1
0x14000350b  lea     rdx, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B; CDetourDis::COPYENTRY const near * const CDetourDis::s_rceCopyTable
0x140003512  movzx   eax, byte ptr [r9]
0x140003516  inc     r9
0x140003519  mov     [r8], al
0x14000351c  movzx   eax, byte ptr [r9]
0x140003520  shl     rax, 4
0x140003524  add     rdx, rax
0x140003527  inc     r8
0x14000352a  mov     rax, [rdx+8]
0x14000352e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003533  add     rsp, 38h
0x140003537  retn
```
