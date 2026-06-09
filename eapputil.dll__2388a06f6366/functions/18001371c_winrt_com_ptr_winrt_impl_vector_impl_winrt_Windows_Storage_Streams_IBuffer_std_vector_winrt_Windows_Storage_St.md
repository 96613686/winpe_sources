# winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer,std::allocator<winrt::Windows::Storage::Streams::IBuffer>>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)

- ea: `0x18001371c`
- end: `0x18001372e`
- name: `?unconditional_release_ref@?$com_ptr@U?$vector_impl@UIBuffer@Streams@Storage@Windows@winrt@@V?$vector@UIBuffer@Streams@Storage@Windows@winrt@@V?$allocator@UIBuffer@Streams@Storage@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ`
- size: `18`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011840`
- `0x180017484`
- `0x18001eda4`
- `0x180026bb4`
- `0x18002a2a8`

## callees

- `0x18000d9e8`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::vector_impl<winrt::Windows::Storage::Streams::IBuffer,std::vector<winrt::Windows::Storage::Streams::IBuffer>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(
        __int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  *a1 = 0;
  return winrt::implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapMethodRunnerOptions,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapMethodRunnerOptionsFactory>::Release(v2);
}

```

## disassembly

```asm
0x18001371c  mov     rax, rcx
0x18001371f  mov     rcx, [rcx]
0x180013722  mov     qword ptr [rax], 0
0x180013729  jmp     ?Release@?$implements@UEapMethodRunnerOptions@factory_implementation@Utility@Eap@Internal@Windows@winrt@@UIActivationFactory@Foundation@67@UIEapMethodRunnerOptionsFactory@34567@@winrt@@QEAAKXZ; winrt::implements<winrt::Windows::Internal::Eap::Utility::factory_implementation::EapMethodRunnerOptions,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Internal::Eap::Utility::IEapMethodRunnerOptionsFactory>::Release(void)
```
