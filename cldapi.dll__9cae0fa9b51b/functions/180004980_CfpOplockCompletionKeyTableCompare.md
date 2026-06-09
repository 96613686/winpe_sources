# CfpOplockCompletionKeyTableCompare

- ea: `0x180004980`
- end: `0x180004998`
- name: `CfpOplockCompletionKeyTableCompare`
- size: `24`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004980`

## pseudocode

```c
__int64 __fastcall CfpOplockCompletionKeyTableCompare(
        struct _RTL_AVL_TABLE *Table,
        _QWORD *FirstStruct,
        _QWORD *SecondStruct)
{
  if ( *FirstStruct == *SecondStruct )
    return 2;
  else
    return *FirstStruct > *SecondStruct;
}

```

## disassembly

```asm
0x180004980  mov     rcx, [r8]
0x180004983  cmp     [rdx], rcx
0x180004986  jnz     short loc_18000498F
0x180004988  mov     eax, 2
0x18000498d  retn
0x18000498f  xor     eax, eax
0x180004991  cmp     [rdx], rcx
0x180004994  setnbe  al
0x180004997  retn
```
