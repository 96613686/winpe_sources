# LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::begin(void)

- ea: `0x18000fbd4`
- end: `0x18000fbfb`
- name: `?begin@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA?AViterator@12@XZ`
- size: `39`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f02c`
- `0x18000f43c`
- `0x18000f8dc`

## callees

- `0x18000813c`
- `0x18000ed28`

## pseudocode

```c
LKRhash::CLKRLinearHashTable_Iterator *__fastcall LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::begin(
        __int64 a1,
        LKRhash::CLKRLinearHashTable_Iterator *a2)
{
  const struct LKRhash::CLKRLinearHashTable_Iterator *v3; // rax
  _BYTE v5[32]; // [rsp+28h] [rbp-20h] BYREF

  v3 = (const struct LKRhash::CLKRLinearHashTable_Iterator *)LKRhash::CLKRLinearHashTable::Begin(a1, v5);
  LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::iterator::iterator(
    a2,
    v3);
  return a2;
}

```

## disassembly

```asm
0x18000fbd4  push    rbx
0x18000fbd6  sub     rsp, 40h
0x18000fbda  mov     rbx, rdx
0x18000fbdd  lea     rdx, [rsp+48h+var_20]
0x18000fbe2  call    ?Begin@CLKRLinearHashTable@LKRhash@@QEAA?AVCLKRLinearHashTable_Iterator@2@XZ; LKRhash::CLKRLinearHashTable::Begin(void)
0x18000fbe7  mov     rdx, rax
0x18000fbea  mov     rcx, rbx
0x18000fbed  call    ??0iterator@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@IEAA@VCLKRLinearHashTable_Iterator@2@@Z; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::iterator::iterator(LKRhash::CLKRLinearHashTable_Iterator)
0x18000fbf2  mov     rax, rbx
0x18000fbf5  add     rsp, 40h
0x18000fbf9  pop     rbx
0x18000fbfa  retn
```
