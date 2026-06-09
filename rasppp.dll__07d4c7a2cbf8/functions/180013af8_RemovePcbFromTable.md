# RemovePcbFromTable

- ea: `0x180013af8`
- end: `0x180013b3d`
- name: `RemovePcbFromTable`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800155b8`
- `0x180015ae0`
- `0x180016d40`

## callees

- `0x180013af8`

## pseudocode

```c
unsigned __int64 __fastcall RemovePcbFromTable(__int64 a1)
{
  unsigned __int64 result; // rax
  __int64 v2; // r9
  unsigned __int64 *v3; // r8
  unsigned __int64 *i; // rdx

  result = *(_DWORD *)(a1 + 16) / (unsigned int)qword_18004C970;
  v2 = *(_DWORD *)(a1 + 16) % (unsigned int)qword_18004C970;
  v3 = (unsigned __int64 *)*((_QWORD *)PcbTable + v2);
  for ( i = v3; i; i = (unsigned __int64 *)*i )
  {
    result = *(_QWORD *)(a1 + 16);
    if ( i[2] == result )
    {
      result = *i;
      if ( i == *((unsigned __int64 **)PcbTable + v2) )
        *((_QWORD *)PcbTable + v2) = result;
      else
        *v3 = result;
      return result;
    }
    v3 = i;
  }
  return result;
}

```

## disassembly

```asm
0x180013af8  mov     eax, [rcx+10h]
0x180013afb  xor     edx, edx
0x180013afd  div     dword ptr cs:qword_18004C970
0x180013b03  mov     r10, qword ptr cs:PcbTable
0x180013b0a  mov     r9d, edx
0x180013b0d  mov     r8, [r10+rdx*8]
0x180013b11  mov     rdx, r8
0x180013b14  test    rdx, rdx
0x180013b17  jz      short locret_180013B3C
0x180013b19  mov     rax, [rcx+10h]
0x180013b1d  cmp     [rdx+10h], rax
0x180013b21  jz      short loc_180013B2B
0x180013b23  mov     r8, rdx
0x180013b26  mov     rdx, [rdx]
0x180013b29  jmp     short loc_180013B14
0x180013b2b  mov     rax, [rdx]
0x180013b2e  cmp     rdx, [r10+r9*8]
0x180013b32  jnz     short loc_180013B39
0x180013b34  mov     [r10+r9*8], rax
0x180013b38  retn
0x180013b39  mov     [r8], rax
0x180013b3c  retn
```
