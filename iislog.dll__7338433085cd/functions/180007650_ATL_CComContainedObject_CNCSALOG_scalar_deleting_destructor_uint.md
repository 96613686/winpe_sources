# ATL::CComContainedObject<CNCSALOG>::`scalar deleting destructor'(uint)

- ea: `0x180007650`
- end: `0x18000767f`
- name: `??_G?$CComContainedObject@VCNCSALOG@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007630`

## callees

- `0x180001048`
- `0x1800075f4`
- `0x180007650`

## pseudocode

```c
CNCSALOG *__fastcall ATL::CComContainedObject<CNCSALOG>::`scalar deleting destructor'(CNCSALOG *Block, char a2)
{
  CNCSALOG::~CNCSALOG(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007650  mov     [rsp+arg_0], rbx
0x180007655  push    rdi
0x180007656  sub     rsp, 20h
0x18000765a  mov     ebx, edx
0x18000765c  mov     rdi, rcx
0x18000765f  call    ??1CNCSALOG@@MEAA@XZ; CNCSALOG::~CNCSALOG(void)
0x180007664  test    bl, 1
0x180007667  jz      short loc_180007671
0x180007669  mov     rcx, rdi; Block
0x18000766c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007671  mov     rbx, [rsp+28h+arg_0]
0x180007676  mov     rax, rdi
0x180007679  add     rsp, 20h
0x18000767d  pop     rdi
0x18000767e  retn
```
