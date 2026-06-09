# CFveApi::InitializeDeviceEncryption(ulong,_GUID const *)

- ea: `0x180053e94`
- end: `0x180054f24`
- name: `?InitializeDeviceEncryption@CFveApi@@QEAAJKPEBU_GUID@@@Z`
- size: `4240`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, unsigned int, const struct _GUID *)`
- caller_count: `3`
- callee_count: `36`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180055850`
- `0x180067cc0`
- `0x180067f60`

## callees

- `0x1800050c0`
- `0x180008d70`
- `0x180008da0`
- `0x1800090c0`
- `0x180009130`
- `0x180009468`
- `0x180009790`
- `0x18000ab88`
- `0x18000b740`
- `0x18000ba30`
- `0x1800177b8`
- `0x180042448`
- `0x1800450c4`
- `0x180047a48`
- `0x180053a20`
- `0x180053a80`
- `0x180053b5c`
- `0x180053bac`
- `0x180053e64`
- `0x180053e94`
- `0x180054f2c`
- `0x180055c44`
- `0x180058cdc`
- `0x180074be0`
- `0x18007dcec`
- `0x180082508`
- `0x1800ab010`
- `0x1800ab2f8`
- `0x1800c5324`
- `0x1800c7330`
- `0x1800d19c0`
- `0x1800d49ec`
- `0x1800d4c38`
- `0x1800d7284`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800547b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800547b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005454d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005454d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800545a1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800545a1`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1800545fc`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1800545fc`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180054e5b`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180054e5b`

## string_xrefs

- `0x180054892`: `VolumePath`
- `0x180054a6e`: `VolumePath`
- `0x180054b7f`: `VolumePath`
- `0x180054de4`: `ServiceName`

## pseudocode

```c
__int64 __fastcall CFveApi::InitializeDeviceEncryption(CFveApi *this, int a2, struct _GUID *a3)
{
  char v4; // bl
  unsigned int v6; // r15d
  unsigned __int16 *v7; // r12
  HANDLE EventW; // r13
  __int64 v9; // r9
  int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // eax
  PVOID *v15; // rcx
  bool v16; // r13
  __int64 v17; // r9
  __int64 v18; // rdx
  GUID *v19; // rcx
  GUID *v20; // rcx
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int16 v26; // bx
  int v27; // eax
  int v28; // ecx
  int v29; // edx
  int v30; // ecx
  int v31; // edx
  unsigned int v32; // ecx
  __int64 v33; // r8
  unsigned int v34; // edx
  unsigned int v35; // ecx
  __int64 v36; // rdx
  unsigned int IsOSVolumeDeviceEncryptionUserInitiated; // eax
  PVOID *v38; // rcx
  unsigned int inited; // eax
  unsigned int v40; // eax
  HANDLE FileW; // rbx
  unsigned int v42; // eax
  unsigned int v43; // eax
  bool v44; // cf
  unsigned int v45; // eax
  unsigned int v46; // eax
  const unsigned __int16 *v47; // rax
  const unsigned __int16 *v48; // rdx
  const unsigned __int16 *v49; // rax
  const unsigned __int16 *v50; // rdx
  const unsigned __int16 *LoggingVolumePath; // rax
  const unsigned __int16 *v52; // rdx
  const unsigned __int16 *LoggingVolumeDriveLetter; // rax
  const unsigned __int16 *v54; // rdx
  struct _FVEAPI_EVENT_DATA_COLLECTION *v55; // rdx
  const unsigned __int16 *v56; // rax
  const unsigned __int16 *v57; // rdx
  const unsigned __int16 *v58; // rax
  const unsigned __int16 *v59; // rdx
  const unsigned __int16 *v60; // rax
  const unsigned __int16 *v61; // rdx
  const unsigned __int16 *LoggingServiceName; // rax
  const unsigned __int16 *v63; // rdx
  int v64; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositionc; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiond; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositione; // [rsp+20h] [rbp-E0h]
  bool v72; // [rsp+40h] [rbp-C0h] BYREF
  bool v73; // [rsp+41h] [rbp-BFh] BYREF
  char v74; // [rsp+42h] [rbp-BEh]
  bool v75; // [rsp+43h] [rbp-BDh] BYREF
  bool v76; // [rsp+44h] [rbp-BCh] BYREF
  bool v77; // [rsp+45h] [rbp-BBh] BYREF
  char v78; // [rsp+46h] [rbp-BAh]
  int v79; // [rsp+48h] [rbp-B8h]
  __int64 v80; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v81; // [rsp+58h] [rbp-A8h]
  __int64 v82; // [rsp+60h] [rbp-A0h]
  int v83; // [rsp+68h] [rbp-98h]
  HANDLE hObject; // [rsp+70h] [rbp-90h]
  struct _GUID *v85; // [rsp+78h] [rbp-88h]
  __int64 v86; // [rsp+80h] [rbp-80h] BYREF
  __int64 v87; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v88; // [rsp+90h] [rbp-70h]
  __int128 *v89; // [rsp+98h] [rbp-68h] BYREF
  __int128 *v90; // [rsp+A0h] [rbp-60h]
  __int64 v91; // [rsp+A8h] [rbp-58h] BYREF
  __int64 *v92; // [rsp+B0h] [rbp-50h]
  __int64 v93; // [rsp+B8h] [rbp-48h] BYREF
  __int64 **v94; // [rsp+C0h] [rbp-40h]
  __int64 v95; // [rsp+C8h] [rbp-38h] BYREF
  __int64 *v96; // [rsp+D0h] [rbp-30h]
  __int128 **v97; // [rsp+D8h] [rbp-28h] BYREF
  __int128 *v98; // [rsp+E0h] [rbp-20h]
  __int64 v99; // [rsp+E8h] [rbp-18h] BYREF
  __int64 *v100; // [rsp+F0h] [rbp-10h]
  __int128 **v101; // [rsp+F8h] [rbp-8h] BYREF
  __int128 *v102; // [rsp+100h] [rbp+0h]
  _DWORD v103[4]; // [rsp+110h] [rbp+10h] BYREF
  HANDLE v104; // [rsp+120h] [rbp+20h]
  unsigned __int64 v105; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 *v106; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int128 *v107; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 *v108; // [rsp+2C8h] [rbp+1C8h]
  const wchar_t *v109; // [rsp+2D0h] [rbp+1D0h]
  const wchar_t *v110; // [rsp+2D8h] [rbp+1D8h]
  void *v111; // [rsp+2E0h] [rbp+1E0h]
  __int64 v112; // [rsp+2E8h] [rbp+1E8h]
  __int128 v113; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int128 v114; // [rsp+300h] [rbp+200h]
  __int128 v115; // [rsp+310h] [rbp+210h]
  __int128 v116; // [rsp+320h] [rbp+220h] BYREF
  __int128 v117; // [rsp+330h] [rbp+230h]
  __int128 v118; // [rsp+340h] [rbp+240h]
  __int128 v119; // [rsp+350h] [rbp+250h] BYREF
  __int128 v120; // [rsp+360h] [rbp+260h]
  __int128 v121; // [rsp+370h] [rbp+270h]
  unsigned __int64 v122; // [rsp+380h] [rbp+280h] BYREF
  WCHAR FileName[264]; // [rsp+390h] [rbp+290h] BYREF

  v85 = a3;
  v4 = a2;
  v79 = a2;
  v77 = 0;
  v86 = 0;
  memset_0(v103, 0, 0x1A0u);
  v74 = 0;
  v72 = 0;
  v75 = 0;
  v6 = 0;
  v76 = 0;
  v7 = 0;
  v106 = 0;
  EventW = 0;
  v105 = 0;
  v78 = 0;
  v73 = 1;
  hObject = (HANDLE)-1LL;
  memset_0(FileName, 0, 0x208u);
  v122 = 0;
  if ( !(unsigned int)FveCanProvisionDE(a3, &v122) )
  {
    v9 = 2150694921LL;
    v10 = -2144272375;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_28;
    v12 = 131;
    goto LABEL_5;
  }
  if ( (*((_DWORD *)this + 27) & 0x8000) != 0 )
  {
    v10 = -2144272173;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_28;
    v12 = 132;
    v9 = 2150695123LL;
LABEL_5:
    WPP_SF_d(v11[2], v12, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v9);
    goto LABEL_28;
  }
  if ( (*((_BYTE *)this + 108) & 1) != 0 && (v4 & 4) == 0 )
  {
    v13 = CFveApiBase::LicenseCheck(this, (wchar_t *)L"SecureStartupFeature-Enabled-DeviceEncryption-BlockRevert");
    v10 = v13;
    if ( v13 == -2144272294 )
    {
      v14 = NgscbCheckIsUpgradedOS(&v72);
      v10 = v14;
      if ( v14 )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v14);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v10 < 0 )
          goto LABEL_28;
      }
      else
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      v16 = v72;
      if ( v72 )
      {
        if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
        {
          WPP_SF_(v15[2], 134, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        v17 = 2150694921LL;
        v10 = -2144272375;
        if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 )
          goto LABEL_27;
        v18 = 135;
        goto LABEL_26;
      }
      goto LABEL_41;
    }
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v13);
      if ( v10 < 0 )
        goto LABEL_28;
    }
  }
  v21 = NgscbCheckIsUpgradedOS(&v72);
  v10 = v21;
  if ( v21 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v21);
    if ( v10 < 0 )
      goto LABEL_28;
  }
  v16 = v72;
LABEL_41:
  v22 = CFveApiBase::ResolveVolumeMountName(this);
  v10 = v22;
  if ( v22 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v22);
    if ( v10 < 0 )
      goto LABEL_27;
  }
  v23 = NgscbCheckDeviceEncryptionOptedOutForVolume(*((const unsigned __int16 **)this + 49), &v75);
  v10 = v23;
  if ( v23 )
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v23);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 < 0 )
      goto LABEL_27;
  }
  else
  {
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v75 )
  {
    v10 = -2144272174;
    if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 )
      goto LABEL_27;
    v18 = 140;
    v17 = 2150695122LL;
LABEL_26:
    WPP_SF_d(v15[2], v18, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v17);
LABEL_27:
    EventW = 0;
    goto LABEL_28;
  }
  if ( !*((_BYTE *)this + 1158) )
  {
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
      WPP_SF_(v15[2], 141, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
    v24 = CFveApi::ReopenWritable(this, &v106);
    v10 = v24;
    if ( v24 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v24);
      if ( v10 < 0 )
      {
        v7 = v106;
LABEL_67:
        EventW = 0;
        goto LABEL_28;
      }
    }
    v7 = v106;
    v78 = 1;
  }
  v25 = CFveApi::CheckDataOnlyPolicy(this, 1, 0, &v73);
  v10 = v25;
  if ( v25 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v25);
    if ( v10 < 0 )
      goto LABEL_67;
  }
  v26 = v79;
  v27 = 0x10000;
  if ( v73 )
    v27 = 65792;
  v28 = v27 | 0x20100;
  LODWORD(v106) = v79 & 8;
  if ( (v79 & 8) == 0 )
    v28 = v27;
  v29 = v28 | 0x40000;
  if ( (v79 & 0x10) == 0 )
    v29 = v28;
  v30 = v29 | 0x400000;
  if ( (v79 & 0x100) == 0 )
    v30 = v29;
  v31 = v30 | 0x80000;
  if ( (v79 & 0x20) == 0 )
    v31 = v30;
  v32 = v31 | 0x100000;
  if ( (v79 & 0x40) == 0 )
    v32 = v31;
  v33 = v32;
  LODWORD(v33) = v32 | 0x200000;
  if ( (v79 & 0x80u) == 0 )
    v33 = v32;
  v83 = v79 & 0x200;
  v34 = v33 | 0x400;
  if ( (v79 & 0x200) == 0 )
    v34 = v33;
  v35 = v34 | 0x800000;
  if ( (v79 & 0x400) == 0 )
    v35 = v34;
  v36 = v35;
  LODWORD(v36) = v35 | 0x1000000;
  if ( (v79 & 0x800) == 0 )
    v36 = v35;
  v6 = v36 | 0x2000000;
  if ( (v79 & 0x1000) == 0 )
    v6 = v36;
  LOBYTE(v33) = 3;
  LOBYTE(v36) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Reduce_DE_Hardware_Reqs>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Reduce_DE_Hardware_Reqs>::GetImpl'::`2'::impl,
    v36,
    v33);
  if ( (v26 & 0x2000) != 0 )
    goto LABEL_109;
  if ( (*((_DWORD *)this + 27) & 0x10000001) == 0 )
  {
    IsOSVolumeDeviceEncryptionUserInitiated = CFveApiBase::IsOSVolumeDeviceEncryptionUserInitiated(&v76);
    v10 = IsOSVolumeDeviceEncryptionUserInitiated;
    if ( IsOSVolumeDeviceEncryptionUserInitiated )
    {
      v38 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          144,
          &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
          IsOSVolumeDeviceEncryptionUserInitiated);
        v38 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 < 0 )
        goto LABEL_103;
    }
    else
    {
      v38 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v76 )
    {
      if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 8) != 0 )
        WPP_SF_S(v38[2], 145, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v7);
LABEL_109:
      v6 |= 0x4000000u;
    }
  }
  if ( !NgscbGet_TEST_BooleanOverride(L"AllowDEHardwareEncryption", &v77) || !v77 )
    v6 |= 1u;
  if ( !v16 )
    v6 |= 0x2000u;
  inited = CFveApi::InitVolume(this, (wchar_t *)L"<none>", v6, v85);
  v10 = inited;
  if ( inited == 1 )
  {
    v10 = 0;
    EventW = 0;
  }
  else
  {
    if ( inited )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, inited);
      if ( v10 < 0 )
        goto LABEL_103;
    }
    v74 = 1;
    v40 = CFveApiBase::ReOpen(this);
    v10 = v40;
    if ( v40 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v40);
      if ( v10 < 0 )
      {
LABEL_103:
        EventW = (HANDLE)v105;
        goto LABEL_28;
      }
    }
    if ( (v79 & 1) != 0 && (*((_DWORD *)this + 26) & 0x100) != 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      if ( (int)StringCchCopyW(FileName, 0x104u, *((const unsigned __int16 **)this + 49)) < 0 )
      {
        FileW = hObject;
      }
      else
      {
        FileW = CreateFileW(FileName, 0, 3u, 0, 3u, 0x80u, 0);
        hObject = FileW;
      }
      if ( EventW && FileW != (HANDLE)-1LL )
      {
        memset_0(v103, 0, 0x1A0u);
        v103[0] = 416;
        v103[2] = 1;
        v104 = FileW;
        CM_Register_Notification(v103, EventW, &InitializeDeEowFreeSpaceCallback, &v86);
      }
    }
    else
    {
      EventW = (HANDLE)v105;
    }
    v42 = CFveApiBase::DisableAuthentication(this, 14);
    v10 = v42;
    if ( !v42 )
      goto LABEL_145;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v42);
    if ( v10 >= 0 )
    {
LABEL_145:
      if ( !(_DWORD)v106 )
        goto LABEL_151;
      v43 = CFveApiBase::SetWcosFveMethod(this);
      v10 = v43;
      if ( !v43 )
        goto LABEL_151;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v43);
      if ( v10 >= 0 )
      {
LABEL_151:
        if ( (v79 & 2) != 0 )
          goto LABEL_152;
        v44 = v83 != 0;
        v83 = -v83;
        v45 = CFveApi::ConversionEncryptEx(this, v73 | (v44 ? 32 : 16));
        v10 = v45;
        if ( !v45 )
          goto LABEL_152;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v45);
        if ( v10 >= 0 )
        {
LABEL_152:
          v46 = CFveApiBase::CommitChangesHelper((__int64)this, 1, 0, 0);
          v10 = v46;
          if ( !v46 )
            goto LABEL_157;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 151, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v46);
          if ( v10 >= 0 )
          {
LABEL_157:
            CFveApi::MarkDEInitializedInThisBootSession(this);
            if ( v86 && EventW && (int)CFveApiBase::UpdateStatus(this) >= 0 && (*((_DWORD *)this + 26) & 0x20000) != 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
              CFveApiBase::Close(this);
              WaitForSingleObject(EventW, 0x1D4C0u);
              CFveApiBase::Open(this, FileName, 0, 1);
            }
          }
        }
      }
    }
  }
LABEL_28:
  v19 = (GUID *)*((_QWORD *)this + 146);
  if ( v19 )
    v20 = v19 + 1;
  else
    v20 = &GUID_NULL;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  if ( v10 >= 0 )
  {
    v111 = v20;
    v112 = 16;
    v109 = L"IdentityGuid";
    v110 = L"GUID";
    if ( (v6 & 0x4000000) != 0 )
    {
      v95 = 0;
      v107 = (__int128 *)&v97;
      v108 = (__int128 *)&v97;
      v97 = &v107;
      v98 = (__int128 *)&v107;
      v96 = 0;
      LoggingVolumePath = CFveApiBase::GetLoggingVolumePath(this);
      FveApiEventLogDeclareWSTRING(
        (struct _FVEAPI_EVENT_DATA *)&v116,
        v52,
        L"VolumePath",
        LoggingVolumePath,
        dwCreationDisposition);
      if ( *(__int128 ****)v98 != &v97 )
        goto LABEL_198;
      *((_QWORD *)&v116 + 1) = v98;
      *(_QWORD *)&v116 = &v97;
      *(_QWORD *)v98 = &v116;
      v98 = &v116;
      v113 = 0;
      v114 = 0;
      v115 = 0;
      LoggingVolumeDriveLetter = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING(
        (struct _FVEAPI_EVENT_DATA *)&v113,
        v54,
        L"VolumeDriveLetter",
        LoggingVolumeDriveLetter,
        dwCreationDispositionb);
      if ( *(__int128 ****)v98 != &v97 )
        goto LABEL_198;
      *((_QWORD *)&v113 + 1) = v98;
      *(_QWORD *)&v113 = &v97;
      v55 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v95;
      *(_QWORD *)v98 = &v113;
      v98 = &v113;
      v96 = FVE_DE_INITIALIZED_BY_USER;
    }
    else
    {
      v99 = 0;
      v107 = (__int128 *)&v101;
      v108 = (__int128 *)&v101;
      v101 = &v107;
      v102 = (__int128 *)&v107;
      v100 = 0;
      v56 = CFveApiBase::GetLoggingVolumePath(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v116, v57, L"VolumePath", v56, dwCreationDisposition);
      if ( *(__int128 ****)v102 != &v101 )
        goto LABEL_198;
      *((_QWORD *)&v116 + 1) = v102;
      *(_QWORD *)&v116 = &v101;
      *(_QWORD *)v102 = &v116;
      v102 = &v116;
      v113 = 0;
      v114 = 0;
      v115 = 0;
      v58 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING(
        (struct _FVEAPI_EVENT_DATA *)&v113,
        v59,
        L"VolumeDriveLetter",
        v58,
        dwCreationDispositiond);
      if ( *(__int128 ****)v102 != &v101 )
        goto LABEL_198;
      *((_QWORD *)&v113 + 1) = v102;
      *(_QWORD *)&v113 = &v101;
      v55 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v99;
      *(_QWORD *)v102 = &v113;
      v102 = &v113;
      v100 = FVE_DE_INITIALIZED_AUTOMATICALLY;
    }
    FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v80, v55);
    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v80);
    if ( !v74 )
      goto LABEL_184;
    v91 = 0;
    v92 = 0;
    v94 = (__int64 **)&v93;
    v80 = 0;
    v93 = (__int64)&v93;
    v81 = 0;
    v82 = 0;
    v119 = 0;
    v120 = 0;
    v121 = 0;
    v60 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
    FveApiEventLogDeclareWSTRING(
      (struct _FVEAPI_EVENT_DATA *)&v119,
      v61,
      L"VolumeDriveLetter",
      v60,
      dwCreationDispositionc);
    if ( *v94 == &v93 )
    {
      *((_QWORD *)&v119 + 1) = v94;
      *(_QWORD *)&v119 = &v93;
      *v94 = (__int64 *)&v119;
      v109 = L"ProvisioningScenarioGuid";
      v111 = v85;
      v110 = L"GUID";
      v112 = 16;
      if ( (__int64 *)v119 == &v93 )
      {
        *((_QWORD *)&v115 + 1) = 8;
        v108 = &v119;
        *((_QWORD *)&v114 + 1) = L"ULONGLONG";
        *(_QWORD *)&v119 = &v107;
        v105 = v122;
        *(_QWORD *)&v114 = L"DePrecheckInfoBitmask";
        *(_QWORD *)&v113 = &v93;
        *((_QWORD *)&v113 + 1) = &v107;
        v107 = &v113;
        v94 = (__int64 **)&v113;
        *(_QWORD *)&v115 = &v105;
        v116 = 0;
        v117 = 0;
        v118 = 0;
        LoggingServiceName = CFveApiBase::GetLoggingServiceName(this);
        FveApiEventLogDeclareWSTRING(
          (struct _FVEAPI_EVENT_DATA *)&v116,
          v63,
          L"ServiceName",
          LoggingServiceName,
          dwCreationDispositione);
        if ( *v94 == &v93 )
        {
          *((_QWORD *)&v116 + 1) = v94;
          *(_QWORD *)&v116 = &v93;
          *v94 = (__int64 *)&v116;
          v94 = (__int64 **)&v116;
          v92 = FVE_DE_VOLUME_INITIALIZATION_SUCCESS;
          FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v80, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v91);
          FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v80);
          goto LABEL_184;
        }
      }
    }
LABEL_198:
    __fastfail(3u);
  }
  *(_QWORD *)&v114 = L"IdentityGuid";
  *(_QWORD *)&v113 = &v89;
  *((_QWORD *)&v113 + 1) = &v89;
  v89 = &v113;
  *(_QWORD *)&v115 = v20;
  v90 = &v113;
  v87 = 0;
  v88 = 0;
  *((_QWORD *)&v114 + 1) = L"GUID";
  *((_QWORD *)&v115 + 1) = 16;
  v47 = CFveApiBase::GetLoggingVolumePath(this);
  FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v116, v48, L"VolumePath", v47, dwCreationDisposition);
  if ( *(__int128 ***)v90 != &v89 )
    goto LABEL_198;
  *((_QWORD *)&v116 + 1) = v90;
  *(_QWORD *)&v116 = &v89;
  *(_QWORD *)v90 = &v116;
  v90 = &v116;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v49 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
  FveApiEventLogDeclareWSTRING(
    (struct _FVEAPI_EVENT_DATA *)&v119,
    v50,
    L"VolumeDriveLetter",
    v49,
    dwCreationDispositiona);
  if ( *(__int128 ***)v90 != &v89 )
    goto LABEL_198;
  *((_QWORD *)&v119 + 1) = v90;
  *(_QWORD *)&v119 = &v89;
  *(_QWORD *)v90 = &v119;
  v109 = L"hr";
  LODWORD(v106) = v10;
  v110 = L"HRESULT";
  v111 = &v106;
  v112 = 4;
  if ( (__int128 **)v119 != &v89 )
    goto LABEL_198;
  v107 = (__int128 *)&v89;
  v108 = &v119;
  *(_QWORD *)&v119 = &v107;
  v90 = (__int128 *)&v107;
  v88 = FVEAPI_OP_DE_INITIALIZE2_FAILURE;
  FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v80, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v87);
  FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v80);
  if ( v74 )
    CFveApiBase::RevertVolume(this);
LABEL_184:
  if ( v86 )
  {
    CM_Unregister_Notification();
    v86 = 0;
  }
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( EventW )
    CloseHandle(EventW);
  if ( v78 )
  {
    v64 = CFveApiBase::Open(this, v7, 0, 0);
    if ( v64 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        153,
        (unsigned int)&WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
        (_DWORD)v7,
        v64);
  }
  if ( v7 )
    CFveApiBase::FastFree(v7);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180053e94  mov     [rsp-8+arg_8], rbx
0x180053e99  push    rbp
0x180053e9a  push    rsi
0x180053e9b  push    rdi
0x180053e9c  push    r12
0x180053e9e  push    r13
0x180053ea0  push    r14
0x180053ea2  push    r15
0x180053ea4  lea     rbp, [rsp-4B0h]
0x180053eac  sub     rsp, 5B0h
0x180053eb3  mov     rax, cs:__security_cookie
0x180053eba  xor     rax, rsp
0x180053ebd  mov     [rbp+4E0h+var_40], rax
0x180053ec4  mov     rsi, r8
0x180053ec7  mov     [rsp+5E0h+var_568], r8
0x180053ecc  mov     ebx, edx
0x180053ece  mov     [rsp+5E0h+var_598], edx
0x180053ed2  mov     rdi, rcx
0x180053ed5  xor     r14d, r14d
0x180053ed8  xor     edx, edx; Val
0x180053eda  mov     [rsp+5E0h+var_59B], r14b
0x180053edf  mov     r8d, 1A0h; Size
0x180053ee5  mov     [rbp+4E0h+var_560], r14
0x180053ee9  lea     rcx, [rbp+4E0h+var_4D0]; void *
0x180053eed  call    memset_0
0x180053ef2  xor     edx, edx; Val
0x180053ef4  mov     [rsp+5E0h+var_59E], r14b
0x180053ef9  mov     r8d, 208h; Size
0x180053eff  mov     [rsp+5E0h+var_5A0], r14b
0x180053f04  lea     rcx, [rbp+4E0h+FileName]; void *
0x180053f0b  mov     [rsp+5E0h+var_59D], r14b
0x180053f10  mov     r15d, r14d
0x180053f13  mov     [rsp+5E0h+var_59C], r14b
0x180053f18  mov     r12d, r14d
0x180053f1b  mov     [rbp+4E0h+var_328], r14
0x180053f22  mov     r13d, r14d
0x180053f25  mov     [rbp+4E0h+var_330], r14
0x180053f2c  mov     [rsp+5E0h+var_59A], r14b
0x180053f31  mov     [rsp+5E0h+var_59F], 1
0x180053f36  mov     [rsp+5E0h+hObject], 0FFFFFFFFFFFFFFFFh
0x180053f3f  call    memset_0
0x180053f44  lea     rdx, [rbp+4E0h+var_260]; unsigned __int64 *
0x180053f4b  mov     [rbp+4E0h+var_260], r14
0x180053f52  mov     rcx, rsi; struct _GUID *
0x180053f55  call    ?FveCanProvisionDE@@YAHPEBU_GUID@@PEA_K@Z; FveCanProvisionDE(_GUID const *,unsigned __int64 *)
0x180053f5a  test    eax, eax
0x180053f5c  jnz     short loc_180053FA5
0x180053f5e  mov     r9d, 80310009h
0x180053f64  mov     ebx, r9d
0x180053f67  mov     rcx, cs:WPP_GLOBAL_Control
0x180053f6e  lea     rsi, WPP_GLOBAL_Control
0x180053f75  cmp     rcx, rsi
0x180053f78  jz      loc_1800540D2
0x180053f7e  mov     r14b, 40h ; '@'
0x180053f81  test    [rcx+1Ch], r14b
0x180053f85  jz      loc_1800540D2
0x180053f8b  mov     edx, 83h
0x180053f90  mov     rcx, [rcx+10h]
0x180053f94  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x180053f9b  call    WPP_SF_d
0x180053fa0  jmp     loc_1800540D2
0x180053fa5  test    dword ptr [rdi+6Ch], 8000h
0x180053fac  jz      short loc_180053FE1
0x180053fae  mov     ebx, 803100D3h
0x180053fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180053fba  lea     rsi, WPP_GLOBAL_Control
0x180053fc1  cmp     rcx, rsi
0x180053fc4  jz      loc_1800540D2
0x180053fca  mov     r14b, 40h ; '@'
0x180053fcd  test    [rcx+1Ch], r14b
0x180053fd1  jz      loc_1800540D2
0x180053fd7  mov     edx, 84h
0x180053fdc  mov     r9d, ebx
0x180053fdf  jmp     short loc_180053F90
0x180053fe1  test    byte ptr [rdi+6Ch], 1
0x180053fe5  lea     rsi, WPP_GLOBAL_Control
0x180053fec  mov     r14b, 40h ; '@'
0x180053fef  setnz   cl
0x180053ff2  test    bl, 4
0x180053ff5  setz    al
0x180053ff8  test    al, cl
0x180053ffa  jz      loc_18005411D
0x180054000  lea     rdx, aSecurestartupf_3; "SecureStartupFeature-Enabled-DeviceEncr"...
0x180054007  mov     rcx, rdi; this
0x18005400a  call    ?LicenseCheck@CFveApiBase@@QEAAJPEBG@Z; CFveApiBase::LicenseCheck(ushort const *)
0x18005400f  mov     ebx, eax
0x180054011  cmp     eax, 8031005Ah
0x180054016  jnz     loc_1800540EB
0x18005401c  lea     rcx, [rsp+5E0h+var_5A0]; bool *
0x180054021  call    ?NgscbCheckIsUpgradedOS@@YAJPEA_N@Z; NgscbCheckIsUpgradedOS(bool *)
0x180054026  lea     rsi, WPP_GLOBAL_Control
0x18005402d  mov     ebx, eax
0x18005402f  test    eax, eax
0x180054031  jz      short loc_18005406A
0x180054033  mov     rcx, cs:WPP_GLOBAL_Control
0x18005403a  cmp     rcx, rsi
0x18005403d  jz      short loc_180054064
0x18005403f  test    [rcx+1Ch], r14b
0x180054043  jz      short loc_180054064
0x180054045  mov     rcx, [rcx+10h]
0x180054049  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x180054050  mov     edx, 85h
0x180054055  mov     r9d, eax
0x180054058  call    WPP_SF_d
0x18005405d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054064  test    ebx, ebx
0x180054066  js      short loc_1800540D2
0x180054068  jmp     short loc_180054071
0x18005406a  mov     rcx, cs:WPP_GLOBAL_Control
0x180054071  mov     r13b, [rsp+5E0h+var_5A0]
0x180054076  test    r13b, r13b
0x180054079  jz      loc_180054164
0x18005407f  cmp     rcx, rsi
0x180054082  jz      short loc_1800540A6
0x180054084  test    byte ptr [rcx+1Ch], 4
0x180054088  jz      short loc_1800540A6
0x18005408a  mov     rcx, [rcx+10h]
0x18005408e  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x180054095  mov     edx, 86h
0x18005409a  call    WPP_SF_
0x18005409f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800540a6  mov     r9d, 80310009h
0x1800540ac  mov     ebx, r9d
0x1800540af  cmp     rcx, rsi
0x1800540b2  jz      short loc_1800540CF
0x1800540b4  test    [rcx+1Ch], r14b
0x1800540b8  jz      short loc_1800540CF
0x1800540ba  mov     edx, 87h
0x1800540bf  mov     rcx, [rcx+10h]
0x1800540c3  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800540ca  call    WPP_SF_d
0x1800540cf  mov     r13, r12
0x1800540d2  mov     rcx, [rdi+490h]
0x1800540d9  test    rcx, rcx
0x1800540dc  jz      loc_1800547DB
0x1800540e2  add     rcx, 10h
0x1800540e6  jmp     loc_1800547E2
0x1800540eb  test    ebx, ebx
0x1800540ed  jz      short loc_18005411D
0x1800540ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800540f6  cmp     rcx, rsi
0x1800540f9  jz      short loc_180054119
0x1800540fb  test    [rcx+1Ch], r14b
0x1800540ff  jz      short loc_180054119
0x180054101  mov     rcx, [rcx+10h]
0x180054105  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x18005410c  mov     edx, 88h
0x180054111  mov     r9d, ebx
0x180054114  call    WPP_SF_d
0x180054119  test    ebx, ebx
0x18005411b  js      short loc_1800540D2
0x18005411d  lea     rcx, [rsp+5E0h+var_5A0]; bool *
0x180054122  call    ?NgscbCheckIsUpgradedOS@@YAJPEA_N@Z; NgscbCheckIsUpgradedOS(bool *)
0x180054127  mov     ebx, eax
0x180054129  test    eax, eax
0x18005412b  jz      short loc_18005415F
0x18005412d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054134  cmp     rcx, rsi
0x180054137  jz      short loc_180054157
0x180054139  test    [rcx+1Ch], r14b
0x18005413d  jz      short loc_180054157
0x18005413f  mov     rcx, [rcx+10h]
0x180054143  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x18005414a  mov     edx, 89h
0x18005414f  mov     r9d, eax
0x180054152  call    WPP_SF_d
0x180054157  test    ebx, ebx
0x180054159  js      loc_1800540D2
0x18005415f  mov     r13b, [rsp+5E0h+var_5A0]
0x180054164  mov     rcx, rdi; this
0x180054167  call    ?ResolveVolumeMountName@CFveApiBase@@QEAAJXZ; CFveApiBase::ResolveVolumeMountName(void)
0x18005416c  mov     ebx, eax
0x18005416e  test    eax, eax
0x180054170  jz      short loc_1800541A4
0x180054172  mov     rcx, cs:WPP_GLOBAL_Control
0x180054179  cmp     rcx, rsi
0x18005417c  jz      short loc_18005419C
0x18005417e  test    [rcx+1Ch], r14b
0x180054182  jz      short loc_18005419C
0x180054184  mov     rcx, [rcx+10h]
0x180054188  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x18005418f  mov     edx, 8Ah
0x180054194  mov     r9d, eax
0x180054197  call    WPP_SF_d
0x18005419c  test    ebx, ebx
0x18005419e  js      loc_1800540CF
0x1800541a4  mov     rcx, [rdi+188h]; unsigned __int16 *
0x1800541ab  lea     rdx, [rsp+5E0h+var_59D]; bool *
0x1800541b0  call    ?NgscbCheckDeviceEncryptionOptedOutForVolume@@YAJPEBGPEA_N@Z; NgscbCheckDeviceEncryptionOptedOutForVolume(ushort const *,bool *)
0x1800541b5  mov     ebx, eax
0x1800541b7  test    eax, eax
0x1800541b9  jz      short loc_1800541F6
0x1800541bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541c2  cmp     rcx, rsi
0x1800541c5  jz      short loc_1800541EC
0x1800541c7  test    [rcx+1Ch], r14b
0x1800541cb  jz      short loc_1800541EC
0x1800541cd  mov     rcx, [rcx+10h]
0x1800541d1  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800541d8  mov     edx, 8Bh
0x1800541dd  mov     r9d, eax
0x1800541e0  call    WPP_SF_d
0x1800541e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541ec  test    ebx, ebx
0x1800541ee  js      loc_1800540CF
0x1800541f4  jmp     short loc_1800541FD
0x1800541f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541fd  cmp     [rsp+5E0h+var_59D], r12b
0x180054202  jz      short loc_180054229
0x180054204  mov     ebx, 803100D2h
0x180054209  cmp     rcx, rsi
0x18005420c  jz      loc_1800540CF
0x180054212  test    [rcx+1Ch], r14b
0x180054216  jz      loc_1800540CF
0x18005421c  mov     edx, 8Ch
0x180054221  mov     r9d, ebx
0x180054224  jmp     loc_1800540BF
0x180054229  cmp     [rdi+486h], r12b
0x180054230  jnz     short loc_1800542B0
0x180054232  cmp     rcx, rsi
0x180054235  jz      short loc_180054252
0x180054237  test    byte ptr [rcx+1Ch], 4
0x18005423b  jz      short loc_180054252
0x18005423d  mov     rcx, [rcx+10h]
0x180054241  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x180054248  mov     edx, 8Dh
0x18005424d  call    WPP_SF_
0x180054252  lea     rdx, [rbp+4E0h+var_328]; unsigned __int16 **
0x180054259  mov     rcx, rdi; this
0x18005425c  call    ?ReopenWritable@CFveApi@@AEAAJPEAPEAG@Z; CFveApi::ReopenWritable(ushort * *)
0x180054261  mov     ebx, eax
0x180054263  test    eax, eax
0x180054265  jz      short loc_1800542A4
0x180054267  mov     rcx, cs:WPP_GLOBAL_Control
0x18005426e  cmp     rcx, rsi
0x180054271  jz      short loc_180054291
0x180054273  test    [rcx+1Ch], r14b
0x180054277  jz      short loc_180054291
0x180054279  mov     rcx, [rcx+10h]
0x18005427d  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x180054284  mov     edx, 8Eh
0x180054289  mov     r9d, eax
0x18005428c  call    WPP_SF_d
0x180054291  test    ebx, ebx
0x180054293  jns     short loc_1800542A4
0x180054295  mov     r12, [rbp+4E0h+var_328]
0x18005429c  mov     r13, r15
0x18005429f  jmp     loc_1800540D2
0x1800542a4  mov     r12, [rbp+4E0h+var_328]
0x1800542ab  mov     [rsp+5E0h+var_59A], 1
0x1800542b0  lea     r9, [rsp+5E0h+var_59F]; bool *
0x1800542b5  xor     r8d, r8d; bool
0x1800542b8  mov     dl, 1; bool
0x1800542ba  mov     rcx, rdi; this
0x1800542bd  call    ?CheckDataOnlyPolicy@CFveApi@@QEAAJ_N0PEA_N@Z; CFveApi::CheckDataOnlyPolicy(bool,bool,bool *)
0x1800542c2  mov     ebx, eax
0x1800542c4  test    eax, eax
0x1800542c6  jz      short loc_1800542F6
0x1800542c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800542cf  cmp     rcx, rsi
0x1800542d2  jz      short loc_1800542F2
0x1800542d4  test    [rcx+1Ch], r14b
0x1800542d8  jz      short loc_1800542F2
0x1800542da  mov     rcx, [rcx+10h]
0x1800542de  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800542e5  mov     edx, 8Fh
0x1800542ea  mov     r9d, eax
0x1800542ed  call    WPP_SF_d
0x1800542f2  test    ebx, ebx
0x1800542f4  js      short loc_18005429C
0x1800542f6  cmp     [rsp+5E0h+var_59F], r15b
0x1800542fb  mov     ecx, 10100h
0x180054300  mov     ebx, [rsp+5E0h+var_598]
0x180054304  mov     eax, 10000h
0x180054309  cmovnz  eax, ecx
0x18005430c  mov     edx, ebx
0x18005430e  and     edx, 8
0x180054311  mov     ecx, eax
0x180054313  or      ecx, 20100h
0x180054319  mov     dword ptr [rbp+4E0h+var_328], edx
0x18005431f  test    edx, edx
0x180054321  cmovz   ecx, eax
0x180054324  mov     eax, ebx
0x180054326  mov     edx, ecx
0x180054328  bts     edx, 12h
0x18005432c  test    bl, 10h
0x18005432f  cmovz   edx, ecx
0x180054332  mov     ecx, edx
0x180054334  bts     ecx, 16h
0x180054338  bt      ebx, 8
0x18005433c  cmovnb  ecx, edx
0x18005433f  mov     edx, ecx
0x180054341  bts     edx, 13h
0x180054345  test    bl, 20h
0x180054348  cmovz   edx, ecx
0x18005434b  mov     ecx, edx
0x18005434d  bts     ecx, 14h
0x180054351  test    r14b, bl
0x180054354  cmovz   ecx, edx
0x180054357  mov     r8d, ecx
  ... truncated ...
```
