# StringCchCopyNW

- ea: `0x18000222c`
- end: `0x180002277`
- name: `StringCchCopyNW`
- size: `75`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000241c`
- `0x1800031d0`
- `0x18000fe2c`
- `0x180010cc0`
- `0x180016050`

## callees

- `0x18000222c`
- `0x18000231c`

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
0x18000222c  sub     rsp, 38h
0x180002230  mov     rax, rdx
0x180002233  test    rdx, rdx
0x180002236  jz      short loc_180002261
0x180002238  cmp     rax, 7FFFFFFFh
0x18000223e  jbe     short loc_180002247
0x180002240  mov     edx, 80070057h; cchDest
0x180002245  jmp     short loc_18000226B
0x180002247  cmp     r9, 7FFFFFFEh
0x18000224e  ja      short loc_180002240
0x180002250  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x180002255  mov     r9, r8; pszSrc
0x180002258  call    StringCopyWorkerW
0x18000225d  mov     edx, eax
0x18000225f  jmp     short loc_180002270
0x180002261  mov     edx, 80070057h
0x180002266  test    rax, rax
0x180002269  jz      short loc_180002270
0x18000226b  xor     eax, eax
0x18000226d  mov     [rcx], ax
0x180002270  mov     eax, edx
0x180002272  add     rsp, 38h
0x180002276  retn
```
