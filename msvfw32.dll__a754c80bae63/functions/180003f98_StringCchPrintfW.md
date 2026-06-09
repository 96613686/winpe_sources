# StringCchPrintfW

- ea: `0x180003f98`
- end: `0x18000401b`
- name: `StringCchPrintfW`
- size: `131`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e90`
- `0x1800031d0`
- `0x180004024`
- `0x1800047f0`
- `0x1800068bc`
- `0x180006cf0`
- `0x18000be48`
- `0x18000f0b8`
- `0x180010884`
- `0x180010aa4`
- `0x180010cc0`
- `0x1800129a0`
- `0x180014adc`
- `0x1800153a4`

## callees

- `0x180001d70`
- `0x180003f98`

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
0x180003f98  mov     [rsp+arg_10], r8
0x180003f9d  mov     qword ptr [rsp+Args], r9
0x180003fa2  push    rbx
0x180003fa3  push    rdi
0x180003fa4  sub     rsp, 38h
0x180003fa8  mov     rax, rdx
0x180003fab  mov     rdi, rcx
0x180003fae  test    rdx, rdx
0x180003fb1  jz      short loc_180004003
0x180003fb3  cmp     rax, 7FFFFFFFh
0x180003fb9  jbe     short loc_180003FC2
0x180003fbb  mov     edx, 80070057h
0x180003fc0  jmp     short loc_18000400D
0x180003fc2  lea     rbx, [rdx-1]
0x180003fc6  mov     [rsp+48h+var_28], 0
0x180003fcf  mov     rdx, rbx; BufferCount
0x180003fd2  lea     r9, [rsp+48h+Args]; Args
0x180003fd7  call    _vsnwprintf
0x180003fdc  test    eax, eax
0x180003fde  js      short loc_180003FF6
0x180003fe0  cdqe
0x180003fe2  cmp     rax, rbx
0x180003fe5  ja      short loc_180003FF6
0x180003fe7  xor     edx, edx
0x180003fe9  cmp     rax, rbx
0x180003fec  jnz     short loc_180004012
0x180003fee  xor     eax, eax
0x180003ff0  mov     [rdi+rbx*2], ax
0x180003ff4  jmp     short loc_180004012
0x180003ff6  xor     eax, eax
0x180003ff8  mov     edx, 8007007Ah
0x180003ffd  mov     [rdi+rbx*2], ax
0x180004001  jmp     short loc_180004012
0x180004003  mov     edx, 80070057h
0x180004008  test    rax, rax
0x18000400b  jz      short loc_180004012
0x18000400d  xor     ecx, ecx
0x18000400f  mov     [rdi], cx
0x180004012  mov     eax, edx
0x180004014  add     rsp, 38h
0x180004018  pop     rdi
0x180004019  pop     rbx
0x18000401a  retn
```
