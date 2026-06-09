# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140007508`
- end: `0x140007528`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140007a20`
- `0x14000cb24`
- `0x14000cc04`
- `0x14000cce4`
- `0x14000cdc4`
- `0x14000cea4`
- `0x14000cf84`
- `0x14000d064`
- `0x14000d144`
- `0x14000d224`
- `0x14000d304`
- `0x14000d3e4`
- `0x14000d4c4`

## callees

- `0x140007508`
- `0x140007530`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_140021244;
  if ( !dword_140021244 )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x140007508  sub     rsp, 28h
0x14000750c  mov     eax, cs:dword_140021244
0x140007512  nop
0x140007513  test    eax, eax
0x140007515  jnz     short loc_140007523
0x140007517  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x14000751e  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x140007523  add     rsp, 28h
0x140007527  retn
```
