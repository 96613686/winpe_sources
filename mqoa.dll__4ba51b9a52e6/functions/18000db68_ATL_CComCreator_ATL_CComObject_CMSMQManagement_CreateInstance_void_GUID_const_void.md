# ATL::CComCreator<ATL::CComObject<CMSMQManagement>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000db68`
- end: `0x18000dc46`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCMSMQManagement@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cbf0`

## callees

- `0x18000173c`
- `0x18000db68`
- `0x18000e7a8`
- `0x18000f34c`
- `0x180022904`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CMSMQManagement>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  HRESULT v6; // edi
  CMSMQManagement *v7; // rax
  CMSMQManagement *v8; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CMSMQManagement *)operator new(0xA8u);
  v8 = v7;
  if ( v7 )
  {
    CMSMQManagement::CMSMQManagement(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CMSMQManagement>::`vftable'{for `ISupportErrorInfo'};
    *((_QWORD *)v8 + 1) = &ATL::CComObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQManagement,&_GUID const IID_IMSMQManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v8 + 2) = &ATL::CComObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQOutgoingQueueManagement,&_GUID const IID_IMSMQOutgoingQueueManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v8 + 3) = &ATL::CComObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQQueueManagement,&_GUID const IID_IMSMQQueueManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'};
    _InterlockedIncrement(&dword_180038608);
  }
  else
  {
    v8 = 0;
  }
  if ( v8 )
  {
    v6 = ATL::CComAutoDeleteCriticalSection::Init((CMSMQManagement *)((char *)v8 + 40));
    if ( v6 >= 0 )
      v6 = CMSMQManagement::FinalConstruct(v8);
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(CMSMQManagement *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(CMSMQManagement *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000db68  mov     [rsp+arg_0], rcx
0x18000db6d  push    rbx
0x18000db6e  push    rbp
0x18000db6f  push    rsi
0x18000db70  push    rdi
0x18000db71  sub     rsp, 28h
0x18000db75  mov     rsi, r8
0x18000db78  mov     rbp, rdx
0x18000db7b  test    r8, r8
0x18000db7e  jnz     short loc_18000DB8A
0x18000db80  mov     eax, 80004003h
0x18000db85  jmp     loc_18000DC3D
0x18000db8a  mov     qword ptr [r8], 0
0x18000db91  mov     edi, 8007000Eh
0x18000db96  mov     ecx, 0A8h; Size
0x18000db9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dba0  mov     rbx, rax
0x18000dba3  mov     [rsp+48h+arg_0], rax
0x18000dba8  test    rax, rax
0x18000dbab  jz      short loc_18000DBE9
0x18000dbad  mov     rcx, rax; this
0x18000dbb0  call    ??0CMSMQManagement@@QEAA@XZ; CMSMQManagement::CMSMQManagement(void)
0x18000dbb5  lea     rax, ??_7?$CComObject@VCMSMQManagement@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CMSMQManagement>::`vftable'{for `ISupportErrorInfo'}
0x18000dbbc  mov     [rbx], rax
0x18000dbbf  lea     rax, ??_7?$CComObject@VCMSMQManagement@@@ATL@@6B?$IDispatchImpl@UIMSMQManagement@@$1?IID_IMSMQManagement@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQManagement,&_GUID const IID_IMSMQManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000dbc6  mov     [rbx+8], rax
0x18000dbca  lea     rax, ??_7?$CComObject@VCMSMQManagement@@@ATL@@6B?$IDispatchImpl@UIMSMQOutgoingQueueManagement@@$1?IID_IMSMQOutgoingQueueManagement@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQOutgoingQueueManagement,&_GUID const IID_IMSMQOutgoingQueueManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000dbd1  mov     [rbx+10h], rax
0x18000dbd5  lea     rax, ??_7?$CComObject@VCMSMQManagement@@@ATL@@6B?$IDispatchImpl@UIMSMQQueueManagement@@$1?IID_IMSMQQueueManagement@@3U_GUID@@B$1?LIBID_MSMQ@@3U3@B$03$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CMSMQManagement>::`vftable'{for `ATL::IDispatchImpl<IMSMQQueueManagement,&_GUID const IID_IMSMQQueueManagement,&_GUID const LIBID_MSMQ,4,0,ATL::CComTypeInfoHolder>'}
0x18000dbdc  mov     [rbx+18h], rax
0x18000dbe0  lock inc cs:dword_180038608
0x18000dbe7  jmp     short loc_18000DBEB
0x18000dbe9  xor     ebx, ebx
0x18000dbeb  test    rbx, rbx
0x18000dbee  jz      short loc_18000DC3B
0x18000dbf0  lea     rcx, [rbx+28h]; this
0x18000dbf4  call    ?Init@CComAutoDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComAutoDeleteCriticalSection::Init(void)
0x18000dbf9  mov     edi, eax
0x18000dbfb  test    eax, eax
0x18000dbfd  js      short loc_18000DC09
0x18000dbff  mov     rcx, rbx; this
0x18000dc02  call    ?FinalConstruct@CMSMQManagement@@QEAAJXZ; CMSMQManagement::FinalConstruct(void)
0x18000dc07  mov     edi, eax
0x18000dc09  test    edi, edi
0x18000dc0b  jnz     short loc_18000DC27
0x18000dc0d  mov     rax, [rbx]
0x18000dc10  mov     r8, rsi
0x18000dc13  mov     rdx, rbp
0x18000dc16  mov     rcx, rbx
0x18000dc19  mov     rax, [rax]
0x18000dc1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc21  mov     edi, eax
0x18000dc23  test    eax, eax
0x18000dc25  jz      short loc_18000DC3B
0x18000dc27  mov     rax, [rbx]
0x18000dc2a  mov     edx, 1
0x18000dc2f  mov     rcx, rbx
0x18000dc32  mov     rax, [rax+20h]
0x18000dc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc3b  mov     eax, edi
0x18000dc3d  add     rsp, 28h
0x18000dc41  pop     rdi
0x18000dc42  pop     rsi
0x18000dc43  pop     rbp
0x18000dc44  pop     rbx
0x18000dc45  retn
```
