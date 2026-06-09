# operator delete(void *,unsigned __int64)

- ea: `0x1800017a4`
- end: `0x1800017a9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `28`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800031a0`
- `0x1800031f0`
- `0x180003230`
- `0x18000b55c`
- `0x18000b580`
- `0x18000b5cc`
- `0x18000b624`
- `0x18000b7a4`
- `0x18000b8bc`
- `0x18000c160`
- `0x18000c6e0`
- `0x18000c720`
- `0x18000c7d0`
- `0x18000c88c`
- `0x18000cae8`
- `0x18000d0a0`
- `0x18000d0e0`
- `0x18000d120`
- `0x18000d160`
- `0x18000d590`
- `0x18000d5d0`
- `0x18000d630`
- `0x18000d940`
- `0x18000daa4`
- `0x18000db00`
- `0x18000db5c`
- `0x18000dbc8`
- `0x18000e343`

## callees

- `0x180003140`

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
0x1800017a4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
