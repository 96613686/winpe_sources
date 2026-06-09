# VerifyStackAvailable

- ea: `0x180017a84`
- end: `0x180017aa6`
- name: `VerifyStackAvailable`
- size: `34`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180002900`
- `0x180013b2c`
- `0x180014128`

## callees

- `0x18001792c`
- `0x180017a84`
- `0x180017aac`

## pseudocode

```c
__int64 VerifyStackAvailable()
{
  InternalVerifyStackAvailable();
  return 1;
}

```

## disassembly

```asm
0x180017a84  push    rbx
0x180017a86  sub     rsp, 20h
0x180017a8a  mov     ebx, 1
0x180017a8f  call    InternalVerifyStackAvailable
0x180017a94  jmp     short loc_180017A9E
0x180017a96  xor     ebx, ebx
0x180017a98  call    _resetstkoflw_static
0x180017a9d  nop
0x180017a9e  mov     eax, ebx
0x180017aa0  add     rsp, 20h
0x180017aa4  pop     rbx
0x180017aa5  retn
0x180018c58  push    rbp
0x180018c5a  sub     rsp, 20h
0x180018c5e  mov     rbp, rdx
0x180018c61  mov     rax, [rcx]
0x180018c64  xor     ecx, ecx
0x180018c66  cmp     dword ptr [rax], 0C00000FDh
0x180018c6c  setz    cl
0x180018c6f  mov     eax, ecx
0x180018c71  add     rsp, 20h
0x180018c75  pop     rbp
0x180018c76  retn
```
