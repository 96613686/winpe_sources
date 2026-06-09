# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140001574`
- end: `0x140001610`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `156`
- prototype: `__int64(wchar_t *Buffer, __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000793c`
- `0x140009104`

## callees

- `0x1400010c0`
- `0x140001574`

## import_xrefs

- `ucrtbase_clr0400!__stdio_common_vswprintf` at `0x1400015da`
- `ucrtbase_clr0400!__stdio_common_vswprintf` at `0x1400015da`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *Buffer, __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v5; // edi
  size_t v6; // rsi
  unsigned __int64 *v7; // rax
  int v8; // eax
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( (unsigned __int64)(a2 - 1) <= 0x7FFFFFFE )
  {
    v5 = 0;
    v6 = a2 - 1;
    v7 = _local_stdio_printf_options();
    v8 = __stdio_common_vswprintf(*v7 | 1, Buffer, v6, a3, 0, va);
    if ( v8 < 0 )
      v8 = -1;
    if ( v8 < 0 || v8 > v6 )
    {
      v5 = -2147024774;
    }
    else if ( v8 != v6 )
    {
      return v5;
    }
    Buffer[v6] = 0;
    return v5;
  }
  v5 = -2147024809;
  if ( a2 )
    *Buffer = 0;
  return v5;
}

```

## disassembly

```asm
0x140001574  mov     [rsp+arg_10], r8
0x140001579  mov     qword ptr [rsp+arg_18], r9
0x14000157e  push    rbx
0x14000157f  push    rbp
0x140001580  push    rsi
0x140001581  push    rdi
0x140001582  push    r14
0x140001584  push    r15
0x140001586  sub     rsp, 38h
0x14000158a  lea     rax, [rdx-1]
0x14000158e  xor     ebx, ebx
0x140001590  mov     rbp, r8
0x140001593  mov     r14, rcx
0x140001596  cmp     rax, 7FFFFFFEh
0x14000159c  jbe     short loc_1400015AD
0x14000159e  mov     edi, 80070057h
0x1400015a3  test    rdx, rdx
0x1400015a6  jz      short loc_140001601
0x1400015a8  mov     [rcx], bx
0x1400015ab  jmp     short loc_140001601
0x1400015ad  lea     r15, [rsp+68h+arg_18]
0x1400015b5  mov     edi, ebx
0x1400015b7  lea     rsi, [rdx-1]
0x1400015bb  call    __local_stdio_printf_options
0x1400015c0  mov     [rsp+68h+ArgList], r15; ArgList
0x1400015c5  mov     r9, rbp; Format
0x1400015c8  mov     r8, rsi; BufferCount
0x1400015cb  mov     [rsp+68h+Locale], rbx; Locale
0x1400015d0  mov     rdx, r14; Buffer
0x1400015d3  mov     rcx, [rax]
0x1400015d6  or      rcx, 1; Options
0x1400015da  call    cs:__imp___stdio_common_vswprintf
0x1400015e0  or      ecx, 0FFFFFFFFh
0x1400015e3  test    eax, eax
0x1400015e5  cmovs   eax, ecx
0x1400015e8  test    eax, eax
0x1400015ea  js      short loc_1400015F7
0x1400015ec  cdqe
0x1400015ee  cmp     rax, rsi
0x1400015f1  ja      short loc_1400015F7
0x1400015f3  jnz     short loc_140001601
0x1400015f5  jmp     short loc_1400015FC
0x1400015f7  mov     edi, 8007007Ah
0x1400015fc  mov     [r14+rsi*2], bx
0x140001601  mov     eax, edi
0x140001603  add     rsp, 38h
0x140001607  pop     r15
0x140001609  pop     r14
0x14000160b  pop     rdi
0x14000160c  pop     rsi
0x14000160d  pop     rbp
0x14000160e  pop     rbx
0x14000160f  retn
```
