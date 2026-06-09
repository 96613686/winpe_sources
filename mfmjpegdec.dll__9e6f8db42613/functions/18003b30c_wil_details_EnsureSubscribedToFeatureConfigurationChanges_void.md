# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x18003b30c`
- end: `0x18003b32c`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001c9b4`
- `0x18003b49c`
- `0x18003b584`
- `0x18003b6c0`
- `0x180040760`
- `0x180040848`
- `0x180059998`
- `0x180059afc`

## callees

- `0x18003b30c`
- `0x18003b334`

## pseudocode

```c
unsigned int __fastcall wil::details::EnsureSubscribedToFeatureConfigurationChanges(wil::details *this)
{
  unsigned int result; // eax

  result = dword_18009D90C;
  if ( !dword_18009D90C )
    return wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  return result;
}

```

## disassembly

```asm
0x18003b30c  sub     rsp, 28h
0x18003b310  mov     eax, cs:dword_18009D90C
0x18003b316  nop
0x18003b317  test    eax, eax
0x18003b319  jnz     short loc_18003B327
0x18003b31b  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18003b322  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ
0x18003b327  add     rsp, 28h
0x18003b32b  retn
```
