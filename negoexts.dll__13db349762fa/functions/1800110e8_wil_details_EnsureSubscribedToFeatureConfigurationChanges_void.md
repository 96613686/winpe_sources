# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800110e8`
- end: `0x180011108`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011488`
- `0x1800115c8`
- `0x180012370`
- `0x180019d00`

## callees

- `0x1800110e8`
- `0x180011110`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18002731C;
  if ( !dword_18002731C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x1800110e8  sub     rsp, 28h
0x1800110ec  mov     eax, cs:dword_18002731C
0x1800110f2  nop
0x1800110f3  test    eax, eax
0x1800110f5  jnz     short loc_180011103
0x1800110f7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800110fe  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180011103  add     rsp, 28h
0x180011107  retn
```
