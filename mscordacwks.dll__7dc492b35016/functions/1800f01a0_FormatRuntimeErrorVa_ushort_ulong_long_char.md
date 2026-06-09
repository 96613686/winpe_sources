# FormatRuntimeErrorVa(ushort *,ulong,long,char *)

- ea: `0x1800f01a0`
- end: `0x1800f02f1`
- name: `?FormatRuntimeErrorVa@@YAJPEAGKJPEAD@Z`
- size: `337`
- prototype: `__int64 __fastcall(wchar_t *Buffer, unsigned int, int, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800f0418`

## callees

- `0x18000b81c`
- `0x180040fe8`
- `0x1800f0118`
- `0x1800f01a0`
- `0x1800f0d20`
- `0x1800f8f40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800f024c`
- `KERNEL32!GetLastError` at `0x1800f024c`
- `KERNEL32!FormatMessageW` at `0x1800f0214`
- `KERNEL32!FormatMessageW` at `0x1800f0214`

## string_xrefs

- `0x1800f0269`: `Common Language Runtime Internal error: 0x%08x`

## pseudocode

```c
__int64 __fastcall FormatRuntimeErrorVa(wchar_t *Buffer, __int64 a2, DWORD a3, va_list a4)
{
  unsigned __int64 v7; // r8
  signed int LastError; // ecx
  signed int v9; // eax
  bool v10; // sf
  int ResourceString; // eax
  unsigned __int64 *v13; // rax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-448h]
  wchar_t Format[512]; // [rsp+40h] [rbp-428h] BYREF

  *Buffer = 0;
  if ( (a3 & 0x1FFF0000) == 0x130000 || !HIWORD(a3) )
  {
    ResourceString = UtilLoadResourceString(4, (unsigned __int16)a3, Format);
    v10 = ResourceString < 0;
    if ( !ResourceString )
    {
      v13 = _local_stdio_printf_options();
      _stdio_common_vsnwprintf_s(*v13, Buffer, 0x1000u, 0xFFFFFFFFFFFFFFFFuLL, Format, 0, a4);
      return a3;
    }
    goto LABEL_14;
  }
  if ( !FormatMessageW(0x1000u, 0, a3, 0x400u, Buffer, 0x1000u, 0) )
  {
    LastError = GetLastError();
    if ( !LastError )
      goto LABEL_15;
    v9 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v9 = LastError;
    v10 = v9 < 0;
LABEL_14:
    if ( !v10 )
      return a3;
LABEL_15:
    LODWORD(lpBuffer) = a3;
    snwprintf_s(Buffer, 0x1000u, 0xFFFFFFFFFFFFFFFFuLL, L"Common Language Runtime Internal error: 0x%08x", lpBuffer);
    return a3;
  }
  v7 = -1;
  do
    ++v7;
  while ( Buffer[v7] );
  if ( v7 > 3 && Buffer[v7 - 2] == 13 && Buffer[v7 - 1] == 10 )
    Buffer[v7 - 2] = 0;
  return a3;
}

```

## disassembly

```asm
0x1800f01a0  mov     [rsp+arg_8], rbx
0x1800f01a5  push    rbp
0x1800f01a6  push    rdi
0x1800f01a7  push    r14
0x1800f01a9  sub     rsp, 450h
0x1800f01b0  mov     rax, cs:__security_cookie
0x1800f01b7  xor     rax, rsp
0x1800f01ba  mov     [rsp+468h+var_28], rax
0x1800f01c2  xor     r14d, r14d
0x1800f01c5  mov     eax, r8d
0x1800f01c8  and     eax, 1FFF0000h
0x1800f01cd  mov     [rcx], r14w
0x1800f01d1  mov     rbp, r9
0x1800f01d4  mov     edi, r8d
0x1800f01d7  mov     rbx, rcx
0x1800f01da  cmp     eax, 130000h
0x1800f01df  jz      loc_1800F02AB
0x1800f01e5  mov     eax, r8d
0x1800f01e8  shr     rax, 10h
0x1800f01ec  test    ax, ax
0x1800f01ef  jz      loc_1800F02AB
0x1800f01f5  mov     [rsp+468h+Arguments], r14; Arguments
0x1800f01fa  xor     edx, edx; lpSource
0x1800f01fc  mov     [rsp+468h+nSize], 1000h; nSize
0x1800f0204  mov     r9d, 400h; dwLanguageId
0x1800f020a  mov     [rsp+468h+lpBuffer], rcx; lpBuffer
0x1800f020f  mov     ecx, 1000h; dwFlags
0x1800f0214  call    cs:__imp_FormatMessageW
0x1800f021a  test    eax, eax
0x1800f021c  jz      short loc_1800F024C
0x1800f021e  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f0222  inc     r8
0x1800f0225  cmp     [rbx+r8*2], r14w
0x1800f022a  jnz     short loc_1800F0222
0x1800f022c  cmp     r8, 3
0x1800f0230  jbe     short loc_1800F0285
0x1800f0232  cmp     word ptr [rbx+r8*2-4], 0Dh
0x1800f0239  jnz     short loc_1800F0285
0x1800f023b  cmp     word ptr [rbx+r8*2-2], 0Ah
0x1800f0242  jnz     short loc_1800F0285
0x1800f0244  mov     [rbx+r8*2-4], r14w
0x1800f024a  jmp     short loc_1800F0285
0x1800f024c  call    cs:__imp_GetLastError
0x1800f0252  mov     ecx, eax
0x1800f0254  test    eax, eax
0x1800f0256  jz      short loc_1800F0269
0x1800f0258  movzx   eax, cx
0x1800f025b  or      eax, 80070000h
0x1800f0260  test    ecx, ecx
0x1800f0262  cmovle  eax, ecx
0x1800f0265  test    eax, eax
0x1800f0267  jns     short loc_1800F0285
0x1800f0269  lea     r9, aCommonLanguage; "Common Language Runtime Internal error:"...
0x1800f0270  mov     dword ptr [rsp+468h+lpBuffer], edi
0x1800f0274  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800f0278  mov     edx, 1000h; BufferCount
0x1800f027d  mov     rcx, rbx; Buffer
0x1800f0280  call    _snwprintf_s
0x1800f0285  mov     eax, edi
0x1800f0287  mov     rcx, [rsp+468h+var_28]
0x1800f028f  xor     rcx, rsp; StackCookie
0x1800f0292  call    __security_check_cookie
0x1800f0297  mov     rbx, [rsp+468h+arg_8]
0x1800f029f  add     rsp, 450h
0x1800f02a6  pop     r14
0x1800f02a8  pop     rdi
0x1800f02a9  pop     rbp
0x1800f02aa  retn
0x1800f02ab  movzx   edx, di
0x1800f02ae  lea     r8, [rsp+468h+Format]
0x1800f02b3  mov     ecx, 4
0x1800f02b8  call    ?UtilLoadResourceString@@YAJW4ResourceCategory@CCompRC@@IPEAGH@Z; UtilLoadResourceString(CCompRC::ResourceCategory,uint,ushort *,int)
0x1800f02bd  test    eax, eax
0x1800f02bf  jnz     short loc_1800F0267
0x1800f02c1  call    __local_stdio_printf_options
0x1800f02c6  lea     rcx, [rsp+468h+Format]
0x1800f02cb  mov     [rsp+468h+Arguments], rbp; ArgList
0x1800f02d0  mov     qword ptr [rsp+468h+nSize], r14; Locale
0x1800f02d5  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800f02d9  mov     [rsp+468h+lpBuffer], rcx; Format
0x1800f02de  mov     r8d, 1000h; BufferCount
0x1800f02e4  mov     rcx, [rax]; Options
0x1800f02e7  mov     rdx, rbx; Buffer
0x1800f02ea  call    __stdio_common_vsnwprintf_s
0x1800f02ef  jmp     short loc_1800F0285
```
