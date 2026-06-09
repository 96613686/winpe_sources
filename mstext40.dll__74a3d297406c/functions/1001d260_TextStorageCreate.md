# TextStorageCreate()

- ea: `0x1001d260`
- end: `0x1001d26b`
- name: `_TextStorageCreate@0`
- size: `11`
- prototype: `_DWORD __stdcall()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10026190`

## callees

- `0x1000b070`

## pseudocode

```c
_DWORD *__stdcall TextStorageCreate()
{
  return MemAllocate(2092);
}

```

## disassembly

```asm
0x1001d260  push    82Ch; Size
0x1001d265  call    _MemAllocate@4; MemAllocate(x)
0x1001d26a  retn
```
