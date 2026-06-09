# CSNOCplCore::~CSNOCplCore(void)

- ea: `0x180008248`
- end: `0x1800084c0`
- name: `??1CSNOCplCore@@QEAA@XZ`
- size: `632`
- prototype: `void __fastcall(CSNOCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010260`

## callees

- `0x180006b70`
- `0x180007618`
- `0x1800077a4`
- `0x180007e50`
- `0x180008248`
- `0x1800086f4`
- `0x180011fa8`
- `0x1800155d0`
- `0x1800159c4`
- `0x180019510`
- `0x180019950`
- `0x18001e4a8`
- `0x18001e500`
- `0x18001ee80`
- `0x18001f2dc`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800082aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800082aa`

## pseudocode

```c
void __fastcall CSNOCplCore::~CSNOCplCore(CSNOCplCore *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx
  CServiceMonitor *v5; // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  CServiceMonitor *v7; // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  CServiceMonitor *v9; // rcx
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  CWwanHelper *v11; // rcx
  __int64 *i; // rbx
  _QWORD *v13; // rbx
  _QWORD *v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx

  *(_QWORD *)this = &CSNOCplCore::`vftable'{for `INotifyNetworkEventsPrivate'};
  *((_QWORD *)this + 1) = &CSNOCplCore::`vftable'{for `INotifyNetworkSignatureEventsPrivate'};
  *((_QWORD *)this + 2) = &CSNOCplCore::`vftable'{for `INetConnectionNotifySink'};
  *((_QWORD *)this + 13) = &CSNOCplCore::`vftable';
  v2 = *((_QWORD *)this + 19);
  if ( v2 )
  {
    ClearProfileDataMap(v2);
    v3 = (void *)*((_QWORD *)this + 19);
    if ( v3 )
      std::map<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>>::`scalar deleting destructor'(v3);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v4 = *((_QWORD *)this + 43);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (CServiceMonitor *)*((_QWORD *)this + 33);
  if ( v5 )
  {
    CServiceMonitor::Stop(v5);
    v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 33);
    if ( v6 )
      (**v6)(v6, 1);
  }
  v7 = (CServiceMonitor *)*((_QWORD *)this + 34);
  if ( v7 )
  {
    CServiceMonitor::Stop(v7);
    v8 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 34);
    if ( v8 )
      (**v8)(v8, 1);
  }
  v9 = (CServiceMonitor *)*((_QWORD *)this + 35);
  if ( v9 )
  {
    CServiceMonitor::Stop(v9);
    v10 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 35);
    if ( v10 )
      (**v10)(v10, 1);
  }
  CWlanHelper::UnregisterWLANEvent((char *)this + 184);
  v11 = (CWwanHelper *)*((_QWORD *)this + 26);
  if ( v11 )
  {
    CWwanHelper::UnregisterWwanEvent(v11);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 26) + 16LL) + 16LL))(*((_QWORD *)this + 26) + 16LL);
    *((_QWORD *)this + 26) = 0;
  }
  if ( *((_QWORD *)this + 22) )
  {
    for ( i = (__int64 *)*((_QWORD *)this + 21); ; i[2] = 0 )
    {
      i = (__int64 *)*i;
      if ( i == *((__int64 **)this + 21) )
        break;
      ReleaseObj((struct IUnknown *)i[2]);
    }
  }
  std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(
    v11,
    *((_QWORD *)this + 21));
  **((_QWORD **)this + 21) = *((_QWORD *)this + 21);
  *(_QWORD *)(*((_QWORD *)this + 21) + 8LL) = *((_QWORD *)this + 21);
  *((_QWORD *)this + 22) = 0;
  v13 = (_QWORD *)((char *)this + 216);
  ClearSignalStrengthDataList((char *)this + 216);
  v14 = (_QWORD *)((char *)this + 232);
  ClearSignalStrengthDataList((char *)this + 232);
  v15 = *((_QWORD *)this + 45);
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    *((_QWORD *)this + 45) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
  ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>((char *)this + 352);
  CMessageWindow::~CMessageWindow((CSNOCplCore *)((char *)this + 256));
  std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(v16, *v14);
  std::_Deallocate<16>(*v14, 24);
  std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(v17, *v13);
  std::_Deallocate<16>(*v13, 24);
  CWlanHelper::~CWlanHelper((CSNOCplCore *)((char *)this + 184));
  std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(
    v18,
    *((_QWORD *)this + 21));
  std::_Deallocate<16>(*((_QWORD *)this + 21), 24);
  CProfileMgr::~CProfileMgr(this);
}

```

## disassembly

```asm
0x180008248  push    rbx
0x18000824a  push    rbp
0x18000824b  push    rsi
0x18000824c  push    rdi
0x18000824d  push    r14
0x18000824f  sub     rsp, 20h
0x180008253  mov     rdi, rcx
0x180008256  lea     rax, ??_7CSNOCplCore@@6BINotifyNetworkEventsPrivate@@@; const CSNOCplCore::`vftable'{for `INotifyNetworkEventsPrivate'}
0x18000825d  mov     [rcx], rax
0x180008260  lea     rax, ??_7CSNOCplCore@@6BINotifyNetworkSignatureEventsPrivate@@@; const CSNOCplCore::`vftable'{for `INotifyNetworkSignatureEventsPrivate'}
0x180008267  mov     [rcx+8], rax
0x18000826b  lea     rax, ??_7CSNOCplCore@@6BINetConnectionNotifySink@@@; const CSNOCplCore::`vftable'{for `INetConnectionNotifySink'}
0x180008272  mov     [rcx+10h], rax
0x180008276  lea     rax, ??_7CSNOCplCore@@6B@; const CSNOCplCore::`vftable'
0x18000827d  mov     [rcx+68h], rax
0x180008281  mov     rcx, [rcx+98h]
0x180008288  xor     r14d, r14d
0x18000828b  test    rcx, rcx
0x18000828e  jz      short loc_1800082A6
0x180008290  call    ?ClearProfileDataMap@@YAXPEAV?$map@U_GUID@@PEAVCProfileData@@VCKey_Less@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@@Z; ClearProfileDataMap(std::map<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>> *)
0x180008295  mov     rcx, [rdi+98h]; void *
0x18000829c  test    rcx, rcx
0x18000829f  jz      short loc_1800082A6
0x1800082a1  call    ??_G?$map@U_GUID@@PEAVCProfileData@@VCKey_Less@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@QEAAPEAXI@Z; std::map<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>>::`scalar deleting destructor'(uint)
0x1800082a6  lea     rcx, [rdi+70h]; lpCriticalSection
0x1800082aa  call    cs:__imp_DeleteCriticalSection
0x1800082b0  mov     rcx, [rdi+158h]
0x1800082b7  test    rcx, rcx
0x1800082ba  jz      short loc_1800082C8
0x1800082bc  mov     rax, [rcx]
0x1800082bf  mov     rax, [rax+10h]
0x1800082c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082c8  mov     rcx, [rdi+108h]; this
0x1800082cf  mov     ebx, 1
0x1800082d4  test    rcx, rcx
0x1800082d7  jz      short loc_1800082F7
0x1800082d9  call    ?Stop@CServiceMonitor@@QEAAJXZ; CServiceMonitor::Stop(void)
0x1800082de  mov     rcx, [rdi+108h]
0x1800082e5  test    rcx, rcx
0x1800082e8  jz      short loc_1800082F7
0x1800082ea  mov     rax, [rcx]
0x1800082ed  mov     edx, ebx
0x1800082ef  mov     rax, [rax]
0x1800082f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082f7  mov     rcx, [rdi+110h]; this
0x1800082fe  test    rcx, rcx
0x180008301  jz      short loc_180008321
0x180008303  call    ?Stop@CServiceMonitor@@QEAAJXZ; CServiceMonitor::Stop(void)
0x180008308  mov     rcx, [rdi+110h]
0x18000830f  test    rcx, rcx
0x180008312  jz      short loc_180008321
0x180008314  mov     rax, [rcx]
0x180008317  mov     edx, ebx
0x180008319  mov     rax, [rax]
0x18000831c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008321  mov     rcx, [rdi+118h]; this
0x180008328  test    rcx, rcx
0x18000832b  jz      short loc_18000834B
0x18000832d  call    ?Stop@CServiceMonitor@@QEAAJXZ; CServiceMonitor::Stop(void)
0x180008332  mov     rcx, [rdi+118h]
0x180008339  test    rcx, rcx
0x18000833c  jz      short loc_18000834B
0x18000833e  mov     rax, [rcx]
0x180008341  mov     edx, ebx
0x180008343  mov     rax, [rax]
0x180008346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000834b  lea     rbp, [rdi+0B8h]
0x180008352  mov     rcx, rbp; pCallbackContext
0x180008355  call    ?UnregisterWLANEvent@CWlanHelper@@QEAAJXZ; CWlanHelper::UnregisterWLANEvent(void)
0x18000835a  mov     rcx, [rdi+0D0h]; this
0x180008361  test    rcx, rcx
0x180008364  jz      short loc_180008389
0x180008366  call    ?UnregisterWwanEvent@CWwanHelper@@QEAAJXZ; CWwanHelper::UnregisterWwanEvent(void)
0x18000836b  mov     rcx, [rdi+0D0h]
0x180008372  add     rcx, 10h
0x180008376  mov     rax, [rcx]
0x180008379  mov     rax, [rax+10h]
0x18000837d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008382  mov     [rdi+0D0h], r14
0x180008389  cmp     [rdi+0B0h], r14
0x180008390  jz      short loc_1800083B4
0x180008392  mov     rbx, [rdi+0A8h]
0x180008399  mov     rbx, [rbx]
0x18000839c  cmp     rbx, [rdi+0A8h]
0x1800083a3  jz      short loc_1800083B4
0x1800083a5  mov     rcx, [rbx+10h]; struct IUnknown *
0x1800083a9  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x1800083ae  mov     [rbx+10h], r14
0x1800083b2  jmp     short loc_180008399
0x1800083b4  mov     rdx, [rdi+0A8h]
0x1800083bb  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@std@@@?$_List_node@PEAUIPicture@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(std::allocator<std::_List_node<IPicture *,void *>> &,std::_List_node<IPicture *,void *> *)
0x1800083c0  mov     rax, [rdi+0A8h]
0x1800083c7  mov     [rax], rax
0x1800083ca  mov     rax, [rdi+0A8h]
0x1800083d1  mov     [rax+8], rax
0x1800083d5  mov     [rdi+0B0h], r14
0x1800083dc  lea     rbx, [rdi+0D8h]
0x1800083e3  mov     rcx, rbx
0x1800083e6  call    ?ClearSignalStrengthDataList@@YAXPEAV?$list@PEAUtagSIGNALSTRENGTHDATA@@V?$allocator@PEAUtagSIGNALSTRENGTHDATA@@@std@@@std@@@Z; ClearSignalStrengthDataList(std::list<tagSIGNALSTRENGTHDATA *> *)
0x1800083eb  lea     rsi, [rdi+0E8h]
0x1800083f2  mov     rcx, rsi
0x1800083f5  call    ?ClearSignalStrengthDataList@@YAXPEAV?$list@PEAUtagSIGNALSTRENGTHDATA@@V?$allocator@PEAUtagSIGNALSTRENGTHDATA@@@std@@@std@@@Z; ClearSignalStrengthDataList(std::list<tagSIGNALSTRENGTHDATA *> *)
0x1800083fa  mov     rcx, [rdi+168h]
0x180008401  test    rcx, rcx
0x180008404  jz      short loc_180008419
0x180008406  mov     rax, [rcx]
0x180008409  mov     rax, [rax+10h]
0x18000840d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008412  mov     [rdi+168h], r14
0x180008419  lea     rax, WPP_GLOBAL_Control
0x180008420  mov     rcx, cs:WPP_GLOBAL_Control
0x180008427  cmp     rcx, rax
0x18000842a  jz      short loc_180008447
0x18000842c  test    byte ptr [rcx+1Ch], 8
0x180008430  jz      short loc_180008447
0x180008432  mov     edx, 0Ch
0x180008437  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000843e  mov     rcx, [rcx+10h]
0x180008442  call    WPP_SF_
0x180008447  lea     rcx, [rdi+160h]
0x18000844e  call    ??1?$CComPtrBase@UIShellFolder2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(void)
0x180008453  lea     rcx, [rdi+100h]; this
0x18000845a  call    ??1CMessageWindow@@QEAA@XZ; CMessageWindow::~CMessageWindow(void)
0x18000845f  mov     rdx, [rsi]
0x180008462  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@std@@@?$_List_node@PEAUIPicture@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(std::allocator<std::_List_node<IPicture *,void *>> &,std::_List_node<IPicture *,void *> *)
0x180008467  mov     r14d, 18h
0x18000846d  mov     edx, r14d
0x180008470  mov     rcx, [rsi]
0x180008473  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180008478  mov     rdx, [rbx]
0x18000847b  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@std@@@?$_List_node@PEAUIPicture@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(std::allocator<std::_List_node<IPicture *,void *>> &,std::_List_node<IPicture *,void *> *)
0x180008480  mov     edx, r14d
0x180008483  mov     rcx, [rbx]
0x180008486  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000848b  mov     rcx, rbp; this
0x18000848e  call    ??1CWlanHelper@@QEAA@XZ; CWlanHelper::~CWlanHelper(void)
0x180008493  mov     rdx, [rdi+0A8h]
0x18000849a  call    ??$_Free_non_head@V?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@std@@@?$_List_node@PEAUIPicture@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@PEAUIPicture@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<IPicture *,void *>::_Free_non_head<std::allocator<std::_List_node<IPicture *,void *>>>(std::allocator<std::_List_node<IPicture *,void *>> &,std::_List_node<IPicture *,void *> *)
0x18000849f  mov     edx, r14d
0x1800084a2  mov     rcx, [rdi+0A8h]
0x1800084a9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800084ae  mov     rcx, rdi; this
0x1800084b1  add     rsp, 20h
0x1800084b5  pop     r14
0x1800084b7  pop     rdi
0x1800084b8  pop     rsi
0x1800084b9  pop     rbp
0x1800084ba  pop     rbx
0x1800084bb  jmp     ??1CProfileMgr@@QEAA@XZ; CProfileMgr::~CProfileMgr(void)
```
