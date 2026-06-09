# _vswprintf_s_l

- ea: `0x180021424`
- end: `0x180021473`
- name: `_vswprintf_s_l`
- size: `79`
- prototype: `int __cdecl(wchar_t *const Buffer, const size_t BufferCount, const wchar_t *const Format, const _locale_t Locale, va_list ArgList)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180021340`
- `0x180021374`
- `0x18018a578`
- `0x18018a5b8`
- `0x1801abff8`
- `0x1801ad080`

## callees

- `0x180021788`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf_s` at `0x18002145c`
- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf_s` at `0x18002145c`

## pseudocode

```c
int __cdecl vswprintf_s_l(
        wchar_t *const Buffer,
        const size_t BufferCount,
        const wchar_t *const Format,
        const _locale_t Locale,
        va_list ArgList)
{
  unsigned __int64 *v9; // rax
  int result; // eax

  v9 = _local_stdio_printf_options();
  result = _o___stdio_common_vswprintf_s(*v9, Buffer, BufferCount, Format, Locale, ArgList);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x180021424  push    rbx
0x180021426  push    rbp
0x180021427  push    rsi
0x180021428  push    rdi
0x180021429  sub     rsp, 38h
0x18002142d  mov     rbx, r9
0x180021430  mov     rdi, r8
0x180021433  mov     rsi, rdx
0x180021436  mov     rbp, rcx
0x180021439  call    __local_stdio_printf_options
0x18002143e  mov     r10, [rsp+58h+ArgList]
0x180021446  mov     r9, rdi
0x180021449  mov     [rsp+58h+var_30], r10
0x18002144e  mov     r8, rsi
0x180021451  mov     rdx, rbp
0x180021454  mov     [rsp+58h+var_38], rbx
0x180021459  mov     rcx, [rax]
0x18002145c  call    cs:__imp__o___stdio_common_vswprintf_s
0x180021462  or      ecx, 0FFFFFFFFh
0x180021465  test    eax, eax
0x180021467  cmovs   eax, ecx
0x18002146a  add     rsp, 38h
0x18002146e  pop     rdi
0x18002146f  pop     rsi
0x180021470  pop     rbp
0x180021471  pop     rbx
0x180021472  retn
```
