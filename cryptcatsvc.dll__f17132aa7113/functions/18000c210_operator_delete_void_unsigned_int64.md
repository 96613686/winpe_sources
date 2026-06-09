# operator delete(void *,unsigned __int64)

- ea: `0x18000c210`
- end: `0x18000c215`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006e24`
- `0x18000e000`
- `0x18000e040`
- `0x18000e080`
- `0x18000e0c0`
- `0x180013af0`
- `0x1800145d8`
- `0x1800172c0`
- `0x180017300`
- `0x180017928`
- `0x18001df10`
- `0x18001df60`
- `0x180021a1b`

## callees

- `0x180008c74`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x18000c210  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
