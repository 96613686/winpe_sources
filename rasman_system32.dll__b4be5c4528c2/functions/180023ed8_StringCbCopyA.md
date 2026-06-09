# StringCbCopyA

- ea: `0x180023ed8`
- end: `0x180023eef`
- name: `StringCbCopyA`
- size: `23`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800030d0`

## callees

- `0x180014a90`

## pseudocode

```c
HRESULT __stdcall StringCbCopyA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)
{
  size_t v4; // [rsp+20h] [rbp-18h]

  return StringCopyWorkerA(pszDest, 0x81u, (size_t *)pszSrc, pszSrc, v4);
}

```

## disassembly

```asm
0x180023ed8  sub     rsp, 38h
0x180023edc  mov     r9, r8; pszSrc
0x180023edf  mov     edx, 81h; cchDest
0x180023ee4  call    StringCopyWorkerA
0x180023ee9  add     rsp, 38h
0x180023eed  retn
```
