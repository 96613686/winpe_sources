# Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::~BackgroundTaskLaunch(void)

- ea: `0x180010678`
- end: `0x18001069d`
- name: `??1BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010bfc`
- `0x1800114f0`
- `0x1800196a1`
- `0x180019801`

## callees

- `0x18000860c`
- `0x1800087b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::~BackgroundTaskLaunch(
        Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch *this)
{
  *(_QWORD *)this = &Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::`vftable';
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x180010678  push    rbx
0x18001067a  sub     rsp, 20h
0x18001067e  lea     rax, ??_7BackgroundTaskLaunch@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLaunch::`vftable'
0x180010685  mov     rbx, rcx
0x180010688  mov     [rcx], rax
0x18001068b  call    ?Destroy@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010690  mov     rcx, rbx
0x180010693  add     rsp, 20h
0x180010697  pop     rbx
0x180010698  jmp     ??1?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
