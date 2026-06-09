# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005d40`
- end: `0x180005dc3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180003560`
- `0x18000374c`
- `0x1800053e0`
- `0x180005e60`
- `0x180006d30`
- `0x180008010`
- `0x180009846`
- `0x18000993e`
- `0x180009a72`
- `0x180009add`

## callees

- `0x180001ffc`
- `0x180005d40`

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
0x180005d40  mov     [rsp+arg_10], r8
0x180005d45  mov     qword ptr [rsp+Args], r9
0x180005d4a  push    rbx
0x180005d4b  push    rdi
0x180005d4c  sub     rsp, 38h
0x180005d50  mov     rax, rdx
0x180005d53  mov     rdi, rcx
0x180005d56  test    rdx, rdx
0x180005d59  jz      short loc_180005DAB
0x180005d5b  cmp     rax, 7FFFFFFFh
0x180005d61  jbe     short loc_180005D6A
0x180005d63  mov     edx, 80070057h
0x180005d68  jmp     short loc_180005DB5
0x180005d6a  lea     rbx, [rdx-1]
0x180005d6e  mov     [rsp+48h+var_28], 0
0x180005d77  mov     rdx, rbx; BufferCount
0x180005d7a  lea     r9, [rsp+48h+Args]; Args
0x180005d7f  call    _vsnwprintf
0x180005d84  test    eax, eax
0x180005d86  js      short loc_180005D9E
0x180005d88  cdqe
0x180005d8a  cmp     rax, rbx
0x180005d8d  ja      short loc_180005D9E
0x180005d8f  xor     edx, edx
0x180005d91  cmp     rax, rbx
0x180005d94  jnz     short loc_180005DBA
0x180005d96  xor     eax, eax
0x180005d98  mov     [rdi+rbx*2], ax
0x180005d9c  jmp     short loc_180005DBA
0x180005d9e  xor     eax, eax
0x180005da0  mov     edx, 8007007Ah
0x180005da5  mov     [rdi+rbx*2], ax
0x180005da9  jmp     short loc_180005DBA
0x180005dab  mov     edx, 80070057h
0x180005db0  test    rax, rax
0x180005db3  jz      short loc_180005DBA
0x180005db5  xor     ecx, ecx
0x180005db7  mov     [rdi], cx
0x180005dba  mov     eax, edx
0x180005dbc  add     rsp, 38h
0x180005dc0  pop     rdi
0x180005dc1  pop     rbx
0x180005dc2  retn
```
