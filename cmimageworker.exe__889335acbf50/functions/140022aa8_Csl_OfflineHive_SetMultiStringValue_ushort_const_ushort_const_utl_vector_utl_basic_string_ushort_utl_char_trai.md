# Csl::OfflineHive::SetMultiStringValue(ushort const *,ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> const &)

- ea: `0x140022aa8`
- end: `0x140022d5d`
- name: `?SetMultiStringValue@OfflineHive@Csl@@QEAAJPEBG0AEBV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `693`
- prototype: `__int64 __fastcall(Csl::OfflineHive *, const unsigned __int16 *, const unsigned __int16 *, _QWORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x14001bb2c`
- `0x14001dd28`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140002b8c`
- `0x140006fe4`
- `0x14000a7a4`
- `0x14000cbb8`
- `0x14000cccc`
- `0x140022aa8`
- `0x140022d64`
- `0x14002e8cc`

## string_xrefs

- `0x140022af8`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140022c69`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::SetMultiStringValue(
        Csl::OfflineHive *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        _QWORD *a4)
{
  void *v7; // rcx
  void *v8; // r15
  _QWORD *v9; // rbx
  __int64 v10; // r14
  __int64 v11; // rdx
  char *v12; // r8
  void *v13; // r9
  unsigned __int64 v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // rcx
  size_t v19; // rbx
  unsigned int v20; // ebx
  void *Src; // [rsp+30h] [rbp-49h] BYREF
  char *v22; // [rsp+38h] [rbp-41h]
  _WORD v23[8]; // [rsp+40h] [rbp-39h] BYREF
  void *v24; // [rsp+50h] [rbp-29h] BYREF
  char *v25; // [rsp+58h] [rbp-21h]
  _WORD v26[8]; // [rsp+60h] [rbp-19h] BYREF
  void *v27[2]; // [rsp+70h] [rbp-9h] BYREF
  _WORD v28[40]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v24 = v26;
  v25 = (char *)v26;
  v26[0] = 0;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(&v24) )
  {
    v8 = v24;
    v9 = (_QWORD *)*a4;
    Src = v23;
    v22 = (char *)v23;
    v23[0] = 0;
    v27[0] = v28;
    v10 = (v25 - (_BYTE *)v24) >> 1;
    v27[1] = v28;
    v28[0] = 0;
    while ( v9 != (_QWORD *)a4[1] )
    {
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v27,
                               *v9,
                               (__int64)(v9[1] - *v9) >> 1) )
        goto LABEL_9;
      v9 += 4;
      if ( v9 == (_QWORD *)a4[1] )
        break;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                               v27,
                               v8,
                               v10) )
      {
LABEL_9:
        if ( v27[0] != v28 )
          operator delete(v27[0], (const struct std::nothrow_t *)&std::nothrow);
        v11 = 716;
        goto LABEL_21;
      }
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      (__int64)&Src,
      (__int64)v27);
    if ( v27[0] != v28 )
      operator delete(v27[0], (const struct std::nothrow_t *)&std::nothrow);
    v12 = v22;
    v13 = Src;
    v14 = (*a4 != a4[1]) + ((v22 - (_BYTE *)Src) >> 1) + 1;
    if ( !v14 )
    {
      v15 = -1;
      v16 = -1;
LABEL_27:
      memcpy_0((void *)v15, v13, 2 * (unsigned int)((v12 - (_BYTE *)v13) >> 1) + 2);
      v20 = Csl::OfflineHive::SetValue(
              a1,
              a2,
              a3,
              (const unsigned __int8 *)v15,
              2 * (unsigned int)((v16 - v15) >> 1),
              7u);
      if ( v15 != -1 )
        operator delete((void *)v15, (const struct std::nothrow_t *)&std::nothrow);
      if ( Src != v23 )
        operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
      if ( v24 != v26 )
        operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
      return v20;
    }
    v17 = 8;
    if ( v14 > 8 )
    {
      if ( v14 > 0x3FFFFFFFFFFFFFFFLL )
        goto LABEL_20;
      v17 = (*a4 != a4[1]) + ((v22 - (_BYTE *)Src) >> 1) + 1;
    }
    v15 = (__int64)operator new(2 * v17, (const struct std::nothrow_t *)&std::nothrow);
    if ( ((v15 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      v19 = 2 * v14;
      memset_0((void *)v15, 0, v19);
      v12 = v22;
      v16 = v15 + v19;
      v13 = Src;
      goto LABEL_27;
    }
LABEL_20:
    v11 = 722;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)0x8007000ELL);
    if ( Src != v23 )
      operator delete(Src, (const struct std::nothrow_t *)&std::nothrow);
    v7 = v24;
    if ( v24 == v26 )
      return 2147942414LL;
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2C8,
    (int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
    (const char *)0x8007000ELL);
  v7 = v24;
  if ( v24 != v26 )
LABEL_24:
    operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140022aa8  mov     [rsp-8+arg_0], rcx
0x140022aad  push    rbp
0x140022aae  push    rbx
0x140022aaf  push    rsi
0x140022ab0  push    rdi
0x140022ab1  push    r12
0x140022ab3  push    r13
0x140022ab5  push    r14
0x140022ab7  push    r15
0x140022ab9  lea     rbp, [rsp-1Fh]
0x140022abe  sub     rsp, 98h
0x140022ac5  lea     rax, [rbp+57h+var_70]
0x140022ac9  mov     r12, r8
0x140022acc  mov     [rbp+57h+var_80], rax
0x140022ad0  lea     rcx, [rbp+57h+var_80]
0x140022ad4  lea     rax, [rbp+57h+var_70]
0x140022ad8  xor     r8d, r8d
0x140022adb  mov     [rbp+57h+var_78], rax
0x140022adf  mov     rsi, r9
0x140022ae2  xor     eax, eax
0x140022ae4  mov     r13, rdx
0x140022ae7  mov     [rbp+57h+var_70], ax
0x140022aeb  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(unsigned __int64,ushort)
0x140022af0  test    al, al
0x140022af2  jnz     short loc_140022B2C
0x140022af4  mov     rcx, [rbp+5Fh]; this
0x140022af8  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140022aff  mov     r9d, 8007000Eh; char *
0x140022b05  mov     edx, 2C8h; void *
0x140022b0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022b0f  mov     rcx, [rbp+57h+var_80]
0x140022b13  lea     rax, [rbp+57h+var_70]
0x140022b17  cmp     rcx, rax
0x140022b1a  jz      loc_140022CA5
0x140022b20  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140022b27  jmp     loc_140022CA0
0x140022b2c  mov     r15, [rbp+57h+var_80]
0x140022b30  lea     rax, [rbp+57h+var_90]
0x140022b34  mov     r14, [rbp+57h+var_78]
0x140022b38  mov     rbx, [rsi]
0x140022b3b  sub     r14, r15
0x140022b3e  mov     [rbp+57h+Src], rax
0x140022b42  lea     rax, [rbp+57h+var_90]
0x140022b46  mov     [rbp+57h+var_98], rax
0x140022b4a  xor     eax, eax
0x140022b4c  mov     [rbp+57h+var_90], ax
0x140022b50  lea     rax, [rbp+57h+var_50]
0x140022b54  mov     [rbp+57h+var_60], rax
0x140022b58  lea     rax, [rbp+57h+var_50]
0x140022b5c  sar     r14, 1
0x140022b5f  mov     [rbp+57h+var_58], rax
0x140022b63  xor     eax, eax
0x140022b65  mov     [rbp+57h+var_50], ax
0x140022b69  cmp     rbx, [rsi+8]
0x140022b6d  jz      short loc_140022BCC
0x140022b6f  mov     r8, [rbx+8]
0x140022b73  lea     rcx, [rbp+57h+var_60]
0x140022b77  sub     r8, [rbx]
0x140022b7a  mov     rdx, [rbx]
0x140022b7d  sar     r8, 1
0x140022b80  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x140022b85  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140022b8c  test    al, al
0x140022b8e  jz      short loc_140022BAD
0x140022b90  add     rbx, 20h ; ' '
0x140022b94  cmp     rbx, [rsi+8]
0x140022b98  jz      short loc_140022BCC
0x140022b9a  mov     r8, r14
0x140022b9d  lea     rcx, [rbp+57h+var_60]
0x140022ba1  mov     rdx, r15
0x140022ba4  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x140022ba9  test    al, al
0x140022bab  jnz     short loc_140022B69
0x140022bad  mov     rcx, [rbp+57h+var_60]; void *
0x140022bb1  lea     rax, [rbp+57h+var_50]
0x140022bb5  cmp     rcx, rax
0x140022bb8  jz      short loc_140022BC2
0x140022bba  mov     rdx, rdi; struct std::nothrow_t *
0x140022bbd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022bc2  mov     edx, 2CCh
0x140022bc7  jmp     loc_140022C65
0x140022bcc  lea     rdx, [rbp+57h+var_60]
0x140022bd0  lea     rcx, [rbp+57h+Src]
0x140022bd4  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x140022bd9  mov     rcx, [rbp+57h+var_60]; void *
0x140022bdd  lea     rax, [rbp+57h+var_50]
0x140022be1  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140022be8  cmp     rcx, rax
0x140022beb  jz      short loc_140022BF5
0x140022bed  mov     rdx, rdi; struct std::nothrow_t *
0x140022bf0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022bf5  mov     r8, [rbp+57h+var_98]
0x140022bf9  xor     ecx, ecx
0x140022bfb  mov     r9, [rbp+57h+Src]
0x140022bff  mov     rbx, r8
0x140022c02  mov     rax, [rsi+8]
0x140022c06  sub     rbx, r9
0x140022c09  sar     rbx, 1
0x140022c0c  cmp     [rsi], rax
0x140022c0f  setnz   cl
0x140022c12  inc     rbx
0x140022c15  add     rbx, rcx
0x140022c18  jnz     short loc_140022C2B
0x140022c1a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140022c1e  lea     rbx, ds:0FFFFFFFFFFFFFFFFh[rbx*2]
0x140022c26  jmp     loc_140022CCA
0x140022c2b  mov     ecx, 8
0x140022c30  cmp     rbx, rcx
0x140022c33  jbe     short loc_140022C47
0x140022c35  mov     rax, 3FFFFFFFFFFFFFFFh
0x140022c3f  cmp     rbx, rax
0x140022c42  ja      short loc_140022C60
0x140022c44  mov     rcx, rbx
0x140022c47  add     rcx, rcx; unsigned __int64
0x140022c4a  mov     rdx, rdi; struct std::nothrow_t *
0x140022c4d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140022c52  mov     rsi, rax
0x140022c55  inc     rax
0x140022c58  test    rax, 0FFFFFFFFFFFFFFFEh
0x140022c5e  jnz     short loc_140022CAF
0x140022c60  mov     edx, 2D2h; void *
0x140022c65  mov     rcx, [rbp+5Fh]; this
0x140022c69  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140022c70  mov     r9d, 8007000Eh; char *
0x140022c76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022c7b  mov     rcx, [rbp+57h+Src]; void *
0x140022c7f  lea     rax, [rbp+57h+var_90]
0x140022c83  cmp     rcx, rax
0x140022c86  jz      short loc_140022C90
0x140022c88  mov     rdx, rdi; struct std::nothrow_t *
0x140022c8b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022c90  mov     rcx, [rbp+57h+var_80]; void *
0x140022c94  lea     rax, [rbp+57h+var_70]
0x140022c98  cmp     rcx, rax
0x140022c9b  jz      short loc_140022CA5
0x140022c9d  mov     rdx, rdi; struct std::nothrow_t *
0x140022ca0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022ca5  mov     eax, 8007000Eh
0x140022caa  jmp     loc_140022D48
0x140022caf  add     rbx, rbx
0x140022cb2  xor     edx, edx; Val
0x140022cb4  mov     r8, rbx; Size
0x140022cb7  mov     rcx, rsi; void *
0x140022cba  call    memset_0
0x140022cbf  mov     r8, [rbp+57h+var_98]
0x140022cc3  add     rbx, rsi
0x140022cc6  mov     r9, [rbp+57h+Src]
0x140022cca  sub     r8, r9
0x140022ccd  mov     rdx, r9; Src
0x140022cd0  sar     r8, 1
0x140022cd3  mov     rcx, rsi; void *
0x140022cd6  lea     r8d, ds:2[r8*2]; Size
0x140022cde  call    memcpy_0
0x140022ce3  mov     rcx, [rbp+57h+arg_0]; this
0x140022ce7  sub     rbx, rsi
0x140022cea  sar     rbx, 1
0x140022ced  mov     r9, rsi; unsigned __int8 *
0x140022cf0  add     ebx, ebx
0x140022cf2  mov     [rsp+0D0h+var_A8], 7; unsigned int
0x140022cfa  mov     r8, r12; unsigned __int16 *
0x140022cfd  mov     [rsp+0D0h+var_B0], ebx; unsigned int
0x140022d01  mov     rdx, r13; unsigned __int16 *
0x140022d04  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x140022d09  mov     ebx, eax
0x140022d0b  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140022d0f  jz      short loc_140022D1C
0x140022d11  mov     rdx, rdi; struct std::nothrow_t *
0x140022d14  mov     rcx, rsi; void *
0x140022d17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022d1c  mov     rcx, [rbp+57h+Src]; void *
0x140022d20  lea     rax, [rbp+57h+var_90]
0x140022d24  cmp     rcx, rax
0x140022d27  jz      short loc_140022D31
0x140022d29  mov     rdx, rdi; struct std::nothrow_t *
0x140022d2c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022d31  mov     rcx, [rbp+57h+var_80]; void *
0x140022d35  lea     rax, [rbp+57h+var_70]
0x140022d39  cmp     rcx, rax
0x140022d3c  jz      short loc_140022D46
0x140022d3e  mov     rdx, rdi; struct std::nothrow_t *
0x140022d41  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022d46  mov     eax, ebx
0x140022d48  add     rsp, 98h
0x140022d4f  pop     r15
0x140022d51  pop     r14
0x140022d53  pop     r13
0x140022d55  pop     r12
0x140022d57  pop     rdi
0x140022d58  pop     rsi
0x140022d59  pop     rbx
0x140022d5a  pop     rbp
0x140022d5b  retn
```
