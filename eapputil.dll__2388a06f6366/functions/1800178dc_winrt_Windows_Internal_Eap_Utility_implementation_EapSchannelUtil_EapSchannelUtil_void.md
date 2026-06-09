# winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::~EapSchannelUtil(void)

- ea: `0x1800178dc`
- end: `0x180017a20`
- name: `??1EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@UEAA@XZ`
- size: `324`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800181f0`

## callees

- `0x180002cb7`
- `0x180002ce7`
- `0x1800083ec`
- `0x18000d038`
- `0x180011030`
- `0x1800178dc`
- `0x18001cd90`
- `0x18001dc94`
- `0x180023af4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017a19`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017a19`
- `SspiCli!DeleteSecurityContext` at `0x180017934`
- `SspiCli!DeleteSecurityContext` at `0x180017934`
- `SspiCli!FreeCredentialsHandle` at `0x180017949`
- `SspiCli!FreeCredentialsHandle` at `0x180017949`
- `CRYPT32!CertFreeCertificateContext` at `0x1800179cb`
- `CRYPT32!CertFreeCertificateContext` at `0x1800179cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::~EapSchannelUtil(
        winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *this)
{
  volatile signed __int32 *v2; // rsi
  int v3; // edi
  HANDLE ProcessHeap; // rax
  const CERT_CONTEXT *v5; // rcx

  *(_QWORD *)this = &winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::`vftable';
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl'::`2'::impl) )
  {
    winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReleaseSecurityHandles(this);
    winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::LogSchannelStatistics((winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil *)((char *)this + 184));
  }
  else
  {
    if ( *((_QWORD *)this + 15) != -1 && *((_QWORD *)this + 16) != -1 )
      DeleteSecurityContext((PCtxtHandle)((char *)this + 120));
    if ( *((_QWORD *)this + 13) != -1 && *((_QWORD *)this + 14) != -1 )
      FreeCredentialsHandle((PCredHandle)((char *)this + 104));
  }
  if ( *((_QWORD *)this + 31) )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((char *)this + 248);
  if ( *((_QWORD *)this + 30) )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((char *)this + 240);
  if ( *((_QWORD *)this + 29) )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((char *)this + 232);
  if ( *((_BYTE *)this + 224) )
  {
    v2 = (volatile signed __int32 *)*((_QWORD *)this + 27);
    if ( v2 )
    {
      v3 = _InterlockedDecrement(v2 + 6);
      if ( v3 )
      {
        if ( v3 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v2);
      }
      *((_QWORD *)this + 27) = 0;
    }
  }
  v5 = (const CERT_CONTEXT *)*((_QWORD *)this + 12);
  if ( v5 )
    CertFreeCertificateContext(v5);
  if ( *((_QWORD *)this + 10) )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((char *)this + 80);
  if ( *((_QWORD *)this + 6) )
    winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref();
  if ( *((_QWORD *)this + 3) )
    winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref();
  winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>((__int64)this);
}

```

## disassembly

```asm
0x1800178dc  mov     [rsp+arg_0], rbx
0x1800178e1  mov     [rsp+arg_8], rsi
0x1800178e6  push    rdi
0x1800178e7  sub     rsp, 20h
0x1800178eb  mov     rbx, rcx
0x1800178ee  lea     rax, ??_7EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@6B@; const winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::`vftable'
0x1800178f5  mov     [rcx], rax
0x1800178f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EapServerTls13@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13> `wil::Feature<__WilFeatureTraits_Feature_EapServerTls13>::GetImpl(void)'::`2'::impl
0x1800178ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EapServerTls13@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EapServerTls13>::__private_IsEnabled(void)
0x180017904  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017908  test    al, al
0x18001790a  jz      short loc_180017922
0x18001790c  mov     rcx, rbx; this
0x18001790f  call    ?ReleaseSecurityHandles@EapSchannelUtil@implementation@Utility@Eap@Internal@Windows@winrt@@AEAAXXZ; winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelUtil::ReleaseSecurityHandles(void)
0x180017914  lea     rcx, [rbx+0B8h]; struct winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelStatistics *
0x18001791b  call    ?LogSchannelStatistics@EapPrivateUtilTelemetry@implementation@Utility@Eap@Internal@Windows@winrt@@SAXAEBUEapSchannelStatistics@234567@@Z; winrt::Windows::Internal::Eap::Utility::implementation::EapPrivateUtilTelemetry::LogSchannelStatistics(winrt::Windows::Internal::Eap::Utility::implementation::EapSchannelStatistics const &)
0x180017920  jmp     short loc_18001794F
0x180017922  lea     rcx, [rbx+78h]; phContext
0x180017926  cmp     [rcx], rdi
0x180017929  jz      short loc_18001793A
0x18001792b  cmp     [rbx+80h], rdi
0x180017932  jz      short loc_18001793A
0x180017934  call    cs:__imp_DeleteSecurityContext
0x18001793a  lea     rcx, [rbx+68h]; phCredential
0x18001793e  cmp     [rcx], rdi
0x180017941  jz      short loc_18001794F
0x180017943  cmp     [rbx+70h], rdi
0x180017947  jz      short loc_18001794F
0x180017949  call    cs:__imp_FreeCredentialsHandle
0x18001794f  lea     rcx, [rbx+0F8h]
0x180017956  cmp     qword ptr [rcx], 0
0x18001795a  jz      short loc_180017961
0x18001795c  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180017961  lea     rcx, [rbx+0F0h]
0x180017968  cmp     qword ptr [rcx], 0
0x18001796c  jz      short loc_180017973
0x18001796e  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180017973  lea     rcx, [rbx+0E8h]
0x18001797a  cmp     qword ptr [rcx], 0
0x18001797e  jz      short loc_180017985
0x180017980  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x180017985  cmp     byte ptr [rbx+0E0h], 0
0x18001798c  jz      short loc_1800179C2
0x18001798e  mov     rsi, [rbx+0D8h]
0x180017995  test    rsi, rsi
0x180017998  jz      short loc_1800179C2
0x18001799a  lock xadd [rsi+18h], edi
0x18001799f  sub     edi, 1
0x1800179a2  jnz     short loc_180017A15
0x1800179a4  nop
0x1800179a5  call    WINRT_IMPL_GetProcessHeap
0x1800179aa  mov     rcx, rax; hHeap
0x1800179ad  mov     r8, rsi; lpMem
0x1800179b0  xor     edx, edx; dwFlags
0x1800179b2  call    WINRT_IMPL_HeapFree
0x1800179b7  mov     qword ptr [rbx+0D8h], 0
0x1800179c2  mov     rcx, [rbx+60h]; pCertContext
0x1800179c6  test    rcx, rcx
0x1800179c9  jz      short loc_1800179D1
0x1800179cb  call    cs:__imp_CertFreeCertificateContext
0x1800179d1  lea     rcx, [rbx+50h]
0x1800179d5  cmp     qword ptr [rcx], 0
0x1800179d9  jz      short loc_1800179E0
0x1800179db  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x1800179e0  lea     rcx, [rbx+30h]
0x1800179e4  cmp     qword ptr [rcx], 0
0x1800179e8  jz      short loc_1800179EF
0x1800179ea  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x1800179ef  lea     rcx, [rbx+18h]
0x1800179f3  cmp     qword ptr [rcx], 0
0x1800179f7  jz      short loc_1800179FE
0x1800179f9  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x1800179fe  mov     rcx, rbx
0x180017a01  mov     rbx, [rsp+28h+arg_0]
0x180017a06  mov     rsi, [rsp+28h+arg_8]
0x180017a0b  add     rsp, 20h
0x180017a0f  pop     rdi
0x180017a10  jmp     ??1?$root_implements@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@U?$IIterable@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(void)
0x180017a15  test    edi, edi
0x180017a17  jns     short loc_1800179B7
0x180017a19  call    cs:__imp_abort
```
