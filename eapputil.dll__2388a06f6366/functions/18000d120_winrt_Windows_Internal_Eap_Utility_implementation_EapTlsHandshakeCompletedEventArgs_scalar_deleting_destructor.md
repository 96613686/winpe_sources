# winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs::`scalar deleting destructor'(uint)

- ea: `0x18000d120`
- end: `0x18000d167`
- name: `??_GEapTlsHandshakeCompletedEventArgs@implementation@Utility@Eap@Internal@Windows@winrt@@UEAAPEAXI@Z`
- size: `71`
- prototype: `winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs *__fastcall(winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800025a0`
- `0x1800083ec`
- `0x18000d038`
- `0x18000d120`

## pseudocode

```c
winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs *__fastcall winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs::`scalar deleting destructor'(
        winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeCompletedEventArgs *this,
        char a2)
{
  _QWORD *v4; // rcx

  v4 = (_QWORD *)((char *)this + 32);
  if ( *v4 )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(v4);
  winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>((__int64)this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000d120  mov     [rsp+arg_0], rbx
0x18000d125  push    rdi
0x18000d126  sub     rsp, 20h
0x18000d12a  mov     rbx, rcx
0x18000d12d  mov     edi, edx
0x18000d12f  add     rcx, 20h ; ' '
0x18000d133  cmp     qword ptr [rcx], 0
0x18000d137  jz      short loc_18000D13E
0x18000d139  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000d13e  mov     rcx, rbx
0x18000d141  call    ??1?$root_implements@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@U?$IVector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@U?$IIterable@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@5673@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>::~root_implements<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::Internal::Eap::Utility::EapAttribute>>(void)
0x18000d146  test    dil, 1
0x18000d14a  jz      short loc_18000D159
0x18000d14c  mov     edx, 28h ; '('; unsigned __int64
0x18000d151  mov     rcx, rbx; void *
0x18000d154  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d159  mov     rax, rbx
0x18000d15c  mov     rbx, [rsp+28h+arg_0]
0x18000d161  add     rsp, 20h
0x18000d165  pop     rdi
0x18000d166  retn
```
