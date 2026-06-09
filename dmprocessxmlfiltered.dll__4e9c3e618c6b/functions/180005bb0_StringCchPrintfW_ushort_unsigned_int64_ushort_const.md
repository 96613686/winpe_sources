# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005bb0`
- end: `0x180005c33`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034b8`
- `0x180006d1a`
- `0x180006e12`
- `0x180006f46`
- `0x180006fb1`

## callees

- `0x180001fbc`
- `0x180005bb0`

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
0x180005bb0  mov     [rsp+arg_10], r8
0x180005bb5  mov     qword ptr [rsp+Args], r9
0x180005bba  push    rbx
0x180005bbb  push    rdi
0x180005bbc  sub     rsp, 38h
0x180005bc0  mov     rax, rdx
0x180005bc3  mov     rdi, rcx
0x180005bc6  test    rdx, rdx
0x180005bc9  jz      short loc_180005C1B
0x180005bcb  cmp     rax, 7FFFFFFFh
0x180005bd1  jbe     short loc_180005BDA
0x180005bd3  mov     edx, 80070057h
0x180005bd8  jmp     short loc_180005C25
0x180005bda  lea     rbx, [rdx-1]
0x180005bde  mov     [rsp+48h+var_28], 0
0x180005be7  mov     rdx, rbx; BufferCount
0x180005bea  lea     r9, [rsp+48h+Args]; Args
0x180005bef  call    _vsnwprintf
0x180005bf4  test    eax, eax
0x180005bf6  js      short loc_180005C0E
0x180005bf8  cdqe
0x180005bfa  cmp     rax, rbx
0x180005bfd  ja      short loc_180005C0E
0x180005bff  xor     edx, edx
0x180005c01  cmp     rax, rbx
0x180005c04  jnz     short loc_180005C2A
0x180005c06  xor     eax, eax
0x180005c08  mov     [rdi+rbx*2], ax
0x180005c0c  jmp     short loc_180005C2A
0x180005c0e  xor     eax, eax
0x180005c10  mov     edx, 8007007Ah
0x180005c15  mov     [rdi+rbx*2], ax
0x180005c19  jmp     short loc_180005C2A
0x180005c1b  mov     edx, 80070057h
0x180005c20  test    rax, rax
0x180005c23  jz      short loc_180005C2A
0x180005c25  xor     ecx, ecx
0x180005c27  mov     [rdi], cx
0x180005c2a  mov     eax, edx
0x180005c2c  add     rsp, 38h
0x180005c30  pop     rdi
0x180005c31  pop     rbx
0x180005c32  retn
```
