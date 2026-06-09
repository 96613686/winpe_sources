# StringCchCopyW

- ea: `0x1800056d4`
- end: `0x18000571a`
- name: `StringCchCopyW`
- size: `70`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180001a80`
- `0x180002250`
- `0x1800047f0`
- `0x18000542c`
- `0x1800054ac`
- `0x180005d70`
- `0x18000627c`
- `0x18000688c`
- `0x180006d58`
- `0x180007288`

## callees

- `0x1800056d4`
- `0x180005720`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT v3; // edx

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringCopyWorkerW(pszDest, cchDest, (size_t *)pszSrc, pszSrc, 0x7FFFFFFEu);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x1800056d4  sub     rsp, 38h
0x1800056d8  mov     rax, rdx
0x1800056db  test    rdx, rdx
0x1800056de  jz      short loc_180005704
0x1800056e0  cmp     rax, 7FFFFFFFh
0x1800056e6  jbe     short loc_1800056EF
0x1800056e8  mov     edx, 80070057h; cchDest
0x1800056ed  jmp     short loc_18000570E
0x1800056ef  mov     r9, r8; pszSrc
0x1800056f2  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x1800056fb  call    StringCopyWorkerW
0x180005700  mov     edx, eax
0x180005702  jmp     short loc_180005713
0x180005704  mov     edx, 80070057h
0x180005709  test    rax, rax
0x18000570c  jz      short loc_180005713
0x18000570e  xor     eax, eax
0x180005710  mov     [rcx], ax
0x180005713  mov     eax, edx
0x180005715  add     rsp, 38h
0x180005719  retn
```
