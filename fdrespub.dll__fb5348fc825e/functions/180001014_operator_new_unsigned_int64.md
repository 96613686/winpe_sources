# operator new[](unsigned __int64)

- ea: `0x180001014`
- end: `0x180001019`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(size_t)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020f8`
- `0x1800022b4`
- `0x180002bc0`
- `0x180002f24`
- `0x180003ae8`
- `0x180004498`
- `0x1800047f8`

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
