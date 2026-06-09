# Csl::GetSystemDirectoryPath(Csl::Path &)

- ea: `0x14000bebc`
- end: `0x14000c05b`
- name: `?GetSystemDirectoryPath@Csl@@YAJAEAVPath@1@@Z`
- size: `415`
- prototype: `__int64 __fastcall(Csl *__hidden this, struct Path *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000c064`
- `0x140017868`
- `0x140018d5c`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140002bb0`
- `0x140006fc4`
- `0x140006fe4`
- `0x14000a7a4`
- `0x14000aa58`
- `0x14000bebc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14000bed5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14000bf46`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14000bed5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14000bf46`

## pseudocode

```c
__int64 __fastcall Csl::GetSystemDirectoryPath(Csl *this, struct Path *a2)
{
  UINT SystemDirectoryW; // ebx
  const char *v4; // r9
  __int64 v6; // rsi
  unsigned __int64 v7; // r14
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  UINT v10; // eax
  const struct std::nothrow_t *v11; // rdx
  const char *v12; // r9
  unsigned int LastError; // ebx
  const struct std::nothrow_t *v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  _QWORD v16[2]; // [rsp+20h] [rbp-30h] BYREF
  void *v17[2]; // [rsp+30h] [rbp-20h] BYREF
  _WORD v18[8]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  if ( !SystemDirectoryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x523,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
             v4);
  v6 = -1;
  while ( 1 )
  {
    v7 = 2LL * SystemDirectoryW;
    if ( !is_mul_ok(SystemDirectoryW, 2u) )
      v7 = -1;
    v8 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( !v8 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)0x8007000ELL,
        v16[0]);
      return LastError;
    }
    memset_0(v8, 0, v7);
    v10 = GetSystemDirectoryW(v9, SystemDirectoryW);
    if ( !v10 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x532,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
                    v12);
      goto LABEL_19;
    }
    if ( v10 <= SystemDirectoryW )
      break;
    SystemDirectoryW = v10;
    operator delete(v9, v11);
  }
  v18[0] = 0;
  v17[0] = v18;
  v17[1] = v18;
  v16[0] = v9;
  do
    ++v6;
  while ( v9[v6] );
  v16[1] = v6;
  if ( !Csl::Path::Assign((Csl::Path *)v17, (__int64)v16) )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      v16[0]);
    if ( v17[0] != v18 )
      operator delete(v17[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_19:
    operator delete(v9, v14);
    return LastError;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    (__int64)this,
    (__int64)v17);
  if ( v17[0] != v18 )
    operator delete(v17[0], (const struct std::nothrow_t *)&std::nothrow);
  operator delete(v9, v15);
  return 0;
}

```

## disassembly

```asm
0x14000bebc  push    rbp
0x14000bebe  push    rbx
0x14000bebf  push    rsi
0x14000bec0  push    rdi
0x14000bec1  push    r12
0x14000bec3  push    r14
0x14000bec5  push    r15
0x14000bec7  mov     rbp, rsp
0x14000beca  sub     rsp, 50h
0x14000bece  mov     r15, rcx
0x14000bed1  xor     edx, edx; uSize
0x14000bed3  xor     ecx, ecx; lpBuffer
0x14000bed5  call    cs:__imp_GetSystemDirectoryW
0x14000bedc  nop     dword ptr [rax+rax+00h]
0x14000bee1  xor     r12d, r12d
0x14000bee4  mov     ebx, eax
0x14000bee6  test    eax, eax
0x14000bee8  jnz     short loc_14000BF04
0x14000beea  mov     rcx, [rbp+38h]; this
0x14000beee  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000bef5  mov     edx, 523h; void *
0x14000befa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000beff  jmp     loc_14000C04B
0x14000bf04  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000bf08  mov     ecx, ebx
0x14000bf0a  mov     eax, 2
0x14000bf0f  mul     rcx
0x14000bf12  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bf19  mov     r14, rax
0x14000bf1c  cmovb   r14, rsi
0x14000bf20  mov     rcx, r14; unsigned __int64
0x14000bf23  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000bf28  mov     rdi, rax
0x14000bf2b  test    rax, rax
0x14000bf2e  jz      loc_14000C02C
0x14000bf34  mov     r8, r14; Size
0x14000bf37  xor     edx, edx; Val
0x14000bf39  mov     rcx, rax; void *
0x14000bf3c  call    memset_0
0x14000bf41  mov     edx, ebx; uSize
0x14000bf43  mov     rcx, rdi; lpBuffer
0x14000bf46  call    cs:__imp_GetSystemDirectoryW
0x14000bf4d  nop     dword ptr [rax+rax+00h]
0x14000bf52  test    eax, eax
0x14000bf54  jz      loc_14000C00B
0x14000bf5a  cmp     eax, ebx
0x14000bf5c  jbe     short loc_14000BF6A
0x14000bf5e  mov     rcx, rdi; void *
0x14000bf61  mov     ebx, eax
0x14000bf63  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000bf68  jmp     short loc_14000BF08
0x14000bf6a  lea     rax, [rbp+var_10]
0x14000bf6e  mov     [rbp+var_10], r12w
0x14000bf73  mov     [rbp+var_20], rax
0x14000bf77  lea     rax, [rbp+var_10]
0x14000bf7b  mov     [rbp+var_18], rax
0x14000bf7f  mov     [rbp+var_30], rdi
0x14000bf83  inc     rsi
0x14000bf86  cmp     [rdi+rsi*2], r12w
0x14000bf8b  jnz     short loc_14000BF83
0x14000bf8d  lea     rdx, [rbp+var_30]
0x14000bf91  mov     [rbp+var_28], rsi
0x14000bf95  lea     rcx, [rbp+var_20]; this
0x14000bf99  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14000bf9e  test    al, al
0x14000bfa0  jnz     short loc_14000BFDA
0x14000bfa2  mov     rcx, [rbp+38h]; this
0x14000bfa6  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000bfad  mov     ebx, 8007000Eh
0x14000bfb2  mov     edx, 53Eh; void *
0x14000bfb7  mov     r9d, ebx; char *
0x14000bfba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bfbf  mov     rcx, [rbp+var_20]; void *
0x14000bfc3  lea     rax, [rbp+var_10]
0x14000bfc7  cmp     rcx, rax
0x14000bfca  jz      short loc_14000C022
0x14000bfcc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bfd3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000bfd8  jmp     short loc_14000C022
0x14000bfda  lea     rdx, [rbp+var_20]
0x14000bfde  mov     rcx, r15
0x14000bfe1  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x14000bfe6  mov     rcx, [rbp+var_20]; void *
0x14000bfea  lea     rax, [rbp+var_10]
0x14000bfee  cmp     rcx, rax
0x14000bff1  jz      short loc_14000BFFF
0x14000bff3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bffa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000bfff  mov     rcx, rdi; void *
0x14000c002  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c007  xor     eax, eax
0x14000c009  jmp     short loc_14000C04B
0x14000c00b  mov     rcx, [rbp+38h]; this
0x14000c00f  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c016  mov     edx, 532h; void *
0x14000c01b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c020  mov     ebx, eax
0x14000c022  mov     rcx, rdi; void *
0x14000c025  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c02a  jmp     short loc_14000C049
0x14000c02c  mov     rcx, [rbp+38h]; this
0x14000c030  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c037  mov     ebx, 8007000Eh
0x14000c03c  mov     edx, 52Ah; void *
0x14000c041  mov     r9d, ebx; char *
0x14000c044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c049  mov     eax, ebx
0x14000c04b  add     rsp, 50h
0x14000c04f  pop     r15
0x14000c051  pop     r14
0x14000c053  pop     r12
0x14000c055  pop     rdi
0x14000c056  pop     rsi
0x14000c057  pop     rbx
0x14000c058  pop     rbp
0x14000c059  retn
```
