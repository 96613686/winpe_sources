# _o___std_exception_copy_0

- ea: `0x1400029a2`
- end: `0x1400029a8`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1400039e0`
- `0x140003af4`
- `0x1400155c8`
- `0x14001560c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1400029a2`

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
0x1400029a2  jmp     cs:__imp__o___std_exception_copy
```
