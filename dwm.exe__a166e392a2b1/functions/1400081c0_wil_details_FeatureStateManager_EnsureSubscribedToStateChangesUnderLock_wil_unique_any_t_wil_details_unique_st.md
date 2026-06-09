# wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)

- ea: `0x1400081c0`
- end: `0x1400081d8`
- name: `?EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@3@PEAX@Z`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000b410`

## callees

- `0x1400081c0`
- `0x14000c3ac`

## pseudocode

```c
__int64 __fastcall wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  if ( *a1 )
    return 0;
  *a1 = 0;
  return wil_details_RtlRegisterFeatureConfigurationChangeNotification((__int64)a1, a2, a3, (__int64)a1);
}

```

## disassembly

```asm
0x1400081c0  cmp     qword ptr [rcx], 0
0x1400081c4  jnz     short loc_1400081D5
0x1400081c6  mov     r9, rcx
0x1400081c9  mov     qword ptr [rcx], 0
0x1400081d0  jmp     wil_details_RtlRegisterFeatureConfigurationChangeNotification
0x1400081d5  xor     eax, eax
0x1400081d7  retn
```
