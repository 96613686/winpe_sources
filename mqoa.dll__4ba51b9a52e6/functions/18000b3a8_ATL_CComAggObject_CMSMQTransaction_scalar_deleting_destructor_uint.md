# ATL::CComAggObject<CMSMQTransaction>::`scalar deleting destructor'(uint)

- ea: `0x18000b3a8`
- end: `0x18000b3c7`
- name: `??_G?$CComAggObject@VCMSMQTransaction@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d644`
- `0x180011f40`

## callees

- `0x18000178c`
- `0x18000ac98`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQTransaction>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQTransaction>::~CComAggObject<CMSMQTransaction>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b3a8  push    rbx
0x18000b3aa  sub     rsp, 20h
0x18000b3ae  mov     rbx, rcx
0x18000b3b1  call    ??1?$CComAggObject@VCMSMQTransaction@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQTransaction>::~CComAggObject<CMSMQTransaction>(void)
0x18000b3b6  mov     rcx, rbx; Block
0x18000b3b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b3be  mov     rax, rbx
0x18000b3c1  add     rsp, 20h
0x18000b3c5  pop     rbx
0x18000b3c6  retn
```
