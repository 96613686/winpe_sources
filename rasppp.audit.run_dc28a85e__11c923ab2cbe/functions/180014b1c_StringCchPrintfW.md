# StringCchPrintfW

- ea: `0x180014b1c`
- end: `0x180014ba0`
- name: `StringCchPrintfW`
- size: `132`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180028c68`
- `0x18002b304`
- `0x18002b7d4`
- `0x18002f22c`
- `0x180030bec`

## callees

- `0x180001d4c`
- `0x180014b1c`

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
0x180014b1c  mov     [rsp+arg_10], r8
0x180014b21  mov     qword ptr [rsp+Args], r9
0x180014b26  push    rbx
0x180014b27  push    rdi
0x180014b28  sub     rsp, 38h
0x180014b2c  mov     rax, rdx
0x180014b2f  mov     rdi, rcx
0x180014b32  test    rdx, rdx
0x180014b35  jz      short loc_180014B87
0x180014b37  cmp     rax, 7FFFFFFFh
0x180014b3d  jbe     short loc_180014B46
0x180014b3f  mov     edx, 80070057h
0x180014b44  jmp     short loc_180014B91
0x180014b46  lea     rbx, [rdx-1]
0x180014b4a  mov     [rsp+48h+var_28], 0
0x180014b53  mov     rdx, rbx; BufferCount
0x180014b56  lea     r9, [rsp+48h+Args]; Args
0x180014b5b  call    _vsnwprintf
0x180014b60  test    eax, eax
0x180014b62  js      short loc_180014B7A
0x180014b64  cdqe
0x180014b66  cmp     rax, rbx
0x180014b69  ja      short loc_180014B7A
0x180014b6b  xor     edx, edx
0x180014b6d  cmp     rax, rbx
0x180014b70  jnz     short loc_180014B96
0x180014b72  xor     eax, eax
0x180014b74  mov     [rdi+rbx*2], ax
0x180014b78  jmp     short loc_180014B96
0x180014b7a  xor     eax, eax
0x180014b7c  mov     edx, 8007007Ah
0x180014b81  mov     [rdi+rbx*2], ax
0x180014b85  jmp     short loc_180014B96
0x180014b87  mov     edx, 80070057h
0x180014b8c  test    rax, rax
0x180014b8f  jz      short loc_180014B96
0x180014b91  xor     ecx, ecx
0x180014b93  mov     [rdi], cx
0x180014b96  mov     eax, edx
0x180014b98  add     rsp, 38h
0x180014b9c  pop     rdi
0x180014b9d  pop     rbx
0x180014b9e  retn
```
