# Container::Manager::Image::_anonymous_namespace_::InitializeUserHive

- ea: `0x140019e40`
- end: `0x14001a316`
- name: `Container::Manager::Image::_anonymous_namespace_::InitializeUserHive`
- size: `1238`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140018184`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140002bb0`
- `0x140006fc4`
- `0x140006fe4`
- `0x14000898c`
- `0x140008f90`
- `0x14000a9b8`
- `0x14000aca8`
- `0x14000cd84`
- `0x140019e40`
- `0x14001adb0`
- `0x140021914`
- `0x140021d08`
- `0x1400228fc`
- `0x1400229c8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a13e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a15b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a21a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a237`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a2a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a13e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a15b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a21a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a237`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a2a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140019efa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140019fc3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140019efa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140019fc3`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::InitializeUserHive(_QWORD *a1, const void **a2)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rbx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // r14
  int v8; // eax
  unsigned int LastError; // ebx
  const struct std::nothrow_t *v10; // rdx
  const char *v11; // r9
  unsigned int v12; // r15d
  unsigned __int64 v13; // rbx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rdi
  int v16; // eax
  const struct std::nothrow_t *v17; // rdx
  const char *v18; // r9
  __int64 v19; // r8
  const void *v20; // rdx
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // rdx
  char v25; // r9
  int v26; // eax
  const struct Path *v27; // rdx
  __int64 v28; // r8
  const unsigned __int16 **i; // rbx
  int v30; // eax
  unsigned int v31; // esi
  __int64 v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  const struct std::nothrow_t *v34; // rdx
  const struct std::nothrow_t *v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  _BYTE v38[8]; // [rsp+20h] [rbp-50h] BYREF
  __int64 v39; // [rsp+28h] [rbp-48h]
  __m128i si128; // [rsp+30h] [rbp-40h] BYREF
  __int64 v41; // [rsp+40h] [rbp-30h]
  void *v42[2]; // [rsp+48h] [rbp-28h] BYREF
  _WORD v43[12]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A0h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+B0h] [rbp+40h] BYREF

  v4 = ((__int64)(a1[1] - *a1) >> 1) + 70;
  v5 = 2 * v4;
  if ( !is_mul_ok(v4, 2u) )
    v5 = -1;
  v6 = (unsigned __int16 *)operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( !v6 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31D,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    return LastError;
  }
  memset_0(v6, 0, v5);
  v8 = StringCchPrintfW(
         v7,
         (unsigned int)v4,
         L"D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)",
         *a1);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x322,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v8);
LABEL_35:
    operator delete(v7, v10);
    return LastError;
  }
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v7, 1u, &SecurityDescriptor, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x329,
                  (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
                  v11);
    goto LABEL_33;
  }
  v12 = ((__int64)(a1[1] - *a1) >> 1) + 77;
  v13 = 2LL * v12;
  if ( !is_mul_ok(v12, 2u) )
    v13 = -1;
  v14 = (unsigned __int16 *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( !v14 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32F,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
LABEL_33:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    goto LABEL_35;
  }
  memset_0(v14, 0, v13);
  v16 = StringCchPrintfW(v15, v12, L"D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)(A;OICIID;KR;;;RC)", *a1);
  LastError = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x334,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v16);
LABEL_32:
    operator delete(v15, v17);
    goto LABEL_33;
  }
  hMem = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v15, 1u, &hMem, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x33B,
                  (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
                  v18);
LABEL_30:
    if ( hMem )
      LocalFree(hMem);
    goto LABEL_32;
  }
  v19 = (_BYTE *)a2[1] - (_BYTE *)*a2;
  v20 = *a2;
  v42[0] = v43;
  v42[1] = v43;
  v43[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v42,
          v20,
          v19 >> 1) )
  {
    v21 = 832;
LABEL_19:
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    goto LABEL_28;
  }
  si128.m128i_i64[1] = 10;
  si128.m128i_i64[0] = (__int64)L"NTUSER.DAT";
  if ( !Csl::Path::Append((Csl::Path *)v42, &si128) )
  {
    v21 = 833;
    goto LABEL_19;
  }
  v38[0] = 0;
  v39 = 0;
  v22 = Csl::OfflineHive::Open((Csl::OfflineHive *)v38, (LPCWSTR *)v42);
  LastError = v22;
  if ( v22 < 0 )
  {
    v24 = 836;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v22);
LABEL_27:
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v38);
LABEL_28:
    if ( v42[0] != v43 )
      operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_30;
  }
  v22 = Csl::OfflineHive::SetKeySecurity((Csl::OfflineHive *)v38, 0, v23, SecurityDescriptor);
  LastError = v22;
  if ( v22 < 0 )
  {
    v24 = 841;
    goto LABEL_22;
  }
  v41 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v26 = Csl::OfflineHive::EnumerateSubkeys((__int64)v38, 0, si128.m128i_i64, v25);
  LastError = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34D,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v26);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
    goto LABEL_27;
  }
  for ( i = (const unsigned __int16 **)si128.m128i_i64[0]; i != (const unsigned __int16 **)si128.m128i_i64[1]; i += 4 )
  {
    v30 = Csl::OfflineHive::SetKeySecurity((Csl::OfflineHive *)v38, *i, v28, hMem);
    v31 = v30;
    if ( v30 < 0 )
    {
      v32 = 851;
LABEL_45:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)(unsigned int)v30);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
      Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v38);
      if ( v42[0] != v43 )
        operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( hMem )
        LocalFree(hMem);
      operator delete(v15, v33);
      if ( SecurityDescriptor )
        LocalFree(SecurityDescriptor);
      operator delete(v7, v34);
      return v31;
    }
  }
  v30 = Csl::DeletePath((LPCWSTR *)v42, v27);
  v31 = v30;
  if ( v30 < 0 )
  {
    v32 = 855;
    goto LABEL_45;
  }
  v30 = Csl::OfflineHive::Save((Csl::OfflineHive *)v38, (LPCWSTR *)v42);
  v31 = v30;
  if ( v30 < 0 )
  {
    v32 = 858;
    goto LABEL_45;
  }
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
  Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v38);
  if ( v42[0] != v43 )
    operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( hMem )
    LocalFree(hMem);
  operator delete(v15, v36);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  operator delete(v7, v37);
  return 0;
}

```

## disassembly

```asm
0x140019e40  mov     [rsp-28h+arg_8], rbx
0x140019e45  mov     [rsp-28h+arg_18], rsi
0x140019e4a  push    rbp
0x140019e4b  push    rdi
0x140019e4c  push    r12
0x140019e4e  push    r14
0x140019e50  push    r15
0x140019e52  mov     rbp, rsp
0x140019e55  sub     rsp, 70h
0x140019e59  mov     rdi, [rcx+8]
0x140019e5d  mov     r12, rdx
0x140019e60  sub     rdi, [rcx]
0x140019e63  mov     rsi, rcx
0x140019e66  sar     rdi, 1
0x140019e69  mov     eax, 2
0x140019e6e  add     rdi, 46h ; 'F'
0x140019e72  mov     edi, edi
0x140019e74  mul     rdi
0x140019e77  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140019e7e  mov     rbx, rax
0x140019e81  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140019e88  cmovb   rbx, rax
0x140019e8c  mov     rcx, rbx; unsigned __int64
0x140019e8f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140019e94  mov     r14, rax
0x140019e97  test    rax, rax
0x140019e9a  jz      loc_14001A2DD
0x140019ea0  mov     r8, rbx; Size
0x140019ea3  xor     edx, edx; Val
0x140019ea5  mov     rcx, rax; void *
0x140019ea8  call    memset_0
0x140019ead  mov     r9, [rsi]
0x140019eb0  lea     r8, aDPaiAOiciKaSAO; "D:PAI(A;OICI;KA;;;%s)(A;OICI;KA;;;SY)(A"...
0x140019eb7  mov     edx, edi; unsigned __int64
0x140019eb9  mov     rcx, r14; unsigned __int16 *
0x140019ebc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140019ec1  mov     ebx, eax
0x140019ec3  test    eax, eax
0x140019ec5  jns     short loc_140019EE4
0x140019ec7  mov     rcx, [rbp+28h]; this
0x140019ecb  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140019ed2  mov     r9d, eax; char *
0x140019ed5  mov     edx, 322h; void *
0x140019eda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019edf  jmp     loc_14001A167
0x140019ee4  xor     r9d, r9d; SecurityDescriptorSize
0x140019ee7  mov     [rbp+SecurityDescriptor], 0
0x140019eef  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140019ef3  mov     rcx, r14; StringSecurityDescriptor
0x140019ef6  lea     edx, [r9+1]; StringSDRevision
0x140019efa  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140019f01  nop     dword ptr [rax+rax+00h]
0x140019f06  test    eax, eax
0x140019f08  jnz     short loc_140019F26
0x140019f0a  mov     rcx, [rbp+28h]; this
0x140019f0e  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140019f15  mov     edx, 329h; void *
0x140019f1a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140019f1f  mov     ebx, eax
0x140019f21  jmp     loc_14001A152
0x140019f26  mov     r15, [rsi+8]
0x140019f2a  mov     eax, 2
0x140019f2f  sub     r15, [rsi]
0x140019f32  sar     r15, 1
0x140019f35  add     r15, 4Dh ; 'M'
0x140019f39  mov     r15d, r15d
0x140019f3c  mul     r15
0x140019f3f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140019f46  mov     rbx, rax
0x140019f49  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140019f50  cmovb   rbx, rax
0x140019f54  mov     rcx, rbx; unsigned __int64
0x140019f57  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140019f5c  mov     rdi, rax
0x140019f5f  test    rax, rax
0x140019f62  jz      loc_14001A2BB
0x140019f68  mov     r8, rbx; Size
0x140019f6b  xor     edx, edx; Val
0x140019f6d  mov     rcx, rax; void *
0x140019f70  call    memset_0
0x140019f75  mov     r9, [rsi]
0x140019f78  lea     r8, aDAiAOiciidKaSA; "D:AI(A;OICIID;KA;;;%s)(A;OICIID;KA;;;SY"...
0x140019f7f  mov     edx, r15d; unsigned __int64
0x140019f82  mov     rcx, rdi; unsigned __int16 *
0x140019f85  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140019f8a  mov     ebx, eax
0x140019f8c  test    eax, eax
0x140019f8e  jns     short loc_140019FAD
0x140019f90  mov     rcx, [rbp+28h]; this
0x140019f94  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140019f9b  mov     r9d, eax; char *
0x140019f9e  mov     edx, 334h; void *
0x140019fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019fa8  jmp     loc_14001A14A
0x140019fad  xor     r9d, r9d; SecurityDescriptorSize
0x140019fb0  mov     [rbp+hMem], 0
0x140019fb8  lea     r8, [rbp+hMem]; SecurityDescriptor
0x140019fbc  mov     rcx, rdi; StringSecurityDescriptor
0x140019fbf  lea     edx, [r9+1]; StringSDRevision
0x140019fc3  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140019fca  nop     dword ptr [rax+rax+00h]
0x140019fcf  test    eax, eax
0x140019fd1  jnz     short loc_140019FEF
0x140019fd3  mov     rcx, [rbp+28h]; this
0x140019fd7  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140019fde  mov     edx, 33Bh; void *
0x140019fe3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140019fe8  mov     ebx, eax
0x140019fea  jmp     loc_14001A135
0x140019fef  mov     r8, [r12+8]
0x140019ff4  lea     rax, [rbp+var_18]
0x140019ff8  sub     r8, [r12]
0x140019ffc  lea     rcx, [rbp+var_28]
0x14001a000  mov     rdx, [r12]
0x14001a004  mov     [rbp+var_28], rax
0x14001a008  lea     rax, [rbp+var_18]
0x14001a00c  mov     [rbp+var_20], rax
0x14001a010  xor     eax, eax
0x14001a012  sar     r8, 1
0x14001a015  mov     [rbp+var_18], ax
0x14001a019  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14001a01e  test    al, al
0x14001a020  jnz     short loc_14001A029
0x14001a022  mov     edx, 340h
0x14001a027  jmp     short loc_14001A052
0x14001a029  lea     rax, aNtuserDat; "NTUSER.DAT"
0x14001a030  mov     qword ptr [rbp+var_40+8], 0Ah
0x14001a038  lea     rdx, [rbp+var_40]
0x14001a03c  mov     qword ptr [rbp+var_40], rax
0x14001a040  lea     rcx, [rbp+var_28]; this
0x14001a044  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001a049  test    al, al
0x14001a04b  jnz     short loc_14001A06F
0x14001a04d  mov     edx, 341h; void *
0x14001a052  mov     rcx, [rbp+28h]; this
0x14001a056  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001a05d  mov     ebx, 8007000Eh
0x14001a062  mov     r9d, ebx; char *
0x14001a065  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a06a  jmp     loc_14001A11C
0x14001a06f  lea     rdx, [rbp+var_28]; struct Path *
0x14001a073  mov     [rbp+var_50], 0
0x14001a077  lea     rcx, [rbp+var_50]; this
0x14001a07b  mov     [rbp+var_48], 0
0x14001a083  call    ?Open@OfflineHive@Csl@@QEAAJAEBVPath@2@@Z; Csl::OfflineHive::Open(Csl::Path const &)
0x14001a088  mov     ebx, eax
0x14001a08a  test    eax, eax
0x14001a08c  jns     short loc_14001A0A8
0x14001a08e  mov     edx, 344h; void *
0x14001a093  mov     rcx, [rbp+28h]; this
0x14001a097  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001a09e  mov     r9d, eax; char *
0x14001a0a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a0a6  jmp     short loc_14001A113
0x14001a0a8  mov     r9, [rbp+SecurityDescriptor]; void *
0x14001a0ac  lea     rcx, [rbp+var_50]; this
0x14001a0b0  xor     edx, edx; unsigned __int16 *
0x14001a0b2  call    ?SetKeySecurity@OfflineHive@Csl@@QEAAJPEBGKPEAX@Z; Csl::OfflineHive::SetKeySecurity(ushort const *,ulong,void *)
0x14001a0b7  mov     ebx, eax
0x14001a0b9  test    eax, eax
0x14001a0bb  jns     short loc_14001A0C4
0x14001a0bd  mov     edx, 349h
0x14001a0c2  jmp     short loc_14001A093
0x14001a0c4  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001a0cc  lea     r8, [rbp+var_40]
0x14001a0d0  xor     edx, edx
0x14001a0d2  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x14001a0da  lea     rcx, [rbp+var_50]
0x14001a0de  movdqu  [rbp+var_40], xmm0
0x14001a0e3  call    ?EnumerateSubkeys@OfflineHive@Csl@@QEBAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@_N@Z; Csl::OfflineHive::EnumerateSubkeys(ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &,bool)
0x14001a0e8  mov     ebx, eax
0x14001a0ea  test    eax, eax
0x14001a0ec  jns     loc_14001A174
0x14001a0f2  mov     rcx, [rbp+28h]; this
0x14001a0f6  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001a0fd  mov     r9d, eax; char *
0x14001a100  mov     edx, 34Dh; void *
0x14001a105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a10a  lea     rcx, [rbp+var_40]
0x14001a10e  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14001a113  lea     rcx, [rbp+var_50]; this
0x14001a117  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x14001a11c  mov     rcx, [rbp+var_28]; void *
0x14001a120  lea     rax, [rbp+var_18]
0x14001a124  cmp     rcx, rax
0x14001a127  jz      short loc_14001A135
0x14001a129  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001a130  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a135  mov     rcx, [rbp+hMem]; hMem
0x14001a139  test    rcx, rcx
0x14001a13c  jz      short loc_14001A14A
0x14001a13e  call    cs:__imp_LocalFree
0x14001a145  nop     dword ptr [rax+rax+00h]
0x14001a14a  mov     rcx, rdi; void *
0x14001a14d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a152  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x14001a156  test    rcx, rcx
0x14001a159  jz      short loc_14001A167
0x14001a15b  call    cs:__imp_LocalFree
0x14001a162  nop     dword ptr [rax+rax+00h]
0x14001a167  mov     rcx, r14; void *
0x14001a16a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a16f  jmp     loc_14001A2FA
0x14001a174  mov     rbx, qword ptr [rbp+var_40]
0x14001a178  cmp     rbx, qword ptr [rbp+var_40+8]
0x14001a17c  jz      short loc_14001A1A1
0x14001a17e  mov     r9, [rbp+hMem]; void *
0x14001a182  lea     rcx, [rbp+var_50]; this
0x14001a186  mov     rdx, [rbx]; unsigned __int16 *
0x14001a189  call    ?SetKeySecurity@OfflineHive@Csl@@QEAAJPEBGKPEAX@Z; Csl::OfflineHive::SetKeySecurity(ushort const *,ulong,void *)
0x14001a18e  mov     esi, eax
0x14001a190  test    eax, eax
0x14001a192  js      short loc_14001A19A
0x14001a194  add     rbx, 20h ; ' '
0x14001a198  jmp     short loc_14001A178
0x14001a19a  mov     edx, 353h
0x14001a19f  jmp     short loc_14001A1D3
0x14001a1a1  lea     rcx, [rbp+var_28]; this
0x14001a1a5  call    ?DeletePath@Csl@@YAJAEBVPath@1@@Z; Csl::DeletePath(Csl::Path const &)
0x14001a1aa  mov     esi, eax
0x14001a1ac  test    eax, eax
0x14001a1ae  jns     short loc_14001A1B7
0x14001a1b0  mov     edx, 357h
0x14001a1b5  jmp     short loc_14001A1D3
0x14001a1b7  lea     rdx, [rbp+var_28]; struct Path *
0x14001a1bb  lea     rcx, [rbp+var_50]; this
0x14001a1bf  call    ?Save@OfflineHive@Csl@@QEBAJAEBVPath@2@@Z; Csl::OfflineHive::Save(Csl::Path const &)
0x14001a1c4  mov     esi, eax
0x14001a1c6  test    eax, eax
0x14001a1c8  jns     loc_14001A252
0x14001a1ce  mov     edx, 35Ah; void *
0x14001a1d3  mov     rcx, [rbp+28h]; this
0x14001a1d7  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001a1de  mov     r9d, eax; char *
0x14001a1e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a1e6  lea     rcx, [rbp+var_40]
0x14001a1ea  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14001a1ef  lea     rcx, [rbp+var_50]; this
0x14001a1f3  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x14001a1f8  mov     rcx, [rbp+var_28]; void *
0x14001a1fc  lea     rax, [rbp+var_18]
0x14001a200  cmp     rcx, rax
0x14001a203  jz      short loc_14001A211
0x14001a205  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001a20c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a211  mov     rcx, [rbp+hMem]; hMem
0x14001a215  test    rcx, rcx
0x14001a218  jz      short loc_14001A226
0x14001a21a  call    cs:__imp_LocalFree
0x14001a221  nop     dword ptr [rax+rax+00h]
0x14001a226  mov     rcx, rdi; void *
0x14001a229  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a22e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x14001a232  test    rcx, rcx
0x14001a235  jz      short loc_14001A243
0x14001a237  call    cs:__imp_LocalFree
0x14001a23e  nop     dword ptr [rax+rax+00h]
0x14001a243  mov     rcx, r14; void *
0x14001a246  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a24b  mov     eax, esi
0x14001a24d  jmp     loc_14001A2FC
0x14001a252  lea     rcx, [rbp+var_40]
0x14001a256  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14001a25b  lea     rcx, [rbp+var_50]; this
0x14001a25f  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x14001a264  mov     rcx, [rbp+var_28]; void *
0x14001a268  lea     rax, [rbp+var_18]
0x14001a26c  cmp     rcx, rax
0x14001a26f  jz      short loc_14001A27D
0x14001a271  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001a278  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a27d  mov     rcx, [rbp+hMem]; hMem
0x14001a281  test    rcx, rcx
0x14001a284  jz      short loc_14001A292
0x14001a286  call    cs:__imp_LocalFree
0x14001a28d  nop     dword ptr [rax+rax+00h]
0x14001a292  mov     rcx, rdi; void *
0x14001a295  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a29a  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x14001a29e  test    rcx, rcx
0x14001a2a1  jz      short loc_14001A2AF
0x14001a2a3  call    cs:__imp_LocalFree
0x14001a2aa  nop     dword ptr [rax+rax+00h]
0x14001a2af  mov     rcx, r14; void *
0x14001a2b2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001a2b7  xor     eax, eax
0x14001a2b9  jmp     short loc_14001A2FC
0x14001a2bb  mov     rcx, [rbp+28h]; this
0x14001a2bf  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001a2c6  mov     ebx, 8007000Eh
0x14001a2cb  mov     edx, 32Fh; void *
0x14001a2d0  mov     r9d, ebx; char *
0x14001a2d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a2d8  jmp     loc_14001A152
0x14001a2dd  mov     rcx, [rbp+28h]; this
0x14001a2e1  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001a2e8  mov     ebx, 8007000Eh
0x14001a2ed  mov     edx, 31Dh; void *
0x14001a2f2  mov     r9d, ebx; char *
0x14001a2f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
