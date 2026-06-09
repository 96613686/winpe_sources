# VFormatString_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____

- ea: `0x180189d20`
- end: `0x180189dee`
- name: `VFormatString_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18018b9e4`

## callees

- `0x180021788`
- `0x180189f70`
- `0x18018a73c`
- `0x18018c3cc`
- `0x180195f48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x180189d61`
- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x180189d61`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VFormatString_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____(
        __int64 a1,
        const wchar_t *a2,
        va_list a3)
{
  unsigned __int64 *v6; // rax
  int v7; // eax
  wchar_t *Buffer[2]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v10; // [rsp+50h] [rbp-38h]
  __int64 v11; // [rsp+90h] [rbp+8h] BYREF

  v11 = a1;
  v6 = _local_stdio_printf_options();
  v7 = __stdio_common_vswprintf(*v6 | 2, 0, 0, a2, 0, a3);
  if ( v7 < 0 )
    v7 = -1;
  LOWORD(v11) = 0;
  *(_OWORD *)Buffer = 0;
  v10 = 0;
  std::vector<unsigned short>::_Construct_n<unsigned short const &>(Buffer, v7 + 1LL, &v11);
  vsnwprintf_s_l(Buffer[0], Buffer[1] - Buffer[0], 0xFFFFFFFFFFFFFFFFuLL, a2, 0, a3);
  std::wstring::wstring(a1, Buffer[0]);
  std::vector<unsigned short>::_Tidy(Buffer);
  return a1;
}

```

## disassembly

```asm
0x180189d20  mov     [rsp+arg_0], rcx
0x180189d25  push    rbx
0x180189d26  push    rbp
0x180189d27  push    rsi
0x180189d28  push    rdi
0x180189d29  sub     rsp, 68h
0x180189d2d  mov     [rsp+88h+var_50], 0FFFFFFFFFFFFFFFEh
0x180189d36  mov     rbx, r8
0x180189d39  mov     rdi, rdx
0x180189d3c  mov     rsi, rcx
0x180189d3f  call    __local_stdio_printf_options
0x180189d44  mov     rcx, [rax]
0x180189d47  or      rcx, 2; Options
0x180189d4b  mov     [rsp+88h+ArgList], rbx; ArgList
0x180189d50  mov     [rsp+88h+Locale], 0; Locale
0x180189d59  mov     r9, rdi; Format
0x180189d5c  xor     r8d, r8d; BufferCount
0x180189d5f  xor     edx, edx; Buffer
0x180189d61  call    cs:__imp___stdio_common_vswprintf
0x180189d67  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180189d6b  test    eax, eax
0x180189d6d  cmovs   eax, ebp
0x180189d70  xor     ecx, ecx
0x180189d72  mov     word ptr [rsp+88h+arg_0], cx
0x180189d7a  xorps   xmm0, xmm0
0x180189d7d  movdqu  xmmword ptr [rsp+88h+Buffer], xmm0
0x180189d83  mov     [rsp+88h+var_38], rcx
0x180189d88  movsxd  rdx, eax
0x180189d8b  inc     rdx
0x180189d8e  lea     r8, [rsp+88h+arg_0]
0x180189d96  lea     rcx, [rsp+88h+Buffer]
0x180189d9b  call    ??$_Construct_n@AEBG@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBG@Z; std::vector<ushort>::_Construct_n<ushort const &>(unsigned __int64,ushort const &)
0x180189da0  nop
0x180189da1  mov     rdx, [rsp+88h+Buffer+8]
0x180189da6  mov     rcx, [rsp+88h+Buffer]; Buffer
0x180189dab  sub     rdx, rcx
0x180189dae  sar     rdx, 1; BufferCount
0x180189db1  mov     [rsp+88h+ArgList], rbx; ArgList
0x180189db6  mov     [rsp+88h+Locale], 0; Locale
0x180189dbf  mov     r9, rdi; Format
0x180189dc2  mov     r8, rbp; MaxCount
0x180189dc5  call    _vsnwprintf_s_l
0x180189dca  mov     rdx, [rsp+88h+Buffer]
0x180189dcf  mov     rcx, rsi
0x180189dd2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180189dd7  nop
0x180189dd8  lea     rcx, [rsp+88h+Buffer]
0x180189ddd  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180189de2  mov     rax, rsi
0x180189de5  add     rsp, 68h
0x180189de9  pop     rdi
0x180189dea  pop     rsi
0x180189deb  pop     rbp
0x180189dec  pop     rbx
0x180189ded  retn
```
