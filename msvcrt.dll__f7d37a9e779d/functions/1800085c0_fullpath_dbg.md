# _fullpath_dbg

- ea: `0x1800085c0`
- end: `0x1800085c5`
- name: `_fullpath_dbg`
- size: `5`
- prototype: `char *__cdecl(char *Buffer, const char *Path, size_t BufferCount)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800084a0`

## pseudocode

```c
// attributes: thunk
char *__cdecl fullpath_dbg(char *Buffer, const char *Path, size_t BufferCount)
{
  return fullpath(Buffer, Path, BufferCount);
}

```

## disassembly

```asm
0x1800085c0  jmp     _fullpath
```
