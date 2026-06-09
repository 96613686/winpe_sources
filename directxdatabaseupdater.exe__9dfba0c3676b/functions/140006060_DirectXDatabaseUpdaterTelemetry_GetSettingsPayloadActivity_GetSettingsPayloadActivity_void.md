# DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::~GetSettingsPayloadActivity(void)

- ea: `0x140006060`
- end: `0x140006085`
- name: `??1GetSettingsPayloadActivity@DirectXDatabaseUpdaterTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x14000b0cc`
- `0x1400189d0`

## callees

- `0x140005884`
- `0x140006b80`

## pseudocode

```c
void __fastcall DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::~GetSettingsPayloadActivity(
        DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity *this)
{
  *(_QWORD *)this = &DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::`vftable';
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x140006060  push    rbx
0x140006062  sub     rsp, 20h
0x140006066  lea     rax, ??_7GetSettingsPayloadActivity@DirectXDatabaseUpdaterTelemetry@@6B@; const DirectXDatabaseUpdaterTelemetry::GetSettingsPayloadActivity::`vftable'
0x14000606d  mov     rbx, rcx
0x140006070  mov     [rcx], rax
0x140006073  call    ?Destroy@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140006078  mov     rcx, rbx
0x14000607b  add     rsp, 20h
0x14000607f  pop     rbx
0x140006080  jmp     ??1?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
