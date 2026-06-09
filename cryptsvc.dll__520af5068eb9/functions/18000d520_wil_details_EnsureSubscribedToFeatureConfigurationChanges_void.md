# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000d520`
- end: `0x18000d540`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000bb18`
- `0x1800129a4`
- `0x180012ae4`
- `0x180013924`

## callees

- `0x18000d520`
- `0x180012644`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18002076C;
  if ( !dword_18002076C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000d520  sub     rsp, 28h
0x18000d524  mov     eax, cs:dword_18002076C
0x18000d52a  nop
0x18000d52b  test    eax, eax
0x18000d52d  jnz     short loc_18000D53B
0x18000d52f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000d536  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000d53b  add     rsp, 28h
0x18000d53f  retn
```
