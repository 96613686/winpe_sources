# I8xWritePortUchar

- ea: `0x140007c00`
- end: `0x140007c0a`
- name: `I8xWritePortUchar`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall I8xWritePortUchar(unsigned __int16 a1, unsigned __int8 a2)
{
  __int64 result; // rax

  result = a2;
  __outbyte(a1, a2);
  return result;
}

```

## disassembly

```asm
0x140007c00  movzx   eax, dl
0x140007c03  nop
0x140007c04  movzx   edx, cx
0x140007c07  out     dx, al
0x140007c08  nop
0x140007c09  retn
```
