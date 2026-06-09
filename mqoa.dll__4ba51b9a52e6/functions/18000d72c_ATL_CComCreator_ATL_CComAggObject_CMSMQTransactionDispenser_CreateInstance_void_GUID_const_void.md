# ATL::CComCreator<ATL::CComAggObject<CMSMQTransactionDispenser>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d72c`
- end: `0x18000d80c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQTransactionDispenser@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ccd0`

## callees

- `0x18000173c`
- `0x18000a900`
- `0x18000b3d0`
- `0x18000d72c`
- `0x18000e748`
- `0x18000f34c`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQTransactionDispenser>>::CreateInstance(
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
    *v8 = &ATL::CComAggObject<CMSMQTransactionDispenser>::`vftable';
    CMSMQCoordinatedTransactionDispenser::CMSMQCoordinatedTransactionDispenser((CMSMQCoordinatedTransactionDispenser *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQTransactionDispenser>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQTransactionDispenser>::`vftable'{for `ATL::IDispatchImpl<IMSMQTransactionDispenser3,&_GUID const IID_IMSMQTransactionDispenser3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
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
      ATL::CComAggObject<CMSMQTransactionDispenser>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d72c  push    rbx
0x18000d72e  push    rbp
0x18000d72f  push    rsi
0x18000d730  push    rdi
0x18000d731  push    r14
0x18000d733  push    r15
0x18000d735  sub     rsp, 28h
0x18000d739  mov     r14, r8
0x18000d73c  mov     r15, rdx
0x18000d73f  mov     rbp, rcx
0x18000d742  test    r8, r8
0x18000d745  jnz     short loc_18000D751
0x18000d747  mov     eax, 80004003h
0x18000d74c  jmp     loc_18000D7FF
0x18000d751  mov     qword ptr [r8], 0
0x18000d758  mov     esi, 8007000Eh
0x18000d75d  mov     ecx, 68h ; 'h'; Size
0x18000d762  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d767  mov     rdi, rax
0x18000d76a  mov     [rsp+58h+arg_10], rax
0x18000d76f  test    rax, rax
0x18000d772  jz      short loc_18000D7B1
0x18000d774  mov     dword ptr [rax+8], 0
0x18000d77b  lea     rax, ??_7?$CComAggObject@VCMSMQTransactionDispenser@@@ATL@@6B@; const ATL::CComAggObject<CMSMQTransactionDispenser>::`vftable'
0x18000d782  mov     [rdi], rax
0x18000d785  lea     rcx, [rdi+18h]; this
0x18000d789  call    ??0CMSMQCoordinatedTransactionDispenser@@QEAA@XZ; CMSMQCoordinatedTransactionDispenser::CMSMQCoordinatedTransactionDispenser(void)
0x18000d78e  lea     rax, ??_7?$CComContainedObject@VCMSMQTransactionDispenser@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQTransactionDispenser>::`vftable'{for `ISupportErrorInfo'}
0x18000d795  mov     [rdi+18h], rax
0x18000d799  lea     rax, ??_7?$CComContainedObject@VCMSMQTransactionDispenser@@@ATL@@6B?$IDispatchImpl@UIMSMQTransactionDispenser3@@$1?IID_IMSMQTransactionDispenser3@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQTransactionDispenser>::`vftable'{for `ATL::IDispatchImpl<IMSMQTransactionDispenser3,&_GUID const IID_IMSMQTransactionDispenser3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d7a0  mov     [rdi+20h], rax
0x18000d7a4  mov     [rdi+28h], rbp
0x18000d7a8  lock inc cs:dword_180038608
0x18000d7af  jmp     short loc_18000D7B3
0x18000d7b1  xor     edi, edi
0x18000d7b3  test    rdi, rdi
0x18000d7b6  jz      short loc_18000D7FD
0x18000d7b8  lea     rcx, [rdi+30h]; this
0x18000d7bc  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000d7c1  xor     esi, esi
0x18000d7c3  test    eax, eax
0x18000d7c5  cmovs   esi, eax
0x18000d7c8  test    esi, esi
0x18000d7ca  js      short loc_18000D7F5
0x18000d7cc  lea     rcx, [rdi+18h]; this
0x18000d7d0  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000d7d5  mov     esi, eax
0x18000d7d7  test    eax, eax
0x18000d7d9  jnz     short loc_18000D7F5
0x18000d7db  mov     rax, [rdi]
0x18000d7de  mov     r8, r14
0x18000d7e1  mov     rdx, r15
0x18000d7e4  mov     rcx, rdi
0x18000d7e7  mov     rax, [rax]
0x18000d7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7ef  mov     esi, eax
0x18000d7f1  test    eax, eax
0x18000d7f3  jz      short loc_18000D7FD
0x18000d7f5  mov     rcx, rdi; Block
0x18000d7f8  call    ??_G?$CComAggObject@VCMSMQTransactionDispenser@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQTransactionDispenser>::`scalar deleting destructor'(uint)
0x18000d7fd  mov     eax, esi
0x18000d7ff  add     rsp, 28h
0x18000d803  pop     r15
0x18000d805  pop     r14
0x18000d807  pop     rdi
0x18000d808  pop     rsi
0x18000d809  pop     rbp
0x18000d80a  pop     rbx
0x18000d80b  retn
```
