# operator delete(void *,unsigned __int64)

- ea: `0x18000a6d0`
- end: `0x18000a6d5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800056a0`
- `0x180006e88`
- `0x180008250`
- `0x18000828c`
- `0x18000a084`
- `0x18000bff0`
- `0x18000c760`
- `0x18000cb10`
- `0x18000cbb0`
- `0x18000e960`
- `0x180011650`
- `0x180014d84`
- `0x180014e50`
- `0x18001a064`
- `0x18001a170`
- `0x18001f874`
- `0x18001fae0`
- `0x1800248f0`
- `0x180028b6c`

## callees

- `0x18000a728`

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
0x18000a6d0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
