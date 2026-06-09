# _dynamic_initializer_for__g_fWilCallbacksInstalled__

- ea: `0x1800010f0`
- end: `0x1800010ff`
- name: `_dynamic_initializer_for__g_fWilCallbacksInstalled__`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c
void (__fastcall __noreturn *dynamic_initializer_for__g_fWilCallbacksInstalled__())(const struct wil::FailureInfo *)
{
  void (__fastcall __noreturn *result)(const struct wil::FailureInfo *); // rax

  result = WilFailFastHook;
  wil::g_pfnWilFailFast = (__int64)WilFailFastHook;
  return result;
}

```

## disassembly

```asm
0x1800010f0  lea     rax, ?WilFailFastHook@@YA_NAEBUFailureInfo@wil@@@Z; WilFailFastHook(wil::FailureInfo const &)
0x1800010f7  mov     cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA, rax
0x1800010fe  retn
```
