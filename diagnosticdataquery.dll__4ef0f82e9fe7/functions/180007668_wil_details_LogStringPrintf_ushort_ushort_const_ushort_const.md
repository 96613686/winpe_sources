# wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)

- ea: `0x180007668`
- end: `0x18000770a`
- name: `?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ`
- size: `162`
- prototype: `unsigned __int16 *(wchar_t *Buffer, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006a04`

## callees

- `0x180007668`
- `0x180008b68`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1800076c5`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1800076c5`

## pseudocode

```c
unsigned __int16 *wil::details::LogStringPrintf(
        wchar_t *Buffer,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        ...)
{
  unsigned __int64 v4; // rdi
  wchar_t *v7; // rbx
  size_t v8; // rdi
  unsigned __int64 *v9; // rax
  int v10; // eax
  __int64 v11; // rax
  const unsigned __int16 *ArgList; // [rsp+98h] [rbp+20h] BYREF

  ArgList = a4;
  v4 = a2 - Buffer;
  v7 = Buffer;
  if ( v4 )
  {
    if ( v4 > 0x7FFFFFFF )
    {
      *Buffer = 0;
    }
    else
    {
      v8 = v4 - 1;
      v9 = _local_stdio_printf_options();
      v10 = __stdio_common_vswprintf(*v9 | 1, v7, v8, a3, 0, (va_list)&ArgList);
      if ( v10 < 0 || v10 >= v8 )
        v7[v8] = 0;
    }
  }
  if ( a2 != v7 )
  {
    v11 = -1;
    do
      ++v11;
    while ( v7[v11] );
    v7 += v11;
  }
  return v7;
}

```

## disassembly

```asm
0x180007668  mov     rax, rsp
0x18000766b  mov     [rax+18h], r8
0x18000766f  mov     [rax+20h], r9
0x180007673  push    rbx
0x180007674  push    rbp
0x180007675  push    rsi
0x180007676  push    rdi
0x180007677  push    r14
0x180007679  push    r15
0x18000767b  sub     rsp, 48h
0x18000767f  mov     rdi, rdx
0x180007682  lea     r15, [rax+20h]
0x180007686  sub     rdi, rcx
0x180007689  xor     r14d, r14d
0x18000768c  sar     rdi, 1
0x18000768f  mov     rbp, r8
0x180007692  mov     rsi, rdx
0x180007695  mov     rbx, rcx
0x180007698  jz      short loc_1800076E3
0x18000769a  cmp     rdi, 7FFFFFFFh
0x1800076a1  ja      short loc_1800076DF
0x1800076a3  dec     rdi
0x1800076a6  call    __local_stdio_printf_options
0x1800076ab  mov     [rsp+78h+ArgList], r15; ArgList
0x1800076b0  mov     r9, rbp; Format
0x1800076b3  mov     r8, rdi; BufferCount
0x1800076b6  mov     [rsp+78h+Locale], r14; Locale
0x1800076bb  mov     rdx, rbx; Buffer
0x1800076be  mov     rcx, [rax]
0x1800076c1  or      rcx, 1; Options
0x1800076c5  call    cs:__imp___stdio_common_vswprintf
0x1800076cb  test    eax, eax
0x1800076cd  js      short loc_1800076D8
0x1800076cf  cdqe
0x1800076d1  cmp     rax, rdi
0x1800076d4  ja      short loc_1800076D8
0x1800076d6  jnz     short loc_1800076E3
0x1800076d8  mov     [rbx+rdi*2], r14w
0x1800076dd  jmp     short loc_1800076E3
0x1800076df  mov     [rcx], r14w
0x1800076e3  cmp     rsi, rbx
0x1800076e6  jz      short loc_1800076FA
0x1800076e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800076ec  inc     rax
0x1800076ef  cmp     [rbx+rax*2], r14w
0x1800076f4  jnz     short loc_1800076EC
0x1800076f6  lea     rbx, [rbx+rax*2]
0x1800076fa  mov     rax, rbx
0x1800076fd  add     rsp, 48h
0x180007701  pop     r15
0x180007703  pop     r14
0x180007705  pop     rdi
0x180007706  pop     rsi
0x180007707  pop     rbp
0x180007708  pop     rbx
0x180007709  retn
```
