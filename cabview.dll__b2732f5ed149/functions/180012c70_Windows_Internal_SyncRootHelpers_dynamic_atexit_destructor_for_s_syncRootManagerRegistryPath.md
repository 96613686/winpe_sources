# Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__

- ea: `0x180012c70`
- end: `0x180012c7c`
- name: `Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000fa40`

## pseudocode

```c
void Windows::Internal::SyncRootHelpers::_dynamic_atexit_destructor_for__s_syncRootManagerRegistryPath__()
{
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&qword_18001A618);
}

```

## disassembly

```asm
0x180012c70  lea     rcx, qword_18001A618
0x180012c77  jmp     ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
```
