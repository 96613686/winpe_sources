# ATL::CComAggObject<CMSMQCoordinatedTransactionDispenser>::`scalar deleting destructor'(uint)

- ea: `0x18000b240`
- end: `0x18000b25f`
- name: `??_G?$CComAggObject@VCMSMQCoordinatedTransactionDispenser@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cdcc`
- `0x180011c70`

## callees

- `0x18000178c`
- `0x18000aa70`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQCoordinatedTransactionDispenser>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQCoordinatedTransactionDispenser>::~CComAggObject<CMSMQCoordinatedTransactionDispenser>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b240  push    rbx
0x18000b242  sub     rsp, 20h
0x18000b246  mov     rbx, rcx
0x18000b249  call    ??1?$CComAggObject@VCMSMQCoordinatedTransactionDispenser@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQCoordinatedTransactionDispenser>::~CComAggObject<CMSMQCoordinatedTransactionDispenser>(void)
0x18000b24e  mov     rcx, rbx; Block
0x18000b251  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b256  mov     rax, rbx
0x18000b259  add     rsp, 20h
0x18000b25d  pop     rbx
0x18000b25e  retn
```
