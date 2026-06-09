# operator delete(void *)

- ea: `0x180007c94`
- end: `0x180007c99`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001fc0`
- `0x180001fec`

## callees

- `0x180007d80`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  MemFree(a1);
}

```

## disassembly

```asm
0x180007c94  jmp     ?MemFree@@YAXPEAX@Z; MemFree(void *)
```
