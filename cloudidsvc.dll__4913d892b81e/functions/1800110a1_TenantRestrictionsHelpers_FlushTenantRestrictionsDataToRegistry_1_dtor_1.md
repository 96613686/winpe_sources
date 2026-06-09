# _TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry_::_1_::dtor$1

- ea: `0x1800110a1`
- end: `0x1800110ad`
- name: `_TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000dd24`

## pseudocode

```c
__int64 __fastcall TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(a2 + 104);
}

```

## disassembly

```asm
0x1800110a1  lea     rcx, [rdx+68h]
0x1800110a8  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
```
