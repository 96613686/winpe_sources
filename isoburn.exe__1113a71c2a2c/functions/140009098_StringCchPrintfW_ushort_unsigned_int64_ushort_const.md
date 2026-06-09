# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140009098`
- end: `0x14000911b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003ecc`
- `0x14000b960`
- `0x14000bbb0`

## callees

- `0x140002bd4`
- `0x140009098`

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
0x140009098  mov     [rsp+arg_10], r8
0x14000909d  mov     qword ptr [rsp+Args], r9
0x1400090a2  push    rbx
0x1400090a3  push    rdi
0x1400090a4  sub     rsp, 38h
0x1400090a8  mov     rax, rdx
0x1400090ab  mov     rdi, rcx
0x1400090ae  test    rdx, rdx
0x1400090b1  jz      short loc_140009103
0x1400090b3  cmp     rax, 7FFFFFFFh
0x1400090b9  jbe     short loc_1400090C2
0x1400090bb  mov     edx, 80070057h
0x1400090c0  jmp     short loc_14000910D
0x1400090c2  lea     rbx, [rdx-1]
0x1400090c6  mov     [rsp+48h+var_28], 0
0x1400090cf  mov     rdx, rbx; BufferCount
0x1400090d2  lea     r9, [rsp+48h+Args]; Args
0x1400090d7  call    _vsnwprintf
0x1400090dc  test    eax, eax
0x1400090de  js      short loc_1400090F6
0x1400090e0  cdqe
0x1400090e2  cmp     rax, rbx
0x1400090e5  ja      short loc_1400090F6
0x1400090e7  xor     edx, edx
0x1400090e9  cmp     rax, rbx
0x1400090ec  jnz     short loc_140009112
0x1400090ee  xor     eax, eax
0x1400090f0  mov     [rdi+rbx*2], ax
0x1400090f4  jmp     short loc_140009112
0x1400090f6  xor     eax, eax
0x1400090f8  mov     edx, 8007007Ah
0x1400090fd  mov     [rdi+rbx*2], ax
0x140009101  jmp     short loc_140009112
0x140009103  mov     edx, 80070057h
0x140009108  test    rax, rax
0x14000910b  jz      short loc_140009112
0x14000910d  xor     ecx, ecx
0x14000910f  mov     [rdi], cx
0x140009112  mov     eax, edx
0x140009114  add     rsp, 38h
0x140009118  pop     rdi
0x140009119  pop     rbx
0x14000911a  retn
```
