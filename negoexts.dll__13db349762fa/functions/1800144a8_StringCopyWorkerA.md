# StringCopyWorkerA

- ea: `0x1800144a8`
- end: `0x1800144f1`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011d88`

## callees

- `0x1800144a8`

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
0x1800144a8  mov     r8, rcx
0x1800144ab  mov     eax, 7FFFFFFEh
0x1800144b0  test    rdx, rdx
0x1800144b3  jz      short loc_1800144D3
0x1800144b5  test    rax, rax
0x1800144b8  jz      short loc_1800144D3
0x1800144ba  mov     cl, [r9]
0x1800144bd  test    cl, cl
0x1800144bf  jz      short loc_1800144D3
0x1800144c1  mov     [r8], cl
0x1800144c4  inc     r9
0x1800144c7  inc     r8
0x1800144ca  dec     rax
0x1800144cd  sub     rdx, 1
0x1800144d1  jnz     short loc_1800144B5
0x1800144d3  mov     rax, rdx
0x1800144d6  lea     rcx, [r8-1]
0x1800144da  neg     rax
0x1800144dd  sbb     eax, eax
0x1800144df  not     eax
0x1800144e1  and     eax, 8007007Ah
0x1800144e6  test    rdx, rdx
0x1800144e9  cmovnz  rcx, r8
0x1800144ed  mov     byte ptr [rcx], 0
0x1800144f0  retn
```
