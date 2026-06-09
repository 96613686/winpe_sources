# CfpSyncRootTableCompare

- ea: `0x18000c060`
- end: `0x18000c078`
- name: `CfpSyncRootTableCompare`
- size: `24`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c060`

## pseudocode

```c
__int64 __fastcall CfpSyncRootTableCompare(struct _RTL_AVL_TABLE *Table, _QWORD *FirstStruct, _QWORD *SecondStruct)
{
  if ( *FirstStruct == *SecondStruct )
    return 2;
  else
    return *FirstStruct > *SecondStruct;
}

```

## disassembly

```asm
0x18000c060  mov     rcx, [r8]
0x18000c063  cmp     [rdx], rcx
0x18000c066  jnz     short loc_18000C06F
0x18000c068  mov     eax, 2
0x18000c06d  retn
0x18000c06f  xor     eax, eax
0x18000c071  cmp     [rdx], rcx
0x18000c074  setnle  al
0x18000c077  retn
```
