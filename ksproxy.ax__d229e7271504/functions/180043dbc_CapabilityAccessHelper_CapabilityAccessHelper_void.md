# CapabilityAccessHelper::~CapabilityAccessHelper(void)

- ea: `0x180043dbc`
- end: `0x180043e27`
- name: `??1CapabilityAccessHelper@@MEAA@XZ`
- size: `107`
- prototype: `void __fastcall(CapabilityAccessHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042f40`

## callees

- `0x1800078ac`
- `0x180007b14`
- `0x1800443d0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180043e0e`
- `KERNEL32!DeleteCriticalSection` at `0x180043e0e`

## pseudocode

```c
void __fastcall CapabilityAccessHelper::~CapabilityAccessHelper(CapabilityAccessHelper *this)
{
  CapabilityAccessHelper *v2; // rcx

  *(_QWORD *)this = &CapabilityAccessHelper::`vftable'{for `IInspectable'};
  v2 = (CapabilityAccessHelper *)((char *)this + 8);
  *(_QWORD *)v2 = &CapabilityAccessHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CapabilityAccessHelper::Shutdown(v2);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)this + 15);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)this + 14);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>((__int64)this);
}

```

## disassembly

```asm
0x180043dbc  push    rbx
0x180043dbe  sub     rsp, 20h
0x180043dc2  mov     rbx, rcx
0x180043dc5  lea     rax, ??_7CapabilityAccessHelper@@6BIInspectable@@@; const CapabilityAccessHelper::`vftable'{for `IInspectable'}
0x180043dcc  mov     [rcx], rax
0x180043dcf  add     rcx, 8; this
0x180043dd3  lea     rax, ??_7CapabilityAccessHelper@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICapabilityAccessHelper@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CapabilityAccessHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'}
0x180043dda  mov     [rcx], rax
0x180043ddd  lea     rax, ??_7CapabilityAccessHelper@@6BIWeakReferenceSource@@@; const CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'}
0x180043de4  mov     [rbx+10h], rax
0x180043de8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICapabilityAccessHelper@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180043def  mov     [rbx+18h], rax
0x180043df3  call    ?Shutdown@CapabilityAccessHelper@@UEAAJXZ; CapabilityAccessHelper::Shutdown(void)
0x180043df8  lea     rcx, [rbx+78h]
0x180043dfc  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180043e01  lea     rcx, [rbx+70h]
0x180043e05  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180043e0a  lea     rcx, [rbx+48h]; lpCriticalSection
0x180043e0e  call    cs:__imp_DeleteCriticalSection
0x180043e15  nop     dword ptr [rax+rax+00h]
0x180043e1a  mov     rcx, rbx
0x180043e1d  add     rsp, 20h
0x180043e21  pop     rbx
0x180043e22  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>(void)
```
