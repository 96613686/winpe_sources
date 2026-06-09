# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18000eb58`
- end: `0x18000eb78`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000f24c`
- `0x1800118f0`
- `0x1800119d8`
- `0x180011b3c`
- `0x180011c24`

## callees

- `0x18000eb58`
- `0x18000eb80`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180022A2C;
  if ( !dword_180022A2C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18000eb58  sub     rsp, 28h
0x18000eb5c  mov     eax, cs:dword_180022A2C
0x18000eb62  nop
0x18000eb63  test    eax, eax
0x18000eb65  jnz     short loc_18000EB73
0x18000eb67  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000eb6e  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000eb73  add     rsp, 28h
0x18000eb77  retn
```
