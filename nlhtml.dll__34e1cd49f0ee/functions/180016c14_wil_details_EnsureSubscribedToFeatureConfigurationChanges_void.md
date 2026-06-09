# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180016c14`
- end: `0x180016c34`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `16`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800178ec`
- `0x18001b554`
- `0x18001b634`
- `0x18001b714`
- `0x18001d09c`
- `0x18001d17c`
- `0x18001d25c`
- `0x18001d33c`
- `0x18001d41c`
- `0x18001d4fc`
- `0x18001d5dc`
- `0x18001d6bc`
- `0x18001d79c`
- `0x18001d87c`
- `0x18001d95c`
- `0x18001da3c`

## callees

- `0x180016c14`
- `0x180016c3c`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18003DEA4;
  if ( !dword_18003DEA4 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180016c14  sub     rsp, 28h
0x180016c18  mov     eax, cs:dword_18003DEA4
0x180016c1e  nop
0x180016c1f  test    eax, eax
0x180016c21  jnz     short loc_180016C2F
0x180016c23  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180016c2a  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180016c2f  add     rsp, 28h
0x180016c33  retn
```
