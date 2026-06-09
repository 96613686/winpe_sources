# _dynamic_initializer_for__g_fWilCallbacksInstalled__

- ea: `0x140001f50`
- end: `0x140001fa9`
- name: `_dynamic_initializer_for__g_fWilCallbacksInstalled__`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001f50`
- `0x1400061b8`
- `0x14000b668`

## pseudocode

```c
void (__fastcall __noreturn *dynamic_initializer_for__g_fWilCallbacksInstalled__())(const struct wil::FailureInfo *)
{
  void (__fastcall __noreturn *result)(const struct wil::FailureInfo *); // rax
  const struct wil::FailureInfo *v1; // rdx
  _BYTE v2[168]; // [rsp+20h] [rbp-A8h] BYREF

  if ( wil::details::g_pfnLoggingCallback
    && (char *)wil::details::g_pfnLoggingCallback != (char *)WilResultLoggingCallback_MaybeFailFast )
  {
    memset_0(v2, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v2, v1);
  }
  result = WilFailFastHook;
  wil::details::g_pfnLoggingCallback = (__int64 (__fastcall *)(_QWORD))WilResultLoggingCallback_MaybeFailFast;
  wil::g_pfnWilFailFast = (__int64)WilFailFastHook;
  return result;
}

```

## disassembly

```asm
0x140001f50  sub     rsp, 0C8h
0x140001f57  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140001f5e  lea     rcx, ?WilResultLoggingCallback_MaybeFailFast@@YAXAEBUFailureInfo@wil@@@Z; WilResultLoggingCallback_MaybeFailFast(wil::FailureInfo const &)
0x140001f65  test    rax, rax
0x140001f68  jz      short loc_140001F6F
0x140001f6a  cmp     rax, rcx
0x140001f6d  jnz     short loc_140001F8C
0x140001f6f  lea     rax, ?WilFailFastHook@@YA_NAEBUFailureInfo@wil@@@Z; WilFailFastHook(wil::FailureInfo const &)
0x140001f76  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x140001f7d  mov     cs:?g_pfnWilFailFast@wil@@3P6A_NAEBUFailureInfo@1@@_EEA, rax
0x140001f84  add     rsp, 0C8h
0x140001f8b  retn
0x140001f8c  xor     edx, edx; Val
0x140001f8e  lea     rcx, [rsp+0C8h+var_A8]; void *
0x140001f93  mov     r8d, 98h; Size
0x140001f99  call    memset_0
0x140001f9e  lea     rcx, [rsp+0C8h+var_A8]; this
0x140001fa3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
