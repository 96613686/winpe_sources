# _o___std_exception_copy_0

- ea: `0x180002e06`
- end: `0x180002e0c`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180004724`
- `0x180004838`
- `0x180008740`
- `0x180008784`
- `0x18001a3c8`
- `0x18001a848`
- `0x1800226a8`
- `0x1800227b4`
- `0x1800228c8`
- `0x1800229d4`
- `0x180022be8`
- `0x1800283f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002e06`

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
0x180002e06  jmp     cs:__imp__o___std_exception_copy
```
