# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180012c54`
- end: `0x180012c74`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e0b0`
- `0x180012ec0`
- `0x180012fa8`
- `0x1800130e8`
- `0x180013228`
- `0x180013368`
- `0x1800134a8`
- `0x1800135e8`
- `0x180013728`
- `0x180013868`
- `0x1800139a8`
- `0x180013ae8`
- `0x180013c28`

## callees

- `0x180012c54`
- `0x180012c7c`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_1800226CC;
  if ( !dword_1800226CC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180012c54  sub     rsp, 28h
0x180012c58  mov     eax, cs:dword_1800226CC
0x180012c5e  nop
0x180012c5f  test    eax, eax
0x180012c61  jnz     short loc_180012C6F
0x180012c63  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180012c6a  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180012c6f  add     rsp, 28h
0x180012c73  retn
```
