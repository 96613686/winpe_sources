# I8xReadPortUchar

- ea: `0x1400010f0`
- end: `0x1400010f9`
- name: `I8xReadPortUchar`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
unsigned __int8 __fastcall I8xReadPortUchar(unsigned __int16 a1)
{
  return __inbyte(a1);
}

```

## disassembly

```asm
0x1400010f0  xchg    ax, ax
0x1400010f2  nop
0x1400010f3  movzx   edx, cx
0x1400010f6  in      al, dx
0x1400010f7  nop
0x1400010f8  retn
```
