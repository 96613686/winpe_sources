# winrt::Windows::Internal::Eap::Utility::implementation::inproc_error_propagating_event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::EapMethodRunnerAuthenticationCompletedEventArgs>>::~inproc_error_propagating_event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::EapMethodRunnerAuthenticationCompletedEventArgs>>(void)

- ea: `0x18000ead4`
- end: `0x18000eae8`
- name: `??1?$inproc_error_propagating_event@U?$TypedEventHandler@UEapMethodRunner@Utility@Eap@Internal@Windows@winrt@@UEapMethodRunnerAuthenticationCompletedEventArgs@23456@@Foundation@Windows@winrt@@@implementation@Utility@Eap@Internal@Windows@winrt@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003139b`
- `0x1800313b1`
- `0x1800313c7`
- `0x180031579`
- `0x18003159d`
- `0x1800315f9`
- `0x180031871`
- `0x1800323cf`

## callees

- `0x18000ead4`
- `0x180011030`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Internal::Eap::Utility::implementation::inproc_error_propagating_event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::EapMethodRunnerAuthenticationCompletedEventArgs>>::~inproc_error_propagating_event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapMethodRunner,winrt::Windows::Internal::Eap::Utility::EapMethodRunnerAuthenticationCompletedEventArgs>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref();
  return result;
}

```

## disassembly

```asm
0x18000ead4  sub     rsp, 28h
0x18000ead8  cmp     qword ptr [rcx], 0
0x18000eadc  jz      short loc_18000EAE3
0x18000eade  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UEapServerSchannelUtil@Utility@Eap@Internal@Windows@winrt@@UEapTlsHandshakeCompletedEventArgs@23456@@Foundation@Windows@winrt@@@impl@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Internal::Eap::Utility::EapServerSchannelUtil,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeCompletedEventArgs>>>::unconditional_release_ref(void)
0x18000eae3  add     rsp, 28h
0x18000eae7  retn
```
