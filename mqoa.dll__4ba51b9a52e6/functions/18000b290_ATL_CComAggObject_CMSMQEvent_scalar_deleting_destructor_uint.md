# ATL::CComAggObject<CMSMQEvent>::`scalar deleting destructor'(uint)

- ea: `0x18000b290`
- end: `0x18000b2af`
- name: `??_G?$CComAggObject@VCMSMQEvent@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cfa8`
- `0x180011d10`

## callees

- `0x18000178c`
- `0x18000aaf0`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQEvent>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQEvent>::~CComAggObject<CMSMQEvent>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b290  push    rbx
0x18000b292  sub     rsp, 20h
0x18000b296  mov     rbx, rcx
0x18000b299  call    ??1?$CComAggObject@VCMSMQEvent@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQEvent>::~CComAggObject<CMSMQEvent>(void)
0x18000b29e  mov     rcx, rbx; Block
0x18000b2a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b2a6  mov     rax, rbx
0x18000b2a9  add     rsp, 20h
0x18000b2ad  pop     rbx
0x18000b2ae  retn
```
