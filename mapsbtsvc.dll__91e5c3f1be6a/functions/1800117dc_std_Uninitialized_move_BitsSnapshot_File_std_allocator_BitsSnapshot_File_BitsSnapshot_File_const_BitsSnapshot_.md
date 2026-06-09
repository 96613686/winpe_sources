# std::_Uninitialized_move<BitsSnapshot::File *,std::allocator<BitsSnapshot::File>>(BitsSnapshot::File * const,BitsSnapshot::File * const,BitsSnapshot::File *,std::allocator<BitsSnapshot::File> &)

- ea: `0x1800117dc`
- end: `0x180011819`
- name: `??$_Uninitialized_move@PEAUFile@BitsSnapshot@@V?$allocator@UFile@BitsSnapshot@@@std@@@std@@YAPEAUFile@BitsSnapshot@@QEAU12@0PEAU12@AEAV?$allocator@UFile@BitsSnapshot@@@0@@Z`
- size: `61`
- prototype: `BitsSnapshot::File *__fastcall(__int64, __int64, BitsSnapshot::File *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800114f8`

## callees

- `0x180011488`
- `0x1800117dc`
- `0x18001187c`

## pseudocode

```c
BitsSnapshot::File *__fastcall std::_Uninitialized_move<BitsSnapshot::File *>(
        __int64 a1,
        __int64 a2,
        BitsSnapshot::File *a3)
{
  __int64 v4; // r8
  __int64 i; // r9
  __int64 v6; // r8

  v4 = a1;
  for ( i = a2; v4 != i; v4 = v6 + 56 )
  {
    std::_Default_allocator_traits<std::allocator<BitsSnapshot::File>>::construct<BitsSnapshot::File,BitsSnapshot::File>(
      a1,
      a3,
      v4,
      i);
    a3 = (BitsSnapshot::File *)((char *)a3 + 56);
  }
  std::_Destroy_range<std::allocator<BitsSnapshot::File>>(a3);
  return a3;
}

```

## disassembly

```asm
0x1800117dc  push    rbx
0x1800117de  sub     rsp, 20h
0x1800117e2  mov     rbx, r8
0x1800117e5  mov     r8, rcx
0x1800117e8  mov     r9, rdx
0x1800117eb  cmp     rcx, rdx
0x1800117ee  jz      short loc_180011805
0x1800117f0  mov     rdx, rbx
0x1800117f3  call    ??$construct@UFile@BitsSnapshot@@U12@@?$_Default_allocator_traits@V?$allocator@UFile@BitsSnapshot@@@std@@@std@@SAXAEAV?$allocator@UFile@BitsSnapshot@@@1@QEAUFile@BitsSnapshot@@$$QEAU34@@Z; std::_Default_allocator_traits<std::allocator<BitsSnapshot::File>>::construct<BitsSnapshot::File,BitsSnapshot::File>(std::allocator<BitsSnapshot::File> &,BitsSnapshot::File * const,BitsSnapshot::File &&)
0x1800117f8  add     rbx, 38h ; '8'
0x1800117fc  add     r8, 38h ; '8'
0x180011800  cmp     r8, r9
0x180011803  jnz     short loc_1800117F0
0x180011805  mov     rdx, rbx
0x180011808  mov     rcx, rbx; this
0x18001180b  call    ??$_Destroy_range@V?$allocator@UFile@BitsSnapshot@@@std@@@std@@YAXPEAUFile@BitsSnapshot@@QEAU12@AEAV?$allocator@UFile@BitsSnapshot@@@0@@Z; std::_Destroy_range<std::allocator<BitsSnapshot::File>>(BitsSnapshot::File *,BitsSnapshot::File * const,std::allocator<BitsSnapshot::File> &)
0x180011810  mov     rax, rbx
0x180011813  add     rsp, 20h
0x180011817  pop     rbx
0x180011818  retn
```
