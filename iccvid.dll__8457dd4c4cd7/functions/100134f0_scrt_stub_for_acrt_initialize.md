# ___scrt_stub_for_acrt_initialize

- ea: `0x100134f0`
- end: `0x100134f3`
- name: `___scrt_stub_for_acrt_initialize`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x10012d15`
- `0x10012d3a`
- `0x10012db2`
- `0x10012dc5`
- `0x10012f57`

## pseudocode

```c
char __scrt_stub_for_acrt_initialize()
{
  return 1;
}

```

## disassembly

```asm
0x100134f0  mov     al, 1
0x100134f2  retn
```
