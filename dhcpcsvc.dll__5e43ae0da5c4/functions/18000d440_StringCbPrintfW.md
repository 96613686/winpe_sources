# StringCbPrintfW

- ea: `0x18000d440`
- end: `0x18000d49d`
- name: `StringCbPrintfW`
- size: `93`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800042d4`
- `0x180006300`
- `0x180009060`
- `0x180009584`

## callees

- `0x18000d440`
- `0x18000d574`

## pseudocode

```c
HRESULT StringCbPrintfW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  HRESULT v3; // edx
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, pszFormat);
  if ( !(cbDest >> 1) )
    return -2147024809;
  if ( cbDest >> 1 <= 0x7FFFFFFF )
    return StringVPrintfWorkerW(pszDest, cbDest >> 1, (size_t *)pszFormat, pszFormat, va);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x18000d440  mov     [rsp+arg_10], r8
0x18000d445  mov     qword ptr [rsp+arg_18], r9
0x18000d44a  sub     rsp, 48h
0x18000d44e  mov     rax, rdx
0x18000d451  shr     rax, 1
0x18000d454  jz      short loc_18000D487
0x18000d456  cmp     rax, 7FFFFFFFh
0x18000d45c  jbe     short loc_18000D465
0x18000d45e  mov     edx, 80070057h
0x18000d463  jmp     short loc_18000D491
0x18000d465  lea     rdx, [rsp+48h+arg_18]
0x18000d46a  mov     [rsp+48h+var_18], 0
0x18000d473  mov     [rsp+48h+argList], rdx; argList
0x18000d478  mov     r9, r8; pszFormat
0x18000d47b  mov     rdx, rax; cchDest
0x18000d47e  call    StringVPrintfWorkerW
0x18000d483  mov     edx, eax
0x18000d485  jmp     short loc_18000D496
0x18000d487  mov     edx, 80070057h
0x18000d48c  test    rax, rax
0x18000d48f  jz      short loc_18000D496
0x18000d491  xor     eax, eax
0x18000d493  mov     [rcx], ax
0x18000d496  mov     eax, edx
0x18000d498  add     rsp, 48h
0x18000d49c  retn
```
