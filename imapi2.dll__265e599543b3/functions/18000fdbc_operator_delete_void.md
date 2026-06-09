# operator delete[](void *)

- ea: `0x18000fdbc`
- end: `0x18000fdc1`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000fc4c`
- `0x1800112ec`
- `0x180011bcc`
- `0x180016a30`
- `0x180016a84`
- `0x1800173b0`
- `0x18003c2b0`
- `0x18003fdb4`
- `0x180042494`
- `0x1800424e4`
- `0x180044cb4`

## callees

- `0x18000fdb0`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x18000fdbc  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
