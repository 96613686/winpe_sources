# StringLengthWorkerW

- ea: `0x180008944`
- end: `0x180008983`
- name: `StringLengthWorkerW`
- size: `63`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008864`
- `0x180008908`

## callees

- `0x180008944`

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
  result = cchMax == 0 ? 0x80070057 : 0;
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
0x180008944  xor     r10d, r10d
0x180008947  mov     r9, rdx
0x18000894a  test    rdx, rdx
0x18000894d  jz      short loc_18000895F
0x18000894f  cmp     [rcx], r10w
0x180008953  jz      short loc_18000895F
0x180008955  add     rcx, 2
0x180008959  sub     rdx, 1
0x18000895d  jnz     short loc_18000894F
0x18000895f  mov     rax, rdx
0x180008962  neg     rax
0x180008965  sbb     eax, eax
0x180008967  not     eax
0x180008969  and     eax, 80070057h
0x18000896e  test    r8, r8
0x180008971  jz      short locret_180008982
0x180008973  test    rdx, rdx
0x180008976  jz      short loc_18000897F
0x180008978  sub     r9, rdx
0x18000897b  mov     [r8], r9
0x18000897e  retn
0x18000897f  mov     [r8], r10
0x180008982  retn
```
