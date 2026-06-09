# DetourTransactionCommit

- ea: `0x1400029d0`
- end: `0x1400029d7`
- name: `DetourTransactionCommit`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d36c`
- `0x14000d4f0`

## callees

- `0x1400029e0`

## pseudocode

```c
__int64 DetourTransactionCommit()
{
  return DetourTransactionCommitEx(0);
}

```

## disassembly

```asm
0x1400029d0  xor     ecx, ecx
0x1400029d2  jmp     DetourTransactionCommitEx
```
