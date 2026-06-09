# _AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor$0

- ea: `0x140011590`
- end: `0x14001159c`
- name: `_AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x140006528`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::AdapterCacheUpdate_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<long (*)(void *),&long NtClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<long (*)(void *),&long NtClose(void *)>>>(*(_QWORD *)(a2 + 176));
}

```

## disassembly

```asm
0x140011590  mov     rcx, [rdx+0B0h]
0x140011597  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AJPEAX@Z$1?NtClose@@YAJ0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<long (*)(void *),&NtClose(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<long (*)(void *),&NtClose(void *)>>>(void)
```
