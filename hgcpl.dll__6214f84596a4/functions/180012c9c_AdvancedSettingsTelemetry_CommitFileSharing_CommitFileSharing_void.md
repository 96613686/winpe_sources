# AdvancedSettingsTelemetry::CommitFileSharing::~CommitFileSharing(void)

- ea: `0x180012c9c`
- end: `0x180012cc1`
- name: `??1CommitFileSharing@AdvancedSettingsTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitFileSharing *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014f30`

## callees

- `0x180006ed0`
- `0x180007510`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitFileSharing::~CommitFileSharing(
        AdvancedSettingsTelemetry::CommitFileSharing *this)
{
  *(_QWORD *)this = &AdvancedSettingsTelemetry::CommitFileSharing::`vftable';
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180012c9c  push    rbx
0x180012c9e  sub     rsp, 20h
0x180012ca2  lea     rax, ??_7CommitFileSharing@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::CommitFileSharing::`vftable'
0x180012ca9  mov     rbx, rcx
0x180012cac  mov     [rcx], rax
0x180012caf  call    ?Destroy@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180012cb4  mov     rcx, rbx
0x180012cb7  add     rsp, 20h
0x180012cbb  pop     rbx
0x180012cbc  jmp     ??1?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
