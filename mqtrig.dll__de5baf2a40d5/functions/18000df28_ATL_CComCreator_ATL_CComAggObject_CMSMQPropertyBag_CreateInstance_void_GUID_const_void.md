# ATL::CComCreator<ATL::CComAggObject<CMSMQPropertyBag>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000df28`
- end: `0x18000dff4`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQPropertyBag@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `204`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000de70`

## callees

- `0x180002f08`
- `0x18000dba4`
- `0x18000df28`
- `0x18000e7dc`
- `0x180014ae8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQPropertyBag>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = MmAllocate(0x48u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQPropertyBag>::`vftable';
    CMSMQPropertyBag::CMSMQPropertyBag((CMSMQPropertyBag *)(v8 + 2));
    v9[2] = &ATL::CComContainedObject<CMSMQPropertyBag>::`vftable'{for `ISupportErrorInfo'};
    v9[3] = &ATL::CComContainedObject<CMSMQPropertyBag>::`vftable'{for `ATL::IDispatchImpl<IMSMQPropertyBag,&_GUID const IID_IMSMQPropertyBag,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
    v9[4] = a1;
    _InterlockedIncrement(&dword_18002CFF8);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v7 = CMSMQPropertyBag::FinalConstruct((CMSMQPropertyBag *)(v9 + 2));
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
      ATL::CComAggObject<CMSMQPropertyBag>::`scalar deleting destructor'(v9);
  }
  return v7;
}

```

## disassembly

```asm
0x18000df28  push    rbx
0x18000df2a  push    rbp
0x18000df2b  push    rsi
0x18000df2c  push    rdi
0x18000df2d  push    r14
0x18000df2f  push    r15
0x18000df31  sub     rsp, 28h
0x18000df35  mov     r14, r8
0x18000df38  mov     r15, rdx
0x18000df3b  mov     rbp, rcx
0x18000df3e  test    r8, r8
0x18000df41  jnz     short loc_18000DF4D
0x18000df43  mov     eax, 80004003h
0x18000df48  jmp     loc_18000DFE7
0x18000df4d  mov     qword ptr [r8], 0
0x18000df54  mov     esi, 8007000Eh
0x18000df59  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000df5e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000df63  mov     rdi, rax
0x18000df66  mov     [rsp+58h+arg_10], rax
0x18000df6b  test    rax, rax
0x18000df6e  jz      short loc_18000DFAD
0x18000df70  mov     dword ptr [rax+8], 0
0x18000df77  lea     rax, ??_7?$CComAggObject@VCMSMQPropertyBag@@@ATL@@6B@; const ATL::CComAggObject<CMSMQPropertyBag>::`vftable'
0x18000df7e  mov     [rdi], rax
0x18000df81  lea     rcx, [rdi+10h]; this
0x18000df85  call    ??0CMSMQPropertyBag@@QEAA@XZ; CMSMQPropertyBag::CMSMQPropertyBag(void)
0x18000df8a  lea     rax, ??_7?$CComContainedObject@VCMSMQPropertyBag@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQPropertyBag>::`vftable'{for `ISupportErrorInfo'}
0x18000df91  mov     [rdi+10h], rax
0x18000df95  lea     rax, ??_7?$CComContainedObject@VCMSMQPropertyBag@@@ATL@@6B?$IDispatchImpl@UIMSMQPropertyBag@@$1?IID_IMSMQPropertyBag@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQPropertyBag>::`vftable'{for `ATL::IDispatchImpl<IMSMQPropertyBag,&_GUID const IID_IMSMQPropertyBag,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000df9c  mov     [rdi+18h], rax
0x18000dfa0  mov     [rdi+20h], rbp
0x18000dfa4  lock inc cs:dword_18002CFF8
0x18000dfab  jmp     short loc_18000DFAF
0x18000dfad  xor     edi, edi
0x18000dfaf  test    rdi, rdi
0x18000dfb2  jz      short loc_18000DFE5
0x18000dfb4  lea     rcx, [rdi+10h]; this
0x18000dfb8  call    ?FinalConstruct@CMSMQPropertyBag@@QEAAJXZ; CMSMQPropertyBag::FinalConstruct(void)
0x18000dfbd  mov     esi, eax
0x18000dfbf  test    eax, eax
0x18000dfc1  jnz     short loc_18000DFDD
0x18000dfc3  mov     rax, [rdi]
0x18000dfc6  mov     r8, r14
0x18000dfc9  mov     rdx, r15
0x18000dfcc  mov     rcx, rdi
0x18000dfcf  mov     rax, [rax]
0x18000dfd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd7  mov     esi, eax
0x18000dfd9  test    eax, eax
0x18000dfdb  jz      short loc_18000DFE5
0x18000dfdd  mov     rcx, rdi; Block
0x18000dfe0  call    ??_G?$CComAggObject@VCMSMQPropertyBag@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQPropertyBag>::`scalar deleting destructor'(uint)
0x18000dfe5  mov     eax, esi
0x18000dfe7  add     rsp, 28h
0x18000dfeb  pop     r15
0x18000dfed  pop     r14
0x18000dfef  pop     rdi
0x18000dff0  pop     rsi
0x18000dff1  pop     rbp
0x18000dff2  pop     rbx
0x18000dff3  retn
```
