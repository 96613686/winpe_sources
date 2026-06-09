# AdvancedSettingsTelemetry::CommitPasswordProtection::~CommitPasswordProtection(void)

- ea: `0x180012cf4`
- end: `0x180012d19`
- name: `??1CommitPasswordProtection@AdvancedSettingsTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitPasswordProtection *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015324`

## callees

- `0x180006ed0`
- `0x180007510`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitPasswordProtection::~CommitPasswordProtection(
        AdvancedSettingsTelemetry::CommitPasswordProtection *this)
{
  *(_QWORD *)this = &AdvancedSettingsTelemetry::CommitPasswordProtection::`vftable';
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180012cf4  push    rbx
0x180012cf6  sub     rsp, 20h
0x180012cfa  lea     rax, ??_7CommitPasswordProtection@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::CommitPasswordProtection::`vftable'
0x180012d01  mov     rbx, rcx
0x180012d04  mov     [rcx], rax
0x180012d07  call    ?Destroy@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180012d0c  mov     rcx, rbx
0x180012d0f  add     rsp, 20h
0x180012d13  pop     rbx
0x180012d14  jmp     ??1?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
