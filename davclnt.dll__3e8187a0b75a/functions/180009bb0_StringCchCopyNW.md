# StringCchCopyNW

- ea: `0x180009bb0`
- end: `0x180009bf8`
- name: `StringCchCopyNW`
- size: `72`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f048`
- `0x18000f690`

## callees

- `0x180007a00`
- `0x180009bb0`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)
{
  HRESULT result; // eax

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF && cchToCopy <= 0x7FFFFFFE )
    return StringCopyWorkerW(pszDest, cchDest, 0, pszSrc, cchToCopy);
  result = -2147024809;
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x180009bb0  sub     rsp, 38h
0x180009bb4  test    rdx, rdx
0x180009bb7  jz      short loc_180009BE4
0x180009bb9  cmp     rdx, 7FFFFFFFh
0x180009bc0  jbe     short loc_180009BC9
0x180009bc2  mov     eax, 80070057h
0x180009bc7  jmp     short loc_180009BEE
0x180009bc9  cmp     r9, 7FFFFFFEh
0x180009bd0  ja      short loc_180009BC2
0x180009bd2  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x180009bd7  mov     r9, r8; pszSrc
0x180009bda  xor     r8d, r8d; pcchNewDestLength
0x180009bdd  call    StringCopyWorkerW
0x180009be2  jmp     short loc_180009BF3
0x180009be4  mov     eax, 80070057h
0x180009be9  test    rdx, rdx
0x180009bec  jz      short loc_180009BF3
0x180009bee  xor     edx, edx
0x180009bf0  mov     [rcx], dx
0x180009bf3  add     rsp, 38h
0x180009bf7  retn
```
