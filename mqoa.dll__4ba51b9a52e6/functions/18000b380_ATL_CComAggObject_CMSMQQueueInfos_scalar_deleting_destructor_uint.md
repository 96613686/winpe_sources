# ATL::CComAggObject<CMSMQQueueInfos>::`scalar deleting destructor'(uint)

- ea: `0x18000b380`
- end: `0x18000b39f`
- name: `??_G?$CComAggObject@VCMSMQQueueInfos@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d55c`
- `0x180011ef0`

## callees

- `0x18000178c`
- `0x18000ac58`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQQueueInfos>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQQueueInfos>::~CComAggObject<CMSMQQueueInfos>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b380  push    rbx
0x18000b382  sub     rsp, 20h
0x18000b386  mov     rbx, rcx
0x18000b389  call    ??1?$CComAggObject@VCMSMQQueueInfos@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQQueueInfos>::~CComAggObject<CMSMQQueueInfos>(void)
0x18000b38e  mov     rcx, rbx; Block
0x18000b391  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b396  mov     rax, rbx
0x18000b399  add     rsp, 20h
0x18000b39d  pop     rbx
0x18000b39e  retn
```
