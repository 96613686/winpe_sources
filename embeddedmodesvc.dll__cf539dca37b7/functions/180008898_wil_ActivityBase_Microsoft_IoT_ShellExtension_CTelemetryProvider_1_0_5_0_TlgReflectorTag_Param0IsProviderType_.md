# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180008898`
- end: `0x1800088b7`
- name: `?IgnoreCurrentThread@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800091c4`
- `0x1800092a0`
- `0x18000bf70`
- `0x180013b38`
- `0x180013c20`
- `0x180013e50`
- `0x180014090`
- `0x1800142d0`
- `0x180014510`
- `0x180014750`
- `0x180014990`
- `0x180014bd0`

## callees

- `0x180008898`
- `0x1800088c0`
- `0x1800094d4`

## pseudocode

```c
void __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x180008898  sub     rsp, 28h
0x18000889c  add     rcx, 120h; this
0x1800088a3  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x1800088a8  test    al, al
0x1800088aa  jz      short loc_1800088B2
0x1800088ac  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800088b1  nop
0x1800088b2  add     rsp, 28h
0x1800088b6  retn
```
