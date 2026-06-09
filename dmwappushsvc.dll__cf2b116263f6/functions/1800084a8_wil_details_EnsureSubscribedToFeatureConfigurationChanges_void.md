# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1800084a8`
- end: `0x1800084c8`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800088d4`
- `0x18000916c`

## callees

- `0x1800084a8`
- `0x1800084d0`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18001C5BC;
  if ( !dword_18001C5BC )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x1800084a8  sub     rsp, 28h
0x1800084ac  mov     eax, cs:dword_18001C5BC
0x1800084b2  nop
0x1800084b3  test    eax, eax
0x1800084b5  jnz     short loc_1800084C3
0x1800084b7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800084be  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x1800084c3  add     rsp, 28h
0x1800084c7  retn
```
