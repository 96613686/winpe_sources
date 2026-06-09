# StringCopyWorkerW

- ea: `0x180007640`
- end: `0x180007691`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004ffc`
- `0x180007560`
- `0x1800078c8`

## callees

- `0x180007640`

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
0x180007640  xor     r10d, r10d
0x180007643  mov     r8, rdx
0x180007646  mov     eax, 7FFFFFFEh
0x18000764b  test    rdx, rdx
0x18000764e  jz      short loc_180007672
0x180007650  test    rax, rax
0x180007653  jz      short loc_180007672
0x180007655  movzx   edx, word ptr [r9]
0x180007659  test    dx, dx
0x18000765c  jz      short loc_180007672
0x18000765e  mov     [rcx], dx
0x180007661  add     r9, 2
0x180007665  add     rcx, 2
0x180007669  dec     rax
0x18000766c  sub     r8, 1
0x180007670  jnz     short loc_180007650
0x180007672  mov     rax, r8
0x180007675  lea     rdx, [rcx-2]
0x180007679  neg     rax
0x18000767c  sbb     eax, eax
0x18000767e  not     eax
0x180007680  and     eax, 8007007Ah
0x180007685  test    r8, r8
0x180007688  cmovnz  rdx, rcx
0x18000768c  mov     [rdx], r10w
0x180007690  retn
```
