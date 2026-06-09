# Csl::GetWindowsDirectoryPath(Csl::Path &)

- ea: `0x14000c18c`
- end: `0x14000c32b`
- name: `?GetWindowsDirectoryPath@Csl@@YAJAEAVPath@1@@Z`
- size: `415`
- prototype: `__int64 __fastcall(Csl *__hidden this, struct Path *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140018d5c`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140002bb0`
- `0x140006fc4`
- `0x140006fe4`
- `0x14000a7a4`
- `0x14000aa58`
- `0x14000c18c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000c1a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000c216`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000c1a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000c216`

## pseudocode

```c
__int64 __fastcall Csl::GetWindowsDirectoryPath(Csl *this, struct Path *a2)
{
  UINT WindowsDirectoryW; // ebx
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

  WindowsDirectoryW = GetWindowsDirectoryW(0, 0);
  if ( !WindowsDirectoryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x57A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
             v4);
  v6 = -1;
  while ( 1 )
  {
    v7 = 2LL * WindowsDirectoryW;
    if ( !is_mul_ok(WindowsDirectoryW, 2u) )
      v7 = -1;
    v8 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( !v8 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x581,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)0x8007000ELL,
        v16[0]);
      return LastError;
    }
    memset_0(v8, 0, v7);
    v10 = GetWindowsDirectoryW(v9, WindowsDirectoryW);
    if ( !v10 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x589,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
                    v12);
      goto LABEL_19;
    }
    if ( v10 <= WindowsDirectoryW )
      break;
    WindowsDirectoryW = v10;
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
      (void *)0x595,
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
0x14000c18c  push    rbp
0x14000c18e  push    rbx
0x14000c18f  push    rsi
0x14000c190  push    rdi
0x14000c191  push    r12
0x14000c193  push    r14
0x14000c195  push    r15
0x14000c197  mov     rbp, rsp
0x14000c19a  sub     rsp, 50h
0x14000c19e  mov     r15, rcx
0x14000c1a1  xor     edx, edx; uSize
0x14000c1a3  xor     ecx, ecx; lpBuffer
0x14000c1a5  call    cs:__imp_GetWindowsDirectoryW
0x14000c1ac  nop     dword ptr [rax+rax+00h]
0x14000c1b1  xor     r12d, r12d
0x14000c1b4  mov     ebx, eax
0x14000c1b6  test    eax, eax
0x14000c1b8  jnz     short loc_14000C1D4
0x14000c1ba  mov     rcx, [rbp+38h]; this
0x14000c1be  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c1c5  mov     edx, 57Ah; void *
0x14000c1ca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c1cf  jmp     loc_14000C31B
0x14000c1d4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000c1d8  mov     ecx, ebx
0x14000c1da  mov     eax, 2
0x14000c1df  mul     rcx
0x14000c1e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c1e9  mov     r14, rax
0x14000c1ec  cmovb   r14, rsi
0x14000c1f0  mov     rcx, r14; unsigned __int64
0x14000c1f3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000c1f8  mov     rdi, rax
0x14000c1fb  test    rax, rax
0x14000c1fe  jz      loc_14000C2FC
0x14000c204  mov     r8, r14; Size
0x14000c207  xor     edx, edx; Val
0x14000c209  mov     rcx, rax; void *
0x14000c20c  call    memset_0
0x14000c211  mov     edx, ebx; uSize
0x14000c213  mov     rcx, rdi; lpBuffer
0x14000c216  call    cs:__imp_GetWindowsDirectoryW
0x14000c21d  nop     dword ptr [rax+rax+00h]
0x14000c222  test    eax, eax
0x14000c224  jz      loc_14000C2DB
0x14000c22a  cmp     eax, ebx
0x14000c22c  jbe     short loc_14000C23A
0x14000c22e  mov     rcx, rdi; void *
0x14000c231  mov     ebx, eax
0x14000c233  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c238  jmp     short loc_14000C1D8
0x14000c23a  lea     rax, [rbp+var_10]
0x14000c23e  mov     [rbp+var_10], r12w
0x14000c243  mov     [rbp+var_20], rax
0x14000c247  lea     rax, [rbp+var_10]
0x14000c24b  mov     [rbp+var_18], rax
0x14000c24f  mov     [rbp+var_30], rdi
0x14000c253  inc     rsi
0x14000c256  cmp     [rdi+rsi*2], r12w
0x14000c25b  jnz     short loc_14000C253
0x14000c25d  lea     rdx, [rbp+var_30]
0x14000c261  mov     [rbp+var_28], rsi
0x14000c265  lea     rcx, [rbp+var_20]; this
0x14000c269  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14000c26e  test    al, al
0x14000c270  jnz     short loc_14000C2AA
0x14000c272  mov     rcx, [rbp+38h]; this
0x14000c276  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c27d  mov     ebx, 8007000Eh
0x14000c282  mov     edx, 595h; void *
0x14000c287  mov     r9d, ebx; char *
0x14000c28a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c28f  mov     rcx, [rbp+var_20]; void *
0x14000c293  lea     rax, [rbp+var_10]
0x14000c297  cmp     rcx, rax
0x14000c29a  jz      short loc_14000C2F2
0x14000c29c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c2a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c2a8  jmp     short loc_14000C2F2
0x14000c2aa  lea     rdx, [rbp+var_20]
0x14000c2ae  mov     rcx, r15
0x14000c2b1  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x14000c2b6  mov     rcx, [rbp+var_20]; void *
0x14000c2ba  lea     rax, [rbp+var_10]
0x14000c2be  cmp     rcx, rax
0x14000c2c1  jz      short loc_14000C2CF
0x14000c2c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c2ca  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c2cf  mov     rcx, rdi; void *
0x14000c2d2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c2d7  xor     eax, eax
0x14000c2d9  jmp     short loc_14000C31B
0x14000c2db  mov     rcx, [rbp+38h]; this
0x14000c2df  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c2e6  mov     edx, 589h; void *
0x14000c2eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c2f0  mov     ebx, eax
0x14000c2f2  mov     rcx, rdi; void *
0x14000c2f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c2fa  jmp     short loc_14000C319
0x14000c2fc  mov     rcx, [rbp+38h]; this
0x14000c300  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c307  mov     ebx, 8007000Eh
0x14000c30c  mov     edx, 581h; void *
0x14000c311  mov     r9d, ebx; char *
0x14000c314  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c319  mov     eax, ebx
0x14000c31b  add     rsp, 50h
0x14000c31f  pop     r15
0x14000c321  pop     r14
0x14000c323  pop     r12
0x14000c325  pop     rdi
0x14000c326  pop     rsi
0x14000c327  pop     rbx
0x14000c328  pop     rbp
0x14000c329  retn
```
