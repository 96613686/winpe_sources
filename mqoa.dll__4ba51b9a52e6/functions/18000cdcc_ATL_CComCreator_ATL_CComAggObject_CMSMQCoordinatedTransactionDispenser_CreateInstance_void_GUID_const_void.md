# ATL::CComCreator<ATL::CComAggObject<CMSMQCoordinatedTransactionDispenser>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000cdcc`
- end: `0x18000ceac`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQCoordinatedTransactionDispenser@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cb90`

## callees

- `0x18000173c`
- `0x18000a900`
- `0x18000b240`
- `0x18000cdcc`
- `0x18000e748`
- `0x18000f34c`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQCoordinatedTransactionDispenser>>::CreateInstance(
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
  v8 = operator new(0x68u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQCoordinatedTransactionDispenser>::`vftable';
    CMSMQCoordinatedTransactionDispenser::CMSMQCoordinatedTransactionDispenser((CMSMQCoordinatedTransactionDispenser *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQCoordinatedTransactionDispenser>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQCoordinatedTransactionDispenser>::`vftable'{for `ATL::IDispatchImpl<IMSMQCoordinatedTransactionDispenser3,&_GUID const IID_IMSMQCoordinatedTransactionDispenser3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
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
      ATL::CComAggObject<CMSMQCoordinatedTransactionDispenser>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000cdcc  push    rbx
0x18000cdce  push    rbp
0x18000cdcf  push    rsi
0x18000cdd0  push    rdi
0x18000cdd1  push    r14
0x18000cdd3  push    r15
0x18000cdd5  sub     rsp, 28h
0x18000cdd9  mov     r14, r8
0x18000cddc  mov     r15, rdx
0x18000cddf  mov     rbp, rcx
0x18000cde2  test    r8, r8
0x18000cde5  jnz     short loc_18000CDF1
0x18000cde7  mov     eax, 80004003h
0x18000cdec  jmp     loc_18000CE9F
0x18000cdf1  mov     qword ptr [r8], 0
0x18000cdf8  mov     esi, 8007000Eh
0x18000cdfd  mov     ecx, 68h ; 'h'; Size
0x18000ce02  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ce07  mov     rdi, rax
0x18000ce0a  mov     [rsp+58h+arg_10], rax
0x18000ce0f  test    rax, rax
0x18000ce12  jz      short loc_18000CE51
0x18000ce14  mov     dword ptr [rax+8], 0
0x18000ce1b  lea     rax, ??_7?$CComAggObject@VCMSMQCoordinatedTransactionDispenser@@@ATL@@6B@; const ATL::CComAggObject<CMSMQCoordinatedTransactionDispenser>::`vftable'
0x18000ce22  mov     [rdi], rax
0x18000ce25  lea     rcx, [rdi+18h]; this
0x18000ce29  call    ??0CMSMQCoordinatedTransactionDispenser@@QEAA@XZ; CMSMQCoordinatedTransactionDispenser::CMSMQCoordinatedTransactionDispenser(void)
0x18000ce2e  lea     rax, ??_7?$CComContainedObject@VCMSMQCoordinatedTransactionDispenser@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQCoordinatedTransactionDispenser>::`vftable'{for `ISupportErrorInfo'}
0x18000ce35  mov     [rdi+18h], rax
0x18000ce39  lea     rax, ??_7?$CComContainedObject@VCMSMQCoordinatedTransactionDispenser@@@ATL@@6B?$IDispatchImpl@UIMSMQCoordinatedTransactionDispenser3@@$1?IID_IMSMQCoordinatedTransactionDispenser3@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQCoordinatedTransactionDispenser>::`vftable'{for `ATL::IDispatchImpl<IMSMQCoordinatedTransactionDispenser3,&_GUID const IID_IMSMQCoordinatedTransactionDispenser3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000ce40  mov     [rdi+20h], rax
0x18000ce44  mov     [rdi+28h], rbp
0x18000ce48  lock inc cs:dword_180038608
0x18000ce4f  jmp     short loc_18000CE53
0x18000ce51  xor     edi, edi
0x18000ce53  test    rdi, rdi
0x18000ce56  jz      short loc_18000CE9D
0x18000ce58  lea     rcx, [rdi+30h]; this
0x18000ce5c  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000ce61  xor     esi, esi
0x18000ce63  test    eax, eax
0x18000ce65  cmovs   esi, eax
0x18000ce68  test    esi, esi
0x18000ce6a  js      short loc_18000CE95
0x18000ce6c  lea     rcx, [rdi+18h]; this
0x18000ce70  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000ce75  mov     esi, eax
0x18000ce77  test    eax, eax
0x18000ce79  jnz     short loc_18000CE95
0x18000ce7b  mov     rax, [rdi]
0x18000ce7e  mov     r8, r14
0x18000ce81  mov     rdx, r15
0x18000ce84  mov     rcx, rdi
0x18000ce87  mov     rax, [rax]
0x18000ce8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce8f  mov     esi, eax
0x18000ce91  test    eax, eax
0x18000ce93  jz      short loc_18000CE9D
0x18000ce95  mov     rcx, rdi; Block
0x18000ce98  call    ??_G?$CComAggObject@VCMSMQCoordinatedTransactionDispenser@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQCoordinatedTransactionDispenser>::`scalar deleting destructor'(uint)
0x18000ce9d  mov     eax, esi
0x18000ce9f  add     rsp, 28h
0x18000cea3  pop     r15
0x18000cea5  pop     r14
0x18000cea7  pop     rdi
0x18000cea8  pop     rsi
0x18000cea9  pop     rbp
0x18000ceaa  pop     rbx
0x18000ceab  retn
```
