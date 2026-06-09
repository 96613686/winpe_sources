# operator new[](unsigned __int64)

- ea: `0x180001054`
- end: `0x180001059`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800089e8`
- `0x180008c40`
- `0x18000e408`
- `0x18000e83c`
- `0x18000ec68`
- `0x18000f02c`
- `0x18000f298`
- `0x18000f478`
- `0x18000f674`
- `0x18000f908`
- `0x18000fb88`
- `0x18000fd64`
- `0x1800103ac`

## callees

- `0x180001008`

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
0x180001054  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
