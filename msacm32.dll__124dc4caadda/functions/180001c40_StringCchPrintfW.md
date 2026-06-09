# StringCchPrintfW

- ea: `0x180001c40`
- end: `0x180001cbd`
- name: `StringCchPrintfW`
- size: `125`
- prototype: `HRESULT(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180001210`
- `0x180001570`
- `0x180001ad0`
- `0x180004b70`
- `0x1800079f0`
- `0x180007cf0`
- `0x18000f644`
- `0x180012020`

## callees

- `0x180001c40`
- `0x180009b08`

## pseudocode

```c
HRESULT StringCchPrintfW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszFormat, ...)
{
  size_t v4; // rbx
  HRESULT v5; // edi
  int v6; // eax
  HRESULT result; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  if ( !cchDest )
    return -2147024809;
  if ( cchDest > 0x7FFFFFFF )
  {
    result = -2147024809;
    *pszDest = 0;
  }
  else
  {
    v4 = cchDest - 1;
    v5 = 0;
    v6 = vsnwprintf(pszDest, cchDest - 1, pszFormat, Args);
    if ( v6 < 0 || v6 > v4 )
    {
      pszDest[v4] = 0;
      return -2147024774;
    }
    else if ( v6 == v4 )
    {
      pszDest[v4] = 0;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180001c40  mov     [rsp+arg_10], r8
0x180001c45  mov     qword ptr [rsp+Args], r9
0x180001c4a  push    rsi
0x180001c4b  push    rdi
0x180001c4c  sub     rsp, 38h
0x180001c50  mov     rsi, rcx
0x180001c53  test    rdx, rdx
0x180001c56  jz      short loc_180001CAC
0x180001c58  cmp     rdx, 7FFFFFFFh
0x180001c5f  ja      short loc_180001C9F
0x180001c61  mov     [rsp+48h+var_18], rbx
0x180001c66  lea     r9, [rsp+48h+Args]; Args
0x180001c6b  lea     rbx, [rdx-1]
0x180001c6f  xor     edi, edi
0x180001c71  mov     rdx, rbx; BufferCount
0x180001c74  call    _vsnwprintf
0x180001c79  test    eax, eax
0x180001c7b  js      short loc_180001C94
0x180001c7d  cdqe
0x180001c7f  cmp     rax, rbx
0x180001c82  ja      short loc_180001C94
0x180001c84  jz      short loc_180001CA6
0x180001c86  mov     rbx, [rsp+48h+var_18]
0x180001c8b  mov     eax, edi
0x180001c8d  add     rsp, 38h
0x180001c91  pop     rdi
0x180001c92  pop     rsi
0x180001c93  retn
0x180001c94  mov     [rsi+rbx*2], di
0x180001c98  mov     edi, 8007007Ah
0x180001c9d  jmp     short loc_180001C86
0x180001c9f  mov     eax, 80070057h
0x180001ca4  jmp     short loc_180001CB6
0x180001ca6  mov     [rsi+rbx*2], di
0x180001caa  jmp     short loc_180001C86
0x180001cac  mov     eax, 80070057h
0x180001cb1  test    rdx, rdx
0x180001cb4  jz      short loc_180001C8D
0x180001cb6  xor     edi, edi
0x180001cb8  mov     [rcx], di
0x180001cbb  jmp     short loc_180001C8D
```
