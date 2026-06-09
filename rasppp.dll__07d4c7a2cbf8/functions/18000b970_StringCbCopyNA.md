# StringCbCopyNA

- ea: `0x18000b970`
- end: `0x18000b9a4`
- name: `StringCbCopyNA`
- size: `52`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_PCNZCH pszSrc, size_t cbToCopy)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a610`
- `0x180023ef4`
- `0x180026a5c`

## callees

- `0x18000b970`
- `0x18000b9f0`

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
0x18000b970  sub     rsp, 38h
0x18000b974  lea     rax, [rdx-1]
0x18000b978  mov     r10d, 7FFFFFFEh
0x18000b97e  cmp     rax, r10
0x18000b981  ja      short loc_18000B98B
0x18000b983  cmp     r9, r10
0x18000b986  jbe     short loc_18000B995
0x18000b988  mov     byte ptr [rcx], 0
0x18000b98b  mov     eax, 80070057h
0x18000b990  add     rsp, 38h
0x18000b994  retn
0x18000b995  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x18000b99a  mov     r9, r8; pszSrc
0x18000b99d  call    StringCopyWorkerA
0x18000b9a2  jmp     short loc_18000B990
```
