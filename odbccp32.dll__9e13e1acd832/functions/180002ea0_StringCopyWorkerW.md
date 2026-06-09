# StringCopyWorkerW

- ea: `0x180002ea0`
- end: `0x180002eed`
- name: `StringCopyWorkerW`
- size: `77`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e14`
- `0x180004afc`

## callees

- `0x180002ea0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  __int64 i; // rax
  STRSAFE_LPWSTR v7; // r8
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
  result = -2147024774;
  if ( cchDest )
  {
    v7 = pszDest;
    result = 0;
  }
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180002ea0  mov     r10, rcx
0x180002ea3  mov     eax, 7FFFFFFEh
0x180002ea8  test    rdx, rdx
0x180002eab  jz      short loc_180002ED3
0x180002ead  nop     dword ptr [rax]
0x180002eb0  test    rax, rax
0x180002eb3  jz      short loc_180002ED3
0x180002eb5  movzx   ecx, word ptr [r9]
0x180002eb9  test    cx, cx
0x180002ebc  jz      short loc_180002ED3
0x180002ebe  mov     [r10], cx
0x180002ec2  add     r9, 2
0x180002ec6  add     r10, 2
0x180002eca  dec     rax
0x180002ecd  sub     rdx, 1
0x180002ed1  jnz     short loc_180002EB0
0x180002ed3  xor     ecx, ecx
0x180002ed5  lea     r8, [r10-2]
0x180002ed9  test    rdx, rdx
0x180002edc  mov     eax, 8007007Ah
0x180002ee1  cmovnz  r8, r10
0x180002ee5  cmovnz  eax, ecx
0x180002ee8  mov     [r8], cx
0x180002eec  retn
```
