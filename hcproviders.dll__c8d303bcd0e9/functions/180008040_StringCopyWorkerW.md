# StringCopyWorkerW

- ea: `0x180008040`
- end: `0x180008091`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000692c`
- `0x180007fc0`
- `0x180008098`

## callees

- `0x180008040`

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
0x180008040  xor     r10d, r10d
0x180008043  mov     r8, rdx
0x180008046  mov     eax, 7FFFFFFEh
0x18000804b  test    rdx, rdx
0x18000804e  jz      short loc_180008072
0x180008050  test    rax, rax
0x180008053  jz      short loc_180008072
0x180008055  movzx   edx, word ptr [r9]
0x180008059  test    dx, dx
0x18000805c  jz      short loc_180008072
0x18000805e  mov     [rcx], dx
0x180008061  add     r9, 2
0x180008065  add     rcx, 2
0x180008069  dec     rax
0x18000806c  sub     r8, 1
0x180008070  jnz     short loc_180008050
0x180008072  mov     rax, r8
0x180008075  lea     rdx, [rcx-2]
0x180008079  neg     rax
0x18000807c  sbb     eax, eax
0x18000807e  not     eax
0x180008080  and     eax, 8007007Ah
0x180008085  test    r8, r8
0x180008088  cmovnz  rdx, rcx
0x18000808c  mov     [rdx], r10w
0x180008090  retn
```
