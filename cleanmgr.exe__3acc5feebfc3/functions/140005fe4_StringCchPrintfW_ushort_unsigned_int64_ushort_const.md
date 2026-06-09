# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140005fe4`
- end: `0x140006041`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `__int64(unsigned __int16 *, size_t, size_t *, ...)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x140004238`
- `0x140007260`
- `0x140009d34`
- `0x14000fa20`
- `0x1400124b8`
- `0x140012a7c`
- `0x140013530`
- `0x140014fe0`

## callees

- `0x140005fe4`
- `0x1400060a0`

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
0x140005fe4  mov     [rsp+arg_10], r8
0x140005fe9  mov     qword ptr [rsp+arg_18], r9
0x140005fee  sub     rsp, 48h
0x140005ff2  mov     rax, rdx
0x140005ff5  test    rdx, rdx
0x140005ff8  jz      short loc_14000602B
0x140005ffa  cmp     rax, 7FFFFFFFh
0x140006000  jbe     short loc_140006009
0x140006002  mov     edx, 80070057h
0x140006007  jmp     short loc_140006035
0x140006009  lea     rdx, [rsp+48h+arg_18]
0x14000600e  mov     [rsp+48h+var_18], 0
0x140006017  mov     [rsp+48h+argList], rdx; argList
0x14000601c  mov     r9, r8; pszFormat
0x14000601f  mov     rdx, rax; cchDest
0x140006022  call    StringVPrintfWorkerW
0x140006027  mov     edx, eax
0x140006029  jmp     short loc_14000603A
0x14000602b  mov     edx, 80070057h
0x140006030  test    rax, rax
0x140006033  jz      short loc_14000603A
0x140006035  xor     eax, eax
0x140006037  mov     [rcx], ax
0x14000603a  mov     eax, edx
0x14000603c  add     rsp, 48h
0x140006040  retn
```
