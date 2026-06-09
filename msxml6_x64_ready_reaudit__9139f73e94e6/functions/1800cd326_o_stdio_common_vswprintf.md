# _o___stdio_common_vswprintf

- ea: `0x1800cd326`
- end: `0x1800cd32c`
- name: `_o___stdio_common_vswprintf`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800cd3f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x1800cd326`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vswprintf()
{
  return _o___stdio_common_vswprintf();
}

```

## disassembly

```asm
0x1800cd326  jmp     cs:__imp__o___stdio_common_vswprintf
```
