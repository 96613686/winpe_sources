# DOSFileDelete(x)

- ea: `0x1000b5f0`
- end: `0x1000b5f5`
- name: `_DOSFileDelete@4`
- size: `5`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1000cbf0`
- `0x1000dfa0`
- `0x1000fc70`
- `0x100113f0`
- `0x10012e70`
- `0x100133f0`
- `0x1001c140`
- `0x1001ede0`
- `0x1001efc0`

## callees

- `0x1002aa10`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall DOSFileDelete(LPCWSTR lpFileName)
{
  return JetDeleteFileW(lpFileName);
}

```

## disassembly

```asm
0x1000b5f0  jmp     _JetDeleteFileW@4; JetDeleteFileW(x)
```
