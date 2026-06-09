# ATL::CComAggObject<CMSMQMessage>::`scalar deleting destructor'(uint)

- ea: `0x18000b2e0`
- end: `0x18000b2ff`
- name: `??_G?$CComAggObject@VCMSMQMessage@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d1bc`
- `0x180011db0`

## callees

- `0x18000178c`
- `0x18000ab58`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQMessage>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQMessage>::~CComAggObject<CMSMQMessage>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b2e0  push    rbx
0x18000b2e2  sub     rsp, 20h
0x18000b2e6  mov     rbx, rcx
0x18000b2e9  call    ??1?$CComAggObject@VCMSMQMessage@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQMessage>::~CComAggObject<CMSMQMessage>(void)
0x18000b2ee  mov     rcx, rbx; Block
0x18000b2f1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b2f6  mov     rax, rbx
0x18000b2f9  add     rsp, 20h
0x18000b2fd  pop     rbx
0x18000b2fe  retn
```
