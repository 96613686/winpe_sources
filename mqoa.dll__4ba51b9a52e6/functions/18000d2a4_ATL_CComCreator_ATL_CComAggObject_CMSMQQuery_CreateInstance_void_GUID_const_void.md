# ATL::CComCreator<ATL::CComAggObject<CMSMQQuery>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d2a4`
- end: `0x18000d384`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQQuery@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cc30`

## callees

- `0x18000173c`
- `0x18000a900`
- `0x18000b308`
- `0x18000d2a4`
- `0x18000e748`
- `0x18000f34c`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQQuery>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
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
    *v8 = &ATL::CComAggObject<CMSMQQuery>::`vftable';
    CMSMQCoordinatedTransactionDispenser::CMSMQCoordinatedTransactionDispenser((CMSMQCoordinatedTransactionDispenser *)(v8 + 3));
    v9[3] = &ATL::CComContainedObject<CMSMQQuery>::`vftable'{for `ISupportErrorInfo'};
    v9[4] = &ATL::CComContainedObject<CMSMQQuery>::`vftable'{for `ATL::IDispatchImpl<IMSMQQuery4,&_GUID const IID_IMSMQQuery4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
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
      ATL::CComAggObject<CMSMQQuery>::`scalar deleting destructor'(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d2a4  push    rbx
0x18000d2a6  push    rbp
0x18000d2a7  push    rsi
0x18000d2a8  push    rdi
0x18000d2a9  push    r14
0x18000d2ab  push    r15
0x18000d2ad  sub     rsp, 28h
0x18000d2b1  mov     r14, r8
0x18000d2b4  mov     r15, rdx
0x18000d2b7  mov     rbp, rcx
0x18000d2ba  test    r8, r8
0x18000d2bd  jnz     short loc_18000D2C9
0x18000d2bf  mov     eax, 80004003h
0x18000d2c4  jmp     loc_18000D377
0x18000d2c9  mov     qword ptr [r8], 0
0x18000d2d0  mov     esi, 8007000Eh
0x18000d2d5  mov     ecx, 68h ; 'h'; Size
0x18000d2da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d2df  mov     rdi, rax
0x18000d2e2  mov     [rsp+58h+arg_10], rax
0x18000d2e7  test    rax, rax
0x18000d2ea  jz      short loc_18000D329
0x18000d2ec  mov     dword ptr [rax+8], 0
0x18000d2f3  lea     rax, ??_7?$CComAggObject@VCMSMQQuery@@@ATL@@6B@; const ATL::CComAggObject<CMSMQQuery>::`vftable'
0x18000d2fa  mov     [rdi], rax
0x18000d2fd  lea     rcx, [rdi+18h]; this
0x18000d301  call    ??0CMSMQCoordinatedTransactionDispenser@@QEAA@XZ; CMSMQCoordinatedTransactionDispenser::CMSMQCoordinatedTransactionDispenser(void)
0x18000d306  lea     rax, ??_7?$CComContainedObject@VCMSMQQuery@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQQuery>::`vftable'{for `ISupportErrorInfo'}
0x18000d30d  mov     [rdi+18h], rax
0x18000d311  lea     rax, ??_7?$CComContainedObject@VCMSMQQuery@@@ATL@@6B?$IDispatchImpl@UIMSMQQuery4@@$1?IID_IMSMQQuery4@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQQuery>::`vftable'{for `ATL::IDispatchImpl<IMSMQQuery4,&_GUID const IID_IMSMQQuery4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d318  mov     [rdi+20h], rax
0x18000d31c  mov     [rdi+28h], rbp
0x18000d320  lock inc cs:dword_180038608
0x18000d327  jmp     short loc_18000D32B
0x18000d329  xor     edi, edi
0x18000d32b  test    rdi, rdi
0x18000d32e  jz      short loc_18000D375
0x18000d330  lea     rcx, [rdi+30h]; this
0x18000d334  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000d339  xor     esi, esi
0x18000d33b  test    eax, eax
0x18000d33d  cmovs   esi, eax
0x18000d340  test    esi, esi
0x18000d342  js      short loc_18000D36D
0x18000d344  lea     rcx, [rdi+18h]; this
0x18000d348  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000d34d  mov     esi, eax
0x18000d34f  test    eax, eax
0x18000d351  jnz     short loc_18000D36D
0x18000d353  mov     rax, [rdi]
0x18000d356  mov     r8, r14
0x18000d359  mov     rdx, r15
0x18000d35c  mov     rcx, rdi
0x18000d35f  mov     rax, [rax]
0x18000d362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d367  mov     esi, eax
0x18000d369  test    eax, eax
0x18000d36b  jz      short loc_18000D375
0x18000d36d  mov     rcx, rdi; Block
0x18000d370  call    ??_G?$CComAggObject@VCMSMQQuery@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQQuery>::`scalar deleting destructor'(uint)
0x18000d375  mov     eax, esi
0x18000d377  add     rsp, 28h
0x18000d37b  pop     r15
0x18000d37d  pop     r14
0x18000d37f  pop     rdi
0x18000d380  pop     rsi
0x18000d381  pop     rbp
0x18000d382  pop     rbx
0x18000d383  retn
```
