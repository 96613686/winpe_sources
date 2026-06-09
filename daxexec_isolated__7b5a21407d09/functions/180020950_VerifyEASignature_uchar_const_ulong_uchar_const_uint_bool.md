# VerifyEASignature(uchar const *,ulong,uchar const *,uint,bool &)

- ea: `0x180020950`
- end: `0x180020c44`
- name: `?VerifyEASignature@@YAJPEBEK0IAEA_N@Z`
- size: `756`
- prototype: `__int64 __fastcall(const unsigned __int8 *, int, BYTE *, DWORD, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001980c`

## callees

- `0x180005340`
- `0x1800059a8`
- `0x18000aef0`
- `0x18000ff24`
- `0x180020950`

## import_xrefs

- `bcrypt!BCryptHash` at `0x180020a93`
- `bcrypt!BCryptHash` at `0x180020a93`
- `bcrypt!BCryptGetProperty` at `0x180020a33`
- `bcrypt!BCryptGetProperty` at `0x180020a33`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180020ad0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180020bbf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180020c11`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180020ad0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180020bbf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180020c11`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800209cc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800209cc`
- `ncrypt!NCryptVerifySignature` at `0x180020b80`
- `ncrypt!NCryptVerifySignature` at `0x180020b80`
- `ncrypt!NCryptFreeObject` at `0x180020ae5`
- `ncrypt!NCryptFreeObject` at `0x180020b51`
- `ncrypt!NCryptFreeObject` at `0x180020ba0`
- `ncrypt!NCryptFreeObject` at `0x180020bd4`
- `ncrypt!NCryptFreeObject` at `0x180020c26`
- `ncrypt!NCryptFreeObject` at `0x180020ae5`
- `ncrypt!NCryptFreeObject` at `0x180020b51`
- `ncrypt!NCryptFreeObject` at `0x180020ba0`
- `ncrypt!NCryptFreeObject` at `0x180020bd4`
- `ncrypt!NCryptFreeObject` at `0x180020c26`
- `ncrypt!NCryptOpenStorageProvider` at `0x180020984`
- `ncrypt!NCryptOpenStorageProvider` at `0x180020984`
- `ncrypt!NCryptOpenKey` at `0x180020b1a`
- `ncrypt!NCryptOpenKey` at `0x180020b1a`

## string_xrefs

- `0x18002099a`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x1800209e7`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180020aa9`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180020b30`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180020be8`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
__int64 __fastcall VerifyEASignature(const unsigned __int8 *a1, int a2, BYTE *a3, DWORD a4, bool *a5)
{
  SECURITY_STATUS v9; // eax
  NTSTATUS Property; // ebx
  __int64 v11; // rdx
  BCRYPT_ALG_HANDLE v12; // rcx
  unsigned int v13; // edi
  void *v14; // rax
  void *v15; // rbx
  int v16; // eax
  unsigned int v17; // edi
  unsigned __int64 v18; // rdx
  SECURITY_STATUS v20; // eax
  unsigned __int64 v21; // rdx
  int pcbResult; // [rsp+20h] [rbp-40h]
  int pcbResulta; // [rsp+20h] [rbp-40h]
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-20h] BYREF
  ULONG v25; // [rsp+44h] [rbp-1Ch] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp-10h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  phProvider = 0;
  v9 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  Property = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A8,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v9,
      pcbResult);
LABEL_29:
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return (unsigned int)Property;
  }
  phAlgorithm = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( Property < 0 )
  {
    v11 = 1196;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)Property,
      pcbResult);
    v12 = phAlgorithm;
    goto LABEL_27;
  }
  *(_DWORD *)pbOutput = 0;
  v25 = 0;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &v25, 0);
  if ( Property < 0 )
  {
    v11 = 1199;
    goto LABEL_5;
  }
  v13 = *(_DWORD *)pbOutput;
  v14 = operator new[](*(unsigned int *)pbOutput, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( !v14 )
  {
    Property = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B2,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)0x8007000ELL,
      pcbResult);
    v12 = phAlgorithm;
    if ( !phAlgorithm )
      goto LABEL_29;
LABEL_27:
    if ( v12 )
      BCryptCloseAlgorithmProvider(v12, 0);
    goto LABEL_29;
  }
  memset_0(v14, 0, v13);
  v16 = BCryptHash(phAlgorithm, 0, 0, a1);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B4,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v16,
      a2);
LABEL_11:
    operator delete(v15, v18);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return v17;
  }
  phKey = 0;
  v20 = NCryptOpenKey(phProvider, &phKey, L"SparseGenerationAppxsvcKey", 0, 0x20u);
  v17 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B7,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v20,
      pcbResulta);
    if ( phKey )
      NCryptFreeObject(phKey);
    goto LABEL_11;
  }
  *a5 = NCryptVerifySignature(phKey, 0, (PBYTE)v15, *(DWORD *)pbOutput, a3, a4, 0) == 0;
  if ( phKey )
    NCryptFreeObject(phKey);
  operator delete(v15, v21);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return 0;
}

```

## disassembly

```asm
0x180020950  push    rbp
0x180020952  push    rbx
0x180020953  push    rsi
0x180020954  push    rdi
0x180020955  push    r12
0x180020957  push    r14
0x180020959  push    r15
0x18002095b  mov     rbp, rsp
0x18002095e  sub     rsp, 60h
0x180020962  mov     r14, r8
0x180020965  mov     [rbp+phProvider], 0
0x18002096d  mov     r15d, edx
0x180020970  mov     r12, rcx
0x180020973  xor     r8d, r8d; dwFlags
0x180020976  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x18002097d  lea     rcx, [rbp+phProvider]; phProvider
0x180020981  mov     esi, r9d
0x180020984  call    cs:__imp_NCryptOpenStorageProvider
0x18002098b  nop     dword ptr [rax+rax+00h]
0x180020990  mov     ebx, eax
0x180020992  test    eax, eax
0x180020994  jns     short loc_1800209B3
0x180020996  mov     rcx, [rbp+38h]; this
0x18002099a  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800209a1  mov     r9d, eax; char *
0x1800209a4  mov     edx, 4A8h; void *
0x1800209a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800209ae  jmp     loc_180020C1D
0x1800209b3  xor     r9d, r9d; dwFlags
0x1800209b6  mov     [rbp+phAlgorithm], 0
0x1800209be  xor     r8d, r8d; pszImplementation
0x1800209c1  lea     rdx, aSha256; "SHA256"
0x1800209c8  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800209cc  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800209d3  nop     dword ptr [rax+rax+00h]
0x1800209d8  mov     ebx, eax
0x1800209da  test    eax, eax
0x1800209dc  jns     short loc_1800209FF
0x1800209de  mov     edx, 4ACh; void *
0x1800209e3  mov     rcx, [rbp+38h]; this
0x1800209e7  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800209ee  mov     r9d, ebx; char *
0x1800209f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800209f6  mov     rcx, [rbp+phAlgorithm]
0x1800209fa  jmp     loc_180020C0A
0x1800209ff  mov     rcx, [rbp+phAlgorithm]; hObject
0x180020a03  lea     rax, [rbp+var_1C]
0x180020a07  mov     [rsp+60h+dwFlags], 0; dwFlags
0x180020a0f  lea     r8, [rbp+pbOutput]; pbOutput
0x180020a13  mov     r9d, 4; cbOutput
0x180020a19  mov     [rsp+60h+pcbResult], rax; int
0x180020a1e  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180020a25  mov     dword ptr [rbp+pbOutput], 0
0x180020a2c  mov     [rbp+var_1C], 0
0x180020a33  call    cs:__imp_BCryptGetProperty
0x180020a3a  nop     dword ptr [rax+rax+00h]
0x180020a3f  mov     ebx, eax
0x180020a41  test    eax, eax
0x180020a43  jns     short loc_180020A4C
0x180020a45  mov     edx, 4AFh
0x180020a4a  jmp     short loc_1800209E3
0x180020a4c  mov     edi, dword ptr [rbp+pbOutput]
0x180020a4f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020a56  mov     ecx, edi; unsigned __int64
0x180020a58  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180020a5d  mov     rbx, rax
0x180020a60  test    rax, rax
0x180020a63  jz      loc_180020BE4
0x180020a69  mov     r8d, edi; Size
0x180020a6c  xor     edx, edx; Val
0x180020a6e  mov     rcx, rax; void *
0x180020a71  call    memset_0
0x180020a76  mov     edx, dword ptr [rbp+pbOutput]
0x180020a79  mov     r9, r12
0x180020a7c  mov     rcx, [rbp+phAlgorithm]
0x180020a80  xor     r8d, r8d
0x180020a83  mov     [rsp+60h+var_30], edx
0x180020a87  xor     edx, edx
0x180020a89  mov     qword ptr [rsp+60h+dwFlags], rbx
0x180020a8e  mov     dword ptr [rsp+60h+pcbResult], r15d; int
0x180020a93  call    cs:__imp_BCryptHash
0x180020a9a  nop     dword ptr [rax+rax+00h]
0x180020a9f  mov     edi, eax
0x180020aa1  test    eax, eax
0x180020aa3  jns     short loc_180020AF8
0x180020aa5  mov     rcx, [rbp+38h]; this
0x180020aa9  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180020ab0  mov     r9d, eax; char *
0x180020ab3  mov     edx, 4B4h; void *
0x180020ab8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020abd  mov     rcx, rbx; void *
0x180020ac0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020ac5  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180020ac9  test    rcx, rcx
0x180020acc  jz      short loc_180020ADC
0x180020ace  xor     edx, edx; dwFlags
0x180020ad0  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180020ad7  nop     dword ptr [rax+rax+00h]
0x180020adc  mov     rcx, [rbp+phProvider]; hObject
0x180020ae0  test    rcx, rcx
0x180020ae3  jz      short loc_180020AF1
0x180020ae5  call    cs:__imp_NCryptFreeObject
0x180020aec  nop     dword ptr [rax+rax+00h]
0x180020af1  mov     eax, edi
0x180020af3  jmp     loc_180020C34
0x180020af8  mov     rcx, [rbp+phProvider]; hProvider
0x180020afc  lea     r8, pszKeyName; "SparseGenerationAppxsvcKey"
0x180020b03  xor     r9d, r9d; dwLegacyKeySpec
0x180020b06  mov     [rbp+phKey], 0
0x180020b0e  lea     rdx, [rbp+phKey]; phKey
0x180020b12  mov     dword ptr [rsp+60h+pcbResult], 20h ; ' '; int
0x180020b1a  call    cs:__imp_NCryptOpenKey
0x180020b21  nop     dword ptr [rax+rax+00h]
0x180020b26  mov     edi, eax
0x180020b28  test    eax, eax
0x180020b2a  jns     short loc_180020B62
0x180020b2c  mov     rcx, [rbp+38h]; this
0x180020b30  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180020b37  mov     r9d, eax; char *
0x180020b3a  mov     edx, 4B7h; void *
0x180020b3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b44  mov     rcx, [rbp+phKey]; hObject
0x180020b48  test    rcx, rcx
0x180020b4b  jz      loc_180020ABD
0x180020b51  call    cs:__imp_NCryptFreeObject
0x180020b58  nop     dword ptr [rax+rax+00h]
0x180020b5d  jmp     loc_180020ABD
0x180020b62  mov     r9d, dword ptr [rbp+pbOutput]; cbHashValue
0x180020b66  mov     r8, rbx; pbHashValue
0x180020b69  mov     rcx, [rbp+phKey]; hKey
0x180020b6d  xor     edx, edx; pPaddingInfo
0x180020b6f  mov     [rsp+60h+var_30], 0; dwFlags
0x180020b77  mov     [rsp+60h+dwFlags], esi; cbSignature
0x180020b7b  mov     [rsp+60h+pcbResult], r14; pbSignature
0x180020b80  call    cs:__imp_NCryptVerifySignature
0x180020b87  nop     dword ptr [rax+rax+00h]
0x180020b8c  test    eax, eax
0x180020b8e  mov     rax, [rbp+arg_20]
0x180020b92  setz    cl
0x180020b95  mov     [rax], cl
0x180020b97  mov     rcx, [rbp+phKey]; hObject
0x180020b9b  test    rcx, rcx
0x180020b9e  jz      short loc_180020BAC
0x180020ba0  call    cs:__imp_NCryptFreeObject
0x180020ba7  nop     dword ptr [rax+rax+00h]
0x180020bac  mov     rcx, rbx; void *
0x180020baf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020bb4  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180020bb8  test    rcx, rcx
0x180020bbb  jz      short loc_180020BCB
0x180020bbd  xor     edx, edx; dwFlags
0x180020bbf  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180020bc6  nop     dword ptr [rax+rax+00h]
0x180020bcb  mov     rcx, [rbp+phProvider]; hObject
0x180020bcf  test    rcx, rcx
0x180020bd2  jz      short loc_180020BE0
0x180020bd4  call    cs:__imp_NCryptFreeObject
0x180020bdb  nop     dword ptr [rax+rax+00h]
0x180020be0  xor     eax, eax
0x180020be2  jmp     short loc_180020C34
0x180020be4  mov     rcx, [rbp+38h]; this
0x180020be8  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\execmodel\\des"...
0x180020bef  mov     ebx, 8007000Eh
0x180020bf4  mov     edx, 4B2h; void *
0x180020bf9  mov     r9d, ebx; char *
0x180020bfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020c01  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180020c05  test    rcx, rcx
0x180020c08  jz      short loc_180020C1D
0x180020c0a  test    rcx, rcx
0x180020c0d  jz      short loc_180020C1D
0x180020c0f  xor     edx, edx; dwFlags
0x180020c11  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180020c18  nop     dword ptr [rax+rax+00h]
0x180020c1d  mov     rcx, [rbp+phProvider]; hObject
0x180020c21  test    rcx, rcx
0x180020c24  jz      short loc_180020C32
0x180020c26  call    cs:__imp_NCryptFreeObject
0x180020c2d  nop     dword ptr [rax+rax+00h]
0x180020c32  mov     eax, ebx
0x180020c34  add     rsp, 60h
0x180020c38  pop     r15
0x180020c3a  pop     r14
0x180020c3c  pop     r12
0x180020c3e  pop     rdi
0x180020c3f  pop     rsi
0x180020c40  pop     rbx
0x180020c41  pop     rbp
0x180020c42  retn
```
