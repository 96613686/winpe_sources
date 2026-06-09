# operator delete(void *,unsigned __int64)

- ea: `0x180001514`
- end: `0x180001519`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `21`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003210`
- `0x180005dd0`
- `0x1800060d0`
- `0x1800061a0`
- `0x180006ec0`
- `0x180007a00`
- `0x180007c50`
- `0x180007d10`
- `0x180007d50`
- `0x180007e00`
- `0x180008b30`
- `0x180008cb0`
- `0x180009b30`
- `0x18000a210`
- `0x18000b070`
- `0x18000b0f0`
- `0x18000e4d0`
- `0x18000e5c0`
- `0x18000eb40`
- `0x18000eb90`
- `0x1800114b0`

## callees

- `0x180013700`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001514  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
