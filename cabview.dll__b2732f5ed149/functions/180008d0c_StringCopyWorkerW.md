# StringCopyWorkerW

- ea: `0x180008d0c`
- end: `0x180008d5d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008af8`
- `0x180008bf4`
- `0x180008c48`

## callees

- `0x180008d0c`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // r8
  STRSAFE_LPWSTR v7; // rdx
  HRESULT result; // eax

  for ( i = cchDest; i; --i )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
  }
  v7 = pszDest - 1;
  result = i == 0 ? 0x8007007A : 0;
  if ( i )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180008d0c  xor     r10d, r10d
0x180008d0f  mov     r8, rdx
0x180008d12  test    rdx, rdx
0x180008d15  jz      short loc_180008D3E
0x180008d17  mov     rax, [rsp+cchToCopy]
0x180008d1c  test    rax, rax
0x180008d1f  jz      short loc_180008D3E
0x180008d21  movzx   edx, word ptr [r9]
0x180008d25  test    dx, dx
0x180008d28  jz      short loc_180008D3E
0x180008d2a  mov     [rcx], dx
0x180008d2d  add     r9, 2
0x180008d31  add     rcx, 2
0x180008d35  dec     rax
0x180008d38  sub     r8, 1
0x180008d3c  jnz     short loc_180008D1C
0x180008d3e  mov     rax, r8
0x180008d41  lea     rdx, [rcx-2]
0x180008d45  neg     rax
0x180008d48  sbb     eax, eax
0x180008d4a  not     eax
0x180008d4c  and     eax, 8007007Ah
0x180008d51  test    r8, r8
0x180008d54  cmovnz  rdx, rcx
0x180008d58  mov     [rdx], r10w
0x180008d5c  retn
```
