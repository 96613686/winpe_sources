# DoSignature(std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180019200`
- end: `0x1800195ad`
- name: `?DoSignature@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV12@@Z`
- size: `941`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800184bc`

## callees

- `0x1800059a8`
- `0x18000ff24`
- `0x180015e68`
- `0x1800166a4`
- `0x1800172c0`
- `0x180018dc0`
- `0x180019200`
- `0x18001ee90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019316`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019316`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192f7`
- `bcrypt!BCryptHash` at `0x18001942b`
- `bcrypt!BCryptHash` at `0x18001942b`
- `bcrypt!BCryptGetProperty` at `0x1800193e6`
- `bcrypt!BCryptGetProperty` at `0x1800193e6`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800193aa`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180019563`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800193aa`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180019563`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180019371`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180019371`
- `ncrypt!NCryptSignHash` at `0x18001948d`
- `ncrypt!NCryptSignHash` at `0x180019532`
- `ncrypt!NCryptSignHash` at `0x18001948d`
- `ncrypt!NCryptSignHash` at `0x180019532`
- `ncrypt!NCryptFreeObject` at `0x180019268`
- `ncrypt!NCryptFreeObject` at `0x1800192dd`
- `ncrypt!NCryptFreeObject` at `0x180019308`
- `ncrypt!NCryptFreeObject` at `0x180019579`
- `ncrypt!NCryptFreeObject` at `0x18001958f`
- `ncrypt!NCryptFreeObject` at `0x180019268`
- `ncrypt!NCryptFreeObject` at `0x1800192dd`
- `ncrypt!NCryptFreeObject` at `0x180019308`
- `ncrypt!NCryptFreeObject` at `0x180019579`
- `ncrypt!NCryptFreeObject` at `0x18001958f`
- `ncrypt!NCryptOpenStorageProvider` at `0x180019234`
- `ncrypt!NCryptOpenStorageProvider` at `0x180019234`
- `ncrypt!NCryptOpenKey` at `0x180019299`
- `ncrypt!NCryptOpenKey` at `0x180019340`
- `ncrypt!NCryptOpenKey` at `0x180019299`
- `ncrypt!NCryptOpenKey` at `0x180019340`

## string_xrefs

- `0x18001924d`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x1800192c0`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180019386`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180019442`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x1800194a4`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DoSignature(__int64 *a1, __int64 a2)
{
  __int64 v3; // r14
  int v4; // r15d
  SECURITY_STATUS v5; // eax
  SECURITY_STATUS SignatureKey; // ebx
  const unsigned __int16 *v8; // rcx
  __int64 v9; // rdx
  NCRYPT_KEY_HANDLE v10; // rsi
  DWORD LastError; // ebx
  NTSTATUS Property; // eax
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rdx
  PBYTE v16; // rdx
  __int64 v17; // rsi
  unsigned __int64 v18; // rcx
  BYTE *v19; // rax
  size_t v20; // rbx
  int dwFlags; // [rsp+20h] [rbp-50h]
  int dwFlagsa; // [rsp+20h] [rbp-50h]
  int dwFlagsb; // [rsp+20h] [rbp-50h]
  NCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-30h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-20h] BYREF
  PBYTE pbHashValue[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  DWORD pbOutput; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cbSignature; // [rsp+C0h] [rbp+50h] BYREF
  ULONG pcbResult; // [rsp+C8h] [rbp+58h] BYREF

  v3 = *a1;
  v4 = *((_DWORD *)a1 + 2) - *a1;
  phProvider = 0;
  v5 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  SignatureKey = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FA,
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
      v9 = 1023;
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
      v9 = 1024;
      goto LABEL_9;
    }
  }
  phAlgorithm = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( Property < 0 )
  {
    v13 = 1029;
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
    v13 = 1032;
    goto LABEL_18;
  }
  std::vector<unsigned char>::vector<unsigned char>(pbHashValue, pbOutput);
  v14 = BCryptHash(phAlgorithm, 0, 0, v3);
  if ( v14 < 0 )
  {
    SignatureKey = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x40A,
                     (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                     (const char *)(unsigned int)v14,
                     v4);
LABEL_25:
    std::vector<unsigned char>::~vector<unsigned char>(pbHashValue);
LABEL_19:
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    goto LABEL_10;
  }
  cbSignature = 0;
  SignatureKey = NCryptSignHash(phKey, 0, pbHashValue[0], pbOutput, 0, 0, &cbSignature, 0);
  if ( SignatureKey < 0 )
  {
    v15 = 1038;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)SignatureKey,
      dwFlagsb);
    goto LABEL_25;
  }
  v16 = *(PBYTE *)a2;
  v17 = *(_QWORD *)(a2 + 8);
  v18 = v17 - *(_QWORD *)a2;
  if ( cbSignature >= v18 )
  {
    if ( cbSignature <= v18 )
      goto LABEL_36;
    if ( (unsigned __int64)cbSignature > *(_QWORD *)(a2 + 16) - (_QWORD)v16 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a2, cbSignature);
      goto LABEL_36;
    }
    v20 = cbSignature - v18;
    memset_0(*(void **)(a2 + 8), 0, v20);
    v19 = (BYTE *)(v20 + v17);
  }
  else
  {
    v19 = &v16[cbSignature];
  }
  *(_QWORD *)(a2 + 8) = v19;
LABEL_36:
  SignatureKey = NCryptSignHash(phKey, 0, pbHashValue[0], pbOutput, *(PBYTE *)a2, cbSignature, &cbSignature, 0);
  if ( SignatureKey < 0 )
  {
    v15 = 1041;
    goto LABEL_28;
  }
  std::vector<unsigned char>::~vector<unsigned char>(pbHashValue);
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
0x180019200  push    rbp
0x180019202  push    rbx
0x180019203  push    rsi
0x180019204  push    rdi
0x180019205  push    r12
0x180019207  push    r14
0x180019209  push    r15
0x18001920b  mov     rbp, rsp
0x18001920e  sub     rsp, 70h
0x180019212  mov     rdi, rdx
0x180019215  mov     r14, [rcx]
0x180019218  mov     r15d, [rcx+8]
0x18001921c  sub     r15d, r14d
0x18001921f  xor     r12d, r12d
0x180019222  mov     [rbp+phProvider], r12
0x180019226  xor     r8d, r8d; dwFlags
0x180019229  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x180019230  lea     rcx, [rbp+phProvider]; phProvider
0x180019234  call    cs:__imp_NCryptOpenStorageProvider
0x18001923b  nop     dword ptr [rax+rax+00h]
0x180019240  mov     ebx, eax
0x180019242  test    eax, eax
0x180019244  jns     short loc_18001927B
0x180019246  mov     rcx, [rbp+38h]; this
0x18001924a  mov     r9d, eax; char *
0x18001924d  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180019254  mov     edx, 3FAh; void *
0x180019259  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001925e  nop
0x18001925f  mov     rcx, [rbp+phProvider]; hObject
0x180019263  test    rcx, rcx
0x180019266  jz      short loc_180019274
0x180019268  call    cs:__imp_NCryptFreeObject
0x18001926f  nop     dword ptr [rax+rax+00h]
0x180019274  mov     eax, ebx
0x180019276  jmp     loc_18001959D
0x18001927b  mov     [rbp+phKey], r12
0x18001927f  mov     [rsp+70h+dwFlags], 20h ; ' '; int
0x180019287  xor     r9d, r9d; dwLegacyKeySpec
0x18001928a  lea     r8, pszKeyName; "SparseGenerationAppxsvcKey"
0x180019291  lea     rdx, [rbp+phKey]; phKey
0x180019295  mov     rcx, [rbp+phProvider]; hProvider
0x180019299  call    cs:__imp_NCryptOpenKey
0x1800192a0  nop     dword ptr [rax+rax+00h]
0x1800192a5  cmp     eax, 80090016h
0x1800192aa  jnz     loc_18001935C
0x1800192b0  call    ?CreateSignatureKey@@YAJPEBG@Z; CreateSignatureKey(ushort const *)
0x1800192b5  mov     ebx, eax
0x1800192b7  test    eax, eax
0x1800192b9  jns     short loc_1800192EE
0x1800192bb  mov     edx, 3FFh; void *
0x1800192c0  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800192c7  mov     r9d, ebx; char *
0x1800192ca  mov     rcx, [rbp+38h]; this
0x1800192ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800192d3  nop
0x1800192d4  mov     rcx, [rbp+phKey]; hObject
0x1800192d8  test    rcx, rcx
0x1800192db  jz      short loc_18001925F
0x1800192dd  call    cs:__imp_NCryptFreeObject
0x1800192e4  nop     dword ptr [rax+rax+00h]
0x1800192e9  jmp     loc_18001925F
0x1800192ee  mov     rsi, [rbp+phKey]
0x1800192f2  test    rsi, rsi
0x1800192f5  jz      short loc_180019322
0x1800192f7  call    cs:__imp_GetLastError
0x1800192fe  nop     dword ptr [rax+rax+00h]
0x180019303  mov     ebx, eax
0x180019305  mov     rcx, rsi; hObject
0x180019308  call    cs:__imp_NCryptFreeObject
0x18001930f  nop     dword ptr [rax+rax+00h]
0x180019314  mov     ecx, ebx; dwErrCode
0x180019316  call    cs:__imp_SetLastError
0x18001931d  nop     dword ptr [rax+rax+00h]
0x180019322  mov     [rbp+phKey], r12
0x180019326  mov     [rsp+70h+dwFlags], 20h ; ' '; dwFlags
0x18001932e  xor     r9d, r9d; dwLegacyKeySpec
0x180019331  lea     r8, pszKeyName; "SparseGenerationAppxsvcKey"
0x180019338  lea     rdx, [rbp+phKey]; phKey
0x18001933c  mov     rcx, [rbp+phProvider]; hProvider
0x180019340  call    cs:__imp_NCryptOpenKey
0x180019347  nop     dword ptr [rax+rax+00h]
0x18001934c  mov     ebx, eax
0x18001934e  test    eax, eax
0x180019350  jns     short loc_18001935C
0x180019352  mov     edx, 400h
0x180019357  jmp     loc_1800192C0
0x18001935c  mov     [rbp+phAlgorithm], r12
0x180019360  xor     r9d, r9d; dwFlags
0x180019363  xor     r8d, r8d; pszImplementation
0x180019366  lea     rdx, aSha256; "SHA256"
0x18001936d  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180019371  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180019378  nop     dword ptr [rax+rax+00h]
0x18001937d  test    eax, eax
0x18001937f  jns     short loc_1800193BB
0x180019381  mov     edx, 405h; void *
0x180019386  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001938d  mov     r9d, eax; char *
0x180019390  mov     rcx, [rbp+38h]; this
0x180019394  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180019399  mov     ebx, eax
0x18001939b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001939f  test    rcx, rcx
0x1800193a2  jz      loc_1800192D4
0x1800193a8  xor     edx, edx; dwFlags
0x1800193aa  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800193b1  nop     dword ptr [rax+rax+00h]
0x1800193b6  jmp     loc_1800192D4
0x1800193bb  mov     [rbp+pbOutput], r12d
0x1800193bf  mov     [rbp+pcbResult], r12d
0x1800193c3  mov     [rsp+70h+cbSignature], r12d; dwFlags
0x1800193c8  lea     rax, [rbp+pcbResult]
0x1800193cc  mov     qword ptr [rsp+70h+dwFlags], rax; pcbResult
0x1800193d1  mov     r9d, 4; cbOutput
0x1800193d7  lea     r8, [rbp+pbOutput]; pbOutput
0x1800193db  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800193e2  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800193e6  call    cs:__imp_BCryptGetProperty
0x1800193ed  nop     dword ptr [rax+rax+00h]
0x1800193f2  test    eax, eax
0x1800193f4  jns     short loc_1800193FD
0x1800193f6  mov     edx, 408h
0x1800193fb  jmp     short loc_180019386
0x1800193fd  mov     edx, [rbp+pbOutput]
0x180019400  lea     rcx, [rbp+pbHashValue]
0x180019404  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180019409  nop
0x18001940a  mov     eax, [rbp+pbOutput]
0x18001940d  mov     rdx, [rbp+pbHashValue]
0x180019411  mov     dword ptr [rsp+70h+var_40], eax
0x180019415  mov     qword ptr [rsp+70h+cbSignature], rdx
0x18001941a  mov     [rsp+70h+dwFlags], r15d; int
0x18001941f  mov     r9, r14
0x180019422  xor     r8d, r8d
0x180019425  xor     edx, edx
0x180019427  mov     rcx, [rbp+phAlgorithm]
0x18001942b  call    cs:__imp_BCryptHash
0x180019432  nop     dword ptr [rax+rax+00h]
0x180019437  test    eax, eax
0x180019439  jns     short loc_180019463
0x18001943b  mov     rcx, [rbp+38h]; this
0x18001943f  mov     r9d, eax; char *
0x180019442  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180019449  mov     edx, 40Ah; void *
0x18001944e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180019453  mov     ebx, eax
0x180019455  lea     rcx, [rbp+pbHashValue]
0x180019459  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001945e  jmp     loc_18001939B
0x180019463  mov     [rbp+arg_10], r12d
0x180019467  mov     [rsp+70h+var_38], r12d; dwFlags
0x18001946c  lea     rax, [rbp+arg_10]
0x180019470  mov     [rsp+70h+var_40], rax; pcbResult
0x180019475  mov     [rsp+70h+cbSignature], r12d; cbSignature
0x18001947a  mov     qword ptr [rsp+70h+dwFlags], r12; int
0x18001947f  mov     r9d, [rbp+pbOutput]; cbHashValue
0x180019483  mov     r8, [rbp+pbHashValue]; pbHashValue
0x180019487  xor     edx, edx; pPaddingInfo
0x180019489  mov     rcx, [rbp+phKey]; hKey
0x18001948d  call    cs:__imp_NCryptSignHash
0x180019494  nop     dword ptr [rax+rax+00h]
0x180019499  mov     ebx, eax
0x18001949b  test    eax, eax
0x18001949d  jns     short loc_1800194B9
0x18001949f  mov     edx, 40Eh; void *
0x1800194a4  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800194ab  mov     r9d, ebx; char *
0x1800194ae  mov     rcx, [rbp+38h]; this
0x1800194b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194b7  jmp     short loc_180019455
0x1800194b9  mov     ebx, [rbp+arg_10]
0x1800194bc  mov     rdx, [rdi]
0x1800194bf  mov     rsi, [rdi+8]
0x1800194c3  mov     rcx, rsi
0x1800194c6  sub     rcx, rdx
0x1800194c9  cmp     rbx, rcx
0x1800194cc  jnb     short loc_1800194D4
0x1800194ce  lea     rax, [rdx+rbx]
0x1800194d2  jmp     short loc_180019503
0x1800194d4  jbe     short loc_180019507
0x1800194d6  mov     rax, [rdi+10h]
0x1800194da  sub     rax, rdx
0x1800194dd  cmp     rbx, rax
0x1800194e0  jbe     short loc_1800194EF
0x1800194e2  mov     rdx, rbx
0x1800194e5  mov     rcx, rdi
0x1800194e8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800194ed  jmp     short loc_180019507
0x1800194ef  sub     rbx, rcx
0x1800194f2  mov     r8, rbx; Size
0x1800194f5  xor     edx, edx; Val
0x1800194f7  mov     rcx, rsi; void *
0x1800194fa  call    memset_0
0x1800194ff  lea     rax, [rbx+rsi]
0x180019503  mov     [rdi+8], rax
0x180019507  mov     eax, [rbp+arg_10]
0x18001950a  mov     [rsp+70h+var_38], r12d; dwFlags
0x18001950f  lea     rcx, [rbp+arg_10]
0x180019513  mov     [rsp+70h+var_40], rcx; pcbResult
0x180019518  mov     [rsp+70h+cbSignature], eax; cbSignature
0x18001951c  mov     rax, [rdi]
0x18001951f  mov     qword ptr [rsp+70h+dwFlags], rax; pbSignature
0x180019524  mov     r9d, [rbp+pbOutput]; cbHashValue
0x180019528  mov     r8, [rbp+pbHashValue]; pbHashValue
0x18001952c  xor     edx, edx; pPaddingInfo
0x18001952e  mov     rcx, [rbp+phKey]; hKey
0x180019532  call    cs:__imp_NCryptSignHash
0x180019539  nop     dword ptr [rax+rax+00h]
0x18001953e  mov     ebx, eax
0x180019540  test    eax, eax
0x180019542  jns     short loc_18001954E
0x180019544  mov     edx, 411h
0x180019549  jmp     loc_1800194A4
0x18001954e  lea     rcx, [rbp+pbHashValue]
0x180019552  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180019557  nop
0x180019558  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001955c  test    rcx, rcx
0x18001955f  jz      short loc_180019570
0x180019561  xor     edx, edx; dwFlags
0x180019563  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001956a  nop     dword ptr [rax+rax+00h]
0x18001956f  nop
0x180019570  mov     rcx, [rbp+phKey]; hObject
0x180019574  test    rcx, rcx
0x180019577  jz      short loc_180019586
0x180019579  call    cs:__imp_NCryptFreeObject
0x180019580  nop     dword ptr [rax+rax+00h]
0x180019585  nop
0x180019586  mov     rcx, [rbp+phProvider]; hObject
0x18001958a  test    rcx, rcx
0x18001958d  jz      short loc_18001959B
0x18001958f  call    cs:__imp_NCryptFreeObject
0x180019596  nop     dword ptr [rax+rax+00h]
0x18001959b  xor     eax, eax
0x18001959d  add     rsp, 70h
0x1800195a1  pop     r15
0x1800195a3  pop     r14
0x1800195a5  pop     r12
0x1800195a7  pop     rdi
0x1800195a8  pop     rsi
0x1800195a9  pop     rbx
0x1800195aa  pop     rbp
0x1800195ab  retn
```
