# operator new[](unsigned __int64)

- ea: `0x1400011f8`
- end: `0x1400011fd`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002308`
- `0x14000370c`

## callees

- `0x140001204`

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
0x1400011f8  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
