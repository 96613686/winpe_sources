# _WaitForConfigRefreshSemaphore_::_1_::dtor$0

- ea: `0x140015ec7`
- end: `0x140015ed3`
- name: `_WaitForConfigRefreshSemaphore_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000f088`

## pseudocode

```c
void __fastcall WaitForConfigRefreshSemaphore_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>((void **)(a2 + 56));
}

```

## disassembly

```asm
0x140015ec7  lea     rcx, [rdx+38h]
0x140015ece  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?ReleaseConfigRefreshMutex@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&ReleaseConfigRefreshMutex(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
```
