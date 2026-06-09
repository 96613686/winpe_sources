# ATL::CComCreator<ATL::CComAggObject<CMSMQManagement>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d0c0`
- end: `0x18000d1b6`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQManagement@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cbf0`

## callees

- `0x18000173c`
- `0x18000b2b8`
- `0x18000d0c0`
- `0x18000e7a8`
- `0x18000f34c`
- `0x180022904`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQManagement>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  HRESULT v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = operator new(0xC0u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQManagement>::`vftable';
    CMSMQManagement::CMSMQManagement((CMSMQManagement *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQManagement>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQManagement,&_GUID const IID_IMSMQManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v9[5] = &ATL::CComContainedObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQOutgoingQueueManagement,&_GUID const IID_IMSMQOutgoingQueueManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v9[6] = &ATL::CComContainedObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQQueueManagement,&_GUID const IID_IMSMQQueueManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v9[7] = a1;
    _InterlockedIncrement(&dword_180038608);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    v10 = ATL::CComAutoDeleteCriticalSection::Init((ATL::CComAutoDeleteCriticalSection *)(v9 + 8));
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 < 0
      || (v7 = CMSMQManagement::FinalConstruct((CMSMQManagement *)(v9 + 3))) != 0
      || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
    {
      ATL::CComAggObject<CMSMQManagement>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d0c0  push    rbx
0x18000d0c2  push    rbp
0x18000d0c3  push    rsi
0x18000d0c4  push    rdi
0x18000d0c5  push    r14
0x18000d0c7  push    r15
0x18000d0c9  sub     rsp, 28h
0x18000d0cd  mov     r14, r8
0x18000d0d0  mov     r15, rdx
0x18000d0d3  mov     rbp, rcx
0x18000d0d6  test    r8, r8
0x18000d0d9  jnz     short loc_18000D0E5
0x18000d0db  mov     eax, 80004003h
0x18000d0e0  jmp     loc_18000D1A9
0x18000d0e5  mov     qword ptr [r8], 0
0x18000d0ec  mov     esi, 8007000Eh
0x18000d0f1  mov     ecx, 0C0h; Size
0x18000d0f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d0fb  mov     rdi, rax
0x18000d0fe  mov     [rsp+58h+arg_10], rax
0x18000d103  test    rax, rax
0x18000d106  jz      short loc_18000D15B
0x18000d108  mov     dword ptr [rax+8], 0
0x18000d10f  lea     rax, ??_7?$CComAggObject@VCMSMQManagement@@@ATL@@6B@; const ATL::CComAggObject<CMSMQManagement>::`vftable'
0x18000d116  mov     [rdi], rax
0x18000d119  lea     rcx, [rdi+18h]; this
0x18000d11d  call    ??0CMSMQManagement@@QEAA@XZ; CMSMQManagement::CMSMQManagement(void)
0x18000d122  lea     rax, ??_7?$CComContainedObject@VCMSMQManagement@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQManagement>::`vftable'{for `ISupportErrorInfo'}
0x18000d129  mov     [rdi+18h], rax
0x18000d12d  lea     rax, ??_7?$CComContainedObject@VCMSMQManagement@@@ATL@@6B?$IDispatchImpl@UIMSMQManagement@@$1?IID_IMSMQManagement@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQManagement,&_GUID const IID_IMSMQManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d134  mov     [rdi+20h], rax
0x18000d138  lea     rax, ??_7?$CComContainedObject@VCMSMQManagement@@@ATL@@6B?$IDispatchImpl@UIMSMQOutgoingQueueManagement@@$1?IID_IMSMQOutgoingQueueManagement@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQOutgoingQueueManagement,&_GUID const IID_IMSMQOutgoingQueueManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d13f  mov     [rdi+28h], rax
0x18000d143  lea     rax, ??_7?$CComContainedObject@VCMSMQManagement@@@ATL@@6B?$IDispatchImpl@UIMSMQQueueManagement@@$1?IID_IMSMQQueueManagement@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQQueueManagement,&_GUID const IID_IMSMQQueueManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d14a  mov     [rdi+30h], rax
0x18000d14e  mov     [rdi+38h], rbp
0x18000d152  lock inc cs:dword_180038608
0x18000d159  jmp     short loc_18000D15D
0x18000d15b  xor     edi, edi
0x18000d15d  test    rdi, rdi
0x18000d160  jz      short loc_18000D1A7
0x18000d162  lea     rcx, [rdi+40h]; this
0x18000d166  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000d16b  xor     esi, esi
0x18000d16d  test    eax, eax
0x18000d16f  cmovs   esi, eax
0x18000d172  test    esi, esi
0x18000d174  js      short loc_18000D19F
0x18000d176  lea     rcx, [rdi+18h]; this
0x18000d17a  call    ?FinalConstruct@CMSMQManagement@@QEAAJXZ; CMSMQManagement::FinalConstruct(void)
0x18000d17f  mov     esi, eax
0x18000d181  test    eax, eax
0x18000d183  jnz     short loc_18000D19F
0x18000d185  mov     rax, [rdi]
0x18000d188  mov     r8, r14
0x18000d18b  mov     rdx, r15
0x18000d18e  mov     rcx, rdi
0x18000d191  mov     rax, [rax]
0x18000d194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d199  mov     esi, eax
0x18000d19b  test    eax, eax
0x18000d19d  jz      short loc_18000D1A7
0x18000d19f  mov     rcx, rdi; Block
0x18000d1a2  call    ??_G?$CComAggObject@VCMSMQManagement@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQManagement>::`scalar deleting destructor'(uint)
0x18000d1a7  mov     eax, esi
0x18000d1a9  add     rsp, 28h
0x18000d1ad  pop     r15
0x18000d1af  pop     r14
0x18000d1b1  pop     rdi
0x18000d1b2  pop     rsi
0x18000d1b3  pop     rbp
0x18000d1b4  pop     rbx
0x18000d1b5  retn
```
