# ATL::CComObject<ColorPrintShellExt>::`vector deleting destructor'(uint)

- ea: `0x180003740`
- end: `0x18000376f`
- name: `??_E?$CComObject@VColorPrintShellExt@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001334`
- `0x180002de8`
- `0x180003740`

## pseudocode

```c
void *__fastcall ATL::CComObject<ColorPrintShellExt>::`vector deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<ColorPrintShellExt>::~CComObject<ColorPrintShellExt>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003740  mov     [rsp+arg_0], rbx
0x180003745  push    rdi
0x180003746  sub     rsp, 20h
0x18000374a  mov     ebx, edx
0x18000374c  mov     rdi, rcx
0x18000374f  call    ??1?$CComObject@VColorPrintShellExt@@@ATL@@UEAA@XZ; ATL::CComObject<ColorPrintShellExt>::~CComObject<ColorPrintShellExt>(void)
0x180003754  test    bl, 1
0x180003757  jz      short loc_180003761
0x180003759  mov     rcx, rdi; Block
0x18000375c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003761  mov     rbx, [rsp+28h+arg_0]
0x180003766  mov     rax, rdi
0x180003769  add     rsp, 20h
0x18000376d  pop     rdi
0x18000376e  retn
```
