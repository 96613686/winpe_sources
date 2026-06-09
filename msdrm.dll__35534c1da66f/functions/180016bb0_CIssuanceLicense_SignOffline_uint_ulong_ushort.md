# CIssuanceLicense::SignOffline(uint,ulong,ushort * *)

- ea: `0x180016bb0`
- end: `0x180017209`
- name: `?SignOffline@CIssuanceLicense@@QEAAJIKPEAPEAG@Z`
- size: `1625`
- prototype: `__int64 __fastcall(CIssuanceLicense *__hidden this, unsigned int, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180005fc0`
- `0x1800068d0`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004260`
- `0x180004654`
- `0x1800046c8`
- `0x180009f08`
- `0x18000a93c`
- `0x18000ef5c`
- `0x18000fee4`
- `0x180015438`
- `0x1800160a4`
- `0x180016bb0`
- `0x1800172d4`
- `0x180017358`
- `0x18001fe60`
- `0x180037320`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180016c64`
- `msvcrt!wcsstr` at `0x180016c7c`
- `msvcrt!wcsstr` at `0x180016c64`
- `msvcrt!wcsstr` at `0x180016c7c`

## string_xrefs

- `0x18001716d`: `[msdrm]:DRMSign FAILED  : %x `
- `0x180016d8d`: `[msdrm]:GetSignatureXML FAILED : %x `
- `0x180016dc5`: `[msdrm]:pCIssuanceLicense->GetSignatureXML FAILED  : %x `
- `0x180016cbe`: `[msdrm]:+DRMSignWB\n`
- `0x180016d26`: `[msdrm]:-DRMSignWB HR=0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CIssuanceLicense::SignOffline(
        CIssuanceLicense *this,
        int a2,
        unsigned int a3,
        unsigned __int16 **a4)
{
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // r12
  int SPHandle; // ebx
  unsigned int v8; // r15d
  unsigned int v9; // r14d
  const wchar_t *v10; // rbx
  wchar_t *v11; // r13
  unsigned __int8 *v12; // rax
  unsigned int *v13; // rax
  CHandlesTable *v14; // rcx
  CIssuanceLicense *v15; // r14
  int SignatureXML; // eax
  int v17; // eax
  const unsigned __int16 *v18; // rbx
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // r13d
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // r15
  int v24; // r14d
  __int64 v25; // rcx
  __int64 v26; // r11
  int v27; // r11d
  __int64 v28; // rax
  unsigned __int64 v29; // rax
  unsigned __int64 v30; // r14
  unsigned int MaxLengthSignedOfflineIssuanceLicense; // eax
  __int64 v32; // r14
  __int64 v33; // rax
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rdx
  unsigned int v36; // eax
  unsigned int v37; // r15d
  unsigned __int64 v38; // r13
  unsigned __int16 *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rsi
  CIssuanceLicense *v42; // r14
  int v43; // eax
  __int64 v44; // rdx
  int v45; // eax
  unsigned int v47; // [rsp+30h] [rbp-4C8h] BYREF
  void *Block; // [rsp+38h] [rbp-4C0h] BYREF
  unsigned int v49; // [rsp+40h] [rbp-4B8h]
  wchar_t *Str; // [rsp+48h] [rbp-4B0h] BYREF
  unsigned int v51; // [rsp+50h] [rbp-4A8h] BYREF
  unsigned int v52; // [rsp+54h] [rbp-4A4h] BYREF
  int v53; // [rsp+58h] [rbp-4A0h]
  CIssuanceLicense *v54; // [rsp+60h] [rbp-498h]
  unsigned __int16 *v55; // [rsp+68h] [rbp-490h] BYREF
  unsigned __int16 *v56; // [rsp+70h] [rbp-488h] BYREF
  wchar_t *v57; // [rsp+80h] [rbp-478h]
  unsigned __int8 *v58; // [rsp+88h] [rbp-470h]
  unsigned int *v59; // [rsp+90h] [rbp-468h]
  unsigned __int16 **v60; // [rsp+98h] [rbp-460h]
  __int64 v61; // [rsp+A0h] [rbp-458h]
  unsigned __int8 v62[512]; // [rsp+B0h] [rbp-448h] BYREF
  unsigned __int8 v63[512]; // [rsp+2B0h] [rbp-248h] BYREF
  __int64 v64; // [rsp+4B0h] [rbp-48h] BYREF

  v61 = -2;
  v60 = a4;
  v49 = a3;
  v53 = a2;
  v54 = this;
  Str = 0;
  Block = 0;
  v51 = 512;
  v52 = 512;
  v55 = 0;
  v56 = 0;
  v5 = 0;
  v6 = 0;
  CIssuanceLicense::DeleteOwnerLicense(this);
  SPHandle = CIssuanceLicense::CreateSelfIssuedLicenseAndIL(this, &Str, (unsigned __int16 **)&Block);
  if ( SPHandle < 0 )
    goto LABEL_78;
  v8 = 0;
  v9 = -2147024774;
  do
  {
    v10 = (const wchar_t *)Block;
    if ( !v8 )
      v10 = Str;
    v57 = wcsstr(v10, L"<BODY");
    v11 = wcsstr(v10, L"</BODY>");
    v12 = v63;
    if ( !v8 )
      v12 = v62;
    v58 = v12;
    v13 = &v52;
    if ( !v8 )
      v13 = &v51;
    v59 = v13;
    v47 = 0;
    _RTLTRACE("[msdrm]:+DRMSignWB\n");
    SPHandle = CHandlesTable::GetSPHandle(v14, v49, &v47);
    if ( SPHandle >= 0 )
      SPHandle = ((__int64 (__fastcall *)(_QWORD, _QWORD, wchar_t *, unsigned int *, unsigned __int8 *))g_pfnSPSign)(
                   v47,
                   2 * (unsigned int)(((char *)v11 - (char *)v57 + 12) >> 1) + 2,
                   v57,
                   v59,
                   v58);
    _RTLTRACE("[msdrm]:-DRMSignWB HR=0x%x\n", SPHandle);
    if ( SPHandle == -2147024774 )
    {
      SPHandle = -2147024774;
LABEL_76:
      CloseGlobalSignerHandle();
      goto LABEL_77;
    }
    if ( SPHandle == -1073426388 )
    {
      SPHandle = -2147168468;
      v9 = -2147168468;
      goto LABEL_77;
    }
    if ( SPHandle < 0 )
    {
      v9 = SPHandle;
      if ( SPHandle != -2147168468 )
        goto LABEL_76;
LABEL_77:
      _RTLTRACE("[msdrm]:DRMSign FAILED  : %x ", v9);
      goto LABEL_78;
    }
    ++v8;
  }
  while ( v8 < 2 );
  v15 = v54;
  SignatureXML = CIssuanceLicense::GetSignatureXML(v54, Str, v51, v62, &v55);
  SPHandle = SignatureXML;
  if ( SignatureXML < 0 )
  {
    _RTLTRACE("[msdrm]:GetSignatureXML FAILED : %x ", (unsigned int)SignatureXML);
    goto LABEL_78;
  }
  v17 = CIssuanceLicense::GetSignatureXML(v15, (unsigned __int16 *)Block, v52, v63, &v56);
  SPHandle = v17;
  if ( v17 < 0 )
  {
    _RTLTRACE("[msdrm]:pCIssuanceLicense->GetSignatureXML FAILED  : %x ", (unsigned int)v17);
    goto LABEL_78;
  }
  v18 = (const unsigned __int16 *)Block;
  v19 = -1;
  do
    ++v19;
  while ( v56[v19] );
  v20 = -1;
  do
    ++v20;
  while ( *((_WORD *)Block + v20) );
  v21 = v19
      + 8
      + v20
      + ((__int64)(*(_QWORD *)(*((_QWORD *)v15 + 118) + 264LL) - *(_QWORD *)(*((_QWORD *)v15 + 118) + 256LL)) >> 1);
  v22 = (unsigned __int16 *)operator new[](saturated_mul(v21, 2u));
  v23 = v22;
  if ( !v22 )
  {
    v24 = -2147024882;
    goto LABEL_35;
  }
  v24 = StringCchCopyW(v22, v21, v18);
  if ( v24 >= 0 )
  {
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    if ( (unsigned int)v25 < 7 )
    {
      SPHandle = -2147024809;
      v24 = -2147024809;
      goto LABEL_36;
    }
    v24 = StringCchCopyW(&v23[(unsigned int)(v25 - 7)], v21 - ((_DWORD)v25 - 7), v56);
    if ( v24 >= 0 )
    {
      do
        ++v26;
      while ( v23[v26] );
      v24 = StringCchCopyW(&v23[(unsigned int)v26], v21 - (unsigned int)v26, L"</XrML>");
      if ( v24 >= 0 )
      {
        v24 = StringCchCopyNW(
                &v23[v27 + 7],
                v21 - (v27 + 7),
                *(const unsigned __int16 **)(*((_QWORD *)v54 + 118) + 256LL),
                ((__int64)(*(_QWORD *)(*((_QWORD *)v54 + 118) + 264LL) - *(_QWORD *)(*((_QWORD *)v54 + 118) + 256LL)) >> 1)
              + 7);
        if ( v24 >= 0 )
        {
          v23[v21 - 1] = 0;
          v5 = v23;
          v23 = 0;
        }
      }
    }
  }
LABEL_35:
  SPHandle = -2147024809;
LABEL_36:
  operator delete(v23);
  if ( v24 < 0 )
  {
    SPHandle = v24;
    goto LABEL_78;
  }
  operator delete(Block);
  Block = v5;
  v28 = -1;
  do
    ++v28;
  while ( v5[v28] );
  try
  {
    v29 = (unsigned int)v28 + 1LL;
    if ( v29 > 0xFFFFFFFF )
      ((void (__noreturn *)(void))SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow)();
    v30 = 2LL * (unsigned int)v29;
    if ( v30 > 0xFFFFFFFF )
      ((void (__noreturn *)(void))SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow)();
    v5 = 0;
    MaxLengthSignedOfflineIssuanceLicense = GetMaxLengthSignedOfflineIssuanceLicense();
  }
  catch ( SafeIntException v64 )
  {
    v47 = -2147467259;
    v5 = 0;
    SPHandle = -2147467259;
    v6 = 0;
    goto LABEL_78;
  }
  if ( (unsigned int)v30 > MaxLengthSignedOfflineIssuanceLicense )
  {
    SPHandle = -2147168383;
    _RTLTRACE(
      "[msdrm]:signed issuance license size (%d) exceeds limit (%d) : %x ",
      v30,
      MaxLengthSignedOfflineIssuanceLicense,
      -2147168383);
LABEL_45:
    v5 = 0;
    goto LABEL_78;
  }
  v32 = -1;
  do
    ++v32;
  while ( Str[v32] );
  v33 = -1;
  do
    ++v33;
  while ( v55[v33] );
  v34 = (unsigned int)(v32 + v33);
  v49 = v34;
  if ( (unsigned int)v34 < (unsigned int)v32 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v55);
  v35 = v34 + 7;
  if ( v34 + 7 < v34 || v35 > 0xFFFFFFFF )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v55);
  if ( (v53 & 0x20) != 0 )
  {
    v36 = v34 + 7;
  }
  else
  {
    v36 = v35 + *(_DWORD *)(*((_QWORD *)v54 + 118) + 240LL);
    if ( v36 < (unsigned int)v35 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v55);
    if ( (unsigned int)v32 > v36 )
      goto LABEL_78;
  }
  if ( v36 == -1 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v55);
  v37 = v36 + 1;
  v38 = v36 + 1;
  v39 = (unsigned __int16 *)operator new[](saturated_mul(v38, 2u));
  v6 = v39;
  if ( !v39 )
  {
    SPHandle = -2147024882;
    goto LABEL_45;
  }
  SPHandle = StringCchCopyW(v39, v38, Str);
  v5 = 0;
  if ( SPHandle >= 0 )
  {
    if ( (unsigned int)v32 > v37 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v40);
    SPHandle = StringCchPrintfW(&v6[(unsigned int)v32], v37 - (unsigned int)v32, L"%s%s", v55, L"</XrML>");
    v5 = 0;
    if ( SPHandle >= 0 )
    {
      v41 = v49 + 7;
      v42 = v54;
      v43 = CIssuanceLicense::SetOwnerLicense(v54, v6, v49 + 7);
      SPHandle = v43;
      if ( v43 < 0 )
      {
        _RTLTRACE("[msdrm]:pCIssuanceLicense->SetOwnerLicense FAILED  : %x ", (unsigned int)v43);
        goto LABEL_45;
      }
      if ( (v53 & 0x20) == 0 )
      {
        SPHandle = StringCchCopyW(&v6[v41], v38, *(const unsigned __int16 **)(*((_QWORD *)v42 + 118) + 232LL));
        v5 = 0;
        if ( SPHandle < 0 )
          goto LABEL_78;
        v45 = StoreAnyLicenseEx(2, v44, v6);
        SPHandle = v45;
        if ( v45 < 0 )
        {
          _RTLTRACE("[msdrm]:StoreAnyLicense FAILED  : %x ", (unsigned int)v45);
          goto LABEL_45;
        }
      }
      *v60 = (unsigned __int16 *)Block;
      Block = 0;
      goto LABEL_45;
    }
  }
LABEL_78:
  operator delete(v5);
  operator delete(Str);
  Str = 0;
  operator delete(v6);
  operator delete(Block);
  Block = 0;
  operator delete(v55);
  operator delete(v56);
  return (unsigned int)SPHandle;
}

```

## disassembly

```asm
0x180016bb0  push    rbx
0x180016bb2  push    rsi
0x180016bb3  push    rdi
0x180016bb4  push    r12
0x180016bb6  push    r13
0x180016bb8  push    r14
0x180016bba  push    r15
0x180016bbc  sub     rsp, 4C0h
0x180016bc3  mov     [rsp+4F8h+var_458], 0FFFFFFFFFFFFFFFEh
0x180016bcf  mov     rax, cs:__security_cookie
0x180016bd6  xor     rax, rsp
0x180016bd9  mov     [rsp+4F8h+var_40], rax
0x180016be1  mov     [rsp+4F8h+var_460], r9
0x180016be9  mov     [rsp+4F8h+var_4B8], r8d
0x180016bee  mov     [rsp+4F8h+var_4A0], edx
0x180016bf2  mov     rbx, rcx
0x180016bf5  mov     [rsp+4F8h+var_498], rcx
0x180016bfa  xor     edi, edi
0x180016bfc  mov     [rsp+4F8h+Str], rdi
0x180016c01  mov     [rsp+4F8h+Block], rdi
0x180016c06  mov     eax, 200h
0x180016c0b  mov     [rsp+4F8h+var_4A8], eax
0x180016c0f  mov     [rsp+4F8h+var_4A4], eax
0x180016c13  mov     [rsp+4F8h+var_490], rdi
0x180016c18  mov     [rsp+4F8h+var_488], rdi
0x180016c1d  mov     esi, edi
0x180016c1f  mov     r12d, edi
0x180016c22  call    ?DeleteOwnerLicense@CIssuanceLicense@@QEAAXXZ; CIssuanceLicense::DeleteOwnerLicense(void)
0x180016c27  lea     r8, [rsp+4F8h+Block]; unsigned __int16 **
0x180016c2c  lea     rdx, [rsp+4F8h+Str]; unsigned __int16 **
0x180016c31  mov     rcx, rbx; this
0x180016c34  call    ?CreateSelfIssuedLicenseAndIL@CIssuanceLicense@@QEAAJPEAPEAG0@Z; CIssuanceLicense::CreateSelfIssuedLicenseAndIL(ushort * *,ushort * *)
0x180016c39  mov     ebx, eax
0x180016c3b  test    eax, eax
0x180016c3d  js      loc_180017179
0x180016c43  mov     r15d, edi
0x180016c46  mov     r14d, 8007007Ah
0x180016c4c  mov     rbx, [rsp+4F8h+Block]
0x180016c51  test    r15d, r15d
0x180016c54  cmovz   rbx, [rsp+4F8h+Str]
0x180016c5a  lea     rdx, aBody_0; "<BODY"
0x180016c61  mov     rcx, rbx; Str
0x180016c64  call    cs:__imp_wcsstr
0x180016c6a  mov     [rsp+4F8h+var_478], rax
0x180016c72  lea     rdx, aBody; "</BODY>"
0x180016c79  mov     rcx, rbx; Str
0x180016c7c  call    cs:__imp_wcsstr
0x180016c82  mov     r13, rax
0x180016c85  lea     rax, [rsp+4F8h+var_248]
0x180016c8d  lea     rcx, [rsp+4F8h+var_448]
0x180016c95  test    r15d, r15d
0x180016c98  cmovz   rax, rcx
0x180016c9c  mov     [rsp+4F8h+var_470], rax
0x180016ca4  lea     rax, [rsp+4F8h+var_4A4]
0x180016ca9  lea     rcx, [rsp+4F8h+var_4A8]
0x180016cae  cmovz   rax, rcx
0x180016cb2  mov     [rsp+4F8h+var_468], rax
0x180016cba  mov     [rsp+4F8h+var_4C8], edi
0x180016cbe  lea     rcx, aMsdrmDrmsignwb; "[msdrm]:+DRMSignWB\n"
0x180016cc5  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180016cca  lea     r8, [rsp+4F8h+var_4C8]; unsigned int *
0x180016ccf  mov     edx, [rsp+4F8h+var_4B8]; unsigned int
0x180016cd3  call    ?GetSPHandle@CHandlesTable@@QEAAJKPEAK@Z; CHandlesTable::GetSPHandle(ulong,ulong *)
0x180016cd8  mov     ebx, eax
0x180016cda  test    eax, eax
0x180016cdc  js      short loc_180016D24
0x180016cde  sub     r13, [rsp+4F8h+var_478]
0x180016ce6  add     r13, 0Ch
0x180016cea  sar     r13, 1
0x180016ced  lea     edx, ds:2[r13*2]
0x180016cf5  mov     rcx, [rsp+4F8h+var_470]
0x180016cfd  mov     [rsp+4F8h+var_4D8], rcx
0x180016d02  mov     r9, [rsp+4F8h+var_468]
0x180016d0a  mov     r8, [rsp+4F8h+var_478]
0x180016d12  mov     ecx, [rsp+4F8h+var_4C8]
0x180016d16  mov     rax, cs:?g_pfnSPSign@@3P6AJKKPEAEPEAK0@ZEA; long (*g_pfnSPSign)(ulong,ulong,uchar *,ulong *,uchar *)
0x180016d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d22  mov     ebx, eax
0x180016d24  mov     edx, ebx
0x180016d26  lea     rcx, aMsdrmDrmsignwb_0; "[msdrm]:-DRMSignWB HR=0x%x\n"
0x180016d2d  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180016d32  cmp     ebx, r14d
0x180016d35  jz      loc_180017162
0x180016d3b  cmp     ebx, 0C004D02Ch
0x180016d41  jz      loc_180017158
0x180016d47  test    ebx, ebx
0x180016d49  js      loc_18001714B
0x180016d4f  inc     r15d
0x180016d52  cmp     r15d, 2
0x180016d56  jb      loc_180016C4C
0x180016d5c  lea     rax, [rsp+4F8h+var_490]
0x180016d61  mov     [rsp+4F8h+var_4D8], rax; unsigned __int16 **
0x180016d66  lea     r9, [rsp+4F8h+var_448]; unsigned __int8 *
0x180016d6e  mov     r8d, [rsp+4F8h+var_4A8]; unsigned int
0x180016d73  mov     rdx, [rsp+4F8h+Str]; unsigned __int16 *
0x180016d78  mov     r14, [rsp+4F8h+var_498]
0x180016d7d  mov     rcx, r14; this
0x180016d80  call    ?GetSignatureXML@CIssuanceLicense@@QEAAJPEAGIPEAEPEAPEAG@Z; CIssuanceLicense::GetSignatureXML(ushort *,uint,uchar *,ushort * *)
0x180016d85  mov     ebx, eax
0x180016d87  test    eax, eax
0x180016d89  jns     short loc_180016D99
0x180016d8b  mov     edx, eax
0x180016d8d  lea     rcx, aMsdrmGetsignat; "[msdrm]:GetSignatureXML FAILED : %x "
0x180016d94  jmp     loc_180017174
0x180016d99  lea     rax, [rsp+4F8h+var_488]
0x180016d9e  mov     [rsp+4F8h+var_4D8], rax; unsigned __int16 **
0x180016da3  lea     r9, [rsp+4F8h+var_248]; unsigned __int8 *
0x180016dab  mov     r8d, [rsp+4F8h+var_4A4]; unsigned int
0x180016db0  mov     rdx, [rsp+4F8h+Block]; unsigned __int16 *
0x180016db5  mov     rcx, r14; this
0x180016db8  call    ?GetSignatureXML@CIssuanceLicense@@QEAAJPEAGIPEAEPEAPEAG@Z; CIssuanceLicense::GetSignatureXML(ushort *,uint,uchar *,ushort * *)
0x180016dbd  mov     ebx, eax
0x180016dbf  test    eax, eax
0x180016dc1  jns     short loc_180016DD1
0x180016dc3  mov     edx, eax
0x180016dc5  lea     rcx, aMsdrmPcissuanc_0; "[msdrm]:pCIssuanceLicense->GetSignature"...
0x180016dcc  jmp     loc_180017174
0x180016dd1  mov     rbx, [rsp+4F8h+Block]
0x180016dd6  mov     r8, [r14+3B0h]
0x180016ddd  or      r9, 0FFFFFFFFFFFFFFFFh
0x180016de1  mov     rdx, r9
0x180016de4  mov     rax, [rsp+4F8h+var_488]
0x180016de9  inc     rdx
0x180016dec  cmp     [rax+rdx*2], di
0x180016df0  jnz     short loc_180016DE9
0x180016df2  mov     rcx, r9
0x180016df5  inc     rcx
0x180016df8  cmp     [rbx+rcx*2], di
0x180016dfc  jnz     short loc_180016DF5
0x180016dfe  mov     r13, [r8+108h]
0x180016e05  sub     r13, [r8+100h]
0x180016e0c  sar     r13, 1
0x180016e0f  add     r13d, ecx
0x180016e12  add     edx, 8
0x180016e15  add     r13d, edx
0x180016e18  mov     r14d, r13d
0x180016e1b  mov     eax, 2
0x180016e20  mul     r14
0x180016e23  cmovb   rax, r9
0x180016e27  mov     rcx, rax; unsigned __int64
0x180016e2a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180016e2f  mov     r15, rax
0x180016e32  test    rax, rax
0x180016e35  jnz     short loc_180016E42
0x180016e37  mov     r14d, 8007000Eh
0x180016e3d  jmp     loc_180016F11
0x180016e42  mov     r8, rbx; unsigned __int16 *
0x180016e45  mov     rdx, r14; unsigned __int64
0x180016e48  mov     rcx, r15; unsigned __int16 *
0x180016e4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016e50  mov     r14d, eax
0x180016e53  test    eax, eax
0x180016e55  js      loc_180016F11
0x180016e5b  or      r11, 0FFFFFFFFFFFFFFFFh
0x180016e5f  mov     rcx, r11
0x180016e62  inc     rcx
0x180016e65  cmp     [r15+rcx*2], di
0x180016e6a  jnz     short loc_180016E62
0x180016e6c  cmp     ecx, 7
0x180016e6f  jnb     short loc_180016E7E
0x180016e71  mov     ebx, 80070057h
0x180016e76  mov     r14d, ebx
0x180016e79  jmp     loc_180016F16
0x180016e7e  add     ecx, 0FFFFFFF9h
0x180016e81  mov     edx, r13d
0x180016e84  sub     edx, ecx; unsigned __int64
0x180016e86  lea     rcx, [r15+rcx*2]; unsigned __int16 *
0x180016e8a  mov     r8, [rsp+4F8h+var_488]; unsigned __int16 *
0x180016e8f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016e94  mov     r14d, eax
0x180016e97  test    eax, eax
0x180016e99  js      short loc_180016F11
0x180016e9b  inc     r11
0x180016e9e  cmp     [r15+r11*2], di
0x180016ea3  jnz     short loc_180016E9B
0x180016ea5  mov     edx, r13d
0x180016ea8  sub     edx, r11d; unsigned __int64
0x180016eab  mov     eax, r11d
0x180016eae  lea     rcx, [r15+rax*2]; unsigned __int16 *
0x180016eb2  lea     r8, aXrml; "</XrML>"
0x180016eb9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016ebe  mov     r14d, eax
0x180016ec1  test    eax, eax
0x180016ec3  js      short loc_180016F11
0x180016ec5  lea     ecx, [r11+7]
0x180016ec9  mov     rax, [rsp+4F8h+var_498]
0x180016ece  mov     rax, [rax+3B0h]
0x180016ed5  mov     r8, [rax+100h]; unsigned __int16 *
0x180016edc  mov     r9, [rax+108h]
0x180016ee3  sub     r9, r8
0x180016ee6  sar     r9, 1
0x180016ee9  add     r9, 7; unsigned __int64
0x180016eed  mov     edx, r13d
0x180016ef0  sub     edx, ecx; unsigned __int64
0x180016ef2  lea     rcx, [r15+rcx*2]; unsigned __int16 *
0x180016ef6  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180016efb  mov     r14d, eax
0x180016efe  test    eax, eax
0x180016f00  js      short loc_180016F11
0x180016f02  lea     eax, [r13-1]
0x180016f06  mov     [r15+rax*2], di
0x180016f0b  mov     rsi, r15
0x180016f0e  mov     r15, rdi
0x180016f11  mov     ebx, 80070057h
0x180016f16  mov     rcx, r15; Block
0x180016f19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016f1e  test    r14d, r14d
0x180016f21  js      loc_180017146
0x180016f27  mov     rcx, [rsp+4F8h+Block]; Block
0x180016f2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016f31  mov     [rsp+4F8h+Block], rsi
0x180016f36  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016f3a  inc     rax
0x180016f3d  cmp     [rsi+rax*2], di
0x180016f41  jnz     short loc_180016F3A
0x180016f43  mov     eax, eax
0x180016f45  inc     rax
0x180016f48  mov     r15d, 0FFFFFFFFh
0x180016f4e  cmp     rax, r15
0x180016f51  ja      loc_180017202
0x180016f57  mov     r14d, eax
0x180016f5a  add     r14, r14
0x180016f5d  cmp     r14, r15
0x180016f60  ja      loc_1800171E0
0x180016f66  mov     rsi, rdi
0x180016f69  call    ?GetMaxLengthSignedOfflineIssuanceLicense@@YAIXZ; GetMaxLengthSignedOfflineIssuanceLicense(void)
0x180016f6e  cmp     r14d, eax
0x180016f71  jbe     short loc_180016F95
0x180016f73  mov     ebx, 8004CF81h
0x180016f78  mov     r9d, ebx
0x180016f7b  mov     r8d, eax
0x180016f7e  mov     edx, r14d
0x180016f81  lea     rcx, aMsdrmSignedIss; "[msdrm]:signed issuance license size (%"...
0x180016f88  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180016f8d  mov     rsi, rdi
0x180016f90  jmp     loc_180017179
0x180016f95  mov     rax, [rsp+4F8h+Str]
0x180016f9a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180016f9e  mov     r14, r8
0x180016fa1  inc     r14
0x180016fa4  cmp     [rax+r14*2], di
0x180016fa9  jnz     short loc_180016FA1
0x180016fab  mov     rcx, [rsp+4F8h+var_490]
0x180016fb0  mov     rax, r8
0x180016fb3  inc     rax
0x180016fb6  cmp     [rcx+rax*2], di
0x180016fba  jnz     short loc_180016FB3
0x180016fbc  add     eax, r14d
0x180016fbf  mov     [rsp+4F8h+var_4B8], eax
0x180016fc3  cmp     eax, r14d
0x180016fc6  jb      loc_1800171E6
0x180016fcc  lea     rdx, [rax+7]
0x180016fd0  cmp     rdx, rax
0x180016fd3  jb      loc_1800171FC
0x180016fd9  cmp     rdx, r15
0x180016fdc  ja      loc_1800171FC
0x180016fe2  test    byte ptr [rsp+4F8h+var_4A0], 20h
0x180016fe7  jnz     short loc_18001700F
0x180016fe9  mov     rax, [rsp+4F8h+var_498]
0x180016fee  mov     rax, [rax+3B0h]
0x180016ff5  mov     eax, [rax+0F0h]
0x180016ffb  add     eax, edx
0x180016ffd  cmp     eax, edx
0x180016fff  jb      loc_1800171EB
0x180017005  cmp     r14d, eax
0x180017008  jbe     short loc_180017011
0x18001700a  jmp     loc_180017179
0x18001700f  mov     eax, edx
0x180017011  cmp     eax, r15d
0x180017014  jz      loc_1800171F0
0x18001701a  lea     r15d, [rax+1]
0x18001701e  mov     r13d, r15d
0x180017021  mov     eax, 2
0x180017026  mul     r13
0x180017029  cmovb   rax, r8
0x18001702d  mov     rcx, rax; unsigned __int64
0x180017030  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180017035  mov     r12, rax
0x180017038  test    rax, rax
0x18001703b  jnz     short loc_180017047
0x18001703d  mov     ebx, 8007000Eh
0x180017042  jmp     loc_180016F8D
0x180017047  mov     r8, [rsp+4F8h+Str]; unsigned __int16 *
0x18001704c  mov     rdx, r13; unsigned __int64
0x18001704f  mov     rcx, r12; unsigned __int16 *
0x180017052  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017057  mov     ebx, eax
0x180017059  mov     rsi, rdi
0x18001705c  test    eax, eax
0x18001705e  js      loc_180017179
0x180017064  cmp     r14d, r15d
0x180017067  ja      loc_1800171F6
0x18001706d  sub     r15d, r14d
0x180017070  mov     edx, r15d; unsigned __int64
0x180017073  mov     eax, r14d
0x180017076  lea     rcx, [r12+rax*2]; unsigned __int16 *
0x18001707a  lea     rax, aXrml; "</XrML>"
0x180017081  mov     [rsp+4F8h+var_4D8], rax
0x180017086  mov     r9, [rsp+4F8h+var_490]
0x18001708b  lea     r8, aSS_0; "%s%s"
  ... truncated ...
```
