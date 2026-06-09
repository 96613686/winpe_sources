# StringCopyWorkerA

- ea: `0x1800022cc`
- end: `0x180002315`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e9c`
- `0x180002118`
- `0x18000eb40`

## callees

- `0x1800022cc`

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
0x1800022cc  mov     r8, rcx
0x1800022cf  mov     eax, 7FFFFFFEh
0x1800022d4  test    rdx, rdx
0x1800022d7  jz      short loc_1800022F7
0x1800022d9  test    rax, rax
0x1800022dc  jz      short loc_1800022F7
0x1800022de  mov     cl, [r9]
0x1800022e1  test    cl, cl
0x1800022e3  jz      short loc_1800022F7
0x1800022e5  mov     [r8], cl
0x1800022e8  inc     r9
0x1800022eb  inc     r8
0x1800022ee  dec     rax
0x1800022f1  sub     rdx, 1
0x1800022f5  jnz     short loc_1800022D9
0x1800022f7  mov     rax, rdx
0x1800022fa  lea     rcx, [r8-1]
0x1800022fe  neg     rax
0x180002301  sbb     eax, eax
0x180002303  not     eax
0x180002305  and     eax, 8007007Ah
0x18000230a  test    rdx, rdx
0x18000230d  cmovnz  rcx, r8
0x180002311  mov     byte ptr [rcx], 0
0x180002314  retn
```
