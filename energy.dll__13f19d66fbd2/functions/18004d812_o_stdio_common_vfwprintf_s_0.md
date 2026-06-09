# _o___stdio_common_vfwprintf_s_0

- ea: `0x18004d812`
- end: `0x18004d818`
- name: `_o___stdio_common_vfwprintf_s_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18004d92c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vfwprintf_s` at `0x18004d812`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vfwprintf_s_0()
{
  return _o___stdio_common_vfwprintf_s();
}

```

## disassembly

```asm
0x18004d812  jmp     cs:__imp__o___stdio_common_vfwprintf_s
```
