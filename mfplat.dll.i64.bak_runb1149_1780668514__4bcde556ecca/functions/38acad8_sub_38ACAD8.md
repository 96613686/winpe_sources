# sub_38ACAD8

- ea: `0x38acad8`
- end: `0x38acb06`
- name: `sub_38ACAD8`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_38ACAD8()
{
  __int64 v0; // rbx
  __int64 v1; // rbp
  _QWORD v2[4]; // [rsp-20h] [rbp-30h] BYREF
  __int64 v3; // [rsp+0h] [rbp-10h] BYREF

  v2[3] = &v3;
  v2[2] = v0;
  v2[1] = v1;
  __asm { retn }
}

```

## disassembly

```asm
0x38acad8  or      cl, [rdx]
0x38acada  cmp     eax, 43C32304h
0x38acadf  or      cl, [rax+rsi*2]
0x38acae2  cmp     eax, 45524808h
0x38acae7  push    rbx
0x38acae8  push    rbp
0x38acae9  push    rsp
0x38acaeb  add     ecx, [rdx]
0x38acaed  cmp     eax, 44C32304h
0x38acaf2  or      ah, [rdi]
0x38acaf4  or      cl, [rax+rsi*2]
0x38acaf7  cmp     eax, 45524808h
0x38acafc  push    rbx
0x38acafd  push    rbp
0x38acafe  push    rsp
0x38acb00  add     eax, 23043D0Ah
0x38acb05  retn
```
