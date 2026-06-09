# StringCchCopyNA

- ea: `0x140074764`
- end: `0x1400747cb`
- name: `StringCchCopyNA`
- size: `103`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140080064`
- `0x1400821c0`
- `0x140082390`
- `0x140082754`

## callees

- `0x140074764`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)
{
  HRESULT result; // eax
  STRSAFE_LPSTR v5; // rax

  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF || cchToCopy > 0x7FFFFFFE )
  {
    result = -2147024809;
    *pszDest = 0;
  }
  else
  {
    do
    {
      if ( !cchToCopy )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --cchToCopy;
      --cchDest;
    }
    while ( cchDest );
    v5 = pszDest - 1;
    if ( cchDest )
      v5 = pszDest;
    *v5 = 0;
    return cchDest == 0 ? 0x8007007A : 0;
  }
  return result;
}

```

## disassembly

```asm
0x140074764  xor     r10d, r10d
0x140074767  test    rdx, rdx
0x14007476a  jz      short loc_1400747BD
0x14007476c  cmp     rdx, 7FFFFFFFh
0x140074773  jbe     short loc_14007477C
0x140074775  mov     eax, 80070057h
0x14007477a  jmp     short loc_1400747C7
0x14007477c  cmp     r9, 7FFFFFFEh
0x140074783  ja      short loc_140074775
0x140074785  test    r9, r9
0x140074788  jz      short loc_1400747A2
0x14007478a  mov     al, [r8]
0x14007478d  test    al, al
0x14007478f  jz      short loc_1400747A2
0x140074791  mov     [rcx], al
0x140074793  inc     r8
0x140074796  inc     rcx
0x140074799  dec     r9
0x14007479c  sub     rdx, 1
0x1400747a0  jnz     short loc_140074785
0x1400747a2  test    rdx, rdx
0x1400747a5  lea     rax, [rcx-1]
0x1400747a9  cmovnz  rax, rcx
0x1400747ad  neg     rdx
0x1400747b0  mov     [rax], r10b
0x1400747b3  sbb     eax, eax
0x1400747b5  not     eax
0x1400747b7  and     eax, 8007007Ah
0x1400747bc  retn
0x1400747bd  mov     eax, 80070057h
0x1400747c2  test    rdx, rdx
0x1400747c5  jz      short locret_1400747CA
0x1400747c7  mov     [rcx], r10b
0x1400747ca  retn
```
