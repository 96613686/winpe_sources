# StringCchCopyW

- ea: `0x180002e14`
- end: `0x180002e43`
- name: `StringCchCopyW`
- size: `47`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `25`
- callee_count: `3`
- tags: ``

## callers

- `0x1800017c0`
- `0x180002d20`
- `0x180004800`
- `0x180004c14`
- `0x180004db0`
- `0x180004e80`
- `0x1800052b8`
- `0x180005fd4`
- `0x180006184`
- `0x180007628`
- `0x180007c0c`
- `0x18000844c`
- `0x18000a66c`
- `0x18000dc70`
- `0x180010140`
- `0x18001085c`
- `0x180010a4c`
- `0x180011d48`
- `0x180012a78`
- `0x180012b14`
- `0x180012e90`
- `0x180013270`
- `0x1800135e4`
- `0x1800136b0`
- `0x18001418c`

## callees

- `0x180002e14`
- `0x180002ea0`
- `0x180002f60`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v3; // rdx
  wchar_t *v4; // rcx
  size_t *v5; // r8
  int v6; // r9d
  size_t v8; // [rsp+20h] [rbp-18h]

  v6 = StringValidateDestW(pszDest, cchDest, (const size_t)pszSrc);
  if ( v6 >= 0 )
    return StringCopyWorkerW(v4, v3, v5, (STRSAFE_PCNZWCH)v5, v8);
  if ( v3 )
    *v4 = 0;
  return v6;
}

```

## disassembly

```asm
0x180002e14  sub     rsp, 38h
0x180002e18  call    StringValidateDestW
0x180002e1d  mov     r9d, eax
0x180002e20  test    eax, eax
0x180002e22  js      short loc_180002E31
0x180002e24  mov     r9, r8; pszSrc
0x180002e27  call    StringCopyWorkerW
0x180002e2c  mov     r9d, eax
0x180002e2f  jmp     short loc_180002E3B
0x180002e31  test    rdx, rdx
0x180002e34  jz      short loc_180002E3B
0x180002e36  xor     eax, eax
0x180002e38  mov     [rcx], ax
0x180002e3b  mov     eax, r9d
0x180002e3e  add     rsp, 38h
0x180002e42  retn
```
