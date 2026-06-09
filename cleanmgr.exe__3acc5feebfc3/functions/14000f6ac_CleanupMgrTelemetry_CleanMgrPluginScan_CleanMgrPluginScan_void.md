# CleanupMgrTelemetry::CleanMgrPluginScan::~CleanMgrPluginScan(void)

- ea: `0x14000f6ac`
- end: `0x14000f6d1`
- name: `??1CleanMgrPluginScan@CleanupMgrTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CleanupMgrTelemetry::CleanMgrPluginScan *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140012a7c`
- `0x140017844`

## callees

- `0x14000f574`
- `0x14000f94c`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::CleanMgrPluginScan::~CleanMgrPluginScan(
        CleanupMgrTelemetry::CleanMgrPluginScan *this)
{
  *(_QWORD *)this = &CleanupMgrTelemetry::CleanMgrPluginScan::`vftable';
  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x14000f6ac  push    rbx
0x14000f6ae  sub     rsp, 20h
0x14000f6b2  lea     rax, ??_7CleanMgrPluginScan@CleanupMgrTelemetry@@6B@; const CleanupMgrTelemetry::CleanMgrPluginScan::`vftable'
0x14000f6b9  mov     rbx, rcx
0x14000f6bc  mov     [rcx], rax
0x14000f6bf  call    ?Destroy@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14000f6c4  mov     rcx, rbx
0x14000f6c7  add     rsp, 20h
0x14000f6cb  pop     rbx
0x14000f6cc  jmp     ??1?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
