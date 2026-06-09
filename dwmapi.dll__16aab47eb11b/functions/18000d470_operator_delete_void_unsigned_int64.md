# operator delete(void *,unsigned __int64)

- ea: `0x18000d470`
- end: `0x18000d475`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007e90`
- `0x18000c6b0`
- `0x18000e7f0`
- `0x18001114c`
- `0x180011180`
- `0x1800117c0`
- `0x1800136ec`
- `0x1800153a0`
- `0x180015610`
- `0x180015ea0`
- `0x180015ed0`
- `0x180015f00`
- `0x180015f50`

## callees

- `0x180009658`

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
0x18000d470  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
