# CapabilityAccessHelper::CapabilityAccessHelper(void)

- ea: `0x180042d68`
- end: `0x180042e33`
- name: `??0CapabilityAccessHelper@@QEAA@XZ`
- size: `203`
- prototype: `CapabilityAccessHelper *__fastcall(CapabilityAccessHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180042b4c`

## callees

- `0x180007a1c`
- `0x180042d68`
- `0x180045010`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x180042dfe`
- `KERNEL32!InitializeCriticalSectionEx` at `0x180042dfe`

## pseudocode

```c
CapabilityAccessHelper *__fastcall CapabilityAccessHelper::CapabilityAccessHelper(CapabilityAccessHelper *this)
{
  _QWORD *v1; // rdi
  struct Microsoft::WRL::Details::ModuleBase *v3; // rcx
  CapabilityAccessHelper *result; // rax

  v1 = (_QWORD *)((char *)this + 16);
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>((__int64)this + 16);
  v3 = Microsoft::WRL::Details::ModuleBase::module_;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'};
  *v1 = &CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 8) = 1;
  if ( v3 )
    v3->IncrementObjectCount(v3);
  *(_QWORD *)this = &CapabilityAccessHelper::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &CapabilityAccessHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'};
  *v1 = &CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 72), 0, 0);
  *((_QWORD *)this + 14) = 0;
  result = this;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 34) = 1;
  return result;
}

```

## disassembly

```asm
0x180042d68  mov     [rsp+arg_0], rbx
0x180042d6d  push    rdi
0x180042d6e  sub     rsp, 20h
0x180042d72  lea     rdi, [rcx+10h]
0x180042d76  mov     rbx, rcx
0x180042d79  mov     rcx, rdi
0x180042d7c  call    ??0?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>(void)
0x180042d81  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180042d88  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICapabilityAccessHelper@@VFtmBase@23@@WRL@Microsoft@@6BIInspectable@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `IInspectable'}
0x180042d8f  mov     [rbx], rax
0x180042d92  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICapabilityAccessHelper@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICapabilityAccessHelper@@UIWeakReferenceSource@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'}
0x180042d99  mov     [rbx+8], rax
0x180042d9d  lea     rax, ??_7CapabilityAccessHelper@@6BIWeakReferenceSource@@@; const CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'}
0x180042da4  mov     [rdi], rax
0x180042da7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICapabilityAccessHelper@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180042dae  mov     [rbx+18h], rax
0x180042db2  mov     qword ptr [rbx+40h], 1
0x180042dba  test    rcx, rcx
0x180042dbd  jz      short loc_180042DCB
0x180042dbf  mov     rax, [rcx]
0x180042dc2  mov     rax, [rax+8]
0x180042dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042dcb  lea     rax, ??_7CapabilityAccessHelper@@6BIInspectable@@@; const CapabilityAccessHelper::`vftable'{for `IInspectable'}
0x180042dd2  xor     r8d, r8d; Flags
0x180042dd5  mov     [rbx], rax
0x180042dd8  lea     rcx, [rbx+48h]; lpCriticalSection
0x180042ddc  lea     rax, ??_7CapabilityAccessHelper@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICapabilityAccessHelper@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CapabilityAccessHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'}
0x180042de3  xor     edx, edx; dwSpinCount
0x180042de5  mov     [rbx+8], rax
0x180042de9  lea     rax, ??_7CapabilityAccessHelper@@6BIWeakReferenceSource@@@; const CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'}
0x180042df0  mov     [rdi], rax
0x180042df3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICapabilityAccessHelper@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180042dfa  mov     [rbx+18h], rax
0x180042dfe  call    cs:__imp_InitializeCriticalSectionEx
0x180042e05  nop     dword ptr [rax+rax+00h]
0x180042e0a  mov     qword ptr [rbx+70h], 0
0x180042e12  mov     rax, rbx
0x180042e15  mov     qword ptr [rbx+78h], 0
0x180042e1d  mov     dword ptr [rbx+88h], 1
0x180042e27  mov     rbx, [rsp+28h+arg_0]
0x180042e2c  add     rsp, 20h
0x180042e30  pop     rdi
0x180042e31  retn
```
