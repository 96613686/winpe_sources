# StringCopyWorkerA

- ea: `0x1800141e0`
- end: `0x180014229`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023280`

## callees

- `0x1800141e0`

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
0x1800141e0  mov     r10, rcx
0x1800141e3  mov     eax, 7FFFFFFEh
0x1800141e8  test    rdx, rdx
0x1800141eb  jz      short loc_180014210
0x1800141ed  nop     dword ptr [rax]
0x1800141f0  test    rax, rax
0x1800141f3  jz      short loc_180014210
0x1800141f5  movzx   r8d, byte ptr [r9]
0x1800141f9  test    r8b, r8b
0x1800141fc  jz      short loc_180014210
0x1800141fe  mov     [r10], r8b
0x180014201  inc     r9
0x180014204  inc     r10
0x180014207  dec     rax
0x18001420a  sub     rdx, 1
0x18001420e  jnz     short loc_1800141F0
0x180014210  xor     ecx, ecx
0x180014212  mov     eax, 8007007Ah
0x180014217  test    rdx, rdx
0x18001421a  cmovnz  eax, ecx
0x18001421d  lea     rcx, [r10-1]
0x180014221  cmovnz  rcx, r10
0x180014225  mov     byte ptr [rcx], 0
0x180014228  retn
```
