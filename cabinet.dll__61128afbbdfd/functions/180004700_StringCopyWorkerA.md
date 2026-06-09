# StringCopyWorkerA

- ea: `0x180004700`
- end: `0x180004749`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001bd8`
- `0x180002cfc`
- `0x180002f0c`
- `0x1800046c4`
- `0x1800048d0`
- `0x180012a40`

## callees

- `0x180004700`

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
0x180004700  mov     r8, rcx
0x180004703  mov     eax, 7FFFFFFEh
0x180004708  test    rdx, rdx
0x18000470b  jz      short loc_18000472B
0x18000470d  test    rax, rax
0x180004710  jz      short loc_18000472B
0x180004712  mov     cl, [r9]
0x180004715  test    cl, cl
0x180004717  jz      short loc_18000472B
0x180004719  mov     [r8], cl
0x18000471c  inc     r9
0x18000471f  inc     r8
0x180004722  dec     rax
0x180004725  sub     rdx, 1
0x180004729  jnz     short loc_18000470D
0x18000472b  mov     rax, rdx
0x18000472e  lea     rcx, [r8-1]
0x180004732  neg     rax
0x180004735  sbb     eax, eax
0x180004737  not     eax
0x180004739  and     eax, 8007007Ah
0x18000473e  test    rdx, rdx
0x180004741  cmovnz  rcx, r8
0x180004745  mov     byte ptr [rcx], 0
0x180004748  retn
```
