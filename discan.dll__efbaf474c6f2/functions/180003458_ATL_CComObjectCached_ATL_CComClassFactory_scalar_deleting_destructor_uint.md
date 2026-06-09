# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180003458`
- end: `0x180003477`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003910`
- `0x180004e90`

## callees

- `0x180001bc4`
- `0x180003108`

## pseudocode

```c
void *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(void *Block)
{
  ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>((__int64)Block);
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003458  push    rbx
0x18000345a  sub     rsp, 20h
0x18000345e  mov     rbx, rcx
0x180003461  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x180003466  mov     rcx, rbx; Block
0x180003469  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000346e  mov     rax, rbx
0x180003471  add     rsp, 20h
0x180003475  pop     rbx
0x180003476  retn
```
