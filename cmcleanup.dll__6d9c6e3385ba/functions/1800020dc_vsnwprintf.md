# _vsnwprintf

- ea: `0x1800020dc`
- end: `0x18000212a`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005090`
- `0x180007370`

## callees

- `0x180001144`
- `0x180001ffa`

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
0x1800020dc  push    rbx
0x1800020de  push    rbp
0x1800020df  push    rsi
0x1800020e0  push    rdi
0x1800020e1  sub     rsp, 38h
0x1800020e5  mov     rbx, r9
0x1800020e8  mov     rdi, r8
0x1800020eb  mov     rsi, rdx
0x1800020ee  mov     rbp, rcx
0x1800020f1  call    __local_stdio_printf_options
0x1800020f6  mov     [rsp+58h+ArgList], rbx; ArgList
0x1800020fb  mov     r9, rdi; Format
0x1800020fe  mov     r8, rsi; BufferCount
0x180002101  mov     [rsp+58h+Locale], 0; Locale
0x18000210a  mov     rdx, rbp; Buffer
0x18000210d  mov     rcx, [rax]
0x180002110  or      rcx, 1; Options
0x180002114  call    _o___stdio_common_vswprintf_0
0x180002119  or      ecx, 0FFFFFFFFh
0x18000211c  test    eax, eax
0x18000211e  cmovs   eax, ecx
0x180002121  add     rsp, 38h
0x180002125  pop     rdi
0x180002126  pop     rsi
0x180002127  pop     rbp
0x180002128  pop     rbx
0x180002129  retn
```
