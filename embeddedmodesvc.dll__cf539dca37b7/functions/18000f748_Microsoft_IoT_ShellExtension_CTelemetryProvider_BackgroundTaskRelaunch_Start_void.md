# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch::Start<>(void)

- ea: `0x18000f748`
- end: `0x18000f778`
- name: `??$Start@$$V@BackgroundTaskRelaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@SA?AV01234@XZ`
- size: `48`
- prototype: `Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch *__fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010acc`

## callees

- `0x18000854c`
- `0x180013a98`

## string_xrefs

- `0x18000f74e`: `BackgroundTaskRelaunch`

## pseudocode

```c
Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch *__fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch::Start<>(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch *this)
{
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    this,
    "BackgroundTaskRelaunch");
  *(_QWORD *)this = &Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch::`vftable';
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch::StartActivity(this);
  return this;
}

```

## disassembly

```asm
0x18000f748  push    rbx
0x18000f74a  sub     rsp, 20h
0x18000f74e  lea     rdx, aBackgroundtask_5; "BackgroundTaskRelaunch"
0x18000f755  mov     rbx, rcx
0x18000f758  call    ??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000f75d  lea     rax, ??_7BackgroundTaskRelaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch::`vftable'
0x18000f764  mov     rcx, rbx; this
0x18000f767  mov     [rbx], rax
0x18000f76a  call    ?StartActivity@BackgroundTaskRelaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskRelaunch::StartActivity(void)
0x18000f76f  mov     rax, rbx
0x18000f772  add     rsp, 20h
0x18000f776  pop     rbx
0x18000f777  retn
```
