# winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::TlsHandshakeCompleted(winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus const &)

- ea: `0x1800294d0`
- end: `0x1800296dd`
- name: `?TlsHandshakeCompleted@EapServerSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXAEBW4EapTlsHandshakeStatus@34567@@Z`
- size: `525`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil *__hidden this, const enum winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026844`

## callees

- `0x180002cf3`
- `0x180002cff`
- `0x180004380`
- `0x1800083ec`
- `0x180010168`
- `0x180010e04`
- `0x180011030`
- `0x18001636c`
- `0x1800164e8`
- `0x18001cd90`
- `0x18001e4c8`
- `0x1800294d0`
- `0x18002e2c8`
- `0x180033010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil::TlsHandshakeCompleted(
        winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil *this,
        const enum winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus *a2)
{
  volatile signed __int32 *v4; // rsi
  _DWORD *v5; // r15
  __int64 *v6; // rax
  unsigned int *v7; // rbx
  volatile signed __int32 *v8; // rax
  _QWORD *v9; // r14
  __int64 v10; // rsi
  signed int v11; // eax
  __int64 v12; // r8
  const wchar_t *v13; // r9
  unsigned int v14; // eax
  int v15; // edx
  char *v16; // [rsp+28h] [rbp-58h]
  __int64 v17; // [rsp+40h] [rbp-40h] BYREF
  unsigned int *v18; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v19[2]; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v20; // [rsp+60h] [rbp-20h] BYREF
  __int128 v21; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  __int64 v23; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+58h] BYREF

  v4 = 0;
  v19[0] = 0;
  v19[1] = 0;
  winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(&v24, (int *)v19);
  v5 = (_DWORD *)((char *)this + 92);
  v6 = winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation,winrt::Windows::Storage::Streams::IBuffer &,_SecPkgContext_StreamSizes &,unsigned long &>(
         &v17,
         &v24,
         (_DWORD *)this + 23,
         (int *)this + 16);
  winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs,enum winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus &,winrt::Windows::Internal::Eap::Utility::EapTlsConnectedPeerInformation>(
    &v23,
    (int *)a2,
    v6);
  if ( v17 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v17);
  v7 = 0;
  v18 = 0;
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)this + 27);
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 26);
  if ( v8 )
  {
    v7 = (unsigned int *)*((_QWORD *)this + 26);
    v18 = v7;
    _InterlockedIncrement(v8);
    v4 = v8;
  }
  ReleaseSRWLockExclusive_0((PSRWLOCK)this + 27);
  if ( v4 )
  {
    v9 = v4 + 2;
    v10 = (__int64)&v4[2 * *((unsigned int *)v4 + 1) + 2];
    if ( v9 != (_QWORD *)v10 )
    {
      do
      {
        v19[0] = (char *)this + 16;
        v20 = 0;
        v21 = 0;
        v11 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64))(*(_QWORD *)*v9 + 24LL))(*v9, (char *)this + 16, v23);
        if ( v11 < 0 )
          winrt::throw_hresult(v11, &v20, v12);
        ++v9;
      }
      while ( v9 != (_QWORD *)v10 );
      v5 = (_DWORD *)((char *)this + 92);
    }
  }
  if ( v7 )
    winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(&v18);
  switch ( *((_DWORD *)this + 19) )
  {
    case 0x8004:
      v13 = L"SHA1";
      break;
    case 0x800C:
      v13 = L"SHA256";
      break;
    case 0x800D:
      v13 = L"SHA384";
      break;
    case 0x800E:
      v13 = L"SHA512";
      break;
    default:
      v14 = wil::verify_hresult<long>(0x80004001);
      LODWORD(v16) = v15;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x44D,
        (unsigned int)"onecoreuap\\net\\eaphost\\eapputil\\lib\\eapserverschannelutil.cpp",
        (const char *)v14,
        (int)"aiHash: %d",
        v16);
  }
  winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::TlsHandshakeFinished(
    *((unsigned int *)this + 6),
    *(unsigned int *)a2,
    *((unsigned int *)this + 16),
    v13,
    *v5,
    *((_DWORD *)this + 24),
    *((_DWORD *)this + 25),
    0);
  *((_DWORD *)this + 7) = 2;
  ++*((_DWORD *)this + 39);
  winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::LogSchannelStatistics((winrt::Windows::Internal::Eap::Utility::implementation::EapServerSchannelUtil *)((char *)this + 152));
  if ( v23 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v23);
  if ( v24 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v24);
}

```

## disassembly

```asm
0x1800294d0  mov     [rsp-38h+arg_0], rbx
0x1800294d5  push    rbp
0x1800294d6  push    rsi
0x1800294d7  push    rdi
0x1800294d8  push    r12
0x1800294da  push    r13
0x1800294dc  push    r14
0x1800294de  push    r15
0x1800294e0  mov     rbp, rsp
0x1800294e3  sub     rsp, 80h
0x1800294ea  mov     r12, rdx
0x1800294ed  mov     rdi, rcx
0x1800294f0  xor     esi, esi
0x1800294f2  mov     [rbp+var_30], rsi
0x1800294f6  mov     [rbp+var_28], rsi
0x1800294fa  lea     rdx, [rbp+var_30]
0x1800294fe  lea     rcx, [rbp+arg_18]
0x180029502  call    ?CreateIBufferOverCallerManagedBytes@implementation@Utility@Eap@Internal@Windows@winrt@@YA?AUIBuffer@Streams@Storage@56@V?$span@E$0?0@gsl@@@Z; winrt::Windows::Internal::Eap::Utility::implementation::CreateIBufferOverCallerManagedBytes(gsl::span<uchar,-1>)
0x180029507  nop
0x180029508  lea     r15, [rdi+5Ch]
0x18002950c  lea     r9, [rdi+40h]
0x180029510  mov     r8, r15
0x180029513  lea     rdx, [rbp+arg_18]
0x180029517  lea     rcx, [rbp+var_40]
0x18002951b  call    ??$make@UEapTlsConnectedPeerInformation@implementation@Utility@Eap@Internal@Windows@winrt@@AEAUIBuffer@Streams@Storage@67@AEAU_SecPkgContext_StreamSizes@@AEAK@winrt@@YA?A_PAEAUIBuffer@Streams@Storage@Windows@0@AEAU_SecPkgContext_StreamSizes@@AEAK@Z
0x180029520  nop
0x180029521  mov     r8, rax
0x180029524  mov     rdx, r12
0x180029527  lea     rcx, [rbp+arg_10]
0x18002952b  call    ??$make@UEapTlsHandshakeCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAW4EapTlsHandshakeStatus@34567@UEapTlsConnectedPeerInformation@34567@@winrt@@YA?A_PAEAW4EapTlsHandshakeStatus@Utility@Eap@Internal@Windows@0@$$QEAUEapTlsConnectedPeerInformation@23450@@Z
0x180029530  nop
0x180029531  cmp     [rbp+var_40], rsi
0x180029535  jz      short loc_180029540
0x180029537  lea     rcx, [rbp+var_40]
0x18002953b  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180029540  mov     rbx, rsi
0x180029543  mov     [rbp+var_38], rbx
0x180029547  lea     r14, [rdi+0D8h]
0x18002954e  mov     rcx, r14; SRWLock
0x180029551  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180029556  mov     rax, [rdi+0D0h]
0x18002955d  test    rax, rax
0x180029560  jz      short loc_18002956F
0x180029562  mov     rbx, rax
0x180029565  mov     [rbp+var_38], rax
0x180029569  lock inc dword ptr [rax]
0x18002956c  mov     rsi, rax
0x18002956f  mov     rcx, r14; SRWLock
0x180029572  call    ReleaseSRWLockExclusive_0
0x180029577  test    rsi, rsi
0x18002957a  jz      short loc_1800295D2
0x18002957c  lea     r14, [rsi+8]
0x180029580  mov     eax, [rsi+4]
0x180029583  lea     rsi, [rsi+rax*8]
0x180029587  add     rsi, 8
0x18002958b  cmp     r14, rsi
0x18002958e  jz      short loc_1800295D2
0x180029590  lea     r15, [rdi+10h]
0x180029594  mov     [rbp+var_30], r15
0x180029598  mov     [rbp+var_20], 0
0x18002959f  xorps   xmm0, xmm0
0x1800295a2  movdqu  [rbp+var_18], xmm0
0x1800295a7  mov     rcx, [r14]
0x1800295aa  mov     rax, [rcx]
0x1800295ad  mov     r8, [rbp+arg_10]
0x1800295b1  mov     rdx, r15
0x1800295b4  mov     rax, [rax+18h]
0x1800295b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295bd  test    eax, eax
0x1800295bf  js      loc_18002969E
0x1800295c5  add     r14, 8
0x1800295c9  cmp     r14, rsi
0x1800295cc  jnz     short loc_180029594
0x1800295ce  lea     r15, [rdi+5Ch]
0x1800295d2  xor     esi, esi
0x1800295d4  test    rbx, rbx
0x1800295d7  jz      short loc_1800295E2
0x1800295d9  lea     rcx, [rbp+var_38]
0x1800295dd  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x1800295e2  mov     edx, [rdi+4Ch]
0x1800295e5  mov     eax, edx
0x1800295e7  sub     eax, 8004h
0x1800295ec  jz      short loc_18002961C
0x1800295ee  sub     eax, 8
0x1800295f1  jz      short loc_180029613
0x1800295f3  sub     eax, 1
0x1800295f6  jz      short loc_18002960A
0x1800295f8  cmp     eax, 1
0x1800295fb  jnz     loc_1800296AA
0x180029601  lea     r9, aSha512; "SHA512"
0x180029608  jmp     short loc_180029623
0x18002960a  lea     r9, aSha384; "SHA384"
0x180029611  jmp     short loc_180029623
0x180029613  lea     r9, aSha256; "SHA256"
0x18002961a  jmp     short loc_180029623
0x18002961c  lea     r9, aSha1; "SHA1"
0x180029623  mov     [rsp+80h+var_48], sil
0x180029628  mov     eax, [rdi+64h]
0x18002962b  mov     [rsp+80h+var_50], eax
0x18002962f  mov     eax, [rdi+60h]
0x180029632  mov     dword ptr [rsp+80h+var_58], eax
0x180029636  mov     eax, [r15]
0x180029639  mov     [rsp+80h+var_60], eax
0x18002963d  mov     r8d, [rdi+40h]
0x180029641  mov     edx, [r12]
0x180029645  mov     ecx, [rdi+18h]
0x180029648  call    ?TlsHandshakeFinished@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAXW4EapMethodType@34567@W4EapTlsHandshakeStatus@34567@KQEBGKKK_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::TlsHandshakeFinished(winrt::Windows::Internal::Eap::Utility::EapMethodType,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus,ulong,ushort const * const,ulong,ulong,ulong,bool)
0x18002964d  mov     dword ptr [rdi+1Ch], 2
0x180029654  lea     rcx, [rdi+98h]; struct winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelStatistics *
0x18002965b  inc     dword ptr [rcx+4]
0x18002965e  call    ?LogSchannelStatistics@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAXAEBUEapSchannelStatistics@234567@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::LogSchannelStatistics(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelStatistics const &)
0x180029663  nop
0x180029664  cmp     [rbp+arg_10], rsi
0x180029668  jz      short loc_180029674
0x18002966a  lea     rcx, [rbp+arg_10]
0x18002966e  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180029673  nop
0x180029674  cmp     [rbp+arg_18], rsi
0x180029678  jz      short loc_180029683
0x18002967a  lea     rcx, [rbp+arg_18]
0x18002967e  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180029683  mov     rbx, [rsp+80h+arg_0]
0x18002968b  add     rsp, 80h
0x180029692  pop     r15
0x180029694  pop     r14
0x180029696  pop     r13
0x180029698  pop     r12
0x18002969a  pop     rdi
0x18002969b  pop     rsi
0x18002969c  pop     rbp
0x18002969d  retn
0x18002969e  lea     rdx, [rbp+var_20]
0x1800296a2  mov     ecx, eax
0x1800296a4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800296aa  mov     ecx, 80004001h
0x1800296af  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800296b4  mov     r9d, eax; char *
0x1800296b7  mov     rcx, [rbp+38h]; this
0x1800296bb  mov     dword ptr [rsp+80h+var_58], edx; char *
0x1800296bf  lea     rax, aAihashD; "aiHash: %d"
0x1800296c6  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800296cb  lea     r8, aOnecoreuapNetE_1; "onecoreuap\\net\\eaphost\\eapputil\\lib"...
0x1800296d2  mov     edx, 44Dh; void *
0x1800296d7  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
