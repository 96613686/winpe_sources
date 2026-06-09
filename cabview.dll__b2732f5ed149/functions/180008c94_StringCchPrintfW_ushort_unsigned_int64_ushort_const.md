# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180008c94`
- end: `0x180008d03`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `111`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800043f8`
- `0x180004564`
- `0x180004a70`
- `0x180011f90`

## callees

- `0x180002620`
- `0x180008c94`
- `0x180008d64`

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
0x180008c94  mov     [rsp+arg_10], r8
0x180008c99  mov     qword ptr [rsp+arg_18], r9
0x180008c9e  sub     rsp, 48h
0x180008ca2  mov     rax, cs:__security_cookie
0x180008ca9  xor     rax, rsp
0x180008cac  mov     [rsp+48h+var_10], rax
0x180008cb1  xor     eax, eax
0x180008cb3  mov     r10, rcx
0x180008cb6  test    rdx, rdx
0x180008cb9  jz      short loc_180008CE1
0x180008cbb  cmp     rdx, 7FFFFFFFh
0x180008cc2  jbe     short loc_180008CCB
0x180008cc4  mov     ecx, 80070057h; pszDest
0x180008cc9  jmp     short loc_180008CEB
0x180008ccb  lea     rax, [rsp+48h+arg_18]
0x180008cd0  mov     r9, r8; pszFormat
0x180008cd3  mov     [rsp+48h+argList], rax; argList
0x180008cd8  call    StringVPrintfWorkerW
0x180008cdd  mov     ecx, eax
0x180008cdf  jmp     short loc_180008CEF
0x180008ce1  mov     ecx, 80070057h
0x180008ce6  test    rdx, rdx
0x180008ce9  jz      short loc_180008CEF
0x180008ceb  mov     [r10], ax
0x180008cef  mov     eax, ecx
0x180008cf1  mov     rcx, [rsp+48h+var_10]
0x180008cf6  xor     rcx, rsp; StackCookie
0x180008cf9  call    __security_check_cookie
0x180008cfe  add     rsp, 48h
0x180008d02  retn
```
