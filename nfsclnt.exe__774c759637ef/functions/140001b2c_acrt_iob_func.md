# __acrt_iob_func

- ea: `0x140001b2c`
- end: `0x140001b4a`
- name: `__acrt_iob_func`
- size: `30`
- prototype: `FILE *__cdecl(unsigned int Ix)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000add4`
- `0x14000b4d8`
- `0x14000b6c8`
- `0x14000d454`
- `0x14000d710`
- `0x14000dcf0`
- `0x14000e9e4`
- `0x14000ee24`

## callees

- `0x140001b50`

## pseudocode

```c
FILE *__cdecl _acrt_iob_func(unsigned int Ix)
{
  return &_iob_func_0()[Ix];
}

```

## disassembly

```asm
0x140001b2c  push    rbx
0x140001b2e  sub     rsp, 20h
0x140001b32  mov     ebx, ecx
0x140001b34  call    __iob_func_0
0x140001b39  lea     rdx, [rbx+rbx*2]
0x140001b3d  shl     rdx, 4
0x140001b41  add     rax, rdx
0x140001b44  add     rsp, 20h
0x140001b48  pop     rbx
0x140001b49  retn
```
