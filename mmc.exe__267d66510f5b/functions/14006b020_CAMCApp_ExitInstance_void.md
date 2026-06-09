# CAMCApp::ExitInstance(void)

- ea: `0x14006b020`
- end: `0x14006b36a`
- name: `?ExitInstance@CAMCApp@@UEAAHXZ`
- size: `842`
- prototype: `__int64 __fastcall(CAMCApp *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140027c80`
- `0x140034224`
- `0x14003ce40`
- `0x140053e34`
- `0x140055928`
- `0x140057d04`
- `0x14006b020`
- `0x1400754f4`
- `0x140076320`
- `0x1400c41d0`
- `0x1400f3010`

## import_xrefs

- `USER32!IsWindow` at `0x14006b092`
- `USER32!IsWindow` at `0x14006b092`
- `MFC42u!__imp_?ExitInstance@CWinApp@@UEAAHXZ` at `0x14006b2c0`
- `MFC42u!__imp_?ExitInstance@CWinApp@@UEAAHXZ` at `0x14006b2c0`
- `MFC42u!__imp_?RunAutomated@CWinApp@@QEAAHXZ` at `0x14006b114`
- `MFC42u!__imp_?RunAutomated@CWinApp@@QEAAHXZ` at `0x14006b114`
- `MFC42u!__imp_?RunEmbedded@CWinApp@@QEAAHXZ` at `0x14006b107`
- `MFC42u!__imp_?RunEmbedded@CWinApp@@QEAAHXZ` at `0x14006b107`
- `ntdll!EtwUnregisterTraceGuids` at `0x14006b318`
- `ntdll!EtwUnregisterTraceGuids` at `0x14006b318`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14006b0d5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14006b1df`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14006b252`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14006b351`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14006b0d5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14006b1df`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14006b252`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14006b351`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x14006b03b`
- `mmcbase!?TraceError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x14006b229`
- `mmcbase!?TraceError@@YAXPEBGAEBVSC@mmcerror@@@Z` at `0x14006b229`
- `mmcbase!?ScSetConsoleEventDispatcher@CConsoleEventDispatcherProvider@@SA?AVSC@mmcerror@@PEAVCConsoleEventDispatcher@@@Z` at `0x14006b0bc`
- `mmcbase!?ScSetConsoleEventDispatcher@CConsoleEventDispatcherProvider@@SA?AVSC@mmcerror@@PEAVCConsoleEventDispatcher@@@Z` at `0x14006b0bc`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14006b0ca`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14006b1d4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14006b0ca`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14006b1d4`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14006b059`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14006b059`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x14006b0f0`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x14006b1fa`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x14006b0f0`
- `mmcbase!?TraceAndClear@SC@mmcerror@@QEAAXXZ` at `0x14006b1fa`
- `ole32!CoCreateInstance` at `0x14006b185`
- `ole32!CoCreateInstance` at `0x14006b185`
- `ole32!CoFreeUnusedLibraries` at `0x14006b22f`
- `ole32!CoFreeUnusedLibraries` at `0x14006b22f`
- `ole32!OleUninitialize` at `0x14006b23e`
- `ole32!OleUninitialize` at `0x14006b23e`
- `ole32!CoRevokeClassObject` at `0x14006b138`
- `ole32!CoRevokeClassObject` at `0x14006b138`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006b33c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006b33c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14006b2f4`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x14006b2f4`
- `KERNEL32!ReleaseActCtx` at `0x14006b268`
- `KERNEL32!ReleaseActCtx` at `0x14006b268`
- `DUI70!UnInitProcessPriv` at `0x14006b2b7`
- `DUI70!UnInitProcessPriv` at `0x14006b2b7`
- `DUI70!UnInitThread` at `0x14006b2aa`
- `DUI70!UnInitThread` at `0x14006b2aa`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=4
__int64 __fastcall CAMCApp::ExitInstance(CAMCApp *this)
{
  struct CWnd *MainWnd; // rax
  HWND v3; // rcx
  struct CWnd *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdi
  HRESULT v8; // eax
  LPVOID v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // edi
  REGHANDLE v12; // rcx
  _QWORD *v13; // rbx
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  __int128 v16; // [rsp+38h] [rbp-28h]
  int v17; // [rsp+48h] [rbp-18h] BYREF
  int v18; // [rsp+4Ch] [rbp-14h]
  LPVOID ppv; // [rsp+88h] [rbp+28h] BYREF

  v16 = 0;
  ++mmcerror::SC::s_CallDepth;
  v15 = 3;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)&v15, L"CAMCApp::ExitInstance");
  if ( (unsigned int)ActiveThreadsTracker(0, 0x1388u, 1) )
    ActiveThreadsTracker(0, 0x1388u, 0);
  MainWnd = AfxGetMainWnd();
  if ( MainWnd )
    v3 = (HWND)*((_QWORD *)MainWnd + 8);
  else
    v3 = 0;
  if ( IsWindow(v3) )
  {
    v4 = AfxGetMainWnd();
    (*(void (__fastcall **)(struct CWnd *))(*(_QWORD *)v4 + 192LL))(v4);
  }
  v5 = CConsoleEventDispatcherProvider::ScSetConsoleEventDispatcher(&v17, 0);
  mmcerror::SC::operator=(&v15, v5);
  mmcerror::SC::~SC((mmcerror::SC *)&v17);
  if ( HIDWORD(v15) && ((_DWORD)v15 != 3 || v15 < 0) )
    mmcerror::SC::TraceAndClear((mmcerror::SC *)&v15);
  _com_ptr_t<_com_IIID<IDataObject,&__s_GUID const _GUID_0000010e_0000_0000_c000_000000000046>>::operator=(
    (char *)this + 416,
    0);
  if ( CWinApp::RunEmbedded(this) || CWinApp::RunAutomated(this) )
  {
    v7 = qword_140161D40;
    if ( qword_140161D40 )
    {
      v8 = 0;
      if ( *(_QWORD *)qword_140161D40 )
      {
        do
        {
          if ( v8 )
            break;
          v8 = CoRevokeClassObject(*(_DWORD *)(v7 + 40));
          v6 = 72;
          if ( (_DWORD)_Module == 176 )
            v6 = 56;
          v7 += v6;
        }
        while ( *(_QWORD *)v7 );
      }
    }
  }
  ATL::AtlModuleTerm((struct ATL::_ATL_MODULE *)v6);
  ppv = 0;
  if ( !CoCreateInstance(&CLSID_ComCacheCleanup, 0, 3u, &GUID_35feb982_55e9_483b_bd15_149f3f9e6c63, &ppv) )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 24LL))(ppv);
    v9 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  v10 = CMMCProtocolRegistrar::ScUnregister((char *)this + 448, &v17);
  mmcerror::SC::operator=(&v15, v10);
  mmcerror::SC::~SC((mmcerror::SC *)&v17);
  if ( HIDWORD(v15) && ((_DWORD)v15 != 3 || v15 < 0) )
    mmcerror::SC::TraceAndClear((mmcerror::SC *)&v15);
  CAMCApp::ScUninitializeHelpControl(this, &v17);
  if ( v18 && (v17 != 3 || v18 < 0) )
    TraceError(L"Uninit Help control failed", (const struct mmcerror::SC *)&v17);
  CoFreeUnusedLibraries();
  if ( *((_DWORD *)this + 106) == 1 )
  {
    OleUninitialize();
    *((_DWORD *)this + 106) = 0;
  }
  mmcerror::SC::~SC((mmcerror::SC *)&v17);
  if ( g_hActCtx != (HANDLE)-1LL )
  {
    ReleaseActCtx(g_hActCtx);
    g_hActCtx = (HANDLE)-1LL;
  }
  if ( qword_1401622E0 )
    qword_1401622E0 = (HMODULE)-1LL;
  CSimpleLock::Enter((CSimpleLock *)&g_lckLkrInit);
  if ( !--dword_1401624C8 )
    byte_1401624CC = 0;
  _InterlockedExchange((volatile __int32 *)&g_lckLkrInit, 0);
  UnInitThread();
  UnInitProcessPriv(&_ImageBase);
  v11 = CWinApp::ExitInstance(this);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025>::GetImpl'::`2'::impl) )
  {
    v12 = RegHandle;
    dword_140157418 = 0;
    RegHandle = 0;
    EventUnregister(v12);
  }
  v13 = (_QWORD *)WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    while ( v13 )
    {
      if ( v13[1] )
      {
        EtwUnregisterTraceGuids();
        v13[1] = 0;
      }
      v13 = (_QWORD *)*v13;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
  CloseHandle(g_hThreadTrackerMutex);
  _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(&ppv);
  mmcerror::SC::~SC((mmcerror::SC *)&v15);
  return v11;
}

```

## disassembly

```asm
0x14006b020  mov     [rsp-18h+arg_10], rbx
0x14006b025  push    rbp
0x14006b026  push    rdi
0x14006b027  push    r14
0x14006b029  mov     rbp, rsp
0x14006b02c  sub     rsp, 60h
0x14006b030  mov     rbx, rcx
0x14006b033  xorps   xmm0, xmm0
0x14006b036  movdqu  [rbp+var_28], xmm0
0x14006b03b  mov     rax, cs:__imp_?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x14006b042  inc     dword ptr [rax]
0x14006b044  mov     r14d, 3
0x14006b04a  mov     [rbp+var_30], r14
0x14006b04e  lea     rdx, aCamcappExitins; "CAMCApp::ExitInstance"
0x14006b055  lea     rcx, [rbp+var_30]
0x14006b059  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14006b05f  mov     r8b, 1
0x14006b062  mov     edi, 1388h
0x14006b067  mov     edx, edi
0x14006b069  xor     ecx, ecx
0x14006b06b  call    ActiveThreadsTracker
0x14006b070  test    eax, eax
0x14006b072  jz      short loc_14006B080
0x14006b074  xor     r8d, r8d
0x14006b077  mov     edx, edi
0x14006b079  xor     ecx, ecx
0x14006b07b  call    ActiveThreadsTracker
0x14006b080  call    ?AfxGetMainWnd@@YAPEAVCWnd@@XZ; AfxGetMainWnd(void)
0x14006b085  test    rax, rax
0x14006b088  jnz     short loc_14006B08E
0x14006b08a  xor     ecx, ecx
0x14006b08c  jmp     short loc_14006B092
0x14006b08e  mov     rcx, [rax+40h]; hWnd
0x14006b092  call    cs:__imp_IsWindow
0x14006b098  test    eax, eax
0x14006b09a  jz      short loc_14006B0B6
0x14006b09c  call    ?AfxGetMainWnd@@YAPEAVCWnd@@XZ; AfxGetMainWnd(void)
0x14006b0a1  mov     rdx, rax
0x14006b0a4  mov     rcx, [rax]
0x14006b0a7  mov     rax, [rcx+0C0h]
0x14006b0ae  mov     rcx, rdx
0x14006b0b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b0b6  xor     edx, edx
0x14006b0b8  lea     rcx, [rbp+var_18]
0x14006b0bc  call    cs:__imp_?ScSetConsoleEventDispatcher@CConsoleEventDispatcherProvider@@SA?AVSC@mmcerror@@PEAVCConsoleEventDispatcher@@@Z; CConsoleEventDispatcherProvider::ScSetConsoleEventDispatcher(CConsoleEventDispatcher *)
0x14006b0c2  nop
0x14006b0c3  mov     rdx, rax
0x14006b0c6  lea     rcx, [rbp+var_30]
0x14006b0ca  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14006b0d0  nop
0x14006b0d1  lea     rcx, [rbp+var_18]
0x14006b0d5  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14006b0db  mov     eax, dword ptr [rbp+var_30+4]
0x14006b0de  test    eax, eax
0x14006b0e0  jz      short loc_14006B0F6
0x14006b0e2  cmp     dword ptr [rbp+var_30], r14d
0x14006b0e6  jnz     short loc_14006B0EC
0x14006b0e8  test    eax, eax
0x14006b0ea  jns     short loc_14006B0F6
0x14006b0ec  lea     rcx, [rbp+var_30]
0x14006b0f0  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x14006b0f6  lea     rcx, [rbx+1A0h]
0x14006b0fd  xor     edx, edx
0x14006b0ff  call    ??4?$_com_ptr_t@V?$_com_IIID@UIDataObject@@$1?_GUID_0000010e_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAAAEAV0@PEAUIDataObject@@@Z; _com_ptr_t<_com_IIID<IDataObject,&__s_GUID const _GUID_0000010e_0000_0000_c000_000000000046>>::operator=(IDataObject *)
0x14006b104  mov     rcx, rbx
0x14006b107  call    cs:__imp_?RunEmbedded@CWinApp@@QEAAHXZ; CWinApp::RunEmbedded(void)
0x14006b10d  test    eax, eax
0x14006b10f  jnz     short loc_14006B11E
0x14006b111  mov     rcx, rbx
0x14006b114  call    cs:__imp_?RunAutomated@CWinApp@@QEAAHXZ; CWinApp::RunAutomated(void)
0x14006b11a  test    eax, eax
0x14006b11c  jz      short loc_14006B15C
0x14006b11e  mov     rdi, cs:qword_140161D40
0x14006b125  test    rdi, rdi
0x14006b128  jz      short loc_14006B15C
0x14006b12a  xor     eax, eax
0x14006b12c  cmp     [rdi], rax
0x14006b12f  jz      short loc_14006B15C
0x14006b131  test    eax, eax
0x14006b133  jnz     short loc_14006B15C
0x14006b135  mov     ecx, [rdi+28h]; dwRegister
0x14006b138  call    cs:__imp_CoRevokeClassObject
0x14006b13e  mov     ecx, 48h ; 'H'
0x14006b143  lea     edx, [rcx-10h]
0x14006b146  cmp     cs:?_Module@@3VCAtlGlobalModule@@A, 0B0h; CAtlGlobalModule _Module
0x14006b150  cmovz   ecx, edx; struct ATL::_ATL_MODULE *
0x14006b153  add     rdi, rcx
0x14006b156  cmp     qword ptr [rdi], 0
0x14006b15a  jnz     short loc_14006B131
0x14006b15c  call    ?AtlModuleTerm@ATL@@YAJPEAU_ATL_MODULE@1@@Z; ATL::AtlModuleTerm(ATL::_ATL_MODULE *)
0x14006b161  mov     [rbp+arg_8], 0
0x14006b169  lea     rax, [rbp+arg_8]
0x14006b16d  mov     [rsp+60h+ppv], rax; ppv
0x14006b172  lea     r9, _GUID_35feb982_55e9_483b_bd15_149f3f9e6c63; riid
0x14006b179  mov     r8d, r14d; dwClsContext
0x14006b17c  xor     edx, edx; pUnkOuter
0x14006b17e  lea     rcx, CLSID_ComCacheCleanup; rclsid
0x14006b185  call    cs:__imp_CoCreateInstance
0x14006b18b  test    eax, eax
0x14006b18d  jnz     short loc_14006B1BC
0x14006b18f  mov     rcx, [rbp+arg_8]
0x14006b193  mov     rax, [rcx]
0x14006b196  mov     rax, [rax+18h]
0x14006b19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b19f  mov     rcx, [rbp+arg_8]
0x14006b1a3  test    rcx, rcx
0x14006b1a6  jz      short loc_14006B1BC
0x14006b1a8  mov     [rbp+arg_8], 0
0x14006b1b0  mov     rax, [rcx]
0x14006b1b3  mov     rax, [rax+10h]
0x14006b1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b1bc  lea     rcx, [rbx+1C0h]
0x14006b1c3  lea     rdx, [rbp+var_18]
0x14006b1c7  call    ?ScUnregister@CMMCProtocolRegistrar@@QEAA?AVSC@mmcerror@@XZ; CMMCProtocolRegistrar::ScUnregister(void)
0x14006b1cc  nop
0x14006b1cd  mov     rdx, rax
0x14006b1d0  lea     rcx, [rbp+var_30]
0x14006b1d4  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14006b1da  nop
0x14006b1db  lea     rcx, [rbp+var_18]
0x14006b1df  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14006b1e5  mov     eax, dword ptr [rbp+var_30+4]
0x14006b1e8  test    eax, eax
0x14006b1ea  jz      short loc_14006B200
0x14006b1ec  cmp     dword ptr [rbp+var_30], r14d
0x14006b1f0  jnz     short loc_14006B1F6
0x14006b1f2  test    eax, eax
0x14006b1f4  jns     short loc_14006B200
0x14006b1f6  lea     rcx, [rbp+var_30]
0x14006b1fa  call    cs:__imp_?TraceAndClear@SC@mmcerror@@QEAAXXZ; mmcerror::SC::TraceAndClear(void)
0x14006b200  lea     rdx, [rbp+var_18]
0x14006b204  mov     rcx, rbx
0x14006b207  call    ?ScUninitializeHelpControl@CAMCApp@@AEAA?AVSC@mmcerror@@XZ; CAMCApp::ScUninitializeHelpControl(void)
0x14006b20c  nop
0x14006b20d  mov     eax, [rbp+var_14]
0x14006b210  test    eax, eax
0x14006b212  jz      short loc_14006B22F
0x14006b214  cmp     [rbp+var_18], r14d
0x14006b218  jnz     short loc_14006B21E
0x14006b21a  test    eax, eax
0x14006b21c  jns     short loc_14006B22F
0x14006b21e  lea     rdx, [rbp+var_18]
0x14006b222  lea     rcx, aUninitHelpCont; "Uninit Help control failed"
0x14006b229  call    cs:__imp_?TraceError@@YAXPEBGAEBVSC@mmcerror@@@Z; TraceError(ushort const *,mmcerror::SC const &)
0x14006b22f  call    cs:__imp_CoFreeUnusedLibraries
0x14006b235  cmp     dword ptr [rbx+1A8h], 1
0x14006b23c  jnz     short loc_14006B24E
0x14006b23e  call    cs:__imp_OleUninitialize
0x14006b244  mov     dword ptr [rbx+1A8h], 0
0x14006b24e  lea     rcx, [rbp+var_18]
0x14006b252  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14006b258  mov     rcx, cs:g_hActCtx; hActCtx
0x14006b25f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14006b263  cmp     rcx, rdi
0x14006b266  jz      short loc_14006B275
0x14006b268  call    cs:__imp_ReleaseActCtx
0x14006b26e  mov     cs:g_hActCtx, rdi
0x14006b275  cmp     cs:qword_1401622E0, 0
0x14006b27d  jz      short loc_14006B286
0x14006b27f  mov     cs:qword_1401622E0, rdi
0x14006b286  lea     rcx, ?g_lckLkrInit@@3VCSimpleLock@@A; this
0x14006b28d  call    ?Enter@CSimpleLock@@QEAAXXZ; CSimpleLock::Enter(void)
0x14006b292  sub     cs:dword_1401624C8, 1
0x14006b299  jnz     short loc_14006B2A2
0x14006b29b  mov     cs:byte_1401624CC, 0
0x14006b2a2  xor     eax, eax
0x14006b2a4  xchg    eax, cs:?g_lckLkrInit@@3VCSimpleLock@@A; CSimpleLock g_lckLkrInit
0x14006b2aa  call    cs:__imp_UnInitThread
0x14006b2b0  lea     rcx, __ImageBase
0x14006b2b7  call    cs:__imp_UnInitProcessPriv
0x14006b2bd  mov     rcx, rbx
0x14006b2c0  call    cs:__imp_?ExitInstance@CWinApp@@UEAAHXZ; CWinApp::ExitInstance(void)
0x14006b2c6  mov     edi, eax
0x14006b2c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025>::GetImpl(void)'::`2'::impl
0x14006b2cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AddTelemetryToMMC2025>::__private_IsEnabled(void)
0x14006b2d4  test    al, al
0x14006b2d6  jz      short loc_14006B2FA
0x14006b2d8  mov     rcx, cs:RegHandle; RegHandle
0x14006b2df  mov     cs:dword_140157418, 0
0x14006b2e9  mov     cs:RegHandle, 0
0x14006b2f4  call    cs:__imp_EventUnregister
0x14006b2fa  lea     r14, WPP_GLOBAL_Control
0x14006b301  mov     rbx, cs:WPP_GLOBAL_Control
0x14006b308  cmp     rbx, r14
0x14006b30b  jz      short loc_14006B335
0x14006b30d  jmp     short loc_14006B329
0x14006b30f  mov     rcx, [rbx+8]
0x14006b313  test    rcx, rcx
0x14006b316  jz      short loc_14006B326
0x14006b318  call    cs:__imp_EtwUnregisterTraceGuids
0x14006b31e  mov     qword ptr [rbx+8], 0
0x14006b326  mov     rbx, [rbx]
0x14006b329  test    rbx, rbx
0x14006b32c  jnz     short loc_14006B30F
0x14006b32e  mov     cs:WPP_GLOBAL_Control, r14
0x14006b335  mov     rcx, cs:?g_hThreadTrackerMutex@@3PEAXEA; hObject
0x14006b33c  call    cs:__imp_CloseHandle
0x14006b342  nop
0x14006b343  lea     rcx, [rbp+arg_8]
0x14006b347  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x14006b34c  nop
0x14006b34d  lea     rcx, [rbp+var_30]
0x14006b351  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14006b357  mov     eax, edi
0x14006b359  mov     rbx, [rsp+60h+arg_10]
0x14006b361  add     rsp, 60h
0x14006b365  pop     r14
0x14006b367  pop     rdi
0x14006b368  pop     rbp
0x14006b369  retn
```
