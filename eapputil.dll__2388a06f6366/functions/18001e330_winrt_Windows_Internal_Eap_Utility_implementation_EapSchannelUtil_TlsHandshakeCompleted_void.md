# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TlsHandshakeCompleted(void)

- ea: `0x18001e330`
- end: `0x18001e426`
- name: `?TlsHandshakeCompleted@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXXZ`
- size: `246`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180019794`

## callees

- `0x1800083ec`
- `0x18001392c`
- `0x18001636c`
- `0x1800164e8`
- `0x18001b578`
- `0x18001cd3c`
- `0x18001cd90`
- `0x18001e330`
- `0x18001e4c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::TlsHandshakeCompleted(
        winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *this)
{
  unsigned int *v2; // r15
  int *v3; // rbp
  __int64 *v4; // rax
  bool v5; // bl
  int v6; // edi
  int v7; // esi
  int v8; // ebp
  const unsigned __int16 *AlgString; // rax
  bool v10; // [rsp+38h] [rbp-30h]
  __int64 v11; // [rsp+70h] [rbp+8h] BYREF
  __int64 v12; // [rsp+78h] [rbp+10h] BYREF

  v2 = (unsigned int *)((char *)this + 156);
  v3 = (int *)((char *)this + 136);
  v4 = winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsConnectedPeerInformation,winrt::Windows::Storage::Streams::IBuffer &,_SecPkgContext_StreamSizes &,unsigned long &>(
         &v12,
         (__int64 *)this + 10,
         (_DWORD *)this + 34,
         (int *)this + 39);
  winrt::make<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs,enum winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus &,winrt::Windows::Internal::Eap::Utility::EapTlsConnectedPeerInformation>(
    &v11,
    (int *)this + 22,
    v4);
  if ( v12 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v12);
  winrt::Windows::Internal::Eap::Utility::implementation::inproc_error_propagating_event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>>::operator()<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>(
    (char *)this + 48,
    this,
    &v11);
  v5 = (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size((char *)this + 80) != 0;
  v6 = *((_DWORD *)this + 36);
  v7 = *((_DWORD *)this + 35);
  v8 = *v3;
  AlgString = winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::GetAlgString(this);
  v10 = v5;
  winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::TlsHandshakeFinished(
    *((unsigned int *)this + 18),
    *((unsigned int *)this + 22),
    *v2,
    AlgString,
    v8,
    v7,
    v6,
    v10);
  ++*((_DWORD *)this + 47);
  winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::LogSchannelStatistics((winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *)((char *)this + 184));
  if ( v11 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v11);
}

```

## disassembly

```asm
0x18001e330  mov     [rsp+arg_10], rbx
0x18001e335  mov     [rsp+arg_18], rbp
0x18001e33a  push    rsi
0x18001e33b  push    rdi
0x18001e33c  push    r12
0x18001e33e  push    r14
0x18001e340  push    r15
0x18001e342  sub     rsp, 40h
0x18001e346  mov     r14, rcx
0x18001e349  lea     r15, [rcx+9Ch]
0x18001e350  lea     rbp, [rcx+88h]
0x18001e357  mov     r9, r15
0x18001e35a  mov     r8, rbp
0x18001e35d  lea     rdx, [rcx+50h]
0x18001e361  lea     rcx, [rsp+68h+arg_8]
0x18001e366  call    ??$make@UEapTlsConnectedPeerInformation@implementation@Utility@Eap@Internal@Windows@winrt@@AEAUIBuffer@Streams@Storage@67@AEAU_SecPkgContext_StreamSizes@@AEAK@winrt@@YA?A_PAEAUIBuffer@Streams@Storage@Windows@0@AEAU_SecPkgContext_StreamSizes@@AEAK@Z
0x18001e36b  nop
0x18001e36c  mov     r8, rax
0x18001e36f  lea     rdx, [r14+58h]
0x18001e373  lea     rcx, [rsp+68h+arg_0]
0x18001e378  call    ??$make@UEapTlsHandshakeCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@AEAW4EapTlsHandshakeStatus@34567@UEapTlsConnectedPeerInformation@34567@@winrt@@YA?A_PAEAW4EapTlsHandshakeStatus@Utility@Eap@Internal@Windows@0@$$QEAUEapTlsConnectedPeerInformation@23450@@Z
0x18001e37d  nop
0x18001e37e  cmp     [rsp+68h+arg_8], 0
0x18001e384  jz      short loc_18001E390
0x18001e386  lea     rcx, [rsp+68h+arg_8]
0x18001e38b  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001e390  lea     rcx, [r14+30h]
0x18001e394  lea     r8, [rsp+68h+arg_0]
0x18001e399  mov     rdx, r14
0x18001e39c  call    ??$?RUEapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UEapTlsDataGeneratedEventArgs@23456@@?$inproc_error_propagating_event@U?$TypedEventHandler@UEapSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsDataGeneratedEventArgs@23456@@Foundation@Windows@winrt@@@implementation@Utility@Eap@Internal@Windows@winrt@@QEAAXAEBUEapSchannelUtil@123456@AEBUEapTlsDataGeneratedEventArgs@23456@@Z; winrt::Windows::Internal::Eap::Utility::implementation::inproc_error_propagating_event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>>::operator()<winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs>(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil const &,winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs const &)
0x18001e3a1  lea     rcx, [r14+50h]
0x18001e3a5  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@winrt@@Uhstring@5@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::hstring>::Size(void)
0x18001e3aa  test    eax, eax
0x18001e3ac  setnz   bl
0x18001e3af  mov     edi, [r14+90h]
0x18001e3b6  mov     esi, [r14+8Ch]
0x18001e3bd  mov     ebp, [rbp+0]
0x18001e3c0  mov     rcx, r14; this
0x18001e3c3  call    ?GetAlgString@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEBAPEBGXZ; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::GetAlgString(void)
0x18001e3c8  mov     [rsp+68h+var_30], bl
0x18001e3cc  mov     [rsp+68h+var_38], edi
0x18001e3d0  mov     [rsp+68h+var_40], esi
0x18001e3d4  mov     [rsp+68h+var_48], ebp
0x18001e3d8  mov     r9, rax
0x18001e3db  mov     r8d, [r15]
0x18001e3de  mov     edx, [r14+58h]
0x18001e3e2  mov     ecx, [r14+48h]
0x18001e3e6  call    ?TlsHandshakeFinished@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAXW4EapMethodType@34567@W4EapTlsHandshakeStatus@34567@KQEBGKKK_N@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::TlsHandshakeFinished(winrt::Windows::Internal::Eap::Utility::EapMethodType,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeStatus,ulong,ushort const * const,ulong,ulong,ulong,bool)
0x18001e3eb  lea     rcx, [r14+0B8h]; struct winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelStatistics *
0x18001e3f2  inc     dword ptr [rcx+4]
0x18001e3f5  call    ?LogSchannelStatistics@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAXAEBUEapSchannelStatistics@234567@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::LogSchannelStatistics(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelStatistics const &)
0x18001e3fa  nop
0x18001e3fb  cmp     [rsp+68h+arg_0], 0
0x18001e401  jz      short loc_18001E40D
0x18001e403  lea     rcx, [rsp+68h+arg_0]
0x18001e408  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18001e40d  lea     r11, [rsp+68h+var_28]
0x18001e412  mov     rbx, [r11+40h]
0x18001e416  mov     rbp, [r11+48h]
0x18001e41a  mov     rsp, r11
0x18001e41d  pop     r15
0x18001e41f  pop     r14
0x18001e421  pop     r12
0x18001e423  pop     rdi
0x18001e424  pop     rsi
0x18001e425  retn
```
