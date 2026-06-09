# operator delete(void *)

- ea: `0x18000a868`
- end: `0x18000a86d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001560`

## callees

- `0x18000a8cc`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  DefaultHeap::Free(a1);
}

```

## disassembly

```asm
0x18000a868  jmp     ?Free@DefaultHeap@@SAXPEAX@Z; DefaultHeap::Free(void *)
```
