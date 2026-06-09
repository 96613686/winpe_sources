# CleanupMgrTelemetry::CleanmgrPluginInstantiate::~CleanmgrPluginInstantiate(void)

- ea: `0x14000f75c`
- end: `0x14000f781`
- name: `??1CleanmgrPluginInstantiate@CleanupMgrTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CleanupMgrTelemetry::CleanmgrPluginInstantiate *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140013530`
- `0x140017868`

## callees

- `0x14000f574`
- `0x14000f94c`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::CleanmgrPluginInstantiate::~CleanmgrPluginInstantiate(
        CleanupMgrTelemetry::CleanmgrPluginInstantiate *this)
{
  *(_QWORD *)this = &CleanupMgrTelemetry::CleanmgrPluginInstantiate::`vftable';
  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x14000f75c  push    rbx
0x14000f75e  sub     rsp, 20h
0x14000f762  lea     rax, ??_7CleanmgrPluginInstantiate@CleanupMgrTelemetry@@6B@; const CleanupMgrTelemetry::CleanmgrPluginInstantiate::`vftable'
0x14000f769  mov     rbx, rcx
0x14000f76c  mov     [rcx], rax
0x14000f76f  call    ?Destroy@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14000f774  mov     rcx, rbx
0x14000f777  add     rsp, 20h
0x14000f77b  pop     rbx
0x14000f77c  jmp     ??1?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
