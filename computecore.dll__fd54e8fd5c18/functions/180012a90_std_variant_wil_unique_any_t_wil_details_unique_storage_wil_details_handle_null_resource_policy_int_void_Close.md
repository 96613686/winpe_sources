# std::variant<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::com_ptr_t<IUnknown,wil::err_exception_policy>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>>::operator=<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,0,0>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)

- ea: `0x180012a90`
- end: `0x180012b5e`
- name: `??$?4V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$0A@$0A@@?$variant@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@2@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@2@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@2@@std@@QEAAAEAV01@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800126a8`

## callees

- `0x180012a90`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ad6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012ad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ac3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ace`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ace`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b35`
- `WS2_32!__imp_closesocket` at `0x180012b09`
- `WS2_32!__imp_closesocket` at `0x180012b09`

## pseudocode

```c

```
