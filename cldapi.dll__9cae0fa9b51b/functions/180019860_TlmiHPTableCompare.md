# TlmiHPTableCompare

- ea: `0x180019860`
- end: `0x180019878`
- name: `TlmiHPTableCompare`
- size: `24`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019860`

## pseudocode

```c
__int64 __fastcall TlmiHPTableCompare(struct _RTL_AVL_TABLE *Table, _QWORD *FirstStruct, _QWORD *SecondStruct)
{
  if ( *FirstStruct == *SecondStruct )
    return 2;
  else
    return *FirstStruct > *SecondStruct;
}

```

## disassembly

```asm
0x180019860  mov     rcx, [rdx]
0x180019863  cmp     rcx, [r8]
0x180019866  jnz     short loc_18001986F
0x180019868  mov     eax, 2
0x18001986d  retn
0x18001986f  xor     eax, eax
0x180019871  cmp     rcx, [r8]
0x180019874  setnle  al
0x180019877  retn
```
