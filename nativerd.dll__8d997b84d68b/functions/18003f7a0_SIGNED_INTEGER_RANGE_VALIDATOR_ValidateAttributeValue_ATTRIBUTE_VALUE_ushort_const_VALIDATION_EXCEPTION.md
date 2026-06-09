# SIGNED_INTEGER_RANGE_VALIDATOR::ValidateAttributeValue(ATTRIBUTE_VALUE *,ushort const *,VALIDATION_EXCEPTION * *)

- ea: `0x18003f7a0`
- end: `0x18003f97e`
- name: `?ValidateAttributeValue@SIGNED_INTEGER_RANGE_VALIDATOR@@UEAAJPEAVATTRIBUTE_VALUE@@PEBGPEAPEAVVALIDATION_EXCEPTION@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(SIGNED_INTEGER_RANGE_VALIDATOR *__hidden this, struct ATTRIBUTE_VALUE *, const unsigned __int16 *, struct VALIDATION_EXCEPTION **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180019f88`
- `0x18001c250`
- `0x18001d2fc`
- `0x18002d45c`
- `0x18003f7a0`
- `0x180059c30`

## import_xrefs

- `msvcrt!_i64tow_s` at `0x18003f8d1`
- `msvcrt!_i64tow_s` at `0x18003f8ff`
- `msvcrt!_i64tow_s` at `0x18003f8d1`
- `msvcrt!_i64tow_s` at `0x18003f8ff`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003f8b0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003f8b0`

## pseudocode

```c
__int64 __fastcall SIGNED_INTEGER_RANGE_VALIDATOR::ValidateAttributeValue(
        SIGNED_INTEGER_RANGE_VALIDATOR *this,
        struct ATTRIBUTE_VALUE *a2,
        const unsigned __int16 *a3,
        struct VALIDATION_EXCEPTION **a4)
{
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  bool v10; // zf
  unsigned int v11; // ebx
  int v12; // eax
  VALIDATION_EXCEPTION *v13; // rax
  VALIDATION_EXCEPTION *v14; // rax
  VALIDATION_EXCEPTION *v15; // rdi
  va_list Arguments[2]; // [rsp+20h] [rbp-158h] BYREF
  __int64 v18; // [rsp+30h] [rbp-148h]
  wchar_t Buffer[64]; // [rsp+40h] [rbp-138h] BYREF
  wchar_t v20[64]; // [rsp+C0h] [rbp-B8h] BYREF

  v18 = 0;
  *(_OWORD *)Arguments = 0;
  if ( !a2 || !a3 || !a4 )
    return (unsigned int)-2147024809;
  v7 = (int)(*((_DWORD *)a2 + 1) << 27) >> 27;
  if ( v7 == 3 )
  {
    v8 = **((_QWORD **)a2 + 1);
    v9 = *((_DWORD *)this + 8);
    if ( (v9 & 2) == 0 )
      goto LABEL_12;
    v10 = v8 == 0x7FFFFFFFFFFFFFFFLL;
  }
  else
  {
    if ( v7 != 2 )
      return (unsigned int)-2147024883;
    v8 = **((int **)a2 + 1);
    v9 = *((_DWORD *)this + 8);
    if ( (v9 & 2) == 0 )
      goto LABEL_12;
    v10 = v8 == 0x7FFFFFFF;
  }
  if ( v10 )
    return 0;
LABEL_12:
  if ( v8 <= *((_QWORD *)this + 3) && v8 >= *((_QWORD *)this + 2) )
  {
    v12 = v9 << 31;
    v11 = 0;
LABEL_18:
    if ( (v12 & 0x80000000) == 0 )
      return v11;
    goto LABEL_19;
  }
  v12 = v9 << 31;
  if ( v12 < 0 )
  {
    v11 = 0;
    if ( v8 > *((_QWORD *)this + 3) || v8 < *((_QWORD *)this + 2) )
      return v11;
    goto LABEL_18;
  }
LABEL_19:
  v13 = (VALIDATION_EXCEPTION *)operator new(0x1E8u);
  if ( !v13 )
    return (unsigned int)-2147024888;
  v14 = VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(v13);
  v15 = v14;
  if ( !v14 )
    return (unsigned int)-2147024888;
  v11 = STRU::Copy((VALIDATION_EXCEPTION *)((char *)v14 + 96), a3);
  if ( (v11 & 0x80000000) == 0 )
  {
    if ( !_i64tow_s(*((_QWORD *)this + 2), Buffer, 0x40u, 10) && !_i64tow_s(*((_QWORD *)this + 3), v20, 0x40u, 10) )
    {
      Arguments[0] = (va_list)Buffer;
      Arguments[1] = (va_list)v20;
      AdminFormatMessage(
        (*((_DWORD *)this + 8) & 1) != 0 ? -1073739057 : -1073739076,
        Arguments,
        (VALIDATION_EXCEPTION *)((char *)v15 + 208),
        0);
      *a4 = v15;
      return v11;
    }
    v11 = -2147418113;
  }
  VALIDATION_EXCEPTION::DereferenceValidationException(v15);
  return v11;
}

```

## disassembly

```asm
0x18003f7a0  push    rbx
0x18003f7a2  push    rbp
0x18003f7a3  push    rsi
0x18003f7a4  push    rdi
0x18003f7a5  push    r14
0x18003f7a7  sub     rsp, 150h
0x18003f7ae  mov     rax, cs:__security_cookie
0x18003f7b5  xor     rax, rsp
0x18003f7b8  mov     [rsp+178h+var_38], rax
0x18003f7c0  xor     eax, eax
0x18003f7c2  xorps   xmm0, xmm0
0x18003f7c5  mov     [rsp+178h+var_148], rax
0x18003f7ca  mov     r14, r9
0x18003f7cd  mov     rbp, r8
0x18003f7d0  mov     rsi, rcx
0x18003f7d3  movups  xmmword ptr [rsp+178h+Arguments], xmm0
0x18003f7d8  test    rdx, rdx
0x18003f7db  jz      loc_18003F959
0x18003f7e1  test    r8, r8
0x18003f7e4  jz      loc_18003F959
0x18003f7ea  test    r9, r9
0x18003f7ed  jz      loc_18003F959
0x18003f7f3  mov     eax, [rdx+4]
0x18003f7f6  shl     eax, 1Bh
0x18003f7f9  sar     eax, 1Bh
0x18003f7fc  cmp     eax, 3
0x18003f7ff  jnz     short loc_18003F825
0x18003f801  mov     rax, [rdx+8]
0x18003f805  mov     rcx, [rax]
0x18003f808  mov     eax, [rsi+20h]
0x18003f80b  test    al, 2
0x18003f80d  jz      short loc_18003F845
0x18003f80f  mov     rdx, 7FFFFFFFFFFFFFFFh
0x18003f819  cmp     rcx, rdx
0x18003f81c  jnz     short loc_18003F845
0x18003f81e  xor     ebx, ebx
0x18003f820  jmp     loc_18003F95E
0x18003f825  cmp     eax, 2
0x18003f828  jnz     loc_18003F952
0x18003f82e  mov     rax, [rdx+8]
0x18003f832  movsxd  rcx, dword ptr [rax]
0x18003f835  mov     eax, [rsi+20h]
0x18003f838  test    al, 2
0x18003f83a  jz      short loc_18003F845
0x18003f83c  cmp     rcx, 7FFFFFFFh
0x18003f843  jmp     short loc_18003F81C
0x18003f845  mov     edx, 80000000h
0x18003f84a  cmp     rcx, [rsi+18h]
0x18003f84e  jg      short loc_18003F85D
0x18003f850  cmp     rcx, [rsi+10h]
0x18003f854  jl      short loc_18003F85D
0x18003f856  shl     eax, 1Fh
0x18003f859  xor     ebx, ebx
0x18003f85b  jmp     short loc_18003F87A
0x18003f85d  shl     eax, 1Fh
0x18003f860  test    edx, eax
0x18003f862  jz      short loc_18003F882
0x18003f864  xor     ebx, ebx
0x18003f866  cmp     rcx, [rsi+18h]
0x18003f86a  jg      loc_18003F95E
0x18003f870  cmp     rcx, [rsi+10h]
0x18003f874  jl      loc_18003F95E
0x18003f87a  test    edx, eax
0x18003f87c  jz      loc_18003F95E
0x18003f882  mov     ecx, 1E8h; Size
0x18003f887  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f88c  test    rax, rax
0x18003f88f  jz      loc_18003F94B
0x18003f895  mov     rcx, rax; this
0x18003f898  call    ??0VALIDATION_EXCEPTION@@QEAA@XZ; VALIDATION_EXCEPTION::VALIDATION_EXCEPTION(void)
0x18003f89d  mov     rdi, rax
0x18003f8a0  test    rax, rax
0x18003f8a3  jz      loc_18003F94B
0x18003f8a9  lea     rcx, [rax+60h]
0x18003f8ad  mov     rdx, rbp
0x18003f8b0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003f8b6  mov     ebx, eax
0x18003f8b8  test    eax, eax
0x18003f8ba  js      short loc_18003F8E0
0x18003f8bc  mov     rcx, [rsi+10h]; Value
0x18003f8c0  lea     rdx, [rsp+178h+Buffer]; Buffer
0x18003f8c5  mov     ebp, 0Ah
0x18003f8ca  mov     r9d, ebp; Radix
0x18003f8cd  lea     r8d, [rbp+36h]; BufferCount
0x18003f8d1  call    cs:__imp__i64tow_s
0x18003f8d7  test    eax, eax
0x18003f8d9  jz      short loc_18003F8EA
0x18003f8db  mov     ebx, 8000FFFFh
0x18003f8e0  mov     rcx, rdi; this
0x18003f8e3  call    ?DereferenceValidationException@VALIDATION_EXCEPTION@@QEAAXXZ; VALIDATION_EXCEPTION::DereferenceValidationException(void)
0x18003f8e8  jmp     short loc_18003F95E
0x18003f8ea  mov     rcx, [rsi+18h]; Value
0x18003f8ee  lea     rdx, [rsp+178h+var_B8]; Buffer
0x18003f8f6  mov     r9d, ebp; Radix
0x18003f8f9  mov     r8d, 40h ; '@'; BufferCount
0x18003f8ff  call    cs:__imp__i64tow_s
0x18003f905  test    eax, eax
0x18003f907  jnz     short loc_18003F8DB
0x18003f909  lea     rax, [rsp+178h+Buffer]
0x18003f90e  mov     [rsp+178h+Arguments], rax
0x18003f913  lea     r8, [rdi+0D0h]; struct STRU *
0x18003f91a  lea     rax, [rsp+178h+var_B8]
0x18003f922  mov     [rsp+178h+Arguments+8], rax
0x18003f927  lea     rdx, [rsp+178h+Arguments]; Arguments
0x18003f92c  mov     eax, [rsi+20h]
0x18003f92f  and     al, 1
0x18003f931  neg     al
0x18003f933  sbb     ecx, ecx
0x18003f935  xor     r9d, r9d; struct SMALL_STRU *
0x18003f938  and     ecx, 13h
0x18003f93b  add     ecx, 0C0000ABCh; dwMessageId
0x18003f941  call    ?AdminFormatMessage@@YAJKQEAPEBDPEAVSTRU@@PEAVSMALL_STRU@@@Z; AdminFormatMessage(ulong,char const * * const,STRU *,SMALL_STRU *)
0x18003f946  mov     [r14], rdi
0x18003f949  jmp     short loc_18003F95E
0x18003f94b  mov     ebx, 80070008h
0x18003f950  jmp     short loc_18003F95E
0x18003f952  mov     ebx, 8007000Dh
0x18003f957  jmp     short loc_18003F95E
0x18003f959  mov     ebx, 80070057h
0x18003f95e  mov     eax, ebx
0x18003f960  mov     rcx, [rsp+178h+var_38]
0x18003f968  xor     rcx, rsp; StackCookie
0x18003f96b  call    __security_check_cookie
0x18003f970  add     rsp, 150h
0x18003f977  pop     r14
0x18003f979  pop     rdi
0x18003f97a  pop     rsi
0x18003f97b  pop     rbp
0x18003f97c  pop     rbx
0x18003f97d  retn
```
