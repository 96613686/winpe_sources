# StringCchCopyA

- ea: `0x1800046c4`
- end: `0x1800046f9`
- name: `StringCchCopyA`
- size: `53`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039b8`
- `0x180014788`
- `0x180014904`

## callees

- `0x1800046c4`
- `0x180004700`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax
  size_t v4; // [rsp+20h] [rbp-18h]

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringCopyWorkerA(pszDest, cchDest, (size_t *)pszSrc, pszSrc, v4);
  result = -2147024809;
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x1800046c4  sub     rsp, 38h
0x1800046c8  test    rdx, rdx
0x1800046cb  jz      short loc_1800046EA
0x1800046cd  cmp     rdx, 7FFFFFFFh
0x1800046d4  ja      short loc_1800046E3
0x1800046d6  mov     r9, r8; pszSrc
0x1800046d9  call    StringCopyWorkerA
0x1800046de  add     rsp, 38h
0x1800046e2  retn
0x1800046e3  mov     eax, 80070057h
0x1800046e8  jmp     short loc_1800046F4
0x1800046ea  mov     eax, 80070057h
0x1800046ef  test    rdx, rdx
0x1800046f2  jz      short loc_1800046DE
0x1800046f4  mov     byte ptr [rcx], 0
0x1800046f7  jmp     short loc_1800046DE
```
