# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180008db8`
- end: `0x180008dd7`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009f90`
- `0x18000b480`

## callees

- `0x180001240`
- `0x180008cb0`

## pseudocode

```c
void *__fastcall ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(void *Block)
{
  ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>();
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180008db8  push    rbx
0x180008dba  sub     rsp, 20h
0x180008dbe  mov     rbx, rcx
0x180008dc1  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x180008dc6  mov     rcx, rbx; Block
0x180008dc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008dce  mov     rax, rbx
0x180008dd1  add     rsp, 20h
0x180008dd5  pop     rbx
0x180008dd6  retn
```
