# _Element::LinkPayload_::_1_::dtor$1

- ea: `0x180018b27`
- end: `0x180018b33`
- name: `_Element::LinkPayload_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800064a8`

## pseudocode

```c
__int64 __fastcall Element::LinkPayload_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int WIMCloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int WIMCloseHandle(void *)>>>((__int64 *)(a2 + 104));
}

```

## disassembly

```asm
0x180018b27  lea     rcx, [rdx+68h]
0x180018b2e  jmp     ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?WIMCloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&WIMCloseHandle(void *)>>>(void)
```
