# CdFcbTableCompare

- ea: `0x140018bd0`
- end: `0x140018be3`
- name: `CdFcbTableCompare`
- size: `19`
- prototype: `RTL_GENERIC_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140018bd0`

## pseudocode

```c
__int64 __fastcall CdFcbTableCompare(struct _RTL_GENERIC_TABLE *Table, _QWORD *FirstStruct, _QWORD *SecondStruct)
{
  __int64 result; // rax

  result = 0;
  if ( *FirstStruct >= *SecondStruct )
  {
    LOBYTE(result) = *FirstStruct <= *SecondStruct;
    return (unsigned int)(result + 1);
  }
  return result;
}

```

## disassembly

```asm
0x140018bd0  mov     rcx, [rdx]
0x140018bd3  xor     eax, eax
0x140018bd5  mov     rdx, [r8]
0x140018bd8  cmp     rcx, rdx
0x140018bdb  jl      short locret_140018BE2
0x140018bdd  setle   al
0x140018be0  inc     eax
0x140018be2  retn
```
