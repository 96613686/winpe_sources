# wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)

- ea: `0x18003aa40`
- end: `0x18003aac1`
- name: `??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ`
- size: `129`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003be54`
- `0x18003f6f4`
- `0x1800c1d78`
- `0x1800c1f55`

## callees

- `0x18003aa40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aa82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003aa82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003aa74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003aa9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003aa74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003aa9a`

## pseudocode

```c

```
