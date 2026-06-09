# CKsOutputPin::ProcessCompleteConnect(IPin *)

- ea: `0x18001aaf0`
- end: `0x18001b187`
- name: `?ProcessCompleteConnect@CKsOutputPin@@UEAAJPEAUIPin@@@Z`
- size: `1687`
- prototype: `__int64 __fastcall(CKsOutputPin *__hidden this, struct IPin *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002b58`
- `0x18000aaac`
- `0x18000df50`
- `0x180010b54`
- `0x18001aaf0`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x180025860`
- `0x180028fc0`
- `0x18003460c`
- `0x180035d90`
- `0x1800374f8`
- `0x18003755c`
- `0x18003b0a8`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001afed`
- `KERNEL32!GetLastError` at `0x18001b04f`
- `KERNEL32!GetLastError` at `0x18001b085`
- `KERNEL32!GetLastError` at `0x18001afed`
- `KERNEL32!GetLastError` at `0x18001b04f`
- `KERNEL32!GetLastError` at `0x18001b085`
- `KERNEL32!CreateEventW` at `0x18001ae99`
- `KERNEL32!CreateEventW` at `0x18001ae99`
- `KERNEL32!CloseHandle` at `0x18001af8e`
- `KERNEL32!CloseHandle` at `0x18001b01f`
- `KERNEL32!CloseHandle` at `0x18001b0ee`
- `KERNEL32!CloseHandle` at `0x18001af8e`
- `KERNEL32!CloseHandle` at `0x18001b01f`
- `KERNEL32!CloseHandle` at `0x18001b0ee`
- `ole32!CoCreateInstance` at `0x18001ad83`
- `ole32!CoCreateInstance` at `0x18001ad83`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::ProcessCompleteConnect(CKsOutputPin *this, struct IPin *a2)
{
  void **p_m_PinHandle; // r12
  IPin_vtbl *v4; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rax
  void *v6; // r14
  IKsPinEx *v7; // r15
  struct IKsPin *v8; // rsi
  int CompatibleInterface; // edi
  int CompatibleMedium; // eax
  __int64 result; // rax
  KSIDENTIFIER *p_m_CurrentInterface; // r14
  CBaseFilter *m_pFilter; // rdx
  __int64 v14; // xmm1_8
  void *v15; // rcx
  $BF1D6C6803037BEC0E57DD3D16D44AB2 v16; // xmm0
  __int64 v17; // xmm1_8
  IKsInterfaceHandler **p_m_InterfaceHandler; // rsi
  IKsControl *v19; // r14
  IKsControl_vtbl *v20; // rax
  HRESULT (__fastcall *KsEvent)(IKsControl *, KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *); // rax
  struct _ASYNC_ITEM *v22; // rsi
  HANDLE EventW; // rax
  IKsControl_vtbl *v24; // rax
  CAsyncItemHandler *m_pAsyncItemHandler; // rcx
  DWORD LastError; // eax
  DWORD v27; // eax
  signed int v28; // eax
  IKsInterfaceHandler *m_InterfaceHandler; // rcx
  IUnknown *m_UnkInner; // rcx
  _BYTE v31[32]; // [rsp+40h] [rbp-40h] BYREF
  struct KSIDENTIFIER v32; // [rsp+60h] [rbp-20h] BYREF
  struct IKsPin *v33; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v34; // [rsp+D0h] [rbp+50h] BYREF

  p_m_PinHandle = &this->m_PinHandle;
  if ( this->m_PinHandle )
  {
    CompatibleInterface = 0;
    p_m_CurrentInterface = &this->m_CurrentInterface;
    v7 = &this->IKsPinEx;
  }
  else
  {
    v33 = 0;
    v4 = a2->__vftable;
    memset(&v32, 0, sizeof(v32));
    QueryInterface = v4->QueryInterface;
    memset(v31, 0, 24);
    if ( QueryInterface(a2, &GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1, (void **)&v33) < 0 )
    {
      this->m_CurrentCommunication = KSPIN_COMMUNICATION_SINK;
      v7 = &this->IKsPinEx;
      v8 = (struct IKsPin *)((unsigned __int64)&this->IKsPinEx & -(__int64)(this != 0));
      result = FindCompatibleInterface(v8, 0, &v32);
      if ( (int)result < 0 )
        return result;
      *(_QWORD *)&v31[16] = 0;
      v6 = 0;
      *(GUID *)v31 = GUID_4747b320_62ce_11cf_a5d6_28db04c10000;
    }
    else
    {
      v6 = 0;
      if ( this->m_OriginalCommunication == KSPIN_COMMUNICATION_BOTH )
        this->m_CurrentCommunication = ChooseCommunicationMethod(this, v33);
      v7 = &this->IKsPinEx;
      v8 = (struct IKsPin *)((unsigned __int64)&this->IKsPinEx & -(__int64)(this != 0));
      CompatibleInterface = FindCompatibleInterface(v8, v33, &v32);
      if ( CompatibleInterface >= 0 )
      {
        CompatibleMedium = FindCompatibleMedium(
                             (struct IKsPin *)((unsigned __int64)&this->IKsPinEx & -(__int64)(this != 0)),
                             v33,
                             (struct KSIDENTIFIER *)v31);
        CompatibleInterface = CompatibleMedium;
        if ( CompatibleMedium >= 0 )
        {
          if ( CompatibleMedium == 1 )
          {
            this->m_MarshalData = 1;
          }
          else
          {
            if ( this->m_CurrentCommunication == KSPIN_COMMUNICATION_SOURCE )
            {
              v34 = 0;
              CompatibleInterface = v33->QueryInterface(v33, &GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1, (void **)&v34);
              if ( CompatibleInterface >= 0 )
              {
                CompatibleInterface = v33->KsCreateSinkPinHandle(v33, &v32, (KSIDENTIFIER *)v31);
                v6 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 24LL))(v34);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              }
            }
            this->m_MarshalData = 0;
          }
        }
      }
      v33->Release(v33);
      if ( CompatibleInterface < 0 )
        return (unsigned int)CompatibleInterface;
    }
    CompatibleInterface = CreatePinHandle(
                            &v32,
                            (struct KSIDENTIFIER *)v31,
                            v6,
                            &this->m_mt,
                            (struct CKsProxy *)this->m_pFilter,
                            this->m_PinFactoryId,
                            0x80000000,
                            p_m_PinHandle);
    if ( CompatibleInterface < 0 )
      goto LABEL_47;
    p_m_CurrentInterface = &this->m_CurrentInterface;
    m_pFilter = this->m_pFilter;
    v14 = *(_QWORD *)&v32.Id;
    v15 = *p_m_PinHandle;
    this->m_CurrentInterface.0 = v32.0;
    v16 = *($BF1D6C6803037BEC0E57DD3D16D44AB2 *)v31;
    *(_QWORD *)&this->m_CurrentInterface.Id = v14;
    v17 = *(_QWORD *)&v31[16];
    this->m_CurrentMedium.0 = v16;
    *(_QWORD *)&this->m_CurrentMedium.Id = v17;
    AggregateSets(
      v15,
      (HKEY)m_pFilter[4].IBaseFilter::IMediaFilter::IPersist::IUnknown::__vftable,
      &this->m_MarshalerList,
      v8);
    this->m_QualitySupport = VerifyQualitySupport(*p_m_PinHandle);
  }
  p_m_InterfaceHandler = &this->m_InterfaceHandler;
  if ( !this->m_InterfaceHandler && this->m_CurrentCommunication != KSPIN_COMMUNICATION_BRIDGE )
  {
    CompatibleInterface = CoCreateInstance(
                            &p_m_CurrentInterface->Set,
                            0,
                            0x401u,
                            &GUID_d3abc7e0_9a61_11d0_a40d_00a0c9223196,
                            (LPVOID *)&this->m_InterfaceHandler);
    if ( *p_m_InterfaceHandler )
    {
      (*p_m_InterfaceHandler)->KsSetPin(
        *p_m_InterfaceHandler,
        (IKsPin *)((unsigned __int64)v7 & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0xFu,
        &WPP_673e2124b19330a2d80119fad92a0606_Traceguids,
        this->m_pFilter->m_pName,
        this->m_pName);
    }
    if ( CompatibleInterface < 0 )
      goto LABEL_47;
  }
  if ( !this->m_hEOSevent )
  {
    LODWORD(v33) = 0;
    v19 = &this->IKsControl;
    v20 = this->IKsControl::IUnknown::__vftable;
    v32.Id = 4;
    v32.Flags = 512;
    KsEvent = v20->KsEvent;
    memset(v31, 0, sizeof(v31));
    v32.Set = GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000;
    if ( ((int (__fastcall *)(IKsControl *, struct KSIDENTIFIER *, __int64))KsEvent)(&this->IKsControl, &v32, 24) >= 0 )
    {
      v22 = (struct _ASYNC_ITEM *)operator new(0x30u);
      if ( !v22 )
      {
        CompatibleInterface = -2147024882;
        goto LABEL_47;
      }
      v32.Flags = 1;
      *(_DWORD *)v31 = 1;
      EventW = CreateEventW(0, 0, 0, 0);
      this->m_hEOSevent = EventW;
      if ( EventW )
      {
        v22->link.bLink = 0;
        v22->link.fLink = 0;
        v22->remove = 1;
        v22->event = this->m_hEOSevent;
        v22->context = this;
        v22->itemRoutine = (void (__fastcall *)(ASYNC_ITEM_STATUS, _ASYNC_ITEM *))CKsOutputPin::EOSEventHandler;
        *(_QWORD *)&v31[8] = this->m_hEOSevent;
        v24 = v19->__vftable;
        *(_OWORD *)&v31[16] = 0;
        CompatibleInterface = v24->KsEvent(&this->IKsControl, &v32, 24u, v31, 32u, (unsigned int *)&v33);
        if ( CompatibleInterface < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            LastError = GetLastError();
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              0x11u,
              &WPP_673e2124b19330a2d80119fad92a0606_Traceguids,
              LastError);
          }
          CloseHandle(this->m_hEOSevent);
          this->m_hEOSevent = 0;
          operator delete(v22, 0x30u);
          goto LABEL_47;
        }
        if ( (this->m_pAsyncItemHandler
           || (CompatibleInterface = this->InitializeAsyncThread(this), CompatibleInterface >= 0))
          && (m_pAsyncItemHandler = this->m_pAsyncItemHandler) != 0 )
        {
          CAsyncItemHandler::QueueAsyncItem(m_pAsyncItemHandler, v22);
        }
        else
        {
          v19->KsEvent(&this->IKsControl, 0, 0, v31, 32u, (unsigned int *)&v33);
          CloseHandle(this->m_hEOSevent);
          this->m_hEOSevent = 0;
          operator delete(v22, 0x30u);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          v27 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x12u, &WPP_673e2124b19330a2d80119fad92a0606_Traceguids, v27);
        }
        operator delete(v22, 0x30u);
        v28 = GetLastError();
        CompatibleInterface = v28;
        if ( v28 > 0 )
          CompatibleInterface = (unsigned __int16)v28 | 0x80070000;
      }
      if ( CompatibleInterface < 0 )
      {
LABEL_47:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            (unsigned int)&WPP_673e2124b19330a2d80119fad92a0606_Traceguids,
            this->m_pFilter->m_pName,
            (__int64)this->m_pName,
            CompatibleInterface);
        if ( *p_m_PinHandle )
        {
          CloseHandle(*p_m_PinHandle);
          *p_m_PinHandle = 0;
          this->m_QualitySupport = 0;
        }
        m_InterfaceHandler = this->m_InterfaceHandler;
        if ( m_InterfaceHandler )
        {
          this->m_InterfaceHandler = 0;
          m_InterfaceHandler->Release(m_InterfaceHandler);
        }
        if ( this->m_DataTypeHandler )
        {
          m_UnkInner = this->m_UnkInner;
          this->m_DataTypeHandler = 0;
          if ( m_UnkInner )
          {
            this->m_UnkInner = 0;
            m_UnkInner->Release(m_UnkInner);
          }
        }
        this->m_CurrentCommunication = this->m_OriginalCommunication;
        this->m_MarshalData = 1;
      }
    }
  }
  return (unsigned int)CompatibleInterface;
}

```

## disassembly

```asm
0x18001aaf0  mov     [rsp-38h+arg_8], rbx
0x18001aaf5  push    rbp
0x18001aaf6  push    rsi
0x18001aaf7  push    rdi
0x18001aaf8  push    r12
0x18001aafa  push    r13
0x18001aafc  push    r14
0x18001aafe  push    r15
0x18001ab00  mov     rbp, rsp
0x18001ab03  sub     rsp, 80h
0x18001ab0a  lea     r12, [rcx+208h]
0x18001ab11  xor     r13d, r13d
0x18001ab14  mov     r9, rdx
0x18001ab17  mov     rbx, rcx
0x18001ab1a  cmp     [r12], r13
0x18001ab1e  jnz     loc_18001AD3E
0x18001ab24  xor     eax, eax
0x18001ab26  mov     [rbp+arg_0], r13
0x18001ab2a  mov     qword ptr [rbp+var_20.Id], rax
0x18001ab2e  lea     r8, [rbp+arg_0]
0x18001ab32  mov     qword ptr [rbp+var_40+10h], rax
0x18001ab36  xorps   xmm0, xmm0
0x18001ab39  mov     rax, [rdx]
0x18001ab3c  xorps   xmm1, xmm1
0x18001ab3f  lea     rdx, _GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1
0x18001ab46  mov     rcx, r9
0x18001ab49  movups  xmmword ptr [rbp+var_20.___u0], xmm0
0x18001ab4d  mov     rax, [rax]
0x18001ab50  movups  xmmword ptr [rbp+var_40], xmm1
0x18001ab54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab59  test    eax, eax
0x18001ab5b  js      loc_18001AC59
0x18001ab61  cmp     dword ptr [rbx+24Ch], 3
0x18001ab68  mov     r14d, r13d
0x18001ab6b  jnz     short loc_18001AB7F
0x18001ab6d  mov     rdx, [rbp+arg_0]; struct IKsPin *
0x18001ab71  mov     rcx, rbx; struct CBasePin *
0x18001ab74  call    ?ChooseCommunicationMethod@@YA?AW4KSPIN_COMMUNICATION@@PEAVCBasePin@@PEAUIKsPin@@@Z; ChooseCommunicationMethod(CBasePin *,IKsPin *)
0x18001ab79  mov     [rbx+250h], eax
0x18001ab7f  mov     rdx, [rbp+arg_0]; struct IKsPin *
0x18001ab83  lea     r15, [rbx+180h]
0x18001ab8a  mov     rax, rbx
0x18001ab8d  lea     r8, [rbp+var_20]; struct KSIDENTIFIER *
0x18001ab91  neg     rax
0x18001ab94  sbb     rsi, rsi
0x18001ab97  and     rsi, r15
0x18001ab9a  mov     rcx, rsi; struct IKsPin *
0x18001ab9d  call    ?FindCompatibleInterface@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z; FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x18001aba2  mov     edi, eax
0x18001aba4  test    eax, eax
0x18001aba6  js      loc_18001AC40
0x18001abac  mov     rdx, [rbp+arg_0]; struct IKsPin *
0x18001abb0  lea     r8, [rbp+var_40]; struct KSIDENTIFIER *
0x18001abb4  mov     rcx, rsi; struct IKsPin *
0x18001abb7  call    ?FindCompatibleMedium@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z; FindCompatibleMedium(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x18001abbc  mov     edi, eax
0x18001abbe  test    eax, eax
0x18001abc0  js      short loc_18001AC40
0x18001abc2  cmp     eax, 1
0x18001abc5  jnz     short loc_18001ABCF
0x18001abc7  mov     [rbx+288h], eax
0x18001abcd  jmp     short loc_18001AC40
0x18001abcf  cmp     dword ptr [rbx+250h], 2
0x18001abd6  jnz     short loc_18001AC39
0x18001abd8  mov     rcx, [rbp+arg_0]
0x18001abdc  lea     r8, [rbp+arg_10]
0x18001abe0  mov     [rbp+arg_10], r13
0x18001abe4  lea     rdx, _GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1
0x18001abeb  mov     rax, [rcx]
0x18001abee  mov     rax, [rax]
0x18001abf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abf6  mov     edi, eax
0x18001abf8  test    eax, eax
0x18001abfa  js      short loc_18001AC39
0x18001abfc  mov     rcx, [rbp+arg_0]
0x18001ac00  lea     r8, [rbp+var_40]
0x18001ac04  lea     rdx, [rbp+var_20]
0x18001ac08  mov     rax, [rcx]
0x18001ac0b  mov     rax, [rax+28h]
0x18001ac0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac14  mov     rcx, [rbp+arg_10]
0x18001ac18  mov     edi, eax
0x18001ac1a  mov     rax, [rcx]
0x18001ac1d  mov     rax, [rax+18h]
0x18001ac21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac26  mov     rcx, [rbp+arg_10]
0x18001ac2a  mov     r14, rax
0x18001ac2d  mov     rdx, [rcx]
0x18001ac30  mov     rax, [rdx+10h]
0x18001ac34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac39  mov     [rbx+288h], r13d
0x18001ac40  mov     rcx, [rbp+arg_0]
0x18001ac44  mov     rax, [rcx]
0x18001ac47  mov     rax, [rax+10h]
0x18001ac4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac50  test    edi, edi
0x18001ac52  jns     short loc_18001AC9F
0x18001ac54  jmp     loc_18001B169
0x18001ac59  mov     rax, rbx
0x18001ac5c  mov     dword ptr [rbx+250h], 1
0x18001ac66  neg     rax
0x18001ac69  lea     r15, [rbx+180h]
0x18001ac70  lea     r8, [rbp+var_20]; struct KSIDENTIFIER *
0x18001ac74  sbb     rsi, rsi
0x18001ac77  xor     edx, edx; struct IKsPin *
0x18001ac79  and     rsi, r15
0x18001ac7c  mov     rcx, rsi; struct IKsPin *
0x18001ac7f  call    ?FindCompatibleInterface@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z; FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x18001ac84  test    eax, eax
0x18001ac86  js      loc_18001B16B
0x18001ac8c  movups  xmm0, xmmword ptr cs:_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1
0x18001ac93  mov     qword ptr [rbp+var_40+10h], r13
0x18001ac97  mov     r14, r13
0x18001ac9a  movdqu  xmmword ptr [rbp+var_40], xmm0
0x18001ac9f  mov     eax, [rbx+248h]
0x18001aca5  lea     r9, [rbx+68h]; struct CMediaType *
0x18001aca9  mov     [rsp+80h+var_48], r12; void **
0x18001acae  lea     rdx, [rbp+var_40]; struct KSIDENTIFIER *
0x18001acb2  mov     [rsp+80h+var_50], 80000000h; unsigned int
0x18001acba  lea     rcx, [rbp+var_20]; struct KSIDENTIFIER *
0x18001acbe  mov     [rsp+80h+var_58], eax; unsigned int
0x18001acc2  mov     r8, r14; void *
0x18001acc5  mov     rax, [rbx+50h]
0x18001acc9  mov     [rsp+80h+ppv], rax; struct CKsProxy *
0x18001acce  call    ?CreatePinHandle@@YAJAEAUKSIDENTIFIER@@0PEAXPEAVCMediaType@@PEAVCKsProxy@@KKPEAPEAX@Z; CreatePinHandle(KSIDENTIFIER &,KSIDENTIFIER &,void *,CMediaType *,CKsProxy *,ulong,ulong,void * *)
0x18001acd3  mov     edi, eax
0x18001acd5  test    eax, eax
0x18001acd7  js      loc_18001B0A8
0x18001acdd  movups  xmm0, xmmword ptr [rbp+var_20.___u0]
0x18001ace1  lea     r14, [rbx+258h]
0x18001ace8  mov     rdx, [rbx+50h]
0x18001acec  movsd   xmm1, qword ptr [rbp+var_20.Id]
0x18001acf1  lea     r8, [rbx+2A8h]; this
0x18001acf8  mov     rcx, [r12]; hFile
0x18001acfc  mov     r9, rsi
0x18001acff  movups  xmmword ptr [r14], xmm0
0x18001ad03  movups  xmm0, xmmword ptr [rbp+var_40]
0x18001ad07  movsd   qword ptr [r14+10h], xmm1
0x18001ad0d  movsd   xmm1, qword ptr [rbp+var_40+10h]
0x18001ad12  movups  xmmword ptr [rbx+270h], xmm0
0x18001ad19  movsd   qword ptr [rbx+280h], xmm1
0x18001ad21  mov     rdx, [rdx+1F8h]; hKey
0x18001ad28  call    ?AggregateSets@@YAJPEAXPEAUHKEY__@@PEAV?$CGenericList@VCAggregateMarshaler@@@@PEAUIUnknown@@@Z; AggregateSets(void *,HKEY__ *,CGenericList<CAggregateMarshaler> *,IUnknown *)
0x18001ad2d  mov     rcx, [r12]; void *
0x18001ad31  call    ?VerifyQualitySupport@@YAHPEAX@Z; VerifyQualitySupport(void *)
0x18001ad36  mov     [rbx+348h], eax
0x18001ad3c  jmp     short loc_18001AD4F
0x18001ad3e  mov     edi, r13d
0x18001ad41  lea     r14, [rcx+258h]
0x18001ad48  lea     r15, [rcx+180h]
0x18001ad4f  lea     rsi, [rbx+240h]
0x18001ad56  cmp     [rsi], r13
0x18001ad59  jnz     loc_18001ADF4
0x18001ad5f  cmp     dword ptr [rbx+250h], 4
0x18001ad66  jz      loc_18001ADF4
0x18001ad6c  lea     r9, _GUID_d3abc7e0_9a61_11d0_a40d_00a0c9223196; riid
0x18001ad73  mov     [rsp+80h+ppv], rsi; ppv
0x18001ad78  xor     edx, edx; pUnkOuter
0x18001ad7a  mov     r8d, 401h; dwClsContext
0x18001ad80  mov     rcx, r14; rclsid
0x18001ad83  call    cs:__imp_CoCreateInstance
0x18001ad8a  nop     dword ptr [rax+rax+00h]
0x18001ad8f  mov     rcx, [rsi]
0x18001ad92  mov     edi, eax
0x18001ad94  test    rcx, rcx
0x18001ad97  jz      short loc_18001ADB3
0x18001ad99  mov     r8, [rcx]
0x18001ad9c  mov     rax, rbx
0x18001ad9f  neg     rax
0x18001ada2  sbb     rdx, rdx
0x18001ada5  mov     rax, [r8+18h]
0x18001ada9  and     rdx, r15
0x18001adac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adb1  jmp     short loc_18001ADEC
0x18001adb3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adba  lea     rax, WPP_GLOBAL_Control
0x18001adc1  cmp     rcx, rax
0x18001adc4  jz      short loc_18001ADEC
0x18001adc6  mov     r9, [rbx+50h]
0x18001adca  lea     r8, WPP_673e2124b19330a2d80119fad92a0606_Traceguids
0x18001add1  mov     rax, [rbx+28h]
0x18001add5  mov     edx, 0Fh
0x18001adda  mov     rcx, [rcx+10h]
0x18001adde  mov     [rsp+80h+ppv], rax
0x18001ade3  mov     r9, [r9+58h]
0x18001ade7  call    WPP_SF_SS
0x18001adec  test    edi, edi
0x18001adee  js      loc_18001B0A8
0x18001adf4  cmp     [rbx+3C8h], r13
0x18001adfb  jnz     loc_18001B169
0x18001ae01  movups  xmm1, xmmword ptr cs:_GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000.Data1
0x18001ae08  mov     dword ptr [rbp+arg_0], r13d
0x18001ae0c  lea     r14, [rbx+1C0h]
0x18001ae13  mov     rax, [r14]
0x18001ae16  xorps   xmm0, xmm0
0x18001ae19  xor     r9d, r9d
0x18001ae1c  mov     [rbp+var_20.Id], 4
0x18001ae23  lea     rcx, [rbp+arg_0]
0x18001ae27  mov     [rbp+var_20.Flags], 200h
0x18001ae2e  mov     qword ptr [rsp+80h+var_58], rcx
0x18001ae33  lea     rdx, [rbp+var_20]
0x18001ae37  mov     rax, [rax+28h]
0x18001ae3b  mov     rcx, r14
0x18001ae3e  lea     r8d, [r9+18h]
0x18001ae42  mov     dword ptr [rsp+80h+ppv], r13d
0x18001ae47  movups  xmmword ptr [rbp+var_40], xmm0
0x18001ae4b  movups  xmmword ptr [rbp+var_40+10h], xmm0
0x18001ae4f  movdqu  xmmword ptr [rbp+var_20.___u0], xmm1
0x18001ae54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae59  test    eax, eax
0x18001ae5b  js      loc_18001B169
0x18001ae61  mov     r15d, 30h ; '0'
0x18001ae67  mov     ecx, r15d; Size
0x18001ae6a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ae6f  mov     rsi, rax
0x18001ae72  test    rax, rax
0x18001ae75  jnz     short loc_18001AE81
0x18001ae77  mov     edi, 8007000Eh
0x18001ae7c  jmp     loc_18001B0A8
0x18001ae81  xor     r9d, r9d; lpName
0x18001ae84  mov     [rbp+var_20.Flags], 1
0x18001ae8b  xor     r8d, r8d; bInitialState
0x18001ae8e  mov     dword ptr [rbp+var_40], 1
0x18001ae95  xor     edx, edx; bManualReset
0x18001ae97  xor     ecx, ecx; lpEventAttributes
0x18001ae99  call    cs:__imp_CreateEventW
0x18001aea0  nop     dword ptr [rax+rax+00h]
0x18001aea5  mov     [rbx+3C8h], rax
0x18001aeac  test    rax, rax
0x18001aeaf  jz      loc_18001B03F
0x18001aeb5  mov     [rsi+8], r13
0x18001aeb9  lea     rcx, [rbp+arg_0]
0x18001aebd  mov     [rsi], r13
0x18001aec0  lea     r9, [rbp+var_40]
0x18001aec4  mov     byte ptr [rsi+10h], 1
0x18001aec8  lea     rdx, [rbp+var_20]
0x18001aecc  mov     rax, [rbx+3C8h]
0x18001aed3  xorps   xmm0, xmm0
0x18001aed6  mov     [rsi+18h], rax
0x18001aeda  mov     r8d, 18h
0x18001aee0  mov     [rsi+28h], rbx
0x18001aee4  lea     rax, ?EOSEventHandler@CKsOutputPin@@SAXW4ASYNC_ITEM_STATUS@@PEAU_ASYNC_ITEM@@@Z; CKsOutputPin::EOSEventHandler(ASYNC_ITEM_STATUS,_ASYNC_ITEM *)
0x18001aeeb  mov     [rsi+20h], rax
0x18001aeef  mov     rax, [rbx+3C8h]
0x18001aef6  mov     qword ptr [rbp+var_40+8], rax
0x18001aefa  mov     rax, [r14]
0x18001aefd  mov     qword ptr [rsp+80h+var_58], rcx
0x18001af02  mov     rcx, r14
0x18001af05  movups  xmmword ptr [rbp+var_40+10h], xmm0
0x18001af09  mov     dword ptr [rsp+80h+ppv], 20h ; ' '
0x18001af11  mov     rax, [rax+28h]
0x18001af15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af1a  mov     edi, eax
0x18001af1c  test    eax, eax
0x18001af1e  js      loc_18001AFDD
0x18001af24  cmp     [rbx+3D8h], r13
0x18001af2b  jnz     short loc_18001AF45
0x18001af2d  mov     rax, [rbx]
0x18001af30  mov     rcx, rbx
0x18001af33  mov     rax, [rax+0C0h]
0x18001af3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af3f  mov     edi, eax
0x18001af41  test    eax, eax
0x18001af43  js      short loc_18001AF5E
0x18001af45  mov     rcx, [rbx+3D8h]; this
0x18001af4c  test    rcx, rcx
0x18001af4f  jz      short loc_18001AF5E
0x18001af51  mov     rdx, rsi; struct _ASYNC_ITEM *
0x18001af54  call    ?QueueAsyncItem@CAsyncItemHandler@@QEAAKPEAU_ASYNC_ITEM@@@Z; CAsyncItemHandler::QueueAsyncItem(_ASYNC_ITEM *)
0x18001af59  jmp     loc_18001B0A0
0x18001af5e  mov     rax, [r14]
0x18001af61  lea     rcx, [rbp+arg_0]
0x18001af65  mov     qword ptr [rsp+80h+var_58], rcx
0x18001af6a  lea     r9, [rbp+var_40]
0x18001af6e  xor     r8d, r8d
0x18001af71  mov     dword ptr [rsp+80h+ppv], 20h ; ' '
0x18001af79  xor     edx, edx
0x18001af7b  mov     rcx, r14
0x18001af7e  mov     rax, [rax+28h]
0x18001af82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af87  mov     rcx, [rbx+3C8h]; hObject
0x18001af8e  call    cs:__imp_CloseHandle
0x18001af95  nop     dword ptr [rax+rax+00h]
0x18001af9a  mov     rdx, r15; unsigned __int64
0x18001af9d  mov     [rbx+3C8h], r13
0x18001afa4  mov     rcx, rsi; void *
0x18001afa7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001afac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afb3  lea     rax, WPP_GLOBAL_Control
0x18001afba  cmp     rcx, rax
0x18001afbd  jz      loc_18001B0A0
0x18001afc3  mov     rcx, [rcx+10h]
0x18001afc7  lea     r8, WPP_673e2124b19330a2d80119fad92a0606_Traceguids
0x18001afce  mov     edx, 10h
0x18001afd3  call    WPP_SF_
0x18001afd8  jmp     loc_18001B0A0
0x18001afdd  lea     rax, WPP_GLOBAL_Control
0x18001afe4  cmp     cs:WPP_GLOBAL_Control, rax
0x18001afeb  jz      short loc_18001B018
0x18001afed  call    cs:__imp_GetLastError
  ... truncated ...
```
