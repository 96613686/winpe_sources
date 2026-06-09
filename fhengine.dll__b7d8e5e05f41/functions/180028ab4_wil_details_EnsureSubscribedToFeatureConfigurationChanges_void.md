# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180028ab4`
- end: `0x180028ad4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180028f84`
- `0x180029068`
- `0x180029148`
- `0x180029228`
- `0x180029308`
- `0x1800293e8`
- `0x1800294c8`
- `0x1800295a8`
- `0x180029688`
- `0x180029768`
- `0x18002abf4`

## callees

- `0x180028ab4`
- `0x180028adc`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180040424;
  if ( !dword_180040424 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180028ab4  sub     rsp, 28h
0x180028ab8  mov     eax, cs:dword_180040424
0x180028abe  nop
0x180028abf  test    eax, eax
0x180028ac1  jnz     short loc_180028ACF
0x180028ac3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180028aca  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180028acf  add     rsp, 28h
0x180028ad3  retn
```
