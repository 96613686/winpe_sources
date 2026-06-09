# _o___std_exception_copy_0

- ea: `0x180003222`
- end: `0x180003228`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180004218`
- `0x1800043f4`
- `0x180004460`
- `0x1800044cc`
- `0x180004504`
- `0x180004548`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180003222`

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
0x180003222  jmp     cs:__imp__o___std_exception_copy
```
