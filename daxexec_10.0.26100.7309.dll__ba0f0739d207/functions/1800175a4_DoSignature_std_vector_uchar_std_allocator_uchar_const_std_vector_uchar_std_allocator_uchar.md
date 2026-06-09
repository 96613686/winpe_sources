# DoSignature(std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800175a4`
- end: `0x1800179da`
- name: `?DoSignature@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV12@@Z`
- size: `1078`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180016774`

## callees

- `0x180005794`
- `0x180006158`
- `0x18000e234`
- `0x18001411c`
- `0x180014a7c`
- `0x180017180`
- `0x1800175a4`
- `0x18001e304`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180017967`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180017967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001769b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001769b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800176ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800176ba`
- `bcrypt!BCryptHash` at `0x1800177cf`
- `bcrypt!BCryptHash` at `0x1800177cf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001774e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017990`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001774e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017990`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180017715`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180017715`
- `bcrypt!BCryptGetProperty` at `0x18001778a`
- `bcrypt!BCryptGetProperty` at `0x18001778a`
- `ncrypt!NCryptSignHash` at `0x180017872`
- `ncrypt!NCryptSignHash` at `0x18001791a`
- `ncrypt!NCryptSignHash` at `0x180017872`
- `ncrypt!NCryptSignHash` at `0x18001791a`
- `ncrypt!NCryptFreeObject` at `0x18001760c`
- `ncrypt!NCryptFreeObject` at `0x180017681`
- `ncrypt!NCryptFreeObject` at `0x1800176ac`
- `ncrypt!NCryptFreeObject` at `0x1800179a6`
- `ncrypt!NCryptFreeObject` at `0x1800179bc`
- `ncrypt!NCryptFreeObject` at `0x18001760c`
- `ncrypt!NCryptFreeObject` at `0x180017681`
- `ncrypt!NCryptFreeObject` at `0x1800176ac`
- `ncrypt!NCryptFreeObject` at `0x1800179a6`
- `ncrypt!NCryptFreeObject` at `0x1800179bc`
- `ncrypt!NCryptOpenKey` at `0x18001763d`
- `ncrypt!NCryptOpenKey` at `0x1800176e4`
- `ncrypt!NCryptOpenKey` at `0x18001763d`
- `ncrypt!NCryptOpenKey` at `0x1800176e4`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800175d8`
- `ncrypt!NCryptOpenStorageProvider` at `0x1800175d8`

## string_xrefs

- `0x1800175f1`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180017664`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001772a`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x1800177e6`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180017889`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DoSignature(__int64 *a1, __int64 a2)
{
  __int64 v3; // r15
  __int64 v4; // r14
  SECURITY_STATUS v5; // eax
  SECURITY_STATUS SignatureKey; // ebx
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rdx
  NCRYPT_KEY_HANDLE v10; // rsi
  DWORD LastError; // ebx
  NTSTATUS Property; // eax
  __int64 v13; // rdx
  int v14; // eax
  PBYTE v15; // rcx
  unsigned __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rsi
  PBYTE v19; // rdx
  unsigned __int64 v20; // rcx
  BYTE *v21; // rax
  size_t v22; // rbx
  int dwFlags; // [rsp+20h] [rbp-50h]
  int dwFlagsa; // [rsp+20h] [rbp-50h]
  int dwFlagsb; // [rsp+20h] [rbp-50h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-30h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-20h] BYREF
  PBYTE pbHashValue[2]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v30; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  DWORD pbOutput; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cbSignature; // [rsp+C0h] [rbp+50h] BYREF
  ULONG pcbResult; // [rsp+C8h] [rbp+58h] BYREF

  v3 = *a1;
  v4 = a1[1] - *a1;
  phProvider = 0;
  v5 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  SignatureKey = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F8,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v5,
      dwFlags);
LABEL_3:
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return (unsigned int)SignatureKey;
  }
  phKey = 0;
  if ( NCryptOpenKey(phProvider, &phKey, L"SparseGenerationAppxsvcKey", 0, 0x20u) == -2146893802 )
  {
    SignatureKey = CreateSignatureKey(v8);
    if ( SignatureKey < 0 )
    {
      v9 = 1021;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)(unsigned int)SignatureKey,
        dwFlagsa);
LABEL_10:
      if ( phKey )
        NCryptFreeObject(phKey);
      goto LABEL_3;
    }
    v10 = phKey;
    if ( phKey )
    {
      LastError = GetLastError();
      NCryptFreeObject(v10);
      SetLastError(LastError);
    }
    phKey = 0;
    SignatureKey = NCryptOpenKey(phProvider, &phKey, L"SparseGenerationAppxsvcKey", 0, 0x20u);
    if ( SignatureKey < 0 )
    {
      v9 = 1022;
      goto LABEL_9;
    }
  }
  phAlgorithm = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( Property < 0 )
  {
    v13 = 1027;
LABEL_18:
    SignatureKey = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)v13,
                     (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                     (const char *)(unsigned int)Property,
                     dwFlagsa);
    goto LABEL_19;
  }
  pbOutput = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v13 = 1030;
    goto LABEL_18;
  }
  std::vector<unsigned char>::vector<unsigned char>(pbHashValue, pbOutput);
  v14 = BCryptHash(phAlgorithm, 0, 0, v3);
  if ( v14 < 0 )
  {
    SignatureKey = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x408,
                     (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                     (const char *)(unsigned int)v14,
                     v4);
LABEL_25:
    v15 = pbHashValue[0];
    if ( !pbHashValue[0] )
      goto LABEL_19;
    v16 = v30 - (unsigned __int64)pbHashValue[0];
    if ( v30 - (unsigned __int64)pbHashValue[0] < 0x1000
      || (v16 += 39LL, v15 = (PBYTE)*((_QWORD *)pbHashValue[0] - 1),
                       (unsigned __int64)(pbHashValue[0] - v15 - 8) <= 0x1F) )
    {
      operator delete(v15, v16);
      *(_OWORD *)pbHashValue = 0;
      v30 = 0;
LABEL_19:
      if ( phAlgorithm )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      goto LABEL_10;
    }
LABEL_44:
    _o__invalid_parameter_noinfo_noreturn(v15, v16);
    __debugbreak();
LABEL_45:
    operator delete(v15, v16);
    *(_OWORD *)pbHashValue = 0;
    v30 = 0;
    goto LABEL_46;
  }
  cbSignature = 0;
  SignatureKey = NCryptSignHash(phKey, 0, pbHashValue[0], pbOutput, 0, 0, &cbSignature, 0);
  if ( SignatureKey < 0 )
  {
    v17 = 1036;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)SignatureKey,
      dwFlagsb);
    goto LABEL_25;
  }
  v18 = *(_QWORD *)(a2 + 8);
  v19 = *(PBYTE *)a2;
  v20 = v18 - *(_QWORD *)a2;
  if ( cbSignature >= v20 )
  {
    if ( cbSignature <= v20 )
      goto LABEL_39;
    if ( (unsigned __int64)cbSignature > *(_QWORD *)(a2 + 16) - (_QWORD)v19 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a2, cbSignature);
      goto LABEL_39;
    }
    v22 = cbSignature - v20;
    memset_0(*(void **)(a2 + 8), 0, v22);
    v21 = (BYTE *)(v18 + v22);
  }
  else
  {
    v21 = &v19[cbSignature];
  }
  *(_QWORD *)(a2 + 8) = v21;
LABEL_39:
  SignatureKey = NCryptSignHash(phKey, 0, pbHashValue[0], pbOutput, *(PBYTE *)a2, cbSignature, &cbSignature, 0);
  if ( SignatureKey < 0 )
  {
    v17 = 1039;
    goto LABEL_31;
  }
  v15 = pbHashValue[0];
  if ( pbHashValue[0] )
  {
    v16 = v30 - (unsigned __int64)pbHashValue[0];
    if ( v30 - (unsigned __int64)pbHashValue[0] < 0x1000 )
      goto LABEL_45;
    v16 += 39LL;
    v15 = (PBYTE)*((_QWORD *)pbHashValue[0] - 1);
    if ( (unsigned __int64)(pbHashValue[0] - v15 - 8) <= 0x1F )
      goto LABEL_45;
    goto LABEL_44;
  }
LABEL_46:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return 0;
}

```

## disassembly

```asm
0x1800175a4  push    rbp
0x1800175a6  push    rbx
0x1800175a7  push    rsi
0x1800175a8  push    rdi
0x1800175a9  push    r12
0x1800175ab  push    r14
0x1800175ad  push    r15
0x1800175af  mov     rbp, rsp
0x1800175b2  sub     rsp, 70h
0x1800175b6  mov     rdi, rdx
0x1800175b9  mov     r15, [rcx]
0x1800175bc  mov     r14, [rcx+8]
0x1800175c0  sub     r14, r15
0x1800175c3  xor     r12d, r12d
0x1800175c6  mov     [rbp+phProvider], r12
0x1800175ca  xor     r8d, r8d; dwFlags
0x1800175cd  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x1800175d4  lea     rcx, [rbp+phProvider]; phProvider
0x1800175d8  call    cs:__imp_NCryptOpenStorageProvider
0x1800175df  nop     dword ptr [rax+rax+00h]
0x1800175e4  mov     ebx, eax
0x1800175e6  test    eax, eax
0x1800175e8  jns     short loc_18001761F
0x1800175ea  mov     rcx, [rbp+38h]; this
0x1800175ee  mov     r9d, eax; char *
0x1800175f1  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800175f8  mov     edx, 3F8h; void *
0x1800175fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017602  nop
0x180017603  mov     rcx, [rbp+phProvider]; hObject
0x180017607  test    rcx, rcx
0x18001760a  jz      short loc_180017618
0x18001760c  call    cs:__imp_NCryptFreeObject
0x180017613  nop     dword ptr [rax+rax+00h]
0x180017618  mov     eax, ebx
0x18001761a  jmp     loc_1800179CA
0x18001761f  mov     [rbp+phKey], r12
0x180017623  mov     [rsp+70h+dwFlags], 20h ; ' '; int
0x18001762b  xor     r9d, r9d; dwLegacyKeySpec
0x18001762e  lea     r8, pszKeyName; "SparseGenerationAppxsvcKey"
0x180017635  lea     rdx, [rbp+phKey]; phKey
0x180017639  mov     rcx, [rbp+phProvider]; hProvider
0x18001763d  call    cs:__imp_NCryptOpenKey
0x180017644  nop     dword ptr [rax+rax+00h]
0x180017649  cmp     eax, 80090016h
0x18001764e  jnz     loc_180017700
0x180017654  call    ?CreateSignatureKey@@YAJPEBG@Z; CreateSignatureKey(ushort const *)
0x180017659  mov     ebx, eax
0x18001765b  test    eax, eax
0x18001765d  jns     short loc_180017692
0x18001765f  mov     edx, 3FDh; void *
0x180017664  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001766b  mov     r9d, ebx; char *
0x18001766e  mov     rcx, [rbp+38h]; this
0x180017672  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017677  nop
0x180017678  mov     rcx, [rbp+phKey]; hObject
0x18001767c  test    rcx, rcx
0x18001767f  jz      short loc_180017603
0x180017681  call    cs:__imp_NCryptFreeObject
0x180017688  nop     dword ptr [rax+rax+00h]
0x18001768d  jmp     loc_180017603
0x180017692  mov     rsi, [rbp+phKey]
0x180017696  test    rsi, rsi
0x180017699  jz      short loc_1800176C6
0x18001769b  call    cs:__imp_GetLastError
0x1800176a2  nop     dword ptr [rax+rax+00h]
0x1800176a7  mov     ebx, eax
0x1800176a9  mov     rcx, rsi; hObject
0x1800176ac  call    cs:__imp_NCryptFreeObject
0x1800176b3  nop     dword ptr [rax+rax+00h]
0x1800176b8  mov     ecx, ebx; dwErrCode
0x1800176ba  call    cs:__imp_SetLastError
0x1800176c1  nop     dword ptr [rax+rax+00h]
0x1800176c6  mov     [rbp+phKey], r12
0x1800176ca  mov     [rsp+70h+dwFlags], 20h ; ' '; dwFlags
0x1800176d2  xor     r9d, r9d; dwLegacyKeySpec
0x1800176d5  lea     r8, pszKeyName; "SparseGenerationAppxsvcKey"
0x1800176dc  lea     rdx, [rbp+phKey]; phKey
0x1800176e0  mov     rcx, [rbp+phProvider]; hProvider
0x1800176e4  call    cs:__imp_NCryptOpenKey
0x1800176eb  nop     dword ptr [rax+rax+00h]
0x1800176f0  mov     ebx, eax
0x1800176f2  test    eax, eax
0x1800176f4  jns     short loc_180017700
0x1800176f6  mov     edx, 3FEh
0x1800176fb  jmp     loc_180017664
0x180017700  mov     [rbp+phAlgorithm], r12
0x180017704  xor     r9d, r9d; dwFlags
0x180017707  xor     r8d, r8d; pszImplementation
0x18001770a  lea     rdx, aSha256; "SHA256"
0x180017711  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180017715  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001771c  nop     dword ptr [rax+rax+00h]
0x180017721  test    eax, eax
0x180017723  jns     short loc_18001775F
0x180017725  mov     edx, 403h; void *
0x18001772a  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180017731  mov     r9d, eax; char *
0x180017734  mov     rcx, [rbp+38h]; this
0x180017738  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001773d  mov     ebx, eax
0x18001773f  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180017743  test    rcx, rcx
0x180017746  jz      loc_180017678
0x18001774c  xor     edx, edx; dwFlags
0x18001774e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180017755  nop     dword ptr [rax+rax+00h]
0x18001775a  jmp     loc_180017678
0x18001775f  mov     [rbp+pbOutput], r12d
0x180017763  mov     [rbp+pcbResult], r12d
0x180017767  mov     [rsp+70h+cbSignature], r12d; dwFlags
0x18001776c  lea     rax, [rbp+pcbResult]
0x180017770  mov     qword ptr [rsp+70h+dwFlags], rax; pcbResult
0x180017775  mov     r9d, 4; cbOutput
0x18001777b  lea     r8, [rbp+pbOutput]; pbOutput
0x18001777f  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180017786  mov     rcx, [rbp+phAlgorithm]; hObject
0x18001778a  call    cs:__imp_BCryptGetProperty
0x180017791  nop     dword ptr [rax+rax+00h]
0x180017796  test    eax, eax
0x180017798  jns     short loc_1800177A1
0x18001779a  mov     edx, 406h
0x18001779f  jmp     short loc_18001772A
0x1800177a1  mov     edx, [rbp+pbOutput]
0x1800177a4  lea     rcx, [rbp+pbHashValue]
0x1800177a8  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1800177ad  nop
0x1800177ae  mov     eax, [rbp+pbOutput]
0x1800177b1  mov     dword ptr [rsp+70h+var_40], eax
0x1800177b5  mov     rax, [rbp+pbHashValue]
0x1800177b9  mov     qword ptr [rsp+70h+cbSignature], rax
0x1800177be  mov     [rsp+70h+dwFlags], r14d; int
0x1800177c3  mov     r9, r15
0x1800177c6  xor     r8d, r8d
0x1800177c9  xor     edx, edx
0x1800177cb  mov     rcx, [rbp+phAlgorithm]
0x1800177cf  call    cs:__imp_BCryptHash
0x1800177d6  nop     dword ptr [rax+rax+00h]
0x1800177db  test    eax, eax
0x1800177dd  jns     short loc_180017848
0x1800177df  mov     rcx, [rbp+38h]; this
0x1800177e3  mov     r9d, eax; char *
0x1800177e6  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800177ed  mov     edx, 408h; void *
0x1800177f2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800177f7  mov     ebx, eax
0x1800177f9  mov     rcx, [rbp+pbHashValue]
0x1800177fd  test    rcx, rcx
0x180017800  jz      loc_18001773F
0x180017806  mov     rdx, [rbp+var_8]
0x18001780a  sub     rdx, rcx
0x18001780d  cmp     rdx, 1000h
0x180017814  mov     rax, rcx
0x180017817  jb      short loc_180017832
0x180017819  add     rdx, 27h ; '''; unsigned __int64
0x18001781d  mov     rcx, [rcx-8]; void *
0x180017821  sub     rax, rcx
0x180017824  add     rax, 0FFFFFFFFFFFFFFF8h
0x180017828  cmp     rax, 1Fh
0x18001782c  ja      loc_180017967
0x180017832  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017837  xorps   xmm0, xmm0
0x18001783a  movdqu  xmmword ptr [rbp+pbHashValue], xmm0
0x18001783f  mov     [rbp+var_8], r12
0x180017843  jmp     loc_18001773F
0x180017848  mov     [rbp+arg_10], r12d
0x18001784c  mov     [rsp+70h+var_38], r12d; dwFlags
0x180017851  lea     rax, [rbp+arg_10]
0x180017855  mov     [rsp+70h+var_40], rax; pcbResult
0x18001785a  mov     [rsp+70h+cbSignature], r12d; cbSignature
0x18001785f  mov     qword ptr [rsp+70h+dwFlags], r12; int
0x180017864  mov     r9d, [rbp+pbOutput]; cbHashValue
0x180017868  mov     r8, [rbp+pbHashValue]; pbHashValue
0x18001786c  xor     edx, edx; pPaddingInfo
0x18001786e  mov     rcx, [rbp+phKey]; hKey
0x180017872  call    cs:__imp_NCryptSignHash
0x180017879  nop     dword ptr [rax+rax+00h]
0x18001787e  mov     ebx, eax
0x180017880  test    eax, eax
0x180017882  jns     short loc_1800178A1
0x180017884  mov     edx, 40Ch; void *
0x180017889  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x180017890  mov     r9d, ebx; char *
0x180017893  mov     rcx, [rbp+38h]; this
0x180017897  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001789c  jmp     loc_1800177F9
0x1800178a1  mov     ebx, [rbp+arg_10]
0x1800178a4  mov     rsi, [rdi+8]
0x1800178a8  mov     rdx, [rdi]
0x1800178ab  mov     rcx, rsi
0x1800178ae  sub     rcx, rdx
0x1800178b1  cmp     rbx, rcx
0x1800178b4  jnb     short loc_1800178BC
0x1800178b6  lea     rax, [rbx+rdx]
0x1800178ba  jmp     short loc_1800178EB
0x1800178bc  jbe     short loc_1800178EF
0x1800178be  mov     rax, [rdi+10h]
0x1800178c2  sub     rax, rdx
0x1800178c5  cmp     rbx, rax
0x1800178c8  jbe     short loc_1800178D7
0x1800178ca  mov     rdx, rbx
0x1800178cd  mov     rcx, rdi
0x1800178d0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800178d5  jmp     short loc_1800178EF
0x1800178d7  sub     rbx, rcx
0x1800178da  mov     r8, rbx; Size
0x1800178dd  xor     edx, edx; Val
0x1800178df  mov     rcx, rsi; void *
0x1800178e2  call    memset_0
0x1800178e7  lea     rax, [rsi+rbx]
0x1800178eb  mov     [rdi+8], rax
0x1800178ef  mov     rcx, [rdi]
0x1800178f2  mov     [rsp+70h+var_38], r12d; dwFlags
0x1800178f7  lea     rax, [rbp+arg_10]
0x1800178fb  mov     [rsp+70h+var_40], rax; pcbResult
0x180017900  mov     eax, [rbp+arg_10]
0x180017903  mov     [rsp+70h+cbSignature], eax; cbSignature
0x180017907  mov     qword ptr [rsp+70h+dwFlags], rcx; pbSignature
0x18001790c  mov     r9d, [rbp+pbOutput]; cbHashValue
0x180017910  mov     r8, [rbp+pbHashValue]; pbHashValue
0x180017914  xor     edx, edx; pPaddingInfo
0x180017916  mov     rcx, [rbp+phKey]; hKey
0x18001791a  call    cs:__imp_NCryptSignHash
0x180017921  nop     dword ptr [rax+rax+00h]
0x180017926  mov     ebx, eax
0x180017928  test    eax, eax
0x18001792a  jns     short loc_180017936
0x18001792c  mov     edx, 40Fh
0x180017931  jmp     loc_180017889
0x180017936  mov     rcx, [rbp+pbHashValue]
0x18001793a  test    rcx, rcx
0x18001793d  jz      short loc_180017985
0x18001793f  mov     rdx, [rbp+var_8]
0x180017943  sub     rdx, rcx
0x180017946  mov     rax, rcx
0x180017949  cmp     rdx, 1000h
0x180017950  jb      short loc_180017974
0x180017952  add     rdx, 27h ; '''
0x180017956  mov     rcx, [rcx-8]
0x18001795a  sub     rax, rcx
0x18001795d  add     rax, 0FFFFFFFFFFFFFFF8h
0x180017961  cmp     rax, 1Fh
0x180017965  jbe     short loc_180017974
0x180017967  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x18001796e  nop     dword ptr [rax+rax+00h]
0x180017973  int     3; Trap to Debugger
0x180017974  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017979  xorps   xmm0, xmm0
0x18001797c  movdqu  xmmword ptr [rbp+pbHashValue], xmm0
0x180017981  mov     [rbp+var_8], r12
0x180017985  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180017989  test    rcx, rcx
0x18001798c  jz      short loc_18001799D
0x18001798e  xor     edx, edx; dwFlags
0x180017990  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180017997  nop     dword ptr [rax+rax+00h]
0x18001799c  nop
0x18001799d  mov     rcx, [rbp+phKey]; hObject
0x1800179a1  test    rcx, rcx
0x1800179a4  jz      short loc_1800179B3
0x1800179a6  call    cs:__imp_NCryptFreeObject
0x1800179ad  nop     dword ptr [rax+rax+00h]
0x1800179b2  nop
0x1800179b3  mov     rcx, [rbp+phProvider]; hObject
0x1800179b7  test    rcx, rcx
0x1800179ba  jz      short loc_1800179C8
0x1800179bc  call    cs:__imp_NCryptFreeObject
0x1800179c3  nop     dword ptr [rax+rax+00h]
0x1800179c8  xor     eax, eax
0x1800179ca  add     rsp, 70h
0x1800179ce  pop     r15
0x1800179d0  pop     r14
0x1800179d2  pop     r12
0x1800179d4  pop     rdi
0x1800179d5  pop     rsi
0x1800179d6  pop     rbx
0x1800179d7  pop     rbp
0x1800179d8  retn
```
