# StringCopyWorkerW

- ea: `0x180014c88`
- end: `0x180014cd9`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008cb8`

## callees

- `0x180014c88`

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
0x180014c88  xor     r10d, r10d
0x180014c8b  mov     r8, rdx
0x180014c8e  mov     eax, 7FFFFFFEh
0x180014c93  test    rdx, rdx
0x180014c96  jz      short loc_180014CBA
0x180014c98  test    rax, rax
0x180014c9b  jz      short loc_180014CBA
0x180014c9d  movzx   edx, word ptr [r9]
0x180014ca1  test    dx, dx
0x180014ca4  jz      short loc_180014CBA
0x180014ca6  mov     [rcx], dx
0x180014ca9  add     r9, 2
0x180014cad  add     rcx, 2
0x180014cb1  dec     rax
0x180014cb4  sub     r8, 1
0x180014cb8  jnz     short loc_180014C98
0x180014cba  mov     rax, r8
0x180014cbd  lea     rdx, [rcx-2]
0x180014cc1  neg     rax
0x180014cc4  sbb     eax, eax
0x180014cc6  not     eax
0x180014cc8  and     eax, 8007007Ah
0x180014ccd  test    r8, r8
0x180014cd0  cmovnz  rdx, rcx
0x180014cd4  mov     [rdx], r10w
0x180014cd8  retn
```
