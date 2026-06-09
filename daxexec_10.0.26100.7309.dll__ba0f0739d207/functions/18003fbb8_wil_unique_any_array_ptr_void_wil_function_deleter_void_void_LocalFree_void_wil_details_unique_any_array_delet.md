# wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)

- ea: `0x18003fbb8`
- end: `0x18003fc51`
- name: `?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ`
- size: `153`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180038ee0`
- `0x18003a1d4`
- `0x18003d978`

## callees

- `0x18003fbb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fbe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fbe9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fc08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fc08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fbfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fc20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fbfa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003fc20`

## pseudocode

```c

```
