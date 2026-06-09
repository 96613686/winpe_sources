# StringCchCopyW

- ea: `0x140053878`
- end: `0x1400538b5`
- name: `StringCchCopyW`
- size: `61`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14005d97c`
- `0x14007e378`
- `0x1400821c0`

## callees

- `0x140053878`
- `0x1400538bc`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  HRESULT v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringCopyWorkerW(pszDest, cchDest, (size_t *)pszSrc, pszSrc, v5);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x140053878  sub     rsp, 38h
0x14005387c  mov     rax, rdx
0x14005387f  test    rdx, rdx
0x140053882  jz      short loc_1400538A4
0x140053884  cmp     rax, 7FFFFFFFh
0x14005388a  ja      short loc_14005389D
0x14005388c  mov     r9, r8; pszSrc
0x14005388f  call    StringCopyWorkerW
0x140053894  mov     edx, eax
0x140053896  mov     eax, edx
0x140053898  add     rsp, 38h
0x14005389c  retn
0x14005389d  mov     edx, 80070057h
0x1400538a2  jmp     short loc_1400538AE
0x1400538a4  mov     edx, 80070057h
0x1400538a9  test    rax, rax
0x1400538ac  jz      short loc_140053896
0x1400538ae  xor     eax, eax
0x1400538b0  mov     [rcx], ax
0x1400538b3  jmp     short loc_140053896
```
