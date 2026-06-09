# _CMapsUpdateTaskHandler::StartAutoCheckForUpdate_::_1_::dtor$4

- ea: `0x180007fe6`
- end: `0x180007ff2`
- name: `_CMapsUpdateTaskHandler::StartAutoCheckForUpdate_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180003360`

## pseudocode

```c
__int64 __fastcall CMapsUpdateTaskHandler::StartAutoCheckForUpdate_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMAPSSTORAGE__ *,long (*)(HMAPSSTORAGE__ *),&long MapsStorageClose(HMAPSSTORAGE__ *),wistd::integral_constant<unsigned __int64,0>,HMAPSSTORAGE__ *,HMAPSSTORAGE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMAPSSTORAGE__ *,long (*)(HMAPSSTORAGE__ *),&long MapsStorageClose(HMAPSSTORAGE__ *),wistd::integral_constant<unsigned __int64,0>,HMAPSSTORAGE__ *,HMAPSSTORAGE__ *,0,std::nullptr_t>>>(a2 + 72);
}

```

## disassembly

```asm
0x180007fe6  lea     rcx, [rdx+48h]
0x180007fed  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHMAPSSTORAGE__@@P6AJPEAU1@@Z$1?MapsStorageClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMAPSSTORAGE__ *,long (*)(HMAPSSTORAGE__ *),&MapsStorageClose(HMAPSSTORAGE__ *),wistd::integral_constant<unsigned __int64,0>,HMAPSSTORAGE__ *,HMAPSSTORAGE__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMAPSSTORAGE__ *,long (*)(HMAPSSTORAGE__ *),&MapsStorageClose(HMAPSSTORAGE__ *),wistd::integral_constant<unsigned __int64,0>,HMAPSSTORAGE__ *,HMAPSSTORAGE__ *,0,std::nullptr_t>>>(void)
```
