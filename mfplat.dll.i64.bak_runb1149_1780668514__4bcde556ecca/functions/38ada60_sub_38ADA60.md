# sub_38ADA60

- ea: `0x38ada60`
- end: `0x38adaa4`
- name: `sub_38ADA60`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_38ADA60()
{
  __int64 v0; // rbx
  __int64 v1; // rbp
  _QWORD v2[4]; // [rsp-38h] [rbp-48h] BYREF
  _QWORD v3[3]; // [rsp-18h] [rbp-28h] BYREF
  __int64 v4; // [rsp+0h] [rbp-10h] BYREF

  v3[2] = &v4;
  v3[1] = v0;
  v3[0] = v1;
  v2[3] = v3;
  v2[2] = v0;
  v2[1] = v1;
  __asm { retn }
}

```

## disassembly

```asm
0x38ada60  and     eax, ebx
0x38ada62  or      cl, [r8+rsi*2]
0x38ada66  cmp     eax, 45524808h
0x38ada6b  push    rbx
0x38ada6c  push    rbp
0x38ada6d  push    rsp
0x38ada6f  add     ecx, [rdx]
0x38ada71  cmp     eax, 4BC32304h
0x38ada76  or      ah, [rdi]
0x38ada78  or      cl, [rax+rsi*2]
0x38ada7b  cmp     eax, 45524808h
0x38ada80  push    rbx
0x38ada81  push    rbp
0x38ada82  push    rsp
0x38ada84  add     ecx, [rdx]
0x38ada86  cmp     eax, 4BC32304h
0x38ada8b  or      cl, [rdx]
0x38ada8d  cmp     eax, 4FC32304h
0x38ada92  or      cl, [rax+rsi*2]
0x38ada95  cmp     eax, 45524808h
0x38ada9a  push    rbx
0x38ada9b  push    rbp
0x38ada9c  push    rsp
0x38ada9e  add     eax, 23043D0Ah
0x38adaa3  retn
```
