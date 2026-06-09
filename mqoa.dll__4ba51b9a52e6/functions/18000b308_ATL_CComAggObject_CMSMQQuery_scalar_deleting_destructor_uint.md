# ATL::CComAggObject<CMSMQQuery>::`scalar deleting destructor'(uint)

- ea: `0x18000b308`
- end: `0x18000b327`
- name: `??_G?$CComAggObject@VCMSMQQuery@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d2a4`
- `0x180011e00`

## callees

- `0x18000178c`
- `0x18000ab98`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQQuery>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQQuery>::~CComAggObject<CMSMQQuery>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b308  push    rbx
0x18000b30a  sub     rsp, 20h
0x18000b30e  mov     rbx, rcx
0x18000b311  call    ??1?$CComAggObject@VCMSMQQuery@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQQuery>::~CComAggObject<CMSMQQuery>(void)
0x18000b316  mov     rcx, rbx; Block
0x18000b319  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b31e  mov     rax, rbx
0x18000b321  add     rsp, 20h
0x18000b325  pop     rbx
0x18000b326  retn
```
