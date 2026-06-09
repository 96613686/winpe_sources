# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005498`
- end: `0x18000551b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003068`
- `0x180009b30`
- `0x18000a2e0`
- `0x18000e4b0`

## callees

- `0x18000224c`
- `0x180005498`

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
0x180005498  mov     [rsp+arg_10], r8
0x18000549d  mov     qword ptr [rsp+Args], r9
0x1800054a2  push    rbx
0x1800054a3  push    rdi
0x1800054a4  sub     rsp, 38h
0x1800054a8  mov     rax, rdx
0x1800054ab  mov     rdi, rcx
0x1800054ae  test    rdx, rdx
0x1800054b1  jz      short loc_180005503
0x1800054b3  cmp     rax, 7FFFFFFFh
0x1800054b9  jbe     short loc_1800054C2
0x1800054bb  mov     edx, 80070057h
0x1800054c0  jmp     short loc_18000550D
0x1800054c2  lea     rbx, [rdx-1]
0x1800054c6  mov     [rsp+48h+var_28], 0
0x1800054cf  mov     rdx, rbx; BufferCount
0x1800054d2  lea     r9, [rsp+48h+Args]; Args
0x1800054d7  call    _vsnwprintf
0x1800054dc  test    eax, eax
0x1800054de  js      short loc_1800054F6
0x1800054e0  cdqe
0x1800054e2  cmp     rax, rbx
0x1800054e5  ja      short loc_1800054F6
0x1800054e7  xor     edx, edx
0x1800054e9  cmp     rax, rbx
0x1800054ec  jnz     short loc_180005512
0x1800054ee  xor     eax, eax
0x1800054f0  mov     [rdi+rbx*2], ax
0x1800054f4  jmp     short loc_180005512
0x1800054f6  xor     eax, eax
0x1800054f8  mov     edx, 8007007Ah
0x1800054fd  mov     [rdi+rbx*2], ax
0x180005501  jmp     short loc_180005512
0x180005503  mov     edx, 80070057h
0x180005508  test    rax, rax
0x18000550b  jz      short loc_180005512
0x18000550d  xor     ecx, ecx
0x18000550f  mov     [rdi], cx
0x180005512  mov     eax, edx
0x180005514  add     rsp, 38h
0x180005518  pop     rdi
0x180005519  pop     rbx
0x18000551a  retn
```
