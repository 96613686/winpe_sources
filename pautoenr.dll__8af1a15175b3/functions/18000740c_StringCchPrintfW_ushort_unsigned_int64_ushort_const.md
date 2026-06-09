# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000740c`
- end: `0x180007490`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800027e0`
- `0x180006b10`

## callees

- `0x18000740c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000744b`
- `msvcrt!_vsnwprintf` at `0x18000744b`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
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
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
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
0x18000740c  mov     [rsp+arg_10], r8
0x180007411  mov     qword ptr [rsp+Args], r9
0x180007416  push    rbx
0x180007417  push    rdi
0x180007418  sub     rsp, 38h
0x18000741c  mov     rax, rdx
0x18000741f  mov     rdi, rcx
0x180007422  test    rdx, rdx
0x180007425  jz      short loc_180007478
0x180007427  cmp     rax, 7FFFFFFFh
0x18000742d  jbe     short loc_180007436
0x18000742f  mov     edx, 80070057h
0x180007434  jmp     short loc_180007482
0x180007436  lea     rbx, [rdx-1]
0x18000743a  mov     [rsp+48h+var_28], 0
0x180007443  mov     rdx, rbx; BufferCount
0x180007446  lea     r9, [rsp+48h+Args]; Args
0x18000744b  call    cs:__imp__vsnwprintf
0x180007451  test    eax, eax
0x180007453  js      short loc_18000746B
0x180007455  cdqe
0x180007457  cmp     rax, rbx
0x18000745a  ja      short loc_18000746B
0x18000745c  xor     edx, edx
0x18000745e  cmp     rax, rbx
0x180007461  jnz     short loc_180007487
0x180007463  xor     eax, eax
0x180007465  mov     [rdi+rbx*2], ax
0x180007469  jmp     short loc_180007487
0x18000746b  xor     eax, eax
0x18000746d  mov     edx, 8007007Ah
0x180007472  mov     [rdi+rbx*2], ax
0x180007476  jmp     short loc_180007487
0x180007478  mov     edx, 80070057h
0x18000747d  test    rax, rax
0x180007480  jz      short loc_180007487
0x180007482  xor     ecx, ecx
0x180007484  mov     [rdi], cx
0x180007487  mov     eax, edx
0x180007489  add     rsp, 38h
0x18000748d  pop     rdi
0x18000748e  pop     rbx
0x18000748f  retn
```
