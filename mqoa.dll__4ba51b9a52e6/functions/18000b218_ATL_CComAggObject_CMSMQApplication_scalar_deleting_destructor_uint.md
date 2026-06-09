# ATL::CComAggObject<CMSMQApplication>::`scalar deleting destructor'(uint)

- ea: `0x18000b218`
- end: `0x18000b237`
- name: `??_G?$CComAggObject@VCMSMQApplication@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cce4`
- `0x180011c20`

## callees

- `0x18000178c`
- `0x18000aa30`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CMSMQApplication>::`scalar deleting destructor'(void *Block)
{
  ATL::CComAggObject<CMSMQApplication>::~CComAggObject<CMSMQApplication>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b218  push    rbx
0x18000b21a  sub     rsp, 20h
0x18000b21e  mov     rbx, rcx
0x18000b221  call    ??1?$CComAggObject@VCMSMQApplication@@@ATL@@QEAA@XZ; ATL::CComAggObject<CMSMQApplication>::~CComAggObject<CMSMQApplication>(void)
0x18000b226  mov     rcx, rbx; Block
0x18000b229  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b22e  mov     rax, rbx
0x18000b231  add     rsp, 20h
0x18000b235  pop     rbx
0x18000b236  retn
```
