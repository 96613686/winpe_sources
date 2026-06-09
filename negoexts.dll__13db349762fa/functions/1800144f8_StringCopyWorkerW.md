# StringCopyWorkerW

- ea: `0x1800144f8`
- end: `0x180014549`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800143d8`
- `0x180014424`

## callees

- `0x1800144f8`

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
0x1800144f8  xor     r10d, r10d
0x1800144fb  mov     r8, rdx
0x1800144fe  mov     eax, 7FFFFFFEh
0x180014503  test    rdx, rdx
0x180014506  jz      short loc_18001452A
0x180014508  test    rax, rax
0x18001450b  jz      short loc_18001452A
0x18001450d  movzx   edx, word ptr [r9]
0x180014511  test    dx, dx
0x180014514  jz      short loc_18001452A
0x180014516  mov     [rcx], dx
0x180014519  add     r9, 2
0x18001451d  add     rcx, 2
0x180014521  dec     rax
0x180014524  sub     r8, 1
0x180014528  jnz     short loc_180014508
0x18001452a  mov     rax, r8
0x18001452d  lea     rdx, [rcx-2]
0x180014531  neg     rax
0x180014534  sbb     eax, eax
0x180014536  not     eax
0x180014538  and     eax, 8007007Ah
0x18001453d  test    r8, r8
0x180014540  cmovnz  rdx, rcx
0x180014544  mov     [rdx], r10w
0x180014548  retn
```
