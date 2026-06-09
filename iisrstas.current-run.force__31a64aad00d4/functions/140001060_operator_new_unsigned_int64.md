# operator new[](unsigned __int64)

- ea: `0x140001060`
- end: `0x140001065`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001898`
- `0x140001f74`
- `0x1400023fc`

## callees

- `0x140001014`

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
0x140001060  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
