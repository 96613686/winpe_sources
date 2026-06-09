# operator new[](unsigned __int64)

- ea: `0x18000a71c`
- end: `0x18000a721`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800056a0`
- `0x180006e88`
- `0x180007770`
- `0x18000cbb0`
- `0x18000d54c`
- `0x18000e8a0`
- `0x180011650`
- `0x180014e50`
- `0x180019ea4`
- `0x18001f874`
- `0x1800248f0`
- `0x180028b6c`

## callees

- `0x18000a6dc`

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
0x18000a71c  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
