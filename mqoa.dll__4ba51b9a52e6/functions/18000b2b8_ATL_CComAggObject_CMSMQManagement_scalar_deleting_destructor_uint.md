# ATL::CComAggObject<CMSMQManagement>::`scalar deleting destructor'(uint)

- ea: `0x18000b2b8`
- end: `0x18000b2d7`
- name: `??_G?$CComAggObject@VCMSMQManagement@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d0c0`
- `0x180011d60`

## callees

- `0x18000178c`
- `0x18000ab18`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQManagement>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQManagement>::~CComAggObject<CMSMQManagement>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b2b8  push    rbx
0x18000b2ba  sub     rsp, 20h
0x18000b2be  mov     rbx, rcx
0x18000b2c1  call    ??1?$CComAggObject@VCMSMQManagement@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQManagement>::~CComAggObject<CMSMQManagement>(void)
0x18000b2c6  mov     rcx, rbx; Block
0x18000b2c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b2ce  mov     rax, rbx
0x18000b2d1  add     rsp, 20h
0x18000b2d5  pop     rbx
0x18000b2d6  retn
```
