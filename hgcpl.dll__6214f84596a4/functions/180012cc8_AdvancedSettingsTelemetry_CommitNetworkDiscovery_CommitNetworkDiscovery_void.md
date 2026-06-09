# AdvancedSettingsTelemetry::CommitNetworkDiscovery::~CommitNetworkDiscovery(void)

- ea: `0x180012cc8`
- end: `0x180012ced`
- name: `??1CommitNetworkDiscovery@AdvancedSettingsTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitNetworkDiscovery *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800151fc`

## callees

- `0x180006ed0`
- `0x180007510`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitNetworkDiscovery::~CommitNetworkDiscovery(
        AdvancedSettingsTelemetry::CommitNetworkDiscovery *this)
{
  *(_QWORD *)this = &AdvancedSettingsTelemetry::CommitNetworkDiscovery::`vftable';
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180012cc8  push    rbx
0x180012cca  sub     rsp, 20h
0x180012cce  lea     rax, ??_7CommitNetworkDiscovery@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::CommitNetworkDiscovery::`vftable'
0x180012cd5  mov     rbx, rcx
0x180012cd8  mov     [rcx], rax
0x180012cdb  call    ?Destroy@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180012ce0  mov     rcx, rbx
0x180012ce3  add     rsp, 20h
0x180012ce7  pop     rbx
0x180012ce8  jmp     ??1?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
