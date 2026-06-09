# operator delete(void *,unsigned __int64)

- ea: `0x18000214c`
- end: `0x180002151`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `57`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002720`
- `0x180003b40`
- `0x180003b80`
- `0x180003bbc`
- `0x180003c00`
- `0x180003c3c`
- `0x180003c80`
- `0x180003cbc`
- `0x180003d00`
- `0x180005440`
- `0x180005520`
- `0x180008020`
- `0x180008060`
- `0x1800080a0`
- `0x18000d5d0`
- `0x18000efc0`
- `0x180011890`
- `0x1800143a8`
- `0x1800145e0`
- `0x180014620`
- `0x180014e50`
- `0x1800152f0`
- `0x1800155f0`
- `0x180017ed0`
- `0x180017f04`
- `0x180017f40`
- `0x180017f80`
- `0x180017fbc`
- `0x180018000`
- `0x18001803c`
- `0x180019d50`
- `0x18001b950`
- `0x18001bc90`
- `0x18001c9a0`
- `0x18001f540`
- `0x18001f580`
- `0x18001f5bc`
- `0x18001f600`
- `0x18001f640`
- `0x180022ba0`
- `0x180022be0`
- `0x180024570`
- `0x180024ec0`
- `0x1800254e9`
- `0x180025e56`
- `0x180026391`
- `0x180026681`
- `0x180026884`
- `0x1800268a7`
- `0x1800268ca`

## callees

- `0x1800021c0`

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
0x18000214c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
