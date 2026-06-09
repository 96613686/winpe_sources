# winrt::Windows::Internal::Eap::Utility::implementation::TlsPrfInternal(ushort const *,gsl::span<uchar,-1>,gsl::span<uchar,-1>,unsigned __int64)

- ea: `0x180030020`
- end: `0x1800303ca`
- name: `?TlsPrfInternal@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@PEBGV?$span@E$0?0@gsl@@1_K@Z`
- size: `938`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001e880`

## callees

- `0x180004380`
- `0x180007eac`
- `0x1800101c4`
- `0x180010df0`
- `0x18001767c`
- `0x180025cd0`
- `0x18002dd5c`
- `0x18002e598`
- `0x18002fc6c`
- `0x180030020`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180030068`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180030068`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180030329`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180030329`
- `bcrypt!BCryptGetProperty` at `0x1800300ab`
- `bcrypt!BCryptGetProperty` at `0x1800300e5`
- `bcrypt!BCryptGetProperty` at `0x18003012a`
- `bcrypt!BCryptGetProperty` at `0x1800300ab`
- `bcrypt!BCryptGetProperty` at `0x1800300e5`
- `bcrypt!BCryptGetProperty` at `0x18003012a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::TlsPrfInternal(
        __int64 a1,
        const WCHAR *a2,
        _DWORD *a3,
        const void *const *a4,
        unsigned int a5)
{
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  rsize_t v12; // rdi
  gsl::details *v13; // rcx
  char *v14; // rsi
  unsigned __int64 v15; // rax
  rsize_t v16; // rbx
  unsigned __int64 v17; // r14
  rsize_t v18; // r15
  char *v19; // r13
  rsize_t v20; // rdi
  char *v21; // r15
  unsigned int v23; // eax
  int pcbResult; // [rsp+28h] [rbp-81h]
  int pcbResulta; // [rsp+28h] [rbp-81h]
  int pcbResultb; // [rsp+28h] [rbp-81h]
  int pcbResultc; // [rsp+28h] [rbp-81h]
  ULONG v28; // [rsp+38h] [rbp-71h] BYREF
  UCHAR pbOutput[4]; // [rsp+3Ch] [rbp-6Dh] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-69h] BYREF
  UCHAR v31[4]; // [rsp+48h] [rbp-61h] BYREF
  UCHAR v32[4]; // [rsp+4Ch] [rbp-5Dh] BYREF
  int v33; // [rsp+50h] [rbp-59h]
  unsigned __int64 phHash; // [rsp+58h] [rbp-51h] BYREF
  char *v35; // [rsp+60h] [rbp-49h]
  rsize_t DestinationSize; // [rsp+68h] [rbp-41h] BYREF
  void *Destination; // [rsp+70h] [rbp-39h]
  __int128 v38; // [rsp+78h] [rbp-31h] BYREF
  __int128 v39; // [rsp+88h] [rbp-21h] BYREF
  __int128 v40; // [rsp+98h] [rbp-11h] BYREF
  char *v41; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v42; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+57h]

  v33 = 0;
  phAlgorithm = 0;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, a2, 0, 8u) | 0x10000000;
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v8,
      pcbResult);
  *(_DWORD *)pbOutput = 0;
  v28 = 0;
  v9 = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &v28, 0) | 0x10000000;
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v9,
      pcbResulta);
  *(_DWORD *)v32 = 0;
  v28 = 0;
  v10 = BCryptGetProperty(phAlgorithm, L"HashBlockLength", v32, 4u, &v28, 0) | 0x10000000;
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v10,
      pcbResultb);
  if ( *(_DWORD *)v32 < *a3 )
  {
    v23 = wil::verify_hresult<long>(0x80004001);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)v23,
      pcbResultb);
  }
  *(_DWORD *)v31 = 0;
  v28 = 0;
  v11 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v31, 4u, &v28, 0) | 0x10000000;
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\cryptohelper.cpp",
      (const char *)(unsigned int)v11,
      pcbResultc);
  winrt::Windows::Internal::Eap::Utility::implementation::AllocateEmptyIBuffer(a1, a5);
  v33 = 1;
  winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(&DestinationSize, a1);
  v12 = (rsize_t)*a4;
  std::vector<unsigned char>::vector<unsigned char>(&v41, v12 + 2LL * *(unsigned int *)v31);
  v14 = v41;
  v15 = v42 - (_QWORD)v41;
  if ( v42 - (_QWORD)v41 == -1 || !v41 && v15 )
    goto LABEL_33;
  v16 = *(unsigned int *)v31;
  if ( *(unsigned int *)v31 > v15 || !v41 && *(_DWORD *)v31 )
    goto LABEL_33;
  v17 = *(unsigned int *)v31 + v12;
  if ( v17 > v15 || v17 == -1 || !v41 && v17 )
    goto LABEL_33;
  v13 = (gsl::details *)(v15 - *(unsigned int *)v31);
  if ( v12 == -1 )
  {
    v18 = v15 - *(unsigned int *)v31;
    if ( v13 == (gsl::details *)-1LL )
      goto LABEL_33;
  }
  else
  {
    if ( (unsigned __int64)v13 < v12 )
      goto LABEL_33;
    v18 = v12;
  }
  if ( v15 < (unsigned __int64)v13 )
LABEL_33:
    gsl::details::terminate(v13);
  v19 = &v41[(_QWORD)v13];
  phHash = *(unsigned int *)v31;
  v35 = v41;
  v39 = *(_OWORD *)a4;
  v38 = *(_OWORD *)a3;
  winrt::Windows::Internal::Eap::Utility::implementation::HMAC_Hash(
    phAlgorithm,
    *(ULONG *)pbOutput,
    (__int64)&v38,
    (__int64)&v39,
    &phHash);
  memcpy_s(&v14[v16], v18, a4[1], v12);
  v20 = DestinationSize;
  if ( DestinationSize )
  {
    v21 = (char *)Destination;
    while ( 1 )
    {
      DestinationSize = v16;
      Destination = v19;
      phHash = v17;
      v35 = v14;
      v40 = *(_OWORD *)a3;
      winrt::Windows::Internal::Eap::Utility::implementation::HMAC_Hash(
        phAlgorithm,
        *(ULONG *)pbOutput,
        (__int64)&v40,
        (__int64)&phHash,
        &DestinationSize);
      if ( v20 <= v16 )
        break;
      memcpy_s(v21, v20, v19, v16);
      v20 -= v16;
      if ( v20 == -1 )
        goto LABEL_33;
      v21 += v16;
      *(_QWORD *)&v38 = v16;
      *((_QWORD *)&v38 + 1) = v14;
      *(_QWORD *)&v39 = v16;
      *((_QWORD *)&v39 + 1) = v14;
      v40 = *(_OWORD *)a3;
      winrt::Windows::Internal::Eap::Utility::implementation::HMAC_Hash(
        phAlgorithm,
        *(ULONG *)pbOutput,
        (__int64)&v40,
        (__int64)&v39,
        &v38);
      if ( !v20 )
        goto LABEL_29;
    }
    memcpy_s(v21, v20, v19, v20);
  }
LABEL_29:
  std::vector<unsigned char>::~vector<unsigned char>(&v41);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return a1;
}

```

## disassembly

```asm
0x180030020  mov     rax, rsp
0x180030023  mov     [rax+10h], rbx
0x180030027  mov     [rax+20h], r9
0x18003002b  mov     [rax+18h], r8
0x18003002f  mov     [rax+8], rcx
0x180030033  push    rbp
0x180030034  push    rsi
0x180030035  push    rdi
0x180030036  push    r12
0x180030038  push    r13
0x18003003a  push    r14
0x18003003c  push    r15
0x18003003e  lea     rbp, [rax-57h]
0x180030042  sub     rsp, 0C0h
0x180030049  mov     rdi, r9
0x18003004c  mov     rbx, r8
0x18003004f  mov     r12, rcx
0x180030052  xor     r15d, r15d
0x180030055  mov     [rbp+4Fh+var_A8], r15d
0x180030059  mov     [rbp+4Fh+phAlgorithm], r15
0x18003005d  lea     r9d, [r15+8]; dwFlags
0x180030061  xor     r8d, r8d; pszImplementation
0x180030064  lea     rcx, [rbp+4Fh+phAlgorithm]; phAlgorithm
0x180030068  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003006e  mov     esi, 10000000h
0x180030073  or      eax, esi
0x180030075  mov     rcx, [rbp+57h]; this
0x180030079  jl      loc_180030368
0x18003007f  mov     dword ptr [rbp+4Fh+pbOutput], r15d
0x180030083  mov     [rbp+4Fh+var_C0], r15d
0x180030087  mov     [rsp+0F0h+pcbResult+8], r15d; dwFlags
0x18003008c  lea     rax, [rbp+4Fh+var_C0]
0x180030090  mov     qword ptr [rsp+0F0h+pcbResult], rax; int
0x180030095  lea     r14d, [r15+4]
0x180030099  mov     r9d, r14d; cbOutput
0x18003009c  lea     r8, [rbp+4Fh+pbOutput]; pbOutput
0x1800300a0  lea     rdx, pszProperty; "ObjectLength"
0x1800300a7  mov     rcx, [rbp+4Fh+phAlgorithm]; hObject
0x1800300ab  call    cs:__imp_BCryptGetProperty
0x1800300b1  or      eax, esi
0x1800300b3  mov     rcx, [rbp+57h]; this
0x1800300b7  jl      loc_18003037D
0x1800300bd  mov     dword ptr [rbp+4Fh+var_AC], r15d
0x1800300c1  mov     [rbp+4Fh+var_C0], r15d
0x1800300c5  mov     [rsp+0F0h+pcbResult+8], r15d; dwFlags
0x1800300ca  lea     rax, [rbp+4Fh+var_C0]
0x1800300ce  mov     qword ptr [rsp+0F0h+pcbResult], rax; int
0x1800300d3  mov     r9d, r14d; cbOutput
0x1800300d6  lea     r8, [rbp+4Fh+var_AC]; pbOutput
0x1800300da  lea     rdx, aHashblocklengt; "HashBlockLength"
0x1800300e1  mov     rcx, [rbp+4Fh+phAlgorithm]; hObject
0x1800300e5  call    cs:__imp_BCryptGetProperty
0x1800300eb  or      eax, esi
0x1800300ed  mov     rcx, [rbp+57h]; this
0x1800300f1  jl      loc_180030392
0x1800300f7  mov     eax, [rbx]
0x1800300f9  cmp     dword ptr [rbp+4Fh+var_AC], eax
0x1800300fc  jb      loc_1800303A7
0x180030102  mov     dword ptr [rbp+4Fh+var_B0], r15d
0x180030106  mov     [rbp+4Fh+var_C0], r15d
0x18003010a  mov     [rsp+0F0h+pcbResult+8], r15d; dwFlags
0x18003010f  lea     rax, [rbp+4Fh+var_C0]
0x180030113  mov     qword ptr [rsp+0F0h+pcbResult], rax; int
0x180030118  mov     r9d, r14d; cbOutput
0x18003011b  lea     r8, [rbp+4Fh+var_B0]; pbOutput
0x18003011f  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180030126  mov     rcx, [rbp+4Fh+phAlgorithm]; hObject
0x18003012a  call    cs:__imp_BCryptGetProperty
0x180030130  or      eax, esi
0x180030132  mov     rcx, [rbp+57h]; this
0x180030136  jl      loc_18003034D
0x18003013c  mov     edx, [rbp+4Fh+arg_20]
0x18003013f  mov     rcx, r12
0x180030142  call    ?AllocateEmptyIBuffer@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@K@Z; winrt::Windows::Internal::Eap::Utility::implementation::AllocateEmptyIBuffer(ulong)
0x180030147  mov     [rbp+4Fh+var_A8], 1
0x18003014e  mov     rdx, r12
0x180030151  lea     rcx, [rbp+4Fh+DestinationSize]
0x180030155  call    ?GetBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AV?$span@$$CBE$0?0@gsl@@AEBUIBuffer@Streams@Storage@56@@Z; winrt::Windows::Internal::Eap::Utility::implementation::GetBytes(winrt::Windows::Storage::Streams::IBuffer const &)
0x18003015a  mov     rdi, [rdi]
0x18003015d  mov     eax, dword ptr [rbp+4Fh+var_B0]
0x180030160  lea     rdx, [rdi+rax*2]
0x180030164  lea     rcx, [rbp+4Fh+var_50]
0x180030168  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18003016d  nop
0x18003016e  mov     rsi, [rbp+4Fh+var_50]
0x180030172  mov     rax, [rbp+4Fh+var_48]
0x180030176  sub     rax, rsi
0x180030179  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003017d  jz      loc_180030362
0x180030183  test    rsi, rsi
0x180030186  jnz     short loc_180030191
0x180030188  test    rax, rax
0x18003018b  jnz     loc_180030362
0x180030191  mov     ebx, dword ptr [rbp+4Fh+var_B0]
0x180030194  cmp     rbx, rax
0x180030197  ja      loc_180030362
0x18003019d  test    rsi, rsi
0x1800301a0  jnz     short loc_1800301AB
0x1800301a2  test    rbx, rbx
0x1800301a5  jnz     loc_180030362
0x1800301ab  lea     r14, [rbx+rdi]
0x1800301af  cmp     r14, rax
0x1800301b2  ja      loc_180030362
0x1800301b8  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x1800301bc  jz      loc_180030362
0x1800301c2  test    rsi, rsi
0x1800301c5  jnz     short loc_1800301D0
0x1800301c7  test    r14, r14
0x1800301ca  jnz     loc_180030362
0x1800301d0  mov     rcx, rax
0x1800301d3  sub     rcx, rbx
0x1800301d6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800301da  jnz     short loc_1800301EA
0x1800301dc  mov     r15, rcx
0x1800301df  cmp     rcx, rdi
0x1800301e2  jz      loc_180030362
0x1800301e8  jmp     short loc_1800301F6
0x1800301ea  cmp     rcx, rdi
0x1800301ed  jb      loc_180030362
0x1800301f3  mov     r15, rdi
0x1800301f6  cmp     rax, rcx
0x1800301f9  jb      loc_180030362
0x1800301ff  lea     r13, [rcx+rsi]
0x180030203  mov     [rbp+4Fh+phHash], rbx
0x180030207  mov     [rbp+4Fh+var_98], rsi
0x18003020b  mov     rax, [rbp+4Fh+arg_18]
0x18003020f  movaps  xmm0, xmmword ptr [rax]
0x180030212  movdqa  [rbp+4Fh+var_70], xmm0
0x180030217  mov     rax, [rbp+4Fh+arg_10]
0x18003021b  movaps  xmm1, xmmword ptr [rax]
0x18003021e  movdqa  [rbp+4Fh+var_80], xmm1
0x180030223  lea     rax, [rbp+4Fh+phHash]
0x180030227  mov     qword ptr [rsp+0F0h+pcbResult], rax; phHash
0x18003022c  lea     r9, [rbp+4Fh+var_70]
0x180030230  lea     r8, [rbp+4Fh+var_80]
0x180030234  mov     edx, dword ptr [rbp+4Fh+pbOutput]; cbHashObject
0x180030237  mov     rcx, [rbp+4Fh+phAlgorithm]; hAlgorithm
0x18003023b  call    ?HMAC_Hash@implementation@Utility@Eap@Internal@Windows@winrt@@YAXQEAXKV?$span@E$0?0@gsl@@11@Z; winrt::Windows::Internal::Eap::Utility::implementation::HMAC_Hash(void * const,ulong,gsl::span<uchar,-1>,gsl::span<uchar,-1>,gsl::span<uchar,-1>)
0x180030240  lea     rcx, [rbx+rsi]; Destination
0x180030244  mov     r9, rdi; SourceSize
0x180030247  mov     rax, [rbp+4Fh+arg_18]
0x18003024b  mov     r8, [rax+8]; Source
0x18003024f  mov     rdx, r15; DestinationSize
0x180030252  call    memcpy_s
0x180030257  mov     rdi, [rbp+4Fh+DestinationSize]
0x18003025b  test    rdi, rdi
0x18003025e  jz      loc_180030314
0x180030264  mov     r15, [rbp+4Fh+Destination]
0x180030268  mov     [rbp+4Fh+DestinationSize], rbx
0x18003026c  mov     [rbp+4Fh+Destination], r13
0x180030270  mov     [rbp+4Fh+phHash], r14
0x180030274  mov     [rbp+4Fh+var_98], rsi
0x180030278  mov     rax, [rbp+4Fh+arg_10]
0x18003027c  movaps  xmm0, xmmword ptr [rax]
0x18003027f  movdqa  [rbp+4Fh+var_60], xmm0
0x180030284  lea     rax, [rbp+4Fh+DestinationSize]
0x180030288  mov     qword ptr [rsp+0F0h+pcbResult], rax; phHash
0x18003028d  lea     r9, [rbp+4Fh+phHash]
0x180030291  lea     r8, [rbp+4Fh+var_60]
0x180030295  mov     edx, dword ptr [rbp+4Fh+pbOutput]; cbHashObject
0x180030298  mov     rcx, [rbp+4Fh+phAlgorithm]; hAlgorithm
0x18003029c  call    ?HMAC_Hash@implementation@Utility@Eap@Internal@Windows@winrt@@YAXQEAXKV?$span@E$0?0@gsl@@11@Z; winrt::Windows::Internal::Eap::Utility::implementation::HMAC_Hash(void * const,ulong,gsl::span<uchar,-1>,gsl::span<uchar,-1>,gsl::span<uchar,-1>)
0x1800302a1  mov     r8, r13; Source
0x1800302a4  mov     rdx, rdi; DestinationSize
0x1800302a7  mov     rcx, r15; Destination
0x1800302aa  cmp     rdi, rbx
0x1800302ad  jbe     short loc_18003030B
0x1800302af  mov     r9, rbx; SourceSize
0x1800302b2  call    memcpy_s
0x1800302b7  sub     rdi, rbx
0x1800302ba  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800302be  jz      loc_180030362
0x1800302c4  add     r15, rbx
0x1800302c7  mov     qword ptr [rbp+4Fh+var_80], rbx
0x1800302cb  mov     qword ptr [rbp+4Fh+var_80+8], rsi
0x1800302cf  mov     qword ptr [rbp+4Fh+var_70], rbx
0x1800302d3  mov     qword ptr [rbp+4Fh+var_70+8], rsi
0x1800302d7  mov     rax, [rbp+4Fh+arg_10]
0x1800302db  movaps  xmm0, xmmword ptr [rax]
0x1800302de  movdqa  [rbp+4Fh+var_60], xmm0
0x1800302e3  lea     rax, [rbp+4Fh+var_80]
0x1800302e7  mov     qword ptr [rsp+0F0h+pcbResult], rax; phHash
0x1800302ec  lea     r9, [rbp+4Fh+var_70]
0x1800302f0  lea     r8, [rbp+4Fh+var_60]
0x1800302f4  mov     edx, dword ptr [rbp+4Fh+pbOutput]; cbHashObject
0x1800302f7  mov     rcx, [rbp+4Fh+phAlgorithm]; hAlgorithm
0x1800302fb  call    ?HMAC_Hash@implementation@Utility@Eap@Internal@Windows@winrt@@YAXQEAXKV?$span@E$0?0@gsl@@11@Z; winrt::Windows::Internal::Eap::Utility::implementation::HMAC_Hash(void * const,ulong,gsl::span<uchar,-1>,gsl::span<uchar,-1>,gsl::span<uchar,-1>)
0x180030300  test    rdi, rdi
0x180030303  jnz     loc_180030268
0x180030309  jmp     short loc_180030314
0x18003030b  mov     r9, rdi; SourceSize
0x18003030e  call    memcpy_s
0x180030313  nop
0x180030314  lea     rcx, [rbp+4Fh+var_50]
0x180030318  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18003031d  nop
0x18003031e  mov     rcx, [rbp+4Fh+phAlgorithm]; hAlgorithm
0x180030322  test    rcx, rcx
0x180030325  jz      short loc_18003032F
0x180030327  xor     edx, edx; dwFlags
0x180030329  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18003032f  mov     rax, r12
0x180030332  mov     rbx, [rsp+0F0h+arg_8]
0x18003033a  add     rsp, 0C0h
0x180030341  pop     r15
0x180030343  pop     r14
0x180030345  pop     r13
0x180030347  pop     r12
0x180030349  pop     rdi
0x18003034a  pop     rsi
0x18003034b  pop     rbp
0x18003034c  retn
0x18003034d  mov     r9d, eax; char *
0x180030350  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180030357  mov     edx, 39h ; '9'; void *
0x18003035c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030362  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x180030368  mov     r9d, eax; char *
0x18003036b  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180030372  mov     edx, 22h ; '"'; void *
0x180030377  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003037d  mov     r9d, eax; char *
0x180030380  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x180030387  mov     edx, 27h ; '''; void *
0x18003038c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030392  mov     r9d, eax; char *
0x180030395  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x18003039c  mov     edx, 2Ch ; ','; void *
0x1800303a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800303a7  mov     ecx, 80004001h
0x1800303ac  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800303b1  mov     r9d, eax; char *
0x1800303b4  mov     rcx, [rbp+57h]; this
0x1800303b8  lea     r8, aOnecoreuapNetE_4; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x1800303bf  mov     edx, 33h ; '3'; void *
0x1800303c4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
