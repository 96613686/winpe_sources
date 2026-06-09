# _vsnwprintf

- ea: `0x180001ff8`
- end: `0x180002046`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004190`
- `0x180005114`

## callees

- `0x180001284`
- `0x180001f5a`

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
0x180001ff8  push    rbx
0x180001ffa  push    rbp
0x180001ffb  push    rsi
0x180001ffc  push    rdi
0x180001ffd  sub     rsp, 38h
0x180002001  mov     rbx, r9
0x180002004  mov     rdi, r8
0x180002007  mov     rsi, rdx
0x18000200a  mov     rbp, rcx
0x18000200d  call    __local_stdio_printf_options
0x180002012  mov     [rsp+58h+ArgList], rbx; ArgList
0x180002017  mov     r9, rdi; Format
0x18000201a  mov     r8, rsi; BufferCount
0x18000201d  mov     [rsp+58h+Locale], 0; Locale
0x180002026  mov     rdx, rbp; Buffer
0x180002029  mov     rcx, [rax]
0x18000202c  or      rcx, 1; Options
0x180002030  call    _o___stdio_common_vswprintf_0
0x180002035  or      ecx, 0FFFFFFFFh
0x180002038  test    eax, eax
0x18000203a  cmovs   eax, ecx
0x18000203d  add     rsp, 38h
0x180002041  pop     rdi
0x180002042  pop     rsi
0x180002043  pop     rbp
0x180002044  pop     rbx
0x180002045  retn
```
