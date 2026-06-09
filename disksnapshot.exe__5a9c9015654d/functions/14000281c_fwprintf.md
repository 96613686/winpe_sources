# fwprintf

- ea: `0x14000281c`
- end: `0x140002867`
- name: `fwprintf`
- size: `75`
- prototype: `int(FILE *const Stream, const wchar_t *const Format, ...)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002c2c`
- `0x1400032c4`
- `0x140006198`
- `0x140007534`
- `0x1400079b0`
- `0x140008a38`
- `0x140009ee0`
- `0x14000ba74`

## callees

- `0x140001944`
- `0x1400026a6`

## pseudocode

```c
int fwprintf(FILE *const Stream, const wchar_t *const Format, ...)
{
  unsigned __int64 *v4; // rax
  va_list va; // [rsp+70h] [rbp+18h] BYREF

  va_start(va, Format);
  v4 = _local_stdio_printf_options();
  return _stdio_common_vfwprintf(*v4, Stream, Format, 0, va);
}

```

## disassembly

```asm
0x14000281c  mov     rax, rsp
0x14000281f  mov     [rax+10h], rdx
0x140002823  mov     [rax+18h], r8
0x140002827  mov     [rax+20h], r9
0x14000282b  push    rbx
0x14000282c  push    rsi
0x14000282d  push    rdi
0x14000282e  sub     rsp, 40h
0x140002832  mov     rdi, rdx
0x140002835  mov     qword ptr [rax-28h], 0
0x14000283d  mov     rbx, rcx
0x140002840  lea     rsi, [rax+18h]
0x140002844  call    __local_stdio_printf_options
0x140002849  xor     r9d, r9d; Locale
0x14000284c  mov     [rsp+58h+ArgList], rsi; ArgList
0x140002851  mov     r8, rdi; Format
0x140002854  mov     rdx, rbx; Stream
0x140002857  mov     rcx, [rax]; Options
0x14000285a  call    __stdio_common_vfwprintf
0x14000285f  add     rsp, 40h
0x140002863  pop     rdi
0x140002864  pop     rsi
0x140002865  pop     rbx
0x140002866  retn
```
