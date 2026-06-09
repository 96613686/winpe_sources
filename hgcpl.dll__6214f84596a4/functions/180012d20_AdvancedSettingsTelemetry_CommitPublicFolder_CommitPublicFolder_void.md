# AdvancedSettingsTelemetry::CommitPublicFolder::~CommitPublicFolder(void)

- ea: `0x180012d20`
- end: `0x180012d45`
- name: `??1CommitPublicFolder@AdvancedSettingsTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(AdvancedSettingsTelemetry::CommitPublicFolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800154e8`

## callees

- `0x180006ed0`
- `0x180007510`

## pseudocode

```c
void __fastcall AdvancedSettingsTelemetry::CommitPublicFolder::~CommitPublicFolder(
        AdvancedSettingsTelemetry::CommitPublicFolder *this)
{
  *(_QWORD *)this = &AdvancedSettingsTelemetry::CommitPublicFolder::`vftable';
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180012d20  push    rbx
0x180012d22  sub     rsp, 20h
0x180012d26  lea     rax, ??_7CommitPublicFolder@AdvancedSettingsTelemetry@@6B@; const AdvancedSettingsTelemetry::CommitPublicFolder::`vftable'
0x180012d2d  mov     rbx, rcx
0x180012d30  mov     [rcx], rax
0x180012d33  call    ?Destroy@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180012d38  mov     rcx, rbx
0x180012d3b  add     rsp, 20h
0x180012d3f  pop     rbx
0x180012d40  jmp     ??1?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
