# `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))

- ea: `0x180001bc8`
- end: `0x180001bcd`
- name: `??_M@YAXPEAX_K1P6AX0@Z@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64, unsigned __int64, void (*)(void *))`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c47c`
- `0x18000c744`
- `0x18000dca6`
- `0x18000dcd7`

## callees

- `0x180001bd4`

## pseudocode

```c
// attributes: thunk
void __fastcall `eh vector destructor iterator'(void *a1, unsigned __int64 a2, int a3, void (*a4)(void *))
{
  ??_M@YAXPEAX_KHP6AX0@Z@Z(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x180001bc8  jmp     ??_M@YAXPEAX_KHP6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,int,void (*)(void *))
```
