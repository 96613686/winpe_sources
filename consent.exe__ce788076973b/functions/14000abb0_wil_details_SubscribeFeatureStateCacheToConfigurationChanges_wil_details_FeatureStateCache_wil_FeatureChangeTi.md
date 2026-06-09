# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000abb0`
- end: `0x14000abc5`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `21`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140017a74`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        unsigned int a2,
        unsigned int a3)
{
  return wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
           &wil::details::g_enabledStateManager,
           a1,
           a2,
           a3);
}

```

## disassembly

```asm
0x14000abb0  mov     r9d, r8d
0x14000abb3  mov     r8d, edx
0x14000abb6  mov     rdx, rcx
0x14000abb9  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000abc0  jmp     ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
```
