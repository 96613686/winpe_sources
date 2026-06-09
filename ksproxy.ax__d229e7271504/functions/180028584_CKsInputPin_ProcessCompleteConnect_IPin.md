# CKsInputPin::ProcessCompleteConnect(IPin *)

- ea: `0x180028584`
- end: `0x1800288dd`
- name: `?ProcessCompleteConnect@CKsInputPin@@QEAAJPEAUIPin@@@Z`
- size: `857`
- prototype: `__int64 __fastcall(CKsInputPin *__hidden this, struct IPin *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002c50`
- `0x180026da0`

## callees

- `0x18000aaac`
- `0x180010b54`
- `0x180022ec4`
- `0x180024e3c`
- `0x180028584`
- `0x18003460c`
- `0x180035d90`
- `0x180036b7c`
- `0x1800374f8`
- `0x18003755c`
- `0x180045010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18002882a`
- `ole32!CoCreateInstance` at `0x18002882a`

## pseudocode

```c
__int64 __fastcall CKsInputPin::ProcessCompleteConnect(CKsInputPin *this, struct IPin *a2)
{
  void **p_m_PinHandle; // r12
  IPin_vtbl *v4; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rax
  void *v6; // r15
  IKsPinEx *v7; // r14
  struct IKsPin *v8; // rsi
  int Instance; // edi
  int CompatibleMedium; // eax
  __int64 result; // rax
  KSIDENTIFIER *p_m_CurrentInterface; // r15
  CBaseFilter *m_pFilter; // rdx
  __int64 v14; // xmm1_8
  void *v15; // rcx
  $BF1D6C6803037BEC0E57DD3D16D44AB2 v16; // xmm0
  __int64 v17; // xmm1_8
  IKsInterfaceHandler **p_m_InterfaceHandler; // rsi
  struct KSIDENTIFIER v19; // [rsp+40h] [rbp-30h] BYREF
  struct KSIDENTIFIER v20; // [rsp+58h] [rbp-18h] BYREF
  struct IKsPin *v21; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v22; // [rsp+B0h] [rbp+40h] BYREF

  p_m_PinHandle = &this->m_PinHandle;
  if ( this->m_PinHandle )
  {
    Instance = 0;
    p_m_CurrentInterface = &this->m_CurrentInterface;
    v7 = &this->IKsPinEx;
LABEL_20:
    p_m_InterfaceHandler = &this->m_InterfaceHandler;
    if ( this->m_InterfaceHandler || this->m_CurrentCommunication == KSPIN_COMMUNICATION_BRIDGE )
      goto LABEL_34;
    Instance = CoCreateInstance(
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
        0xCu,
        &WPP_51c792051e8832a7f1dd74ffd1c33eda_Traceguids,
        this->m_pFilter->m_pName,
        this->m_pName);
    }
    if ( Instance >= 0 )
    {
LABEL_34:
      if ( this->m_MarshalData )
        Instance = CKsProxy::StartIoThread((CKsProxy *)this->m_pFilter);
      if ( Instance >= 0 )
        return (unsigned int)CKsProxy::InitiateEndOfStreamNotification(
                               (CKsProxy *)this->m_pFilter,
                               (char *)this->m_PinHandle);
    }
    return (unsigned int)Instance;
  }
  v21 = 0;
  v4 = a2->__vftable;
  memset(&v20, 0, sizeof(v20));
  QueryInterface = v4->QueryInterface;
  memset(&v19, 0, sizeof(v19));
  if ( QueryInterface(a2, &GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1, (void **)&v21) < 0 )
  {
    this->m_CurrentCommunication = KSPIN_COMMUNICATION_SINK;
    v7 = &this->IKsPinEx;
    v8 = (struct IKsPin *)((unsigned __int64)&this->IKsPinEx & -(__int64)(this != 0));
    result = FindCompatibleInterface(v8, 0, &v20);
    if ( (int)result < 0 )
      return result;
    *(_QWORD *)&v19.Id = 0;
    v6 = 0;
    v19.Set = GUID_4747b320_62ce_11cf_a5d6_28db04c10000;
  }
  else
  {
    v6 = 0;
    if ( this->m_OriginalCommunication == KSPIN_COMMUNICATION_BOTH )
      this->m_CurrentCommunication = ChooseCommunicationMethod(this, v21);
    v7 = &this->IKsPinEx;
    v8 = (struct IKsPin *)((unsigned __int64)&this->IKsPinEx & -(__int64)(this != 0));
    Instance = FindCompatibleInterface(v8, v21, &v20);
    if ( Instance >= 0 )
    {
      CompatibleMedium = FindCompatibleMedium(
                           (struct IKsPin *)((unsigned __int64)&this->IKsPinEx & -(__int64)(this != 0)),
                           v21,
                           &v19);
      Instance = CompatibleMedium;
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
            v22 = 0;
            Instance = v21->QueryInterface(v21, &GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1, (void **)&v22);
            if ( Instance >= 0 )
            {
              Instance = v21->KsCreateSinkPinHandle(v21, &v20, &v19);
              v6 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 24LL))(v22);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
            }
          }
          this->m_MarshalData = 0;
        }
      }
    }
    v21->Release(v21);
    if ( Instance < 0 )
      return (unsigned int)Instance;
  }
  Instance = CreatePinHandle(
               &v20,
               &v19,
               v6,
               &this->m_mt,
               (struct CKsProxy *)this->m_pFilter,
               this->m_PinFactoryId,
               0x40000000u,
               p_m_PinHandle);
  if ( Instance >= 0 )
  {
    p_m_CurrentInterface = &this->m_CurrentInterface;
    m_pFilter = this->m_pFilter;
    v14 = *(_QWORD *)&v20.Id;
    v15 = *p_m_PinHandle;
    this->m_CurrentInterface.0 = v20.0;
    v16 = v19.0;
    *(_QWORD *)&this->m_CurrentInterface.Id = v14;
    v17 = *(_QWORD *)&v19.Id;
    this->m_CurrentMedium.0 = v16;
    *(_QWORD *)&this->m_CurrentMedium.Id = v17;
    AggregateSets(
      v15,
      (HKEY)m_pFilter[4].IBaseFilter::IMediaFilter::IPersist::IUnknown::__vftable,
      &this->m_MarshalerList,
      v8);
    this->m_QualitySupport = EstablishQualitySupport(v7, *p_m_PinHandle, (struct CKsProxy *)this->m_pFilter);
    goto LABEL_20;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180028584  mov     [rsp-28h+arg_8], rbx
0x180028589  mov     [rsp-28h+arg_18], rsi
0x18002858e  push    rbp
0x18002858f  push    rdi
0x180028590  push    r12
0x180028592  push    r14
0x180028594  push    r15
0x180028596  mov     rbp, rsp
0x180028599  sub     rsp, 70h
0x18002859d  lea     r12, [rcx+178h]
0x1800285a4  mov     r9, rdx
0x1800285a7  cmp     qword ptr [r12], 0
0x1800285ac  mov     rbx, rcx
0x1800285af  jnz     loc_1800287E5
0x1800285b5  xor     eax, eax
0x1800285b7  mov     [rbp+arg_0], 0
0x1800285bf  mov     qword ptr [rbp+var_18.Id], rax
0x1800285c3  lea     r8, [rbp+arg_0]
0x1800285c7  mov     qword ptr [rbp+var_30.Id], rax
0x1800285cb  xorps   xmm0, xmm0
0x1800285ce  mov     rax, [rdx]
0x1800285d1  xorps   xmm1, xmm1
0x1800285d4  lea     rdx, _GUID_b61178d1_a2d9_11cf_9e53_00aa00a216a1
0x1800285db  mov     rcx, r9
0x1800285de  movups  xmmword ptr [rbp+var_18.___u0], xmm0
0x1800285e2  mov     rax, [rax]
0x1800285e5  movups  xmmword ptr [rbp+var_30.___u0], xmm1
0x1800285e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285ee  test    eax, eax
0x1800285f0  js      loc_1800286F5
0x1800285f6  xor     r15d, r15d
0x1800285f9  cmp     dword ptr [rbx+19Ch], 3
0x180028600  jnz     short loc_180028614
0x180028602  mov     rdx, [rbp+arg_0]; struct IKsPin *
0x180028606  mov     rcx, rbx; struct CBasePin *
0x180028609  call    ?ChooseCommunicationMethod@@YA?AW4KSPIN_COMMUNICATION@@PEAVCBasePin@@PEAUIKsPin@@@Z; ChooseCommunicationMethod(CBasePin *,IKsPin *)
0x18002860e  mov     [rbx+1A0h], eax
0x180028614  mov     rdx, [rbp+arg_0]; struct IKsPin *
0x180028618  lea     r14, [rbx+138h]
0x18002861f  mov     rax, rbx
0x180028622  lea     r8, [rbp+var_18]; struct KSIDENTIFIER *
0x180028626  neg     rax
0x180028629  sbb     rsi, rsi
0x18002862c  and     rsi, r14
0x18002862f  mov     rcx, rsi; struct IKsPin *
0x180028632  call    ?FindCompatibleInterface@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z; FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x180028637  mov     edi, eax
0x180028639  test    eax, eax
0x18002863b  js      loc_1800286DC
0x180028641  mov     rdx, [rbp+arg_0]; struct IKsPin *
0x180028645  lea     r8, [rbp+var_30]; struct KSIDENTIFIER *
0x180028649  mov     rcx, rsi; struct IKsPin *
0x18002864c  call    ?FindCompatibleMedium@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z; FindCompatibleMedium(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x180028651  mov     edi, eax
0x180028653  test    eax, eax
0x180028655  js      loc_1800286DC
0x18002865b  cmp     eax, 1
0x18002865e  jnz     short loc_180028668
0x180028660  mov     [rbx+1DCh], eax
0x180028666  jmp     short loc_1800286DC
0x180028668  cmp     dword ptr [rbx+1A0h], 2
0x18002866f  jnz     short loc_1800286D2
0x180028671  mov     rcx, [rbp+arg_0]
0x180028675  lea     r8, [rbp+arg_10]
0x180028679  mov     [rbp+arg_10], r15
0x18002867d  lea     rdx, _GUID_423c13a2_2070_11d0_9ef7_00aa00a216a1
0x180028684  mov     rax, [rcx]
0x180028687  mov     rax, [rax]
0x18002868a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002868f  mov     edi, eax
0x180028691  test    eax, eax
0x180028693  js      short loc_1800286D2
0x180028695  mov     rcx, [rbp+arg_0]
0x180028699  lea     r8, [rbp+var_30]
0x18002869d  lea     rdx, [rbp+var_18]
0x1800286a1  mov     rax, [rcx]
0x1800286a4  mov     rax, [rax+28h]
0x1800286a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286ad  mov     rcx, [rbp+arg_10]
0x1800286b1  mov     edi, eax
0x1800286b3  mov     rax, [rcx]
0x1800286b6  mov     rax, [rax+18h]
0x1800286ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286bf  mov     rcx, [rbp+arg_10]
0x1800286c3  mov     r15, rax
0x1800286c6  mov     rdx, [rcx]
0x1800286c9  mov     rax, [rdx+10h]
0x1800286cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286d2  mov     dword ptr [rbx+1DCh], 0
0x1800286dc  mov     rcx, [rbp+arg_0]
0x1800286e0  mov     rax, [rcx]
0x1800286e3  mov     rax, [rax+10h]
0x1800286e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286ec  test    edi, edi
0x1800286ee  jns     short loc_18002873F
0x1800286f0  jmp     loc_1800288C1
0x1800286f5  mov     rax, rbx
0x1800286f8  mov     dword ptr [rbx+1A0h], 1
0x180028702  neg     rax
0x180028705  lea     r14, [rbx+138h]
0x18002870c  lea     r8, [rbp+var_18]; struct KSIDENTIFIER *
0x180028710  sbb     rsi, rsi
0x180028713  xor     edx, edx; struct IKsPin *
0x180028715  and     rsi, r14
0x180028718  mov     rcx, rsi; struct IKsPin *
0x18002871b  call    ?FindCompatibleInterface@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z; FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)
0x180028720  test    eax, eax
0x180028722  js      loc_1800288C3
0x180028728  movups  xmm0, xmmword ptr cs:_GUID_4747b320_62ce_11cf_a5d6_28db04c10000.Data1
0x18002872f  mov     qword ptr [rbp+var_30.Id], 0
0x180028737  xor     r15d, r15d
0x18002873a  movdqu  xmmword ptr [rbp+var_30.___u0], xmm0
0x18002873f  mov     eax, [rbx+198h]
0x180028745  lea     r9, [rbx+68h]; struct CMediaType *
0x180028749  mov     [rsp+70h+var_38], r12; void **
0x18002874e  lea     rdx, [rbp+var_30]; struct KSIDENTIFIER *
0x180028752  mov     [rsp+70h+var_40], 40000000h; unsigned int
0x18002875a  lea     rcx, [rbp+var_18]; struct KSIDENTIFIER *
0x18002875e  mov     [rsp+70h+var_48], eax; unsigned int
0x180028762  mov     r8, r15; void *
0x180028765  mov     rax, [rbx+50h]
0x180028769  mov     [rsp+70h+ppv], rax; struct CKsProxy *
0x18002876e  call    ?CreatePinHandle@@YAJAEAUKSIDENTIFIER@@0PEAXPEAVCMediaType@@PEAVCKsProxy@@KKPEAPEAX@Z; CreatePinHandle(KSIDENTIFIER &,KSIDENTIFIER &,void *,CMediaType *,CKsProxy *,ulong,ulong,void * *)
0x180028773  mov     edi, eax
0x180028775  test    eax, eax
0x180028777  js      loc_1800288C1
0x18002877d  movups  xmm0, xmmword ptr [rbp+var_18.___u0]
0x180028781  lea     r15, [rbx+1A8h]
0x180028788  mov     rdx, [rbx+50h]
0x18002878c  movsd   xmm1, qword ptr [rbp+var_18.Id]
0x180028791  lea     r8, [rbx+218h]; this
0x180028798  mov     rcx, [r12]; hFile
0x18002879c  mov     r9, rsi
0x18002879f  movups  xmmword ptr [r15], xmm0
0x1800287a3  movups  xmm0, xmmword ptr [rbp+var_30.___u0]
0x1800287a7  movsd   qword ptr [r15+10h], xmm1
0x1800287ad  movsd   xmm1, qword ptr [rbp+var_30.Id]
0x1800287b2  movups  xmmword ptr [rbx+1C0h], xmm0
0x1800287b9  movsd   qword ptr [rbx+1D0h], xmm1
0x1800287c1  mov     rdx, [rdx+1F8h]; hKey
0x1800287c8  call    ?AggregateSets@@YAJPEAXPEAUHKEY__@@PEAV?$CGenericList@VCAggregateMarshaler@@@@PEAUIUnknown@@@Z; AggregateSets(void *,HKEY__ *,CGenericList<CAggregateMarshaler> *,IUnknown *)
0x1800287cd  mov     r8, [rbx+50h]; struct CKsProxy *
0x1800287d1  mov     rcx, r14; struct IKsPin *
0x1800287d4  mov     rdx, [r12]; void *
0x1800287d8  call    ?EstablishQualitySupport@@YAHPEAUIKsPin@@PEAXPEAVCKsProxy@@@Z; EstablishQualitySupport(IKsPin *,void *,CKsProxy *)
0x1800287dd  mov     [rbx+240h], eax
0x1800287e3  jmp     short loc_1800287F5
0x1800287e5  xor     edi, edi
0x1800287e7  lea     r15, [rcx+1A8h]
0x1800287ee  lea     r14, [rcx+138h]
0x1800287f5  lea     rsi, [rbx+190h]
0x1800287fc  cmp     qword ptr [rsi], 0
0x180028800  jnz     loc_180028897
0x180028806  cmp     dword ptr [rbx+1A0h], 4
0x18002880d  jz      loc_180028897
0x180028813  lea     r9, _GUID_d3abc7e0_9a61_11d0_a40d_00a0c9223196; riid
0x18002881a  mov     [rsp+70h+ppv], rsi; ppv
0x18002881f  xor     edx, edx; pUnkOuter
0x180028821  mov     r8d, 401h; dwClsContext
0x180028827  mov     rcx, r15; rclsid
0x18002882a  call    cs:__imp_CoCreateInstance
0x180028831  nop     dword ptr [rax+rax+00h]
0x180028836  mov     rcx, [rsi]
0x180028839  mov     edi, eax
0x18002883b  test    rcx, rcx
0x18002883e  jz      short loc_18002885A
0x180028840  mov     r8, [rcx]
0x180028843  mov     rax, rbx
0x180028846  neg     rax
0x180028849  sbb     rdx, rdx
0x18002884c  mov     rax, [r8+18h]
0x180028850  and     rdx, r14
0x180028853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028858  jmp     short loc_180028893
0x18002885a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028861  lea     rax, WPP_GLOBAL_Control
0x180028868  cmp     rcx, rax
0x18002886b  jz      short loc_180028893
0x18002886d  mov     r9, [rbx+50h]
0x180028871  lea     r8, WPP_51c792051e8832a7f1dd74ffd1c33eda_Traceguids
0x180028878  mov     rax, [rbx+28h]
0x18002887c  mov     edx, 0Ch
0x180028881  mov     rcx, [rcx+10h]
0x180028885  mov     [rsp+70h+ppv], rax
0x18002888a  mov     r9, [r9+58h]
0x18002888e  call    WPP_SF_SS
0x180028893  test    edi, edi
0x180028895  js      short loc_1800288C1
0x180028897  cmp     dword ptr [rbx+1DCh], 0
0x18002889e  jz      short loc_1800288AB
0x1800288a0  mov     rcx, [rbx+50h]; this
0x1800288a4  call    ?StartIoThread@CKsProxy@@QEAAJXZ; CKsProxy::StartIoThread(void)
0x1800288a9  mov     edi, eax
0x1800288ab  test    edi, edi
0x1800288ad  js      short loc_1800288C1
0x1800288af  mov     rdx, [rbx+178h]; hFile
0x1800288b6  mov     rcx, [rbx+50h]; this
0x1800288ba  call    ?InitiateEndOfStreamNotification@CKsProxy@@QEAAJPEAX@Z; CKsProxy::InitiateEndOfStreamNotification(void *)
0x1800288bf  mov     edi, eax
0x1800288c1  mov     eax, edi
0x1800288c3  lea     r11, [rsp+70h+var_s0]
0x1800288c8  mov     rbx, [r11+38h]
0x1800288cc  mov     rsi, [r11+48h]
0x1800288d0  mov     rsp, r11
0x1800288d3  pop     r15
0x1800288d5  pop     r14
0x1800288d7  pop     r12
0x1800288d9  pop     rdi
0x1800288da  pop     rbp
0x1800288db  retn
```
