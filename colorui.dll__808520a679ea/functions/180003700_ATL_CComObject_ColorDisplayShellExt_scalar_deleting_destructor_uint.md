# ATL::CComObject<ColorDisplayShellExt>::`scalar deleting destructor'(uint)

- ea: `0x180003700`
- end: `0x18000372f`
- name: `??_G?$CComObject@VColorDisplayShellExt@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001334`
- `0x180002d78`
- `0x180003700`

## pseudocode

```c
void *__fastcall ATL::CComObject<ColorDisplayShellExt>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<ColorDisplayShellExt>::~CComObject<ColorDisplayShellExt>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180003700  mov     [rsp+arg_0], rbx
0x180003705  push    rdi
0x180003706  sub     rsp, 20h
0x18000370a  mov     ebx, edx
0x18000370c  mov     rdi, rcx
0x18000370f  call    ??1?$CComObject@VColorDisplayShellExt@@@ATL@@UEAA@XZ; ATL::CComObject<ColorDisplayShellExt>::~CComObject<ColorDisplayShellExt>(void)
0x180003714  test    bl, 1
0x180003717  jz      short loc_180003721
0x180003719  mov     rcx, rdi; Block
0x18000371c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003721  mov     rbx, [rsp+28h+arg_0]
0x180003726  mov     rax, rdi
0x180003729  add     rsp, 20h
0x18000372d  pop     rdi
0x18000372e  retn
```
