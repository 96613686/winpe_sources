# _vsnwprintf

- ea: `0x18000299c`
- end: `0x1800029ea`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005360`
- `0x1800062f0`
- `0x18000a0b8`

## callees

- `0x1800017d4`
- `0x1800028b6`

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
0x18000299c  push    rbx
0x18000299e  push    rbp
0x18000299f  push    rsi
0x1800029a0  push    rdi
0x1800029a1  sub     rsp, 38h
0x1800029a5  mov     rbx, r9
0x1800029a8  mov     rdi, r8
0x1800029ab  mov     rsi, rdx
0x1800029ae  mov     rbp, rcx
0x1800029b1  call    __local_stdio_printf_options
0x1800029b6  mov     [rsp+58h+ArgList], rbx; ArgList
0x1800029bb  mov     r9, rdi; Format
0x1800029be  mov     r8, rsi; BufferCount
0x1800029c1  mov     [rsp+58h+Locale], 0; Locale
0x1800029ca  mov     rdx, rbp; Buffer
0x1800029cd  mov     rcx, [rax]
0x1800029d0  or      rcx, 1; Options
0x1800029d4  call    _o___stdio_common_vswprintf_0
0x1800029d9  or      ecx, 0FFFFFFFFh
0x1800029dc  test    eax, eax
0x1800029de  cmovs   eax, ecx
0x1800029e1  add     rsp, 38h
0x1800029e5  pop     rdi
0x1800029e6  pop     rsi
0x1800029e7  pop     rbp
0x1800029e8  pop     rbx
0x1800029e9  retn
```
