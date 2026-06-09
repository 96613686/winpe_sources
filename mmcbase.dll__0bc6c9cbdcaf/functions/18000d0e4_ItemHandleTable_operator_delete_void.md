# ItemHandleTable::operator delete(void *)

- ea: `0x18000d0e4`
- end: `0x18000d0ec`
- name: `??3ItemHandleTable@@SAXPEAX@Z`
- size: `8`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001b690`
- `0x18001bd3f`

## callees

- `0x180007978`

## pseudocode

```c
void __fastcall ItemHandleTable::operator delete(CHeapFactory *a1)
{
  CHeapFactory::Free(a1, a1);
}

```

## disassembly

```asm
0x18000d0e4  mov     rdx, rcx; void *
0x18000d0e7  jmp     ?Free@CHeapFactory@@QEAAHPEAX@Z; CHeapFactory::Free(void *)
```
