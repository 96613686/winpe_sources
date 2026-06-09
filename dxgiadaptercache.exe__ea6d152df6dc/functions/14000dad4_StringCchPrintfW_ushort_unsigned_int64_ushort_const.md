# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000dad4`
- end: `0x14000db57`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140007368`
- `0x140007738`
- `0x1400116ae`
- `0x140011800`
- `0x140011934`
- `0x14001199f`

## callees

- `0x140002d64`
- `0x14000dad4`

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
0x14000dad4  mov     [rsp+arg_10], r8
0x14000dad9  mov     qword ptr [rsp+Args], r9
0x14000dade  push    rbx
0x14000dadf  push    rdi
0x14000dae0  sub     rsp, 38h
0x14000dae4  mov     rax, rdx
0x14000dae7  mov     rdi, rcx
0x14000daea  test    rdx, rdx
0x14000daed  jz      short loc_14000DB3F
0x14000daef  cmp     rax, 7FFFFFFFh
0x14000daf5  jbe     short loc_14000DAFE
0x14000daf7  mov     edx, 80070057h
0x14000dafc  jmp     short loc_14000DB49
0x14000dafe  lea     rbx, [rdx-1]
0x14000db02  mov     [rsp+48h+var_28], 0
0x14000db0b  mov     rdx, rbx; BufferCount
0x14000db0e  lea     r9, [rsp+48h+Args]; Args
0x14000db13  call    _vsnwprintf
0x14000db18  test    eax, eax
0x14000db1a  js      short loc_14000DB32
0x14000db1c  cdqe
0x14000db1e  cmp     rax, rbx
0x14000db21  ja      short loc_14000DB32
0x14000db23  xor     edx, edx
0x14000db25  cmp     rax, rbx
0x14000db28  jnz     short loc_14000DB4E
0x14000db2a  xor     eax, eax
0x14000db2c  mov     [rdi+rbx*2], ax
0x14000db30  jmp     short loc_14000DB4E
0x14000db32  xor     eax, eax
0x14000db34  mov     edx, 8007007Ah
0x14000db39  mov     [rdi+rbx*2], ax
0x14000db3d  jmp     short loc_14000DB4E
0x14000db3f  mov     edx, 80070057h
0x14000db44  test    rax, rax
0x14000db47  jz      short loc_14000DB4E
0x14000db49  xor     ecx, ecx
0x14000db4b  mov     [rdi], cx
0x14000db4e  mov     eax, edx
0x14000db50  add     rsp, 38h
0x14000db54  pop     rdi
0x14000db55  pop     rbx
0x14000db56  retn
```
