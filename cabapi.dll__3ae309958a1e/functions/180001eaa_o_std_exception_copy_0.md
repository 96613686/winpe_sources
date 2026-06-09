# _o___std_exception_copy_0

- ea: `0x180001eaa`
- end: `0x180001eb0`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800032dc`
- `0x1800033f0`
- `0x180003434`
- `0x1800034a0`
- `0x180007988`
- `0x1800079cc`
- `0x180007a28`
- `0x180007a6c`
- `0x180007ab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001eaa`

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
0x180001eaa  jmp     cs:__imp__o___std_exception_copy
```
