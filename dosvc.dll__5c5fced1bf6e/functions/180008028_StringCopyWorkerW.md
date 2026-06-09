# StringCopyWorkerW

- ea: `0x180008028`
- end: `0x180008079`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ebc`
- `0x180007f38`

## callees

- `0x180008028`

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
0x180008028  xor     r10d, r10d
0x18000802b  mov     r8, rdx
0x18000802e  mov     eax, 7FFFFFFEh
0x180008033  test    rdx, rdx
0x180008036  jz      short loc_18000805A
0x180008038  test    rax, rax
0x18000803b  jz      short loc_18000805A
0x18000803d  movzx   edx, word ptr [r9]
0x180008041  test    dx, dx
0x180008044  jz      short loc_18000805A
0x180008046  mov     [rcx], dx
0x180008049  add     r9, 2
0x18000804d  add     rcx, 2
0x180008051  dec     rax
0x180008054  sub     r8, 1
0x180008058  jnz     short loc_180008038
0x18000805a  mov     rax, r8
0x18000805d  lea     rdx, [rcx-2]
0x180008061  neg     rax
0x180008064  sbb     eax, eax
0x180008066  not     eax
0x180008068  and     eax, 8007007Ah
0x18000806d  test    r8, r8
0x180008070  cmovnz  rdx, rcx
0x180008074  mov     [rdx], r10w
0x180008078  retn
```
