# _vsnwprintf

- ea: `0x180002624`
- end: `0x180002672`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a89c`
- `0x18000a9a4`
- `0x18000cb30`
- `0x18000d2e0`

## callees

- `0x180001914`
- `0x180002586`

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
0x180002624  push    rbx
0x180002626  push    rbp
0x180002627  push    rsi
0x180002628  push    rdi
0x180002629  sub     rsp, 38h
0x18000262d  mov     rbx, r9
0x180002630  mov     rdi, r8
0x180002633  mov     rsi, rdx
0x180002636  mov     rbp, rcx
0x180002639  call    __local_stdio_printf_options
0x18000263e  mov     [rsp+58h+ArgList], rbx; ArgList
0x180002643  mov     r9, rdi; Format
0x180002646  mov     r8, rsi; BufferCount
0x180002649  mov     [rsp+58h+Locale], 0; Locale
0x180002652  mov     rdx, rbp; Buffer
0x180002655  mov     rcx, [rax]
0x180002658  or      rcx, 1; Options
0x18000265c  call    _o___stdio_common_vswprintf_0
0x180002661  or      ecx, 0FFFFFFFFh
0x180002664  test    eax, eax
0x180002666  cmovs   eax, ecx
0x180002669  add     rsp, 38h
0x18000266d  pop     rdi
0x18000266e  pop     rsi
0x18000266f  pop     rbp
0x180002670  pop     rbx
0x180002671  retn
```
