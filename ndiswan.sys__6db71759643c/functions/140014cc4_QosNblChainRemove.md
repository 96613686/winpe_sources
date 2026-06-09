# QosNblChainRemove

- ea: `0x140014cc4`
- end: `0x140014ce6`
- name: `QosNblChainRemove`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400148a0`
- `0x140014d6c`

## callees

- `0x140014cc4`

## pseudocode

```c
_QWORD *__fastcall QosNblChainRemove(__int64 a1, __int64 a2, _QWORD *a3)
{
  *(_QWORD *)a1 = *a3;
  *a3 = 0;
  if ( *(_QWORD **)(a1 + 8) == a3 )
    *(_QWORD *)(a1 + 8) = 0;
  --*(_DWORD *)(a1 + 16);
  return a3;
}

```

## disassembly

```asm
0x140014cc4  mov     rax, [r8]
0x140014cc7  mov     [rcx], rax
0x140014cca  mov     qword ptr [r8], 0
0x140014cd1  cmp     [rcx+8], r8
0x140014cd5  jnz     short loc_140014CDF
0x140014cd7  mov     qword ptr [rcx+8], 0
0x140014cdf  dec     dword ptr [rcx+10h]
0x140014ce2  mov     rax, r8
0x140014ce5  retn
```
