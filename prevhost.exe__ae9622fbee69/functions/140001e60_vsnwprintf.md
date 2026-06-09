# _vsnwprintf

- ea: `0x140001e60`
- end: `0x140001eae`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400043dc`
- `0x1400050b0`

## callees

- `0x140001174`
- `0x140001d32`

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
0x140001e60  push    rbx
0x140001e62  push    rbp
0x140001e63  push    rsi
0x140001e64  push    rdi
0x140001e65  sub     rsp, 38h
0x140001e69  mov     rbx, r9
0x140001e6c  mov     rdi, r8
0x140001e6f  mov     rsi, rdx
0x140001e72  mov     rbp, rcx
0x140001e75  call    __local_stdio_printf_options
0x140001e7a  mov     [rsp+58h+ArgList], rbx; ArgList
0x140001e7f  mov     r9, rdi; Format
0x140001e82  mov     r8, rsi; BufferCount
0x140001e85  mov     [rsp+58h+Locale], 0; Locale
0x140001e8e  mov     rdx, rbp; Buffer
0x140001e91  mov     rcx, [rax]
0x140001e94  or      rcx, 1; Options
0x140001e98  call    _o___stdio_common_vswprintf_0
0x140001e9d  or      ecx, 0FFFFFFFFh
0x140001ea0  test    eax, eax
0x140001ea2  cmovs   eax, ecx
0x140001ea5  add     rsp, 38h
0x140001ea9  pop     rdi
0x140001eaa  pop     rsi
0x140001eab  pop     rbp
0x140001eac  pop     rbx
0x140001ead  retn
```
