# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x140004788`
- end: `0x14000479e`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140003f50`

## callees

- `0x140004788`
- `0x14000c410`

## pseudocode

```c
__int64 (*__fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        __int64 *a1))(void)
{
  __int64 v1; // rcx
  __int64 (*result)(void); // rax

  v1 = *a1;
  if ( v1 )
    return wil_details_RtlUnregisterFeatureConfigurationChangeNotification(v1);
  return result;
}

```

## disassembly

```asm
0x140004788  sub     rsp, 28h
0x14000478c  mov     rcx, [rcx]
0x14000478f  test    rcx, rcx
0x140004792  jz      short loc_140004799
0x140004794  call    wil_details_RtlUnregisterFeatureConfigurationChangeNotification
0x140004799  add     rsp, 28h
0x14000479d  retn
```
