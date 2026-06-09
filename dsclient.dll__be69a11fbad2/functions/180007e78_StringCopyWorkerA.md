# StringCopyWorkerA

- ea: `0x180007e78`
- end: `0x180007ec1`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b2c`

## callees

- `0x180007e78`

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
  STRSAFE_LPSTR v7; // rcx
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
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180007e78  mov     r8, rcx
0x180007e7b  mov     eax, 7FFFFFFEh
0x180007e80  test    rdx, rdx
0x180007e83  jz      short loc_180007EA3
0x180007e85  test    rax, rax
0x180007e88  jz      short loc_180007EA3
0x180007e8a  mov     cl, [r9]
0x180007e8d  test    cl, cl
0x180007e8f  jz      short loc_180007EA3
0x180007e91  mov     [r8], cl
0x180007e94  inc     r9
0x180007e97  inc     r8
0x180007e9a  dec     rax
0x180007e9d  sub     rdx, 1
0x180007ea1  jnz     short loc_180007E85
0x180007ea3  mov     rax, rdx
0x180007ea6  lea     rcx, [r8-1]
0x180007eaa  neg     rax
0x180007ead  sbb     eax, eax
0x180007eaf  not     eax
0x180007eb1  and     eax, 8007007Ah
0x180007eb6  test    rdx, rdx
0x180007eb9  cmovnz  rcx, r8
0x180007ebd  mov     byte ptr [rcx], 0
0x180007ec0  retn
```
