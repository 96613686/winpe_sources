# sub_38DEB20

- ea: `0x38deb20`
- end: `0x38deb4c`
- name: `sub_38DEB20`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_38DEB20()
{
  __int64 v0; // rbx
  __int64 v1; // rbp
  _QWORD v3[3]; // [rsp-18h] [rbp-28h] BYREF
  __int64 v4; // [rsp+0h] [rbp-10h] BYREF

  v3[2] = &v4;
  v3[1] = v0;
  v3[0] = v1;
  __asm { retf }
}

```

## disassembly

```asm
0x38deb20  cmp     eax, 79CB2304h
0x38deb25  or      cl, [rax+rsi*2]
0x38deb28  cmp     eax, 45524808h
0x38deb2d  push    rbx
0x38deb2e  push    rbp
0x38deb2f  push    rsp
0x38deb31  add     ecx, [rdx]
0x38deb33  cmp     eax, 7CCB2304h
0x38deb38  or      ah, [rdi]
0x38deb3a  or      cl, [rax+rsi*2]
0x38deb3d  cmp     eax, 45524808h
0x38deb42  push    rbx
0x38deb43  push    rbp
0x38deb44  push    rsp
0x38deb46  add     eax, 23043D0Ah
0x38deb4b  retf
```
