# operator delete(void *,unsigned __int64)

- ea: `0x18000f530`
- end: `0x18000f535`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `40`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004a7c`
- `0x1800077b0`
- `0x18000a6f0`
- `0x18000a960`
- `0x18000bad0`
- `0x18000bb60`
- `0x18000bc40`
- `0x180011374`
- `0x1800113a0`
- `0x1800113e0`
- `0x180011420`
- `0x1800117d0`
- `0x180012080`
- `0x180017fb0`
- `0x180018044`
- `0x18001a254`
- `0x18001a390`
- `0x18001a4cc`
- `0x18001a60c`
- `0x18001a73c`
- `0x18001a86c`
- `0x18001a8a4`
- `0x18001a8dc`
- `0x18001a914`
- `0x18001a94c`
- `0x18001aa50`
- `0x18001aa90`
- `0x18001aad0`
- `0x18001ab10`
- `0x18001ab50`
- `0x18001ab90`
- `0x18001abd0`
- `0x18001ac20`
- `0x18001ac70`
- `0x18001acc0`
- `0x18001ad00`
- `0x18001ad40`
- `0x18001ad80`
- `0x18001b070`
- `0x180022190`

## callees

- `0x18000f518`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18000f530  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
