# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000cc54`
- end: `0x14000ccb1`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `__int64(unsigned __int16 *, size_t, size_t *, ...)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1400066d8`
- `0x140006844`
- `0x140007ad8`
- `0x140008d0c`
- `0x14000b0cc`
- `0x14000f654`
- `0x14000fa90`
- `0x140011804`
- `0x1400122f8`

## callees

- `0x14000cc54`
- `0x14000cd58`

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
0x14000cc54  mov     [rsp+arg_10], r8
0x14000cc59  mov     qword ptr [rsp+arg_18], r9
0x14000cc5e  sub     rsp, 48h
0x14000cc62  mov     rax, rdx
0x14000cc65  test    rdx, rdx
0x14000cc68  jz      short loc_14000CC9B
0x14000cc6a  cmp     rax, 7FFFFFFFh
0x14000cc70  jbe     short loc_14000CC79
0x14000cc72  mov     edx, 80070057h
0x14000cc77  jmp     short loc_14000CCA5
0x14000cc79  lea     rdx, [rsp+48h+arg_18]
0x14000cc7e  mov     [rsp+48h+var_18], 0
0x14000cc87  mov     [rsp+48h+argList], rdx; argList
0x14000cc8c  mov     r9, r8; pszFormat
0x14000cc8f  mov     rdx, rax; cchDest
0x14000cc92  call    StringVPrintfWorkerW
0x14000cc97  mov     edx, eax
0x14000cc99  jmp     short loc_14000CCAA
0x14000cc9b  mov     edx, 80070057h
0x14000cca0  test    rax, rax
0x14000cca3  jz      short loc_14000CCAA
0x14000cca5  xor     eax, eax
0x14000cca7  mov     [rcx], ax
0x14000ccaa  mov     eax, edx
0x14000ccac  add     rsp, 48h
0x14000ccb0  retn
```
