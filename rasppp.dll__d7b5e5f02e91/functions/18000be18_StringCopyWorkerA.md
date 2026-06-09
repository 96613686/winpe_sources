# StringCopyWorkerA

- ea: `0x18000be18`
- end: `0x18000be61`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bd94`
- `0x18000bdd0`

## callees

- `0x18000be18`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  STRSAFE_LPSTR v7; // rcx
  HRESULT result; // eax

  for ( ; cchDest; --cchDest )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
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
0x18000be18  mov     r8, rcx
0x18000be1b  test    rdx, rdx
0x18000be1e  jz      short loc_18000BE43
0x18000be20  mov     rax, [rsp+cchToCopy]
0x18000be25  test    rax, rax
0x18000be28  jz      short loc_18000BE43
0x18000be2a  mov     cl, [r9]
0x18000be2d  test    cl, cl
0x18000be2f  jz      short loc_18000BE43
0x18000be31  mov     [r8], cl
0x18000be34  inc     r9
0x18000be37  inc     r8
0x18000be3a  dec     rax
0x18000be3d  sub     rdx, 1
0x18000be41  jnz     short loc_18000BE25
0x18000be43  mov     rax, rdx
0x18000be46  lea     rcx, [r8-1]
0x18000be4a  neg     rax
0x18000be4d  sbb     eax, eax
0x18000be4f  not     eax
0x18000be51  and     eax, 8007007Ah
0x18000be56  test    rdx, rdx
0x18000be59  cmovnz  rcx, r8
0x18000be5d  mov     byte ptr [rcx], 0
0x18000be60  retn
```
