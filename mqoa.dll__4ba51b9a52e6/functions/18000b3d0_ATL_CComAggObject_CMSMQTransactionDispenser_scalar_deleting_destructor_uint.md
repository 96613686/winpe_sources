# ATL::CComAggObject<CMSMQTransactionDispenser>::`scalar deleting destructor'(uint)

- ea: `0x18000b3d0`
- end: `0x18000b3ef`
- name: `??_G?$CComAggObject@VCMSMQTransactionDispenser@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d72c`
- `0x180011f90`

## callees

- `0x18000178c`
- `0x18000acd8`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQTransactionDispenser>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQTransactionDispenser>::~CComAggObject<CMSMQTransactionDispenser>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b3d0  push    rbx
0x18000b3d2  sub     rsp, 20h
0x18000b3d6  mov     rbx, rcx
0x18000b3d9  call    ??1?$CComAggObject@VCMSMQTransactionDispenser@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQTransactionDispenser>::~CComAggObject<CMSMQTransactionDispenser>(void)
0x18000b3de  mov     rcx, rbx; Block
0x18000b3e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b3e6  mov     rax, rbx
0x18000b3e9  add     rsp, 20h
0x18000b3ed  pop     rbx
0x18000b3ee  retn
```
