# CalcNewUncompactSize

- ea: `0x180008990`
- end: `0x1800089bf`
- name: `CalcNewUncompactSize`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800089c8`

## callees

- `0x180008990`

## pseudocode

```c
__int64 __fastcall CalcNewUncompactSize(unsigned int a1, unsigned int a2, unsigned int a3)
{
  unsigned int v3; // r9d
  unsigned int v4; // eax
  __int64 result; // rax

  if ( a2 > a3 )
    return a1;
  v3 = (a2 + 3) & 0xFFFFFFFC;
  if ( v3 < a2 )
    return a1;
  v4 = (a3 + 3) & 0xFFFFFFFC;
  if ( v4 < a3 )
    return a1;
  result = a1 + v4 - v3;
  if ( (unsigned int)result < a1 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x180008990  cmp     edx, r8d
0x180008993  ja      short loc_1800089BC
0x180008995  lea     r9d, [rdx+3]
0x180008999  mov     r10d, 0FFFFFFFCh
0x18000899f  and     r9d, r10d
0x1800089a2  cmp     r9d, edx
0x1800089a5  jb      short loc_1800089BC
0x1800089a7  lea     eax, [r8+3]
0x1800089ab  and     eax, r10d
0x1800089ae  cmp     eax, r8d
0x1800089b1  jb      short loc_1800089BC
0x1800089b3  sub     eax, r9d
0x1800089b6  add     eax, ecx
0x1800089b8  cmp     eax, ecx
0x1800089ba  jnb     short locret_1800089BE
0x1800089bc  mov     eax, ecx
0x1800089be  retn
```
