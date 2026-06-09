# `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x18000dff0`
- end: `0x18000dff5`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ@SA@PEAX@Z`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f618`

## pseudocode

```c
// attributes: thunk
void __fastcall `wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl'::`5'::_lambda_1_::_lambda_invoker_cdecl_(
        wil::details::EnabledStateManager *a1)
{
  wil::details::EnabledStateManager::OnStateChange(a1);
}

```

## disassembly

```asm
0x18000dff0  jmp     ?OnStateChange@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::OnStateChange(void)
```
