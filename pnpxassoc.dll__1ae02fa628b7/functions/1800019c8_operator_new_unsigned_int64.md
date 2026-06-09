# operator new[](unsigned __int64)

- ea: `0x1800019c8`
- end: `0x1800019cd`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800056c8`
- `0x18000a9e8`
- `0x18000bae8`
- `0x18000e104`

## callees

- `0x1800019d4`

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
0x1800019c8  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
