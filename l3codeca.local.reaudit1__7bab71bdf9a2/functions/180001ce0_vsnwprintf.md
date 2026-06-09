# _vsnwprintf

- ea: `0x180001ce0`
- end: `0x180001d2e`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800028f4`
- `0x180003124`

## callees

- `0x180001034`
- `0x180001c2a`

## pseudocode

```c
int __cdecl vsnwprintf(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)
{
  unsigned __int64 *v8; // rax
  int result; // eax

  v8 = _local_stdio_printf_options();
  result = o___stdio_common_vswprintf_0(*v8 | 1, Buffer, BufferCount, Format, 0, Args);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x180001ce0  push    rbx
0x180001ce2  push    rbp
0x180001ce3  push    rsi
0x180001ce4  push    rdi
0x180001ce5  sub     rsp, 38h
0x180001ce9  mov     rbx, r9
0x180001cec  mov     rdi, r8
0x180001cef  mov     rsi, rdx
0x180001cf2  mov     rbp, rcx
0x180001cf5  call    __local_stdio_printf_options
0x180001cfa  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001cff  mov     r9, rdi; Format
0x180001d02  mov     r8, rsi; BufferCount
0x180001d05  mov     [rsp+58h+Locale], 0; Locale
0x180001d0e  mov     rdx, rbp; Buffer
0x180001d11  mov     rcx, [rax]
0x180001d14  or      rcx, 1; Options
0x180001d18  call    _o___stdio_common_vswprintf_0
0x180001d1d  or      ecx, 0FFFFFFFFh
0x180001d20  test    eax, eax
0x180001d22  cmovs   eax, ecx
0x180001d25  add     rsp, 38h
0x180001d29  pop     rdi
0x180001d2a  pop     rsi
0x180001d2b  pop     rbp
0x180001d2c  pop     rbx
0x180001d2d  retn
```
