# StringCchPrintfW

- ea: `0x18000d510`
- end: `0x18000d56d`
- name: `StringCchPrintfW`
- size: `93`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180009060`
- `0x18000f090`
- `0x18000f2a0`

## callees

- `0x18000d510`
- `0x18000d574`

## pseudocode

```c
HRESULT StringCchPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  HRESULT v3; // edx
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, pszFormat);
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
    return StringVPrintfWorkerW(pszDest, cchDest, (size_t *)pszFormat, pszFormat, va);
  v3 = -2147024809;
  *pszDest = 0;
  return v3;
}

```

## disassembly

```asm
0x18000d510  mov     [rsp+arg_10], r8
0x18000d515  mov     qword ptr [rsp+arg_18], r9
0x18000d51a  sub     rsp, 48h
0x18000d51e  mov     rax, rdx
0x18000d521  test    rdx, rdx
0x18000d524  jz      short loc_18000D557
0x18000d526  cmp     rax, 7FFFFFFFh
0x18000d52c  jbe     short loc_18000D535
0x18000d52e  mov     edx, 80070057h
0x18000d533  jmp     short loc_18000D561
0x18000d535  lea     rdx, [rsp+48h+arg_18]
0x18000d53a  mov     [rsp+48h+var_18], 0
0x18000d543  mov     [rsp+48h+argList], rdx; argList
0x18000d548  mov     r9, r8; pszFormat
0x18000d54b  mov     rdx, rax; cchDest
0x18000d54e  call    StringVPrintfWorkerW
0x18000d553  mov     edx, eax
0x18000d555  jmp     short loc_18000D566
0x18000d557  mov     edx, 80070057h
0x18000d55c  test    rax, rax
0x18000d55f  jz      short loc_18000D566
0x18000d561  xor     eax, eax
0x18000d563  mov     [rcx], ax
0x18000d566  mov     eax, edx
0x18000d568  add     rsp, 48h
0x18000d56c  retn
```
