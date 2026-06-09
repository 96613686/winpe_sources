# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800086f8`
- end: `0x180008718`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180009688`
- `0x1800164c8`
- `0x18002611c`
- `0x1800261fc`
- `0x1800263a8`
- `0x180026488`
- `0x180026568`
- `0x1800266c8`
- `0x180026828`
- `0x180026988`
- `0x180026ae8`
- `0x180026bc8`
- `0x180026ca8`
- `0x180026d88`
- `0x180026e68`

## callees

- `0x1800086f8`
- `0x180008720`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18003DD0C;
  if ( !dword_18003DD0C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x1800086f8  sub     rsp, 28h
0x1800086fc  mov     eax, cs:dword_18003DD0C
0x180008702  nop
0x180008703  test    eax, eax
0x180008705  jnz     short loc_180008713
0x180008707  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000870e  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180008713  add     rsp, 28h
0x180008717  retn
```
