# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800052d4`
- end: `0x1800052f4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005fa8`

## callees

- `0x1800052d4`
- `0x1800052fc`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18000F1DC;
  if ( !dword_18000F1DC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x1800052d4  sub     rsp, 28h
0x1800052d8  mov     eax, cs:dword_18000F1DC
0x1800052de  nop
0x1800052df  test    eax, eax
0x1800052e1  jnz     short loc_1800052EF
0x1800052e3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800052ea  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x1800052ef  add     rsp, 28h
0x1800052f3  retn
```
