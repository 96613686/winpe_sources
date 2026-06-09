# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006b40`
- end: `0x180006bc3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037d4`
- `0x180004020`
- `0x180007900`

## callees

- `0x18000262c`
- `0x180006b40`

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
0x180006b40  mov     [rsp+arg_10], r8
0x180006b45  mov     qword ptr [rsp+Args], r9
0x180006b4a  push    rbx
0x180006b4b  push    rdi
0x180006b4c  sub     rsp, 38h
0x180006b50  mov     rax, rdx
0x180006b53  mov     rdi, rcx
0x180006b56  test    rdx, rdx
0x180006b59  jz      short loc_180006BAB
0x180006b5b  cmp     rax, 7FFFFFFFh
0x180006b61  jbe     short loc_180006B6A
0x180006b63  mov     edx, 80070057h
0x180006b68  jmp     short loc_180006BB5
0x180006b6a  lea     rbx, [rdx-1]
0x180006b6e  mov     [rsp+48h+var_28], 0
0x180006b77  mov     rdx, rbx; BufferCount
0x180006b7a  lea     r9, [rsp+48h+Args]; Args
0x180006b7f  call    _vsnwprintf
0x180006b84  test    eax, eax
0x180006b86  js      short loc_180006B9E
0x180006b88  cdqe
0x180006b8a  cmp     rax, rbx
0x180006b8d  ja      short loc_180006B9E
0x180006b8f  xor     edx, edx
0x180006b91  cmp     rax, rbx
0x180006b94  jnz     short loc_180006BBA
0x180006b96  xor     eax, eax
0x180006b98  mov     [rdi+rbx*2], ax
0x180006b9c  jmp     short loc_180006BBA
0x180006b9e  xor     eax, eax
0x180006ba0  mov     edx, 8007007Ah
0x180006ba5  mov     [rdi+rbx*2], ax
0x180006ba9  jmp     short loc_180006BBA
0x180006bab  mov     edx, 80070057h
0x180006bb0  test    rax, rax
0x180006bb3  jz      short loc_180006BBA
0x180006bb5  xor     ecx, ecx
0x180006bb7  mov     [rdi], cx
0x180006bba  mov     eax, edx
0x180006bbc  add     rsp, 38h
0x180006bc0  pop     rdi
0x180006bc1  pop     rbx
0x180006bc2  retn
```
