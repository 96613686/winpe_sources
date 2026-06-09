# StringCbCopyW

- ea: `0x180031010`
- end: `0x18003102b`
- name: `StringCbCopyW`
- size: `27`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ffa4`

## callees

- `0x1800310c0`

## pseudocode

```c
HRESULT __stdcall StringCbCopyW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v4; // [rsp+20h] [rbp-18h]

  return StringCopyWorkerW(pszDest, 0x15u, (size_t *)pszSrc, L"0.0.0.0", v4);
}

```

## disassembly

```asm
0x180031010  sub     rsp, 38h
0x180031014  lea     r9, a0000; "0.0.0.0"
0x18003101b  mov     edx, 15h; cchDest
0x180031020  call    StringCopyWorkerW
0x180031025  add     rsp, 38h
0x180031029  retn
```
