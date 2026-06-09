# _get_startup_file_mode

- ea: `0x1400016a8`
- end: `0x1400016ae`
- name: `_get_startup_file_mode`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001090`

## pseudocode

```c
__int64 get_startup_file_mode()
{
  return 0x4000;
}

```

## disassembly

```asm
0x1400016a8  mov     eax, 4000h
0x1400016ad  retn
```
