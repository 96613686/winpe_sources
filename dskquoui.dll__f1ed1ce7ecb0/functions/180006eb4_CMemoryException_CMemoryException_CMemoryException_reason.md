# CMemoryException::CMemoryException(CMemoryException::reason)

- ea: `0x180006eb4`
- end: `0x180006eba`
- name: `??0CMemoryException@@QEAA@W4reason@0@@Z`
- size: `6`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180007b58`
- `0x180008aac`
- `0x180009b34`
- `0x18000c8c4`
- `0x180011ed4`
- `0x180011f58`
- `0x180011fdc`
- `0x180012064`
- `0x1800121a4`
- `0x18001270c`
- `0x180014850`
- `0x180014980`
- `0x180015440`
- `0x18001a888`
- `0x18001b8fc`

## pseudocode

```c
_DWORD *__fastcall CMemoryException::CMemoryException(_DWORD *a1, int a2)
{
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x180006eb4  mov     [rcx], edx
0x180006eb6  mov     rax, rcx
0x180006eb9  retn
```
