# ATL::CComCreator<ATL::CComObject<CMSMQCoordinatedTransactionDispenser>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d8e4`
- end: `0x18000d9ac`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQCoordinatedTransactionDispenser@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cb90`

## callees

- `0x18000173c`
- `0x18000a900`
- `0x18000d8e4`
- `0x18000e748`
- `0x18000f34c`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQCoordinatedTransactionDispenser>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComObject<CMSMQCoordinatedTransactionDispenser>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSMQCoordinatedTransactionDispenser>::`vftable'{for `ATL::IDispatchImpl<IMSMQCoordinatedTransactionDispenser3,&_GUID const IID_IMSMQCoordinatedTransactionDispenser3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
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
0x18000d8e4  mov     [rsp+arg_0], rcx
0x18000d8e9  push    rbx
0x18000d8ea  push    rbp
0x18000d8eb  push    rsi
0x18000d8ec  push    rdi
0x18000d8ed  sub     rsp, 28h
0x18000d8f1  mov     rsi, r8
0x18000d8f4  mov     rbp, rdx
0x18000d8f7  test    r8, r8
0x18000d8fa  jnz     short loc_18000D906
0x18000d8fc  mov     eax, 80004003h
0x18000d901  jmp     loc_18000D9A3
0x18000d906  mov     qword ptr [r8], 0
0x18000d90d  mov     edi, 8007000Eh
0x18000d912  mov     ecx, 50h ; 'P'; Size
0x18000d917  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d91c  mov     rbx, rax
0x18000d91f  mov     [rsp+48h+arg_0], rax
0x18000d924  test    rax, rax
0x18000d927  jz      short loc_18000D94F
0x18000d929  mov     rcx, rax; this
0x18000d92c  call    ??0CMSMQCoordinatedTransactionDispenser@@QEAA@XZ; CMSMQCoordinatedTransactionDispenser::CMSMQCoordinatedTransactionDispenser(void)
0x18000d931  lea     rax, ??_7?$CComObject@VCMSMQCoordinatedTransactionDispenser@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQCoordinatedTransactionDispenser>::`vftable'{for `ISupportErrorInfo'}
0x18000d938  mov     [rbx], rax
0x18000d93b  lea     rax, ??_7?$CComObject@VCMSMQCoordinatedTransactionDispenser@@@ATL@@6B?$IDispatchImpl@UIMSMQCoordinatedTransactionDispenser3@@$1?IID_IMSMQCoordinatedTransactionDispenser3@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQCoordinatedTransactionDispenser>::`vftable'{for `ATL::IDispatchImpl<IMSMQCoordinatedTransactionDispenser3,&_GUID const IID_IMSMQCoordinatedTransactionDispenser3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d942  mov     [rbx+8], rax
0x18000d946  lock inc cs:dword_180038608
0x18000d94d  jmp     short loc_18000D951
0x18000d94f  xor     ebx, ebx
0x18000d951  test    rbx, rbx
0x18000d954  jz      short loc_18000D9A1
0x18000d956  lea     rcx, [rbx+18h]; this
0x18000d95a  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000d95f  mov     edi, eax
0x18000d961  test    eax, eax
0x18000d963  js      short loc_18000D96F
0x18000d965  mov     rcx, rbx; this
0x18000d968  call    ?FinalConstruct@CMSMQQuery@@QEAAJXZ; CMSMQQuery::FinalConstruct(void)
0x18000d96d  mov     edi, eax
0x18000d96f  test    edi, edi
0x18000d971  jnz     short loc_18000D98D
0x18000d973  mov     rax, [rbx]
0x18000d976  mov     r8, rsi
0x18000d979  mov     rdx, rbp
0x18000d97c  mov     rcx, rbx
0x18000d97f  mov     rax, [rax]
0x18000d982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d987  mov     edi, eax
0x18000d989  test    eax, eax
0x18000d98b  jz      short loc_18000D9A1
0x18000d98d  mov     rax, [rbx]
0x18000d990  mov     edx, 1
0x18000d995  mov     rcx, rbx
0x18000d998  mov     rax, [rax+28h]
0x18000d99c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9a1  mov     eax, edi
0x18000d9a3  add     rsp, 28h
0x18000d9a7  pop     rdi
0x18000d9a8  pop     rsi
0x18000d9a9  pop     rbp
0x18000d9aa  pop     rbx
0x18000d9ab  retn
```
