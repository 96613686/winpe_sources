# ATL::CComCreator<ATL::CComAggObject<CMSMQTriggerSet>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000e0e4`
- end: `0x18000e1c4`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQTriggerSet@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000dee0`

## callees

- `0x18000dbf4`
- `0x18000e0e4`
- `0x18000e83c`
- `0x18000ed1c`
- `0x180010390`
- `0x180014ae8`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQTriggerSet>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = MmAllocate(0x4D8u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQTriggerSet>::`vftable';
    CMSMQTriggerSet::CMSMQTriggerSet((CMSMQTriggerSet *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQTriggerSet>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQTriggerSet>::`vftable'{for `ATL::IDispatchImpl<IMSMQTriggerSet,&_GUID const IID_IMSMQTriggerSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'};
    v9[5] = a1;
    _InterlockedIncrement(&dword_18002CFF8);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v10 = ATL::CComAutoDeleteCriticalSection::Init((ATL::CComAutoDeleteCriticalSection *)(v9 + 6));
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 < 0
      || (v7 = CMSMQTriggerSet::FinalConstruct((CMSMQTriggerSet *)(v9 + 3))) != 0
      || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
    {
      ATL::CComAggObject<CMSMQTriggerSet>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e0e4  push    rbx
0x18000e0e6  push    rbp
0x18000e0e7  push    rsi
0x18000e0e8  push    rdi
0x18000e0e9  push    r14
0x18000e0eb  push    r15
0x18000e0ed  sub     rsp, 28h
0x18000e0f1  mov     r14, r8
0x18000e0f4  mov     r15, rdx
0x18000e0f7  mov     rbp, rcx
0x18000e0fa  test    r8, r8
0x18000e0fd  jnz     short loc_18000E109
0x18000e0ff  mov     eax, 80004003h
0x18000e104  jmp     loc_18000E1B7
0x18000e109  mov     qword ptr [r8], 0
0x18000e110  mov     esi, 8007000Eh
0x18000e115  mov     ecx, 4D8h; unsigned __int64
0x18000e11a  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000e11f  mov     rdi, rax
0x18000e122  mov     [rsp+58h+arg_10], rax
0x18000e127  test    rax, rax
0x18000e12a  jz      short loc_18000E169
0x18000e12c  mov     dword ptr [rax+8], 0
0x18000e133  lea     rax, ??_7?$CComAggObject@VCMSMQTriggerSet@@@ATL@@6B@; const ATL::CComAggObject<CMSMQTriggerSet>::`vftable'
0x18000e13a  mov     [rdi], rax
0x18000e13d  lea     rcx, [rdi+18h]; this
0x18000e141  call    ??0CMSMQTriggerSet@@QEAA@XZ; CMSMQTriggerSet::CMSMQTriggerSet(void)
0x18000e146  lea     rax, ??_7?$CComContainedObject@VCMSMQTriggerSet@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQTriggerSet>::`vftable'{for `ISupportErrorInfo'}
0x18000e14d  mov     [rdi+18h], rax
0x18000e151  lea     rax, ??_7?$CComContainedObject@VCMSMQTriggerSet@@@ATL@@6B?$IDispatchImpl@UIMSMQTriggerSet@@$1?IID_IMSMQTriggerSet@@3U_GUID@@B$1?LIBID_MSMQTriggerObjects@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQTriggerSet>::`vftable'{for `ATL::IDispatchImpl<IMSMQTriggerSet,&_GUID const IID_IMSMQTriggerSet,&_GUID const LIBID_MSMQTriggerObjects,1,0,ATL::CComTypeInfoHolder>'}
0x18000e158  mov     [rdi+20h], rax
0x18000e15c  mov     [rdi+28h], rbp
0x18000e160  lock inc cs:dword_18002CFF8
0x18000e167  jmp     short loc_18000E16B
0x18000e169  xor     edi, edi
0x18000e16b  test    rdi, rdi
0x18000e16e  jz      short loc_18000E1B5
0x18000e170  lea     rcx, [rdi+30h]; this
0x18000e174  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000e179  xor     esi, esi
0x18000e17b  test    eax, eax
0x18000e17d  cmovs   esi, eax
0x18000e180  test    esi, esi
0x18000e182  js      short loc_18000E1AD
0x18000e184  lea     rcx, [rdi+18h]; this
0x18000e188  call    ?FinalConstruct@CMSMQTriggerSet@@QEAAJXZ; CMSMQTriggerSet::FinalConstruct(void)
0x18000e18d  mov     esi, eax
0x18000e18f  test    eax, eax
0x18000e191  jnz     short loc_18000E1AD
0x18000e193  mov     rax, [rdi]
0x18000e196  mov     r8, r14
0x18000e199  mov     rdx, r15
0x18000e19c  mov     rcx, rdi
0x18000e19f  mov     rax, [rax]
0x18000e1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1a7  mov     esi, eax
0x18000e1a9  test    eax, eax
0x18000e1ab  jz      short loc_18000E1B5
0x18000e1ad  mov     rcx, rdi; Block
0x18000e1b0  call    ??_G?$CComAggObject@VCMSMQTriggerSet@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQTriggerSet>::`scalar deleting destructor'(uint)
0x18000e1b5  mov     eax, esi
0x18000e1b7  add     rsp, 28h
0x18000e1bb  pop     r15
0x18000e1bd  pop     r14
0x18000e1bf  pop     rdi
0x18000e1c0  pop     rsi
0x18000e1c1  pop     rbp
0x18000e1c2  pop     rbx
0x18000e1c3  retn
```
