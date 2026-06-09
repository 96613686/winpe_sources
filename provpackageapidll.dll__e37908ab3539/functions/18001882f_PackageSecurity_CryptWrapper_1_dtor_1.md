# _PackageSecurity::CryptWrapper_::_1_::dtor$1

- ea: `0x18001882f`
- end: `0x18001883b`
- name: `_PackageSecurity::CryptWrapper_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a528`

## pseudocode

```c
__int64 __fastcall PackageSecurity::CryptWrapper_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long BCryptDestroyKey(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long BCryptDestroyKey(void *)>>>(a2 + 88);
}

```

## disassembly

```asm
0x18001882f  lea     rcx, [rdx+58h]
0x180018836  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&BCryptDestroyKey(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&BCryptDestroyKey(void *)>>>(void)
```
