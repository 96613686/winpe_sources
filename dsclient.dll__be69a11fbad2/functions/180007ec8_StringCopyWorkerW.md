# StringCopyWorkerW

- ea: `0x180007ec8`
- end: `0x180007f19`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007df4`
- `0x180007e40`

## callees

- `0x180007ec8`

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
0x180007ec8  xor     r10d, r10d
0x180007ecb  mov     r8, rdx
0x180007ece  mov     eax, 7FFFFFFEh
0x180007ed3  test    rdx, rdx
0x180007ed6  jz      short loc_180007EFA
0x180007ed8  test    rax, rax
0x180007edb  jz      short loc_180007EFA
0x180007edd  movzx   edx, word ptr [r9]
0x180007ee1  test    dx, dx
0x180007ee4  jz      short loc_180007EFA
0x180007ee6  mov     [rcx], dx
0x180007ee9  add     r9, 2
0x180007eed  add     rcx, 2
0x180007ef1  dec     rax
0x180007ef4  sub     r8, 1
0x180007ef8  jnz     short loc_180007ED8
0x180007efa  mov     rax, r8
0x180007efd  lea     rdx, [rcx-2]
0x180007f01  neg     rax
0x180007f04  sbb     eax, eax
0x180007f06  not     eax
0x180007f08  and     eax, 8007007Ah
0x180007f0d  test    r8, r8
0x180007f10  cmovnz  rdx, rcx
0x180007f14  mov     [rdx], r10w
0x180007f18  retn
```
