# winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::~EapMethodRunnerAuthenticationCompletedEventArgs(void)

- ea: `0x18000ec20`
- end: `0x18000ec90`
- name: `??1EapMethodRunnerAuthenticationCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@UEAA@XZ`
- size: `112`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ecf0`

## callees

- `0x1800083ec`
- `0x18000d038`
- `0x18000ec20`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs::~EapMethodRunnerAuthenticationCompletedEventArgs(
        winrt::Windows::Internal::Eap::Utility::implementation::EapMethodRunnerAuthenticationCompletedEventArgs *this)
{
  _QWORD *v2; // rcx

  v2 = (_QWORD *)((char *)this + 112);
  if ( *v2 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v2);
  if ( *((_QWORD *)this + 12) )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((char *)this + 96);
  if ( *((_QWORD *)this + 10) )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((char *)this + 80);
  if ( *((_QWORD *)this + 8) )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((char *)this + 64);
  if ( *((_QWORD *)this + 6) )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((char *)this + 48);
  if ( *((_QWORD *)this + 4) )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref((char *)this + 32);
  winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>((__int64)this);
}

```

## disassembly

```asm
0x18000ec20  push    rbx
0x18000ec22  sub     rsp, 20h
0x18000ec26  mov     rbx, rcx
0x18000ec29  add     rcx, 70h ; 'p'
0x18000ec2d  cmp     qword ptr [rcx], 0
0x18000ec31  jz      short loc_18000EC38
0x18000ec33  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000ec38  lea     rcx, [rbx+60h]
0x18000ec3c  cmp     qword ptr [rcx], 0
0x18000ec40  jz      short loc_18000EC47
0x18000ec42  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000ec47  lea     rcx, [rbx+50h]
0x18000ec4b  cmp     qword ptr [rcx], 0
0x18000ec4f  jz      short loc_18000EC56
0x18000ec51  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000ec56  lea     rcx, [rbx+40h]
0x18000ec5a  cmp     qword ptr [rcx], 0
0x18000ec5e  jz      short loc_18000EC65
0x18000ec60  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000ec65  lea     rcx, [rbx+30h]
0x18000ec69  cmp     qword ptr [rcx], 0
0x18000ec6d  jz      short loc_18000EC74
0x18000ec6f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000ec74  lea     rcx, [rbx+20h]
0x18000ec78  cmp     qword ptr [rcx], 0
0x18000ec7c  jz      short loc_18000EC83
0x18000ec7e  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000ec83  mov     rcx, rbx
0x18000ec86  add     rsp, 20h
0x18000ec8a  pop     rbx
0x18000ec8b  jmp     ??1?$root_implements@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@U?$IIterable@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(void)
```
