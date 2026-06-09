# winrt::Windows::Internal::Eap::Utility::implementation::TlsHashInternal(ushort const *,gsl::span<uchar,-1>,gsl::span<uchar,-1>)

- ea: `0x18002fdc0`
- end: `0x18003001a`
- name: `?TlsHashInternal@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@PEBGV?$span@E$0?0@gsl@@1@Z`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001e6b0`

## callees

- `0x1800101c4`
- `0x18001767c`
- `0x180025cd0`
- `0x18002dd5c`
- `0x18002e598`
- `0x18002fdc0`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002fe03`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002fe03`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002ff7b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002ff7b`
- `bcrypt!BCryptCreateHash` at `0x18002ff04`
- `bcrypt!BCryptCreateHash` at `0x18002ff04`
- `bcrypt!BCryptHashData` at `0x18002ff25`
- `bcrypt!BCryptHashData` at `0x18002ff25`
- `bcrypt!BCryptFinishHash` at `0x18002ff47`
- `bcrypt!BCryptFinishHash` at `0x18002ff47`
- `bcrypt!BCryptDestroyHash` at `0x18002ff5f`
- `bcrypt!BCryptDestroyHash` at `0x18002ff5f`
- `bcrypt!BCryptGetProperty` at `0x18002fe50`
- `bcrypt!BCryptGetProperty` at `0x18002fe97`
- `bcrypt!BCryptGetProperty` at `0x18002fe50`
- `bcrypt!BCryptGetProperty` at `0x18002fe97`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::TlsHashInternal(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4)
{
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int pcbResult; // [rsp+28h] [rbp-29h]
  int pcbResulta; // [rsp+28h] [rbp-29h]
  int pcbResultb; // [rsp+28h] [rbp-29h]
  int pcbResultc; // [rsp+28h] [rbp-29h]
  ULONG v18; // [rsp+48h] [rbp-9h] BYREF
  UCHAR pbOutput[4]; // [rsp+4Ch] [rbp-5h] BYREF
  UCHAR v20[4]; // [rsp+50h] [rbp-1h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp+7h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp+Fh] BYREF
  int v23; // [rsp+68h] [rbp+17h]
  PUCHAR cbOutput[2]; // [rsp+70h] [rbp+1Fh] BYREF
  PUCHAR pbHashObject[3]; // [rsp+80h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B0h] [rbp+5Fh]

  v23 = 0;
  phAlgorithm = 0;
  v7 = BCryptOpenAlgorithmProvider(&phAlgorithm, a2, 0, 8u) | 0x10000000;
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v7,
      pcbResult);
  *(_DWORD *)pbOutput = 0;
  v18 = 0;
  v8 = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &v18, 0) | 0x10000000;
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v8,
      pcbResulta);
  *(_DWORD *)v20 = 0;
  v18 = 0;
  v9 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v20, 4u, &v18, 0) | 0x10000000;
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v9,
      pcbResultb);
  winrt::Windows::Internal::Eap::Utility::implementation::AllocateEmptyIBuffer(a1, *(unsigned int *)v20);
  v23 = 1;
  winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(cbOutput, a1);
  std::vector<unsigned char>::vector<unsigned char>(pbHashObject, *(unsigned int *)pbOutput);
  phHash = 0;
  v10 = BCryptCreateHash(
          phAlgorithm,
          &phHash,
          pbHashObject[0],
          *(ULONG *)pbOutput,
          *(PUCHAR *)(a3 + 8),
          *(_DWORD *)a3,
          0)
      | 0x10000000;
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v10,
      pcbResultc);
  v11 = BCryptHashData(phHash, *(PUCHAR *)(a4 + 8), *(_DWORD *)a4, 0) | 0x10000000;
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v11,
      pcbResultc);
  v12 = BCryptFinishHash(phHash, cbOutput[1], (ULONG)cbOutput[0], 0) | 0x10000000;
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v12,
      pcbResultc);
  if ( phHash )
    BCryptDestroyHash(phHash);
  std::vector<unsigned char>::~vector<unsigned char>((char **)pbHashObject);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return a1;
}

```

## disassembly

```asm
0x18002fdc0  mov     rax, rsp
0x18002fdc3  mov     [rax+10h], rbx
0x18002fdc7  mov     [rax+18h], rsi
0x18002fdcb  mov     [rax+8], rcx
0x18002fdcf  push    rbp
0x18002fdd0  push    rdi
0x18002fdd1  push    r15
0x18002fdd3  lea     rbp, [rax-5Fh]
0x18002fdd7  sub     rsp, 90h
0x18002fdde  mov     rdi, r9
0x18002fde1  mov     rsi, r8
0x18002fde4  mov     rbx, rcx
0x18002fde7  mov     [rbp+57h+var_40], 0
0x18002fdee  mov     [rbp+57h+phAlgorithm], 0
0x18002fdf6  mov     r9d, 8; dwFlags
0x18002fdfc  xor     r8d, r8d; pszImplementation
0x18002fdff  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18002fe03  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002fe09  mov     r15d, 10000000h
0x18002fe0f  or      eax, r15d
0x18002fe12  mov     rcx, [rbp+5Fh]; this
0x18002fe16  jl      loc_18002FFB1
0x18002fe1c  mov     dword ptr [rbp+57h+pbOutput], 0
0x18002fe23  mov     [rbp+57h+var_60], 0
0x18002fe2a  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x18002fe32  lea     rax, [rbp+57h+var_60]
0x18002fe36  mov     [rsp+0A0h+pcbResult], rax; int
0x18002fe3b  mov     r9d, 4; cbOutput
0x18002fe41  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18002fe45  lea     rdx, pszProperty; "ObjectLength"
0x18002fe4c  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18002fe50  call    cs:__imp_BCryptGetProperty
0x18002fe56  or      eax, r15d
0x18002fe59  mov     rcx, [rbp+5Fh]; this
0x18002fe5d  jl      loc_18002FFC6
0x18002fe63  mov     dword ptr [rbp+57h+var_58], 0
0x18002fe6a  mov     [rbp+57h+var_60], 0
0x18002fe71  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x18002fe79  lea     rax, [rbp+57h+var_60]
0x18002fe7d  mov     [rsp+0A0h+pcbResult], rax; int
0x18002fe82  mov     r9d, 4; cbOutput
0x18002fe88  lea     r8, [rbp+57h+var_58]; pbOutput
0x18002fe8c  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18002fe93  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18002fe97  call    cs:__imp_BCryptGetProperty
0x18002fe9d  or      eax, r15d
0x18002fea0  mov     rcx, [rbp+5Fh]; this
0x18002fea4  jl      loc_18002FFDB
0x18002feaa  mov     edx, dword ptr [rbp+57h+var_58]
0x18002fead  mov     rcx, rbx
0x18002feb0  call    ?AllocateEmptyIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@K@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateEmptyIBuffer(ulong)
0x18002feb5  mov     [rbp+57h+var_40], 1
0x18002febc  mov     rdx, rbx
0x18002febf  lea     rcx, [rbp+57h+cbOutput]
0x18002fec3  call    ?GetBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AV?$span@$$CBE$0?0@gsl@@AEBUIBuffer@Streams@Storage@56@@Z; winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(winrt::Windows::Storage::Streams::IBuffer const &)
0x18002fec8  mov     edx, dword ptr [rbp+57h+pbOutput]
0x18002fecb  lea     rcx, [rbp+57h+pbHashObject]
0x18002fecf  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18002fed4  nop
0x18002fed5  mov     [rbp+57h+phHash], 0
0x18002fedd  mov     [rsp+0A0h+var_70], 0; dwFlags
0x18002fee5  mov     eax, [rsi]
0x18002fee7  mov     [rsp+0A0h+dwFlags], eax; cbSecret
0x18002feeb  mov     rax, [rsi+8]
0x18002feef  mov     [rsp+0A0h+pcbResult], rax; int
0x18002fef4  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x18002fef8  mov     r8, [rbp+57h+pbHashObject]; pbHashObject
0x18002fefc  lea     rdx, [rbp+57h+phHash]; phHash
0x18002ff00  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18002ff04  call    cs:__imp_BCryptCreateHash
0x18002ff0a  or      eax, r15d
0x18002ff0d  mov     rcx, [rbp+5Fh]; this
0x18002ff11  jl      loc_18002FFF0
0x18002ff17  xor     r9d, r9d; dwFlags
0x18002ff1a  mov     r8d, [rdi]; cbInput
0x18002ff1d  mov     rdx, [rdi+8]; pbInput
0x18002ff21  mov     rcx, [rbp+57h+phHash]; hHash
0x18002ff25  call    cs:__imp_BCryptHashData
0x18002ff2b  or      eax, r15d
0x18002ff2e  mov     rcx, [rbp+5Fh]; this
0x18002ff32  jl      loc_180030005
0x18002ff38  xor     r9d, r9d; dwFlags
0x18002ff3b  mov     r8d, dword ptr [rbp+57h+cbOutput]; cbOutput
0x18002ff3f  mov     rdx, [rbp+57h+var_30]; pbOutput
0x18002ff43  mov     rcx, [rbp+57h+phHash]; hHash
0x18002ff47  call    cs:__imp_BCryptFinishHash
0x18002ff4d  or      eax, r15d
0x18002ff50  mov     rcx, [rbp+5Fh]; this
0x18002ff54  jl      short loc_18002FF9C
0x18002ff56  mov     rcx, [rbp+57h+phHash]; hHash
0x18002ff5a  test    rcx, rcx
0x18002ff5d  jz      short loc_18002FF66
0x18002ff5f  call    cs:__imp_BCryptDestroyHash
0x18002ff65  nop
0x18002ff66  lea     rcx, [rbp+57h+pbHashObject]
0x18002ff6a  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002ff6f  nop
0x18002ff70  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18002ff74  test    rcx, rcx
0x18002ff77  jz      short loc_18002FF81
0x18002ff79  xor     edx, edx; dwFlags
0x18002ff7b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18002ff81  mov     rax, rbx
0x18002ff84  lea     r11, [rsp+0A0h+var_10]
0x18002ff8c  mov     rbx, [r11+28h]
0x18002ff90  mov     rsi, [r11+30h]
0x18002ff94  mov     rsp, r11
0x18002ff97  pop     r15
0x18002ff99  pop     rdi
0x18002ff9a  pop     rbp
0x18002ff9b  retn
0x18002ff9c  mov     r9d, eax; char *
0x18002ff9f  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002ffa6  mov     edx, 79h ; 'y'; void *
0x18002ffab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ffb1  mov     r9d, eax; char *
0x18002ffb4  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002ffbb  mov     edx, 65h ; 'e'; void *
0x18002ffc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ffc6  mov     r9d, eax; char *
0x18002ffc9  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002ffd0  mov     edx, 6Ah ; 'j'; void *
0x18002ffd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ffdb  mov     r9d, eax; char *
0x18002ffde  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002ffe5  mov     edx, 6Fh ; 'o'; void *
0x18002ffea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002fff0  mov     r9d, eax; char *
0x18002fff3  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18002fffa  mov     edx, 77h ; 'w'; void *
0x18002ffff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030005  mov     r9d, eax; char *
0x180030008  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18003000f  mov     edx, 78h ; 'x'; void *
0x180030014  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
