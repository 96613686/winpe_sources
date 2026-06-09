# operator delete(void *)

- ea: `0x140009cb0`
- end: `0x140009cb5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002260`
- `0x140002a70`
- `0x1400035a0`
- `0x1400046bc`
- `0x140006648`
- `0x140007748`
- `0x140007970`
- `0x140008e10`
- `0x14000929c`
- `0x14000d830`
- `0x14000d984`
- `0x14000ddcc`
- `0x14000e110`
- `0x14000e6f0`
- `0x140010a20`
- `0x1400118f0`
- `0x140011930`
- `0x140012cc0`
- `0x140012d90`
- `0x140012dc8`
- `0x140014810`
- `0x140015080`
- `0x1400150c0`
- `0x1400154a0`

## callees

- `0x140009dc3`

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
0x140009cb0  jmp     free_0
```
