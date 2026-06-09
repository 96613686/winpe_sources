# FILockInitialize

- ea: `0x140002538`
- end: `0x140002540`
- name: `FILockInitialize`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000f210`
- `0x1400142d0`
- `0x140014730`
- `0x140017510`

## pseudocode

```c
void __fastcall FILockInitialize(_QWORD *a1)
{
  *a1 = 0;
}

```

## disassembly

```asm
0x140002538  mov     qword ptr [rcx], 0
0x14000253f  retn
```
