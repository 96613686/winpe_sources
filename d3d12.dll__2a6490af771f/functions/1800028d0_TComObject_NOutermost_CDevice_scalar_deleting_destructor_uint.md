# TComObject<NOutermost::CDevice>::`scalar deleting destructor'(uint)

- ea: `0x1800028d0`
- end: `0x180002906`
- name: `??_G?$TComObject@VCDevice@NOutermost@@@@UEAAPEAXI@Z`
- size: `54`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800028d0`
- `0x18000290c`
- `0x18000b7e0`

## pseudocode

```c
void *__fastcall TComObject<NOutermost::CDevice>::`scalar deleting destructor'(void *Block, char a2)
{
  TComObject<NOutermost::CDevice>::~TComObject<NOutermost::CDevice>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800028d0  mov     [rsp+arg_0], rbx
0x1800028d5  push    rdi
0x1800028d6  sub     rsp, 20h
0x1800028da  mov     ebx, edx
0x1800028dc  mov     rdi, rcx
0x1800028df  call    ??1?$TComObject@VCDevice@NOutermost@@@@UEAA@XZ; TComObject<NOutermost::CDevice>::~TComObject<NOutermost::CDevice>(void)
0x1800028e4  test    bl, 1
0x1800028e7  jnz     short loc_1800028F7
0x1800028e9  mov     rbx, [rsp+28h+arg_0]
0x1800028ee  mov     rax, rdi
0x1800028f1  add     rsp, 20h
0x1800028f5  pop     rdi
0x1800028f6  retn
0x1800028f7  mov     edx, 80h
0x1800028fc  mov     rcx, rdi; Block
0x1800028ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002904  jmp     short loc_1800028E9
```
