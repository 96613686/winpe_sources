# ATL::CComAggObject<CMSMQQueueInfo>::`scalar deleting destructor'(uint)

- ea: `0x18000b358`
- end: `0x18000b377`
- name: `??_G?$CComAggObject@VCMSMQQueueInfo@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d474`
- `0x180011ea0`

## callees

- `0x18000178c`
- `0x18000ac18`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQQueueInfo>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQQueueInfo>::~CComAggObject<CMSMQQueueInfo>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b358  push    rbx
0x18000b35a  sub     rsp, 20h
0x18000b35e  mov     rbx, rcx
0x18000b361  call    ??1?$CComAggObject@VCMSMQQueueInfo@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQQueueInfo>::~CComAggObject<CMSMQQueueInfo>(void)
0x18000b366  mov     rcx, rbx; Block
0x18000b369  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b36e  mov     rax, rbx
0x18000b371  add     rsp, 20h
0x18000b375  pop     rbx
0x18000b376  retn
```
