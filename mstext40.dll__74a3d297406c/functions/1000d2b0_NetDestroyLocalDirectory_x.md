# NetDestroyLocalDirectory(x)

- ea: `0x1000d2b0`
- end: `0x1000d2b5`
- name: `_NetDestroyLocalDirectory@4`
- size: `5`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x10010450`
- `0x10011d90`

## callees

- `0x1000ba60`

## pseudocode

```c
// attributes: thunk
int __stdcall NetDestroyLocalDirectory(const WCHAR *a1)
{
  return DOSRemoveDirectory(a1);
}

```

## disassembly

```asm
0x1000d2b0  jmp     _DOSRemoveDirectory@4; DOSRemoveDirectory(x)
```
