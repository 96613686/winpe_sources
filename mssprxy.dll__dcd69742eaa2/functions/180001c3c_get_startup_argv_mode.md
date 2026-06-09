# _get_startup_argv_mode

- ea: `0x180001c3c`
- end: `0x180001c42`
- name: `_get_startup_argv_mode`
- size: `6`
- prototype: `_crt_argv_mode __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015dc`

## pseudocode

```c
_crt_argv_mode __cdecl get_startup_argv_mode()
{
  return 1;
}

```

## disassembly

```asm
0x180001c3c  mov     eax, 1
0x180001c41  retn
```
