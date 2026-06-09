# CSNOCplCore::InitializePage(CSNOCplPage *)

- ea: `0x18000bf2c`
- end: `0x18000c364`
- name: `?InitializePage@CSNOCplCore@@QEAAJPEAVCSNOCplPage@@@Z`
- size: `1080`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct CSNOCplPage *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014ee0`

## callees

- `0x180002270`
- `0x18000400c`
- `0x180006b70`
- `0x18000a2e0`
- `0x18000a6d4`
- `0x18000b1f8`
- `0x18000b384`
- `0x18000bf2c`
- `0x18000f550`
- `0x180010e9c`
- `0x180011c38`
- `0x180014218`
- `0x180014274`
- `0x1800158ac`
- `0x180016cb8`
- `0x1800199fc`
- `0x180019ba0`
- `0x18001bec0`
- `0x18001e4a8`
- `0x18001fad8`
- `0x1800213ec`
- `0x1800215b4`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c21f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c21f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c2a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c215`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c215`
- `ntdll!WinSqmSetDWORD` at `0x18000c2b7`
- `ntdll!WinSqmSetDWORD` at `0x18000c2b7`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18000bff0`
- `SHLWAPI!__imp_IUnknown_GetSite` at `0x18000bff0`
- `SHLWAPI!__imp_SHQueueUserWorkItem` at `0x18000c086`
- `SHLWAPI!__imp_SHQueueUserWorkItem` at `0x18000c086`
- `USER32!SetPropW` at `0x18000c026`
- `USER32!SetPropW` at `0x18000c026`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18000c26a`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18000c26a`
- `wwapi!WwanRegisterNotification` at `0x18000c127`
- `wwapi!WwanRegisterNotification` at `0x18000c127`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSNOCplCore::InitializePage(CSNOCplCore *this, struct CSNOCplPage *a2, int a3, int a4)
{
  int v6; // ecx
  __int64 *v7; // r14
  __int64 v8; // rcx
  PVOID *v9; // rdx
  HRESULT Site; // edi
  HWND *v11; // rsi
  unsigned int Error; // eax
  HWND v13; // rsi
  CWwanHelper *v14; // rax
  CWwanHelper *v15; // rax
  __int64 v16; // rcx
  int v17; // esi
  PVOID *v18; // rcx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+40h] [rbp-48h] BYREF

  v6 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
  if ( (Microsoft_Windows_Network_and_Sharing_CenterEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, (int)&Perf_Initialization_Page_Start, a3, a4, &v23);
  *((_QWORD *)this + 41) = a2;
  *((_QWORD *)this + 40) = a2;
  v7 = (__int64 *)((char *)this + 344);
  v8 = *((_QWORD *)this + 43);
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    *v7 = 0;
  }
  Site = IUnknown_GetSite(
           (IUnknown *)(((unsigned __int64)a2 + 208) & -(__int64)(a2 != 0)),
           &GUID_00000000_0000_0000_c000_000000000046,
           (void **)this + 43);
  if ( Site < 0 )
    goto LABEL_34;
  v11 = (HWND *)((char *)this + 256);
  Site = CMessageWindow::Initialize((LONG_PTR)this + 256);
  if ( Site < 0 )
    goto LABEL_34;
  if ( !SetPropW(*v11, L"_Netcenter_ptr", this)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    Error = ResultFromKnownLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, Error);
  }
  if ( !(unsigned int)SHQueueUserWorkItem(s_SNOCplCoreAsyncNavPaneHelper, *v11, 0, 0, 0, 0, 16) )
  {
    Site = ResultFromKnownLastError();
    if ( Site < 0 )
      goto LABEL_34;
  }
  *((_QWORD *)this + 24) = *v11;
  *((_QWORD *)this + 23) = this;
  Site = CWlanHelper::RegisterWLANEvent((char *)this + 184);
  if ( Site < 0 )
    goto LABEL_34;
  v13 = *v11;
  v14 = (CWwanHelper *)DirectUI::HAllocAndZero((DirectUI *)0x38, (unsigned __int64)v9);
  v23.Ptr = (ULONGLONG)v14;
  if ( v14 )
    v15 = CWwanHelper::CWwanHelper(v14, v13, this);
  else
    v15 = 0;
  *((_QWORD *)this + 26) = v15;
  if ( v15 )
  {
    v16 = *((_QWORD *)v15 + 3);
    if ( v16 )
    {
      if ( *((_QWORD *)v15 + 4) )
      {
        LODWORD(v23.Ptr) = 0;
        WwanRegisterNotification(v16, 2, CWwanHelper::WwanNotificationCallback, v15, 0, &v23);
      }
    }
  }
  if ( !*((_DWORD *)this + 72) )
    goto LABEL_34;
  v17 = CProfileMgr::RegisterProfileEvent(this);
  if ( v17 < 0 )
    (*(void (__fastcall **)(CSNOCplCore *))(*(_QWORD *)this + 232LL))(this);
  Site = CProfileMgr::RegisterNetmanEvent(this);
  if ( Site < 0 )
    (*(void (__fastcall **)(CSNOCplCore *))(*(_QWORD *)this + 240LL))(this);
  if ( v17 < 0 )
    Site = v17;
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)Site);
LABEL_34:
    v18 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 74) )
  {
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 )
      WPP_SF_d(v18[2], 18, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, 2147500037LL);
    return 2147500037LL;
  }
  else
  {
    if ( Site >= 0 )
    {
      CSNOCplCore::StartServiceMonitors(this, v9);
      CoCreateInstance(&CLSID_HomeGroupCtrl, 0, 1u, &GUID_b0a10e19_e52b_4038_bbf7_867e5e6a51fb, (LPVOID *)this + 44);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      ClearProfileDataMap(*((_QWORD *)this + 19));
      if ( !*((_DWORD *)this + 72) || (Site = CProfileMgr::GetConnectedProfileList(this), Site >= 0) )
      {
        if ( !*((_DWORD *)this + 74) )
        {
          v23.Ptr = (ULONGLONG)a2;
          v23.Size = 0;
          DirectUI::Element::StartDefer(a2, &v23.Size);
          CSNOCplCore::GetXWizardTaskInfo(this);
          if ( !*((_DWORD *)this + 74) )
          {
            CSNOCplCore::PopulateProfileArea(this);
            CSNOCplCore::HandleConnectivityChange(this);
          }
          DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v23);
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
      if ( Site >= 0 )
      {
        WinSqmSetDWORD(0, 3696, 1);
        DUI_WalkIUnknownElements(a2, (void (*)(struct IUnknown *, __int64))DUI_SetSiteOnUnknown, *v7);
        Site = 0;
      }
    }
    CSNOCplCore::GetDeferParams(this);
    HrAddNSCInstance(this, *((HWND *)this + 32));
    *((_DWORD *)this + 73) = 1;
    if ( (Microsoft_Windows_Network_and_Sharing_CenterEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v20, (int)&Perf_Initialization_Page_Stop, v21, v22, &v23);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
        (unsigned int)Site);
    return (unsigned int)Site;
  }
}

```

## disassembly

```asm
0x18000bf2c  mov     [rsp+arg_10], rbx
0x18000bf31  mov     [rsp+arg_18], rbp
0x18000bf36  push    rsi
0x18000bf37  push    rdi
0x18000bf38  push    r12
0x18000bf3a  push    r14
0x18000bf3c  push    r15
0x18000bf3e  sub     rsp, 60h
0x18000bf42  mov     rax, cs:__security_cookie
0x18000bf49  xor     rax, rsp
0x18000bf4c  mov     [rsp+88h+var_38], rax
0x18000bf51  mov     rbp, rdx
0x18000bf54  mov     rbx, rcx
0x18000bf57  lea     r12, WPP_GLOBAL_Control
0x18000bf5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf65  cmp     rcx, r12
0x18000bf68  jz      short loc_18000BF85
0x18000bf6a  test    byte ptr [rcx+1Ch], 8
0x18000bf6e  jz      short loc_18000BF85
0x18000bf70  mov     edx, 0Fh
0x18000bf75  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000bf7c  mov     rcx, [rcx+10h]
0x18000bf80  call    WPP_SF_
0x18000bf85  test    cs:Microsoft_Windows_Network_and_Sharing_CenterEnableBits, 1
0x18000bf8c  jz      short loc_18000BFA4
0x18000bf8e  lea     rax, [rsp+88h+var_48]
0x18000bf93  mov     [rsp+88h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x18000bf98  lea     rdx, Perf_Initialization_Page_Start; int
0x18000bf9f  call    McGenEventWrite_EventWriteTransfer
0x18000bfa4  mov     [rbx+148h], rbp
0x18000bfab  mov     [rbx+140h], rbp
0x18000bfb2  lea     r14, [rbx+158h]
0x18000bfb9  mov     rcx, [r14]
0x18000bfbc  xor     r15d, r15d
0x18000bfbf  test    rcx, rcx
0x18000bfc2  jz      short loc_18000BFD3
0x18000bfc4  mov     rax, [rcx]
0x18000bfc7  mov     rax, [rax+10h]
0x18000bfcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfd0  mov     [r14], r15
0x18000bfd3  mov     rax, rbp
0x18000bfd6  lea     rdx, [rbp+0D0h]
0x18000bfdd  neg     rax
0x18000bfe0  sbb     rcx, rcx
0x18000bfe3  and     rcx, rdx; punk
0x18000bfe6  mov     r8, r14; ppv
0x18000bfe9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18000bff0  call    cs:__imp_IUnknown_GetSite
0x18000bff6  mov     edi, eax
0x18000bff8  test    eax, eax
0x18000bffa  js      loc_18000C1A5
0x18000c000  lea     rsi, [rbx+100h]
0x18000c007  mov     rcx, rsi; dwNewLong
0x18000c00a  call    ?Initialize@CMessageWindow@@QEAAJXZ; CMessageWindow::Initialize(void)
0x18000c00f  mov     edi, eax
0x18000c011  test    eax, eax
0x18000c013  js      loc_18000C1A5
0x18000c019  mov     r8, rbx; hData
0x18000c01c  lea     rdx, String; "_Netcenter_ptr"
0x18000c023  mov     rcx, [rsi]; hWnd
0x18000c026  call    cs:__imp_SetPropW
0x18000c02c  mov     edi, 10h
0x18000c031  test    eax, eax
0x18000c033  jnz     short loc_18000C068
0x18000c035  mov     rax, cs:WPP_GLOBAL_Control
0x18000c03c  cmp     rax, r12
0x18000c03f  jz      short loc_18000C068
0x18000c041  test    byte ptr [rax+1Ch], 1
0x18000c045  jz      short loc_18000C068
0x18000c047  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c04c  mov     edx, edi
0x18000c04e  mov     r9d, eax
0x18000c051  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000c058  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c05f  mov     rcx, [rcx+10h]
0x18000c063  call    WPP_SF_d
0x18000c068  mov     [rsp+88h+var_58], edi
0x18000c06c  mov     [rsp+88h+var_60], r15
0x18000c071  mov     [rsp+88h+ppv], r15
0x18000c076  xor     r9d, r9d
0x18000c079  xor     r8d, r8d
0x18000c07c  mov     rdx, [rsi]
0x18000c07f  lea     rcx, ?s_SNOCplCoreAsyncNavPaneHelper@@YAKPEAX@Z; s_SNOCplCoreAsyncNavPaneHelper(void *)
0x18000c086  call    cs:__imp_SHQueueUserWorkItem
0x18000c08c  test    eax, eax
0x18000c08e  jnz     short loc_18000C09F
0x18000c090  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000c095  mov     edi, eax
0x18000c097  test    eax, eax
0x18000c099  js      loc_18000C1A5
0x18000c09f  lea     rcx, [rbx+0B8h]; pCallbackContext
0x18000c0a6  mov     rax, [rsi]
0x18000c0a9  mov     [rcx+8], rax
0x18000c0ad  mov     [rcx], rbx
0x18000c0b0  call    ?RegisterWLANEvent@CWlanHelper@@QEAAJXZ; CWlanHelper::RegisterWLANEvent(void)
0x18000c0b5  mov     edi, eax
0x18000c0b7  test    eax, eax
0x18000c0b9  js      loc_18000C1A5
0x18000c0bf  mov     rsi, [rsi]
0x18000c0c2  mov     ecx, 38h ; '8'; this
0x18000c0c7  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18000c0cc  mov     [rsp+88h+var_48.Ptr], rax
0x18000c0d1  test    rax, rax
0x18000c0d4  jz      short loc_18000C0E6
0x18000c0d6  mov     r8, rbx; void *
0x18000c0d9  mov     rdx, rsi; HWND
0x18000c0dc  mov     rcx, rax; this
0x18000c0df  call    ??0CWwanHelper@@IEAA@PEAUHWND__@@PEAX@Z; CWwanHelper::CWwanHelper(HWND__ *,void *)
0x18000c0e4  jmp     short loc_18000C0E9
0x18000c0e6  mov     rax, r15
0x18000c0e9  mov     [rbx+0D0h], rax
0x18000c0f0  test    rax, rax
0x18000c0f3  jz      short loc_18000C12D
0x18000c0f5  mov     rcx, [rax+18h]
0x18000c0f9  test    rcx, rcx
0x18000c0fc  jz      short loc_18000C12D
0x18000c0fe  cmp     [rax+20h], r15
0x18000c102  jz      short loc_18000C12D
0x18000c104  mov     dword ptr [rsp+88h+var_48.Ptr], r15d
0x18000c109  lea     rdx, [rsp+88h+var_48]
0x18000c10e  mov     [rsp+88h+var_60], rdx
0x18000c113  mov     [rsp+88h+ppv], r15
0x18000c118  mov     r9, rax
0x18000c11b  lea     r8, ?WwanNotificationCallback@CWwanHelper@@KAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z; CWwanHelper::WwanNotificationCallback(_L2_NOTIFICATION_DATA *,void *)
0x18000c122  mov     edx, 2
0x18000c127  call    cs:__imp_WwanRegisterNotification
0x18000c12d  cmp     [rbx+120h], r15d
0x18000c134  jz      short loc_18000C1A5
0x18000c136  mov     rcx, rbx; this
0x18000c139  call    ?RegisterProfileEvent@CProfileMgr@@AEAAJXZ; CProfileMgr::RegisterProfileEvent(void)
0x18000c13e  mov     esi, eax
0x18000c140  test    eax, eax
0x18000c142  jns     short loc_18000C156
0x18000c144  mov     rcx, [rbx]
0x18000c147  mov     rax, [rcx+0E8h]
0x18000c14e  mov     rcx, rbx
0x18000c151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c156  mov     rcx, rbx; this
0x18000c159  call    ?RegisterNetmanEvent@CProfileMgr@@AEAAJXZ; CProfileMgr::RegisterNetmanEvent(void)
0x18000c15e  mov     edi, eax
0x18000c160  test    eax, eax
0x18000c162  jns     short loc_18000C176
0x18000c164  mov     rax, [rbx]
0x18000c167  mov     rcx, rbx
0x18000c16a  mov     rax, [rax+0F0h]
0x18000c171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c176  test    esi, esi
0x18000c178  cmovs   edi, esi
0x18000c17b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c182  cmp     rcx, r12
0x18000c185  jz      short loc_18000C1AC
0x18000c187  test    byte ptr [rcx+1Ch], 4
0x18000c18b  jz      short loc_18000C1AC
0x18000c18d  mov     edx, 11h
0x18000c192  mov     r9d, edi
0x18000c195  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000c19c  mov     rcx, [rcx+10h]
0x18000c1a0  call    WPP_SF_d
0x18000c1a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1ac  cmp     [rbx+128h], r15d
0x18000c1b3  jz      short loc_18000C1E5
0x18000c1b5  cmp     rcx, r12
0x18000c1b8  jz      short loc_18000C1DB
0x18000c1ba  test    byte ptr [rcx+1Ch], 2
0x18000c1be  jz      short loc_18000C1DB
0x18000c1c0  mov     edx, 12h
0x18000c1c5  mov     r9d, 80004005h
0x18000c1cb  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000c1d2  mov     rcx, [rcx+10h]
0x18000c1d6  call    WPP_SF_d
0x18000c1db  mov     eax, 80004005h
0x18000c1e0  jmp     loc_18000C33E
0x18000c1e5  test    edi, edi
0x18000c1e7  js      loc_18000C2D2
0x18000c1ed  mov     rcx, rbx; this
0x18000c1f0  call    ?StartServiceMonitors@CSNOCplCore@@AEAAXXZ; CSNOCplCore::StartServiceMonitors(void)
0x18000c1f5  lea     rax, [rbx+160h]
0x18000c1fc  mov     [rsp+88h+ppv], rax; ppv
0x18000c201  lea     r9, _GUID_b0a10e19_e52b_4038_bbf7_867e5e6a51fb; riid
0x18000c208  xor     edx, edx; pUnkOuter
0x18000c20a  lea     r8d, [rdx+1]; dwClsContext
0x18000c20e  lea     rcx, CLSID_HomeGroupCtrl; rclsid
0x18000c215  call    cs:__imp_CoCreateInstance
0x18000c21b  lea     rcx, [rbx+70h]; lpCriticalSection
0x18000c21f  call    cs:__imp_EnterCriticalSection
0x18000c225  mov     rcx, [rbx+98h]
0x18000c22c  call    ?ClearProfileDataMap@@YAXPEAV?$map@U_GUID@@PEAVCProfileData@@VCKey_Less@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@@Z; ClearProfileDataMap(std::map<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>> *)
0x18000c231  cmp     [rbx+120h], r15d
0x18000c238  jz      short loc_18000C24F
0x18000c23a  mov     r8, [rbx+98h]
0x18000c241  mov     rcx, rbx; this
0x18000c244  call    ?GetConnectedProfileList@CProfileMgr@@QEAAJGPEAV?$map@U_GUID@@PEAVCProfileData@@VCKey_Less@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@@Z; CProfileMgr::GetConnectedProfileList(ushort,std::map<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>> *)
0x18000c249  mov     edi, eax
0x18000c24b  test    eax, eax
0x18000c24d  js      short loc_18000C29E
0x18000c24f  cmp     [rbx+128h], r15d
0x18000c256  jnz     short loc_18000C29E
0x18000c258  mov     [rsp+88h+var_48.Ptr], rbp
0x18000c25d  mov     [rsp+88h+var_48.Size], r15d
0x18000c262  lea     rdx, [rsp+88h+var_48.Size]
0x18000c267  mov     rcx, rbp
0x18000c26a  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x18000c270  nop
0x18000c271  mov     rcx, rbx; this
0x18000c274  call    ?GetXWizardTaskInfo@CSNOCplCore@@AEAAJXZ; CSNOCplCore::GetXWizardTaskInfo(void)
0x18000c279  cmp     [rbx+128h], r15d
0x18000c280  jnz     short loc_18000C293
0x18000c282  mov     rcx, rbx; this
0x18000c285  call    ?PopulateProfileArea@CSNOCplCore@@AEAAJXZ; CSNOCplCore::PopulateProfileArea(void)
0x18000c28a  mov     rcx, rbx; this
0x18000c28d  call    ?HandleConnectivityChange@CSNOCplCore@@AEAAXXZ; CSNOCplCore::HandleConnectivityChange(void)
0x18000c292  nop
0x18000c293  lea     rcx, [rsp+88h+var_48]; this
0x18000c298  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x18000c29d  nop
0x18000c29e  lea     rcx, [rbx+70h]; lpCriticalSection
0x18000c2a2  call    cs:__imp_LeaveCriticalSection
0x18000c2a8  test    edi, edi
0x18000c2aa  js      short loc_18000C2D2
0x18000c2ac  mov     edx, 0E70h
0x18000c2b1  xor     ecx, ecx
0x18000c2b3  lea     r8d, [rcx+1]
0x18000c2b7  call    cs:__imp_WinSqmSetDWORD
0x18000c2bd  mov     r8, [r14]; __int64
0x18000c2c0  lea     rdx, ?DUI_SetSiteOnUnknown@@YAXPEAUIUnknown@@_J@Z; void (*)(struct IUnknown *, __int64)
0x18000c2c7  mov     rcx, rbp; struct DirectUI::Element *
0x18000c2ca  call    ?DUI_WalkIUnknownElements@@YAXPEAVElement@DirectUI@@P6AXPEAUIUnknown@@_J@Z2@Z; DUI_WalkIUnknownElements(DirectUI::Element *,void (*)(IUnknown *,__int64),__int64)
0x18000c2cf  mov     edi, r15d
0x18000c2d2  mov     rcx, rbx; this
0x18000c2d5  call    ?GetDeferParams@CSNOCplCore@@AEAAJXZ; CSNOCplCore::GetDeferParams(void)
0x18000c2da  mov     rdx, [rbx+100h]; HWND
0x18000c2e1  mov     rcx, rbx; void *
0x18000c2e4  call    ?HrAddNSCInstance@@YAJPEAXQEAUHWND__@@@Z; HrAddNSCInstance(void *,HWND__ * const)
0x18000c2e9  mov     dword ptr [rbx+124h], 1
0x18000c2f3  test    cs:Microsoft_Windows_Network_and_Sharing_CenterEnableBits, 2
0x18000c2fa  jz      short loc_18000C312
0x18000c2fc  lea     rax, [rsp+88h+var_48]
0x18000c301  mov     [rsp+88h+ppv], rax; PEVENT_DATA_DESCRIPTOR
0x18000c306  lea     rdx, Perf_Initialization_Page_Stop; int
0x18000c30d  call    McGenEventWrite_EventWriteTransfer
0x18000c312  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c319  cmp     rcx, r12
0x18000c31c  jz      short loc_18000C33C
0x18000c31e  test    byte ptr [rcx+1Ch], 8
0x18000c322  jz      short loc_18000C33C
0x18000c324  mov     edx, 13h
0x18000c329  mov     r9d, edi
0x18000c32c  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000c333  mov     rcx, [rcx+10h]
0x18000c337  call    WPP_SF_d
0x18000c33c  mov     eax, edi
0x18000c33e  mov     rcx, [rsp+88h+var_38]
0x18000c343  xor     rcx, rsp; StackCookie
0x18000c346  call    __security_check_cookie
0x18000c34b  lea     r11, [rsp+88h+var_28]
0x18000c350  mov     rbx, [r11+40h]
0x18000c354  mov     rbp, [r11+48h]
0x18000c358  mov     rsp, r11
0x18000c35b  pop     r15
0x18000c35d  pop     r14
0x18000c35f  pop     r12
0x18000c361  pop     rdi
0x18000c362  pop     rsi
0x18000c363  retn
```
