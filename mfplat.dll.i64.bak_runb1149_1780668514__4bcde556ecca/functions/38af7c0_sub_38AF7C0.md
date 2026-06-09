# sub_38AF7C0

- ea: `0x38af7c0`
- end: `0x38af804`
- name: `sub_38AF7C0`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_38AF7C0()
{
  __int64 v0; // rbx
  __int64 v1; // rbp
  _QWORD v2[4]; // [rsp-38h] [rbp-50h] BYREF
  _QWORD v3[3]; // [rsp-18h] [rbp-30h] BYREF
  __int64 v4; // [rsp+0h] [rbp-18h] BYREF

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
0x38af7c0  and     eax, ebx
0x38af7c2  push    rdi
0x38af7c3  or      cl, [rax+rsi*2]
0x38af7c6  cmp     eax, 45524808h
0x38af7cb  push    rbx
0x38af7cc  push    rbp
0x38af7cd  push    rsp
0x38af7cf  add     ecx, [rdx]
0x38af7d1  cmp     eax, 61C32304h
0x38af7d6  or      ah, [rdi]
0x38af7d8  or      cl, [rax+rsi*2]
0x38af7db  cmp     eax, 45524808h
0x38af7e0  push    rbx
0x38af7e1  push    rbp
0x38af7e2  push    rsp
0x38af7e4  add     ecx, [rdx]
0x38af7e6  cmp     eax, 61C32304h
0x38af7eb  or      cl, [rdx]
0x38af7ed  cmp     eax, 65C32304h
0x38af7f2  or      cl, [rax+rsi*2]
0x38af7f5  cmp     eax, 45524808h
0x38af7fa  push    rbx
0x38af7fb  push    rbp
0x38af7fc  push    rsp
0x38af7fe  add     eax, 23043D0Ah
0x38af803  retn
```
