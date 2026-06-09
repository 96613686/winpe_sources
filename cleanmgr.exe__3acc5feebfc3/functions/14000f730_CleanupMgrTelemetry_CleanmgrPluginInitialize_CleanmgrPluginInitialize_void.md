# CleanupMgrTelemetry::CleanmgrPluginInitialize::~CleanmgrPluginInitialize(void)

- ea: `0x14000f730`
- end: `0x14000f755`
- name: `??1CleanmgrPluginInitialize@CleanupMgrTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(CleanupMgrTelemetry::CleanmgrPluginInitialize *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140013530`
- `0x14001787a`

## callees

- `0x14000f574`
- `0x14000f94c`

## pseudocode

```c
void __fastcall CleanupMgrTelemetry::CleanmgrPluginInitialize::~CleanmgrPluginInitialize(
        CleanupMgrTelemetry::CleanmgrPluginInitialize *this)
{
  *(_QWORD *)this = &CleanupMgrTelemetry::CleanmgrPluginInitialize::`vftable';
  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x14000f730  push    rbx
0x14000f732  sub     rsp, 20h
0x14000f736  lea     rax, ??_7CleanmgrPluginInitialize@CleanupMgrTelemetry@@6B@; const CleanupMgrTelemetry::CleanmgrPluginInitialize::`vftable'
0x14000f73d  mov     rbx, rcx
0x14000f740  mov     [rcx], rax
0x14000f743  call    ?Destroy@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14000f748  mov     rcx, rbx
0x14000f74b  add     rsp, 20h
0x14000f74f  pop     rbx
0x14000f750  jmp     ??1?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
