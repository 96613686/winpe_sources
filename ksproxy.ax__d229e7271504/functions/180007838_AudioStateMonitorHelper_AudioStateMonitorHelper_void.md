# AudioStateMonitorHelper::~AudioStateMonitorHelper(void)

- ea: `0x180007838`
- end: `0x1800078a3`
- name: `??1AudioStateMonitorHelper@@MEAA@XZ`
- size: `107`
- prototype: `void __fastcall(AudioStateMonitorHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007800`

## callees

- `0x1800078ac`
- `0x180007b14`
- `0x180007e00`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000788a`
- `KERNEL32!DeleteCriticalSection` at `0x18000788a`

## pseudocode

```c
void __fastcall AudioStateMonitorHelper::~AudioStateMonitorHelper(AudioStateMonitorHelper *this)
{
  AudioStateMonitorHelper *v2; // rcx

  *(_QWORD *)this = &AudioStateMonitorHelper::`vftable'{for `IInspectable'};
  v2 = (AudioStateMonitorHelper *)((char *)this + 8);
  *(_QWORD *)v2 = &AudioStateMonitorHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioStateMonitorHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  AudioStateMonitorHelper::Shutdown(v2);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((char *)this + 120);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((char *)this + 112);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x180007838  push    rbx
0x18000783a  sub     rsp, 20h
0x18000783e  mov     rbx, rcx
0x180007841  lea     rax, ??_7AudioStateMonitorHelper@@6BIInspectable@@@; const AudioStateMonitorHelper::`vftable'{for `IInspectable'}
0x180007848  mov     [rcx], rax
0x18000784b  add     rcx, 8; this
0x18000784f  lea     rax, ??_7AudioStateMonitorHelper@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioStateMonitorHelper@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@@; const AudioStateMonitorHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioStateMonitorHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'}
0x180007856  mov     [rcx], rax
0x180007859  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAudioStateMonitorHelper@@VFtmBase@23@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x180007860  mov     [rbx+10h], rax
0x180007864  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAudioStateMonitorHelper@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000786b  mov     [rbx+18h], rax
0x18000786f  call    ?Shutdown@AudioStateMonitorHelper@@UEAAJXZ; AudioStateMonitorHelper::Shutdown(void)
0x180007874  lea     rcx, [rbx+78h]
0x180007878  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18000787d  lea     rcx, [rbx+70h]
0x180007881  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180007886  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000788a  call    cs:__imp_DeleteCriticalSection
0x180007891  nop     dword ptr [rax+rax+00h]
0x180007896  mov     rcx, rbx
0x180007899  add     rsp, 20h
0x18000789d  pop     rbx
0x18000789e  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>(void)
```
