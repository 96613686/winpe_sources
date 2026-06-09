# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800062f0`
- end: `0x180006373`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x180003db8`
- `0x18000a0b8`
- `0x18000c950`
- `0x18000d707`
- `0x18000d7ff`
- `0x18000d933`
- `0x18000d99e`

## callees

- `0x18000299c`
- `0x1800062f0`

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
0x1800062f0  mov     [rsp+arg_10], r8
0x1800062f5  mov     qword ptr [rsp+Args], r9
0x1800062fa  push    rbx
0x1800062fb  push    rdi
0x1800062fc  sub     rsp, 38h
0x180006300  mov     rax, rdx
0x180006303  mov     rdi, rcx
0x180006306  test    rdx, rdx
0x180006309  jz      short loc_18000635B
0x18000630b  cmp     rax, 7FFFFFFFh
0x180006311  jbe     short loc_18000631A
0x180006313  mov     edx, 80070057h
0x180006318  jmp     short loc_180006365
0x18000631a  lea     rbx, [rdx-1]
0x18000631e  mov     [rsp+48h+var_28], 0
0x180006327  mov     rdx, rbx; BufferCount
0x18000632a  lea     r9, [rsp+48h+Args]; Args
0x18000632f  call    _vsnwprintf
0x180006334  test    eax, eax
0x180006336  js      short loc_18000634E
0x180006338  cdqe
0x18000633a  cmp     rax, rbx
0x18000633d  ja      short loc_18000634E
0x18000633f  xor     edx, edx
0x180006341  cmp     rax, rbx
0x180006344  jnz     short loc_18000636A
0x180006346  xor     eax, eax
0x180006348  mov     [rdi+rbx*2], ax
0x18000634c  jmp     short loc_18000636A
0x18000634e  xor     eax, eax
0x180006350  mov     edx, 8007007Ah
0x180006355  mov     [rdi+rbx*2], ax
0x180006359  jmp     short loc_18000636A
0x18000635b  mov     edx, 80070057h
0x180006360  test    rax, rax
0x180006363  jz      short loc_18000636A
0x180006365  xor     ecx, ecx
0x180006367  mov     [rdi], cx
0x18000636a  mov     eax, edx
0x18000636c  add     rsp, 38h
0x180006370  pop     rdi
0x180006371  pop     rbx
0x180006372  retn
```
