# operator new[](unsigned __int64)

- ea: `0x180001258`
- end: `0x18000125d`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d68`
- `0x1800046b4`
- `0x18000521c`
- `0x180007430`
- `0x1800082b0`
- `0x180008efc`

## callees

- `0x180001264`

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
0x180001258  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
