# RemovePcbFromTable

- ea: `0x1800141bc`
- end: `0x180014202`
- name: `RemovePcbFromTable`
- size: `70`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180015d28`
- `0x180016260`
- `0x180017510`

## callees

- `0x1800141bc`

## pseudocode

```c
unsigned __int64 __fastcall RemovePcbFromTable(__int64 a1)
{
  unsigned __int64 result; // rax
  __int64 v2; // r9
  unsigned __int64 *v3; // r8
  unsigned __int64 *i; // rdx

  result = *(_DWORD *)(a1 + 16) / (unsigned int)qword_18004D970;
  v2 = *(_DWORD *)(a1 + 16) % (unsigned int)qword_18004D970;
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
0x1800141bc  mov     eax, [rcx+10h]
0x1800141bf  xor     edx, edx
0x1800141c1  div     dword ptr cs:qword_18004D970
0x1800141c7  mov     r10, qword ptr cs:PcbTable
0x1800141ce  mov     r9d, edx
0x1800141d1  mov     r8, [r10+rdx*8]
0x1800141d5  mov     rdx, r8
0x1800141d8  test    rdx, rdx
0x1800141db  jz      short locret_180014201
0x1800141dd  mov     rax, [rcx+10h]
0x1800141e1  cmp     [rdx+10h], rax
0x1800141e5  jz      short loc_1800141EF
0x1800141e7  mov     r8, rdx
0x1800141ea  mov     rdx, [rdx]
0x1800141ed  jmp     short loc_1800141D8
0x1800141ef  mov     rax, [rdx]
0x1800141f2  cmp     rdx, [r10+r9*8]
0x1800141f6  jnz     short loc_1800141FE
0x1800141f8  mov     [r10+r9*8], rax
0x1800141fc  retn
0x1800141fe  mov     [r8], rax
0x180014201  retn
```
