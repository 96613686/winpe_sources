# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000935c`
- end: `0x1800093cb`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `111`
- prototype: `__int64(unsigned __int16 *, size_t, size_t *, ...)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800051d8`
- `0x180006308`
- `0x180006498`

## callees

- `0x180004310`
- `0x18000935c`
- `0x180009474`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, size_t a2, size_t *a3, ...)
{
  unsigned int v4; // ecx
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringVPrintfWorkerW(a1, a2, a3, (STRSAFE_LPCWSTR)a3, va);
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18000935c  mov     [rsp+arg_10], r8
0x180009361  mov     qword ptr [rsp+arg_18], r9
0x180009366  sub     rsp, 48h
0x18000936a  mov     rax, cs:__security_cookie
0x180009371  xor     rax, rsp
0x180009374  mov     [rsp+48h+var_10], rax
0x180009379  xor     eax, eax
0x18000937b  mov     r10, rcx
0x18000937e  test    rdx, rdx
0x180009381  jz      short loc_1800093A9
0x180009383  cmp     rdx, 7FFFFFFFh
0x18000938a  jbe     short loc_180009393
0x18000938c  mov     ecx, 80070057h; pszDest
0x180009391  jmp     short loc_1800093B3
0x180009393  lea     rax, [rsp+48h+arg_18]
0x180009398  mov     r9, r8; pszFormat
0x18000939b  mov     [rsp+48h+argList], rax; argList
0x1800093a0  call    StringVPrintfWorkerW
0x1800093a5  mov     ecx, eax
0x1800093a7  jmp     short loc_1800093B7
0x1800093a9  mov     ecx, 80070057h
0x1800093ae  test    rdx, rdx
0x1800093b1  jz      short loc_1800093B7
0x1800093b3  mov     [r10], ax
0x1800093b7  mov     eax, ecx
0x1800093b9  mov     rcx, [rsp+48h+var_10]
0x1800093be  xor     rcx, rsp; StackCookie
0x1800093c1  call    __security_check_cookie
0x1800093c6  add     rsp, 48h
0x1800093ca  retn
```
