# _vsnwprintf

- ea: `0x180001ffc`
- end: `0x18000204a`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004310`
- `0x180005d40`

## callees

- `0x1800011e4`
- `0x180001f3a`

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
0x180001ffc  push    rbx
0x180001ffe  push    rbp
0x180001fff  push    rsi
0x180002000  push    rdi
0x180002001  sub     rsp, 38h
0x180002005  mov     rbx, r9
0x180002008  mov     rdi, r8
0x18000200b  mov     rsi, rdx
0x18000200e  mov     rbp, rcx
0x180002011  call    __local_stdio_printf_options
0x180002016  mov     [rsp+58h+ArgList], rbx; ArgList
0x18000201b  mov     r9, rdi; Format
0x18000201e  mov     r8, rsi; BufferCount
0x180002021  mov     [rsp+58h+Locale], 0; Locale
0x18000202a  mov     rdx, rbp; Buffer
0x18000202d  mov     rcx, [rax]
0x180002030  or      rcx, 1; Options
0x180002034  call    _o___stdio_common_vswprintf_0
0x180002039  or      ecx, 0FFFFFFFFh
0x18000203c  test    eax, eax
0x18000203e  cmovs   eax, ecx
0x180002041  add     rsp, 38h
0x180002045  pop     rdi
0x180002046  pop     rsi
0x180002047  pop     rbp
0x180002048  pop     rbx
0x180002049  retn
```
