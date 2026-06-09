# VerifyStackAvailable

- ea: `0x180015c4c`
- end: `0x180015c6e`
- name: `VerifyStackAvailable`
- size: `34`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180001550`
- `0x180004454`
- `0x180004c00`
- `0x180006090`
- `0x180009ecc`
- `0x18000fb20`
- `0x180010c90`
- `0x180015490`
- `0x180016e90`
- `0x180017990`
- `0x18001eb38`

## callees

- `0x180015c4c`
- `0x180015c74`
- `0x18001e0e0`

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
0x180015c4c  push    rbx
0x180015c4e  sub     rsp, 20h
0x180015c52  mov     ebx, 1
0x180015c57  call    InternalVerifyStackAvailable
0x180015c5c  jmp     short loc_180015C66
0x180015c5e  xor     ebx, ebx
0x180015c60  call    _resetstkoflw_static
0x180015c65  nop
0x180015c66  mov     eax, ebx
0x180015c68  add     rsp, 20h
0x180015c6c  pop     rbx
0x180015c6d  retn
0x18001f25c  push    rbp
0x18001f25e  sub     rsp, 20h
0x18001f262  mov     rbp, rdx
0x18001f265  mov     rax, [rcx]
0x18001f268  xor     ecx, ecx
0x18001f26a  cmp     dword ptr [rax], 0C00000FDh
0x18001f270  setz    cl
0x18001f273  mov     eax, ecx
0x18001f275  add     rsp, 20h
0x18001f279  pop     rbp
0x18001f27a  retn
```
