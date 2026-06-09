# operator new[](unsigned __int64)

- ea: `0x18000138c`
- end: `0x180001391`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(size_t)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ff0`
- `0x18000f654`
- `0x180011050`
- `0x1800116f8`
- `0x180011fb4`
- `0x180013950`
- `0x180013a50`
- `0x180013c00`
- `0x1800144e8`
- `0x180014b78`
- `0x180015428`
- `0x18001561c`
- `0x180016060`
- `0x1800168b8`
- `0x180016fa8`

## callees

- `0x18000134c`

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
0x18000138c  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
