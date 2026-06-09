# PrjfCompareCommandTableEntry

- ea: `0x140037a50`
- end: `0x140037a70`
- name: `PrjfCompareCommandTableEntry`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, _DWORD *FirstStruct, _DWORD *SecondStruct)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140037a50`

## pseudocode

```c
__int64 __fastcall PrjfCompareCommandTableEntry(
        struct _RTL_AVL_TABLE *Table,
        _DWORD *FirstStruct,
        _DWORD *SecondStruct)
{
  __int64 result; // rax

  if ( *FirstStruct > *SecondStruct )
    return 1;
  result = 2;
  if ( *FirstStruct < *SecondStruct )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140037a50  mov     ecx, [r8]
0x140037a53  mov     r8d, [rdx]
0x140037a56  cmp     r8d, ecx
0x140037a59  jle     short loc_140037A62
0x140037a5b  mov     eax, 1
0x140037a60  retn
0x140037a62  xor     edx, edx
0x140037a64  mov     eax, 2
0x140037a69  cmp     r8d, ecx
0x140037a6c  cmovl   eax, edx
0x140037a6f  retn
```
