# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x140005884`
- end: `0x1400058b3`
- name: `??1?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140005f34`
- `0x140005f60`
- `0x140006060`
- `0x1400061d4`
- `0x140006200`
- `0x14000629c`

## callees

- `0x1400058bc`
- `0x140006190`
- `0x14000e5e0`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  wil::details::shared_object<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(a1 + 280);
  return wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x140005884  push    rbx
0x140005886  sub     rsp, 20h
0x14000588a  mov     rbx, rcx
0x14000588d  add     rcx, 120h; this
0x140005894  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140005899  lea     rcx, [rbx+118h]
0x1400058a0  call    ?reset@?$shared_object@V?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1400058a5  lea     rcx, [rbx+8]
0x1400058a9  add     rsp, 20h
0x1400058ad  pop     rbx
0x1400058ae  jmp     ??1?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>(void)
```
