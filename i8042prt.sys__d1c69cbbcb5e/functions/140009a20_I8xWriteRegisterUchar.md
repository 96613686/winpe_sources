# I8xWriteRegisterUchar

- ea: `0x140009a20`
- end: `0x140009a28`
- name: `I8xWriteRegisterUchar`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall I8xWriteRegisterUchar(_BYTE *a1, char a2)
{
  _UNKNOWN *retaddr; // [rsp+0h] [rbp+0h] BYREF

  *a1 = a2;
  _InterlockedOr((volatile signed __int32 *)&retaddr, 0);
}

```

## disassembly

```asm
0x140009a20  mov     [rcx], dl
0x140009a22  lock or dword ptr [rsp+0], 0
0x140009a27  retn
```
