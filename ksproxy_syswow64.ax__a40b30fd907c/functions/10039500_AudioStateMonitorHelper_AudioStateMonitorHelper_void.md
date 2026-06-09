# AudioStateMonitorHelper::~AudioStateMonitorHelper(void)

- ea: `0x10039500`
- end: `0x1003954a`
- name: `??1AudioStateMonitorHelper@@MAE@XZ`
- size: `74`
- prototype: `void __thiscall(AudioStateMonitorHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100388f0`

## callees

- `0x1000f598`
- `0x100392dd`
- `0x10039880`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1003953c`
- `KERNEL32!DeleteCriticalSection` at `0x1003953c`

## pseudocode

```c
void __thiscall AudioStateMonitorHelper::~AudioStateMonitorHelper(AudioStateMonitorHelper *this)
{
  *(_DWORD *)this = &AudioStateMonitorHelper::`vftable'{for `IInspectable'};
  *((_DWORD *)this + 1) = &AudioStateMonitorHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioStateMonitorHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'};
  *((_DWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
  *((_DWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  AudioStateMonitorHelper::Shutdown((AudioStateMonitorHelper *)((char *)this + 4));
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>((int *)this + 16);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>((int *)this + 15);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 36));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>((int *)this);
}

```

## disassembly

```asm
0x10039500  mov     edi, edi
0x10039502  push    esi
0x10039503  mov     esi, ecx
0x10039505  lea     eax, [esi+4]
0x10039508  mov     dword ptr [esi], offset ??_7AudioStateMonitorHelper@@6BIInspectable@@@; const AudioStateMonitorHelper::`vftable'{for `IInspectable'}
0x1003950e  push    eax; this
0x1003950f  mov     dword ptr [eax], offset ??_7AudioStateMonitorHelper@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAudioStateMonitorHelper@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@@; const AudioStateMonitorHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IAudioStateMonitorHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'}
0x10039515  mov     dword ptr [esi+8], offset ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAudioStateMonitorHelper@@VFtmBase@23@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x1003951c  mov     dword ptr [esi+0Ch], offset ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIAudioStateMonitorHelper@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IAudioStateMonitorHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x10039523  call    ?Shutdown@AudioStateMonitorHelper@@UAGJXZ; AudioStateMonitorHelper::Shutdown(void)
0x10039528  lea     ecx, [esi+40h]
0x1003952b  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10039530  lea     ecx, [esi+3Ch]
0x10039533  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10039538  lea     eax, [esi+24h]
0x1003953b  push    eax; lpCriticalSection
0x1003953c  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10039542  mov     ecx, esi
0x10039544  pop     esi
0x10039545  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UAE@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>(void)
```
