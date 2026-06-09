# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800073d8`
- end: `0x18000745c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800037a8`
- `0x180003b4c`
- `0x18000a428`
- `0x18000e2ac`
- `0x180018be0`

## callees

- `0x1800073d8`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180007417`
- `msvcrt!_vsnwprintf` at `0x180007417`

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
0x1800073d8  mov     [rsp+arg_10], r8
0x1800073dd  mov     qword ptr [rsp+Args], r9
0x1800073e2  push    rbx
0x1800073e3  push    rdi
0x1800073e4  sub     rsp, 38h
0x1800073e8  mov     rax, rdx
0x1800073eb  mov     rdi, rcx
0x1800073ee  test    rdx, rdx
0x1800073f1  jz      short loc_180007444
0x1800073f3  cmp     rax, 7FFFFFFFh
0x1800073f9  jbe     short loc_180007402
0x1800073fb  mov     edx, 80070057h
0x180007400  jmp     short loc_18000744E
0x180007402  lea     rbx, [rdx-1]
0x180007406  mov     [rsp+48h+var_28], 0
0x18000740f  mov     rdx, rbx; BufferCount
0x180007412  lea     r9, [rsp+48h+Args]; Args
0x180007417  call    cs:__imp__vsnwprintf
0x18000741d  test    eax, eax
0x18000741f  js      short loc_180007437
0x180007421  cdqe
0x180007423  cmp     rax, rbx
0x180007426  ja      short loc_180007437
0x180007428  xor     edx, edx
0x18000742a  cmp     rax, rbx
0x18000742d  jnz     short loc_180007453
0x18000742f  xor     eax, eax
0x180007431  mov     [rdi+rbx*2], ax
0x180007435  jmp     short loc_180007453
0x180007437  xor     eax, eax
0x180007439  mov     edx, 8007007Ah
0x18000743e  mov     [rdi+rbx*2], ax
0x180007442  jmp     short loc_180007453
0x180007444  mov     edx, 80070057h
0x180007449  test    rax, rax
0x18000744c  jz      short loc_180007453
0x18000744e  xor     ecx, ecx
0x180007450  mov     [rdi], cx
0x180007453  mov     eax, edx
0x180007455  add     rsp, 38h
0x180007459  pop     rdi
0x18000745a  pop     rbx
0x18000745b  retn
```
