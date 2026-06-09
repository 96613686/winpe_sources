# _Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::DecryptDataWithKeyProtector_::_1_::dtor$1

- ea: `0x18000b083`
- end: `0x18000b08f`
- name: `_Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::DecryptDataWithKeyProtector_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000776c`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::DecryptDataWithKeyProtector_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,enum _MI_Result (*)(_MI_Instance *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,enum _MI_Result (*)(_MI_Instance *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>((__int64 *)(a2 + 128));
}

```

## disassembly

```asm
0x18000b083  lea     rcx, [rdx+80h]
0x18000b08a  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,_MI_Result (*)(_MI_Instance *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,_MI_Result (*)(_MI_Instance *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>(void)
```
