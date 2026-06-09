# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000886c`
- end: `0x1800088f0`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800077f8`
- `0x18000d038`
- `0x18000de18`

## callees

- `0x18000886c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800088ab`
- `msvcrt!_vsnwprintf` at `0x1800088ab`

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
0x18000886c  mov     [rsp+arg_10], r8
0x180008871  mov     qword ptr [rsp+Args], r9
0x180008876  push    rbx
0x180008877  push    rdi
0x180008878  sub     rsp, 38h
0x18000887c  mov     rax, rdx
0x18000887f  mov     rdi, rcx
0x180008882  test    rdx, rdx
0x180008885  jz      short loc_1800088D8
0x180008887  cmp     rax, 7FFFFFFFh
0x18000888d  jbe     short loc_180008896
0x18000888f  mov     edx, 80070057h
0x180008894  jmp     short loc_1800088E2
0x180008896  lea     rbx, [rdx-1]
0x18000889a  mov     [rsp+48h+var_28], 0
0x1800088a3  mov     rdx, rbx; BufferCount
0x1800088a6  lea     r9, [rsp+48h+Args]; Args
0x1800088ab  call    cs:__imp__vsnwprintf
0x1800088b1  test    eax, eax
0x1800088b3  js      short loc_1800088CB
0x1800088b5  cdqe
0x1800088b7  cmp     rax, rbx
0x1800088ba  ja      short loc_1800088CB
0x1800088bc  xor     edx, edx
0x1800088be  cmp     rax, rbx
0x1800088c1  jnz     short loc_1800088E7
0x1800088c3  xor     eax, eax
0x1800088c5  mov     [rdi+rbx*2], ax
0x1800088c9  jmp     short loc_1800088E7
0x1800088cb  xor     eax, eax
0x1800088cd  mov     edx, 8007007Ah
0x1800088d2  mov     [rdi+rbx*2], ax
0x1800088d6  jmp     short loc_1800088E7
0x1800088d8  mov     edx, 80070057h
0x1800088dd  test    rax, rax
0x1800088e0  jz      short loc_1800088E7
0x1800088e2  xor     ecx, ecx
0x1800088e4  mov     [rdi], cx
0x1800088e7  mov     eax, edx
0x1800088e9  add     rsp, 38h
0x1800088ed  pop     rdi
0x1800088ee  pop     rbx
0x1800088ef  retn
```
