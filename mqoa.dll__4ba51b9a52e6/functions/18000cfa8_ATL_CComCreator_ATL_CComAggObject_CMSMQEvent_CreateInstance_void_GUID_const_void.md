# ATL::CComCreator<ATL::CComAggObject<CMSMQEvent>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000cfa8`
- end: `0x18000d0b9`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMSMQEvent@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000cbd0`

## callees

- `0x18000173c`
- `0x180009988`
- `0x18000b290`
- `0x18000cfa8`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMSMQEvent>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int HiddenWindow; // edi
  _QWORD *v8; // rax
  __int64 (__fastcall ***v9)(void *, __int64, _QWORD *); // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  HiddenWindow = -2147024882;
  v8 = operator new(0x60u);
  v9 = (__int64 (__fastcall ***)(void *, __int64, _QWORD *))v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *v8 = &ATL::CComAggObject<CMSMQEvent>::`vftable';
    *((_DWORD *)v8 + 12) = 0;
    v8[5] = 0;
    v8[2] = &ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `ISupportErrorInfo'};
    v8[3] = &ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMSMQEvent>'};
    v8[4] = &ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `CProxy_DMSMQEventEvents<CMSMQEvent>'};
    v8[7] = &ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `ATL::IDispatchImpl<IMSMQEvent3,&_GUID const IID_IMSMQEvent3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v8[8] = &ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `ATL::IDispatchImpl<IMSMQPrivateEvent,&_GUID const IID_IMSMQPrivateEvent,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v8[9] = &ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MSMQEvent,&_GUID const DIID__DMSMQEventEvents,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    v8[11] = 0;
    v8[10] = a1;
    _InterlockedIncrement(&dword_180038608);
    HiddenWindow = CMSMQEvent::CreateHiddenWindow((LONG_PTR)(v8 + 2));
    if ( HiddenWindow || (HiddenWindow = (**v9)(v9, a2, a3)) != 0 )
      ATL::CComAggObject<CMSMQEvent>::`scalar deleting destructor'(v9);
  }
  return HiddenWindow;
}

```

## disassembly

```asm
0x18000cfa8  mov     [rsp+arg_0], rbx
0x18000cfad  mov     [rsp+arg_8], rbp
0x18000cfb2  push    rsi
0x18000cfb3  push    rdi
0x18000cfb4  push    r14
0x18000cfb6  sub     rsp, 20h
0x18000cfba  mov     rsi, r8
0x18000cfbd  mov     rbp, rdx
0x18000cfc0  mov     r14, rcx
0x18000cfc3  test    r8, r8
0x18000cfc6  jnz     short loc_18000CFD2
0x18000cfc8  mov     eax, 80004003h
0x18000cfcd  jmp     loc_18000D0A6
0x18000cfd2  mov     ecx, 60h ; '`'; Size
0x18000cfd7  mov     qword ptr [r8], 0
0x18000cfde  mov     edi, 8007000Eh
0x18000cfe3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cfe8  mov     [rsp+38h+arg_10], rax
0x18000cfed  mov     rbx, rax
0x18000cff0  test    rax, rax
0x18000cff3  jz      loc_18000D0A4
0x18000cff9  mov     dword ptr [rax+8], 0
0x18000d000  lea     rax, ??_7?$CComAggObject@VCMSMQEvent@@@ATL@@6B@; const ATL::CComAggObject<CMSMQEvent>::`vftable'
0x18000d007  mov     [rbx], rax
0x18000d00a  lea     rax, ??_7?$CComContainedObject@VCMSMQEvent@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `ISupportErrorInfo'}
0x18000d011  mov     dword ptr [rbx+30h], 0
0x18000d018  mov     qword ptr [rbx+28h], 0
0x18000d020  mov     [rbx+10h], rax
0x18000d024  lea     rax, ??_7?$CComContainedObject@VCMSMQEvent@@@ATL@@6B?$IConnectionPointContainerImpl@VCMSMQEvent@@@1@@; const ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `ATL::IConnectionPointContainerImpl<CMSMQEvent>'}
0x18000d02b  mov     [rbx+18h], rax
0x18000d02f  lea     rax, ??_7?$CComContainedObject@VCMSMQEvent@@@ATL@@6B?$CProxy_DMSMQEventEvents@VCMSMQEvent@@@@@; const ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `CProxy_DMSMQEventEvents<CMSMQEvent>'}
0x18000d036  mov     [rbx+20h], rax
0x18000d03a  lea     rax, ??_7?$CComContainedObject@VCMSMQEvent@@@ATL@@6B?$IDispatchImpl@UIMSMQEvent3@@$1?IID_IMSMQEvent3@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `ATL::IDispatchImpl<IMSMQEvent3,&_GUID const IID_IMSMQEvent3,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d041  mov     [rbx+38h], rax
0x18000d045  lea     rax, ??_7?$CComContainedObject@VCMSMQEvent@@@ATL@@6B?$IDispatchImpl@UIMSMQPrivateEvent@@$1?IID_IMSMQPrivateEvent@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `ATL::IDispatchImpl<IMSMQPrivateEvent,&_GUID const IID_IMSMQPrivateEvent,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d04c  mov     [rbx+40h], rax
0x18000d050  lea     rax, ??_7?$CComContainedObject@VCMSMQEvent@@@ATL@@6B?$IProvideClassInfo2Impl@$1?CLSID_MSMQEvent@@3U_GUID@@B$1?DIID__DMSMQEventEvents@@3U2@B$1?LIBID_MSMQ@@3U2@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<CMSMQEvent>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_MSMQEvent,&_GUID const DIID__DMSMQEventEvents,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000d057  mov     [rbx+48h], rax
0x18000d05b  mov     qword ptr [rbx+58h], 0
0x18000d063  mov     [rbx+50h], r14
0x18000d067  lock inc cs:dword_180038608
0x18000d06e  test    rbx, rbx
0x18000d071  jz      short loc_18000D0A4
0x18000d073  lea     rcx, [rbx+10h]; dwNewLong
0x18000d077  call    ?CreateHiddenWindow@CMSMQEvent@@QEAAJXZ; CMSMQEvent::CreateHiddenWindow(void)
0x18000d07c  mov     edi, eax
0x18000d07e  test    eax, eax
0x18000d080  jnz     short loc_18000D09C
0x18000d082  mov     rax, [rbx]
0x18000d085  mov     r8, rsi
0x18000d088  mov     rdx, rbp
0x18000d08b  mov     rcx, rbx
0x18000d08e  mov     rax, [rax]
0x18000d091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d096  mov     edi, eax
0x18000d098  test    eax, eax
0x18000d09a  jz      short loc_18000D0A4
0x18000d09c  mov     rcx, rbx; Block
0x18000d09f  call    ??_G?$CComAggObject@VCMSMQEvent@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQEvent>::`scalar deleting destructor'(uint)
0x18000d0a4  mov     eax, edi
0x18000d0a6  mov     rbx, [rsp+38h+arg_0]
0x18000d0ab  mov     rbp, [rsp+38h+arg_8]
0x18000d0b0  add     rsp, 20h
0x18000d0b4  pop     r14
0x18000d0b6  pop     rdi
0x18000d0b7  pop     rsi
0x18000d0b8  retn
```
