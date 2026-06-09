# wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180007698`
- end: `0x1800076b6`
- name: `?IgnoreCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `30`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008fd0`
- `0x1800090ac`
- `0x180009190`
- `0x1800093c0`
- `0x1800095f0`
- `0x180009820`
- `0x180013cf0`
- `0x180013f20`
- `0x180014150`
- `0x180014380`
- `0x1800145b0`
- `0x1800147e0`
- `0x180014a10`
- `0x180014c40`

## callees

- `0x180007698`
- `0x1800079e0`
- `0x180009a4c`

## pseudocode

```c
void __fastcall wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x180007698  sub     rsp, 28h
0x18000769c  add     rcx, 120h; this
0x1800076a3  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x1800076a8  test    al, al
0x1800076aa  jz      short loc_1800076B1
0x1800076ac  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800076b1  add     rsp, 28h
0x1800076b5  retn
```
