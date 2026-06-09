# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180008490`
- end: `0x18000853e`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `174`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800060c8`

## callees

- `0x180008490`
- `0x180008b68`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1800084f7`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1800084f7`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *Buffer, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v5; // edx
  size_t v6; // rbx
  unsigned __int64 *v7; // rax
  int v8; // eax
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v6 = a2 - 1;
      v7 = _local_stdio_printf_options();
      v8 = __stdio_common_vswprintf(*v7 | 1, Buffer, v6, a3, 0, va);
      if ( v8 < 0 || v8 > v6 )
      {
        v5 = -2147024774;
        Buffer[v6] = 0;
      }
      else
      {
        v5 = 0;
        if ( v8 == v6 )
          Buffer[v6] = 0;
      }
    }
    else
    {
      v5 = -2147024809;
      *Buffer = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x180008490  mov     [rsp+arg_10], r8
0x180008495  mov     qword ptr [rsp+arg_18], r9
0x18000849a  push    rbx
0x18000849b  push    rbp
0x18000849c  push    rsi
0x18000849d  push    rdi
0x18000849e  sub     rsp, 48h
0x1800084a2  mov     rsi, r8
0x1800084a5  mov     rax, rdx
0x1800084a8  mov     rdi, rcx
0x1800084ab  test    rdx, rdx
0x1800084ae  jz      short loc_180008524
0x1800084b0  cmp     rax, 7FFFFFFFh
0x1800084b6  jbe     short loc_1800084BF
0x1800084b8  mov     edx, 80070057h
0x1800084bd  jmp     short loc_18000852E
0x1800084bf  mov     [rsp+68h+var_38], 0
0x1800084c8  lea     rbp, [rsp+68h+arg_18]
0x1800084d0  lea     rbx, [rdx-1]
0x1800084d4  call    __local_stdio_printf_options
0x1800084d9  mov     [rsp+68h+ArgList], rbp; ArgList
0x1800084de  mov     r9, rsi; Format
0x1800084e1  mov     r8, rbx; BufferCount
0x1800084e4  mov     [rsp+68h+Locale], 0; Locale
0x1800084ed  mov     rdx, rdi; Buffer
0x1800084f0  mov     rcx, [rax]
0x1800084f3  or      rcx, 1; Options
0x1800084f7  call    cs:__imp___stdio_common_vswprintf
0x1800084fd  test    eax, eax
0x1800084ff  js      short loc_180008517
0x180008501  cdqe
0x180008503  cmp     rax, rbx
0x180008506  ja      short loc_180008517
0x180008508  xor     edx, edx
0x18000850a  cmp     rax, rbx
0x18000850d  jnz     short loc_180008533
0x18000850f  xor     eax, eax
0x180008511  mov     [rdi+rbx*2], ax
0x180008515  jmp     short loc_180008533
0x180008517  xor     eax, eax
0x180008519  mov     edx, 8007007Ah
0x18000851e  mov     [rdi+rbx*2], ax
0x180008522  jmp     short loc_180008533
0x180008524  mov     edx, 80070057h
0x180008529  test    rax, rax
0x18000852c  jz      short loc_180008533
0x18000852e  xor     ecx, ecx
0x180008530  mov     [rdi], cx
0x180008533  mov     eax, edx
0x180008535  add     rsp, 48h
0x180008539  pop     rdi
0x18000853a  pop     rsi
0x18000853b  pop     rbp
0x18000853c  pop     rbx
0x18000853d  retn
```
