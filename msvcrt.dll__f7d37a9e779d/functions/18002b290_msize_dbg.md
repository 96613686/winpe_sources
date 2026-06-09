# _msize_dbg

- ea: `0x18002b290`
- end: `0x18002b295`
- name: `_msize_dbg`
- size: `5`
- prototype: `size_t __cdecl(void *Block)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001d110`

## pseudocode

```c
// attributes: thunk
size_t __cdecl msize_dbg(void *Block)
{
  return msize(Block);
}

```

## disassembly

```asm
0x18002b290  jmp     _msize
```
