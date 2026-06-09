# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18001fc20`
- end: `0x18001fc40`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180020730`

## callees

- `0x180011a20`
- `0x18001fc20`

## pseudocode

```c
__int64 __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  __int64 result; // rax

  result = (unsigned int)dword_18003353C;
  if ( !dword_18003353C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((RTL_SRWLOCK *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18001fc20  sub     rsp, 28h
0x18001fc24  mov     eax, cs:dword_18003353C
0x18001fc2a  nop
0x18001fc2b  test    eax, eax
0x18001fc2d  jnz     short loc_18001FC3B
0x18001fc2f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18001fc36  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18001fc3b  add     rsp, 28h
0x18001fc3f  retn
```
