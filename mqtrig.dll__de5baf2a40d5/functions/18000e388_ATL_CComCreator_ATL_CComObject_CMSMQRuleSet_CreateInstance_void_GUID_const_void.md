# ATL::CComCreator<ATL::CComObject<CMSMQRuleSet>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000e388`
- end: `0x18000e481`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQRuleSet@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `249`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000deb0`

## callees

- `0x18000a130`
- `0x18000dc6c`
- `0x18000e388`
- `0x18000ed1c`
- `0x18000fae4`
- `0x18000fb0c`
- `0x180014ae8`
- `0x180022010`

## import_xrefs

- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000e435`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000e435`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQRuleSet>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  HRESULT FreeThreadedMarshaler; // ebx
  CMSMQRuleSet *v7; // rax
  CMSMQRuleSet *v8; // rdi
  IUnknown *v9; // rax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  FreeThreadedMarshaler = -2147024882;
  v7 = (CMSMQRuleSet *)MmAllocate(0x4C0u);
  v8 = v7;
  if ( v7 )
  {
    CMSMQRuleSet::CMSMQRuleSet(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CMSMQRuleSet>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSMQRuleSet>::`vftable'{for `ATL::IDispatchImpl<IMSMQRuleSet,&_GUID const IID_IMSMQRuleSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
    _InterlockedIncrement(&dword_18002CFF8);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 4);
    FreeThreadedMarshaler = ATL::CComAutoDeleteCriticalSection::Init((CMSMQRuleSet *)((char *)v8 + 24));
    if ( FreeThreadedMarshaler >= 0 )
    {
      v9 = (IUnknown *)(*(__int64 (__fastcall **)(CMSMQRuleSet *))(*(_QWORD *)v8 + 32LL))(v8);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v9, (LPUNKNOWN *)v8 + 148);
    }
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 4);
    if ( FreeThreadedMarshaler
      || (FreeThreadedMarshaler = (**(__int64 (__fastcall ***)(CMSMQRuleSet *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
    {
      ATL::CComObject<CMSMQRuleSet>::`scalar deleting destructor'(v8);
    }
  }
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x18000e388  mov     [rsp+arg_8], rbx
0x18000e38d  mov     [rsp+arg_10], rbp
0x18000e392  mov     [rsp+arg_0], rcx
0x18000e397  push    rsi
0x18000e398  push    rdi
0x18000e399  push    r14
0x18000e39b  sub     rsp, 20h
0x18000e39f  mov     r14, r8
0x18000e3a2  mov     rbp, rdx
0x18000e3a5  test    r8, r8
0x18000e3a8  jnz     short loc_18000E3B4
0x18000e3aa  mov     eax, 80004003h
0x18000e3af  jmp     loc_18000E46E
0x18000e3b4  mov     qword ptr [r8], 0
0x18000e3bb  mov     ebx, 8007000Eh
0x18000e3c0  mov     ecx, 4C0h; unsigned __int64
0x18000e3c5  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000e3ca  mov     rdi, rax
0x18000e3cd  mov     [rsp+38h+arg_0], rax
0x18000e3d2  test    rax, rax
0x18000e3d5  jz      short loc_18000E3FD
0x18000e3d7  mov     rcx, rax; this
0x18000e3da  call    ??0CMSMQRuleSet@@QEAA@XZ; CMSMQRuleSet::CMSMQRuleSet(void)
0x18000e3df  lea     rax, ??_7?$CComObject@VCMSMQRuleSet@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQRuleSet>::`vftable'{for `ISupportErrorInfo'}
0x18000e3e6  mov     [rdi], rax
0x18000e3e9  lea     rax, ??_7?$CComObject@VCMSMQRuleSet@@@ATL@@6B?$IDispatchImpl@UIMSMQRuleSet@@$1?IID_IMSMQRuleSet@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQRuleSet>::`vftable'{for `ATL::IDispatchImpl<IMSMQRuleSet,&_GUID const IID_IMSMQRuleSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000e3f0  mov     [rdi+8], rax
0x18000e3f4  lock inc cs:dword_18002CFF8
0x18000e3fb  jmp     short loc_18000E3FF
0x18000e3fd  xor     edi, edi
0x18000e3ff  test    rdi, rdi
0x18000e402  jz      short loc_18000E46C
0x18000e404  lea     rcx, [rdi+10h]; volatile int *
0x18000e408  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000e40d  lea     rcx, [rdi+18h]; this
0x18000e411  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000e416  mov     ebx, eax
0x18000e418  test    eax, eax
0x18000e41a  js      short loc_18000E43D
0x18000e41c  mov     rax, [rdi]
0x18000e41f  mov     rcx, rdi
0x18000e422  mov     rax, [rax+20h]
0x18000e426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e42b  mov     rcx, rax; punkOuter
0x18000e42e  lea     rdx, [rdi+4A0h]; ppunkMarshal
0x18000e435  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000e43b  mov     ebx, eax
0x18000e43d  lea     rcx, [rdi+10h]; volatile int *
0x18000e441  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000e446  test    ebx, ebx
0x18000e448  jnz     short loc_18000E464
0x18000e44a  mov     rax, [rdi]
0x18000e44d  mov     r8, r14
0x18000e450  mov     rdx, rbp
0x18000e453  mov     rcx, rdi
0x18000e456  mov     rax, [rax]
0x18000e459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e45e  mov     ebx, eax
0x18000e460  test    eax, eax
0x18000e462  jz      short loc_18000E46C
0x18000e464  mov     rcx, rdi; Block
0x18000e467  call    ??_G?$CComObject@VCMSMQRuleSet@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQRuleSet>::`scalar deleting destructor'(uint)
0x18000e46c  mov     eax, ebx
0x18000e46e  mov     rbx, [rsp+38h+arg_8]
0x18000e473  mov     rbp, [rsp+38h+arg_10]
0x18000e478  add     rsp, 20h
0x18000e47c  pop     r14
0x18000e47e  pop     rdi
0x18000e47f  pop     rsi
0x18000e480  retn
```
