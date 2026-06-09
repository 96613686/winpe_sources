# operator new[](unsigned __int64)

- ea: `0x180001014`
- end: `0x180001019`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180002254`
- `0x180003604`
- `0x180003a04`
- `0x180003c8c`

## callees

- `0x18000102c`

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
0x180001014  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
