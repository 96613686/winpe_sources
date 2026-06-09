# sub_38DDD89

- ea: `0x38ddd89`
- end: `0x38dddd0`
- name: `sub_38DDD89`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_38DDD89()
{
  __int64 v0; // rbx
  __int64 v1; // rbp
  _QWORD v3[3]; // [rsp-40h] [rbp-40h] BYREF
  _QWORD v4[3]; // [rsp-28h] [rbp-28h] BYREF
  _QWORD v5[2]; // [rsp-10h] [rbp-10h] BYREF

  BYTE1(v0) |= MEMORY[0x51110093];
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
0x38ddd89  or      bh, cs:51110093h
0x38ddd8f  or      cl, [rax+rsi*2]
0x38ddd92  cmp     eax, 45524808h
0x38ddd97  push    rbx
0x38ddd98  push    rbp
0x38ddd99  push    rsp
0x38ddd9b  add     ecx, [rdx]
0x38ddd9d  cmp     eax, 6FCB2304h
0x38ddda2  or      ah, [rdi]
0x38ddda4  or      cl, [rax+rsi*2]
0x38ddda7  cmp     eax, 45524808h
0x38dddac  push    rbx
0x38dddad  push    rbp
0x38dddae  push    rsp
0x38dddb0  add     ecx, [rdx]
0x38dddb2  cmp     eax, 6FCB2304h
0x38dddb7  or      cl, [rdx]
0x38dddb9  cmp     eax, 73CB2304h
0x38dddbe  or      cl, [rax+rsi*2]
0x38dddc1  cmp     eax, 45524808h
0x38dddc6  push    rbx
0x38dddc7  push    rbp
0x38dddc8  push    rsp
0x38dddca  add     eax, 23043D0Ah
0x38dddcf  retf
```
