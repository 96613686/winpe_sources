# StSecpCacheGenericTableAllocRoutine

- ea: `0x14000e7e0`
- end: `0x14000e803`
- name: `StSecpCacheGenericTableAllocRoutine`
- size: `35`
- prototype: `RTL_GENERIC_ALLOCATE_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000e7f1`
- `ntoskrnl!ExAllocatePool2` at `0x14000e7f1`

## pseudocode

```c
__int64 __fastcall StSecpCacheGenericTableAllocRoutine(struct _RTL_GENERIC_TABLE *Table, CLONG ByteSize)
{
  return ExAllocatePool2(256, ByteSize, 1884517459);
}

```

## disassembly

```asm
0x14000e7e0  sub     rsp, 28h
0x14000e7e4  mov     edx, edx
0x14000e7e6  mov     ecx, 100h
0x14000e7eb  mov     r8d, 70537453h
0x14000e7f1  call    cs:__imp_ExAllocatePool2
0x14000e7f8  nop     dword ptr [rax+rax+00h]
0x14000e7fd  add     rsp, 28h
0x14000e801  retn
```
