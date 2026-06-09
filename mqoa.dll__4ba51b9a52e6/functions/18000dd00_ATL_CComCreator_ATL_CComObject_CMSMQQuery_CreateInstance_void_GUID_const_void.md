# ATL::CComCreator<ATL::CComObject<CMSMQQuery>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000dd00`
- end: `0x18000ddc8`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQQuery@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cc30`

## callees

- `0x18000173c`
- `0x18000a900`
- `0x18000dd00`
- `0x18000e748`
- `0x18000f34c`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQQuery>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
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
    *(_QWORD *)v8 = &ATL::CComObject<CMSMQQuery>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSMQQuery>::`vftable'{for `ATL::IDispatchImpl<IMSMQQuery4,&_GUID const IID_IMSMQQuery4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
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
0x18000dd00  mov     [rsp+arg_0], rcx
0x18000dd05  push    rbx
0x18000dd06  push    rbp
0x18000dd07  push    rsi
0x18000dd08  push    rdi
0x18000dd09  sub     rsp, 28h
0x18000dd0d  mov     rsi, r8
0x18000dd10  mov     rbp, rdx
0x18000dd13  test    r8, r8
0x18000dd16  jnz     short loc_18000DD22
0x18000dd18  mov     eax, 80004003h
0x18000dd1d  jmp     loc_18000DDBF
0x18000dd22  mov     qword ptr [r8], 0
0x18000dd29  mov     edi, 8007000Eh
0x18000dd2e  mov     ecx, 50h ; 'P'; Size
0x18000dd33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dd38  mov     rbx, rax
0x18000dd3b  mov     [rsp+48h+arg_0], rax
0x18000dd40  test    rax, rax
0x18000dd43  jz      short loc_18000DD6B
0x18000dd45  mov     rcx, rax; this
0x18000dd48  call    ??0CMSMQCoordinatedTransactionDispenser@@QEAA@XZ; CMSMQCoordinatedTransactionDispenser::CMSMQCoordinatedTransactionDispenser(void)
0x18000dd4d  lea     rax, ??_7?$CComObject@VCMSMQQuery@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQQuery>::`vftable'{for `ISupportErrorInfo'}
0x18000dd54  mov     [rbx], rax
0x18000dd57  lea     rax, ??_7?$CComObject@VCMSMQQuery@@@ATL@@6B?$IDispatchImpl@UIMSMQQuery4@@$1?IID_IMSMQQuery4@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQQuery>::`vftable'{for `ATL::IDispatchImpl<IMSMQQuery4,&_GUID const IID_IMSMQQuery4,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000dd5e  mov     [rbx+8], rax
0x18000dd62  lock inc cs:dword_180038608
0x18000dd69  jmp     short loc_18000DD6D
0x18000dd6b  xor     ebx, ebx
0x18000dd6d  test    rbx, rbx
0x18000dd70  jz      short loc_18000DDBD
0x18000dd72  lea     rcx, [rbx+18h]; this
0x18000dd76  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000dd7b  mov     edi, eax
0x18000dd7d  test    eax, eax
0x18000dd7f  js      short loc_18000DD8B
0x18000dd81  mov     rcx, rbx; this
0x18000dd84  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000dd89  mov     edi, eax
0x18000dd8b  test    edi, edi
0x18000dd8d  jnz     short loc_18000DDA9
0x18000dd8f  mov     rax, [rbx]
0x18000dd92  mov     r8, rsi
0x18000dd95  mov     rdx, rbp
0x18000dd98  mov     rcx, rbx
0x18000dd9b  mov     rax, [rax]
0x18000dd9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dda3  mov     edi, eax
0x18000dda5  test    eax, eax
0x18000dda7  jz      short loc_18000DDBD
0x18000dda9  mov     rax, [rbx]
0x18000ddac  mov     edx, 1
0x18000ddb1  mov     rcx, rbx
0x18000ddb4  mov     rax, [rax+28h]
0x18000ddb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ddbd  mov     eax, edi
0x18000ddbf  add     rsp, 28h
0x18000ddc3  pop     rdi
0x18000ddc4  pop     rsi
0x18000ddc5  pop     rbp
0x18000ddc6  pop     rbx
0x18000ddc7  retn
```
