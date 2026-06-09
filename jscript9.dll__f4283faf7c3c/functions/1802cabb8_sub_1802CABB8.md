# sub_1802CABB8

- ea: `0x1802cabb8`
- end: `0x1802cac28`
- name: `sub_1802CABB8`
- size: `112`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1801b7960`
- `0x1801b9f68`
- `0x1802c8b9c`

## callees

- `0x180107364`

## import_xrefs

- `KERNEL32!SetThreadStackGuarantee` at `0x1802cabf3`
- `KERNEL32!SetThreadStackGuarantee` at `0x1802cabf3`
- `KERNEL32!TlsSetValue` at `0x1802cac14`
- `KERNEL32!TlsSetValue` at `0x1802cac14`

## pseudocode

```c
_QWORD *sub_1802CABB8()
{
  __int64 v0; // rax
  char *DeallocationStack; // rbx
  _QWORD *v2; // rdi
  ULONG StackSizeInBytes[6]; // [rsp+20h] [rbp-18h] BYREF

  v0 = sub_180107364(16, byte_18043C6AB, sub_180186320);
  StackSizeInBytes[0] = 0;
  DeallocationStack = (char *)NtCurrentTeb()->DeallocationStack;
  v2 = (_QWORD *)v0;
  SetThreadStackGuarantee(StackSizeInBytes);
  v2[1] = &DeallocationStack[StackSizeInBytes[0] + 49152];
  TlsSetValue(dwTlsIndex, v2);
  return v2;
}

```

## disassembly

```asm
0x1802cabb8  mov     [rsp+arg_0], rbx
0x1802cabbd  push    rdi
0x1802cabbe  sub     rsp, 30h
0x1802cabc2  lea     r8, sub_180186320
0x1802cabc9  mov     ecx, 10h
0x1802cabce  lea     rdx, byte_18043C6AB
0x1802cabd5  call    sub_180107364
0x1802cabda  mov     [rsp+38h+StackSizeInBytes], 0
0x1802cabe2  lea     rcx, [rsp+38h+StackSizeInBytes]; StackSizeInBytes
0x1802cabe7  mov     rbx, gs:1478h
0x1802cabf0  mov     rdi, rax
0x1802cabf3  call    cs:SetThreadStackGuarantee
0x1802cabf9  mov     ecx, [rsp+38h+StackSizeInBytes]
0x1802cabfd  lea     rdx, [rbx+0C000h]
0x1802cac04  add     rdx, rcx
0x1802cac07  mov     [rdi+8], rdx
0x1802cac0b  mov     rdx, rdi; lpTlsValue
0x1802cac0e  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1802cac14  call    cs:TlsSetValue
0x1802cac1a  mov     rbx, [rsp+38h+arg_0]
0x1802cac1f  mov     rax, rdi
0x1802cac22  add     rsp, 30h
0x1802cac26  pop     rdi
0x1802cac27  retn
```
