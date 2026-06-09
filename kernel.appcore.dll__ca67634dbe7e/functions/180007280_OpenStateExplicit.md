# OpenStateExplicit

- ea: `0x180007280`
- end: `0x180007286`
- name: `OpenStateExplicit`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!OpenStateExplicit` at `0x180007280`

## pseudocode

```c
// attributes: thunk
__int64 OpenStateExplicit()
{
  return __imp_OpenStateExplicit();
}

```

## disassembly

```asm
0x180007280  jmp     cs:__imp_OpenStateExplicit
```
