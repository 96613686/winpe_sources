# ATL::CComCreator<ATL::CComAggObject<CMSMQTransaction>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d644`
- end: `0x18000d724`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQTransaction@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ccb0`

## callees

- `0x18000173c`
- `0x18000b3a8`
- `0x18000d644`
- `0x18000e748`
- `0x18000f34c`
- `0x180020154`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQTransaction>>::CreateInstance(
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
  v8 = operator new(0x98u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQTransaction>::`vftable';
    CMSMQTransaction::CMSMQTransaction((CMSMQTransaction *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQTransaction>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQTransaction>::`vftable'{for `ATL::IDispatchImpl<IMSMQTransaction3,&_GUID const IID_IMSMQTransaction3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v9[5] = a1;
    _InterlockedIncrement(&dword_180038608);
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
      || (v7 = CMSMQQuery::FinalConstruct((CMSMQQuery *)(v9 + 3))) != 0
      || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
    {
      ATL::CComAggObject<CMSMQTransaction>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d644  push    rbx
0x18000d646  push    rbp
0x18000d647  push    rsi
0x18000d648  push    rdi
0x18000d649  push    r14
0x18000d64b  push    r15
0x18000d64d  sub     rsp, 28h
0x18000d651  mov     r14, r8
0x18000d654  mov     r15, rdx
0x18000d657  mov     rbp, rcx
0x18000d65a  test    r8, r8
0x18000d65d  jnz     short loc_18000D669
0x18000d65f  mov     eax, 80004003h
0x18000d664  jmp     loc_18000D717
0x18000d669  mov     qword ptr [r8], 0
0x18000d670  mov     esi, 8007000Eh
0x18000d675  mov     ecx, 98h; Size
0x18000d67a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d67f  mov     rdi, rax
0x18000d682  mov     [rsp+58h+arg_10], rax
0x18000d687  test    rax, rax
0x18000d68a  jz      short loc_18000D6C9
0x18000d68c  mov     dword ptr [rax+8], 0
0x18000d693  lea     rax, ??_7?$CComAggObject@VCMSMQTransaction@@@ATL@@6B@; const ATL::CComAggObject<CMSMQTransaction>::`vftable'
0x18000d69a  mov     [rdi], rax
0x18000d69d  lea     rcx, [rdi+18h]; this
0x18000d6a1  call    ??0CMSMQTransaction@@QEAA@XZ; CMSMQTransaction::CMSMQTransaction(void)
0x18000d6a6  lea     rax, ??_7?$CComContainedObject@VCMSMQTransaction@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQTransaction>::`vftable'{for `ISupportErrorInfo'}
0x18000d6ad  mov     [rdi+18h], rax
0x18000d6b1  lea     rax, ??_7?$CComContainedObject@VCMSMQTransaction@@@ATL@@6B?$IDispatchImpl@UIMSMQTransaction3@@$1?IID_IMSMQTransaction3@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQTransaction>::`vftable'{for `ATL::IDispatchImpl<IMSMQTransaction3,&_GUID const IID_IMSMQTransaction3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d6b8  mov     [rdi+20h], rax
0x18000d6bc  mov     [rdi+28h], rbp
0x18000d6c0  lock inc cs:dword_180038608
0x18000d6c7  jmp     short loc_18000D6CB
0x18000d6c9  xor     edi, edi
0x18000d6cb  test    rdi, rdi
0x18000d6ce  jz      short loc_18000D715
0x18000d6d0  lea     rcx, [rdi+30h]; this
0x18000d6d4  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000d6d9  xor     esi, esi
0x18000d6db  test    eax, eax
0x18000d6dd  cmovs   esi, eax
0x18000d6e0  test    esi, esi
0x18000d6e2  js      short loc_18000D70D
0x18000d6e4  lea     rcx, [rdi+18h]; this
0x18000d6e8  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000d6ed  mov     esi, eax
0x18000d6ef  test    eax, eax
0x18000d6f1  jnz     short loc_18000D70D
0x18000d6f3  mov     rax, [rdi]
0x18000d6f6  mov     r8, r14
0x18000d6f9  mov     rdx, r15
0x18000d6fc  mov     rcx, rdi
0x18000d6ff  mov     rax, [rax]
0x18000d702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d707  mov     esi, eax
0x18000d709  test    eax, eax
0x18000d70b  jz      short loc_18000D715
0x18000d70d  mov     rcx, rdi; Block
0x18000d710  call    ??_G?$CComAggObject@VCMSMQTransaction@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQTransaction>::`scalar deleting destructor'(uint)
0x18000d715  mov     eax, esi
0x18000d717  add     rsp, 28h
0x18000d71b  pop     r15
0x18000d71d  pop     r14
0x18000d71f  pop     rdi
0x18000d720  pop     rsi
0x18000d721  pop     rbp
0x18000d722  pop     rbx
0x18000d723  retn
```
