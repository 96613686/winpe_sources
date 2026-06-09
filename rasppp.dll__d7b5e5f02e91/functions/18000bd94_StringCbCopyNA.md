# StringCbCopyNA

- ea: `0x18000bd94`
- end: `0x18000bdc9`
- name: `StringCbCopyNA`
- size: `53`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_PCNZCH pszSrc, size_t cbToCopy)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a9f0`
- `0x180024c7c`
- `0x18002787c`

## callees

- `0x18000bd94`
- `0x18000be18`

## pseudocode

```c
HRESULT __stdcall StringCbCopyNA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_PCNZCH pszSrc, size_t cbToCopy)
{
  if ( cbDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  if ( cbToCopy > 0x7FFFFFFE )
  {
    *pszDest = 0;
    return -2147024809;
  }
  return StringCopyWorkerA(pszDest, cbDest, (size_t *)pszSrc, pszSrc, cbToCopy);
}

```

## disassembly

```asm
0x18000bd94  sub     rsp, 38h
0x18000bd98  lea     rax, [rdx-1]
0x18000bd9c  mov     r10d, 7FFFFFFEh
0x18000bda2  cmp     rax, r10
0x18000bda5  ja      short loc_18000BDAF
0x18000bda7  cmp     r9, r10
0x18000bdaa  jbe     short loc_18000BDBA
0x18000bdac  mov     byte ptr [rcx], 0
0x18000bdaf  mov     eax, 80070057h
0x18000bdb4  add     rsp, 38h
0x18000bdb8  retn
0x18000bdba  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x18000bdbf  mov     r9, r8; pszSrc
0x18000bdc2  call    StringCopyWorkerA
0x18000bdc7  jmp     short loc_18000BDB4
```
