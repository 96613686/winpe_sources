# StringCchCopyNW

- ea: `0x180005680`
- end: `0x1800056cb`
- name: `StringCchCopyNW`
- size: `75`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800054ac`

## callees

- `0x180005680`
- `0x180005720`

## pseudocode

```c
HRESULT __stdcall StringCchCopyNW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)
{
  HRESULT v4; // edx

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF && cchToCopy <= 0x7FFFFFFE )
    return StringCopyWorkerW(pszDest, cchDest, (size_t *)pszSrc, pszSrc, cchToCopy);
  v4 = -2147024809;
  *pszDest = 0;
  return v4;
}

```

## disassembly

```asm
0x180005680  sub     rsp, 38h
0x180005684  mov     rax, rdx
0x180005687  test    rdx, rdx
0x18000568a  jz      short loc_1800056B5
0x18000568c  cmp     rax, 7FFFFFFFh
0x180005692  jbe     short loc_18000569B
0x180005694  mov     edx, 80070057h; cchDest
0x180005699  jmp     short loc_1800056BF
0x18000569b  cmp     r9, 7FFFFFFEh
0x1800056a2  ja      short loc_180005694
0x1800056a4  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x1800056a9  mov     r9, r8; pszSrc
0x1800056ac  call    StringCopyWorkerW
0x1800056b1  mov     edx, eax
0x1800056b3  jmp     short loc_1800056C4
0x1800056b5  mov     edx, 80070057h
0x1800056ba  test    rax, rax
0x1800056bd  jz      short loc_1800056C4
0x1800056bf  xor     eax, eax
0x1800056c1  mov     [rcx], ax
0x1800056c4  mov     eax, edx
0x1800056c6  add     rsp, 38h
0x1800056ca  retn
```
