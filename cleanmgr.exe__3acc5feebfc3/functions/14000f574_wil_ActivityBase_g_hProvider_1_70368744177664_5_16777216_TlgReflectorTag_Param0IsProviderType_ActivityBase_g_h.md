# wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x14000f574`
- end: `0x14000f5a3`
- name: `??1?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `47`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f6ac`
- `0x14000f6d8`
- `0x14000f704`
- `0x14000f730`
- `0x14000f75c`
- `0x14000f87c`
- `0x14000f904`

## callees

- `0x14000f5ac`
- `0x14000f930`
- `0x140015fc8`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  wil::details::shared_object<wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<g_hProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(a1 + 280);
  return wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<g_hProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<g_hProvider,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x14000f574  push    rbx
0x14000f576  sub     rsp, 20h
0x14000f57a  mov     rbx, rcx
0x14000f57d  add     rcx, 120h; this
0x14000f584  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x14000f589  lea     rcx, [rbx+118h]
0x14000f590  call    ?reset@?$shared_object@V?$ActivityData@Vg_hProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<g_hProvider,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x14000f595  lea     rcx, [rbx+8]
0x14000f599  add     rsp, 20h
0x14000f59d  pop     rbx
0x14000f59e  jmp     ??1?$ActivityData@Vg_hProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<g_hProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<g_hProvider,_TlgReflectorTag_Param0IsProviderType>(void)
```
