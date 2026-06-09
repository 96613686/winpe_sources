# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x180008d34`
- end: `0x180008db7`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `131`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180004428`
- `0x1800047cc`
- `0x180014fb6`
- `0x1800150e4`
- `0x180015218`
- `0x180015283`

## callees

- `0x1800028e8`
- `0x180008d34`

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
0x180008d34  mov     [rsp+arg_10], r8
0x180008d39  mov     qword ptr [rsp+Args], r9
0x180008d3e  push    rbx
0x180008d3f  push    rdi
0x180008d40  sub     rsp, 38h
0x180008d44  mov     rax, rdx
0x180008d47  mov     rdi, rcx
0x180008d4a  test    rdx, rdx
0x180008d4d  jz      short loc_180008D9F
0x180008d4f  cmp     rax, 7FFFFFFFh
0x180008d55  jbe     short loc_180008D5E
0x180008d57  mov     edx, 80070057h
0x180008d5c  jmp     short loc_180008DA9
0x180008d5e  lea     rbx, [rdx-1]
0x180008d62  mov     [rsp+48h+var_28], 0
0x180008d6b  mov     rdx, rbx; BufferCount
0x180008d6e  lea     r9, [rsp+48h+Args]; Args
0x180008d73  call    _vsnwprintf
0x180008d78  test    eax, eax
0x180008d7a  js      short loc_180008D92
0x180008d7c  cdqe
0x180008d7e  cmp     rax, rbx
0x180008d81  ja      short loc_180008D92
0x180008d83  xor     edx, edx
0x180008d85  cmp     rax, rbx
0x180008d88  jnz     short loc_180008DAE
0x180008d8a  xor     eax, eax
0x180008d8c  mov     [rdi+rbx*2], ax
0x180008d90  jmp     short loc_180008DAE
0x180008d92  xor     eax, eax
0x180008d94  mov     edx, 8007007Ah
0x180008d99  mov     [rdi+rbx*2], ax
0x180008d9d  jmp     short loc_180008DAE
0x180008d9f  mov     edx, 80070057h
0x180008da4  test    rax, rax
0x180008da7  jz      short loc_180008DAE
0x180008da9  xor     ecx, ecx
0x180008dab  mov     [rdi], cx
0x180008dae  mov     eax, edx
0x180008db0  add     rsp, 38h
0x180008db4  pop     rdi
0x180008db5  pop     rbx
0x180008db6  retn
```
