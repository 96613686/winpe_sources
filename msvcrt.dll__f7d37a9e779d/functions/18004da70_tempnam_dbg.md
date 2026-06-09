# _tempnam_dbg

- ea: `0x18004da70`
- end: `0x18004da75`
- name: `_tempnam_dbg`
- size: `5`
- prototype: `char *__cdecl(const char *DirectoryName, const char *FilePrefix)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18004d7a0`

## pseudocode

```c
// attributes: thunk
char *__cdecl tempnam_dbg(const char *DirectoryName, const char *FilePrefix)
{
  return tempnam(DirectoryName, FilePrefix);
}

```

## disassembly

```asm
0x18004da70  jmp     _tempnam
```
