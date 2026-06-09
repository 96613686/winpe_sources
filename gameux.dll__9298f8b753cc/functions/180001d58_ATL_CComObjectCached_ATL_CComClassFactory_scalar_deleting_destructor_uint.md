# ATL::CComObjectCached<ATL::CComClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180001d58`
- end: `0x180001d77`
- name: `??_G?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002110`
- `0x180002480`

## callees

- `0x18000125c`
- `0x180001c9c`

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
0x180001d58  push    rbx
0x180001d5a  sub     rsp, 20h
0x180001d5e  mov     rbx, rcx
0x180001d61  call    ??1?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectCached<ATL::CComClassFactory>::~CComObjectCached<ATL::CComClassFactory>(void)
0x180001d66  mov     rcx, rbx; Block
0x180001d69  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d6e  mov     rax, rbx
0x180001d71  add     rsp, 20h
0x180001d75  pop     rbx
0x180001d76  retn
```
