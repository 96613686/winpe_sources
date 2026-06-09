# VerifyStackAvailable

- ea: `0x180009160`
- end: `0x180009182`
- name: `VerifyStackAvailable`
- size: `34`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `3`
- tags: ``

## callers

- `0x180006b60`
- `0x180008b80`
- `0x1800091e0`
- `0x18000d6cc`
- `0x18000da9c`
- `0x18000fc08`
- `0x1800105e0`
- `0x180011630`
- `0x18001edb0`
- `0x18001f5cc`
- `0x18001fb58`
- `0x18001fd90`
- `0x18002032c`

## callees

- `0x180009160`
- `0x180009190`
- `0x180024d64`

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
0x180009160  push    rbx
0x180009162  sub     rsp, 20h
0x180009166  mov     ebx, 1
0x18000916b  call    InternalVerifyStackAvailable
0x180009170  jmp     short loc_18000917A
0x180009172  xor     ebx, ebx
0x180009174  call    _resetstkoflw_static
0x180009179  nop
0x18000917a  mov     eax, ebx
0x18000917c  add     rsp, 20h
0x180009180  pop     rbx
0x180009181  retn
0x180025b70  push    rbp
0x180025b72  sub     rsp, 20h
0x180025b76  mov     rbp, rdx
0x180025b79  mov     rax, [rcx]
0x180025b7c  xor     ecx, ecx
0x180025b7e  cmp     dword ptr [rax], 0C00000FDh
0x180025b84  setz    cl
0x180025b87  mov     eax, ecx
0x180025b89  add     rsp, 20h
0x180025b8d  pop     rbp
0x180025b8e  retn
```
