# _PackageSecurity::CryptWrapper_::_1_::dtor$0

- ea: `0x18001881d`
- end: `0x180018829`
- name: `_PackageSecurity::CryptWrapper_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a4e0`

## pseudocode

```c
__int64 __fastcall PackageSecurity::CryptWrapper_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long BCryptCloseAlgorithmProviderX(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long BCryptCloseAlgorithmProviderX(void *)>>>(a2 + 80);
}

```

## disassembly

```asm
0x18001881d  lea     rcx, [rdx+50h]
0x180018824  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?BCryptCloseAlgorithmProviderX@@YAJ0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&BCryptCloseAlgorithmProviderX(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&BCryptCloseAlgorithmProviderX(void *)>>>(void)
```
