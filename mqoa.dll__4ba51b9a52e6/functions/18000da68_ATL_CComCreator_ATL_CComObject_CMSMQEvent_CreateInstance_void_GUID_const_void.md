# ATL::CComCreator<ATL::CComObject<CMSMQEvent>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000da68`
- end: `0x18000db5f`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQEvent@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000cbd0`

## callees

- `0x18000173c`
- `0x180009988`
- `0x18000da68`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQEvent>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int HiddenWindow; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  HiddenWindow = -2147024882;
  v7 = operator new(0x50u);
  v8 = v7;
  if ( v7 )
  {
    v7[16] = 0;
    v7[8] = 0;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 9) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CMSMQEvent>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v7 + 1) = &ATL::CComObject<CMSMQEvent>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMSMQEvent>'};
    *((_QWORD *)v7 + 2) = &ATL::CComObject<CMSMQEvent>::`vftable'{for `CProxy_DMSMQEventEvents<CMSMQEvent>'};
    *((_QWORD *)v7 + 5) = &ATL::CComObject<CMSMQEvent>::`vftable'{for `ATL::IDispatchImpl<IMSMQEvent3,&_GUID const IID_IMSMQEvent3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v7 + 6) = &ATL::CComObject<CMSMQEvent>::`vftable'{for `ATL::IDispatchImpl<IMSMQPrivateEvent,&_GUID const IID_IMSMQPrivateEvent,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v7 + 7) = &ATL::CComObject<CMSMQEvent>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MSMQEvent,&_GUID const DIID__DMSMQEventEvents,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    _InterlockedIncrement(&dword_180038608);
    HiddenWindow = CMSMQEvent::CreateHiddenWindow((LONG_PTR)v7);
    if ( HiddenWindow || (HiddenWindow = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
  }
  return HiddenWindow;
}

```

## disassembly

```asm
0x18000da68  push    rbx
0x18000da6a  push    rbp
0x18000da6b  push    rsi
0x18000da6c  push    rdi
0x18000da6d  sub     rsp, 28h
0x18000da71  mov     rsi, r8
0x18000da74  mov     rbp, rdx
0x18000da77  test    r8, r8
0x18000da7a  jnz     short loc_18000DA86
0x18000da7c  mov     eax, 80004003h
0x18000da81  jmp     loc_18000DB56
0x18000da86  mov     ecx, 50h ; 'P'; Size
0x18000da8b  mov     qword ptr [r8], 0
0x18000da92  mov     edi, 8007000Eh
0x18000da97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000da9c  mov     [rsp+48h+arg_0], rax
0x18000daa1  mov     rbx, rax
0x18000daa4  test    rax, rax
0x18000daa7  jz      loc_18000DB54
0x18000daad  mov     dword ptr [rax+40h], 0
0x18000dab4  mov     dword ptr [rax+20h], 0
0x18000dabb  mov     qword ptr [rax+18h], 0
0x18000dac3  mov     qword ptr [rax+48h], 0
0x18000dacb  lea     rax, ??_7?$CComObject@VCMSMQEvent@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQEvent>::`vftable'{for `ISupportErrorInfo'}
0x18000dad2  mov     [rbx], rax
0x18000dad5  lea     rax, ??_7?$CComObject@VCMSMQEvent@@@ATL@@6B?$IConnectionPointContainerImpl@VCMSMQEvent@@@1@@; const ATL::CComObject<CMSMQEvent>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMSMQEvent>'}
0x18000dadc  mov     [rbx+8], rax
0x18000dae0  lea     rax, ??_7?$CComObject@VCMSMQEvent@@@ATL@@6B?$CProxy_DMSMQEventEvents@VCMSMQEvent@@@@@; const ATL::CComObject<CMSMQEvent>::`vftable'{for `CProxy_DMSMQEventEvents<CMSMQEvent>'}
0x18000dae7  mov     [rbx+10h], rax
0x18000daeb  lea     rax, ??_7?$CComObject@VCMSMQEvent@@@ATL@@6B?$IDispatchImpl@UIMSMQEvent3@@$1?IID_IMSMQEvent3@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQEvent>::`vftable'{for `ATL::IDispatchImpl<IMSMQEvent3,&_GUID const IID_IMSMQEvent3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000daf2  mov     [rbx+28h], rax
0x18000daf6  lea     rax, ??_7?$CComObject@VCMSMQEvent@@@ATL@@6B?$IDispatchImpl@UIMSMQPrivateEvent@@$1?IID_IMSMQPrivateEvent@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQEvent>::`vftable'{for `ATL::IDispatchImpl<IMSMQPrivateEvent,&_GUID const IID_IMSMQPrivateEvent,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000dafd  mov     [rbx+30h], rax
0x18000db01  lea     rax, ??_7?$CComObject@VCMSMQEvent@@@ATL@@6B?$IProvideClassInfo2Impl@$1?CLSID_MSMQEvent@@3U_GUID@@B$1?DIID__DMSMQEventEvents@@3U2@B$1?LIBID_MSMQ@@3U2@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQEvent>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MSMQEvent,&_GUID const DIID__DMSMQEventEvents,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000db08  mov     [rbx+38h], rax
0x18000db0c  lock inc cs:dword_180038608
0x18000db13  test    rbx, rbx
0x18000db16  jz      short loc_18000DB54
0x18000db18  mov     rcx, rbx; dwNewLong
0x18000db1b  call    ?CreateHiddenWindow@CMSMQEvent@@QEAAJXZ; CMSMQEvent::CreateHiddenWindow(void)
0x18000db20  mov     edi, eax
0x18000db22  test    eax, eax
0x18000db24  jnz     short loc_18000DB40
0x18000db26  mov     rax, [rbx]
0x18000db29  mov     r8, rsi
0x18000db2c  mov     rdx, rbp
0x18000db2f  mov     rcx, rbx
0x18000db32  mov     rax, [rax]
0x18000db35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db3a  mov     edi, eax
0x18000db3c  test    eax, eax
0x18000db3e  jz      short loc_18000DB54
0x18000db40  mov     rax, [rbx]
0x18000db43  mov     edx, 1
0x18000db48  mov     rcx, rbx
0x18000db4b  mov     rax, [rax+28h]
0x18000db4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db54  mov     eax, edi
0x18000db56  add     rsp, 28h
0x18000db5a  pop     rdi
0x18000db5b  pop     rsi
0x18000db5c  pop     rbp
0x18000db5d  pop     rbx
0x18000db5e  retn
```
