# _vsnwprintf

- ea: `0x140001f28`
- end: `0x140001f76`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005300`
- `0x14000681c`

## callees

- `0x140001164`
- `0x140001dfa`

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
0x140001f28  push    rbx
0x140001f2a  push    rbp
0x140001f2b  push    rsi
0x140001f2c  push    rdi
0x140001f2d  sub     rsp, 38h
0x140001f31  mov     rbx, r9
0x140001f34  mov     rdi, r8
0x140001f37  mov     rsi, rdx
0x140001f3a  mov     rbp, rcx
0x140001f3d  call    __local_stdio_printf_options
0x140001f42  mov     [rsp+58h+ArgList], rbx; ArgList
0x140001f47  mov     r9, rdi; Format
0x140001f4a  mov     r8, rsi; BufferCount
0x140001f4d  mov     [rsp+58h+Locale], 0; Locale
0x140001f56  mov     rdx, rbp; Buffer
0x140001f59  mov     rcx, [rax]
0x140001f5c  or      rcx, 1; Options
0x140001f60  call    _o___stdio_common_vswprintf_0
0x140001f65  or      ecx, 0FFFFFFFFh
0x140001f68  test    eax, eax
0x140001f6a  cmovs   eax, ecx
0x140001f6d  add     rsp, 38h
0x140001f71  pop     rdi
0x140001f72  pop     rsi
0x140001f73  pop     rbp
0x140001f74  pop     rbx
0x140001f75  retn
```
