# StringCopyWorkerA

- ea: `0x180014a90`
- end: `0x180014ad9`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023ed8`

## callees

- `0x180014a90`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  __int64 i; // rax
  HRESULT result; // eax
  STRSAFE_LPSTR v8; // rcx

  for ( i = 2147483646; cchDest; --cchDest )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  result = -2147024774;
  if ( cchDest )
    result = 0;
  v8 = pszDest - 1;
  if ( cchDest )
    v8 = pszDest;
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x180014a90  mov     r10, rcx
0x180014a93  mov     eax, 7FFFFFFEh
0x180014a98  test    rdx, rdx
0x180014a9b  jz      short loc_180014AC0
0x180014a9d  nop     dword ptr [rax]
0x180014aa0  test    rax, rax
0x180014aa3  jz      short loc_180014AC0
0x180014aa5  movzx   r8d, byte ptr [r9]
0x180014aa9  test    r8b, r8b
0x180014aac  jz      short loc_180014AC0
0x180014aae  mov     [r10], r8b
0x180014ab1  inc     r9
0x180014ab4  inc     r10
0x180014ab7  dec     rax
0x180014aba  sub     rdx, 1
0x180014abe  jnz     short loc_180014AA0
0x180014ac0  xor     ecx, ecx
0x180014ac2  mov     eax, 8007007Ah
0x180014ac7  test    rdx, rdx
0x180014aca  cmovnz  eax, ecx
0x180014acd  lea     rcx, [r10-1]
0x180014ad1  cmovnz  rcx, r10
0x180014ad5  mov     byte ptr [rcx], 0
0x180014ad8  retn
```
