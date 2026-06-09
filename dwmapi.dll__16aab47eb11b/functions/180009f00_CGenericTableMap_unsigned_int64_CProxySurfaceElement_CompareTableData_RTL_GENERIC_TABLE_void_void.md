# CGenericTableMap<unsigned __int64,CProxySurfaceElement>::CompareTableData(_RTL_GENERIC_TABLE *,void *,void *)

- ea: `0x180009f00`
- end: `0x180009f10`
- name: `?CompareTableData@?$CGenericTableMap@_KVCProxySurfaceElement@@@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_GENERIC_TABLE@@PEAX1@Z`
- size: `16`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009f00`

## pseudocode

```c
__int64 __fastcall CGenericTableMap<unsigned __int64,CProxySurfaceElement>::CompareTableData(
        struct _RTL_GENERIC_TABLE *Table,
        _QWORD *FirstStruct,
        _QWORD *SecondStruct)
{
  __int64 result; // rax

  result = 0;
  if ( *FirstStruct >= *SecondStruct )
  {
    LOBYTE(result) = *FirstStruct == *SecondStruct;
    return (unsigned int)(result + 1);
  }
  return result;
}

```

## disassembly

```asm
0x180009f00  mov     rcx, [r8]
0x180009f03  xor     eax, eax
0x180009f05  cmp     [rdx], rcx
0x180009f08  jb      short locret_180009F0F
0x180009f0a  setz    al
0x180009f0d  inc     eax
0x180009f0f  retn
```
