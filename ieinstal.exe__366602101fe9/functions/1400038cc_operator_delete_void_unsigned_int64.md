# operator delete(void *,unsigned __int64)

- ea: `0x1400038cc`
- end: `0x1400038d1`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400022d0`
- `0x140002790`
- `0x1400029e0`
- `0x140002fe0`

## callees

- `0x1400039bc`

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
0x1400038cc  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
