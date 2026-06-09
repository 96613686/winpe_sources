# StringLengthWorkerW

- ea: `0x1400089a4`
- end: `0x1400089e3`
- name: `StringLengthWorkerW`
- size: `63`
- prototype: `static HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cchMax, size_t *pcchLength)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400086f8`
- `0x140008808`

## callees

- `0x1400089a4`

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
0x1400089a4  xor     r10d, r10d
0x1400089a7  mov     r9, rdx
0x1400089aa  test    rdx, rdx
0x1400089ad  jz      short loc_1400089BF
0x1400089af  cmp     [rcx], r10w
0x1400089b3  jz      short loc_1400089BF
0x1400089b5  add     rcx, 2
0x1400089b9  sub     rdx, 1
0x1400089bd  jnz     short loc_1400089AF
0x1400089bf  mov     rax, rdx
0x1400089c2  neg     rax
0x1400089c5  sbb     eax, eax
0x1400089c7  not     eax
0x1400089c9  and     eax, 80070057h
0x1400089ce  test    r8, r8
0x1400089d1  jz      short locret_1400089E2
0x1400089d3  test    rdx, rdx
0x1400089d6  jz      short loc_1400089DF
0x1400089d8  sub     r9, rdx
0x1400089db  mov     [r8], r9
0x1400089de  retn
0x1400089df  mov     [r8], r10
0x1400089e2  retn
```
