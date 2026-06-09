# operator new[](unsigned __int64)

- ea: `0x180002290`
- end: `0x180002295`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a70`
- `0x180003fa0`

## callees

- `0x180002250`

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
0x180002290  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
