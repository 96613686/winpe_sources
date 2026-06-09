# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::BeginTlsHandshakeNew(winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions const &)

- ea: `0x1800188f0`
- end: `0x180018b00`
- name: `?BeginTlsHandshakeNew@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBUEapTlsHandshakeOptions@34567@@Z`
- size: `528`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *__hidden this, const struct winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180018580`
- `0x180018b10`

## callees

- `0x1800083ec`
- `0x1800137f0`
- `0x18001767c`
- `0x1800188f0`
- `0x180018d08`
- `0x180019d04`
- `0x18001a180`
- `0x18001ca90`
- `0x18001e218`
- `0x18001e42c`
- `0x18002e2c8`
- `0x18002e5f4`

## import_xrefs

- `SspiCli!FreeContextBuffer` at `0x180018ae3`
- `SspiCli!FreeContextBuffer` at `0x180018ae3`
- `SspiCli!DeleteSecurityContext` at `0x180018986`
- `SspiCli!DeleteSecurityContext` at `0x180018986`
- `SspiCli!InitializeSecurityContextW` at `0x180018a4c`
- `SspiCli!InitializeSecurityContextW` at `0x180018a4c`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::BeginTlsHandshakeNew(
        winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *this,
        const struct winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions *a2)
{
  __int64 v4; // rdi
  unsigned int v5; // ebx
  unsigned int v6; // eax
  winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *v7; // rdi
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  unsigned int v10; // eax
  int v11; // edx
  bool v12; // r8
  _DWORD v13[2]; // [rsp+60h] [rbp-29h] BYREF
  PVOID pvContextBuffer; // [rsp+68h] [rbp-21h]
  struct _SecBufferDesc pOutput; // [rsp+70h] [rbp-19h] BYREF
  _DWORD *v16; // [rsp+80h] [rbp-9h] BYREF
  __int64 v17; // [rsp+88h] [rbp-1h]
  __int128 v18; // [rsp+90h] [rbp+7h] BYREF
  __int64 v19; // [rsp+A0h] [rbp+17h]
  __int128 v20; // [rsp+A8h] [rbp+1Fh] BYREF
  __int64 v21; // [rsp+B8h] [rbp+2Fh]
  unsigned int pfContextAttr; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v23; // [rsp+100h] [rbp+77h] BYREF

  ++*((_DWORD *)this + 46);
  if ( !*((_DWORD *)this + 64)
    || !(unsigned int)winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::SessionResumptionState(a2)
    || *((_DWORD *)this + 19) != 3 )
  {
    v4 = winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::CertificateContext(a2);
    v5 = winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::CryptographicRestrictions(a2);
    v6 = winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::DisabledTlsVersions(a2);
    winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::InitializeCredentialsHandle(
      this,
      v6,
      v5,
      v4);
  }
  *((_DWORD *)this + 64) = winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::SessionResumptionState(a2);
  if ( *((_QWORD *)this + 15) != -1 && *((_QWORD *)this + 16) != -1 )
  {
    DeleteSecurityContext((PCtxtHandle)((char *)this + 120));
    *((_QWORD *)this + 16) = -1;
    *((_QWORD *)this + 15) = -1;
  }
  v16 = 0;
  v17 = 0;
  v7 = (winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *)winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(
                                                                                    &v23,
                                                                                    &v16);
  v8 = (_QWORD *)((char *)this + 80);
  if ( (winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *)((char *)this + 80) != v7 )
  {
    if ( *v8 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((char *)this + 80);
    v9 = *(_QWORD *)v7;
    *(_QWORD *)v7 = 0;
    *v8 = v9;
  }
  if ( v23 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v23);
  *((_DWORD *)this + 22) = 0;
  *((_DWORD *)this + 19) = 1;
  v13[0] = 0;
  v13[1] = 2;
  pvContextBuffer = 0;
  pOutput.ulVersion = 0;
  pOutput.cBuffers = 1;
  pOutput.pBuffers = (PSecBuffer)v13;
  pfContextAttr = 0;
  v10 = InitializeSecurityContextW(
          (PCredHandle)((char *)this + 104),
          0,
          0,
          0x819Cu,
          0,
          0,
          0,
          0,
          (PCtxtHandle)((char *)this + 120),
          &pOutput,
          &pfContextAttr,
          0);
  v16 = v13;
  LOBYTE(v17) = 1;
  LOBYTE(v11) = v10 != 590610;
  winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(
    (winrt::Windows::Internal::Eap::Utility::implementation *)v10,
    v11,
    v12);
  v20 = 0;
  v21 = 0;
  if ( pvContextBuffer && v13[0] )
  {
    std::vector<unsigned char>::vector<unsigned char>(&v18, pvContextBuffer, (char *)pvContextBuffer + v13[0]);
    v20 = v18;
    v18 = 0u;
    v21 = v19;
    v19 = 0;
    std::vector<unsigned char>::~vector<unsigned char>((char **)&v18);
  }
  winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TlsHandshakeDataGenerated(this, &v20);
  std::vector<unsigned char>::~vector<unsigned char>((char **)&v20);
  if ( pvContextBuffer )
    FreeContextBuffer(pvContextBuffer);
}

```

## disassembly

```asm
0x1800188f0  mov     [rsp-8+arg_8], rbx
0x1800188f5  push    rbp
0x1800188f6  push    rsi
0x1800188f7  push    rdi
0x1800188f8  push    r14
0x1800188fa  push    r15
0x1800188fc  lea     rbp, [rsp-37h]
0x180018901  sub     rsp, 0C0h
0x180018908  mov     r14, rdx
0x18001890b  mov     rsi, rcx
0x18001890e  inc     dword ptr [rcx+0B8h]
0x180018914  xor     r15d, r15d
0x180018917  cmp     [rcx+100h], r15d
0x18001891e  jz      short loc_180018932
0x180018920  mov     rcx, rdx
0x180018923  call    ?SessionResumptionState@?$consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions@UIEapTlsHandshakeOptions@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::SessionResumptionState(void)
0x180018928  test    eax, eax
0x18001892a  jz      short loc_180018932
0x18001892c  cmp     dword ptr [rsi+4Ch], 3
0x180018930  jz      short loc_18001895F
0x180018932  mov     rcx, r14
0x180018935  call    ?CertificateContext@?$consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions@UIEapTlsHandshakeOptions@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::CertificateContext(void)
0x18001893a  mov     rdi, rax
0x18001893d  mov     rcx, r14
0x180018940  call    ?CryptographicRestrictions@?$consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions@UIEapTlsHandshakeOptions@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::CryptographicRestrictions(void)
0x180018945  mov     ebx, eax
0x180018947  mov     rcx, r14
0x18001894a  call    ?DisabledTlsVersions@?$consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions@UIEapTlsHandshakeOptions@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::DisabledTlsVersions(void)
0x18001894f  mov     r9, rdi
0x180018952  mov     r8d, ebx
0x180018955  mov     edx, eax
0x180018957  mov     rcx, rsi
0x18001895a  call    ?InitializeCredentialsHandle@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXW4EapTlsVersionFlags@34567@W4EapTlsCryptographicRestrictions@34567@PEBU_CERT_CONTEXT@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::InitializeCredentialsHandle(winrt::Windows::Internal::Eap::Utility::EapTlsVersionFlags,winrt::Windows::Internal::Eap::Utility::EapTlsCryptographicRestrictions,_CERT_CONTEXT const *)
0x18001895f  mov     rcx, r14
0x180018962  call    ?SessionResumptionState@?$consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions@UIEapTlsHandshakeOptions@Utility@Eap@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Eap_Utility_IEapTlsHandshakeOptions<winrt::Windows::Internal::Eap::Utility::IEapTlsHandshakeOptions>::SessionResumptionState(void)
0x180018967  mov     [rsi+100h], eax
0x18001896d  lea     r14, [rsi+78h]
0x180018971  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018975  cmp     [r14], rbx
0x180018978  jz      short loc_180018996
0x18001897a  cmp     [rsi+80h], rbx
0x180018981  jz      short loc_180018996
0x180018983  mov     rcx, r14; phContext
0x180018986  call    cs:__imp_DeleteSecurityContext
0x18001898c  mov     [rsi+80h], rbx
0x180018993  mov     [r14], rbx
0x180018996  mov     [rbp+57h+var_60], r15
0x18001899a  mov     [rbp+57h+var_58], r15
0x18001899e  lea     rdx, [rbp+57h+var_60]
0x1800189a2  lea     rcx, [rbp+57h+arg_10]
0x1800189a6  call    ?CreateIBufferOverCallerManagedBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(gsl::span<uchar,-1>)
0x1800189ab  mov     rdi, rax
0x1800189ae  lea     rbx, [rsi+50h]
0x1800189b2  cmp     rbx, rax
0x1800189b5  jz      short loc_1800189CD
0x1800189b7  cmp     [rbx], r15
0x1800189ba  jz      short loc_1800189C4
0x1800189bc  mov     rcx, rbx
0x1800189bf  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800189c4  mov     rcx, [rdi]
0x1800189c7  mov     [rdi], r15
0x1800189ca  mov     [rbx], rcx
0x1800189cd  cmp     [rbp+57h+arg_10], r15
0x1800189d1  jz      short loc_1800189DC
0x1800189d3  lea     rcx, [rbp+57h+arg_10]
0x1800189d7  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800189dc  mov     [rsi+58h], r15d
0x1800189e0  mov     dword ptr [rsi+4Ch], 1
0x1800189e7  mov     [rbp+57h+var_80], r15d
0x1800189eb  mov     [rbp+57h+var_7C], 2
0x1800189f2  mov     [rbp+57h+pvContextBuffer], r15
0x1800189f6  mov     [rbp+57h+var_70.ulVersion], r15d
0x1800189fa  mov     [rbp+57h+var_70.cBuffers], 1
0x180018a01  lea     rax, [rbp+57h+var_80]
0x180018a05  mov     [rbp+57h+var_70.pBuffers], rax
0x180018a09  mov     [rbp+57h+arg_0], r15d
0x180018a0d  lea     rcx, [rsi+68h]; phCredential
0x180018a11  mov     [rsp+0E0h+ptsExpiry], r15; ptsExpiry
0x180018a16  lea     rax, [rbp+57h+arg_0]
0x180018a1a  mov     [rsp+0E0h+pfContextAttr], rax; pfContextAttr
0x180018a1f  lea     rax, [rbp+57h+var_70]
0x180018a23  mov     [rsp+0E0h+pOutput], rax; pOutput
0x180018a28  mov     [rsp+0E0h+phNewContext], r14; phNewContext
0x180018a2d  mov     [rsp+0E0h+Reserved2], r15d; Reserved2
0x180018a32  mov     [rsp+0E0h+pInput], r15; pInput
0x180018a37  mov     [rsp+0E0h+TargetDataRep], r15d; TargetDataRep
0x180018a3c  mov     [rsp+0E0h+Reserved1], r15d; Reserved1
0x180018a41  mov     r9d, 819Ch; fContextReq
0x180018a47  xor     r8d, r8d; pszTargetName
0x180018a4a  xor     edx, edx; phContext
0x180018a4c  call    cs:__imp_InitializeSecurityContextW
0x180018a52  lea     rcx, [rbp+57h+var_80]
0x180018a56  mov     [rbp+57h+var_60], rcx
0x180018a5a  mov     byte ptr [rbp+57h+var_58], 1
0x180018a5e  cmp     eax, 90312h
0x180018a63  setnz   dl; int
0x180018a66  mov     ecx, eax; this
0x180018a68  call    ?ThrowSecurityStatusIf@implementation@Utility@Eap@Internal@Windows@winrt@@YAXJ_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::ThrowSecurityStatusIf(long,bool)
0x180018a6d  xorps   xmm0, xmm0
0x180018a70  movdqu  [rbp+57h+var_38], xmm0
0x180018a75  mov     [rbp+57h+var_28], r15
0x180018a79  mov     rdx, [rbp+57h+pvContextBuffer]
0x180018a7d  test    rdx, rdx
0x180018a80  jz      short loc_180018AC3
0x180018a82  mov     eax, [rbp+57h+var_80]
0x180018a85  test    eax, eax
0x180018a87  jz      short loc_180018AC3
0x180018a89  lea     r8, [rdx+rax]
0x180018a8d  lea     rcx, [rbp+57h+var_50]
0x180018a91  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x180018a96  mov     rax, qword ptr [rbp+57h+var_50]
0x180018a9a  mov     qword ptr [rbp+57h+var_38], rax
0x180018a9e  mov     qword ptr [rbp+57h+var_50], r15
0x180018aa2  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180018aa6  mov     qword ptr [rbp+57h+var_38+8], rax
0x180018aaa  mov     qword ptr [rbp+57h+var_50+8], r15
0x180018aae  mov     rax, [rbp+57h+var_40]
0x180018ab2  mov     [rbp+57h+var_28], rax
0x180018ab6  mov     [rbp+57h+var_40], r15
0x180018aba  lea     rcx, [rbp+57h+var_50]
0x180018abe  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180018ac3  lea     rdx, [rbp+57h+var_38]
0x180018ac7  mov     rcx, rsi
0x180018aca  call    ?TlsHandshakeDataGenerated@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TlsHandshakeDataGenerated(std::vector<uchar> const &)
0x180018acf  nop
0x180018ad0  lea     rcx, [rbp+57h+var_38]
0x180018ad4  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180018ad9  nop
0x180018ada  mov     rcx, [rbp+57h+pvContextBuffer]; pvContextBuffer
0x180018ade  test    rcx, rcx
0x180018ae1  jz      short loc_180018AE9
0x180018ae3  call    cs:__imp_FreeContextBuffer
0x180018ae9  mov     rbx, [rsp+0E0h+arg_8]
0x180018af1  add     rsp, 0C0h
0x180018af8  pop     r15
0x180018afa  pop     r14
0x180018afc  pop     rdi
0x180018afd  pop     rsi
0x180018afe  pop     rbp
0x180018aff  retn
```
