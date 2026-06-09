# AdvancedSettingsTelemetry::CommitSettings::~CommitSettings(void)

- ea: `0x180007170`
- end: `0x180007195`
- name: `??1CommitSettings@AdvancedSettingsTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitSettings *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a9c0`

## callees

- `0x180006ed0`
- `0x180007510`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitSettings::~CommitSettings(
        AdvancedSettingsTelemetry::CommitSettings *this)
{
  *(_QWORD *)this = &AdvancedSettingsTelemetry::CommitSettings::`vftable';
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180007170  push    rbx
0x180007172  sub     rsp, 20h
0x180007176  lea     rax, ??_7CommitSettings@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::CommitSettings::`vftable'
0x18000717d  mov     rbx, rcx
0x180007180  mov     [rcx], rax
0x180007183  call    ?Destroy@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180007188  mov     rcx, rbx
0x18000718b  add     rsp, 20h
0x18000718f  pop     rbx
0x180007190  jmp     ??1?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
