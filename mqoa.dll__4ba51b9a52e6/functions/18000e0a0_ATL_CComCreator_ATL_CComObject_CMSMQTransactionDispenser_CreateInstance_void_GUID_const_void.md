# ATL::CComCreator<ATL::CComObject<CMSMQTransactionDispenser>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000e0a0`
- end: `0x18000e168`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQTransactionDispenser@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ccd0`

## callees

- `0x18000173c`
- `0x18000a900`
- `0x18000e0a0`
- `0x18000e748`
- `0x18000f34c`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQTransactionDispenser>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  HRESULT v6; // edi
  CMSMQCoordinatedTransactionDispenser *v7; // rax
  CMSMQCoordinatedTransactionDispenser *v8; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMSMQCoordinatedTransactionDispenser *)operator new(0x50u);
  v8 = v7;
  if ( v7 )
  {
    CMSMQCoordinatedTransactionDispenser::CMSMQCoordinatedTransactionDispenser(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CMSMQTransactionDispenser>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSMQTransactionDispenser>::`vftable'{for `ATL::IDispatchImpl<IMSMQTransactionDispenser3,&_GUID const IID_IMSMQTransactionDispenser3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    _InterlockedIncrement(&dword_180038608);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v6 = ATL::CComAutoDeleteCriticalSection::Init((CMSMQCoordinatedTransactionDispenser *)((char *)v8 + 24));
    if ( v6 >= 0 )
      v6 = CMSMQQuery::FinalConstruct(v8);
    if ( v6
      || (v6 = (**(__int64 (__fastcall ***)(CMSMQCoordinatedTransactionDispenser *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
    {
      (*(void (__fastcall **)(CMSMQCoordinatedTransactionDispenser *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e0a0  mov     [rsp+arg_0], rcx
0x18000e0a5  push    rbx
0x18000e0a6  push    rbp
0x18000e0a7  push    rsi
0x18000e0a8  push    rdi
0x18000e0a9  sub     rsp, 28h
0x18000e0ad  mov     rsi, r8
0x18000e0b0  mov     rbp, rdx
0x18000e0b3  test    r8, r8
0x18000e0b6  jnz     short loc_18000E0C2
0x18000e0b8  mov     eax, 80004003h
0x18000e0bd  jmp     loc_18000E15F
0x18000e0c2  mov     qword ptr [r8], 0
0x18000e0c9  mov     edi, 8007000Eh
0x18000e0ce  mov     ecx, 50h ; 'P'; Size
0x18000e0d3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e0d8  mov     rbx, rax
0x18000e0db  mov     [rsp+48h+arg_0], rax
0x18000e0e0  test    rax, rax
0x18000e0e3  jz      short loc_18000E10B
0x18000e0e5  mov     rcx, rax; this
0x18000e0e8  call    ??0CMSMQCoordinatedTransactionDispenser@@QEAA@XZ; CMSMQCoordinatedTransactionDispenser::CMSMQCoordinatedTransactionDispenser(void)
0x18000e0ed  lea     rax, ??_7?$CComObject@VCMSMQTransactionDispenser@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQTransactionDispenser>::`vftable'{for `ISupportErrorInfo'}
0x18000e0f4  mov     [rbx], rax
0x18000e0f7  lea     rax, ??_7?$CComObject@VCMSMQTransactionDispenser@@@ATL@@6B?$IDispatchImpl@UIMSMQTransactionDispenser3@@$1?IID_IMSMQTransactionDispenser3@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQTransactionDispenser>::`vftable'{for `ATL::IDispatchImpl<IMSMQTransactionDispenser3,&_GUID const IID_IMSMQTransactionDispenser3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000e0fe  mov     [rbx+8], rax
0x18000e102  lock inc cs:dword_180038608
0x18000e109  jmp     short loc_18000E10D
0x18000e10b  xor     ebx, ebx
0x18000e10d  test    rbx, rbx
0x18000e110  jz      short loc_18000E15D
0x18000e112  lea     rcx, [rbx+18h]; this
0x18000e116  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000e11b  mov     edi, eax
0x18000e11d  test    eax, eax
0x18000e11f  js      short loc_18000E12B
0x18000e121  mov     rcx, rbx; this
0x18000e124  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000e129  mov     edi, eax
0x18000e12b  test    edi, edi
0x18000e12d  jnz     short loc_18000E149
0x18000e12f  mov     rax, [rbx]
0x18000e132  mov     r8, rsi
0x18000e135  mov     rdx, rbp
0x18000e138  mov     rcx, rbx
0x18000e13b  mov     rax, [rax]
0x18000e13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e143  mov     edi, eax
0x18000e145  test    eax, eax
0x18000e147  jz      short loc_18000E15D
0x18000e149  mov     rax, [rbx]
0x18000e14c  mov     edx, 1
0x18000e151  mov     rcx, rbx
0x18000e154  mov     rax, [rax+28h]
0x18000e158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e15d  mov     eax, edi
0x18000e15f  add     rsp, 28h
0x18000e163  pop     rdi
0x18000e164  pop     rsi
0x18000e165  pop     rbp
0x18000e166  pop     rbx
0x18000e167  retn
```
