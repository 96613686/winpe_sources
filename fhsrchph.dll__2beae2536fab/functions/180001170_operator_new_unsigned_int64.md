# operator new[](unsigned __int64)

- ea: `0x180001170`
- end: `0x180001175`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(size_t)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003414`
- `0x180007d58`
- `0x180007dac`

## callees

- `0x1800011c4`

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
0x180001170  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
