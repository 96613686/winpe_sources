# operator new[](unsigned __int64)

- ea: `0x1800034f0`
- end: `0x1800034f5`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(size_t)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ee18`
- `0x18000f004`
- `0x180010170`
- `0x180010610`
- `0x180010864`

## callees

- `0x1800034ac`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](size_t a1)
{
  return operator new(a1);
}

```

## disassembly

```asm
0x1800034f0  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
