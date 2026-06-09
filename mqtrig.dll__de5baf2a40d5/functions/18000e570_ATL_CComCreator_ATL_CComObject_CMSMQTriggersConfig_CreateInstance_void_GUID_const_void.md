# ATL::CComCreator<ATL::CComObject<CMSMQTriggersConfig>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000e570`
- end: `0x18000e689`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQTriggersConfig@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `281`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000df00`

## callees

- `0x18000dcbc`
- `0x18000e570`
- `0x18000ed1c`
- `0x18000fae4`
- `0x18000fb0c`
- `0x180014ae8`
- `0x180022010`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x18000e5e3`
- `ATL!__imp_AtlComPtrAssign` at `0x18000e5e3`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000e63d`
- `ole32!CoCreateFreeThreadedMarshaler` at `0x18000e63d`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQTriggersConfig>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  HRESULT FreeThreadedMarshaler; // ebx
  char *v7; // rax
  CMSMQTriggersConfig *v8; // rdi
  IUnknown *v9; // rax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  FreeThreadedMarshaler = -2147024882;
  v7 = (char *)MmAllocate(0x50u);
  v8 = (CMSMQTriggersConfig *)v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 4) = 0;
    *(_OWORD *)(v7 + 24) = 0;
    *(_OWORD *)(v7 + 40) = 0;
    *((_QWORD *)v7 + 7) = 0;
    v7[64] = 0;
    *((_QWORD *)v7 + 9) = 0;
    AtlComPtrAssign(v7 + 72, 0);
    *(_QWORD *)v8 = &ATL::CComObject<CMSMQTriggersConfig>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSMQTriggersConfig>::`vftable'{for `ATL::IDispatchImpl<IMSMQTriggersConfig,&_GUID const IID_IMSMQTriggersConfig,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
    _InterlockedIncrement(&dword_18002CFF8);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    ATL::SafeIncrementReferenceMultiThread((volatile int *)v8 + 4);
    FreeThreadedMarshaler = ATL::CComAutoDeleteCriticalSection::Init((CMSMQTriggersConfig *)((char *)v8 + 24));
    if ( FreeThreadedMarshaler >= 0 )
    {
      v9 = (IUnknown *)(*(__int64 (__fastcall **)(CMSMQTriggersConfig *))(*(_QWORD *)v8 + 32LL))(v8);
      FreeThreadedMarshaler = CoCreateFreeThreadedMarshaler(v9, (LPUNKNOWN *)v8 + 9);
    }
    ATL::SafeDecrementReferenceMultiThread((volatile int *)v8 + 4);
    if ( FreeThreadedMarshaler
      || (FreeThreadedMarshaler = (**(__int64 (__fastcall ***)(CMSMQTriggersConfig *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
    {
      ATL::CComObject<CMSMQTriggersConfig>::`scalar deleting destructor'(v8);
    }
  }
  return (unsigned int)FreeThreadedMarshaler;
}

```

## disassembly

```asm
0x18000e570  mov     [rsp+arg_8], rbx
0x18000e575  mov     [rsp+arg_10], rbp
0x18000e57a  mov     [rsp+arg_0], rcx
0x18000e57f  push    rsi
0x18000e580  push    rdi
0x18000e581  push    r14
0x18000e583  sub     rsp, 20h
0x18000e587  mov     r14, r8
0x18000e58a  mov     rbp, rdx
0x18000e58d  test    r8, r8
0x18000e590  jnz     short loc_18000E59C
0x18000e592  mov     eax, 80004003h
0x18000e597  jmp     loc_18000E676
0x18000e59c  mov     qword ptr [r8], 0
0x18000e5a3  mov     ebx, 8007000Eh
0x18000e5a8  mov     ecx, 50h ; 'P'; unsigned __int64
0x18000e5ad  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000e5b2  mov     rdi, rax
0x18000e5b5  mov     [rsp+38h+arg_0], rax
0x18000e5ba  test    rax, rax
0x18000e5bd  jz      short loc_18000E608
0x18000e5bf  mov     dword ptr [rax+10h], 0
0x18000e5c6  xorps   xmm0, xmm0
0x18000e5c9  xor     eax, eax
0x18000e5cb  movups  xmmword ptr [rdi+18h], xmm0
0x18000e5cf  movups  xmmword ptr [rdi+28h], xmm0
0x18000e5d3  mov     [rdi+38h], rax
0x18000e5d7  mov     [rdi+40h], al
0x18000e5da  lea     rcx, [rdi+48h]
0x18000e5de  mov     [rcx], rax
0x18000e5e1  xor     edx, edx
0x18000e5e3  call    cs:__imp_AtlComPtrAssign
0x18000e5e9  nop
0x18000e5ea  lea     rax, ??_7?$CComObject@VCMSMQTriggersConfig@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQTriggersConfig>::`vftable'{for `ISupportErrorInfo'}
0x18000e5f1  mov     [rdi], rax
0x18000e5f4  lea     rax, ??_7?$CComObject@VCMSMQTriggersConfig@@@ATL@@6B?$IDispatchImpl@UIMSMQTriggersConfig@@$1?IID_IMSMQTriggersConfig@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQTriggersConfig>::`vftable'{for `ATL::IDispatchImpl<IMSMQTriggersConfig,&_GUID const IID_IMSMQTriggersConfig,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000e5fb  mov     [rdi+8], rax
0x18000e5ff  lock inc cs:dword_18002CFF8
0x18000e606  jmp     short loc_18000E60A
0x18000e608  xor     edi, edi
0x18000e60a  test    rdi, rdi
0x18000e60d  jz      short loc_18000E674
0x18000e60f  lea     rcx, [rdi+10h]; volatile int *
0x18000e613  call    ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
0x18000e618  lea     rcx, [rdi+18h]; this
0x18000e61c  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000e621  mov     ebx, eax
0x18000e623  test    eax, eax
0x18000e625  js      short loc_18000E645
0x18000e627  mov     rax, [rdi]
0x18000e62a  mov     rcx, rdi
0x18000e62d  mov     rax, [rax+20h]
0x18000e631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e636  mov     rcx, rax; punkOuter
0x18000e639  lea     rdx, [rdi+48h]; ppunkMarshal
0x18000e63d  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000e643  mov     ebx, eax
0x18000e645  lea     rcx, [rdi+10h]; volatile int *
0x18000e649  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeDecrementReferenceMultiThread(long volatile *)
0x18000e64e  test    ebx, ebx
0x18000e650  jnz     short loc_18000E66C
0x18000e652  mov     rax, [rdi]
0x18000e655  mov     r8, r14
0x18000e658  mov     rdx, rbp
0x18000e65b  mov     rcx, rdi
0x18000e65e  mov     rax, [rax]
0x18000e661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e666  mov     ebx, eax
0x18000e668  test    eax, eax
0x18000e66a  jz      short loc_18000E674
0x18000e66c  mov     rcx, rdi; Block
0x18000e66f  call    ??_G?$CComObject@VCMSMQTriggersConfig@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQTriggersConfig>::`scalar deleting destructor'(uint)
0x18000e674  mov     eax, ebx
0x18000e676  mov     rbx, [rsp+38h+arg_8]
0x18000e67b  mov     rbp, [rsp+38h+arg_10]
0x18000e680  add     rsp, 20h
0x18000e684  pop     r14
0x18000e686  pop     rdi
0x18000e687  pop     rsi
0x18000e688  retn
```
