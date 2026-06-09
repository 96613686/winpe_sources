# QosNblChainRemove

- ea: `0x140011f7c`
- end: `0x140011f9e`
- name: `QosNblChainRemove`
- size: `34`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140011b58`
- `0x1400121c8`

## callees

- `0x140011f7c`

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
0x140011f7c  mov     rax, [r8]
0x140011f7f  mov     [rcx], rax
0x140011f82  mov     qword ptr [r8], 0
0x140011f89  cmp     [rcx+8], r8
0x140011f8d  jnz     short loc_140011F97
0x140011f8f  mov     qword ptr [rcx+8], 0
0x140011f97  dec     dword ptr [rcx+10h]
0x140011f9a  mov     rax, r8
0x140011f9d  retn
```
