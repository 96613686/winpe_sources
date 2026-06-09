# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x140014c90`
- end: `0x140014cb0`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000ff00`
- `0x140014f60`
- `0x140015090`
- `0x140015178`
- `0x1400152a8`
- `0x1400153d8`
- `0x140015508`
- `0x140015638`
- `0x140015768`
- `0x140015898`
- `0x1400159c8`
- `0x140015af8`

## callees

- `0x140014c90`
- `0x140014cb8`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_140029DEC;
  if ( !dword_140029DEC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x140014c90  sub     rsp, 28h
0x140014c94  mov     eax, cs:dword_140029DEC
0x140014c9a  nop
0x140014c9b  test    eax, eax
0x140014c9d  jnz     short loc_140014CAB
0x140014c9f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x140014ca6  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x140014cab  add     rsp, 28h
0x140014caf  retn
```
