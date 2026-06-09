# operator new[](unsigned __int64)

- ea: `0x180001318`
- end: `0x18000131d`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(size_t)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180002170`
- `0x1800025d0`
- `0x180002b00`
- `0x180002e80`
- `0x180003158`
- `0x180003a68`
- `0x180003f0c`
- `0x180004370`
- `0x180005ba0`
- `0x1800079f4`
- `0x180007c2c`
- `0x180008890`
- `0x180008dc0`

## callees

- `0x180001098`

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
0x180001318  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
