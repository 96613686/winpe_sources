# StringCopyWorkerW

- ea: `0x180006ba4`
- end: `0x180006bf5`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e00`
- `0x180006ac4`
- `0x180006c50`

## callees

- `0x180006ba4`

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
0x180006ba4  xor     r10d, r10d
0x180006ba7  mov     r8, rdx
0x180006baa  mov     eax, 7FFFFFFEh
0x180006baf  test    rdx, rdx
0x180006bb2  jz      short loc_180006BD6
0x180006bb4  test    rax, rax
0x180006bb7  jz      short loc_180006BD6
0x180006bb9  movzx   edx, word ptr [r9]
0x180006bbd  test    dx, dx
0x180006bc0  jz      short loc_180006BD6
0x180006bc2  mov     [rcx], dx
0x180006bc5  add     r9, 2
0x180006bc9  add     rcx, 2
0x180006bcd  dec     rax
0x180006bd0  sub     r8, 1
0x180006bd4  jnz     short loc_180006BB4
0x180006bd6  mov     rax, r8
0x180006bd9  lea     rdx, [rcx-2]
0x180006bdd  neg     rax
0x180006be0  sbb     eax, eax
0x180006be2  not     eax
0x180006be4  and     eax, 8007007Ah
0x180006be9  test    r8, r8
0x180006bec  cmovnz  rdx, rcx
0x180006bf0  mov     [rdx], r10w
0x180006bf4  retn
```
