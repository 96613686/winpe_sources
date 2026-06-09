# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x180012bf0`
- end: `0x180012c10`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012f98`
- `0x180013a00`

## callees

- `0x180012bf0`
- `0x180012c18`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  __int64 result; // rax

  result = (unsigned int)dword_18002615C;
  if ( !dword_18002615C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((RTL_SRWLOCK *)wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x180012bf0  sub     rsp, 28h
0x180012bf4  mov     eax, cs:dword_18002615C
0x180012bfa  nop
0x180012bfb  test    eax, eax
0x180012bfd  jnz     short loc_180012C0B
0x180012bff  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180012c06  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180012c0b  add     rsp, 28h
0x180012c0f  retn
```
