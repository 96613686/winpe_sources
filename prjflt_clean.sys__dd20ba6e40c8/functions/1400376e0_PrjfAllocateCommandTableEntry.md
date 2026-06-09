# PrjfAllocateCommandTableEntry

- ea: `0x1400376e0`
- end: `0x140037713`
- name: `PrjfAllocateCommandTableEntry`
- size: `51`
- prototype: `RTL_AVL_ALLOCATE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000b1d0`
- `0x1400376e0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140037700`
- `ntoskrnl!ExAllocatePool2` at `0x140037700`

## pseudocode

```c
__int64 __fastcall PrjfAllocateCommandTableEntry(
        struct _RTL_AVL_TABLE *Table,
        __int64 ByteSize,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rbx

  v4 = (unsigned int)ByteSize;
  if ( (unsigned int)ByteSize < 0x10 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(Table, ByteSize, a3, a4);
  return ExAllocatePool2(256, v4, 1868778064);
}

```

## disassembly

```asm
0x1400376e0  push    rbx
0x1400376e2  sub     rsp, 20h
0x1400376e6  mov     ebx, edx
0x1400376e8  cmp     edx, 10h
0x1400376eb  jnb     short loc_1400376F2
0x1400376ed  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400376f2  mov     rdx, rbx
0x1400376f5  mov     ecx, 100h
0x1400376fa  mov     r8d, 6F634A50h
0x140037700  call    cs:__imp_ExAllocatePool2
0x140037707  nop     dword ptr [rax+rax+00h]
0x14003770c  add     rsp, 20h
0x140037710  pop     rbx
0x140037711  retn
```
