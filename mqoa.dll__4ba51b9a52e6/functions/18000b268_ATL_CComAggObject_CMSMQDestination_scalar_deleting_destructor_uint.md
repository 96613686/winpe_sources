# ATL::CComAggObject<CMSMQDestination>::`scalar deleting destructor'(uint)

- ea: `0x18000b268`
- end: `0x18000b287`
- name: `??_G?$CComAggObject@VCMSMQDestination@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ceb4`
- `0x180011cc0`

## callees

- `0x18000178c`
- `0x18000aab0`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQDestination>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQDestination>::~CComAggObject<CMSMQDestination>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b268  push    rbx
0x18000b26a  sub     rsp, 20h
0x18000b26e  mov     rbx, rcx
0x18000b271  call    ??1?$CComAggObject@VCMSMQDestination@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQDestination>::~CComAggObject<CMSMQDestination>(void)
0x18000b276  mov     rcx, rbx; Block
0x18000b279  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b27e  mov     rax, rbx
0x18000b281  add     rsp, 20h
0x18000b285  pop     rbx
0x18000b286  retn
```
