# _o___stdio_common_vsprintf_s_0

- ea: `0x180015070`
- end: `0x180015076`
- name: `_o___stdio_common_vsprintf_s_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800151e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf_s` at `0x180015070`

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
0x180015070  jmp     cs:__imp__o___stdio_common_vsprintf_s
```
