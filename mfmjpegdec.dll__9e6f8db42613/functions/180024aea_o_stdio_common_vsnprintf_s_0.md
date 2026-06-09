# _o___stdio_common_vsnprintf_s_0

- ea: `0x180024aea`
- end: `0x180024af0`
- name: `_o___stdio_common_vsnprintf_s_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180024cb4`
- `0x180024d14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsnprintf_s` at `0x180024aea`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vsnprintf_s_0()
{
  return _o___stdio_common_vsnprintf_s();
}

```

## disassembly

```asm
0x180024aea  jmp     cs:__imp__o___stdio_common_vsnprintf_s
```
