# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005aec`
- end: `0x180005b49`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `__int64(unsigned __int16 *, size_t, size_t *, ...)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ee0`
- `0x18000804c`
- `0x18000ddd0`
- `0x18000e994`
- `0x18000f0ec`
- `0x18000f860`
- `0x18000faf0`
- `0x18000ffa0`

## callees

- `0x180005aec`
- `0x180005b98`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, size_t a2, size_t *a3, ...)
{
  unsigned int v3; // edx
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
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180005aec  mov     [rsp+arg_10], r8
0x180005af1  mov     qword ptr [rsp+arg_18], r9
0x180005af6  sub     rsp, 48h
0x180005afa  mov     rax, rdx
0x180005afd  test    rdx, rdx
0x180005b00  jz      short loc_180005B33
0x180005b02  cmp     rax, 7FFFFFFFh
0x180005b08  jbe     short loc_180005B11
0x180005b0a  mov     edx, 80070057h
0x180005b0f  jmp     short loc_180005B3D
0x180005b11  lea     rdx, [rsp+48h+arg_18]
0x180005b16  mov     [rsp+48h+var_18], 0
0x180005b1f  mov     [rsp+48h+argList], rdx; argList
0x180005b24  mov     r9, r8; pszFormat
0x180005b27  mov     rdx, rax; cchDest
0x180005b2a  call    StringVPrintfWorkerW
0x180005b2f  mov     edx, eax
0x180005b31  jmp     short loc_180005B42
0x180005b33  mov     edx, 80070057h
0x180005b38  test    rax, rax
0x180005b3b  jz      short loc_180005B42
0x180005b3d  xor     eax, eax
0x180005b3f  mov     [rcx], ax
0x180005b42  mov     eax, edx
0x180005b44  add     rsp, 48h
0x180005b48  retn
```
