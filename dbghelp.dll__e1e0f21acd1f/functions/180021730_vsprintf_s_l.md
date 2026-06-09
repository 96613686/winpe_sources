# _vsprintf_s_l

- ea: `0x180021730`
- end: `0x18002177f`
- name: `_vsprintf_s_l`
- size: `79`
- prototype: `int __cdecl(char *const Buffer, const size_t BufferCount, const char *const Format, const _locale_t Locale, va_list ArgList)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016b34`
- `0x180021688`
- `0x1800216d8`
- `0x18019b9f0`
- `0x1801acb50`
- `0x1801acbb4`
- `0x1801acc18`
- `0x1801accb8`
- `0x1801acfd8`

## callees

- `0x180021788`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf_s` at `0x180021768`
- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf_s` at `0x180021768`

## pseudocode

```c
int __cdecl vsprintf_s_l(
        char *const Buffer,
        const size_t BufferCount,
        const char *const Format,
        const _locale_t Locale,
        va_list ArgList)
{
  unsigned __int64 *v9; // rax
  int result; // eax

  v9 = _local_stdio_printf_options();
  result = _o___stdio_common_vsprintf_s(*v9, Buffer, BufferCount, Format, Locale, ArgList);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x180021730  push    rbx
0x180021732  push    rbp
0x180021733  push    rsi
0x180021734  push    rdi
0x180021735  sub     rsp, 38h
0x180021739  mov     rbx, r9
0x18002173c  mov     rdi, r8
0x18002173f  mov     rsi, rdx
0x180021742  mov     rbp, rcx
0x180021745  call    __local_stdio_printf_options
0x18002174a  mov     r10, [rsp+58h+ArgList]
0x180021752  mov     r9, rdi
0x180021755  mov     [rsp+58h+var_30], r10
0x18002175a  mov     r8, rsi
0x18002175d  mov     rdx, rbp
0x180021760  mov     [rsp+58h+var_38], rbx
0x180021765  mov     rcx, [rax]
0x180021768  call    cs:__imp__o___stdio_common_vsprintf_s
0x18002176e  or      ecx, 0FFFFFFFFh
0x180021771  test    eax, eax
0x180021773  cmovs   eax, ecx
0x180021776  add     rsp, 38h
0x18002177a  pop     rdi
0x18002177b  pop     rsi
0x18002177c  pop     rbp
0x18002177d  pop     rbx
0x18002177e  retn
```
