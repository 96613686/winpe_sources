# _Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::SaveToStorage_::_1_::dtor$1

- ea: `0x18001658a`
- end: `0x180016596`
- name: `_Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::SaveToStorage_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800115dc`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgEncryptedPayloadCache::SaveToStorage_::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(a2 + 88);
}

```

## disassembly

```asm
0x18001658a  lea     rcx, [rdx+58h]
0x180016591  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
```
