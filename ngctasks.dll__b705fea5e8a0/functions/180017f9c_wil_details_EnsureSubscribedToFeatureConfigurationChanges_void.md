# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180017f9c`
- end: `0x180017fbc`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180018608`
- `0x180018854`
- `0x18001beec`

## callees

- `0x180017f9c`
- `0x180017fc4`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180031834;
  if ( !dword_180031834 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180017f9c  sub     rsp, 28h
0x180017fa0  mov     eax, cs:dword_180031834
0x180017fa6  nop
0x180017fa7  test    eax, eax
0x180017fa9  jnz     short loc_180017FB7
0x180017fab  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180017fb2  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180017fb7  add     rsp, 28h
0x180017fbb  retn
```
