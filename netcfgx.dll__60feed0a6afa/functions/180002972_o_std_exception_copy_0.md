# _o___std_exception_copy_0

- ea: `0x180002972`
- end: `0x180002978`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180007bc8`
- `0x180007c10`
- `0x180008154`
- `0x18000c0f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002972`

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
0x180002972  jmp     cs:__imp__o___std_exception_copy
```
