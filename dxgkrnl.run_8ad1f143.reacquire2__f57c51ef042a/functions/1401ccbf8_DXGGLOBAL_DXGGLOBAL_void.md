# DXGGLOBAL::~DXGGLOBAL(void)

- ea: `0x1401ccbf8`
- end: `0x1401cd369`
- name: `??1DXGGLOBAL@@EEAA@XZ`
- size: `1905`
- prototype: `void __fastcall(DXGGLOBAL *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x140074f70`

## callees

- `0x14000d7d0`
- `0x14001b890`
- `0x140032870`
- `0x140052490`
- `0x14005ee30`
- `0x140065480`
- `0x140072d9c`
- `0x140074e88`
- `0x140074f3c`
- `0x140074fd0`
- `0x1401ccbf8`
- `0x1401d8014`
- `0x140222bbc`
- `0x14023be38`
- `0x140243c9c`
- `0x14025c214`
- `0x14025c530`
- `0x1403a3d50`
- `0x1403b65c8`
- `0x1403c84e4`

## import_xrefs

- `ntoskrnl!KeCancelTimer` at `0x1401ccf83`
- `ntoskrnl!KeCancelTimer` at `0x1401ccfa6`
- `ntoskrnl!KeCancelTimer` at `0x1401ccf83`
- `ntoskrnl!KeCancelTimer` at `0x1401ccfa6`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ccccb`
- `ntoskrnl!ExDeleteResourceLite` at `0x1401ccccb`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1401ccf93`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1401ccfb6`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1401ccf93`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1401ccfb6`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1401ccf4d`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1401ccf4d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401ccc96`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401ccd4d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401ccd70`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401cd007`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401ccc96`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401ccd4d`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401ccd70`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1401cd007`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1401ccf0f`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1401ccf2e`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1401ccf0f`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x1401ccf2e`
- `ntoskrnl!RtlNumberOfClearBits` at `0x1401ccdd4`
- `ntoskrnl!RtlNumberOfClearBits` at `0x1401cce4e`
- `ntoskrnl!RtlNumberOfClearBits` at `0x1401ccdd4`
- `ntoskrnl!RtlNumberOfClearBits` at `0x1401cce4e`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401ccead`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401ccec1`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401ccead`
- `ntoskrnl!RtlInitializeBitMap` at `0x1401ccec1`
- `ntoskrnl!ExUnregisterExtension` at `0x1401ccc25`
- `ntoskrnl!ExUnregisterExtension` at `0x1401ccc25`
- `watchdog!WdLogSingleEntry0` at `0x1401ccdf1`
- `watchdog!WdLogSingleEntry0` at `0x1401cce61`
- `watchdog!WdLogSingleEntry0` at `0x1401cd024`
- `watchdog!WdLogSingleEntry0` at `0x1401cd077`
- `watchdog!WdLogSingleEntry0` at `0x1401cd0ca`
- `watchdog!WdLogSingleEntry0` at `0x1401cd11e`
- `watchdog!WdLogSingleEntry0` at `0x1401cd171`
- `watchdog!WdLogSingleEntry0` at `0x1401cd1c3`
- `watchdog!WdLogSingleEntry0` at `0x1401ccdf1`
- `watchdog!WdLogSingleEntry0` at `0x1401cce61`
- `watchdog!WdLogSingleEntry0` at `0x1401cd024`
- `watchdog!WdLogSingleEntry0` at `0x1401cd077`
- `watchdog!WdLogSingleEntry0` at `0x1401cd0ca`
- `watchdog!WdLogSingleEntry0` at `0x1401cd11e`
- `watchdog!WdLogSingleEntry0` at `0x1401cd171`
- `watchdog!WdLogSingleEntry0` at `0x1401cd1c3`

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
    xmmword_14015E340 = 0;
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
0x1401ccbf8  push    rbx
0x1401ccbfa  push    rbp
0x1401ccbfb  push    rsi
0x1401ccbfc  push    rdi
0x1401ccbfd  push    r12
0x1401ccbff  push    r13
0x1401ccc01  push    r14
0x1401ccc03  push    r15
0x1401ccc05  sub     rsp, 58h
0x1401ccc09  lea     rax, ??_7DXGGLOBAL@@6B@; const DXGGLOBAL::`vftable'
0x1401ccc10  mov     rdi, rcx
0x1401ccc13  mov     [rcx], rax
0x1401ccc16  xor     r15d, r15d
0x1401ccc19  mov     rcx, cs:?DxgExtensionRegistration@@3PEAU_EX_EXTENSION@@EA; _EX_EXTENSION * DxgExtensionRegistration
0x1401ccc20  test    rcx, rcx
0x1401ccc23  jz      short loc_1401CCC50
0x1401ccc25  call    cs:__imp_ExUnregisterExtension
0x1401ccc2c  nop     dword ptr [rax+rax+00h]
0x1401ccc31  xorps   xmm0, xmm0
0x1401ccc34  mov     cs:?DxgExtensionRegistration@@3PEAU_EX_EXTENSION@@EA, r15; _EX_EXTENSION * DxgExtensionRegistration
0x1401ccc3b  movups  cs:?DxgExtensionInfo@@3U_EX_EXTENSION_REGISTRATION_2@@A, xmm0; _EX_EXTENSION_REGISTRATION_2 DxgExtensionInfo
0x1401ccc42  mov     cs:?DxgHostTable@@3PEAU_PS_DXG_HOST_INTERFACE@@EA, r15; _PS_DXG_HOST_INTERFACE * DxgHostTable
0x1401ccc49  movups  cs:xmmword_14015E340, xmm0
0x1401ccc50  mov     rbx, r15
0x1401ccc53  mov     r12d, 1
0x1401ccc59  lea     r14, ?m_pDxgmmsExport@DXGGLOBAL@@0PAPEAVDXGMMS_EXPORT@@A; DXGMMS_EXPORT * near * DXGGLOBAL::m_pDxgmmsExport
0x1401ccc60  mov     rsi, [r14+rbx*8]
0x1401ccc64  test    rsi, rsi
0x1401ccc67  jz      short loc_1401CCC79
0x1401ccc69  mov     rcx, rsi; this
0x1401ccc6c  call    ?Release@DXGMMS_EXPORT@@QEAAJXZ; DXGMMS_EXPORT::Release(void)
0x1401ccc71  mov     rcx, rsi; void *
0x1401ccc74  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401ccc79  mov     [r14+rbx*8], r15
0x1401ccc7d  add     rbx, r12
0x1401ccc80  cmp     rbx, 2
0x1401ccc84  jnz     short loc_1401CCC59
0x1401ccc86  cmp     [rdi+553h], r15b
0x1401ccc8d  jz      short loc_1401CCCA2
0x1401ccc8f  lea     rcx, [rdi+0A0h]; Lookaside
0x1401ccc96  call    cs:__imp_ExDeleteLookasideListEx
0x1401ccc9d  nop     dword ptr [rax+rax+00h]
0x1401ccca2  mov     rbx, [rdi+20h]
0x1401ccca6  test    rbx, rbx
0x1401ccca9  jz      short loc_1401CCCBB
0x1401cccab  mov     rcx, rbx; this
0x1401cccae  call    ??1HMGRTABLE@@QEAA@XZ; HMGRTABLE::~HMGRTABLE(void)
0x1401cccb3  mov     rcx, rbx; void *
0x1401cccb6  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401cccbb  mov     rcx, [rdi+260h]; Resource
0x1401cccc2  mov     [rdi+20h], r15
0x1401cccc6  test    rcx, rcx
0x1401cccc9  jz      short loc_1401CCCEA
0x1401ccccb  call    cs:__imp_ExDeleteResourceLite
0x1401cccd2  nop     dword ptr [rax+rax+00h]
0x1401cccd7  mov     rcx, [rdi+260h]; void *
0x1401cccde  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401ccce3  mov     [rdi+260h], r15
0x1401cccea  mov     rcx, [rdi+3C8h]; this
0x1401cccf1  test    rcx, rcx
0x1401cccf4  jz      short loc_1401CCD02
0x1401cccf6  call    ??_GDXGDIAGNOSTICS@@QEAAPEAXI@Z; DXGDIAGNOSTICS::`scalar deleting destructor'(uint)
0x1401cccfb  mov     [rdi+3C8h], r15
0x1401ccd02  mov     rcx, [rdi+3D0h]; this
0x1401ccd09  test    rcx, rcx
0x1401ccd0c  jz      short loc_1401CCD1A
0x1401ccd0e  call    ??_GDXGDIAGNOSTICS@@QEAAPEAXI@Z; DXGDIAGNOSTICS::`scalar deleting destructor'(uint)
0x1401ccd13  mov     [rdi+3D0h], r15
0x1401ccd1a  mov     rbx, [rdi+3D8h]
0x1401ccd21  test    rbx, rbx
0x1401ccd24  jz      short loc_1401CCD3D
0x1401ccd26  mov     rcx, rbx; this
0x1401ccd29  call    ??1DXGSESSIONMGR@@QEAA@XZ; DXGSESSIONMGR::~DXGSESSIONMGR(void)
0x1401ccd2e  mov     rcx, rbx; void *
0x1401ccd31  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401ccd36  mov     [rdi+3D8h], r15
0x1401ccd3d  cmp     [rdi+551h], r15b
0x1401ccd44  jz      short loc_1401CCD60
0x1401ccd46  lea     rcx, [rdi+480h]; Lookaside
0x1401ccd4d  call    cs:__imp_ExDeleteLookasideListEx
0x1401ccd54  nop     dword ptr [rax+rax+00h]
0x1401ccd59  mov     [rdi+551h], r15b
0x1401ccd60  cmp     [rdi+552h], r15b
0x1401ccd67  jz      short loc_1401CCD83
0x1401ccd69  lea     rcx, [rdi+4E0h]; Lookaside
0x1401ccd70  call    cs:__imp_ExDeleteLookasideListEx
0x1401ccd77  nop     dword ptr [rax+rax+00h]
0x1401ccd7c  mov     [rdi+552h], r15b
0x1401ccd83  mov     rcx, [rdi+568h]; this
0x1401ccd8a  test    rcx, rcx
0x1401ccd8d  jz      short loc_1401CCD9B
0x1401ccd8f  call    ?DestroyDxgProcess@DXGPROCESS@@SAXPEAV1@@Z; DXGPROCESS::DestroyDxgProcess(DXGPROCESS *)
0x1401ccd94  mov     [rdi+568h], r15
0x1401ccd9b  mov     rcx, [rdi+4A748h]; void *
0x1401ccda2  test    rcx, rcx
0x1401ccda5  jz      short loc_1401CCDB3
0x1401ccda7  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401ccdac  mov     [rdi+4A748h], r15
0x1401ccdb3  or      r13d, 0FFFFFFFFh
0x1401ccdb7  mov     r14d, 40002h
0x1401ccdbd  cmp     [rdi+388h], r15
0x1401ccdc4  jz      loc_1401CCEE0
0x1401ccdca  lea     rsi, [rdi+368h]
0x1401ccdd1  mov     rcx, rsi; BitMapHeader
0x1401ccdd4  call    cs:__imp_RtlNumberOfClearBits
0x1401ccddb  nop     dword ptr [rax+rax+00h]
0x1401ccde0  mov     rcx, rdi; this
0x1401ccde3  mov     ebx, eax
0x1401ccde5  call    ?GetMaximumGlobalAdapterCount@DXGGLOBAL@@QEBAKXZ; DXGGLOBAL::GetMaximumGlobalAdapterCount(void)
0x1401ccdea  cmp     ebx, eax
0x1401ccdec  jz      short loc_1401CCE35
0x1401ccdee  mov     ecx, r12d
0x1401ccdf1  call    cs:__imp_WdLogSingleEntry0
0x1401ccdf8  nop     dword ptr [rax+rax+00h]
0x1401ccdfd  mov     [rsp+98h+var_58], r15
0x1401cce02  lea     r9, aRtlnumberofcle_0; "RtlNumberOfClearBits(&m_GlobalAdapterOr"...
0x1401cce09  mov     [rsp+98h+var_60], r15
0x1401cce0e  mov     eax, 6A2h
0x1401cce13  mov     [rsp+98h+var_68], r15
0x1401cce18  mov     r8d, r13d
0x1401cce1b  mov     [rsp+98h+var_70], r15
0x1401cce20  mov     edx, r14d
0x1401cce23  xor     ecx, ecx
0x1401cce25  mov     [rsp+98h+var_78], rax
0x1401cce2a  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cce30  call    DxgkLogInternalTriageEvent
0x1401cce35  mov     rcx, rdi; this
0x1401cce38  lea     rbp, [rdi+378h]
0x1401cce3f  call    ?GetMaximumGlobalAdapterCount@DXGGLOBAL@@QEBAKXZ; DXGGLOBAL::GetMaximumGlobalAdapterCount(void)
0x1401cce44  mov     ebx, 400h
0x1401cce49  mov     rcx, rbp; BitMapHeader
0x1401cce4c  sub     ebx, eax
0x1401cce4e  call    cs:__imp_RtlNumberOfClearBits
0x1401cce55  nop     dword ptr [rax+rax+00h]
0x1401cce5a  cmp     eax, ebx
0x1401cce5c  jz      short loc_1401CCEA5
0x1401cce5e  mov     ecx, r12d
0x1401cce61  call    cs:__imp_WdLogSingleEntry0
0x1401cce68  nop     dword ptr [rax+rax+00h]
0x1401cce6d  mov     [rsp+98h+var_58], r15
0x1401cce72  lea     r9, aRtlnumberofcle_1; "RtlNumberOfClearBits(&m_SessionizedAdap"...
0x1401cce79  mov     [rsp+98h+var_60], r15
0x1401cce7e  mov     eax, 6A3h
0x1401cce83  mov     [rsp+98h+var_68], r15
0x1401cce88  mov     r8d, r13d
0x1401cce8b  mov     [rsp+98h+var_70], r15
0x1401cce90  mov     edx, r14d
0x1401cce93  xor     ecx, ecx
0x1401cce95  mov     [rsp+98h+var_78], rax
0x1401cce9a  mov     cs:WdLogGlobalForLineNumber, eax
0x1401ccea0  call    DxgkLogInternalTriageEvent
0x1401ccea5  xor     r8d, r8d; SizeOfBitMap
0x1401ccea8  xor     edx, edx; BitMapBuffer
0x1401cceaa  mov     rcx, rsi; BitMapHeader
0x1401ccead  call    cs:__imp_RtlInitializeBitMap
0x1401cceb4  nop     dword ptr [rax+rax+00h]
0x1401cceb9  xor     r8d, r8d; SizeOfBitMap
0x1401ccebc  xor     edx, edx; BitMapBuffer
0x1401ccebe  mov     rcx, rbp; BitMapHeader
0x1401ccec1  call    cs:__imp_RtlInitializeBitMap
0x1401ccec8  nop     dword ptr [rax+rax+00h]
0x1401ccecd  mov     rcx, [rdi+388h]; void *
0x1401cced4  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401cced9  mov     [rdi+388h], r15
0x1401ccee0  mov     rbx, [rdi+5C8h]
0x1401ccee7  test    rbx, rbx
0x1401cceea  jz      short loc_1401CCF03
0x1401cceec  mov     rcx, rbx; this
0x1401cceef  call    ??1QDC_CACHE@@QEAA@XZ; QDC_CACHE::~QDC_CACHE(void)
0x1401ccef4  mov     rcx, rbx; void *
0x1401ccef7  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401ccefc  mov     [rdi+5C8h], r15
0x1401ccf03  mov     rcx, [rdi+770h]
0x1401ccf0a  test    rcx, rcx
0x1401ccf0d  jz      short loc_1401CCF22
0x1401ccf0f  call    cs:__imp_ExUnsubscribeWnfStateChange
0x1401ccf16  nop     dword ptr [rax+rax+00h]
0x1401ccf1b  mov     [rdi+770h], r15
0x1401ccf22  mov     rcx, [rdi+828h]
0x1401ccf29  test    rcx, rcx
0x1401ccf2c  jz      short loc_1401CCF41
0x1401ccf2e  call    cs:__imp_ExUnsubscribeWnfStateChange
0x1401ccf35  nop     dword ptr [rax+rax+00h]
0x1401ccf3a  mov     [rdi+828h], r15
0x1401ccf41  mov     rcx, [rdi+830h]; Handle
0x1401ccf48  test    rcx, rcx
0x1401ccf4b  jz      short loc_1401CCF60
0x1401ccf4d  call    cs:__imp_PoUnregisterPowerSettingCallback
0x1401ccf54  nop     dword ptr [rax+rax+00h]
0x1401ccf59  mov     [rdi+830h], r15
0x1401ccf60  cmp     [rdi+83Ch], r15d
0x1401ccf67  jz      short loc_1401CCF7C
0x1401ccf69  lea     rcx, SLEEPSTUDY_ETW_PROVIDER_Context
0x1401ccf70  call    McGenEventUnregister_EtwUnregister
0x1401ccf75  mov     [rdi+83Ch], r15d
0x1401ccf7c  lea     rcx, [rdi+780h]; PKTIMER
0x1401ccf83  call    cs:__imp_KeCancelTimer
0x1401ccf8a  nop     dword ptr [rax+rax+00h]
0x1401ccf8f  test    al, al
0x1401ccf91  jnz     short loc_1401CCF9F
0x1401ccf93  call    cs:__imp_KeFlushQueuedDpcs
0x1401ccf9a  nop     dword ptr [rax+rax+00h]
0x1401ccf9f  lea     rcx, [rdi+4AA80h]; PKTIMER
0x1401ccfa6  call    cs:__imp_KeCancelTimer
0x1401ccfad  nop     dword ptr [rax+rax+00h]
0x1401ccfb2  test    al, al
0x1401ccfb4  jnz     short loc_1401CCFC2
0x1401ccfb6  call    cs:__imp_KeFlushQueuedDpcs
0x1401ccfbd  nop     dword ptr [rax+rax+00h]
0x1401ccfc2  mov     rcx, [rdi+4A6F8h]; void *
0x1401ccfc9  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1401ccfce  mov     rcx, [rdi+6A0h]; this
0x1401ccfd5  test    rcx, rcx
0x1401ccfd8  jz      short loc_1401CCFDF
0x1401ccfda  call    ??_GDXG_GUEST_GLOBAL_VMBUS@@QEAAPEAXI@Z; DXG_GUEST_GLOBAL_VMBUS::`scalar deleting destructor'(uint)
0x1401ccfdf  mov     rcx, [rdi+4A838h]; this
0x1401ccfe6  test    rcx, rcx
0x1401ccfe9  jz      short loc_1401CCFF7
0x1401ccfeb  call    ?Release@ReferenceCounted@@QEBA_KXZ; ReferenceCounted::Release(void)
0x1401ccff0  mov     [rdi+4A838h], r15
0x1401ccff7  cmp     [rdi+4A920h], r15b
0x1401ccffe  jz      short loc_1401CD013
0x1401cd000  lea     rcx, [rdi+4A930h]; Lookaside
0x1401cd007  call    cs:__imp_ExDeleteLookasideListEx
0x1401cd00e  nop     dword ptr [rax+rax+00h]
0x1401cd013  mov     eax, [rdi+168h]
0x1401cd019  cmp     [rdi+16Ch], eax
0x1401cd01f  jz      short loc_1401CD068
0x1401cd021  mov     ecx, r12d
0x1401cd024  call    cs:__imp_WdLogSingleEntry0
0x1401cd02b  nop     dword ptr [rax+rax+00h]
0x1401cd030  mov     [rsp+98h+var_58], r15
0x1401cd035  lea     r9, aMSharehandleta; "m_ShareHandleTable.IsEmpty()"
0x1401cd03c  mov     [rsp+98h+var_60], r15
0x1401cd041  mov     eax, 6F5h
0x1401cd046  mov     [rsp+98h+var_68], r15
0x1401cd04b  mov     r8d, r13d
0x1401cd04e  mov     [rsp+98h+var_70], r15
0x1401cd053  mov     edx, r14d
0x1401cd056  xor     ecx, ecx
0x1401cd058  mov     [rsp+98h+var_78], rax
0x1401cd05d  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cd063  call    DxgkLogInternalTriageEvent
0x1401cd068  lea     rbx, [rdi+250h]
0x1401cd06f  cmp     [rbx], rbx
0x1401cd072  jz      short loc_1401CD0BB
0x1401cd074  mov     ecx, r12d
0x1401cd077  call    cs:__imp_WdLogSingleEntry0
0x1401cd07e  nop     dword ptr [rax+rax+00h]
0x1401cd083  mov     [rsp+98h+var_58], r15
0x1401cd088  lea     r9, aMSyncobjectlis; "m_SyncObjectList.IsEmpty()"
0x1401cd08f  mov     [rsp+98h+var_60], r15
0x1401cd094  mov     eax, 6F6h
0x1401cd099  mov     [rsp+98h+var_68], r15
0x1401cd09e  mov     r8d, r13d
0x1401cd0a1  mov     [rsp+98h+var_70], r15
0x1401cd0a6  mov     edx, r14d
0x1401cd0a9  xor     ecx, ecx
0x1401cd0ab  mov     [rsp+98h+var_78], rax
0x1401cd0b0  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cd0b6  call    DxgkLogInternalTriageEvent
0x1401cd0bb  lea     rsi, [rdi+298h]
0x1401cd0c2  cmp     [rsi], rsi
0x1401cd0c5  jz      short loc_1401CD10E
0x1401cd0c7  mov     ecx, r12d
0x1401cd0ca  call    cs:__imp_WdLogSingleEntry0
0x1401cd0d1  nop     dword ptr [rax+rax+00h]
0x1401cd0d6  mov     [rsp+98h+var_58], r15
0x1401cd0db  lea     r9, aMKeyedmutexlis; "m_KeyedMutexList.IsEmpty()"
0x1401cd0e2  mov     [rsp+98h+var_60], r15
0x1401cd0e7  mov     eax, 6F7h
0x1401cd0ec  mov     [rsp+98h+var_68], r15
0x1401cd0f1  mov     r8d, r13d
0x1401cd0f4  mov     [rsp+98h+var_70], r15
0x1401cd0f9  mov     edx, r14d
0x1401cd0fc  xor     ecx, ecx
0x1401cd0fe  mov     [rsp+98h+var_78], rax
0x1401cd103  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cd109  call    DxgkLogInternalTriageEvent
0x1401cd10e  lea     rbp, [rdi+328h]
0x1401cd115  cmp     [rbp+0], rbp
0x1401cd119  jz      short loc_1401CD162
0x1401cd11b  mov     ecx, r12d
0x1401cd11e  call    cs:__imp_WdLogSingleEntry0
0x1401cd125  nop     dword ptr [rax+rax+00h]
0x1401cd12a  mov     [rsp+98h+var_58], r15
0x1401cd12f  lea     r9, aMAdapterlistIs; "m_AdapterList.IsEmpty()"
0x1401cd136  mov     [rsp+98h+var_60], r15
0x1401cd13b  mov     eax, 6F8h
0x1401cd140  mov     [rsp+98h+var_68], r15
0x1401cd145  mov     r8d, r13d
0x1401cd148  mov     [rsp+98h+var_70], r15
0x1401cd14d  mov     edx, r14d
0x1401cd150  xor     ecx, ecx
0x1401cd152  mov     [rsp+98h+var_78], rax
0x1401cd157  mov     cs:WdLogGlobalForLineNumber, eax
0x1401cd15d  call    DxgkLogInternalTriageEvent
0x1401cd162  lea     r14, [rdi+710h]
0x1401cd169  cmp     [r14], r14
0x1401cd16c  jz      short loc_1401CD1B7
  ... truncated ...
```
