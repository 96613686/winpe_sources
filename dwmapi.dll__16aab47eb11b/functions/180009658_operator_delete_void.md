# operator delete(void *)

- ea: `0x180009658`
- end: `0x18000965d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009340`
- `0x18000d470`
- `0x1800117a4`
- `0x180011800`

## callees

- `0x18000c748`

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
0x180009658  jmp     ?Free@DefaultHeap@@SAXPEAX@Z; DefaultHeap::Free(void *)
```
