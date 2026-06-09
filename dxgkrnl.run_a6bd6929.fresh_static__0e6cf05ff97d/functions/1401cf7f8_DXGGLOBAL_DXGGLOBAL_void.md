# DXGGLOBAL::~DXGGLOBAL(void)

- ea: `0x1401cf7f8`
- end: `0x1401cff69`
- name: `??1DXGGLOBAL@@EEAA@XZ`
- size: `1905`
- prototype: `void __fastcall(DXGGLOBAL *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x1400755b0`

## callees

- `0x14000d990`
- `0x14001b9c0`
- `0x140032a40`
- `0x140052670`
- `0x14005f1e4`
- `0x1400658a0`
- `0x1400733dc`
- `0x1400754c8`
- `0x14007557c`
- `0x140075610`
- `0x1401cf7f8`
- `0x1401dac14`
- `0x14022521c`
- `0x14023e998`
- `0x14024693c`
- `0x140260864`
- `0x140260b80`
- `0x1403a4b30`
- `0x1403c03d8`
- `0x1403c7894`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1401cfb83`
- `ntoskrnl!KeCancelTimer` at `0x1401cfba6`
- `ntoskrnl!KeCancelTimer` at `0x1401cfb83`
- `ntoskrnl!KeCancelTimer` at `0x1401cfba6`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401cf8cb`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401cf8cb`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1401cfb93`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1401cfbb6`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1401cfb93`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1401cfbb6`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1401cfb4d`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1401cfb4d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401cf896`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401cf94d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401cf970`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401cfc07`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401cf896`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401cf94d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401cf970`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401cfc07`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1401cfb0f`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1401cfb2e`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1401cfb0f`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1401cfb2e`
- `ntoskrnl!RtlNumberOfClearBits` at `0x1401cf9d4`
- `ntoskrnl!RtlNumberOfClearBits` at `0x1401cfa4e`
- `ntoskrnl!RtlNumberOfClearBits` at `0x1401cf9d4`
- `ntoskrnl!RtlNumberOfClearBits` at `0x1401cfa4e`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401cfaad`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401cfac1`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401cfaad`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401cfac1`
- `ntoskrnl!ExUnregisterExtension` at `0x1401cf825`
- `ntoskrnl!ExUnregisterExtension` at `0x1401cf825`
- `watchdog!WdLogSingleEntry0` at `0x1401cf9f1`
- `watchdog!WdLogSingleEntry0` at `0x1401cfa61`
- `watchdog!WdLogSingleEntry0` at `0x1401cfc24`
- `watchdog!WdLogSingleEntry0` at `0x1401cfc77`
- `watchdog!WdLogSingleEntry0` at `0x1401cfcca`
- `watchdog!WdLogSingleEntry0` at `0x1401cfd1e`
- `watchdog!WdLogSingleEntry0` at `0x1401cfd71`
- `watchdog!WdLogSingleEntry0` at `0x1401cfdc3`
- `watchdog!WdLogSingleEntry0` at `0x1401cf9f1`
- `watchdog!WdLogSingleEntry0` at `0x1401cfa61`
- `watchdog!WdLogSingleEntry0` at `0x1401cfc24`
- `watchdog!WdLogSingleEntry0` at `0x1401cfc77`
- `watchdog!WdLogSingleEntry0` at `0x1401cfcca`
- `watchdog!WdLogSingleEntry0` at `0x1401cfd1e`
- `watchdog!WdLogSingleEntry0` at `0x1401cfd71`
- `watchdog!WdLogSingleEntry0` at `0x1401cfdc3`

## pseudocode

```c
void __fastcall DXGGLOBAL::~DXGGLOBAL(DXGGLOBAL *this, unsigned int a2)
{
  __int64 i; // rbx
  struct DXGMMS_EXPORT * near *v4; // rsi
  void *v5; // rbx
  struct _ERESOURCE *v6; // rcx
  DXGDIAGNOSTICS *v7; // rcx
  DXGDIAGNOSTICS *v8; // rcx
  void *v9; // rbx
  struct DXGPROCESS *v10; // rcx
  void *v11; // rcx
  ULONG v12; // ebx
  unsigned int v13; // ebx
  void *v14; // rbx
  void *v15; // rcx
  unsigned int v16; // edx
  DXG_GUEST_GLOBAL_VMBUS *v17; // rcx
  ReferenceCounted *v18; // rcx

  *(_QWORD *)this = &DXGGLOBAL::`vftable';
  if ( DxgExtensionRegistration )
  {
    ExUnregisterExtension();
    DxgExtensionRegistration = 0;
    DxgExtensionInfo = 0;
    DxgHostTable = 0;
    xmmword_1401623D8 = 0;
  }
  for ( i = 0; i != 2; ++i )
  {
    v4 = (&DXGGLOBAL::m_pDxgmmsExport)[i];
    if ( v4 )
    {
      DXGMMS_EXPORT::Release((DXGMMS_EXPORT *)(&DXGGLOBAL::m_pDxgmmsExport)[i]);
      DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v4);
    }
    (&DXGGLOBAL::m_pDxgmmsExport)[i] = 0;
  }
  if ( *((_BYTE *)this + 1363) )
    ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)this + 160));
  v5 = (void *)*((_QWORD *)this + 4);
  if ( v5 )
  {
    HMGRTABLE::~HMGRTABLE(*((HMGRTABLE **)this + 4));
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v5);
  }
  v6 = (struct _ERESOURCE *)*((_QWORD *)this + 76);
  *((_QWORD *)this + 4) = 0;
  if ( v6 )
  {
    ExDeleteResourceLite(v6);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(*((void **)this + 76));
    *((_QWORD *)this + 76) = 0;
  }
  v7 = (DXGDIAGNOSTICS *)*((_QWORD *)this + 121);
  if ( v7 )
  {
    DXGDIAGNOSTICS::`scalar deleting destructor'(v7, a2);
    *((_QWORD *)this + 121) = 0;
  }
  v8 = (DXGDIAGNOSTICS *)*((_QWORD *)this + 122);
  if ( v8 )
  {
    DXGDIAGNOSTICS::`scalar deleting destructor'(v8, a2);
    *((_QWORD *)this + 122) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 123);
  if ( v9 )
  {
    DXGSESSIONMGR::~DXGSESSIONMGR(*((DXGSESSIONMGR **)this + 123));
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v9);
    *((_QWORD *)this + 123) = 0;
  }
  if ( *((_BYTE *)this + 1361) )
  {
    ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)this + 12);
    *((_BYTE *)this + 1361) = 0;
  }
  if ( *((_BYTE *)this + 1362) )
  {
    ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)this + 13);
    *((_BYTE *)this + 1362) = 0;
  }
  v10 = (struct DXGPROCESS *)*((_QWORD *)this + 173);
  if ( v10 )
  {
    DXGPROCESS::DestroyDxgProcess(v10);
    *((_QWORD *)this + 173) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 38121);
  if ( v11 )
  {
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v11);
    *((_QWORD *)this + 38121) = 0;
  }
  if ( *((_QWORD *)this + 113) )
  {
    v12 = RtlNumberOfClearBits((PRTL_BITMAP)((char *)this + 872));
    if ( v12 != DXGGLOBAL::GetMaximumGlobalAdapterCount(this) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 1698;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"RtlNumberOfClearBits(&m_GlobalAdapterOrdinalMap) == GetMaximumGlobalAdapterCount()",
        1698,
        0,
        0,
        0,
        0);
    }
    v13 = 1024 - DXGGLOBAL::GetMaximumGlobalAdapterCount(this);
    if ( RtlNumberOfClearBits((PRTL_BITMAP)((char *)this + 888)) != v13 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 1699;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"RtlNumberOfClearBits(&m_SessionizedAdapterOrdinalMap) == ((MAX_ADAPTERS_CEILING) - GetMaximumGloba"
                       "lAdapterCount())",
        1699,
        0,
        0,
        0,
        0);
    }
    RtlInitializeBitMap((PRTL_BITMAP)((char *)this + 872), 0, 0);
    RtlInitializeBitMap((PRTL_BITMAP)((char *)this + 888), 0, 0);
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(*((void **)this + 113));
    *((_QWORD *)this + 113) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 185);
  if ( v14 )
  {
    QDC_CACHE::~QDC_CACHE(*((QDC_CACHE **)this + 185));
    DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v14);
    *((_QWORD *)this + 185) = 0;
  }
  if ( *((_QWORD *)this + 238) )
  {
    ExUnsubscribeWnfStateChange();
    *((_QWORD *)this + 238) = 0;
  }
  if ( *((_QWORD *)this + 261) )
  {
    ExUnsubscribeWnfStateChange();
    *((_QWORD *)this + 261) = 0;
  }
  v15 = (void *)*((_QWORD *)this + 262);
  if ( v15 )
  {
    PoUnregisterPowerSettingCallback(v15);
    *((_QWORD *)this + 262) = 0;
  }
  if ( *((_DWORD *)this + 527) )
  {
    McGenEventUnregister_EtwUnregister(&SLEEPSTUDY_ETW_PROVIDER_Context);
    *((_DWORD *)this + 527) = 0;
  }
  if ( !KeCancelTimer((PKTIMER)this + 30) )
    KeFlushQueuedDpcs();
  if ( !KeCancelTimer((PKTIMER)this + 4778) )
    KeFlushQueuedDpcs();
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(*((void **)this + 38111));
  v17 = (DXG_GUEST_GLOBAL_VMBUS *)*((_QWORD *)this + 212);
  if ( v17 )
    DXG_GUEST_GLOBAL_VMBUS::`scalar deleting destructor'(v17, v16);
  v18 = (ReferenceCounted *)*((_QWORD *)this + 38151);
  if ( v18 )
  {
    ReferenceCounted::Release(v18);
    *((_QWORD *)this + 38151) = 0;
  }
  if ( *((_BYTE *)this + 305440) )
    ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)((char *)this + 305456));
  if ( *((_DWORD *)this + 91) != *((_DWORD *)this + 90) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1781;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_ShareHandleTable.IsEmpty()", 1781, 0, 0, 0, 0);
  }
  if ( *((DXGGLOBAL **)this + 74) != (DXGGLOBAL *)((char *)this + 592) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1782;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_SyncObjectList.IsEmpty()", 1782, 0, 0, 0, 0);
  }
  if ( *((DXGGLOBAL **)this + 83) != (DXGGLOBAL *)((char *)this + 664) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1783;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_KeyedMutexList.IsEmpty()", 1783, 0, 0, 0, 0);
  }
  if ( *((DXGGLOBAL **)this + 101) != (DXGGLOBAL *)((char *)this + 808) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1784;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_AdapterList.IsEmpty()", 1784, 0, 0, 0, 0);
  }
  if ( *((DXGGLOBAL **)this + 226) != (DXGGLOBAL *)((char *)this + 1808) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1785;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_SharedPowerList.IsEmpty()", 1785, 0, 0, 0, 0);
  }
  if ( *((_QWORD *)this + 187) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1786;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_UefiFrameData == NULL", 1786, 0, 0, 0, 0);
  }
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 305744));
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 305552));
  CSERIALIZEDWORKQUEUE::~CSERIALIZEDWORKQUEUE((DXGGLOBAL *)((char *)this + 305368));
  REMOTEMONITORMAPPING::Clear((DXGGLOBAL *)((char *)this + 305272), 0);
  DisplayDiagnostics::~DisplayDiagnostics((DXGGLOBAL *)((char *)this + 305024));
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 304976));
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 304904));
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 304824));
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 2112));
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 1824));
  DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>::~DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>((char *)this + 1808);
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 1616));
  DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>::~DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>((char *)this + 1584);
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 1536));
  DXGADAPTERSOURCEHASH::~DXGADAPTERSOURCEHASH((DXGGLOBAL *)((char *)this + 1400));
  REMOTE_VSYNC::~REMOTE_VSYNC((DXGGLOBAL *)((char *)this + 1088));
  REMOTE_VSYNC::~REMOTE_VSYNC((DXGGLOBAL *)((char *)this + 1032));
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 824));
  DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>::~DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>((char *)this + 808);
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 760));
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 680));
  DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>::~DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>((char *)this + 664);
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 616));
  DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>::~DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>((char *)this + 592);
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 544));
  DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>::~DXGNODELIST<ADAPTER_DISPLAY,DXGPROTECTEDSESSION>((char *)this + 424);
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 376));
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(*((void **)this + 43));
  DXGFASTMUTEX::~DXGFASTMUTEX((DXGGLOBAL *)((char *)this + 296));
}

```

## disassembly

```asm
0x1401cf7f8  push    rbx
0x1401cf7fa  push    rbp
0x1401cf7fb  push    rsi
0x1401cf7fc  push    rdi
0x1401cf7fd  push    r12
0x1401cf7ff  push    r13
0x1401cf801  push    r14
0x1401cf803  push    r15
0x1401cf805  sub     rsp, 58h
0x1401cf809  lea     rax, ??_7DXGGLOBAL@@6B@; const DXGGLOBAL::`vftable'
0x1401cf810  mov     rdi, rcx
0x1401cf813  mov     [rcx], rax
0x1401cf816  xor     r15d, r15d
0x1401cf819  mov     rcx, cs:?DxgExtensionRegistration@@3PEAU_EX_EXTENSION@@EA; _EX_EXTENSION * DxgExtensionRegistration
0x1401cf820  test    rcx, rcx
0x1401cf823  jz      short loc_1401CF850
0x1401cf825  call    cs:__imp_ExUnregisterExtension
0x1401cf82c  nop     dword ptr [rax+rax+00h]
0x1401cf831  xorps   xmm0, xmm0
0x1401cf834  mov     cs:?DxgExtensionRegistration@@3PEAU_EX_EXTENSION@@EA, r15; _EX_EXTENSION * DxgExtensionRegistration
0x1401cf83b  movups  cs:?DxgExtensionInfo@@3U_EX_EXTENSION_REGISTRATION_2@@A, xmm0; _EX_EXTENSION_REGISTRATION_2 DxgExtensionInfo
0x1401cf842  mov     cs:?DxgHostTable@@3PEAU_PS_DXG_HOST_INTERFACE@@EA, r15; _PS_DXG_HOST_INTERFACE * DxgHostTable
0x1401cf849  movups  cs:xmmword_1401623D8, xmm0
0x1401cf850  mov     rbx, r15
0x1401cf853  mov     r12d, 1
0x1401cf859  lea     r14, ?m_pDxgmmsExport@DXGGLOBAL@@0PAPEAVDXGMMS_EXPORT@@A; DXGMMS_EXPORT * near * DXGGLOBAL::m_pDxgmmsExport
0x1401cf860  mov     rsi, [r14+rbx*8]
0x1401cf864  test    rsi, rsi
0x1401cf867  jz      short loc_1401CF879
0x1401cf869  mov     rcx, rsi; this
0x1401cf86c  call    ?Release@DXGMMS_EXPORT@@QEAAJXZ; DXGMMS_EXPORT::Release(void)
0x1401cf871  mov     rcx, rsi; void *
0x1401cf874  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401cf879  mov     [r14+rbx*8], r15
0x1401cf87d  add     rbx, r12
0x1401cf880  cmp     rbx, 2
0x1401cf884  jnz     short loc_1401CF859
0x1401cf886  cmp     [rdi+553h], r15b
0x1401cf88d  jz      short loc_1401CF8A2
0x1401cf88f  lea     rcx, [rdi+0A0h]; Lookaside
0x1401cf896  call    cs:__imp_ExDeleteLookasideListEx
0x1401cf89d  nop     dword ptr [rax+rax+00h]
0x1401cf8a2  mov     rbx, [rdi+20h]
0x1401cf8a6  test    rbx, rbx
0x1401cf8a9  jz      short loc_1401CF8BB
0x1401cf8ab  mov     rcx, rbx; this
0x1401cf8ae  call    ??1HMGRTABLE@@QEAA@XZ; HMGRTABLE::~HMGRTABLE(void)
0x1401cf8b3  mov     rcx, rbx; void *
0x1401cf8b6  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401cf8bb  mov     rcx, [rdi+260h]; Resource
0x1401cf8c2  mov     [rdi+20h], r15
0x1401cf8c6  test    rcx, rcx
0x1401cf8c9  jz      short loc_1401CF8EA
0x1401cf8cb  call    cs:__imp_ExDeleteResourceLite
0x1401cf8d2  nop     dword ptr [rax+rax+00h]
0x1401cf8d7  mov     rcx, [rdi+260h]; void *
0x1401cf8de  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401cf8e3  mov     [rdi+260h], r15
0x1401cf8ea  mov     rcx, [rdi+3C8h]; this
0x1401cf8f1  test    rcx, rcx
0x1401cf8f4  jz      short loc_1401CF902
0x1401cf8f6  call    ??_GDXGDIAGNOSTICS@@QEAAPEAXI@Z; DXGDIAGNOSTICS::`scalar deleting destructor'(uint)
0x1401cf8fb  mov     [rdi+3C8h], r15
0x1401cf902  mov     rcx, [rdi+3D0h]; this
0x1401cf909  test    rcx, rcx
0x1401cf90c  jz      short loc_1401CF91A
0x1401cf90e  call    ??_GDXGDIAGNOSTICS@@QEAAPEAXI@Z; DXGDIAGNOSTICS::`scalar deleting destructor'(uint)
0x1401cf913  mov     [rdi+3D0h], r15
0x1401cf91a  mov     rbx, [rdi+3D8h]
0x1401cf921  test    rbx, rbx
0x1401cf924  jz      short loc_1401CF93D
0x1401cf926  mov     rcx, rbx; this
0x1401cf929  call    ??1DXGSESSIONMGR@@QEAA@XZ; DXGSESSIONMGR::~DXGSESSIONMGR(void)
0x1401cf92e  mov     rcx, rbx; void *
0x1401cf931  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401cf936  mov     [rdi+3D8h], r15
0x1401cf93d  cmp     [rdi+551h], r15b
0x1401cf944  jz      short loc_1401CF960
0x1401cf946  lea     rcx, [rdi+480h]; Lookaside
0x1401cf94d  call    cs:__imp_ExDeleteLookasideListEx
0x1401cf954  nop     dword ptr [rax+rax+00h]
0x1401cf959  mov     [rdi+551h], r15b
0x1401cf960  cmp     [rdi+552h], r15b
0x1401cf967  jz      short loc_1401CF983
0x1401cf969  lea     rcx, [rdi+4E0h]; Lookaside
0x1401cf970  call    cs:__imp_ExDeleteLookasideListEx
0x1401cf977  nop     dword ptr [rax+rax+00h]
0x1401cf97c  mov     [rdi+552h], r15b
0x1401cf983  mov     rcx, [rdi+568h]; this
0x1401cf98a  test    rcx, rcx
0x1401cf98d  jz      short loc_1401CF99B
0x1401cf98f  call    ?DestroyDxgProcess@DXGPROCESS@@SAXPEAV1@@Z; DXGPROCESS::DestroyDxgProcess(DXGPROCESS *)
0x1401cf994  mov     [rdi+568h], r15
0x1401cf99b  mov     rcx, [rdi+4A748h]; void *
0x1401cf9a2  test    rcx, rcx
0x1401cf9a5  jz      short loc_1401CF9B3
0x1401cf9a7  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401cf9ac  mov     [rdi+4A748h], r15
0x1401cf9b3  or      r13d, 0FFFFFFFFh
0x1401cf9b7  mov     r14d, 40002h
0x1401cf9bd  cmp     [rdi+388h], r15
0x1401cf9c4  jz      loc_1401CFAE0
0x1401cf9ca  lea     rsi, [rdi+368h]
0x1401cf9d1  mov     rcx, rsi; BitMapHeader
0x1401cf9d4  call    cs:__imp_RtlNumberOfClearBits
0x1401cf9db  nop     dword ptr [rax+rax+00h]
0x1401cf9e0  mov     rcx, rdi; this
0x1401cf9e3  mov     ebx, eax
0x1401cf9e5  call    ?GetMaximumGlobalAdapterCount@DXGGLOBAL@@QEBAKXZ; DXGGLOBAL::GetMaximumGlobalAdapterCount(void)
0x1401cf9ea  cmp     ebx, eax
0x1401cf9ec  jz      short loc_1401CFA35
0x1401cf9ee  mov     ecx, r12d
0x1401cf9f1  call    cs:__imp_WdLogSingleEntry0
0x1401cf9f8  nop     dword ptr [rax+rax+00h]
0x1401cf9fd  mov     [rsp+98h+var_58], r15
0x1401cfa02  lea     r9, aRtlnumberofcle_0; "RtlNumberOfClearBits(&m_GlobalAdapterOr"...
0x1401cfa09  mov     [rsp+98h+var_60], r15
0x1401cfa0e  mov     eax, 6A2h
0x1401cfa13  mov     [rsp+98h+var_68], r15
0x1401cfa18  mov     r8d, r13d
0x1401cfa1b  mov     [rsp+98h+var_70], r15
0x1401cfa20  mov     edx, r14d
0x1401cfa23  xor     ecx, ecx
0x1401cfa25  mov     [rsp+98h+var_78], rax
0x1401cfa2a  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cfa30  call    DxgkLogInternalTriageEvent
0x1401cfa35  mov     rcx, rdi; this
0x1401cfa38  lea     rbp, [rdi+378h]
0x1401cfa3f  call    ?GetMaximumGlobalAdapterCount@DXGGLOBAL@@QEBAKXZ; DXGGLOBAL::GetMaximumGlobalAdapterCount(void)
0x1401cfa44  mov     ebx, 400h
0x1401cfa49  mov     rcx, rbp; BitMapHeader
0x1401cfa4c  sub     ebx, eax
0x1401cfa4e  call    cs:__imp_RtlNumberOfClearBits
0x1401cfa55  nop     dword ptr [rax+rax+00h]
0x1401cfa5a  cmp     eax, ebx
0x1401cfa5c  jz      short loc_1401CFAA5
0x1401cfa5e  mov     ecx, r12d
0x1401cfa61  call    cs:__imp_WdLogSingleEntry0
0x1401cfa68  nop     dword ptr [rax+rax+00h]
0x1401cfa6d  mov     [rsp+98h+var_58], r15
0x1401cfa72  lea     r9, aRtlnumberofcle_1; "RtlNumberOfClearBits(&m_SessionizedAdap"...
0x1401cfa79  mov     [rsp+98h+var_60], r15
0x1401cfa7e  mov     eax, 6A3h
0x1401cfa83  mov     [rsp+98h+var_68], r15
0x1401cfa88  mov     r8d, r13d
0x1401cfa8b  mov     [rsp+98h+var_70], r15
0x1401cfa90  mov     edx, r14d
0x1401cfa93  xor     ecx, ecx
0x1401cfa95  mov     [rsp+98h+var_78], rax
0x1401cfa9a  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cfaa0  call    DxgkLogInternalTriageEvent
0x1401cfaa5  xor     r8d, r8d; SizeOfBitMap
0x1401cfaa8  xor     edx, edx; BitMapBuffer
0x1401cfaaa  mov     rcx, rsi; BitMapHeader
0x1401cfaad  call    cs:__imp_RtlInitializeBitMap
0x1401cfab4  nop     dword ptr [rax+rax+00h]
0x1401cfab9  xor     r8d, r8d; SizeOfBitMap
0x1401cfabc  xor     edx, edx; BitMapBuffer
0x1401cfabe  mov     rcx, rbp; BitMapHeader
0x1401cfac1  call    cs:__imp_RtlInitializeBitMap
0x1401cfac8  nop     dword ptr [rax+rax+00h]
0x1401cfacd  mov     rcx, [rdi+388h]; void *
0x1401cfad4  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401cfad9  mov     [rdi+388h], r15
0x1401cfae0  mov     rbx, [rdi+5C8h]
0x1401cfae7  test    rbx, rbx
0x1401cfaea  jz      short loc_1401CFB03
0x1401cfaec  mov     rcx, rbx; this
0x1401cfaef  call    ??1QDC_CACHE@@QEAA@XZ; QDC_CACHE::~QDC_CACHE(void)
0x1401cfaf4  mov     rcx, rbx; void *
0x1401cfaf7  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401cfafc  mov     [rdi+5C8h], r15
0x1401cfb03  mov     rcx, [rdi+770h]
0x1401cfb0a  test    rcx, rcx
0x1401cfb0d  jz      short loc_1401CFB22
0x1401cfb0f  call    cs:__imp_ExUnsubscribeWnfStateChange
0x1401cfb16  nop     dword ptr [rax+rax+00h]
0x1401cfb1b  mov     [rdi+770h], r15
0x1401cfb22  mov     rcx, [rdi+828h]
0x1401cfb29  test    rcx, rcx
0x1401cfb2c  jz      short loc_1401CFB41
0x1401cfb2e  call    cs:__imp_ExUnsubscribeWnfStateChange
0x1401cfb35  nop     dword ptr [rax+rax+00h]
0x1401cfb3a  mov     [rdi+828h], r15
0x1401cfb41  mov     rcx, [rdi+830h]; Handle
0x1401cfb48  test    rcx, rcx
0x1401cfb4b  jz      short loc_1401CFB60
0x1401cfb4d  call    cs:__imp_PoUnregisterPowerSettingCallback
0x1401cfb54  nop     dword ptr [rax+rax+00h]
0x1401cfb59  mov     [rdi+830h], r15
0x1401cfb60  cmp     [rdi+83Ch], r15d
0x1401cfb67  jz      short loc_1401CFB7C
0x1401cfb69  lea     rcx, SLEEPSTUDY_ETW_PROVIDER_Context
0x1401cfb70  call    McGenEventUnregister_EtwUnregister
0x1401cfb75  mov     [rdi+83Ch], r15d
0x1401cfb7c  lea     rcx, [rdi+780h]; PKTIMER
0x1401cfb83  call    cs:__imp_KeCancelTimer
0x1401cfb8a  nop     dword ptr [rax+rax+00h]
0x1401cfb8f  test    al, al
0x1401cfb91  jnz     short loc_1401CFB9F
0x1401cfb93  call    cs:__imp_KeFlushQueuedDpcs
0x1401cfb9a  nop     dword ptr [rax+rax+00h]
0x1401cfb9f  lea     rcx, [rdi+4AA80h]; PKTIMER
0x1401cfba6  call    cs:__imp_KeCancelTimer
0x1401cfbad  nop     dword ptr [rax+rax+00h]
0x1401cfbb2  test    al, al
0x1401cfbb4  jnz     short loc_1401CFBC2
0x1401cfbb6  call    cs:__imp_KeFlushQueuedDpcs
0x1401cfbbd  nop     dword ptr [rax+rax+00h]
0x1401cfbc2  mov     rcx, [rdi+4A6F8h]; void *
0x1401cfbc9  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401cfbce  mov     rcx, [rdi+6A0h]; this
0x1401cfbd5  test    rcx, rcx
0x1401cfbd8  jz      short loc_1401CFBDF
0x1401cfbda  call    ??_GDXG_GUEST_GLOBAL_VMBUS@@QEAAPEAXI@Z; DXG_GUEST_GLOBAL_VMBUS::`scalar deleting destructor'(uint)
0x1401cfbdf  mov     rcx, [rdi+4A838h]; this
0x1401cfbe6  test    rcx, rcx
0x1401cfbe9  jz      short loc_1401CFBF7
0x1401cfbeb  call    ?Release@ReferenceCounted@@QEBA_KXZ; ReferenceCounted::Release(void)
0x1401cfbf0  mov     [rdi+4A838h], r15
0x1401cfbf7  cmp     [rdi+4A920h], r15b
0x1401cfbfe  jz      short loc_1401CFC13
0x1401cfc00  lea     rcx, [rdi+4A930h]; Lookaside
0x1401cfc07  call    cs:__imp_ExDeleteLookasideListEx
0x1401cfc0e  nop     dword ptr [rax+rax+00h]
0x1401cfc13  mov     eax, [rdi+168h]
0x1401cfc19  cmp     [rdi+16Ch], eax
0x1401cfc1f  jz      short loc_1401CFC68
0x1401cfc21  mov     ecx, r12d
0x1401cfc24  call    cs:__imp_WdLogSingleEntry0
0x1401cfc2b  nop     dword ptr [rax+rax+00h]
0x1401cfc30  mov     [rsp+98h+var_58], r15
0x1401cfc35  lea     r9, aMSharehandleta; "m_ShareHandleTable.IsEmpty()"
0x1401cfc3c  mov     [rsp+98h+var_60], r15
0x1401cfc41  mov     eax, 6F5h
0x1401cfc46  mov     [rsp+98h+var_68], r15
0x1401cfc4b  mov     r8d, r13d
0x1401cfc4e  mov     [rsp+98h+var_70], r15
0x1401cfc53  mov     edx, r14d
0x1401cfc56  xor     ecx, ecx
0x1401cfc58  mov     [rsp+98h+var_78], rax
0x1401cfc5d  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cfc63  call    DxgkLogInternalTriageEvent
0x1401cfc68  lea     rbx, [rdi+250h]
0x1401cfc6f  cmp     [rbx], rbx
0x1401cfc72  jz      short loc_1401CFCBB
0x1401cfc74  mov     ecx, r12d
0x1401cfc77  call    cs:__imp_WdLogSingleEntry0
0x1401cfc7e  nop     dword ptr [rax+rax+00h]
0x1401cfc83  mov     [rsp+98h+var_58], r15
0x1401cfc88  lea     r9, aMSyncobjectlis; "m_SyncObjectList.IsEmpty()"
0x1401cfc8f  mov     [rsp+98h+var_60], r15
0x1401cfc94  mov     eax, 6F6h
0x1401cfc99  mov     [rsp+98h+var_68], r15
0x1401cfc9e  mov     r8d, r13d
0x1401cfca1  mov     [rsp+98h+var_70], r15
0x1401cfca6  mov     edx, r14d
0x1401cfca9  xor     ecx, ecx
0x1401cfcab  mov     [rsp+98h+var_78], rax
0x1401cfcb0  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cfcb6  call    DxgkLogInternalTriageEvent
0x1401cfcbb  lea     rsi, [rdi+298h]
0x1401cfcc2  cmp     [rsi], rsi
0x1401cfcc5  jz      short loc_1401CFD0E
0x1401cfcc7  mov     ecx, r12d
0x1401cfcca  call    cs:__imp_WdLogSingleEntry0
0x1401cfcd1  nop     dword ptr [rax+rax+00h]
0x1401cfcd6  mov     [rsp+98h+var_58], r15
0x1401cfcdb  lea     r9, aMKeyedmutexlis; "m_KeyedMutexList.IsEmpty()"
0x1401cfce2  mov     [rsp+98h+var_60], r15
0x1401cfce7  mov     eax, 6F7h
0x1401cfcec  mov     [rsp+98h+var_68], r15
0x1401cfcf1  mov     r8d, r13d
0x1401cfcf4  mov     [rsp+98h+var_70], r15
0x1401cfcf9  mov     edx, r14d
0x1401cfcfc  xor     ecx, ecx
0x1401cfcfe  mov     [rsp+98h+var_78], rax
0x1401cfd03  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cfd09  call    DxgkLogInternalTriageEvent
0x1401cfd0e  lea     rbp, [rdi+328h]
0x1401cfd15  cmp     [rbp+0], rbp
0x1401cfd19  jz      short loc_1401CFD62
0x1401cfd1b  mov     ecx, r12d
0x1401cfd1e  call    cs:__imp_WdLogSingleEntry0
0x1401cfd25  nop     dword ptr [rax+rax+00h]
0x1401cfd2a  mov     [rsp+98h+var_58], r15
0x1401cfd2f  lea     r9, aMAdapterlistIs; "m_AdapterList.IsEmpty()"
0x1401cfd36  mov     [rsp+98h+var_60], r15
0x1401cfd3b  mov     eax, 6F8h
0x1401cfd40  mov     [rsp+98h+var_68], r15
0x1401cfd45  mov     r8d, r13d
0x1401cfd48  mov     [rsp+98h+var_70], r15
0x1401cfd4d  mov     edx, r14d
0x1401cfd50  xor     ecx, ecx
0x1401cfd52  mov     [rsp+98h+var_78], rax
0x1401cfd57  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cfd5d  call    DxgkLogInternalTriageEvent
0x1401cfd62  lea     r14, [rdi+710h]
0x1401cfd69  cmp     [r14], r14
0x1401cfd6c  jz      short loc_1401CFDB7
  ... truncated ...
```
