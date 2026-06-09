# ScReadNoFence(ulong *)

- ea: `0x14000ae88`
- end: `0x14000ae8b`
- name: `?ScReadNoFence@@YAKPEAK@Z`
- size: `3`
- prototype: `unsigned int __fastcall(unsigned int *)`
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x140002b70`
- `0x140002bd0`
- `0x140003040`
- `0x140005b2c`
- `0x14000a014`
- `0x14000bc88`
- `0x14000c328`
- `0x14001c0e0`
- `0x14001d370`
- `0x14001da78`
- `0x140020550`
- `0x1400206f0`
- `0x140020ba8`
- `0x14002470c`

## pseudocode

```c
__int64 __fastcall ScReadNoFence(unsigned int *a1)
{
  return *a1;
}

```

## disassembly

```asm
0x14000ae88  mov     eax, [rcx]
0x14000ae8a  retn
```
