# operator delete[](void *)

- ea: `0x1003a6f2`
- end: `0x1003a6f7`
- name: `??_V@YAXPAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `48`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x10008c1d`
- `0x10009a20`
- `0x10009f60`
- `0x1000a516`
- `0x1000b1eb`
- `0x1000b28d`
- `0x1000b4de`
- `0x1000b6a2`
- `0x1000bd50`
- `0x1000bee0`
- `0x1000cf60`
- `0x1000dda5`
- `0x1000e110`
- `0x1000e200`
- `0x1000ee97`
- `0x10013660`
- `0x10013750`
- `0x10016250`
- `0x10016b80`
- `0x100175b0`
- `0x100176a0`
- `0x1001c7fd`
- `0x1001c916`
- `0x1001cd50`
- `0x1001e1f8`
- `0x1001e4c6`
- `0x1001e8ef`
- `0x1001ffa0`
- `0x100202e2`
- `0x10020f9f`
- `0x10021163`
- `0x10021805`
- `0x100218b2`
- `0x10021e37`
- `0x1002343f`
- `0x10025317`
- `0x10027726`
- `0x1002796c`
- `0x10029e70`
- `0x1002a5bd`
- `0x1002abaa`
- `0x1002ad94`
- `0x1002b288`
- `0x1002d050`
- `0x10030836`
- `0x10030b42`
- `0x10031712`
- `0x10034140`

## callees

- `0x1003a73d`

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
0x1003a6f2  jmp     ??3@YAXPAX@Z; operator delete(void *)
```
