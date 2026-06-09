# wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x180007648`
- end: `0x180007666`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `30`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008bfc`
- `0x180008ddc`
- `0x180008e9c`
- `0x1800136e4`
- `0x1800137a4`
- `0x180013864`
- `0x180013924`
- `0x1800139e4`
- `0x180013aa4`
- `0x180013b64`
- `0x180013c24`

## callees

- `0x180007648`
- `0x1800079e0`
- `0x180008f5c`

## pseudocode

```c
void __fastcall wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  __int64 v1; // rdx
  wil::details::ThreadFailureCallbackHolder *v2; // rcx

  if ( !wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(v2, v1);
}

```

## disassembly

```asm
0x180007648  sub     rsp, 28h
0x18000764c  add     rcx, 120h; this
0x180007653  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x180007658  test    al, al
0x18000765a  jnz     short loc_180007661
0x18000765c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180007661  add     rsp, 28h
0x180007665  retn
```
