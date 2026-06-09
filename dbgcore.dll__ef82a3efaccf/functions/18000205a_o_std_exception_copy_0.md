# _o___std_exception_copy_0

- ea: `0x18000205a`
- end: `0x180002060`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x180003f28`
- `0x180004104`
- `0x18001d738`
- `0x18001d77c`
- `0x1800278e8`
- `0x18002a1e4`
- `0x18002a228`
- `0x18002a284`
- `0x18002a2c8`
- `0x18002a30c`
- `0x18002a368`
- `0x18002a690`
- `0x18002a95c`
- `0x18002a9b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x18000205a`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x18000205a  jmp     cs:__imp__o___std_exception_copy
```
