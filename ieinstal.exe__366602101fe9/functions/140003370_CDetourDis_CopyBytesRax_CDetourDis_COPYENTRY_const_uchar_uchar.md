# CDetourDis::CopyBytesRax(CDetourDis::COPYENTRY const *,uchar *,uchar *)

- ea: `0x140003370`
- end: `0x1400033ae`
- name: `?CopyBytesRax@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z`
- size: `62`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *__hidden this, const struct CDetourDis::COPYENTRY *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003370`
- `0x140011010`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyBytesRax(
        CDetourDis *this,
        const struct CDetourDis::COPYENTRY *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4)
{
  const struct CDetourDis::COPYENTRY near *const *v4; // rdx

  if ( (*a4 & 8) != 0 )
    *((_DWORD *)this + 2) = 1;
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
0x140003370  sub     rsp, 38h
0x140003374  test    byte ptr [r9], 8
0x140003378  jz      short loc_140003381
0x14000337a  mov     dword ptr [rcx+8], 1
0x140003381  movzx   eax, byte ptr [r9]
0x140003385  lea     rdx, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B; CDetourDis::COPYENTRY const near * const CDetourDis::s_rceCopyTable
0x14000338c  mov     [r8], al
0x14000338f  inc     r9
0x140003392  movzx   eax, byte ptr [r9]
0x140003396  shl     rax, 4
0x14000339a  add     rdx, rax
0x14000339d  inc     r8
0x1400033a0  mov     rax, [rdx+8]
0x1400033a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033a9  add     rsp, 38h
0x1400033ad  retn
```
