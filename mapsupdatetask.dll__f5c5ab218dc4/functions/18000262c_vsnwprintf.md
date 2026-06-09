# _vsnwprintf

- ea: `0x18000262c`
- end: `0x18000267a`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800052e0`
- `0x180006b40`

## callees

- `0x180001814`
- `0x18000256a`

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
0x18000262c  push    rbx
0x18000262e  push    rbp
0x18000262f  push    rsi
0x180002630  push    rdi
0x180002631  sub     rsp, 38h
0x180002635  mov     rbx, r9
0x180002638  mov     rdi, r8
0x18000263b  mov     rsi, rdx
0x18000263e  mov     rbp, rcx
0x180002641  call    __local_stdio_printf_options
0x180002646  mov     [rsp+58h+ArgList], rbx; ArgList
0x18000264b  mov     r9, rdi; Format
0x18000264e  mov     r8, rsi; BufferCount
0x180002651  mov     [rsp+58h+Locale], 0; Locale
0x18000265a  mov     rdx, rbp; Buffer
0x18000265d  mov     rcx, [rax]
0x180002660  or      rcx, 1; Options
0x180002664  call    _o___stdio_common_vswprintf_0
0x180002669  or      ecx, 0FFFFFFFFh
0x18000266c  test    eax, eax
0x18000266e  cmovs   eax, ecx
0x180002671  add     rsp, 38h
0x180002675  pop     rdi
0x180002676  pop     rsi
0x180002677  pop     rbp
0x180002678  pop     rbx
0x180002679  retn
```
