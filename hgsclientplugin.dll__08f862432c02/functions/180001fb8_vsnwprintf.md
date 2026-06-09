# _vsnwprintf

- ea: `0x180001fb8`
- end: `0x180002006`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800043e8`
- `0x180005380`
- `0x1800068ec`
- `0x1800069fc`
- `0x180006b00`
- `0x180007bd0`

## callees

- `0x180001154`
- `0x180001eea`

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
0x180001fb8  push    rbx
0x180001fba  push    rbp
0x180001fbb  push    rsi
0x180001fbc  push    rdi
0x180001fbd  sub     rsp, 38h
0x180001fc1  mov     rbx, r9
0x180001fc4  mov     rdi, r8
0x180001fc7  mov     rsi, rdx
0x180001fca  mov     rbp, rcx
0x180001fcd  call    __local_stdio_printf_options
0x180001fd2  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001fd7  mov     r9, rdi; Format
0x180001fda  mov     r8, rsi; BufferCount
0x180001fdd  mov     [rsp+58h+Locale], 0; Locale
0x180001fe6  mov     rdx, rbp; Buffer
0x180001fe9  mov     rcx, [rax]
0x180001fec  or      rcx, 1; Options
0x180001ff0  call    _o___stdio_common_vswprintf_0
0x180001ff5  or      ecx, 0FFFFFFFFh
0x180001ff8  test    eax, eax
0x180001ffa  cmovs   eax, ecx
0x180001ffd  add     rsp, 38h
0x180002001  pop     rdi
0x180002002  pop     rsi
0x180002003  pop     rbp
0x180002004  pop     rbx
0x180002005  retn
```
