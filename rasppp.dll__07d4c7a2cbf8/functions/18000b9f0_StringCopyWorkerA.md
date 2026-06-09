# StringCopyWorkerA

- ea: `0x18000b9f0`
- end: `0x18000ba39`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b970`
- `0x18000b9ac`

## callees

- `0x18000b9f0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  STRSAFE_LPSTR v7; // rcx
  HRESULT result; // eax

  for ( ; cchDest; --cchDest )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
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
0x18000b9f0  mov     r8, rcx
0x18000b9f3  test    rdx, rdx
0x18000b9f6  jz      short loc_18000BA1B
0x18000b9f8  mov     rax, [rsp+cchToCopy]
0x18000b9fd  test    rax, rax
0x18000ba00  jz      short loc_18000BA1B
0x18000ba02  mov     cl, [r9]
0x18000ba05  test    cl, cl
0x18000ba07  jz      short loc_18000BA1B
0x18000ba09  mov     [r8], cl
0x18000ba0c  inc     r9
0x18000ba0f  inc     r8
0x18000ba12  dec     rax
0x18000ba15  sub     rdx, 1
0x18000ba19  jnz     short loc_18000B9FD
0x18000ba1b  mov     rax, rdx
0x18000ba1e  lea     rcx, [r8-1]
0x18000ba22  neg     rax
0x18000ba25  sbb     eax, eax
0x18000ba27  not     eax
0x18000ba29  and     eax, 8007007Ah
0x18000ba2e  test    rdx, rdx
0x18000ba31  cmovnz  rcx, r8
0x18000ba35  mov     byte ptr [rcx], 0
0x18000ba38  retn
```
