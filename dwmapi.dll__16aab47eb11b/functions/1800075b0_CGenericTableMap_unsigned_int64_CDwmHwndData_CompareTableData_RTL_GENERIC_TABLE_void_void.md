# CGenericTableMap<unsigned __int64,CDwmHwndData>::CompareTableData(_RTL_GENERIC_TABLE *,void *,void *)

- ea: `0x1800075b0`
- end: `0x1800075ca`
- name: `?CompareTableData@?$CGenericTableMap@_KVCDwmHwndData@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z`
- size: `26`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800075b0`

## pseudocode

```c
__int64 __fastcall CGenericTableMap<unsigned __int64,CDwmHwndData>::CompareTableData(
        struct _RTL_GENERIC_TABLE *Table,
        _QWORD *FirstStruct,
        _QWORD *SecondStruct)
{
  if ( *FirstStruct >= *SecondStruct )
    return (unsigned int)(*FirstStruct == *SecondStruct) + 1;
  else
    return 0;
}

```

## disassembly

```asm
0x1800075b0  mov     r9, [rdx]
0x1800075b3  mov     rax, [r8]
0x1800075b6  cmp     r9, rax
0x1800075b9  jnb     short loc_1800075BE
0x1800075bb  xor     eax, eax
0x1800075bd  retn
0x1800075be  xor     ecx, ecx
0x1800075c0  cmp     r9, rax
0x1800075c3  setz    cl
0x1800075c6  lea     eax, [rcx+1]
0x1800075c9  retn
```
