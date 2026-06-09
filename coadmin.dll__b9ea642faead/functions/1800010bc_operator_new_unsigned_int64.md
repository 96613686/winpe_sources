# operator new[](unsigned __int64)

- ea: `0x1800010bc`
- end: `0x1800010c1`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180003590`
- `0x1800063c0`
- `0x1800068d4`
- `0x18000ca70`
- `0x18000cc5c`
- `0x18000cd48`
- `0x18000cdd8`
- `0x18000cfd4`

## callees

- `0x180001064`

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
0x1800010bc  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
