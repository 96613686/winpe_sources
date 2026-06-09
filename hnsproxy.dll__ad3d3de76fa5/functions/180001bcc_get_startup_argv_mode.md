# _get_startup_argv_mode

- ea: `0x180001bcc`
- end: `0x180001bd2`
- name: `_get_startup_argv_mode`
- size: `6`
- prototype: `_crt_argv_mode __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000156c`

## pseudocode

```c
_crt_argv_mode __cdecl get_startup_argv_mode()
{
  return 1;
}

```

## disassembly

```asm
0x180001bcc  mov     eax, 1
0x180001bd1  retn
```
