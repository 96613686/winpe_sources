# LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::iterator::iterator(LKRhash::CLKRLinearHashTable_Iterator)

- ea: `0x18000ed28`
- end: `0x18000ed5d`
- name: `??0iterator@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@IEAA@VCLKRLinearHashTable_Iterator@2@@Z`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f18c`
- `0x18000fbd4`
- `0x18000fc04`

## callees

- `0x180008224`
- `0x18000825c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LKRhash::CLKRLinearHashTable_Iterator *__fastcall LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::iterator::iterator(
        LKRhash::CLKRLinearHashTable_Iterator *a1,
        const struct LKRhash::CLKRLinearHashTable_Iterator *a2)
{
  LKRhash::CLKRLinearHashTable_Iterator::CLKRLinearHashTable_Iterator(a1, a2);
  LKRhash::CLKRLinearHashTable_Iterator::_AddRef(a2, -1);
  return a1;
}

```

## disassembly

```asm
0x18000ed28  mov     [rsp+arg_0], rbx
0x18000ed2d  mov     [rsp+arg_8], rdx
0x18000ed32  push    rdi
0x18000ed33  sub     rsp, 20h
0x18000ed37  mov     rbx, rdx
0x18000ed3a  mov     rdi, rcx
0x18000ed3d  call    ??0CLKRLinearHashTable_Iterator@LKRhash@@QEAA@AEBV01@@Z; LKRhash::CLKRLinearHashTable_Iterator::CLKRLinearHashTable_Iterator(LKRhash::CLKRLinearHashTable_Iterator const &)
0x18000ed42  nop
0x18000ed43  or      edx, 0FFFFFFFFh; int
0x18000ed46  mov     rcx, rbx; this
0x18000ed49  call    ?_AddRef@CLKRLinearHashTable_Iterator@LKRhash@@IEBAXH@Z; LKRhash::CLKRLinearHashTable_Iterator::_AddRef(int)
0x18000ed4e  nop
0x18000ed4f  mov     rax, rdi
0x18000ed52  mov     rbx, [rsp+28h+arg_0]
0x18000ed57  add     rsp, 20h
0x18000ed5b  pop     rdi
0x18000ed5c  retn
```
