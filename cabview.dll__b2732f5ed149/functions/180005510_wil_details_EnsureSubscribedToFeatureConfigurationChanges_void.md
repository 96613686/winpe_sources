# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180005510`
- end: `0x180005530`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800067c0`
- `0x18000b454`
- `0x18000b5b0`
- `0x18000b70c`

## callees

- `0x180005510`
- `0x180005538`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18001A1A4;
  if ( !dword_18001A1A4 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180005510  sub     rsp, 28h
0x180005514  mov     eax, cs:dword_18001A1A4
0x18000551a  nop
0x18000551b  test    eax, eax
0x18000551d  jnz     short loc_18000552B
0x18000551f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180005526  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000552b  add     rsp, 28h
0x18000552f  retn
```
