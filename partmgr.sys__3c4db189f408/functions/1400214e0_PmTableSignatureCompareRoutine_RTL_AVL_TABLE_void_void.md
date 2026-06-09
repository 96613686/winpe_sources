# PmTableSignatureCompareRoutine(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x1400214e0`
- end: `0x1400214f5`
- name: `?PmTableSignatureCompareRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `21`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400214e0`

## pseudocode

```c
__int64 __fastcall PmTableSignatureCompareRoutine(
        struct _RTL_AVL_TABLE *Table,
        _DWORD *FirstStruct,
        _DWORD *SecondStruct)
{
  unsigned int v3; // eax
  unsigned int v4; // ecx

  v3 = SecondStruct[6];
  v4 = FirstStruct[6];
  if ( v3 <= v4 )
    return 2 - (unsigned int)(v3 < v4);
  else
    return 0;
}

```

## disassembly

```asm
0x1400214e0  mov     eax, [r8+18h]
0x1400214e4  mov     ecx, [rdx+18h]
0x1400214e7  cmp     eax, ecx
0x1400214e9  jbe     short loc_1400214EF
0x1400214eb  xor     eax, eax
0x1400214ed  retn
0x1400214ef  sbb     eax, eax
0x1400214f1  add     eax, 2
0x1400214f4  retn
```
