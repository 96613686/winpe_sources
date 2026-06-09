# _Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod_::_1_::dtor$0

- ea: `0x18000b113`
- end: `0x18000b11f`
- name: `_Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod_::_1_::dtor$0`
- size: `12`
- prototype: `enum _MI_Result __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009ce0`

## pseudocode

```c
enum _MI_Result __fastcall Microsoft::HostGuardian::Client::Plugin::CimUtilities::InvokeStaticWmiMethod_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Operation *,enum _MI_Result (*)(_MI_Operation *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *),wistd::integral_constant<unsigned __int64,0>,_MI_Operation *,_MI_Operation *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Operation *,enum _MI_Result (*)(_MI_Operation *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *),wistd::integral_constant<unsigned __int64,0>,_MI_Operation *,_MI_Operation *,0,std::nullptr_t>>>(
           (Microsoft::HostGuardian::Client::Plugin::CimUtilities **)(a2 + 184),
           (struct _MI_Operation *)a2);
}

```

## disassembly

```asm
0x18000b113  lea     rcx, [rdx+0B8h]
0x18000b11a  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Operation@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Operation_Close_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Operation *,_MI_Result (*)(_MI_Operation *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *),wistd::integral_constant<unsigned __int64,0>,_MI_Operation *,_MI_Operation *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Operation *,_MI_Result (*)(_MI_Operation *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *),wistd::integral_constant<unsigned __int64,0>,_MI_Operation *,_MI_Operation *,0,std::nullptr_t>>>(void)
```
