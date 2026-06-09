# _PackageSecurity::CryptWrapper_::_1_::dtor$4

- ea: `0x180018865`
- end: `0x180018871`
- name: `_PackageSecurity::CryptWrapper_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a504`

## pseudocode

```c
__int64 __fastcall PackageSecurity::CryptWrapper_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long BCryptDestroyHash(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long BCryptDestroyHash(void *)>>>(a2 + 104);
}

```

## disassembly

```asm
0x180018865  lea     rcx, [rdx+68h]
0x18001886c  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&BCryptDestroyHash(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&BCryptDestroyHash(void *)>>>(void)
```
