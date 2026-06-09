# StringCchCopyW

- ea: `0x180002280`
- end: `0x1800022c6`
- name: `StringCchCopyW`
- size: `70`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fd8`
- `0x180002e90`
- `0x1800031d0`
- `0x180003bf0`
- `0x180003ca0`
- `0x1800043b0`
- `0x18000be48`
- `0x18000c300`
- `0x18000f0b8`
- `0x18000fe2c`
- `0x180010cc0`
- `0x180012ac4`
- `0x180013edc`
- `0x1800149d4`
- `0x180014adc`
- `0x180015234`

## callees

- `0x180002280`
- `0x18000231c`

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
0x180002280  sub     rsp, 38h
0x180002284  mov     rax, rdx
0x180002287  test    rdx, rdx
0x18000228a  jz      short loc_1800022B0
0x18000228c  cmp     rax, 7FFFFFFFh
0x180002292  jbe     short loc_18000229B
0x180002294  mov     edx, 80070057h; cchDest
0x180002299  jmp     short loc_1800022BA
0x18000229b  mov     r9, r8; pszSrc
0x18000229e  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x1800022a7  call    StringCopyWorkerW
0x1800022ac  mov     edx, eax
0x1800022ae  jmp     short loc_1800022BF
0x1800022b0  mov     edx, 80070057h
0x1800022b5  test    rax, rax
0x1800022b8  jz      short loc_1800022BF
0x1800022ba  xor     eax, eax
0x1800022bc  mov     [rcx], ax
0x1800022bf  mov     eax, edx
0x1800022c1  add     rsp, 38h
0x1800022c5  retn
```
