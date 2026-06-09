# CTabWindow::_LaunchNewTabThread(tagIE8_THREADPARAM *,tagTABWINDOWDATA *,_EARLYSTART_DATA *)

- ea: `0x18027f19c`
- end: `0x18027fffa`
- name: `?_LaunchNewTabThread@CTabWindow@@AEAAJPEAUtagIE8_THREADPARAM@@PEAUtagTABWINDOWDATA@@PEAU_EARLYSTART_DATA@@@Z`
- size: `3678`
- prototype: `__int64 __fastcall(CTabWindow *__hidden this, struct tagIE8_THREADPARAM *, struct tagTABWINDOWDATA *, struct _EARLYSTART_DATA *)`
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180273cc4`

## callees

- `0x180005030`
- `0x1800144d0`
- `0x18001d0b0`
- `0x180024bc4`
- `0x180069118`
- `0x180086b60`
- `0x180094450`
- `0x18009ce20`
- `0x1801cae6c`
- `0x1801caff4`
- `0x1801cfe54`
- `0x1801d1024`
- `0x1801ef0dc`
- `0x180226550`
- `0x180269bc8`
- `0x180269bec`
- `0x18026a554`
- `0x18026f9d0`
- `0x180271fe8`
- `0x180273330`
- `0x180278950`
- `0x18027a284`
- `0x18027b51c`
- `0x18027f034`
- `0x18027f0bc`
- `0x18027f19c`
- `0x180282ad4`
- `0x1802835fc`
- `0x1802a6ca8`
- `0x180426040`
- `0x18042bfbc`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18027fe50`
- `KERNEL32!GetCurrentProcessId` at `0x18027fe50`
- `iertutil!__imp_IEIsScriptDebuggingEnabled` at `0x18027f7e0`
- `iertutil!__imp_IEIsScriptDebuggingEnabled` at `0x18027f7e0`
- `iertutil!__imp_?IEGetThreadRef@@YAJPEAPEAUIUnknown@@@Z` at `0x18027f9ba`
- `iertutil!__imp_?IEGetThreadRef@@YAJPEAPEAUIUnknown@@@Z` at `0x18027f9ba`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18027fd55`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18027fd55`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18027fd65`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18027fd65`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18027f3e8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18027fe00`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18027f3e8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18027fe00`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x18027fd79`
- `api-ms-win-downlevel-shell32-l1-1-0!GetCurrentProcessExplicitAppUserModelID` at `0x18027fd79`
- `msIso!__imp_?LCIECreateAndInitThreadRef@@YAJPEAUIUnknown@@PEAPEAUILCIEThreadRef@@@Z` at `0x18027f9ce`
- `msIso!__imp_?LCIECreateAndInitThreadRef@@YAJPEAUIUnknown@@PEAPEAUILCIEThreadRef@@@Z` at `0x18027f9ce`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x18027fa60`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x18027faf4`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x18027fb6d`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x18027fa60`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x18027faf4`
- `msIso!__imp_?LCIEMarshalInterfaceIntoBufferForHandle@@YAJKKAEBU_GUID@@PEAUIUnknown@@PEAE_KPEFAK@Z` at `0x18027fb6d`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18027ff23`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18027ff5c`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18027ff98`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18027ff23`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18027ff5c`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18027ff98`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18027fd07`
- `msIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18027fd07`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18027f923`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18027f923`
- `msIso!__imp_?LCIEForceSecurityProxiesFromFlags@@YAHK@Z` at `0x18027f7a0`
- `msIso!__imp_?LCIEForceSecurityProxiesFromFlags@@YAHK@Z` at `0x18027f7a0`
- `msIso!__imp_?IsoLockArtifact@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18027fca5`
- `msIso!__imp_?IsoLockArtifact@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x18027fca5`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18027fcc7`
- `msIso!__imp_?IsoUnlockArtifact@@YAJK@Z` at `0x18027fcc7`
- `msIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z` at `0x18027f955`
- `msIso!__imp_?IsoAllocSharedMemoryPerFlags@@YAJKPEAKKPEAPEAX@Z` at `0x18027f955`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x18027ffb6`
- `msIso!__imp_?IsoFreeSharedMemory@@YAJK@Z` at `0x18027ffb6`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x18027f8e3`
- `msIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x18027f8e3`
- `msIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x18027fdc9`
- `msIso!__imp_?IsoCreateComponentByCreDat@@YAJKPEAU_IsoCreationComponentData@@PEBGPEAK22PEAU_IsoWindowsContainer@@PEA_KW4IsoCreationFailureTreatment@@@Z` at `0x18027fdc9`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18027f908`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18027f908`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x18027fdf0`
- `msIso!__imp_?IsoRemoveDependency@@YAJ_K@Z` at `0x18027fdf0`
- `urlmon!__imp_CoInternetIsExtensionsOff` at `0x18027f7ce`
- `urlmon!__imp_CoInternetIsExtensionsOff` at `0x18027f7ce`

## pseudocode

```c
__int64 __fastcall CTabWindow::_LaunchNewTabThread(
        CTabWindow *this,
        struct tagIE8_THREADPARAM *a2,
        struct tagTABWINDOWDATA *a3,
        struct _EARLYSTART_DATA *a4)
{
  struct tagTABWINDOWDATA *v4; // r15
  int v8; // ecx
  struct _ITEMIDLIST_ABSOLUTE *v9; // rcx
  HRESULT FrameTabWindow; // ebx
  unsigned int v11; // r13d
  _BYTE *v12; // r12
  _QWORD *v13; // rbx
  bool v14; // zf
  __int64 v15; // rcx
  char v16; // r12
  __int64 v17; // rcx
  int v18; // r15d
  char *v19; // rdx
  void *v20; // rcx
  int (__fastcall ***v21)(_QWORD, GUID *, struct ITravelLogRecoveryData **); // rcx
  __int64 v22; // rdx
  struct ITravelLogRecoveryData *v23; // rcx
  __int64 v24; // rdx
  struct ITravelLogRecoveryData *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  unsigned int v29; // r15d
  unsigned int v30; // r12d
  __int64 v31; // rcx
  int v32; // eax
  int v33; // r13d
  bool v34; // al
  __int64 v35; // rcx
  unsigned int v36; // r8d
  struct IUnknown **v37; // r12
  struct IUnknown *v38; // r9
  unsigned int v39; // r12d
  struct IUnknown *v40; // r9
  struct IUnknown *v41; // r9
  unsigned int v42; // eax
  unsigned int v43; // edx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  __int128 v46; // xmm1
  int v47; // eax
  char *v49; // [rsp+50h] [rbp-B0h] BYREF
  struct ITravelLogRecoveryData *v50; // [rsp+58h] [rbp-A8h] BYREF
  struct tagTABWINDOWDATA *v51; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v52; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v53; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v54; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v55; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v56; // [rsp+78h] [rbp-88h] BYREF
  struct IRecoveryStore *v57; // [rsp+80h] [rbp-80h] BYREF
  PWSTR AppID; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v59; // [rsp+90h] [rbp-70h]
  unsigned int v60; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v61; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v62; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v63; // [rsp+A0h] [rbp-60h] BYREF
  struct IUnknown *v64; // [rsp+A8h] [rbp-58h] BYREF
  int v65; // [rsp+B0h] [rbp-50h]
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-40h] BYREF
  struct IUnknown *v68; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v69; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v70; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v71; // [rsp+E8h] [rbp-18h]
  __int64 v72; // [rsp+F8h] [rbp-8h]
  struct IUnknown *v73; // [rsp+100h] [rbp+0h] BYREF
  _BYTE *v74; // [rsp+108h] [rbp+8h]
  struct _GUID v75; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v76[2]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v77; // [rsp+122h] [rbp+22h]
  __int16 v78; // [rsp+124h] [rbp+24h]
  unsigned int v79; // [rsp+128h] [rbp+28h]
  int v80; // [rsp+130h] [rbp+30h]
  unsigned int v81; // [rsp+138h] [rbp+38h]
  int v82; // [rsp+284h] [rbp+184h]
  int v83; // [rsp+288h] [rbp+188h]
  unsigned int v84; // [rsp+2B8h] [rbp+1B8h]
  int v85; // [rsp+2BCh] [rbp+1BCh]
  int v86; // [rsp+2C0h] [rbp+1C0h]
  unsigned __int16 v87[2088]; // [rsp+3A0h] [rbp+2A0h] BYREF

  v51 = a3;
  v4 = a3;
  v53 = 0;
  v54 = 0;
  v56 = 0;
  *(_QWORD *)&v70 = 0;
  v71 = 0u;
  v72 = 0;
  BYTE8(v70) = 1;
  v49 = 0;
  v52 = 0;
  v65 = 0;
  v62 = 0;
  v61 = 0;
  v63 = 0;
  v60 = 0;
  v64 = 0;
  memset_0(v76, 0, 0x278u);
  v8 = *((_DWORD *)a2 + 29);
  *((_DWORD *)this + 3519) = *((_DWORD *)a2 + 28);
  *((_DWORD *)this + 3520) = v8;
  v9 = (struct _ITEMIDLIST_ABSOLUTE *)*((_QWORD *)a2 + 44);
  v76[0] = 20;
  v77 = 632;
  v55 = 0;
  v57 = 0;
  FrameTabWindow = LCIEGetURLPolicy(v9, v4, 0, &v56, &v55);
  if ( FrameTabWindow < 0 )
    goto LABEL_76;
  v11 = v56;
  LCIESetTabFlags2FromIsoProcessFlags(v56, v55, v4);
  v12 = (char *)v4 + 32;
  v74 = (char *)v4 + 32;
  FrameTabWindow = LCIEReconcileIsoIntegrityInFlags(
                     (unsigned int *)v4 + 8,
                     (unsigned int *)a2,
                     (unsigned int *)this + 74);
  if ( FrameTabWindow < 0 )
    goto LABEL_76;
  if ( (int)CRecoveryStore::Get(&v57) >= 0 )
  {
    LOBYTE(v11) = v11 & 0x7F;
    v13 = (_QWORD *)((char *)this + 13704);
    v14 = *((_BYTE *)v4 + 26) == 0;
    v59 = v11;
    if ( v14 || (v15 = *((_QWORD *)a2 + 50), (*v13 = v15) == 0) )
    {
      v16 = 0;
    }
    else
    {
      v16 = 1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    }
    if ( *((_DWORD *)this + 3479) != 2 )
    {
      if ( v16 )
      {
        v31 = *v13;
        v75 = 0;
        (*(void (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v31 + 24LL))(v31, &v75);
        v32 = (*(__int64 (__fastcall **)(struct IRecoveryStore *, char *, struct _GUID *))(*(_QWORD *)v57 + 104LL))(
                v57,
                (char *)this + 13736,
                &v75);
      }
      else
      {
        v32 = (*(__int64 (__fastcall **)(struct IRecoveryStore *, char *, _QWORD, char *))(*(_QWORD *)v57 + 88LL))(
                v57,
                (char *)this + 13736,
                0,
                (char *)this + 13704);
      }
      v18 = v32;
      goto LABEL_14;
    }
    v17 = *((_QWORD *)this + 1714);
    v75 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v17 + 24LL))(v17, &v75);
    if ( v18 < 0 )
    {
LABEL_14:
      pv = 0;
      if ( GetReuseTabIdFromThreadParam(a2, (unsigned __int16 **)&pv) >= 0 )
      {
        v20 = pv;
        if ( *v13 && pv )
        {
          (*(void (__fastcall **)(_QWORD, LPVOID))(*(_QWORD *)*v13 + 304LL))(*v13, pv);
          v20 = pv;
        }
        CoTaskMemFree(v20);
      }
      if ( v18 >= 0 )
      {
        CTabWindow::_InitializeRecoveryData(this);
        if ( ((*((_DWORD *)this + 3508) - 3) & 0xFFFFFFFB) != 0 )
        {
          v21 = (int (__fastcall ***)(_QWORD, GUID *, struct ITravelLogRecoveryData **))*v13;
          if ( *v13 )
          {
            v50 = 0;
            if ( (**v21)(v21, &GUID_5f59b0c4_f563_41f3_b7cb_02ca36c4dbc6, &v50) >= 0 )
              CTabWindow::s_ConfigureTabRecoveryDataAndUpdateThreadParams(a2, v50, v16 != 1);
          }
        }
      }
      AppID = 0;
      if ( (**(int (__fastcall ***)(struct IRecoveryStore *, GUID *, PWSTR *))v57)(
             v57,
             &GUID_8fd276bb_5a9d_4fc0_b0bd_90fa7cf1283d,
             &AppID) >= 0 )
      {
        v50 = 0;
        LOBYTE(v22) = v11;
        if ( (*(int (__fastcall **)(PWSTR, __int64, struct ITravelLogRecoveryData **))(*(_QWORD *)AppID + 48LL))(
               AppID,
               v22,
               &v50) >= 0 )
        {
          v23 = v50;
          *((_QWORD *)a2 + 52) = v50;
          (*(void (__fastcall **)(struct ITravelLogRecoveryData *))(*(_QWORD *)v23 + 8LL))(v23);
        }
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v50);
      }
      v67 = 0;
      if ( (**(int (__fastcall ***)(struct IRecoveryStore *, GUID *, __int64 *))v57)(
             v57,
             &GUID_239d58cc_793c_4b64_8320_b51380087c0b,
             &v67) >= 0 )
      {
        v50 = 0;
        LOBYTE(v24) = v11;
        if ( (*(int (__fastcall **)(__int64, __int64, struct ITravelLogRecoveryData **))(*(_QWORD *)v67 + 40LL))(
               v67,
               v24,
               &v50) >= 0 )
        {
          v25 = v50;
          *((_QWORD *)a2 + 53) = v50;
          (*(void (__fastcall **)(struct ITravelLogRecoveryData *))(*(_QWORD *)v25 + 8LL))(v25);
        }
        ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v50);
      }
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v67);
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&AppID);
      v4 = v51;
      v12 = v74;
      goto LABEL_33;
    }
    LODWORD(v50) = 0;
    v18 = (*(__int64 (__fastcall **)(struct IRecoveryStore *, char *, struct _GUID *, struct ITravelLogRecoveryData **))(*(_QWORD *)v57 + 168LL))(
            v57,
            (char *)this + 13736,
            &v75,
            &v50);
    if ( v18 >= 0 )
    {
      v19 = (char *)this + 13736;
      if ( v16 )
      {
        v18 = (*(__int64 (__fastcall **)(struct IRecoveryStore *, char *, struct _GUID *, _QWORD))(*(_QWORD *)v57 + 112LL))(
                v57,
                v19,
                &v75,
                (unsigned int)v50);
        if ( v18 < 0 )
          goto LABEL_13;
      }
      else
      {
        v18 = (*(__int64 (__fastcall **)(struct IRecoveryStore *, char *, _QWORD, _QWORD, char *))(*(_QWORD *)v57 + 96LL))(
                v57,
                v19,
                (unsigned int)v50,
                0,
                (char *)this + 13704);
        if ( v18 < 0 )
          goto LABEL_13;
        (*(void (__fastcall **)(struct IRecoveryStore *, char *, struct _GUID *))(*(_QWORD *)v57 + 128LL))(
          v57,
          (char *)this + 13736,
          &v75);
      }
      CTabWindow::_DeleteRoamedTabData(this, &v75);
    }
LABEL_13:
    LOBYTE(v11) = v59;
    goto LABEL_14;
  }
LABEL_33:
  if ( *((_BYTE *)this + 458) )
  {
    if ( *((_QWORD *)a2 + 50) )
    {
      v26 = *((_QWORD *)this + 1713);
      if ( v26 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 120LL))(v26);
        v27 = *((_QWORD *)a2 + 50);
        LODWORD(v50) = 0;
        (*(void (__fastcall **)(__int64, struct ITravelLogRecoveryData **))(*(_QWORD *)v27 + 136LL))(v27, &v50);
        (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1713) + 128LL))(
          *((_QWORD *)this + 1713),
          (unsigned int)((_DWORD)v50 + 1));
      }
    }
    *((_BYTE *)this + 458) = 0;
  }
  if ( *((_QWORD *)this + 1713) )
  {
    v28 = *((_QWORD *)a2 + 44);
    if ( !v28 || (int)IEGetNameAndFlagsEx(v28, 0x8000, 0, (int)v87, 0x824u, 0) < 0 )
      StringCchCopyW(v87, 0x824u, L"about:blank");
    (*(void (__fastcall **)(_QWORD, unsigned __int16 *))(**((_QWORD **)this + 1713) + 32LL))(
      *((_QWORD *)this + 1713),
      v87);
  }
  GetSessionStartTime(*((_DWORD *)a2 + 28), (struct _FILETIME *)((char *)a2 + 188));
  v14 = *((_DWORD *)this + 3479) == 2;
  *((_DWORD *)this + 3430) = *((_DWORD *)a2 + 43);
  if ( v14 && !*((_BYTE *)v4 + 1) )
    *((_BYTE *)this + 265) = 0;
  v69 = 0;
  if ( !a4 )
    goto LABEL_58;
  if ( ((*(_BYTE *)a4 ^ *v12) & 0x7F) != 0 || *((_BYTE *)v4 + 38) )
  {
    a4 = 0;
LABEL_58:
    FrameTabWindow = LCIEGetBrowserTabTargetProcess(a2, v4, 0, &v56, &v53, &v54, &v69);
    if ( FrameTabWindow < 0 )
      goto LABEL_135;
    v30 = v53;
    v29 = v56;
    goto LABEL_60;
  }
  v29 = *(_DWORD *)a4;
  v30 = *((_DWORD *)a4 + 1);
  v54 = *((_DWORD *)a4 + 2);
LABEL_60:
  v53 = v30;
  v33 = LCIEForceSecurityProxiesFromFlags(v29);
  if ( *((_DWORD *)a2 + 46) )
    v29 |= 0x400000u;
  if ( (v29 & 0xF000) == 0x5000 )
  {
    *((_DWORD *)a2 + 38) = CoInternetIsExtensionsOff();
    *((_DWORD *)a2 + 41) = IEIsScriptDebuggingEnabled();
  }
  if ( *((_BYTE *)this + 264) && !*((_QWORD *)a2 + 41) )
  {
    AppID = 0;
    FrameTabWindow = IECreateInstance(
                       &CLSID_IEThreadHandshake,
                       0,
                       1u,
                       &GUID_535252ce_bc27_4c3a_9709_4c2456109784,
                       (LPVOID *)&AppID);
    if ( FrameTabWindow < 0 )
      goto LABEL_76;
    *((_QWORD *)a2 + 41) = AppID;
  }
  *((_DWORD *)a2 + 19) = *((_DWORD *)this + 60);
  CTabWindowManager::GetBrowserRect(*((CTabWindowManager **)this + 60), (struct tagRECT *)((char *)a2 + 56));
  CTabWindow::_InterceptInitialShortcutNavigate(this, a2);
  *((_DWORD *)this + 3402) = *((_DWORD *)a2 + 34);
  v34 = LCIEFrameTabWindow();
  v35 = *((_QWORD *)a2 + 46);
  if ( v34 )
  {
    FrameTabWindow = CTabWindow::CreateFrameTabWindow((LONG_PTR)this, *((HWND *)a2 + 46));
    if ( FrameTabWindow < 0 )
      goto LABEL_76;
  }
  else
  {
    *((_QWORD *)this + 43) = v35;
  }
  FrameTabWindow = LCIEPackIETHREADPARAM_GetVariableBufferSize(v35, a2, &v60);
  if ( FrameTabWindow < 0 )
    goto LABEL_76;
  v36 = v60 + 936;
  if ( v60 >= 0xFFFFFC58 )
  {
    FrameTabWindow = -2147024362;
    goto LABEL_76;
  }
  if ( a4 )
  {
    FrameTabWindow = IsoAllocMessageBuffer(*((_DWORD *)a4 + 14), &v52, v36, (struct _IsoMessage **)&v49);
    if ( FrameTabWindow < 0 )
      goto LABEL_76;
  }
  else
  {
    FrameTabWindow = IsoAllocSharedMemoryPerFlags(v29, &v52, v36, (void **)&v49);
    if ( FrameTabWindow < 0 )
      goto LABEL_135;
  }
  FrameTabWindow = LCIEPackIETHREADPARAM(
                     v29,
                     v30,
                     (struct LCIE_WRAPPER_IE8_THREADPARAM *)(v49 + 432),
                     (const unsigned __int8 *)&v49[v60 + 936],
                     a2);
  if ( FrameTabWindow < 0 )
    goto LABEL_76;
  v65 = 1;
  v73 = 0;
  v68 = 0;
  IEGetThreadRef(&v73);
  FrameTabWindow = LCIECreateAndInitThreadRef(v73, (struct ILCIEThreadRef **)&v68);
  if ( FrameTabWindow < 0 )
    goto LABEL_76;
  v37 = (struct IUnknown **)((char *)this + 14056);
  ATL::AtlComPtrAssign((struct IUnknown **)this + 1757, v68);
  if ( v33 )
  {
    FrameTabWindow = CLCIE_IIDProxy_Master::MakeMaster(1u, &GUID_00000000_0000_0000_c000_000000000046, &v64, *v37);
    if ( FrameTabWindow < 0 )
      goto LABEL_76;
  }
  v38 = v64;
  if ( !v33 )
    v38 = *v37;
  v39 = v53;
  FrameTabWindow = LCIEMarshalInterfaceIntoBufferForHandle(
                     v29,
                     v53,
                     &IID_IUnknown,
                     v38,
                     (unsigned __int8 *)v49 + 172,
                     0x80u,
                     &v61);
  ((void (__fastcall *)(struct IUnknown *))v68->lpVtbl->Release)(v68);
  if ( v33 )
    ((void (__fastcall *)(struct IUnknown *))v64->lpVtbl->Release)(v64);
  if ( FrameTabWindow < 0 )
    goto LABEL_76;
  v40 = (struct IUnknown *)((char *)this + 16);
  if ( v33 )
  {
    FrameTabWindow = CLCIE_IIDProxy_Master::MakeMaster(1u, &GUID_17a643ed_26bc_4afa_b545_1bbbe77dbc30, &v64, v40);
    if ( FrameTabWindow < 0 )
      goto LABEL_76;
    v40 = v64;
  }
  FrameTabWindow = LCIEMarshalInterfaceIntoBufferForHandle(
                     v29,
                     v39,
                     &IID_ITabWindow2,
                     v40,
                     (unsigned __int8 *)v49 + 44,
                     0x80u,
                     &v62);
  if ( v33 )
    ((void (__fastcall *)(struct IUnknown *))v64->lpVtbl->Release)(v64);
  if ( FrameTabWindow < 0 )
  {
LABEL_76:
    if ( !v65 )
      goto LABEL_135;
    goto LABEL_77;
  }
  if ( IsBrokerAvailable() )
  {
    v41 = *(struct IUnknown **)(*((_QWORD *)this + 60) + 208LL);
    if ( !v41 )
    {
      FrameTabWindow = -2147467262;
      goto LABEL_76;
    }
    FrameTabWindow = LCIEMarshalInterfaceIntoBufferForHandle(
                       v29,
                       v39,
                       &IID_IEUserBroker,
                       v41,
                       (unsigned __int8 *)v49 + 300,
                       0x80u,
                       &v63);
    if ( FrameTabWindow < 0 )
      goto LABEL_76;
  }
  else
  {
    memset_0(v49 + 300, 0, 0x80u);
  }
  *((_DWORD *)v49 + 8) = *((_DWORD *)this + 3510);
  *((_DWORD *)v49 + 9) = *((_DWORD *)this + 3511);
  if ( v57 )
    (*(void (__fastcall **)(struct IRecoveryStore *, char *))(*(_QWORD *)v57 + 280LL))(v57, v49 + 40);
  *((_DWORD *)v49 + 3) = 3073;
  *(_QWORD *)(v49 + 4) = *((unsigned int *)this + 3510);
  v78 = 515;
  v84 = v52;
  v79 = v54;
  v86 = *((_DWORD *)this + 3510);
  v42 = v55;
  v85 = 103;
  v83 = 104;
  v80 = 105;
  v82 = 0;
  if ( !v55 )
  {
    v42 = v81;
    if ( *((_DWORD *)v51 + 13) )
      v42 = *((_DWORD *)v51 + 13);
  }
  v43 = *((_DWORD *)a2 + 29);
  v44 = *((_DWORD *)a2 + 28);
  v81 = v42;
  IESessionSetTabProcessCompCreDat(v44, v43, (struct _IsoCreationComponentData *)v76);
  *((_DWORD *)this + 3479) = 3;
  if ( a4 )
  {
    v45 = *((_DWORD *)a4 + 14);
    v51 = 0;
    if ( (int)IsoLockArtifact(v45, 0x14u, &v51, 0) >= 0 )
    {
      *((_DWORD *)v51 + 9) = *((_DWORD *)this + 3510);
      IsoUnlockArtifact(*((_DWORD *)a4 + 14));
    }
    *((_QWORD *)this + 1741) = *((_QWORD *)a4 + 8);
    if ( WaitForEarlyStart(a4) )
      FrameTabWindow = -2147467259;
    else
      FrameTabWindow = LCIEPostMessage(*((_DWORD *)a4 + 14), *((_DWORD *)v49 + 1), 0xC01u, 0, v52);
    CTabWindow::_SetBrowserTabComponentHandle(this, *((_DWORD *)a4 + 14));
    v46 = *((_OWORD *)a4 + 2);
    v70 = *((_OWORD *)a4 + 1);
    BYTE8(v70) = 0;
    v72 = *((_QWORD *)a4 + 6);
    v71 = v46;
  }
  else
  {
    AppID = 0;
    if ( (unsigned __int8)IEConfiguration_GetBool(268435465) || IsDualEngineProcess() )
      FrameTabWindow = GetCurrentProcessExplicitAppUserModelID(&AppID);
    if ( FrameTabWindow >= 0 )
    {
      v55 = 0;
      FrameTabWindow = IsoCreateComponentByCreDat(
                         v29 | 0x20000000,
                         v76,
                         AppID,
                         &v55,
                         0,
                         0,
                         &v70,
                         (char *)this + 13928,
                         0);
      if ( FrameTabWindow >= 0 )
        CTabWindow::_SetBrowserTabComponentHandle(this, v55);
      if ( v69 )
        IsoRemoveDependency(v69);
    }
    CoTaskMemFree(AppID);
  }
  if ( FrameTabWindow < 0 )
  {
    FrameTabWindow = -2147467259;
LABEL_77:
    LCIEDestroyIETHREADPARAM((struct LCIE_WRAPPER_IE8_THREADPARAM *)(v49 + 432), v60);
    goto LABEL_135;
  }
  v47 = v70 & 0xF000;
  v52 = 0;
  v62 = 0;
  v61 = 0;
  v63 = 0;
  if ( v47 == 0x2000 )
  {
    *((_QWORD *)this + 32) = v71;
    *((_DWORD *)this + 62) = DWORD1(v70);
    BYTE8(v70) = 0;
    *((_DWORD *)this + 63) = GetCurrentProcessId();
    if ( *((_BYTE *)this + 265) && *((_BYTE *)this + 273) )
      CTabWindow::SetTabPriority(this, -1);
  }
  else if ( ((v47 - 0x4000) & 0xFFFFEFFF) == 0 )
  {
    *((_DWORD *)this + 63) = DWORD1(v70);
  }
  if ( *((_BYTE *)this + 264) && (int)WaitForBrowserCreation(*((_QWORD *)a2 + 41), v71) >= 0 )
    (*(void (__fastcall **)(_QWORD, _QWORD, GUID *, char *))(**((_QWORD **)a2 + 41) + 40LL))(
      *((_QWORD *)a2 + 41),
      *((unsigned int *)this + 3509),
      &GUID_d30c1661_cdaf_11d0_8a3e_00c04fc9e26e,
      (char *)this + 464);
  FrameTabWindow = 0;
LABEL_135:
  if ( v61 )
  {
    v51 = 0;
    LCIEUnmarshalInterfaceFromBuffer(&IID_IUnknown, (void **)&v51, (unsigned __int8 *)v49 + 172, 0x80u);
    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v51);
  }
  if ( v62 )
  {
    v51 = 0;
    LCIEUnmarshalInterfaceFromBuffer(&IID_ITabWindow2, (void **)&v51, (unsigned __int8 *)v49 + 44, 0x80u);
    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v51);
  }
  if ( v63 )
  {
    v51 = 0;
    LCIEUnmarshalInterfaceFromBuffer(&IID_IEUserBroker, (void **)&v51, (unsigned __int8 *)v49 + 300, 0x80u);
    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v51);
  }
  if ( v52 )
    IsoFreeSharedMemory(v52);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v57);
  _IsoWindowsContainer::~_IsoWindowsContainer((_IsoWindowsContainer *)&v70);
  return (unsigned int)FrameTabWindow;
}

```

## disassembly

```asm
0x18027f19c  push    rbp
0x18027f19e  push    rbx
0x18027f19f  push    rsi
0x18027f1a0  push    rdi
0x18027f1a1  push    r12
0x18027f1a3  push    r13
0x18027f1a5  push    r14
0x18027f1a7  push    r15
0x18027f1a9  lea     rbp, [rsp-1308h]
0x18027f1b1  mov     eax, 1408h
0x18027f1b6  call    _alloca_probe
0x18027f1bb  sub     rsp, rax
0x18027f1be  mov     rax, cs:__security_cookie
0x18027f1c5  xor     rax, rsp
0x18027f1c8  mov     [rbp+1340h+var_50], rax
0x18027f1cf  xor     r13d, r13d
0x18027f1d2  mov     [rsp+1440h+var_13E0], r8
0x18027f1d7  mov     r15, r8
0x18027f1da  mov     [rsp+1440h+var_13D4], r13d
0x18027f1df  mov     rsi, rdx
0x18027f1e2  mov     [rsp+1440h+var_13D0], r13d
0x18027f1e7  mov     rdi, rcx
0x18027f1ea  mov     [rsp+1440h+var_13C8], r13d
0x18027f1ef  mov     ebx, 278h
0x18027f1f4  mov     qword ptr [rbp+1340h+var_1368], r13
0x18027f1f8  mov     r8d, ebx; Size
0x18027f1fb  mov     qword ptr [rbp+1340h+var_1358], r13
0x18027f1ff  xor     edx, edx; Val
0x18027f201  mov     qword ptr [rbp+1340h+var_1358+8], r13
0x18027f205  lea     rcx, [rbp+1340h+var_1320]; void *
0x18027f209  mov     [rbp+1340h+var_1348], r13
0x18027f20d  mov     r14, r9
0x18027f210  mov     byte ptr [rbp+1340h+var_1368+8], 1
0x18027f214  mov     [rsp+1440h+var_13F0], r13
0x18027f219  mov     [rsp+1440h+var_13D8], r13d
0x18027f21e  mov     [rbp+1340h+var_1390], r13d
0x18027f222  mov     [rbp+1340h+var_13A4], r13d
0x18027f226  mov     [rbp+1340h+var_13A8], r13d
0x18027f22a  mov     [rbp+1340h+var_13A0], r13d
0x18027f22e  mov     [rbp+1340h+var_13AC], r13d
0x18027f232  mov     [rbp+1340h+var_1398], r13
0x18027f236  call    memset_0
0x18027f23b  mov     ecx, [rsi+74h]
0x18027f23e  lea     r9, [rsp+1440h+var_13C8]; unsigned int *
0x18027f243  mov     eax, [rsi+70h]
0x18027f246  xor     r8d, r8d; unsigned int *
0x18027f249  mov     [rdi+36FCh], eax
0x18027f24f  mov     rdx, r15; struct tagTABWINDOWDATA *
0x18027f252  lea     rax, [rsp+1440h+var_13CC]
0x18027f257  mov     [rdi+3700h], ecx
0x18027f25d  mov     rcx, [rsi+160h]; struct _ITEMIDLIST_ABSOLUTE *
0x18027f264  mov     qword ptr [rsp+1440h+cchBuf], rax; unsigned int *
0x18027f269  mov     [rbp+1340h+var_1320], 14h
0x18027f26d  mov     [rbp+1340h+var_131E], bx
0x18027f271  mov     [rsp+1440h+var_13CC], r13d
0x18027f276  mov     [rbp+1340h+var_13C0], r13
0x18027f27a  call    ?LCIEGetURLPolicy@@YAJPEAU_ITEMIDLIST_ABSOLUTE@@PEAUtagTABWINDOWDATA@@PEAK22@Z; LCIEGetURLPolicy(_ITEMIDLIST_ABSOLUTE *,tagTABWINDOWDATA *,ulong *,ulong *,ulong *)
0x18027f27f  mov     ebx, eax
0x18027f281  test    eax, eax
0x18027f283  js      loc_18027FEE7
0x18027f289  mov     r13d, [rsp+1440h+var_13C8]
0x18027f28e  mov     r8, r15; struct tagTABWINDOWDATA *
0x18027f291  mov     edx, [rsp+1440h+var_13CC]; unsigned int
0x18027f295  mov     ecx, r13d; unsigned int
0x18027f298  call    ?LCIESetTabFlags2FromIsoProcessFlags@@YAXKKPEAUtagTABWINDOWDATA@@@Z; LCIESetTabFlags2FromIsoProcessFlags(ulong,ulong,tagTABWINDOWDATA *)
0x18027f29d  lea     r12, [r15+20h]
0x18027f2a1  mov     rdx, rsi; unsigned int *
0x18027f2a4  mov     rcx, r12; unsigned int *
0x18027f2a7  mov     [rbp+1340h+var_1338], r12
0x18027f2ab  lea     r8, [rdi+128h]; unsigned int *
0x18027f2b2  call    ?LCIEReconcileIsoIntegrityInFlags@@YAJPEAK00@Z; LCIEReconcileIsoIntegrityInFlags(ulong *,ulong *,ulong *)
0x18027f2b7  mov     ebx, eax
0x18027f2b9  test    eax, eax
0x18027f2bb  js      loc_18027FEE4
0x18027f2c1  lea     rcx, [rbp+1340h+var_13C0]; struct IRecoveryStore **
0x18027f2c5  call    ?Get@CRecoveryStore@@SAJPEAPEAUIRecoveryStore@@@Z; CRecoveryStore::Get(IRecoveryStore * *)
0x18027f2ca  test    eax, eax
0x18027f2cc  js      loc_18027F546
0x18027f2d2  and     r13b, 7Fh
0x18027f2d6  lea     rbx, [rdi+3588h]
0x18027f2dd  cmp     byte ptr [r15+1Ah], 0
0x18027f2e2  mov     [rbp+1340h+var_13B0], r13d
0x18027f2e6  jz      short loc_18027F308
0x18027f2e8  mov     rcx, [rsi+190h]
0x18027f2ef  mov     [rbx], rcx
0x18027f2f2  test    rcx, rcx
0x18027f2f5  jz      short loc_18027F308
0x18027f2f7  mov     rax, [rcx]
0x18027f2fa  mov     r12b, 1
0x18027f2fd  mov     rax, [rax+8]
0x18027f301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f306  jmp     short loc_18027F30B
0x18027f308  xor     r12b, r12b
0x18027f30b  cmp     dword ptr [rdi+365Ch], 2
0x18027f312  jnz     loc_18027F6E9
0x18027f318  mov     rcx, [rdi+3590h]
0x18027f31f  lea     rdx, [rbp+1340h+var_1330]
0x18027f323  xorps   xmm0, xmm0
0x18027f326  movups  xmmword ptr [rbp+1340h+var_1330.Data1], xmm0
0x18027f32a  mov     rax, [rcx]
0x18027f32d  mov     rax, [rax+18h]
0x18027f331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f336  mov     r15d, eax
0x18027f339  test    eax, eax
0x18027f33b  js      short loc_18027F3A6
0x18027f33d  mov     rcx, [rbp+1340h+var_13C0]
0x18027f341  lea     r13, [rdi+35A8h]
0x18027f348  mov     dword ptr [rsp+1440h+var_13E8], 0
0x18027f350  lea     r9, [rsp+1440h+var_13E8]
0x18027f355  lea     r8, [rbp+1340h+var_1330]
0x18027f359  mov     rdx, r13
0x18027f35c  mov     rax, [rcx]
0x18027f35f  mov     rax, [rax+0A8h]
0x18027f366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f36b  mov     r15d, eax
0x18027f36e  test    eax, eax
0x18027f370  js      short loc_18027F3A2
0x18027f372  mov     rdx, r13
0x18027f375  test    r12b, r12b
0x18027f378  jz      loc_18027F68C
0x18027f37e  mov     rcx, [rbp+1340h+var_13C0]
0x18027f382  lea     r8, [rbp+1340h+var_1330]
0x18027f386  mov     r9d, dword ptr [rsp+1440h+var_13E8]
0x18027f38b  mov     rax, [rcx]
0x18027f38e  mov     rax, [rax+70h]
0x18027f392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f397  mov     r15d, eax
0x18027f39a  test    eax, eax
0x18027f39c  jns     loc_18027F6D8
0x18027f3a2  mov     r13d, [rbp+1340h+var_13B0]
0x18027f3a6  lea     rdx, [rbp+1340h+pv]; unsigned __int16 **
0x18027f3aa  mov     [rbp+1340h+pv], 0
0x18027f3b2  mov     rcx, rsi; struct tagIE8_THREADPARAM *
0x18027f3b5  call    ?GetReuseTabIdFromThreadParam@@YAJPEAUtagIE8_THREADPARAM@@PEAPEAG@Z; GetReuseTabIdFromThreadParam(tagIE8_THREADPARAM *,ushort * *)
0x18027f3ba  test    eax, eax
0x18027f3bc  js      short loc_18027F3F4
0x18027f3be  mov     r8, [rbx]
0x18027f3c1  mov     rcx, [rbp+1340h+pv]
0x18027f3c5  test    r8, r8
0x18027f3c8  jz      short loc_18027F3E8
0x18027f3ca  test    rcx, rcx
0x18027f3cd  jz      short loc_18027F3E8
0x18027f3cf  mov     rax, [r8]
0x18027f3d2  mov     rdx, rcx
0x18027f3d5  mov     rcx, r8
0x18027f3d8  mov     rax, [rax+130h]
0x18027f3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f3e4  mov     rcx, [rbp+1340h+pv]; pv
0x18027f3e8  call    cs:__imp_CoTaskMemFree
0x18027f3ef  nop     dword ptr [rax+rax+00h]
0x18027f3f4  test    r15d, r15d
0x18027f3f7  js      short loc_18027F451
0x18027f3f9  mov     rcx, rdi; this
0x18027f3fc  call    ?_InitializeRecoveryData@CTabWindow@@AEAAXXZ; CTabWindow::_InitializeRecoveryData(void)
0x18027f401  mov     eax, [rdi+36D0h]
0x18027f407  sub     eax, 3
0x18027f40a  test    eax, 0FFFFFFFBh
0x18027f40f  jz      short loc_18027F451
0x18027f411  mov     rcx, [rbx]
0x18027f414  test    rcx, rcx
0x18027f417  jz      short loc_18027F451
0x18027f419  mov     [rsp+1440h+var_13E8], 0
0x18027f422  lea     r8, [rsp+1440h+var_13E8]
0x18027f427  mov     rax, [rcx]
0x18027f42a  lea     rdx, _GUID_5f59b0c4_f563_41f3_b7cb_02ca36c4dbc6
0x18027f431  mov     rax, [rax]
0x18027f434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f439  test    eax, eax
0x18027f43b  js      short loc_18027F451
0x18027f43d  mov     rdx, [rsp+1440h+var_13E8]; struct ITravelLogRecoveryData *
0x18027f442  xor     r12b, 1
0x18027f446  mov     r8b, r12b; bool
0x18027f449  mov     rcx, rsi; struct tagIE8_THREADPARAM *
0x18027f44c  call    ?s_ConfigureTabRecoveryDataAndUpdateThreadParams@CTabWindow@@CAXPEAUtagIE8_THREADPARAM@@PEAUITravelLogRecoveryData@@_N@Z; CTabWindow::s_ConfigureTabRecoveryDataAndUpdateThreadParams(tagIE8_THREADPARAM *,ITravelLogRecoveryData *,bool)
0x18027f451  mov     rcx, [rbp+1340h+var_13C0]
0x18027f455  lea     r8, [rbp+1340h+AppID]
0x18027f459  mov     [rbp+1340h+AppID], 0
0x18027f461  lea     rdx, _GUID_8fd276bb_5a9d_4fc0_b0bd_90fa7cf1283d
0x18027f468  mov     rax, [rcx]
0x18027f46b  mov     rax, [rax]
0x18027f46e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f473  test    eax, eax
0x18027f475  js      short loc_18027F4BE
0x18027f477  mov     rcx, [rbp+1340h+AppID]
0x18027f47b  lea     r8, [rsp+1440h+var_13E8]
0x18027f480  mov     [rsp+1440h+var_13E8], 0
0x18027f489  mov     dl, r13b
0x18027f48c  mov     rax, [rcx]
0x18027f48f  mov     rax, [rax+30h]
0x18027f493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f498  test    eax, eax
0x18027f49a  js      short loc_18027F4B4
0x18027f49c  mov     rcx, [rsp+1440h+var_13E8]
0x18027f4a1  mov     [rsi+1A0h], rcx
0x18027f4a8  mov     rax, [rcx]
0x18027f4ab  mov     rax, [rax+8]
0x18027f4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f4b4  lea     rcx, [rsp+1440h+var_13E8]; void *
0x18027f4b9  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18027f4be  mov     rcx, [rbp+1340h+var_13C0]
0x18027f4c2  lea     r8, [rbp+1340h+var_1380]
0x18027f4c6  mov     [rbp+1340h+var_1380], 0
0x18027f4ce  lea     rdx, _GUID_239d58cc_793c_4b64_8320_b51380087c0b
0x18027f4d5  mov     rax, [rcx]
0x18027f4d8  mov     rax, [rax]
0x18027f4db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f4e0  test    eax, eax
0x18027f4e2  js      short loc_18027F52B
0x18027f4e4  mov     rcx, [rbp+1340h+var_1380]
0x18027f4e8  lea     r8, [rsp+1440h+var_13E8]
0x18027f4ed  mov     [rsp+1440h+var_13E8], 0
0x18027f4f6  mov     dl, r13b
0x18027f4f9  mov     rax, [rcx]
0x18027f4fc  mov     rax, [rax+28h]
0x18027f500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f505  test    eax, eax
0x18027f507  js      short loc_18027F521
0x18027f509  mov     rcx, [rsp+1440h+var_13E8]
0x18027f50e  mov     [rsi+1A8h], rcx
0x18027f515  mov     rax, [rcx]
0x18027f518  mov     rax, [rax+8]
0x18027f51c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f521  lea     rcx, [rsp+1440h+var_13E8]; void *
0x18027f526  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18027f52b  lea     rcx, [rbp+1340h+var_1380]; void *
0x18027f52f  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18027f534  lea     rcx, [rbp+1340h+AppID]; void *
0x18027f538  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18027f53d  mov     r15, [rsp+1440h+var_13E0]
0x18027f542  mov     r12, [rbp+1340h+var_1338]
0x18027f546  xor     r13d, r13d
0x18027f549  cmp     [rdi+1CAh], r13b
0x18027f550  jz      short loc_18027F5B6
0x18027f552  cmp     [rsi+190h], r13
0x18027f559  jz      short loc_18027F5AF
0x18027f55b  mov     rcx, [rdi+3588h]
0x18027f562  test    rcx, rcx
0x18027f565  jz      short loc_18027F5AF
0x18027f567  mov     rax, [rcx]
0x18027f56a  mov     rax, [rax+78h]
0x18027f56e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f573  mov     rcx, [rsi+190h]
0x18027f57a  lea     rdx, [rsp+1440h+var_13E8]
0x18027f57f  mov     dword ptr [rsp+1440h+var_13E8], r13d
0x18027f584  mov     rax, [rcx]
0x18027f587  mov     rax, [rax+88h]
0x18027f58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f593  mov     rcx, [rdi+3588h]
0x18027f59a  mov     edx, dword ptr [rsp+1440h+var_13E8]
0x18027f59e  inc     edx
0x18027f5a0  mov     rax, [rcx]
0x18027f5a3  mov     rax, [rax+80h]
0x18027f5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f5af  mov     [rdi+1CAh], r13b
0x18027f5b6  cmp     [rdi+3588h], r13
0x18027f5bd  jz      short loc_18027F621
0x18027f5bf  mov     rcx, [rsi+160h]; int
0x18027f5c6  mov     ebx, 824h
0x18027f5cb  test    rcx, rcx
0x18027f5ce  jz      short loc_18027F5F1
0x18027f5d0  mov     [rsp+1440h+var_1418], r13; __int64
0x18027f5d5  lea     r9, [rbp+1340h+var_10A0]; int
0x18027f5dc  xor     r8d, r8d; int
0x18027f5df  mov     [rsp+1440h+cchBuf], ebx; cchBuf
0x18027f5e3  mov     edx, 8000h; int
0x18027f5e8  call    IEGetNameAndFlagsEx
0x18027f5ed  test    eax, eax
0x18027f5ef  jns     short loc_18027F607
0x18027f5f1  lea     r8, aAboutBlank; "about:blank"
0x18027f5f8  mov     rdx, rbx; unsigned __int64
0x18027f5fb  lea     rcx, [rbp+1340h+var_10A0]; unsigned __int16 *
0x18027f602  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18027f607  mov     rcx, [rdi+3588h]
0x18027f60e  lea     rdx, [rbp+1340h+var_10A0]
0x18027f615  mov     rax, [rcx]
0x18027f618  mov     rax, [rax+20h]
0x18027f61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027f621  mov     ecx, [rsi+70h]; unsigned int
0x18027f624  lea     rdx, [rsi+0BCh]; struct _FILETIME *
0x18027f62b  call    ?GetSessionStartTime@@YA_NKPEAU_FILETIME@@@Z; GetSessionStartTime(ulong,_FILETIME *)
0x18027f630  cmp     dword ptr [rdi+365Ch], 2
0x18027f637  mov     eax, [rsi+0ACh]
0x18027f63d  mov     [rdi+3598h], eax
0x18027f643  jnz     short loc_18027F652
0x18027f645  cmp     [r15+1], r13b
0x18027f649  jnz     short loc_18027F652
0x18027f64b  mov     [rdi+109h], r13b
0x18027f652  mov     [rbp+1340h+var_1370], r13
0x18027f656  test    r14, r14
0x18027f659  jz      loc_18027F74C
0x18027f65f  mov     al, [r12]
0x18027f663  xor     al, [r14]
0x18027f666  test    al, 7Fh
0x18027f668  jnz     loc_18027F749
0x18027f66e  cmp     [r15+26h], r13b
0x18027f672  jnz     loc_18027F749
0x18027f678  mov     ebx, [r14+8]
0x18027f67c  mov     r15d, [r14]
0x18027f67f  mov     r12d, [r14+4]
0x18027f683  mov     [rsp+1440h+var_13D0], ebx
  ... truncated ...
```
