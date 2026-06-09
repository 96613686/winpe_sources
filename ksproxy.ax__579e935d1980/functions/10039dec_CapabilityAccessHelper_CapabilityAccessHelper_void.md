# CapabilityAccessHelper::~CapabilityAccessHelper(void)

- ea: `0x10039dec`
- end: `0x10039e36`
- name: `??1CapabilityAccessHelper@@MAE@XZ`
- size: `74`
- prototype: `void __thiscall(CapabilityAccessHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10038920`

## callees

- `0x1000f598`
- `0x100392dd`
- `0x1003a180`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10039e28`
- `KERNEL32!DeleteCriticalSection` at `0x10039e28`

## pseudocode

```c
void __thiscall CapabilityAccessHelper::~CapabilityAccessHelper(CapabilityAccessHelper *this)
{
  *(_DWORD *)this = &CapabilityAccessHelper::`vftable'{for `IInspectable'};
  *((_DWORD *)this + 1) = &CapabilityAccessHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'};
  *((_DWORD *)this + 2) = &CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'};
  *((_DWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CapabilityAccessHelper::Shutdown((CapabilityAccessHelper *)((char *)this + 4));
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>((char *)this + 64);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>((char *)this + 60);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 36));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x10039dec  mov     edi, edi
0x10039dee  push    esi
0x10039def  mov     esi, ecx
0x10039df1  lea     eax, [esi+4]
0x10039df4  mov     dword ptr [esi], offset ??_7CapabilityAccessHelper@@6BIInspectable@@@; const CapabilityAccessHelper::`vftable'{for `IInspectable'}
0x10039dfa  push    eax; this
0x10039dfb  mov     dword ptr [eax], offset ??_7CapabilityAccessHelper@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICapabilityAccessHelper@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CapabilityAccessHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'}
0x10039e01  mov     dword ptr [esi+8], offset ??_7CapabilityAccessHelper@@6BIWeakReferenceSource@@@; const CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'}
0x10039e08  mov     dword ptr [esi+0Ch], offset ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICapabilityAccessHelper@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x10039e0f  call    ?Shutdown@CapabilityAccessHelper@@UAGJXZ; CapabilityAccessHelper::Shutdown(void)
0x10039e14  lea     ecx, [esi+40h]
0x10039e17  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10039e1c  lea     ecx, [esi+3Ch]
0x10039e1f  call    ??1?$com_ptr_t@UICapabilityUsageStatics@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QAE@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsageStatics,wil::err_returncode_policy>(void)
0x10039e24  lea     eax, [esi+24h]
0x10039e27  push    eax; lpCriticalSection
0x10039e28  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x10039e2e  mov     ecx, esi
0x10039e30  pop     esi
0x10039e31  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UAE@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>(void)
```
