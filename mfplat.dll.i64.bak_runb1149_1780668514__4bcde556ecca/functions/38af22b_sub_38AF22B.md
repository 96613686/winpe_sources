# sub_38AF22B

- ea: `0x38af22b`
- end: `0x38af253`
- name: `sub_38AF22B`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_38AF22B()
{
  __int64 v0; // rbx
  __int64 v1; // rbp
  _QWORD v2[4]; // [rsp-20h] [rbp-38h] BYREF
  __int64 v3; // [rsp+0h] [rbp-18h] BYREF

  v2[3] = &v3;
  v2[2] = v0;
  v2[1] = v1;
  __asm { retn }
}

```

## disassembly

```asm
0x38af22b  push    rdi
0x38af22c  or      cl, [rax+rsi*2]
0x38af22f  cmp     eax, 45524808h
0x38af234  push    rbx
0x38af235  push    rbp
0x38af236  push    rsp
0x38af238  add     ecx, [rdx]
0x38af23a  cmp     eax, 62C32304h
0x38af23f  or      ah, [rdi]
0x38af241  or      cl, [rax+rsi*2]
0x38af244  cmp     eax, 45524808h
0x38af249  push    rbx
0x38af24a  push    rbp
0x38af24b  push    rsp
0x38af24d  add     eax, 23043D0Ah
0x38af252  retn
```
