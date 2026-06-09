# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180007e28`
- end: `0x180007e48`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007c14`
- `0x18000ecf0`

## callees

- `0x180007e28`
- `0x180007e50`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  __int64 result; // rax

  result = (unsigned int)dword_18001E78C;
  if ( !dword_18001E78C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((RTL_SRWLOCK *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180007e28  sub     rsp, 28h
0x180007e2c  mov     eax, cs:dword_18001E78C
0x180007e32  nop
0x180007e33  test    eax, eax
0x180007e35  jnz     short loc_180007E43
0x180007e37  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180007e3e  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180007e43  add     rsp, 28h
0x180007e47  retn
```
