# StringCopyWorkerA

- ea: `0x140005d20`
- end: `0x140005d69`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004930`

## callees

- `0x140005d20`

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
0x140005d20  mov     r8, rcx
0x140005d23  mov     eax, 7FFFFFFEh
0x140005d28  test    rdx, rdx
0x140005d2b  jz      short loc_140005D4B
0x140005d2d  test    rax, rax
0x140005d30  jz      short loc_140005D4B
0x140005d32  mov     cl, [r9]
0x140005d35  test    cl, cl
0x140005d37  jz      short loc_140005D4B
0x140005d39  mov     [r8], cl
0x140005d3c  inc     r9
0x140005d3f  inc     r8
0x140005d42  dec     rax
0x140005d45  sub     rdx, 1
0x140005d49  jnz     short loc_140005D2D
0x140005d4b  mov     rax, rdx
0x140005d4e  lea     rcx, [r8-1]
0x140005d52  neg     rax
0x140005d55  sbb     eax, eax
0x140005d57  not     eax
0x140005d59  and     eax, 8007007Ah
0x140005d5e  test    rdx, rdx
0x140005d61  cmovnz  rcx, r8
0x140005d65  mov     byte ptr [rcx], 0
0x140005d68  retn
```
