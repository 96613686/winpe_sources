# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::Start<>(void)

- ea: `0x18000f710`
- end: `0x18000f740`
- name: `??$Start@$$V@BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SA?AV01234@XZ`
- size: `48`
- prototype: `Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *__fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010bfc`
- `0x1800114f0`

## callees

- `0x18000854c`
- `0x180013958`

## string_xrefs

- `0x18000f716`: `BackgroundTaskLaunch`

## pseudocode

```c
Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *__fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::Start<>(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *this)
{
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    this,
    "BackgroundTaskLaunch");
  *(_QWORD *)this = &Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::`vftable';
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::StartActivity(this);
  return this;
}

```

## disassembly

```asm
0x18000f710  push    rbx
0x18000f712  sub     rsp, 20h
0x18000f716  lea     rdx, aBackgroundtask_6; "BackgroundTaskLaunch"
0x18000f71d  mov     rbx, rcx
0x18000f720  call    ??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000f725  lea     rax, ??_7BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::`vftable'
0x18000f72c  mov     rcx, rbx; this
0x18000f72f  mov     [rbx], rax
0x18000f732  call    ?StartActivity@BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::StartActivity(void)
0x18000f737  mov     rax, rbx
0x18000f73a  add     rsp, 20h
0x18000f73e  pop     rbx
0x18000f73f  retn
```
