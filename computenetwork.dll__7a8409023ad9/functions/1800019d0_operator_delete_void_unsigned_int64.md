# operator delete(void *,unsigned __int64)

- ea: `0x1800019d0`
- end: `0x1800019d5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003e10`
- `0x180004108`
- `0x180004210`
- `0x180004470`
- `0x1800044b0`
- `0x18000a130`
- `0x18000a1d0`
- `0x18000a608`
- `0x18000aaa0`
- `0x18000b7f0`
- `0x18000b890`
- `0x18000e351`

## callees

- `0x180001eec`

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
0x1800019d0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
