# operator delete(void *,unsigned __int64)

- ea: `0x180001008`
- end: `0x18000100d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `51`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800021ec`
- `0x180003270`
- `0x180003678`
- `0x1800036fc`
- `0x1800037e0`
- `0x180003840`
- `0x180003880`
- `0x1800038c0`
- `0x180004f90`
- `0x180006f10`
- `0x180006fc0`
- `0x180007004`
- `0x180007f08`
- `0x1800080b0`
- `0x1800080f0`
- `0x180008130`
- `0x180008160`
- `0x1800081a0`
- `0x180009d70`
- `0x18000a7e0`
- `0x18000ab04`
- `0x18000d1e0`
- `0x18000d7a0`
- `0x18000e238`
- `0x18000e3b0`
- `0x18000e3f0`
- `0x180011580`
- `0x1800120f0`
- `0x1800121e0`
- `0x180012f4c`
- `0x180012f80`
- `0x1800131e0`
- `0x1800136c0`
- `0x180013a50`
- `0x180014250`
- `0x180014cc0`
- `0x180015218`
- `0x1800155d0`
- `0x180015610`
- `0x180015650`
- `0x1800156c8`
- `0x180016924`
- `0x180018fd0`
- `0x18001b0dc`
- `0x18001b140`
- `0x18001b180`
- `0x18001c108`
- `0x18001c28c`
- `0x18001c39c`
- `0x18001c730`

## callees

- `0x180001060`

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
0x180001008  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
