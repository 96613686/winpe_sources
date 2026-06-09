# CapabilityAccessHelper::CapabilityAccessHelper(void)

- ea: `0x1003872f`
- end: `0x100387b6`
- name: `??0CapabilityAccessHelper@@QAE@XZ`
- size: `135`
- prototype: `CapabilityAccessHelper *__thiscall(CapabilityAccessHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10038410`

## callees

- `0x1002d510`
- `0x1003872f`
- `0x10038fb5`

## import_xrefs

- `KERNEL32!InitializeCriticalSectionEx` at `0x1003879d`
- `KERNEL32!InitializeCriticalSectionEx` at `0x1003879d`

## pseudocode

```c
CapabilityAccessHelper *__thiscall CapabilityAccessHelper::CapabilityAccessHelper(CapabilityAccessHelper *this)
{
  _DWORD *v2; // ebx
  struct Microsoft::WRL::Details::ModuleBase *v3; // ecx
  CapabilityAccessHelper *result; // eax

  v2 = (_DWORD *)((char *)this + 12);
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)((char *)this + 12));
  v3 = Microsoft::WRL::Details::ModuleBase::module_;
  *((_DWORD *)this + 8) = 1;
  *(_DWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `IInspectable'};
  *((_DWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'};
  *((_DWORD *)this + 2) = &CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'};
  *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( v3 )
    ((void (__thiscall *)(unsigned int (__stdcall *)(Microsoft::WRL::Details::ModuleBase *), struct Microsoft::WRL::Details::ModuleBase *))v3->IncrementObjectCount)(
      v3->IncrementObjectCount,
      v3);
  *(_DWORD *)this = &CapabilityAccessHelper::`vftable'{for `IInspectable'};
  *((_DWORD *)this + 1) = &CapabilityAccessHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'};
  *((_DWORD *)this + 2) = &CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'};
  *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 36), 0, 0);
  *((_DWORD *)this + 15) = 0;
  result = this;
  *((_DWORD *)this + 16) = 0;
  *((_DWORD *)this + 20) = 1;
  return result;
}

```

## disassembly

```asm
0x1003872f  mov     edi, edi
0x10038731  push    ebx
0x10038732  push    esi
0x10038733  push    edi
0x10038734  mov     edi, ecx
0x10038736  lea     ebx, [edi+0Ch]
0x10038739  mov     ecx, ebx; this
0x1003873b  call    ??0FtmBase@WRL@Microsoft@@QAE@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x10038740  mov     ecx, ?module_@ModuleBase@Details@WRL@Microsoft@@2PAV1234@A; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x10038746  mov     dword ptr [edi+20h], 1
0x1003874d  mov     dword ptr [edi], offset ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICapabilityAccessHelper@@VFtmBase@23@@WRL@Microsoft@@6BIInspectable@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `IInspectable'}
0x10038753  mov     dword ptr [edi+4], offset ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICapabilityAccessHelper@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICapabilityAccessHelper@@UIWeakReferenceSource@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'}
0x1003875a  mov     dword ptr [edi+8], offset ??_7CapabilityAccessHelper@@6BIWeakReferenceSource@@@; const CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'}
0x10038761  mov     dword ptr [ebx], offset ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICapabilityAccessHelper@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x10038767  test    ecx, ecx
0x10038769  jz      short loc_1003877B
0x1003876b  mov     eax, [ecx]
0x1003876d  push    ecx
0x1003876e  mov     esi, [eax+4]
0x10038771  mov     ecx, esi; this
0x10038773  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10038779  call    esi
0x1003877b  xor     esi, esi
0x1003877d  mov     dword ptr [edi], offset ??_7CapabilityAccessHelper@@6BIInspectable@@@; const CapabilityAccessHelper::`vftable'{for `IInspectable'}
0x10038783  push    esi; Flags
0x10038784  push    esi; dwSpinCount
0x10038785  lea     eax, [edi+24h]
0x10038788  mov     dword ptr [edi+4], offset ??_7CapabilityAccessHelper@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UICapabilityAccessHelper@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CapabilityAccessHelper::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,ICapabilityAccessHelper,IWeakReferenceSource,Microsoft::WRL::FtmBase>'}
0x1003878f  push    eax; lpCriticalSection
0x10038790  mov     dword ptr [edi+8], offset ??_7CapabilityAccessHelper@@6BIWeakReferenceSource@@@; const CapabilityAccessHelper::`vftable'{for `IWeakReferenceSource'}
0x10038797  mov     dword ptr [ebx], offset ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UICapabilityAccessHelper@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1003879d  call    ds:__imp__InitializeCriticalSectionEx@12; InitializeCriticalSectionEx(x,x,x)
0x100387a3  mov     [edi+3Ch], esi
0x100387a6  mov     eax, edi
0x100387a8  mov     [edi+40h], esi
0x100387ab  mov     dword ptr [edi+50h], 1
0x100387b2  pop     edi
0x100387b3  pop     esi
0x100387b4  pop     ebx
0x100387b5  retn
```
