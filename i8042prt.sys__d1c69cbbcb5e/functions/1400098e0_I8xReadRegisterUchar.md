# I8xReadRegisterUchar

- ea: `0x1400098e0`
- end: `0x1400098e6`
- name: `I8xReadRegisterUchar`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall I8xReadRegisterUchar(__int64 a1)
{
  return *(_BYTE *)a1;
}

```

## disassembly

```asm
0x1400098e0  xchg    ax, ax
0x1400098e2  nop
0x1400098e3  mov     al, [rcx]
0x1400098e5  retn
```
