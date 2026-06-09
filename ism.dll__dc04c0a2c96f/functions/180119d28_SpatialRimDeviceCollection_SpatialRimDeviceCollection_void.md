# SpatialRimDeviceCollection::~SpatialRimDeviceCollection(void)

- ea: `0x180119d28`
- end: `0x180119daa`
- name: `??1SpatialRimDeviceCollection@@UEAA@XZ`
- size: `130`
- prototype: `void __fastcall(SpatialRimDeviceCollection *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180119ee0`

## callees

- `0x180012b74`
- `0x180099dd4`
- `0x1800b01b0`
- `0x18011629c`
- `0x18011a090`
- `0x180121608`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180119d5c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180119d8b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180119d5c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180119d8b`

## pseudocode

```c
void __fastcall SpatialRimDeviceCollection::~SpatialRimDeviceCollection(SpatialRimDeviceCollection *this)
{
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 2976);
  std::_Hash<std::_Umap_traits<unsigned long,std::shared_ptr<LegacyDeviceInfo>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LegacyDeviceInfo>>>,0>>::~_Hash<std::_Umap_traits<unsigned long,std::shared_ptr<LegacyDeviceInfo>,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,std::shared_ptr<LegacyDeviceInfo>>>,0>>((char *)this + 2912);
  Microsoft::WRL::ComPtr<SpectrumListener>::InternalRelease((char *)this + 2888);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2848));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 2832);
  *((_QWORD *)this + 352) = &Microsoft::WRL::Wrappers::HandleT<SpatialRimDeviceCollection::HMODULETraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<SpatialRimDeviceCollection::HMODULETraits>::Close();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2768));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 2760);
  HIDDeviceCollection::~HIDDeviceCollection(this);
}

```

## disassembly

```asm
0x180119d28  push    rbx
0x180119d2a  sub     rsp, 20h
0x180119d2e  mov     rbx, rcx
0x180119d31  add     rcx, 0BA0h
0x180119d38  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180119d3d  lea     rcx, [rbx+0B60h]
0x180119d44  call    ??1?$_Hash@V?$_Umap_traits@KV?$shared_ptr@ULegacyDeviceInfo@@@std@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@ULegacyDeviceInfo@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<ulong,std::shared_ptr<LegacyDeviceInfo>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::shared_ptr<LegacyDeviceInfo>>>,0>>::~_Hash<std::_Umap_traits<ulong,std::shared_ptr<LegacyDeviceInfo>,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,std::shared_ptr<LegacyDeviceInfo>>>,0>>(void)
0x180119d49  lea     rcx, [rbx+0B48h]
0x180119d50  call    ?InternalRelease@?$ComPtr@VSpectrumListener@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SpectrumListener>::InternalRelease(void)
0x180119d55  lea     rcx, [rbx+0B20h]; lpCriticalSection
0x180119d5c  call    cs:__imp_DeleteCriticalSection
0x180119d62  lea     rcx, [rbx+0B10h]
0x180119d69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180119d6e  lea     rcx, [rbx+0B00h]
0x180119d75  lea     rax, ??_7?$HandleT@UHMODULETraits@SpatialRimDeviceCollection@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SpatialRimDeviceCollection::HMODULETraits>::`vftable'
0x180119d7c  mov     [rcx], rax
0x180119d7f  call    ?Close@?$HandleT@UHMODULETraits@SpatialRimDeviceCollection@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<SpatialRimDeviceCollection::HMODULETraits>::Close(void)
0x180119d84  lea     rcx, [rbx+0AD0h]; lpCriticalSection
0x180119d8b  call    cs:__imp_DeleteCriticalSection
0x180119d91  lea     rcx, [rbx+0AC8h]
0x180119d98  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180119d9d  mov     rcx, rbx; this
0x180119da0  add     rsp, 20h
0x180119da4  pop     rbx
0x180119da5  jmp     ??1HIDDeviceCollection@@UEAA@XZ; HIDDeviceCollection::~HIDDeviceCollection(void)
```
