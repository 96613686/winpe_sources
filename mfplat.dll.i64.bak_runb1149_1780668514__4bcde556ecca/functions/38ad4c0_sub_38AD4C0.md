# sub_38AD4C0

- ea: `0x38ad4c0`
- end: `0x38ad4ed`
- name: `sub_38AD4C0`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_38AD4C0()
{
  __int64 v0; // rbx
  __int64 v1; // rbp
  _QWORD v2[4]; // [rsp-30h] [rbp-30h] BYREF
  _QWORD v3[2]; // [rsp-10h] [rbp-10h] BYREF

  BYTE1(v0) |= MEMORY[0x4D4DF7CA];
  v3[1] = v0;
  v2[3] = v3;
  v2[2] = v0;
  v2[1] = v1;
  __asm { retn }
}

```

## disassembly

```asm
0x38ad4c0  or      bh, cs:4D4DF7CAh
0x38ad4c6  or      cl, [rax+rsi*2]
0x38ad4c9  cmp     eax, 45524808h
0x38ad4ce  push    rbx
0x38ad4cf  push    rbp
0x38ad4d0  push    rsp
0x38ad4d2  add     ecx, [rdx]
0x38ad4d4  cmp     eax, 4CC32304h
0x38ad4d9  or      ah, [rdi]
0x38ad4db  or      cl, [rax+rsi*2]
0x38ad4de  cmp     eax, 45524808h
0x38ad4e3  push    rbx
0x38ad4e4  push    rbp
0x38ad4e5  push    rsp
0x38ad4e7  add     eax, 23043D0Ah
0x38ad4ec  retn
```
