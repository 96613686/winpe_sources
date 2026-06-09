# StringCopyWorkerA

- ea: `0x180005b08`
- end: `0x180005b51`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004368`

## callees

- `0x180005b08`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  __int64 i; // rax
  STRSAFE_LPSTR v7; // rcx
  HRESULT result; // eax

  for ( i = 2147483646; cchDest; --cchDest )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  v7 = pszDest - 1;
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180005b08  mov     r8, rcx
0x180005b0b  mov     eax, 7FFFFFFEh
0x180005b10  test    rdx, rdx
0x180005b13  jz      short loc_180005B33
0x180005b15  test    rax, rax
0x180005b18  jz      short loc_180005B33
0x180005b1a  mov     cl, [r9]
0x180005b1d  test    cl, cl
0x180005b1f  jz      short loc_180005B33
0x180005b21  mov     [r8], cl
0x180005b24  inc     r9
0x180005b27  inc     r8
0x180005b2a  dec     rax
0x180005b2d  sub     rdx, 1
0x180005b31  jnz     short loc_180005B15
0x180005b33  mov     rax, rdx
0x180005b36  lea     rcx, [r8-1]
0x180005b3a  neg     rax
0x180005b3d  sbb     eax, eax
0x180005b3f  not     eax
0x180005b41  and     eax, 8007007Ah
0x180005b46  test    rdx, rdx
0x180005b49  cmovnz  rcx, r8
0x180005b4d  mov     byte ptr [rcx], 0
0x180005b50  retn
```
