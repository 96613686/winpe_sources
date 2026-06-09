# StringCopyWorkerW

- ea: `0x180007120`
- end: `0x180007171`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b40`
- `0x1800070d0`
- `0x18000fea0`

## callees

- `0x180007120`

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
0x180007120  xor     r10d, r10d
0x180007123  mov     r8, rdx
0x180007126  mov     eax, 7FFFFFFEh
0x18000712b  test    rdx, rdx
0x18000712e  jz      short loc_180007152
0x180007130  test    rax, rax
0x180007133  jz      short loc_180007152
0x180007135  movzx   edx, word ptr [r9]
0x180007139  test    dx, dx
0x18000713c  jz      short loc_180007152
0x18000713e  mov     [rcx], dx
0x180007141  add     r9, 2
0x180007145  add     rcx, 2
0x180007149  dec     rax
0x18000714c  sub     r8, 1
0x180007150  jnz     short loc_180007130
0x180007152  mov     rax, r8
0x180007155  lea     rdx, [rcx-2]
0x180007159  neg     rax
0x18000715c  sbb     eax, eax
0x18000715e  not     eax
0x180007160  and     eax, 8007007Ah
0x180007165  test    r8, r8
0x180007168  cmovnz  rdx, rcx
0x18000716c  mov     [rdx], r10w
0x180007170  retn
```
