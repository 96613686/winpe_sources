# StSecpCacheGenericTableFreeRoutine

- ea: `0x14000e840`
- end: `0x14000e852`
- name: `StSecpCacheGenericTableFreeRoutine`
- size: `18`
- prototype: `RTL_GENERIC_FREE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400122e0`

## pseudocode

```c
void __fastcall StSecpCacheGenericTableFreeRoutine(struct _RTL_GENERIC_TABLE *Table, PVOID Buffer)
{
  StSecFree(Buffer);
}

```

## disassembly

```asm
0x14000e840  sub     rsp, 28h
0x14000e844  mov     rcx, rdx
0x14000e847  call    StSecFree
0x14000e84c  add     rsp, 28h
0x14000e850  retn
```
