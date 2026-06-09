# operator delete(void *,unsigned __int64)

- ea: `0x180001560`
- end: `0x180001565`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003470`
- `0x180005aa0`
- `0x180005ae0`
- `0x18000a6b0`
- `0x18000a7f0`

## callees

- `0x18000a868`

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
0x180001560  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
