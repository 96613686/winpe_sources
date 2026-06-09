# Common::GenericMap<ushort const *,ushort const *>::GenericMapFree(_RTL_AVL_TABLE *,void *)

- ea: `0x180009c20`
- end: `0x180009c28`
- name: `?GenericMapFree@?$GenericMap@PEBGPEBG@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z`
- size: `8`
- prototype: `RTL_AVL_FREE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`

## pseudocode

```c
void __fastcall Common::GenericMap<unsigned short const *,unsigned short const *>::GenericMapFree(
        struct _RTL_AVL_TABLE *Table,
        PVOID Buffer)
{
  Common::GlobalHeap::Free(Buffer);
}

```

## disassembly

```asm
0x180009c20  mov     rcx, rdx; void *
0x180009c23  jmp     ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
```
