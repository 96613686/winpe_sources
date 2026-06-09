# ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::`scalar deleting destructor'(uint)

- ea: `0x180002b28`
- end: `0x180002b47`
- name: `??_G?$CComObjectCached@VMapsBackgroundTransferClassFactory@@@ATL@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(void *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002e00`
- `0x1800031a0`

## callees

- `0x180001e54`
- `0x180002aa4`

## pseudocode

```c
void *__fastcall ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::`scalar deleting destructor'(void *Block)
{
  ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::~CComObjectCached<MapsBackgroundTransferClassFactory>((__int64)Block);
  operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002b28  push    rbx
0x180002b2a  sub     rsp, 20h
0x180002b2e  mov     rbx, rcx
0x180002b31  call    ??1?$CComObjectCached@VMapsBackgroundTransferClassFactory@@@ATL@@QEAA@XZ; ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::~CComObjectCached<MapsBackgroundTransferClassFactory>(void)
0x180002b36  mov     rcx, rbx; Block
0x180002b39  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002b3e  mov     rax, rbx
0x180002b41  add     rsp, 20h
0x180002b45  pop     rbx
0x180002b46  retn
```
