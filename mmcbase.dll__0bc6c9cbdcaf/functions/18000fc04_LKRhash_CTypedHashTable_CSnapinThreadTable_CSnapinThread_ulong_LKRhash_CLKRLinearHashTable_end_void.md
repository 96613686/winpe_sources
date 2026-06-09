# LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::end(void)

- ea: `0x18000fc04`
- end: `0x18000fc3b`
- name: `?end@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA?AViterator@12@XZ`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f02c`
- `0x18000f43c`
- `0x18000f8dc`

## callees

- `0x18000ed28`

## pseudocode

```c
LKRhash::CLKRLinearHashTable_Iterator *__fastcall LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::end(
        __int64 a1,
        LKRhash::CLKRLinearHashTable_Iterator *a2)
{
  __int128 v4; // [rsp+28h] [rbp-20h] BYREF
  int v5; // [rsp+38h] [rbp-10h]
  __int16 v6; // [rsp+3Ch] [rbp-Ch]

  v5 = 0;
  v4 = 0;
  v6 = 0;
  LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,unsigned long,LKRhash::CLKRLinearHashTable>::iterator::iterator(
    a2,
    (const struct LKRhash::CLKRLinearHashTable_Iterator *)&v4);
  return a2;
}

```

## disassembly

```asm
0x18000fc04  push    rbx
0x18000fc06  sub     rsp, 40h
0x18000fc0a  mov     rbx, rdx
0x18000fc0d  mov     [rsp+48h+var_10], 0
0x18000fc15  xorps   xmm0, xmm0
0x18000fc18  lea     rdx, [rsp+48h+var_20]
0x18000fc1d  xor     eax, eax
0x18000fc1f  mov     rcx, rbx
0x18000fc22  movdqu  [rsp+48h+var_20], xmm0
0x18000fc28  mov     [rsp+48h+var_C], ax
0x18000fc2d  call    ??0iterator@?$CTypedHashTable@VCSnapinThreadTable@@VCSnapinThread@@KVCLKRLinearHashTable@LKRhash@@@LKRhash@@IEAA@VCLKRLinearHashTable_Iterator@2@@Z; LKRhash::CTypedHashTable<CSnapinThreadTable,CSnapinThread,ulong,LKRhash::CLKRLinearHashTable>::iterator::iterator(LKRhash::CLKRLinearHashTable_Iterator)
0x18000fc32  mov     rax, rbx
0x18000fc35  add     rsp, 40h
0x18000fc39  pop     rbx
0x18000fc3a  retn
```
