# DbgWPrintf(ushort const * const,...)

- ea: `0x18002fc18`
- end: `0x18002fce7`
- name: `?DbgWPrintf@@YAXQEBGZZ`
- size: `207`
- prototype: `void(const wchar_t *, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002fce8`

## callees

- `0x1800177e8`
- `0x18002fbd4`
- `0x18002fc18`
- `0x18003dc30`
- `0x18003f110`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18002fc93`
- `KERNEL32!OutputDebugStringW` at `0x18002fc93`
- `KERNEL32!IsDebuggerPresent` at `0x18002fc84`
- `KERNEL32!IsDebuggerPresent` at `0x18002fc84`
- `ucrtbase_clr0400!__stdio_common_vsnwprintf_s` at `0x18002fc7e`
- `ucrtbase_clr0400!__stdio_common_vsnwprintf_s` at `0x18002fc7e`
- `ucrtbase_clr0400!fflush` at `0x18002fcc7`
- `ucrtbase_clr0400!fflush` at `0x18002fcc7`
- `ucrtbase_clr0400!__acrt_iob_func` at `0x18002fca2`
- `ucrtbase_clr0400!__acrt_iob_func` at `0x18002fcbe`
- `ucrtbase_clr0400!__acrt_iob_func` at `0x18002fca2`
- `ucrtbase_clr0400!__acrt_iob_func` at `0x18002fcbe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void DbgWPrintf(const wchar_t *a1, ...)
{
  unsigned __int64 *v2; // rax
  FILE *v3; // rax
  FILE *v4; // rax
  wchar_t Buffer[4096]; // [rsp+40h] [rbp-2028h] BYREF
  va_list va; // [rsp+2078h] [rbp+10h] BYREF

  va_start(va, a1);
  v2 = _local_stdio_printf_options();
  __stdio_common_vsnwprintf_s(*v2, Buffer, 0x1000u, 0xFFFFFFFFFFFFFFFFuLL, a1, 0, va);
  if ( IsDebuggerPresent() )
  {
    OutputDebugStringW(Buffer);
  }
  else
  {
    v3 = __acrt_iob_func(1u);
    fwprintf(v3, L"%s", Buffer);
    v4 = __acrt_iob_func(1u);
    fflush(v4);
  }
}

```

## disassembly

```asm
0x18002fc18  mov     rax, rsp
0x18002fc1b  mov     [rax+8], rcx
0x18002fc1f  mov     [rax+10h], rdx
0x18002fc23  mov     [rax+18h], r8
0x18002fc27  mov     [rax+20h], r9
0x18002fc2b  push    rbx
0x18002fc2c  push    rdi
0x18002fc2d  mov     eax, 2058h
0x18002fc32  call    _alloca_probe
0x18002fc37  sub     rsp, rax
0x18002fc3a  mov     rax, cs:__security_cookie
0x18002fc41  xor     rax, rsp
0x18002fc44  mov     [rsp+2068h+var_28], rax
0x18002fc4c  mov     rbx, rcx
0x18002fc4f  lea     rdi, [rsp+2068h+arg_8]
0x18002fc57  call    __local_stdio_printf_options
0x18002fc5c  mov     [rsp+2068h+ArgList], rdi; ArgList
0x18002fc61  lea     rdx, [rsp+2068h+Buffer]; Buffer
0x18002fc66  and     [rsp+2068h+var_2040], 0
0x18002fc6c  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18002fc70  mov     r8d, 1000h; BufferCount
0x18002fc76  mov     [rsp+2068h+Format], rbx; Format
0x18002fc7b  mov     rcx, [rax]; Options
0x18002fc7e  call    cs:__imp___stdio_common_vsnwprintf_s
0x18002fc84  call    cs:__imp_IsDebuggerPresent
0x18002fc8a  test    eax, eax
0x18002fc8c  jz      short loc_18002FC9B
0x18002fc8e  lea     rcx, [rsp+2068h+Buffer]; lpOutputString
0x18002fc93  call    cs:__imp_OutputDebugStringW
0x18002fc99  jmp     short loc_18002FCCD
0x18002fc9b  mov     ebx, 1
0x18002fca0  mov     ecx, ebx; Ix
0x18002fca2  call    cs:__imp___acrt_iob_func
0x18002fca8  mov     rcx, rax; Stream
0x18002fcab  lea     r8, [rsp+2068h+Buffer]
0x18002fcb0  lea     rdx, aS_7; "%s"
0x18002fcb7  call    fwprintf
0x18002fcbc  mov     ecx, ebx; Ix
0x18002fcbe  call    cs:__imp___acrt_iob_func
0x18002fcc4  mov     rcx, rax; Stream
0x18002fcc7  call    cs:__imp_fflush
0x18002fccd  mov     rcx, [rsp+2068h+var_28]
0x18002fcd5  xor     rcx, rsp; StackCookie
0x18002fcd8  call    __security_check_cookie
0x18002fcdd  add     rsp, 2058h
0x18002fce4  pop     rdi
0x18002fce5  pop     rbx
0x18002fce6  retn
```
