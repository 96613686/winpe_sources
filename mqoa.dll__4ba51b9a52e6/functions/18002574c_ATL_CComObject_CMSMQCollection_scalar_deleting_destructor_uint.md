# ATL::CComObject<CMSMQCollection>::`scalar deleting destructor'(uint)

- ea: `0x18002574c`
- end: `0x18002576b`
- name: `??_G?$CComObject@VCMSMQCollection@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025910`
- `0x180025f18`
- `0x180026140`

## callees

- `0x18000178c`
- `0x180025620`

## pseudocode

```c
CMSMQCollection *__fastcall ATL::CComObject<CMSMQCollection>::`scalar deleting destructor'(CMSMQCollection *Block)
{
  ATL::CComObject<CMSMQCollection>::~CComObject<CMSMQCollection>(Block);
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18002574c  push    rbx
0x18002574e  sub     rsp, 20h
0x180025752  mov     rbx, rcx
0x180025755  call    ??1?$CComObject@VCMSMQCollection@@@ATL@@QEAA@XZ; ATL::CComObject<CMSMQCollection>::~CComObject<CMSMQCollection>(void)
0x18002575a  mov     rcx, rbx; Block
0x18002575d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180025762  mov     rax, rbx
0x180025765  add     rsp, 20h
0x180025769  pop     rbx
0x18002576a  retn
```
