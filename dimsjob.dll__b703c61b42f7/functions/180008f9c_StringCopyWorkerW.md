# StringCopyWorkerW

- ea: `0x180008f9c`
- end: `0x180008fed`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005fd8`
- `0x180008ebc`
- `0x180009374`

## callees

- `0x180008f9c`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v5; // r8
  __int64 i; // rax
  STRSAFE_LPWSTR v7; // rdx
  HRESULT result; // eax

  v5 = cchDest;
  for ( i = 2147483646; v5; --v5 )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  v7 = pszDest - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180008f9c  xor     r10d, r10d
0x180008f9f  mov     r8, rdx
0x180008fa2  mov     eax, 7FFFFFFEh
0x180008fa7  test    rdx, rdx
0x180008faa  jz      short loc_180008FCE
0x180008fac  test    rax, rax
0x180008faf  jz      short loc_180008FCE
0x180008fb1  movzx   edx, word ptr [r9]
0x180008fb5  test    dx, dx
0x180008fb8  jz      short loc_180008FCE
0x180008fba  mov     [rcx], dx
0x180008fbd  add     r9, 2
0x180008fc1  add     rcx, 2
0x180008fc5  dec     rax
0x180008fc8  sub     r8, 1
0x180008fcc  jnz     short loc_180008FAC
0x180008fce  mov     rax, r8
0x180008fd1  lea     rdx, [rcx-2]
0x180008fd5  neg     rax
0x180008fd8  sbb     eax, eax
0x180008fda  not     eax
0x180008fdc  and     eax, 8007007Ah
0x180008fe1  test    r8, r8
0x180008fe4  cmovnz  rdx, rcx
0x180008fe8  mov     [rdx], r10w
0x180008fec  retn
```
