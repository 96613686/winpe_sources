# _o___stdio_common_vsprintf_s_0

- ea: `0x140002c3a`
- end: `0x140002c40`
- name: `_o___stdio_common_vsprintf_s_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002e4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf_s` at `0x140002c3a`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vsprintf_s_0()
{
  return _o___stdio_common_vsprintf_s();
}

```

## disassembly

```asm
0x140002c3a  jmp     cs:__imp__o___stdio_common_vsprintf_s
```
