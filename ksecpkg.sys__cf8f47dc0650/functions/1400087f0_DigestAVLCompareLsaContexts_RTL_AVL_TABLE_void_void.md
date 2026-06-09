# DigestAVLCompareLsaContexts(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x1400087f0`
- end: `0x140008805`
- name: `?DigestAVLCompareLsaContexts@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `21`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400087f0`

## pseudocode

```c
__int64 __fastcall DigestAVLCompareLsaContexts(struct _RTL_AVL_TABLE *Table, _QWORD *FirstStruct, _QWORD *SecondStruct)
{
  if ( *SecondStruct <= *FirstStruct )
    return 2 - (unsigned int)(*SecondStruct < *FirstStruct);
  else
    return 0;
}

```

## disassembly

```asm
0x1400087f0  mov     rax, [rdx]
0x1400087f3  mov     rcx, [r8]
0x1400087f6  cmp     rcx, rax
0x1400087f9  jbe     short loc_1400087FF
0x1400087fb  xor     eax, eax
0x1400087fd  retn
0x1400087ff  sbb     eax, eax
0x140008801  add     eax, 2
0x140008804  retn
```
