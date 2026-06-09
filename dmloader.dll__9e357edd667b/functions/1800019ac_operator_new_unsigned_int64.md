# operator new[](unsigned __int64)

- ea: `0x1800019ac`
- end: `0x1800019b1`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a810`
- `0x18000c14c`
- `0x18000c290`
- `0x18000c494`
- `0x18000e9e4`

## callees

- `0x18000dfa8`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](unsigned __int64 a1)
{
  return operator new(a1);
}

```

## disassembly

```asm
0x1800019ac  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
