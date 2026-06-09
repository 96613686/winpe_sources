# CMessageWindow::v_WndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180019d98`
- end: `0x18001a4dd`
- name: `?v_WndProc@CMessageWindow@@QEAA_JPEAUHWND__@@I_K_J@Z`
- size: `1861`
- prototype: `__int64(CMessageWindow *__hidden this, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180019d20`

## callees

- `0x180002c2c`
- `0x180008a88`
- `0x1800091ec`
- `0x18000c890`
- `0x18000ea5c`
- `0x18000f85c`
- `0x180010e9c`
- `0x18001305c`
- `0x180014274`
- `0x1800158ac`
- `0x1800159c4`
- `0x180019900`
- `0x180019970`
- `0x180019d98`
- `0x18001a4e4`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a45f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a4a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a45f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a4a6`
- `SHELL32!ShellExecuteExW` at `0x18001a3d8`
- `SHELL32!ShellExecuteExW` at `0x18001a3d8`
- `USER32!GetPropW` at `0x180019dc7`
- `USER32!GetPropW` at `0x180019dc7`
- `USER32!DefWindowProcW` at `0x18001a4bd`
- `USER32!DefWindowProcW` at `0x18001a4bd`

## string_xrefs

- `0x18001a193`: `NCWM_SERVICE_NETPROFM_RUNNING`
- `0x18001a1da`: `NCWM_SERVICE_NETPROFM_STOPPED`
- `0x180019e7b`: `NCWM_SERVICE_NETMAN_RUNNING`
- `0x180019eba`: `NCWM_SERVICE_NETMAN_STOPPED`
- `0x18001a261`: `NCWM_SERVICE_WLAN_RUNNING`
- `0x180019e42`: `NCWM_SERVICE_WLAN_STOPPED`
- `0x18001a433`: `NCWM_CONNECTION_RENAMED`
- `0x180019f35`: `Event: Network deleted`
- `0x18001a003`: `Event: Signature deleted`
- `0x18001a0a6`: `Event: Signature moved`
- `0x18001a2fb`: `NCWM_NAVLINK_ENUM_ADD`
- `0x18001a2d2`: `NCWM_NAVLINK_ENUM_DONE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LRESULT __fastcall CMessageWindow::v_WndProc(
        CMessageWindow *this,
        HWND a2,
        unsigned int a3,
        const WCHAR *a4,
        struct _GUID *pv)
{
  HWND *PropW; // rbx
  __int64 v9; // r8
  __int64 v10; // r15
  UINT v11; // edx
  PVOID *v12; // rcx
  unsigned int i; // edx
  __int64 v14; // rdi
  struct _GUID *v15; // rcx
  struct _GUID *v16; // rdi
  _BYTE v18[12]; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+2Ch] [rbp-D4h]
  _DWORD v20[2]; // [rsp+30h] [rbp-D0h]
  const char *v21; // [rsp+38h] [rbp-C8h]
  void (__fastcall *v22)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+40h] [rbp-C0h]
  _DWORD v23[4]; // [rsp+48h] [rbp-B8h]
  const char *v24; // [rsp+58h] [rbp-A8h]
  void (__fastcall *v25)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+60h] [rbp-A0h]
  int v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+6Ch] [rbp-94h]
  int v28; // [rsp+70h] [rbp-90h]
  const char *v29; // [rsp+78h] [rbp-88h]
  void (__fastcall *v30)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+80h] [rbp-80h]
  int v31; // [rsp+88h] [rbp-78h]
  int v32; // [rsp+8Ch] [rbp-74h]
  int v33; // [rsp+90h] [rbp-70h]
  const char *v34; // [rsp+98h] [rbp-68h]
  void (__fastcall *v35)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+A0h] [rbp-60h]
  int v36; // [rsp+A8h] [rbp-58h]
  int v37; // [rsp+ACh] [rbp-54h]
  int v38; // [rsp+B0h] [rbp-50h]
  const char *v39; // [rsp+B8h] [rbp-48h]
  void (__fastcall *v40)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C8h] [rbp-38h]
  int v42; // [rsp+CCh] [rbp-34h]
  int v43; // [rsp+D0h] [rbp-30h]
  const char *v44; // [rsp+D8h] [rbp-28h]
  void (__fastcall *v45)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+E0h] [rbp-20h]
  int v46; // [rsp+E8h] [rbp-18h]
  int v47; // [rsp+ECh] [rbp-14h]
  int v48; // [rsp+F0h] [rbp-10h]
  const char *v49; // [rsp+F8h] [rbp-8h]
  void (__fastcall *v50)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+100h] [rbp+0h]
  int v51; // [rsp+108h] [rbp+8h]
  int v52; // [rsp+10Ch] [rbp+Ch]
  int v53; // [rsp+110h] [rbp+10h]
  const char *v54; // [rsp+118h] [rbp+18h]
  void (__fastcall *v55)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+120h] [rbp+20h]
  int v56; // [rsp+128h] [rbp+28h]
  int v57; // [rsp+12Ch] [rbp+2Ch]
  int v58; // [rsp+130h] [rbp+30h]
  const char *v59; // [rsp+138h] [rbp+38h]
  void (__fastcall *v60)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+140h] [rbp+40h]
  int v61; // [rsp+148h] [rbp+48h]
  int v62; // [rsp+14Ch] [rbp+4Ch]
  int v63; // [rsp+150h] [rbp+50h]
  const char *v64; // [rsp+158h] [rbp+58h]
  void (__fastcall *v65)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+160h] [rbp+60h]
  int v66; // [rsp+168h] [rbp+68h]
  int v67; // [rsp+16Ch] [rbp+6Ch]
  int v68; // [rsp+170h] [rbp+70h]
  const char *v69; // [rsp+178h] [rbp+78h]
  void (__fastcall *v70)(CSNOCplCore *__hidden, struct tagNETPROFILE_EVENT_DATA *const); // [rsp+180h] [rbp+80h]
  int v71; // [rsp+188h] [rbp+88h]
  int v72; // [rsp+18Ch] [rbp+8Ch]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+190h] [rbp+90h] BYREF

  PropW = (HWND *)GetPropW(a2, L"_Netcenter_ptr");
  if ( !PropW )
    goto LABEL_71;
  v10 = 0;
  if ( a3 > 0x8007 )
  {
    switch ( a3 )
    {
      case 0x8008u:
        v16 = pv;
        if ( !*((_DWORD *)PropW + 62) )
        {
          CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_WLAN_SIGNAL_CHANGE");
          CSNOCplCore::UpdateSignalStrength((CSNOCplCore *)PropW, pv, pv[1].Data1);
          goto LABEL_68;
        }
        break;
      case 0x800Du:
        v16 = pv;
        if ( !*((_DWORD *)PropW + 62) )
        {
          CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_CONNECTION_RENAMED");
          CSNOCplCore::OnWMConnectionRenamed((CSNOCplCore *)PropW, (struct tagNETCONNNAMEDATA *const)pv);
          CTraceWrapper::~CTraceWrapper((CTraceWrapper *)v18);
        }
        CoTaskMemFree(*(LPVOID *)pv[1].Data4);
        break;
      case 0x800Eu:
        if ( *((_DWORD *)PropW + 62) )
          return v10;
        CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_REFRESH");
        CSNOCplCore::Refresh((CSNOCplCore *)PropW);
        goto LABEL_40;
      case 0x800Fu:
        if ( !*((_DWORD *)PropW + 62) )
        {
          CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_NAVIGATE");
          memset_0(&pExecInfo, 0, sizeof(pExecInfo));
          pExecInfo.cbSize = 112;
          pExecInfo.fMask = 512;
          pExecInfo.hwnd = PropW[42];
          pExecInfo.lpFile = a4;
          pExecInfo.nShow = 1;
          if ( !ShellExecuteExW(&pExecInfo) )
            ResultFromKnownLastError();
          CTraceWrapper::~CTraceWrapper((CTraceWrapper *)v18);
        }
LABEL_32:
        v15 = (struct _GUID *)a4;
LABEL_70:
        CoTaskMemFree(v15);
        return v10;
      case 0x8010u:
        v16 = pv;
        if ( !*((_DWORD *)PropW + 62) )
        {
          CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_WWAN_SIGNAL_CHANGE");
          CSNOCplCore::UpdateSignalStrength((CSNOCplCore *)PropW, pv, pv[1].Data1);
LABEL_68:
          CTraceWrapper::~CTraceWrapper((CTraceWrapper *)v18);
        }
        break;
      case 0x8011u:
        if ( !*((_DWORD *)PropW + 62) )
        {
          CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_NAVLINK_ENUM_ADD");
          CSNOCplCore::AddNavLink((CSNOCplCore *)PropW, (const struct NAVLINK_INFO *)pv);
          CTraceWrapper::~CTraceWrapper((CTraceWrapper *)v18);
        }
        v15 = pv;
        goto LABEL_70;
      case 0x8012u:
        if ( *((_DWORD *)PropW + 62) )
          return v10;
        CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_NAVLINK_ENUM_DONE");
        CSNOCplCore::CommitNavLinks((CSNOCplCore *)PropW);
        goto LABEL_40;
      default:
LABEL_71:
        v11 = a3;
        return DefWindowProcW(a2, v11, (WPARAM)a4, (LPARAM)pv);
    }
    v15 = v16;
    goto LABEL_70;
  }
  if ( a3 == 32775 )
  {
    if ( *((_DWORD *)PropW + 62) )
      return v10;
    CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_SERVICE_WLAN_RUNNING");
    CWlanHelper::RegisterWLANEvent(PropW + 23);
    CSNOCplCore::Refresh((CSNOCplCore *)PropW);
    goto LABEL_40;
  }
  v11 = 275;
  switch ( a3 )
  {
    case 0x113u:
      if ( a4 == (const WCHAR *)120 )
      {
        if ( !*((_DWORD *)PropW + 62) )
        {
          CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "WM_TIMER");
          CSNOCplCore::KillDeferTimerAndRefreshNetworkList((CSNOCplCore *)PropW, 1);
          goto LABEL_40;
        }
        return v10;
      }
      return DefWindowProcW(a2, v11, (WPARAM)a4, (LPARAM)pv);
    case 0x8001u:
      if ( !*((_DWORD *)PropW + 62) )
      {
        CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_SERVICE_NETPROFM_STOPPED");
        (*((void (__fastcall **)(HWND *))*PropW + 29))(PropW);
        *((_DWORD *)PropW + 72) = 0;
        CSNOCplCore::Refresh((CSNOCplCore *)PropW);
        goto LABEL_40;
      }
      return v10;
    case 0x8002u:
      if ( !*((_DWORD *)PropW + 62) )
      {
        CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_SERVICE_NETPROFM_RUNNING");
        *((_DWORD *)PropW + 72) = (*((int (__fastcall **)(HWND *))*PropW + 31))(PropW) >= 0;
        CSNOCplCore::Refresh((CSNOCplCore *)PropW);
        goto LABEL_40;
      }
      return v10;
    case 0x8003u:
      a4 = (const WCHAR *)pv;
      if ( !*((_DWORD *)PropW + 62) )
      {
        v20[0] = 1;
        v21 = "Event: Network added";
        v22 = CSNOCplCore::OnWMProfileAdded;
        v23[0] = 0;
        v23[1] = v19;
        v23[2] = 2;
        v24 = "Event: Network deleted";
        v25 = CSNOCplCore::OnWMProfileDeleted;
        v26 = 0;
        v27 = v19;
        v28 = 3;
        v29 = "Event: Network connected";
        v30 = CSNOCplCore::OnWMProfileConnected;
        v31 = 0;
        v32 = v19;
        v33 = 4;
        v34 = "Event: Network disconnected";
        v35 = CSNOCplCore::OnWMProfileDisconnected;
        v36 = 0;
        v37 = v19;
        v38 = 5;
        v39 = "Event: Network property change";
        v40 = CSNOCplCore::OnWMProfilePropertyChange;
        v41 = 0;
        v42 = v19;
        v43 = 6;
        v44 = "Event: Signature added";
        v45 = CSNOCplCore::OnWMSignatureAdded;
        v46 = 0;
        v47 = v19;
        v48 = 7;
        v49 = "Event: Signature deleted";
        v50 = CSNOCplCore::OnWMSignatureDeleted;
        v51 = 0;
        v52 = v19;
        v53 = 8;
        v54 = "Event: Signature connected";
        v55 = CSNOCplCore::OnWMSignatureConnected;
        v56 = 0;
        v57 = v19;
        v58 = 9;
        v59 = "Event: Signature disconnected";
        v60 = CSNOCplCore::OnWMSignatureDisconnected;
        v61 = 0;
        v62 = v19;
        v63 = 10;
        v64 = "Event: Signature property change";
        v65 = CSNOCplCore::OnWMSignaturePropertyChange;
        v66 = 0;
        v67 = v19;
        v68 = 11;
        v69 = "Event: Signature moved";
        v70 = CSNOCplCore::OnWMSignatureMoved;
        v71 = 0;
        v72 = v19;
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_31aceb967a8f36dcbf14b86f9200de5a_Traceguids, pv->Data1);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        for ( i = 0; i < 0xB; ++i )
        {
          v14 = 8LL * i;
          if ( pv->Data1 == v20[v14] )
          {
            if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
              WPP_SF_s(v12[2], 14, v9, (&v21)[4 * i]);
            (*(void (__fastcall **)(char *, struct _GUID *))&v23[v14 - 2])(
              (CSNOCplCore *)((char *)PropW + (int)v23[v14]),
              (struct tagNETPROFILE_EVENT_DATA *const)pv);
            v12 = (PVOID *)WPP_GLOBAL_Control;
            break;
          }
        }
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
          WPP_SF_d(v12[2], 15, &WPP_31aceb967a8f36dcbf14b86f9200de5a_Traceguids, pv->Data1);
      }
      goto LABEL_32;
    case 0x8004u:
      if ( !*((_DWORD *)PropW + 62) )
      {
        CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_SERVICE_NETMAN_STOPPED");
        (*((void (__fastcall **)(HWND *))*PropW + 33))(PropW);
        CSNOCplCore::Refresh((CSNOCplCore *)PropW);
        goto LABEL_40;
      }
      return v10;
  }
  if ( a3 != 32773 )
  {
    if ( a3 == 32774 )
    {
      if ( !*((_DWORD *)PropW + 62) )
      {
        CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_SERVICE_WLAN_STOPPED");
        CWlanHelper::UnregisterWLANEvent(PropW + 23);
        CSNOCplCore::Refresh((CSNOCplCore *)PropW);
LABEL_40:
        CTraceWrapper::~CTraceWrapper((CTraceWrapper *)v18);
        return v10;
      }
      return v10;
    }
    goto LABEL_71;
  }
  if ( !*((_DWORD *)PropW + 62) )
  {
    CTraceWrapper::CTraceWrapper((CTraceWrapper *)v18, "NCWM_SERVICE_NETMAN_RUNNING");
    (*((void (__fastcall **)(HWND *))*PropW + 32))(PropW);
    CSNOCplCore::Refresh((CSNOCplCore *)PropW);
    goto LABEL_40;
  }
  return v10;
}

```

## disassembly

```asm
0x180019d98  push    rbp
0x180019d9a  push    rbx
0x180019d9b  push    rsi
0x180019d9c  push    rdi
0x180019d9d  push    r12
0x180019d9f  push    r13
0x180019da1  push    r14
0x180019da3  push    r15
0x180019da5  lea     rbp, [rsp-108h]
0x180019dad  sub     rsp, 208h
0x180019db4  mov     rsi, r9
0x180019db7  mov     edi, r8d
0x180019dba  mov     r14, rdx
0x180019dbd  lea     rdx, String; "_Netcenter_ptr"
0x180019dc4  mov     rcx, r14; hWnd
0x180019dc7  call    cs:__imp_GetPropW
0x180019dcd  mov     rbx, rax
0x180019dd0  xor     r12d, r12d
0x180019dd3  test    rax, rax
0x180019dd6  jz      loc_18001A4AE
0x180019ddc  mov     r15d, r12d
0x180019ddf  mov     eax, 8007h
0x180019de4  cmp     edi, eax
0x180019de6  ja      loc_18001A28A
0x180019dec  jz      loc_18001A254
0x180019df2  mov     eax, edi
0x180019df4  mov     edx, 113h
0x180019df9  sub     eax, edx
0x180019dfb  jz      loc_18001A210
0x180019e01  sub     eax, 7EEEh
0x180019e06  jz      loc_18001A1CD
0x180019e0c  sub     eax, 1
0x180019e0f  jz      loc_18001A186
0x180019e15  sub     eax, 1
0x180019e18  jz      loc_180019EEC
0x180019e1e  sub     eax, 1
0x180019e21  jz      loc_180019EAD
0x180019e27  sub     eax, 1
0x180019e2a  jz      short loc_180019E6E
0x180019e2c  cmp     eax, 1
0x180019e2f  jnz     loc_18001A4AE
0x180019e35  cmp     [rbx+0F8h], r12d
0x180019e3c  jnz     loc_18001A4C6
0x180019e42  lea     rdx, aNcwmServiceWla_0; "NCWM_SERVICE_WLAN_STOPPED"
0x180019e49  lea     rcx, [rsp+240h+var_220]; this
0x180019e4e  call    ??0CTraceWrapper@@QEAA@PEBD@Z; CTraceWrapper::CTraceWrapper(char const *)
0x180019e53  nop
0x180019e54  lea     rcx, [rbx+0B8h]; pCallbackContext
0x180019e5b  call    ?UnregisterWLANEvent@CWlanHelper@@QEAAJXZ; CWlanHelper::UnregisterWLANEvent(void)
0x180019e60  mov     rcx, rbx; this
0x180019e63  call    ?Refresh@CSNOCplCore@@AEAAJXZ; CSNOCplCore::Refresh(void)
0x180019e68  nop
0x180019e69  jmp     loc_18001A245
0x180019e6e  cmp     [rbx+0F8h], r12d
0x180019e75  jnz     loc_18001A4C6
0x180019e7b  lea     rdx, aNcwmServiceNet_0; "NCWM_SERVICE_NETMAN_RUNNING"
0x180019e82  lea     rcx, [rsp+240h+var_220]; this
0x180019e87  call    ??0CTraceWrapper@@QEAA@PEBD@Z; CTraceWrapper::CTraceWrapper(char const *)
0x180019e8c  nop
0x180019e8d  mov     rax, [rbx]
0x180019e90  mov     rcx, rbx
0x180019e93  mov     rax, [rax+100h]
0x180019e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e9f  mov     rcx, rbx; this
0x180019ea2  call    ?Refresh@CSNOCplCore@@AEAAJXZ; CSNOCplCore::Refresh(void)
0x180019ea7  nop
0x180019ea8  jmp     loc_18001A245
0x180019ead  cmp     [rbx+0F8h], r12d
0x180019eb4  jnz     loc_18001A4C6
0x180019eba  lea     rdx, aNcwmServiceNet_2; "NCWM_SERVICE_NETMAN_STOPPED"
0x180019ec1  lea     rcx, [rsp+240h+var_220]; this
0x180019ec6  call    ??0CTraceWrapper@@QEAA@PEBD@Z; CTraceWrapper::CTraceWrapper(char const *)
0x180019ecb  nop
0x180019ecc  mov     rax, [rbx]
0x180019ecf  mov     rcx, rbx
0x180019ed2  mov     rax, [rax+108h]
0x180019ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ede  mov     rcx, rbx; this
0x180019ee1  call    ?Refresh@CSNOCplCore@@AEAAJXZ; CSNOCplCore::Refresh(void)
0x180019ee6  nop
0x180019ee7  jmp     loc_18001A245
0x180019eec  mov     rsi, [rbp+140h+pv]
0x180019ef3  cmp     [rbx+0F8h], r12d
0x180019efa  jnz     loc_18001A17E
0x180019f00  mov     [rsp+240h+var_210], 1
0x180019f08  lea     rax, aEventNetworkAd; "Event: Network added"
0x180019f0f  mov     [rsp+240h+var_208], rax
0x180019f14  lea     rax, ?OnWMProfileAdded@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMProfileAdded(tagNETPROFILE_EVENT_DATA * const)
0x180019f1b  mov     [rsp+240h+var_200], rax
0x180019f20  mov     [rsp+240h+var_1F8], r12d
0x180019f25  mov     eax, [rsp+240h+var_214]
0x180019f29  mov     [rsp+240h+var_1F4], eax
0x180019f2d  mov     [rsp+240h+var_1F0], 2
0x180019f35  lea     rax, aEventNetworkDe; "Event: Network deleted"
0x180019f3c  mov     [rsp+240h+var_1E8], rax
0x180019f41  lea     rax, ?OnWMProfileDeleted@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMProfileDeleted(tagNETPROFILE_EVENT_DATA * const)
0x180019f48  mov     [rsp+240h+var_1E0], rax
0x180019f4d  mov     [rsp+240h+var_1D8], r12d
0x180019f52  mov     eax, [rsp+240h+var_214]
0x180019f56  mov     [rsp+240h+var_1D4], eax
0x180019f5a  mov     [rsp+240h+var_1D0], 3
0x180019f62  lea     rax, aEventNetworkCo; "Event: Network connected"
0x180019f69  mov     [rsp+240h+var_1C8], rax
0x180019f6e  lea     rax, ?OnWMProfileConnected@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMProfileConnected(tagNETPROFILE_EVENT_DATA * const)
0x180019f75  mov     [rbp+140h+var_1C0], rax
0x180019f79  mov     [rbp+140h+var_1B8], r12d
0x180019f7d  mov     eax, [rsp+240h+var_214]
0x180019f81  mov     [rbp+140h+var_1B4], eax
0x180019f84  mov     [rbp+140h+var_1B0], 4
0x180019f8b  lea     rax, aEventNetworkDi; "Event: Network disconnected"
0x180019f92  mov     [rbp+140h+var_1A8], rax
0x180019f96  lea     rax, ?OnWMProfileDisconnected@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMProfileDisconnected(tagNETPROFILE_EVENT_DATA * const)
0x180019f9d  mov     [rbp+140h+var_1A0], rax
0x180019fa1  mov     [rbp+140h+var_198], r12d
0x180019fa5  mov     eax, [rsp+240h+var_214]
0x180019fa9  mov     [rbp+140h+var_194], eax
0x180019fac  mov     [rbp+140h+var_190], 5
0x180019fb3  lea     rax, aEventNetworkPr; "Event: Network property change"
0x180019fba  mov     [rbp+140h+var_188], rax
0x180019fbe  lea     rax, ?OnWMProfilePropertyChange@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMProfilePropertyChange(tagNETPROFILE_EVENT_DATA * const)
0x180019fc5  mov     [rbp+140h+var_180], rax
0x180019fc9  mov     [rbp+140h+var_178], r12d
0x180019fcd  mov     eax, [rsp+240h+var_214]
0x180019fd1  mov     [rbp+140h+var_174], eax
0x180019fd4  mov     [rbp+140h+var_170], 6
0x180019fdb  lea     rax, aEventSignature_2; "Event: Signature added"
0x180019fe2  mov     [rbp+140h+var_168], rax
0x180019fe6  lea     rax, ?OnWMSignatureAdded@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMSignatureAdded(tagNETPROFILE_EVENT_DATA * const)
0x180019fed  mov     [rbp+140h+var_160], rax
0x180019ff1  mov     [rbp+140h+var_158], r12d
0x180019ff5  mov     eax, [rsp+240h+var_214]
0x180019ff9  mov     [rbp+140h+var_154], eax
0x180019ffc  mov     [rbp+140h+var_150], 7
0x18001a003  lea     rax, aEventSignature; "Event: Signature deleted"
0x18001a00a  mov     [rbp+140h+var_148], rax
0x18001a00e  lea     rax, ?OnWMSignatureDeleted@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMSignatureDeleted(tagNETPROFILE_EVENT_DATA * const)
0x18001a015  mov     [rbp+140h+var_140], rax
0x18001a019  mov     [rbp+140h+var_138], r12d
0x18001a01d  mov     eax, [rsp+240h+var_214]
0x18001a021  mov     [rbp+140h+var_134], eax
0x18001a024  mov     r14d, 8
0x18001a02a  mov     [rbp+140h+var_130], r14d
0x18001a02e  lea     rax, aEventSignature_0; "Event: Signature connected"
0x18001a035  mov     [rbp+140h+var_128], rax
0x18001a039  lea     rax, ?OnWMSignatureConnected@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMSignatureConnected(tagNETPROFILE_EVENT_DATA * const)
0x18001a040  mov     [rbp+140h+var_120], rax
0x18001a044  mov     [rbp+140h+var_118], r12d
0x18001a048  mov     eax, [rsp+240h+var_214]
0x18001a04c  mov     [rbp+140h+var_114], eax
0x18001a04f  mov     [rbp+140h+var_110], 9
0x18001a056  lea     rax, aEventSignature_4; "Event: Signature disconnected"
0x18001a05d  mov     [rbp+140h+var_108], rax
0x18001a061  lea     rax, ?OnWMSignatureDisconnected@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMSignatureDisconnected(tagNETPROFILE_EVENT_DATA * const)
0x18001a068  mov     [rbp+140h+var_100], rax
0x18001a06c  mov     [rbp+140h+var_F8], r12d
0x18001a070  mov     eax, [rsp+240h+var_214]
0x18001a074  mov     [rbp+140h+var_F4], eax
0x18001a077  mov     [rbp+140h+var_F0], 0Ah
0x18001a07e  lea     rax, aEventSignature_3; "Event: Signature property change"
0x18001a085  mov     [rbp+140h+var_E8], rax
0x18001a089  lea     rax, ?OnWMSignaturePropertyChange@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMSignaturePropertyChange(tagNETPROFILE_EVENT_DATA * const)
0x18001a090  mov     [rbp+140h+var_E0], rax
0x18001a094  mov     [rbp+140h+var_D8], r12d
0x18001a098  mov     eax, [rsp+240h+var_214]
0x18001a09c  mov     [rbp+140h+var_D4], eax
0x18001a09f  mov     [rbp+140h+var_D0], 0Bh
0x18001a0a6  lea     rax, aEventSignature_1; "Event: Signature moved"
0x18001a0ad  mov     [rbp+140h+var_C8], rax
0x18001a0b1  lea     rax, ?OnWMSignatureMoved@CSNOCplCore@@QEAAXQEAUtagNETPROFILE_EVENT_DATA@@@Z; CSNOCplCore::OnWMSignatureMoved(tagNETPROFILE_EVENT_DATA * const)
0x18001a0b8  mov     [rbp+140h+var_C0], rax
0x18001a0bf  mov     [rbp+140h+var_B8], r12d
0x18001a0c6  mov     eax, [rsp+240h+var_214]
0x18001a0ca  mov     [rbp+140h+var_B4], eax
0x18001a0d0  lea     r13, WPP_GLOBAL_Control
0x18001a0d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0de  cmp     rcx, r13
0x18001a0e1  jz      short loc_18001A107
0x18001a0e3  test    [rcx+1Ch], r14b
0x18001a0e7  jz      short loc_18001A107
0x18001a0e9  lea     edx, [r14+5]
0x18001a0ed  mov     r9d, [rsi]
0x18001a0f0  lea     r8, WPP_31aceb967a8f36dcbf14b86f9200de5a_Traceguids
0x18001a0f7  mov     rcx, [rcx+10h]
0x18001a0fb  call    WPP_SF_d
0x18001a100  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a107  mov     edx, r12d
0x18001a10a  cmp     edx, 0Bh
0x18001a10d  jnb     short loc_18001A15B
0x18001a10f  mov     edi, edx
0x18001a111  shl     rdi, 5
0x18001a115  mov     eax, [rsp+rdi+240h+var_210]
0x18001a119  cmp     [rsi], eax
0x18001a11b  jz      short loc_18001A121
0x18001a11d  inc     edx
0x18001a11f  jmp     short loc_18001A10A
0x18001a121  cmp     rcx, r13
0x18001a124  jz      short loc_18001A13F
0x18001a126  test    [rcx+1Ch], r14b
0x18001a12a  jz      short loc_18001A13F
0x18001a12c  mov     edx, 0Eh
0x18001a131  mov     r9, [rsp+rdi+240h+var_208]
0x18001a136  mov     rcx, [rcx+10h]
0x18001a13a  call    WPP_SF_s
0x18001a13f  movsxd  rcx, [rsp+rdi+240h+var_1F8]
0x18001a144  add     rcx, rbx
0x18001a147  mov     rdx, rsi
0x18001a14a  mov     rax, [rsp+rdi+240h+var_200]
0x18001a14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a154  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a15b  cmp     rcx, r13
0x18001a15e  jz      short loc_18001A17E
0x18001a160  test    [rcx+1Ch], r14b
0x18001a164  jz      short loc_18001A17E
0x18001a166  mov     edx, 0Fh
0x18001a16b  mov     r9d, [rsi]
0x18001a16e  lea     r8, WPP_31aceb967a8f36dcbf14b86f9200de5a_Traceguids
0x18001a175  mov     rcx, [rcx+10h]
0x18001a179  call    WPP_SF_d
0x18001a17e  mov     rcx, rsi
0x18001a181  jmp     loc_18001A4A6
0x18001a186  cmp     [rbx+0F8h], r12d
0x18001a18d  jnz     loc_18001A4C6
0x18001a193  lea     rdx, aNcwmServiceNet; "NCWM_SERVICE_NETPROFM_RUNNING"
0x18001a19a  lea     rcx, [rsp+240h+var_220]; this
0x18001a19f  call    ??0CTraceWrapper@@QEAA@PEBD@Z; CTraceWrapper::CTraceWrapper(char const *)
0x18001a1a4  nop
0x18001a1a5  mov     rax, [rbx]
0x18001a1a8  mov     rcx, rbx
0x18001a1ab  mov     rax, [rax+0F8h]
0x18001a1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1b7  not     eax
0x18001a1b9  shr     eax, 1Fh
0x18001a1bc  mov     [rbx+120h], eax
0x18001a1c2  mov     rcx, rbx; this
0x18001a1c5  call    ?Refresh@CSNOCplCore@@AEAAJXZ; CSNOCplCore::Refresh(void)
0x18001a1ca  nop
0x18001a1cb  jmp     short loc_18001A245
0x18001a1cd  cmp     [rbx+0F8h], r12d
0x18001a1d4  jnz     loc_18001A4C6
0x18001a1da  lea     rdx, aNcwmServiceNet_1; "NCWM_SERVICE_NETPROFM_STOPPED"
0x18001a1e1  lea     rcx, [rsp+240h+var_220]; this
0x18001a1e6  call    ??0CTraceWrapper@@QEAA@PEBD@Z; CTraceWrapper::CTraceWrapper(char const *)
0x18001a1eb  nop
0x18001a1ec  mov     rax, [rbx]
0x18001a1ef  mov     rcx, rbx
0x18001a1f2  mov     rax, [rax+0E8h]
0x18001a1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1fe  mov     [rbx+120h], r12d
0x18001a205  mov     rcx, rbx; this
0x18001a208  call    ?Refresh@CSNOCplCore@@AEAAJXZ; CSNOCplCore::Refresh(void)
0x18001a20d  nop
0x18001a20e  jmp     short loc_18001A245
0x18001a210  cmp     rsi, 78h ; 'x'
0x18001a214  jnz     loc_18001A4B0
0x18001a21a  cmp     [rbx+0F8h], r12d
0x18001a221  jnz     loc_18001A4C6
0x18001a227  lea     rdx, aWmTimer; "WM_TIMER"
0x18001a22e  lea     rcx, [rsp+240h+var_220]; this
0x18001a233  call    ??0CTraceWrapper@@QEAA@PEBD@Z; CTraceWrapper::CTraceWrapper(char const *)
0x18001a238  nop
0x18001a239  lea     edx, [rsi-77h]; int
0x18001a23c  mov     rcx, rbx; this
0x18001a23f  call    ?KillDeferTimerAndRefreshNetworkList@CSNOCplCore@@AEAAXH@Z; CSNOCplCore::KillDeferTimerAndRefreshNetworkList(int)
0x18001a244  nop
0x18001a245  lea     rcx, [rsp+240h+var_220]; this
0x18001a24a  call    ??1CTraceWrapper@@UEAA@XZ; CTraceWrapper::~CTraceWrapper(void)
0x18001a24f  jmp     loc_18001A4C6
0x18001a254  cmp     [rbx+0F8h], r12d
0x18001a25b  jnz     loc_18001A4C6
0x18001a261  lea     rdx, aNcwmServiceWla; "NCWM_SERVICE_WLAN_RUNNING"
0x18001a268  lea     rcx, [rsp+240h+var_220]; this
0x18001a26d  call    ??0CTraceWrapper@@QEAA@PEBD@Z; CTraceWrapper::CTraceWrapper(char const *)
0x18001a272  nop
0x18001a273  lea     rcx, [rbx+0B8h]; pCallbackContext
0x18001a27a  call    ?RegisterWLANEvent@CWlanHelper@@QEAAJXZ; CWlanHelper::RegisterWLANEvent(void)
0x18001a27f  mov     rcx, rbx; this
0x18001a282  call    ?Refresh@CSNOCplCore@@AEAAJXZ; CSNOCplCore::Refresh(void)
0x18001a287  nop
0x18001a288  jmp     short loc_18001A245
0x18001a28a  mov     eax, edi
0x18001a28c  sub     eax, 8008h
0x18001a291  jz      loc_18001A467
0x18001a297  sub     eax, 5
0x18001a29a  jz      loc_18001A423
0x18001a2a0  sub     eax, 1
0x18001a2a3  jz      loc_18001A3F6
0x18001a2a9  sub     eax, 1
0x18001a2ac  jz      loc_18001A36E
0x18001a2b2  sub     eax, 1
0x18001a2b5  jz      short loc_18001A333
0x18001a2b7  sub     eax, 1
0x18001a2ba  jz      short loc_18001A2F2
0x18001a2bc  cmp     eax, 1
0x18001a2bf  jnz     loc_18001A4AE
0x18001a2c5  cmp     [rbx+0F8h], r12d
0x18001a2cc  jnz     loc_18001A4C6
0x18001a2d2  lea     rdx, aNcwmNavlinkEnu; "NCWM_NAVLINK_ENUM_DONE"
0x18001a2d9  lea     rcx, [rsp+240h+var_220]; this
0x18001a2de  call    ??0CTraceWrapper@@QEAA@PEBD@Z; CTraceWrapper::CTraceWrapper(char const *)
0x18001a2e3  nop
  ... truncated ...
```
