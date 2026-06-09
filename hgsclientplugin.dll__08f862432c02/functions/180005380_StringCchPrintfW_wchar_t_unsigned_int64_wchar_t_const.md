# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x180005380`
- end: `0x180005403`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `131`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e48`
- `0x180007bd0`
- `0x18000a9d6`
- `0x18000aace`
- `0x18000ac02`
- `0x18000ac6d`

## callees

- `0x180001fb8`
- `0x180005380`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
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
0x180005380  mov     [rsp+arg_10], r8
0x180005385  mov     qword ptr [rsp+Args], r9
0x18000538a  push    rbx
0x18000538b  push    rdi
0x18000538c  sub     rsp, 38h
0x180005390  mov     rax, rdx
0x180005393  mov     rdi, rcx
0x180005396  test    rdx, rdx
0x180005399  jz      short loc_1800053EB
0x18000539b  cmp     rax, 7FFFFFFFh
0x1800053a1  jbe     short loc_1800053AA
0x1800053a3  mov     edx, 80070057h
0x1800053a8  jmp     short loc_1800053F5
0x1800053aa  lea     rbx, [rdx-1]
0x1800053ae  mov     [rsp+48h+var_28], 0
0x1800053b7  mov     rdx, rbx; BufferCount
0x1800053ba  lea     r9, [rsp+48h+Args]; Args
0x1800053bf  call    _vsnwprintf
0x1800053c4  test    eax, eax
0x1800053c6  js      short loc_1800053DE
0x1800053c8  cdqe
0x1800053ca  cmp     rax, rbx
0x1800053cd  ja      short loc_1800053DE
0x1800053cf  xor     edx, edx
0x1800053d1  cmp     rax, rbx
0x1800053d4  jnz     short loc_1800053FA
0x1800053d6  xor     eax, eax
0x1800053d8  mov     [rdi+rbx*2], ax
0x1800053dc  jmp     short loc_1800053FA
0x1800053de  xor     eax, eax
0x1800053e0  mov     edx, 8007007Ah
0x1800053e5  mov     [rdi+rbx*2], ax
0x1800053e9  jmp     short loc_1800053FA
0x1800053eb  mov     edx, 80070057h
0x1800053f0  test    rax, rax
0x1800053f3  jz      short loc_1800053FA
0x1800053f5  xor     ecx, ecx
0x1800053f7  mov     [rdi], cx
0x1800053fa  mov     eax, edx
0x1800053fc  add     rsp, 38h
0x180005400  pop     rdi
0x180005401  pop     rbx
0x180005402  retn
```
