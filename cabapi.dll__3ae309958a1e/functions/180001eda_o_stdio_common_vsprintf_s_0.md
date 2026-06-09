# _o___stdio_common_vsprintf_s_0

- ea: `0x180001eda`
- end: `0x180001ee0`
- name: `_o___stdio_common_vsprintf_s_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002098`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf_s` at `0x180001eda`

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
0x180001eda  jmp     cs:__imp__o___stdio_common_vsprintf_s
```
