# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x180009688`
- end: `0x18000970b`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `131`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800050b8`
- `0x180005488`
- `0x180013ad8`
- `0x180013bf4`
- `0x1800158bb`
- `0x1800159e9`
- `0x180015b1d`
- `0x180015b88`
- `0x180015c70`
- `0x180015d86`
- `0x180015de2`
- `0x180015e3e`
- `0x180015f40`
- `0x180016056`
- `0x1800160b2`
- `0x18001610e`
- `0x18001616a`

## callees

- `0x180003398`
- `0x180009688`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
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
0x180009688  mov     [rsp+arg_10], r8
0x18000968d  mov     qword ptr [rsp+Args], r9
0x180009692  push    rbx
0x180009693  push    rdi
0x180009694  sub     rsp, 38h
0x180009698  mov     rax, rdx
0x18000969b  mov     rdi, rcx
0x18000969e  test    rdx, rdx
0x1800096a1  jz      short loc_1800096F3
0x1800096a3  cmp     rax, 7FFFFFFFh
0x1800096a9  jbe     short loc_1800096B2
0x1800096ab  mov     edx, 80070057h
0x1800096b0  jmp     short loc_1800096FD
0x1800096b2  lea     rbx, [rdx-1]
0x1800096b6  mov     [rsp+48h+var_28], 0
0x1800096bf  mov     rdx, rbx; BufferCount
0x1800096c2  lea     r9, [rsp+48h+Args]; Args
0x1800096c7  call    _vsnwprintf
0x1800096cc  test    eax, eax
0x1800096ce  js      short loc_1800096E6
0x1800096d0  cdqe
0x1800096d2  cmp     rax, rbx
0x1800096d5  ja      short loc_1800096E6
0x1800096d7  xor     edx, edx
0x1800096d9  cmp     rax, rbx
0x1800096dc  jnz     short loc_180009702
0x1800096de  xor     eax, eax
0x1800096e0  mov     [rdi+rbx*2], ax
0x1800096e4  jmp     short loc_180009702
0x1800096e6  xor     eax, eax
0x1800096e8  mov     edx, 8007007Ah
0x1800096ed  mov     [rdi+rbx*2], ax
0x1800096f1  jmp     short loc_180009702
0x1800096f3  mov     edx, 80070057h
0x1800096f8  test    rax, rax
0x1800096fb  jz      short loc_180009702
0x1800096fd  xor     ecx, ecx
0x1800096ff  mov     [rdi], cx
0x180009702  mov     eax, edx
0x180009704  add     rsp, 38h
0x180009708  pop     rdi
0x180009709  pop     rbx
0x18000970a  retn
```
