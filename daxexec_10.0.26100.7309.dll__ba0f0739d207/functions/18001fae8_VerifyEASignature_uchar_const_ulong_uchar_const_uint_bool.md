# VerifyEASignature(uchar const *,ulong,uchar const *,uint,bool &)

- ea: `0x18001fae8`
- end: `0x18001fdca`
- name: `?VerifyEASignature@@YAJPEBEK0IAEA_N@Z`
- size: `738`
- prototype: `int(const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180017c44`

## callees

- `0x180005794`
- `0x180006158`
- `0x1800093a0`
- `0x18000e234`
- `0x18001fae8`

## import_xrefs

- `bcrypt!BCryptHash` at `0x18001fc15`
- `bcrypt!BCryptHash` at `0x18001fc15`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001fc52`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001fd3b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001fd88`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001fc52`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001fd3b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001fd88`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001fb6b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001fb6b`
- `bcrypt!BCryptGetProperty` at `0x18001fbb2`
- `bcrypt!BCryptGetProperty` at `0x18001fbb2`
- `ncrypt!NCryptVerifySignature` at `0x18001fcfc`
- `ncrypt!NCryptVerifySignature` at `0x18001fcfc`
- `ncrypt!NCryptFreeObject` at `0x18001fc67`
- `ncrypt!NCryptFreeObject` at `0x18001fcd0`
- `ncrypt!NCryptFreeObject` at `0x18001fd1c`
- `ncrypt!NCryptFreeObject` at `0x18001fd50`
- `ncrypt!NCryptFreeObject` at `0x18001fd9d`
- `ncrypt!NCryptFreeObject` at `0x18001fc67`
- `ncrypt!NCryptFreeObject` at `0x18001fcd0`
- `ncrypt!NCryptFreeObject` at `0x18001fd1c`
- `ncrypt!NCryptFreeObject` at `0x18001fd50`
- `ncrypt!NCryptFreeObject` at `0x18001fd9d`
- `ncrypt!NCryptOpenKey` at `0x18001fc99`
- `ncrypt!NCryptOpenKey` at `0x18001fc99`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001fb26`
- `ncrypt!NCryptOpenStorageProvider` at `0x18001fb26`

## string_xrefs

- `0x18001fb3c`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001fc2b`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001fcaf`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18001fd6e`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
__int64 __fastcall VerifyEASignature(const unsigned __int8 *a1, int a2, BYTE *a3, DWORD a4, bool *a5)
{
  SECURITY_STATUS v9; // eax
  NTSTATUS Property; // ebx
  __int64 v11; // rdx
  unsigned int v12; // edi
  void *v13; // rax
  void *v14; // rbx
  int v15; // eax
  unsigned int v16; // edi
  unsigned __int64 v17; // rdx
  SECURITY_STATUS v19; // eax
  unsigned __int64 v20; // rdx
  int pcbResult; // [rsp+20h] [rbp-40h]
  int pcbResulta; // [rsp+20h] [rbp-40h]
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-20h] BYREF
  ULONG v24; // [rsp+44h] [rbp-1Ch] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp-10h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  phProvider = 0;
  v9 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Software Key Storage Provider", 0);
  Property = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A6,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v9,
      pcbResult);
LABEL_28:
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return (unsigned int)Property;
  }
  phAlgorithm = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( Property < 0 )
  {
    v11 = 1194;
    goto LABEL_26;
  }
  *(_DWORD *)pbOutput = 0;
  v24 = 0;
  Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &v24, 0);
  if ( Property < 0 )
  {
    v11 = 1197;
    goto LABEL_26;
  }
  v12 = *(_DWORD *)pbOutput;
  v13 = operator new[](*(unsigned int *)pbOutput, (const struct std::nothrow_t *)&std::nothrow);
  v14 = v13;
  if ( !v13 )
  {
    Property = -2147024882;
    v11 = 1200;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)Property,
      pcbResult);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    goto LABEL_28;
  }
  memset_0(v13, 0, v12);
  v15 = BCryptHash(phAlgorithm, 0, 0, a1);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B2,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v15,
      a2);
LABEL_10:
    operator delete(v14, v17);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    if ( phProvider )
      NCryptFreeObject(phProvider);
    return v16;
  }
  phKey = 0;
  v19 = NCryptOpenKey(phProvider, &phKey, L"SparseGenerationAppxsvcKey", 0, 0x20u);
  v16 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B5,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
      (const char *)(unsigned int)v19,
      pcbResulta);
    if ( phKey )
      NCryptFreeObject(phKey);
    goto LABEL_10;
  }
  *a5 = NCryptVerifySignature(phKey, 0, (PBYTE)v14, *(DWORD *)pbOutput, a3, a4, 0) == 0;
  if ( phKey )
    NCryptFreeObject(phKey);
  operator delete(v14, v20);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return 0;
}

```

## disassembly

```asm
0x18001fae8  mov     rax, rsp
0x18001faeb  mov     [rax+8], rbx
0x18001faef  mov     [rax+10h], rsi
0x18001faf3  mov     [rax+18h], rdi
0x18001faf7  mov     [rax+20h], r12
0x18001fafb  push    rbp
0x18001fafc  push    r14
0x18001fafe  push    r15
0x18001fb00  mov     rbp, rsp
0x18001fb03  sub     rsp, 60h
0x18001fb07  and     [rbp+phProvider], 0
0x18001fb0c  mov     r14, r8
0x18001fb0f  mov     r15d, edx
0x18001fb12  mov     r12, rcx
0x18001fb15  xor     r8d, r8d; dwFlags
0x18001fb18  lea     rdx, pszProviderName; "Microsoft Software Key Storage Provider"
0x18001fb1f  lea     rcx, [rbp+phProvider]; phProvider
0x18001fb23  mov     esi, r9d
0x18001fb26  call    cs:__imp_NCryptOpenStorageProvider
0x18001fb2d  nop     dword ptr [rax+rax+00h]
0x18001fb32  mov     ebx, eax
0x18001fb34  test    eax, eax
0x18001fb36  jns     short loc_18001FB55
0x18001fb38  mov     rcx, [rbp+18h]; this
0x18001fb3c  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001fb43  mov     r9d, eax; char *
0x18001fb46  mov     edx, 4A6h; void *
0x18001fb4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb50  jmp     loc_18001FD94
0x18001fb55  and     [rbp+phAlgorithm], 0
0x18001fb5a  lea     rdx, aSha256; "SHA256"
0x18001fb61  xor     r9d, r9d; dwFlags
0x18001fb64  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18001fb68  xor     r8d, r8d; pszImplementation
0x18001fb6b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001fb72  nop     dword ptr [rax+rax+00h]
0x18001fb77  mov     ebx, eax
0x18001fb79  test    eax, eax
0x18001fb7b  jns     short loc_18001FB87
0x18001fb7d  mov     edx, 4AAh
0x18001fb82  jmp     loc_18001FD6A
0x18001fb87  and     [rsp+60h+cbSignature], 0
0x18001fb8c  lea     rax, [rbp+var_1C]
0x18001fb90  mov     rcx, [rbp+phAlgorithm]; hObject
0x18001fb94  lea     r8, [rbp+pbOutput]; pbOutput
0x18001fb98  and     dword ptr [rbp+pbOutput], 0
0x18001fb9c  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18001fba3  and     [rbp+var_1C], 0
0x18001fba7  mov     r9d, 4; cbOutput
0x18001fbad  mov     [rsp+60h+pcbResult], rax; int
0x18001fbb2  call    cs:__imp_BCryptGetProperty
0x18001fbb9  nop     dword ptr [rax+rax+00h]
0x18001fbbe  mov     ebx, eax
0x18001fbc0  test    eax, eax
0x18001fbc2  jns     short loc_18001FBCE
0x18001fbc4  mov     edx, 4ADh
0x18001fbc9  jmp     loc_18001FD6A
0x18001fbce  mov     edi, dword ptr [rbp+pbOutput]
0x18001fbd1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fbd8  mov     ecx, edi; unsigned __int64
0x18001fbda  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001fbdf  mov     rbx, rax
0x18001fbe2  test    rax, rax
0x18001fbe5  jz      loc_18001FD60
0x18001fbeb  mov     r8d, edi; Size
0x18001fbee  xor     edx, edx; Val
0x18001fbf0  mov     rcx, rax; void *
0x18001fbf3  call    memset_0
0x18001fbf8  mov     eax, dword ptr [rbp+pbOutput]
0x18001fbfb  mov     r9, r12
0x18001fbfe  mov     rcx, [rbp+phAlgorithm]
0x18001fc02  xor     r8d, r8d
0x18001fc05  mov     [rsp+60h+dwFlags], eax; dwFlags
0x18001fc09  xor     edx, edx
0x18001fc0b  mov     qword ptr [rsp+60h+cbSignature], rbx
0x18001fc10  mov     dword ptr [rsp+60h+pcbResult], r15d; int
0x18001fc15  call    cs:__imp_BCryptHash
0x18001fc1c  nop     dword ptr [rax+rax+00h]
0x18001fc21  mov     edi, eax
0x18001fc23  test    eax, eax
0x18001fc25  jns     short loc_18001FC7A
0x18001fc27  mov     rcx, [rbp+18h]; this
0x18001fc2b  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001fc32  mov     r9d, eax; char *
0x18001fc35  mov     edx, 4B2h; void *
0x18001fc3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc3f  mov     rcx, rbx; void *
0x18001fc42  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fc47  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001fc4b  test    rcx, rcx
0x18001fc4e  jz      short loc_18001FC5E
0x18001fc50  xor     edx, edx; dwFlags
0x18001fc52  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001fc59  nop     dword ptr [rax+rax+00h]
0x18001fc5e  mov     rcx, [rbp+phProvider]; hObject
0x18001fc62  test    rcx, rcx
0x18001fc65  jz      short loc_18001FC73
0x18001fc67  call    cs:__imp_NCryptFreeObject
0x18001fc6e  nop     dword ptr [rax+rax+00h]
0x18001fc73  mov     eax, edi
0x18001fc75  jmp     loc_18001FDAB
0x18001fc7a  mov     rcx, [rbp+phProvider]; hProvider
0x18001fc7e  lea     r8, pszKeyName; "SparseGenerationAppxsvcKey"
0x18001fc85  and     [rbp+phKey], 0
0x18001fc8a  lea     rdx, [rbp+phKey]; phKey
0x18001fc8e  xor     r9d, r9d; dwLegacyKeySpec
0x18001fc91  mov     dword ptr [rsp+60h+pcbResult], 20h ; ' '; int
0x18001fc99  call    cs:__imp_NCryptOpenKey
0x18001fca0  nop     dword ptr [rax+rax+00h]
0x18001fca5  mov     edi, eax
0x18001fca7  test    eax, eax
0x18001fca9  jns     short loc_18001FCE1
0x18001fcab  mov     rcx, [rbp+18h]; this
0x18001fcaf  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001fcb6  mov     r9d, eax; char *
0x18001fcb9  mov     edx, 4B5h; void *
0x18001fcbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fcc3  mov     rcx, [rbp+phKey]; hObject
0x18001fcc7  test    rcx, rcx
0x18001fcca  jz      loc_18001FC3F
0x18001fcd0  call    cs:__imp_NCryptFreeObject
0x18001fcd7  nop     dword ptr [rax+rax+00h]
0x18001fcdc  jmp     loc_18001FC3F
0x18001fce1  and     [rsp+60h+dwFlags], 0
0x18001fce6  mov     r8, rbx; pbHashValue
0x18001fce9  mov     r9d, dword ptr [rbp+pbOutput]; cbHashValue
0x18001fced  xor     edx, edx; pPaddingInfo
0x18001fcef  mov     rcx, [rbp+phKey]; hKey
0x18001fcf3  mov     [rsp+60h+cbSignature], esi; cbSignature
0x18001fcf7  mov     [rsp+60h+pcbResult], r14; pbSignature
0x18001fcfc  call    cs:__imp_NCryptVerifySignature
0x18001fd03  nop     dword ptr [rax+rax+00h]
0x18001fd08  test    eax, eax
0x18001fd0a  mov     rax, [rbp+arg_20]
0x18001fd0e  setz    cl
0x18001fd11  mov     [rax], cl
0x18001fd13  mov     rcx, [rbp+phKey]; hObject
0x18001fd17  test    rcx, rcx
0x18001fd1a  jz      short loc_18001FD28
0x18001fd1c  call    cs:__imp_NCryptFreeObject
0x18001fd23  nop     dword ptr [rax+rax+00h]
0x18001fd28  mov     rcx, rbx; void *
0x18001fd2b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fd30  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001fd34  test    rcx, rcx
0x18001fd37  jz      short loc_18001FD47
0x18001fd39  xor     edx, edx; dwFlags
0x18001fd3b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001fd42  nop     dword ptr [rax+rax+00h]
0x18001fd47  mov     rcx, [rbp+phProvider]; hObject
0x18001fd4b  test    rcx, rcx
0x18001fd4e  jz      short loc_18001FD5C
0x18001fd50  call    cs:__imp_NCryptFreeObject
0x18001fd57  nop     dword ptr [rax+rax+00h]
0x18001fd5c  xor     eax, eax
0x18001fd5e  jmp     short loc_18001FDAB
0x18001fd60  mov     ebx, 8007000Eh
0x18001fd65  mov     edx, 4B0h; void *
0x18001fd6a  mov     rcx, [rbp+18h]; this
0x18001fd6e  lea     r8, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\execmodel\\des"...
0x18001fd75  mov     r9d, ebx; char *
0x18001fd78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd7d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18001fd81  test    rcx, rcx
0x18001fd84  jz      short loc_18001FD94
0x18001fd86  xor     edx, edx; dwFlags
0x18001fd88  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001fd8f  nop     dword ptr [rax+rax+00h]
0x18001fd94  mov     rcx, [rbp+phProvider]; hObject
0x18001fd98  test    rcx, rcx
0x18001fd9b  jz      short loc_18001FDA9
0x18001fd9d  call    cs:__imp_NCryptFreeObject
0x18001fda4  nop     dword ptr [rax+rax+00h]
0x18001fda9  mov     eax, ebx
0x18001fdab  lea     r11, [rsp+60h+var_s0]
0x18001fdb0  mov     rbx, [r11+20h]
0x18001fdb4  mov     rsi, [r11+28h]
0x18001fdb8  mov     rdi, [r11+30h]
0x18001fdbc  mov     r12, [r11+38h]
0x18001fdc0  mov     rsp, r11
0x18001fdc3  pop     r15
0x18001fdc5  pop     r14
0x18001fdc7  pop     rbp
0x18001fdc8  retn
```
