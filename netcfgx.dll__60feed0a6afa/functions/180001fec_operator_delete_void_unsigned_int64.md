# operator delete(void *,unsigned __int64)

- ea: `0x180001fec`
- end: `0x180001ff1`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `34`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800031b0`
- `0x180003220`
- `0x180003290`
- `0x1800032e0`
- `0x180004240`
- `0x180005b00`
- `0x180005c4c`
- `0x180007ca0`
- `0x180007cf0`
- `0x180007f78`
- `0x18000805c`
- `0x180008210`
- `0x1800085a0`
- `0x1800086a0`
- `0x180008b40`
- `0x180008b80`
- `0x180009368`
- `0x180009de8`
- `0x18000a1b4`
- `0x18000a344`
- `0x18000a3b4`
- `0x18000a5dc`
- `0x18000a954`
- `0x18000ab50`
- `0x18000aed4`
- `0x18000c204`
- `0x18000c4d8`
- `0x18000c7f0`
- `0x18000c850`
- `0x18000c890`
- `0x180010700`
- `0x180010724`
- `0x180010810`
- `0x180010a00`

## callees

- `0x180007c94`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  ??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180001fec  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
