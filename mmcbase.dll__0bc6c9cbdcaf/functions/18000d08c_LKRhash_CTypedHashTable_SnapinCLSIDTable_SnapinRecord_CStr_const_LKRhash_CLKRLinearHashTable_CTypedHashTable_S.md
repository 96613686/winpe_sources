# LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>(char const *,double,ulong,ulong,bool,bool,CLKRhashAllocator *)

- ea: `0x18000d08c`
- end: `0x18000d0de`
- name: `??0?$CTypedHashTable@VSnapinCLSIDTable@@VSnapinRecord@@PEBVCStr@@VCLKRLinearHashTable@LKRhash@@@LKRhash@@QEAA@PEBDNKK_N1PEAVCLKRhashAllocator@@@Z`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001f90`

## callees

- `0x180019ba0`

## pseudocode

```c
LKRhash::CLKRLinearHashTable *__fastcall LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>(
        LKRhash::CLKRLinearHashTable *a1,
        __int64 a2,
        double a3)
{
  unsigned int v5; // [rsp+40h] [rbp-28h]
  bool v6; // [rsp+48h] [rbp-20h]
  bool v7; // [rsp+50h] [rbp-18h]
  struct CLKRhashAllocator *v8; // [rsp+58h] [rbp-10h]

  LKRhash::CLKRLinearHashTable::CLKRLinearHashTable(
    a1,
    "string",
    LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::_ExtractKey,
    LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::_CalcKeyHash,
    LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::_EqualKeys,
    (void (*)(const void *, int))CObject::AssertValid,
    a3,
    1u,
    v5,
    v6,
    v7,
    v8);
  return a1;
}

```

## disassembly

```asm
0x18000d08c  push    rbx
0x18000d08e  sub     rsp, 60h
0x18000d092  mov     [rsp+68h+var_30], 1; unsigned int
0x18000d09a  lea     rax, ?AssertValid@CObject@@UEBAXXZ; CObject::AssertValid(void)
0x18000d0a1  movsd   [rsp+68h+var_38], xmm2; double
0x18000d0a7  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VSnapinCLSIDTable@@VSnapinRecord@@PEBVCStr@@VCLKRLinearHashTable@LKRhash@@@LKRhash@@CAK_K@Z; unsigned int (*)(unsigned __int64)
0x18000d0ae  mov     [rsp+68h+var_40], rax; void (*)(const void *, int)
0x18000d0b3  lea     r8, ?_ExtractKey@?$CTypedHashTable@VSnapinCLSIDTable@@VSnapinRecord@@PEBVCStr@@VCLKRLinearHashTable@LKRhash@@@LKRhash@@CA?B_KPEBX@Z; unsigned __int64 (*)(const void *)
0x18000d0ba  lea     rax, ?_EqualKeys@?$CTypedHashTable@VSnapinCLSIDTable@@VSnapinRecord@@PEBVCStr@@VCLKRLinearHashTable@LKRhash@@@LKRhash@@CA_N_K0@Z; LKRhash::CTypedHashTable<SnapinCLSIDTable,SnapinRecord,CStr const *,LKRhash::CLKRLinearHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18000d0c1  mov     rbx, rcx
0x18000d0c4  lea     rdx, aString; "string"
0x18000d0cb  mov     [rsp+68h+var_48], rax; bool (*)(unsigned __int64, unsigned __int64)
0x18000d0d0  call    ??0CLKRLinearHashTable@LKRhash@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N7PEAVCLKRhashAllocator@@@Z; LKRhash::CLKRLinearHashTable::CLKRLinearHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool,bool,CLKRhashAllocator *)
0x18000d0d5  mov     rax, rbx
0x18000d0d8  add     rsp, 60h
0x18000d0dc  pop     rbx
0x18000d0dd  retn
```
