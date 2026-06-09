# StringCchPrintfW

- ea: `0x180014434`
- end: `0x1800144b7`
- name: `StringCchPrintfW`
- size: `131`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180027da8`
- `0x18002a350`
- `0x18002a7e0`
- `0x18002defc`
- `0x18002f784`

## callees

- `0x180001d4c`
- `0x180014434`

## pseudocode

```c
HRESULT StringCchPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  HRESULT v4; // edx
  size_t v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  if ( !cchDest )
    return -2147024809;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = cchDest - 1;
    v6 = vsnwprintf(pszDest, cchDest - 1, pszFormat, Args);
    if ( v6 < 0 || v6 > v5 )
    {
      v4 = -2147024774;
      pszDest[v5] = 0;
    }
    else
    {
      v4 = 0;
      if ( v6 == v5 )
        pszDest[v5] = 0;
    }
  }
  else
  {
    v4 = -2147024809;
    *pszDest = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180014434  mov     [rsp+arg_10], r8
0x180014439  mov     qword ptr [rsp+Args], r9
0x18001443e  push    rbx
0x18001443f  push    rdi
0x180014440  sub     rsp, 38h
0x180014444  mov     rax, rdx
0x180014447  mov     rdi, rcx
0x18001444a  test    rdx, rdx
0x18001444d  jz      short loc_18001449F
0x18001444f  cmp     rax, 7FFFFFFFh
0x180014455  jbe     short loc_18001445E
0x180014457  mov     edx, 80070057h
0x18001445c  jmp     short loc_1800144A9
0x18001445e  lea     rbx, [rdx-1]
0x180014462  mov     [rsp+48h+var_28], 0
0x18001446b  mov     rdx, rbx; BufferCount
0x18001446e  lea     r9, [rsp+48h+Args]; Args
0x180014473  call    _vsnwprintf
0x180014478  test    eax, eax
0x18001447a  js      short loc_180014492
0x18001447c  cdqe
0x18001447e  cmp     rax, rbx
0x180014481  ja      short loc_180014492
0x180014483  xor     edx, edx
0x180014485  cmp     rax, rbx
0x180014488  jnz     short loc_1800144AE
0x18001448a  xor     eax, eax
0x18001448c  mov     [rdi+rbx*2], ax
0x180014490  jmp     short loc_1800144AE
0x180014492  xor     eax, eax
0x180014494  mov     edx, 8007007Ah
0x180014499  mov     [rdi+rbx*2], ax
0x18001449d  jmp     short loc_1800144AE
0x18001449f  mov     edx, 80070057h
0x1800144a4  test    rax, rax
0x1800144a7  jz      short loc_1800144AE
0x1800144a9  xor     ecx, ecx
0x1800144ab  mov     [rdi], cx
0x1800144ae  mov     eax, edx
0x1800144b0  add     rsp, 38h
0x1800144b4  pop     rdi
0x1800144b5  pop     rbx
0x1800144b6  retn
```
