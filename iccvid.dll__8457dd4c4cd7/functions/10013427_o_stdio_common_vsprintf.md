# __o___stdio_common_vsprintf

- ea: `0x10013427`
- end: `0x1001342d`
- name: `__o___stdio_common_vsprintf`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x10013493`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf` at `0x10013427`

## pseudocode

```c
// attributes: thunk
int _o___stdio_common_vsprintf()
{
  return __o___stdio_common_vsprintf();
}

```

## disassembly

```asm
0x10013427  jmp     ds:__imp___o___stdio_common_vsprintf
```
