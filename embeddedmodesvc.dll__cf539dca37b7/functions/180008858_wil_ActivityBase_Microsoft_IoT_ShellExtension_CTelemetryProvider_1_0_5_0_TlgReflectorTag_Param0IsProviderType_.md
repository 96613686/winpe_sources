# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x180008858`
- end: `0x180008876`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `30`
- prototype: `void __fastcall(__int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800090a4`
- `0x18000becc`
- `0x180013778`
- `0x180013818`
- `0x1800138b8`
- `0x180013958`
- `0x1800139f8`
- `0x180013a98`

## callees

- `0x180008858`
- `0x1800088c0`
- `0x180009150`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( !wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(v1);
}

```

## disassembly

```asm
0x180008858  sub     rsp, 28h
0x18000885c  add     rcx, 120h; this
0x180008863  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x180008868  test    al, al
0x18000886a  jnz     short loc_180008871
0x18000886c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180008871  add     rsp, 28h
0x180008875  retn
```
