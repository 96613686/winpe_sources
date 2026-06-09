# sub_38DC4DF

- ea: `0x38dc4df`
- end: `0x38dc535`
- name: `sub_38DC4DF`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_38DC4DF()
{
  __int64 v0; // rbx
  __int64 v1; // rbp
  _QWORD v3[3]; // [rsp-40h] [rbp-40h] BYREF
  _QWORD v4[3]; // [rsp-28h] [rbp-28h] BYREF
  _QWORD v5[2]; // [rsp-10h] [rbp-10h] BYREF

  BYTE1(v0) |= MEMORY[0x5E58E7F0];
  v5[1] = v0;
  v4[2] = v5;
  v4[1] = v0;
  v4[0] = v1;
  v3[2] = v4;
  v3[1] = v0;
  v3[0] = v1;
  __asm { retf }
}

```

## disassembly

```asm
0x38dc4df  or      dil, cs:5558E7EAh
0x38dc4e6  or      bh, cs:5E58E7F0h
0x38dc4ec  or      cl, [rdx]
0x38dc4ee  cmp     eax, 52CB2304h
0x38dc4f3  or      cl, [rax+rsi*2]
0x38dc4f6  cmp     eax, 45524808h
0x38dc4fb  push    rbx
0x38dc4fc  push    rbp
0x38dc4fd  push    rsp
0x38dc4ff  add     al, 0Ah
0x38dc501  cmp     eax, 49CB2304h
0x38dc506  or      ah, [rdi]
0x38dc508  or      cl, [rdx]
0x38dc50a  and     cl, [rdx]
0x38dc50c  or      al, 70h
0x38dc50e  cmp     eax, 45524808h
0x38dc513  push    rbx
0x38dc514  push    rbp
0x38dc515  push    rsp
0x38dc517  add     al, 0Ah
0x38dc519  cmp     eax, 49CB2304h
0x38dc51e  or      ah, [rdi]
0x38dc520  or      cl, [rdx]
0x38dc522  and     cl, [rdx]
0x38dc524  or      al, 70h
0x38dc526  cmp     eax, 45524808h
0x38dc52b  push    rbx
0x38dc52c  push    rbp
0x38dc52d  push    rsp
0x38dc52f  add     eax, 23043D0Ah
0x38dc534  retf
```
