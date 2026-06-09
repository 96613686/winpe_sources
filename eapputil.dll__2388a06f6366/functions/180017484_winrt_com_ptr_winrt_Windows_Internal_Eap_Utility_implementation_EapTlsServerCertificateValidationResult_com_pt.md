# winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult>::~com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult>(void)

- ea: `0x180017484`
- end: `0x180017498`
- name: `??1?$com_ptr@UEapTlsServerCertificateValidationResult@implementation@Utility@Eap@Internal@Windows@winrt@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180031fc7`
- `0x180032240`
- `0x180032509`

## callees

- `0x18001371c`
- `0x180017484`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult>::~com_ptr<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsServerCertificateValidationResult>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x180017484  sub     rsp, 28h
0x180017488  cmp     qword ptr [rcx], 0
0x18001748c  jz      short loc_180017493
0x18001748e  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180017493  add     rsp, 28h
0x180017497  retn
```
