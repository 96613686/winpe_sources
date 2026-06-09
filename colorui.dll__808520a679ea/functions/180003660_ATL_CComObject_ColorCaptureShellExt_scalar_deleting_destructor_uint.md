# ATL::CComObject<ColorCaptureShellExt>::`scalar deleting destructor'(uint)

- ea: `0x180003660`
- end: `0x18000368f`
- name: `??_G?$CComObject@VColorCaptureShellExt@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001334`
- `0x180002d08`
- `0x180003660`

## pseudocode

```c
void *__fastcall ATL::CComObject<ColorCaptureShellExt>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<ColorCaptureShellExt>::~CComObject<ColorCaptureShellExt>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003660  mov     [rsp+arg_0], rbx
0x180003665  push    rdi
0x180003666  sub     rsp, 20h
0x18000366a  mov     ebx, edx
0x18000366c  mov     rdi, rcx
0x18000366f  call    ??1?$CComObject@VColorCaptureShellExt@@@ATL@@UEAA@XZ; ATL::CComObject<ColorCaptureShellExt>::~CComObject<ColorCaptureShellExt>(void)
0x180003674  test    bl, 1
0x180003677  jz      short loc_180003681
0x180003679  mov     rcx, rdi; Block
0x18000367c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003681  mov     rbx, [rsp+28h+arg_0]
0x180003686  mov     rax, rdi
0x180003689  add     rsp, 20h
0x18000368d  pop     rdi
0x18000368e  retn
```
