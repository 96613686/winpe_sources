# StringLengthWorkerW

- ea: `0x180004300`
- end: `0x18000433a`
- name: `StringLengthWorkerW`
- size: `58`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b90`
- `0x1800051a0`
- `0x18000f048`
- `0x18001068c`
- `0x1800109a4`

## callees

- `0x180004300`

## pseudocode

```c
HRESULT __stdcall StringLengthWorkerW(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)
{
  size_t i; // r9
  HRESULT result; // eax

  for ( i = cchMax; cchMax; --cchMax )
  {
    if ( !*psz )
      break;
    ++psz;
  }
  result = -2147024809;
  if ( cchMax )
    result = 0;
  if ( pcchLength )
  {
    if ( cchMax )
      *pcchLength = i - cchMax;
    else
      *pcchLength = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004300  mov     r9, rdx
0x180004303  test    rdx, rdx
0x180004306  jz      short loc_180004318
0x180004308  cmp     word ptr [rcx], 0
0x18000430c  jz      short loc_180004318
0x18000430e  add     rcx, 2
0x180004312  sub     rdx, 1
0x180004316  jnz     short loc_180004308
0x180004318  xor     ecx, ecx
0x18000431a  mov     eax, 80070057h
0x18000431f  test    rdx, rdx
0x180004322  cmovnz  eax, ecx
0x180004325  test    r8, r8
0x180004328  jz      short locret_180004335
0x18000432a  test    rdx, rdx
0x18000432d  jz      short loc_180004336
0x18000432f  sub     r9, rdx
0x180004332  mov     [r8], r9
0x180004335  retn
0x180004336  mov     [r8], rcx
0x180004339  retn
```
