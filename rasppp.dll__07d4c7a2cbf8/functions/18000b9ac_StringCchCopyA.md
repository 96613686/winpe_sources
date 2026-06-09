# StringCchCopyA

- ea: `0x18000b9ac`
- end: `0x18000b9ea`
- name: `StringCchCopyA`
- size: `62`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b310`
- `0x1800109cc`
- `0x180012dcc`
- `0x180015ae0`
- `0x180029d0c`
- `0x18002ce44`
- `0x18002cfb4`

## callees

- `0x18000b9ac`
- `0x18000b9f0`

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
0x18000b9ac  sub     rsp, 38h
0x18000b9b0  test    rdx, rdx
0x18000b9b3  jz      short loc_18000B9D8
0x18000b9b5  cmp     rdx, 7FFFFFFFh
0x18000b9bc  jbe     short loc_18000B9C5
0x18000b9be  mov     eax, 80070057h
0x18000b9c3  jmp     short loc_18000B9E2
0x18000b9c5  mov     r9, r8; pszSrc
0x18000b9c8  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x18000b9d1  call    StringCopyWorkerA
0x18000b9d6  jmp     short loc_18000B9E5
0x18000b9d8  mov     eax, 80070057h
0x18000b9dd  test    rdx, rdx
0x18000b9e0  jz      short loc_18000B9E5
0x18000b9e2  mov     byte ptr [rcx], 0
0x18000b9e5  add     rsp, 38h
0x18000b9e9  retn
```
