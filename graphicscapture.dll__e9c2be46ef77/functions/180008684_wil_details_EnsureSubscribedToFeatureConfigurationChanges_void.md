# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180008684`
- end: `0x1800086a4`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000957c`
- `0x18000fe34`
- `0x18000ff74`
- `0x1800100b4`
- `0x1800101f4`
- `0x180010334`
- `0x180010474`
- `0x180022ef8`
- `0x180023038`
- `0x180023178`

## callees

- `0x180008684`
- `0x1800086ac`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_180035B8C;
  if ( !dword_180035B8C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180008684  sub     rsp, 28h
0x180008688  mov     eax, cs:dword_180035B8C
0x18000868e  nop
0x18000868f  test    eax, eax
0x180008691  jnz     short loc_18000869F
0x180008693  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000869a  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000869f  add     rsp, 28h
0x1800086a3  retn
```
