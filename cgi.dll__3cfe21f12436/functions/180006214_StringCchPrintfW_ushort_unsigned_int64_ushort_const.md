# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006214`
- end: `0x180006298`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000337c`

## callees

- `0x180006214`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006253`
- `msvcrt!_vsnwprintf` at `0x180006253`

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
0x180006214  mov     [rsp+arg_10], r8
0x180006219  mov     qword ptr [rsp+Args], r9
0x18000621e  push    rbx
0x18000621f  push    rdi
0x180006220  sub     rsp, 38h
0x180006224  mov     rax, rdx
0x180006227  mov     rdi, rcx
0x18000622a  test    rdx, rdx
0x18000622d  jz      short loc_180006280
0x18000622f  cmp     rax, 7FFFFFFFh
0x180006235  jbe     short loc_18000623E
0x180006237  mov     edx, 80070057h
0x18000623c  jmp     short loc_18000628A
0x18000623e  lea     rbx, [rdx-1]
0x180006242  mov     [rsp+48h+var_28], 0
0x18000624b  mov     rdx, rbx; BufferCount
0x18000624e  lea     r9, [rsp+48h+Args]; Args
0x180006253  call    cs:__imp__vsnwprintf
0x180006259  test    eax, eax
0x18000625b  js      short loc_180006273
0x18000625d  cdqe
0x18000625f  cmp     rax, rbx
0x180006262  ja      short loc_180006273
0x180006264  xor     edx, edx
0x180006266  cmp     rax, rbx
0x180006269  jnz     short loc_18000628F
0x18000626b  xor     eax, eax
0x18000626d  mov     [rdi+rbx*2], ax
0x180006271  jmp     short loc_18000628F
0x180006273  xor     eax, eax
0x180006275  mov     edx, 8007007Ah
0x18000627a  mov     [rdi+rbx*2], ax
0x18000627e  jmp     short loc_18000628F
0x180006280  mov     edx, 80070057h
0x180006285  test    rax, rax
0x180006288  jz      short loc_18000628F
0x18000628a  xor     ecx, ecx
0x18000628c  mov     [rdi], cx
0x18000628f  mov     eax, edx
0x180006291  add     rsp, 38h
0x180006295  pop     rdi
0x180006296  pop     rbx
0x180006297  retn
```
