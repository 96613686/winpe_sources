# ATL::CComAggObject<CMSMQQueue>::`scalar deleting destructor'(uint)

- ea: `0x18000b330`
- end: `0x18000b34f`
- name: `??_G?$CComAggObject@VCMSMQQueue@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d38c`
- `0x180011e50`

## callees

- `0x18000178c`
- `0x18000abd8`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQQueue>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQQueue>::~CComAggObject<CMSMQQueue>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b330  push    rbx
0x18000b332  sub     rsp, 20h
0x18000b336  mov     rbx, rcx
0x18000b339  call    ??1?$CComAggObject@VCMSMQQueue@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQQueue>::~CComAggObject<CMSMQQueue>(void)
0x18000b33e  mov     rcx, rbx; Block
0x18000b341  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b346  mov     rax, rbx
0x18000b349  add     rsp, 20h
0x18000b34d  pop     rbx
0x18000b34e  retn
```
