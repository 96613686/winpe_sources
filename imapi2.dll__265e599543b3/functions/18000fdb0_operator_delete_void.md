# operator delete(void *)

- ea: `0x18000fdb0`
- end: `0x18000fdb5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `45`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180008e20`
- `0x180008e60`
- `0x18000b990`
- `0x18000e9a0`
- `0x18000ef44`
- `0x18000f5f0`
- `0x18000fdbc`
- `0x180011170`
- `0x1800111b0`
- `0x1800111e8`
- `0x180011210`
- `0x180014780`
- `0x1800147c0`
- `0x1800156d0`
- `0x180015710`
- `0x1800160c0`
- `0x180016100`
- `0x180016cc0`
- `0x180016d00`
- `0x180016d40`
- `0x180016d80`
- `0x180016dc0`
- `0x180016e00`
- `0x1800171ac`
- `0x180024fe0`
- `0x180025508`
- `0x180028000`
- `0x180028ce0`
- `0x18002d830`
- `0x18002d870`
- `0x180032700`
- `0x180035e60`
- `0x180035ee0`
- `0x180035f60`
- `0x180036960`
- `0x1800369a0`
- `0x18003c2f0`
- `0x18003c330`
- `0x18003c370`
- `0x18003fc60`
- `0x18003fd24`
- `0x1800417c0`
- `0x180041824`
- `0x180042590`
- `0x180049df4`

## callees

- `0x18001031e`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x18000fdb0  jmp     free_0
```
