# StringCchCopyA

- ea: `0x18000bdd0`
- end: `0x18000be0f`
- name: `StringCchCopyA`
- size: `63`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b720`
- `0x180010f00`
- `0x18001348c`
- `0x180016260`
- `0x18002aca4`
- `0x18002dfa8`
- `0x18002e12c`

## callees

- `0x18000bdd0`
- `0x18000be18`

## pseudocode

```c
HRESULT __stdcall StringCchCopyA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringCopyWorkerA(pszDest, cchDest, (size_t *)pszSrc, pszSrc, 0x7FFFFFFEu);
  result = -2147024809;
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x18000bdd0  sub     rsp, 38h
0x18000bdd4  test    rdx, rdx
0x18000bdd7  jz      short loc_18000BDFC
0x18000bdd9  cmp     rdx, 7FFFFFFFh
0x18000bde0  jbe     short loc_18000BDE9
0x18000bde2  mov     eax, 80070057h
0x18000bde7  jmp     short loc_18000BE06
0x18000bde9  mov     r9, r8; pszSrc
0x18000bdec  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x18000bdf5  call    StringCopyWorkerA
0x18000bdfa  jmp     short loc_18000BE09
0x18000bdfc  mov     eax, 80070057h
0x18000be01  test    rdx, rdx
0x18000be04  jz      short loc_18000BE09
0x18000be06  mov     byte ptr [rcx], 0
0x18000be09  add     rsp, 38h
0x18000be0d  retn
```
