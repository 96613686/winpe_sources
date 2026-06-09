# _vsnwprintf

- ea: `0x180001fbc`
- end: `0x18000200a`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004bf8`
- `0x180005bb0`

## callees

- `0x180001154`
- `0x180001dca`

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
0x180001fbc  push    rbx
0x180001fbe  push    rbp
0x180001fbf  push    rsi
0x180001fc0  push    rdi
0x180001fc1  sub     rsp, 38h
0x180001fc5  mov     rbx, r9
0x180001fc8  mov     rdi, r8
0x180001fcb  mov     rsi, rdx
0x180001fce  mov     rbp, rcx
0x180001fd1  call    __local_stdio_printf_options
0x180001fd6  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001fdb  mov     r9, rdi; Format
0x180001fde  mov     r8, rsi; BufferCount
0x180001fe1  mov     [rsp+58h+Locale], 0; Locale
0x180001fea  mov     rdx, rbp; Buffer
0x180001fed  mov     rcx, [rax]
0x180001ff0  or      rcx, 1; Options
0x180001ff4  call    _o___stdio_common_vswprintf_0
0x180001ff9  or      ecx, 0FFFFFFFFh
0x180001ffc  test    eax, eax
0x180001ffe  cmovs   eax, ecx
0x180002001  add     rsp, 38h
0x180002005  pop     rdi
0x180002006  pop     rsi
0x180002007  pop     rbp
0x180002008  pop     rbx
0x180002009  retn
```
