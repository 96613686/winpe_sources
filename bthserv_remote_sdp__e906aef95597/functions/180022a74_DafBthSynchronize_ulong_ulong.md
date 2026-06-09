# DafBthSynchronize(ulong *,ulong *)

- ea: `0x180022a74`
- end: `0x180023546`
- name: `?DafBthSynchronize@@YAJPEAK0@Z`
- size: `2770`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000d498`
- `0x18000e210`
- `0x180010f60`

## callees

- `0x1800017a0`
- `0x180002558`
- `0x1800026d0`
- `0x18000270c`
- `0x1800223c0`
- `0x1800227f4`
- `0x180022a74`
- `0x18002354c`
- `0x18002359c`
- `0x180023628`
- `0x18002368c`
- `0x180023734`
- `0x1800237a0`
- `0x180023a84`
- `0x180023da8`
- `0x180024014`
- `0x18002424c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022e9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180022e9a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022d06`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002346d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800234d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002346d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800234d1`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180022eab`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002344e`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180022eab`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18002344e`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x180022e5b`
- `api-ms-win-devices-query-l1-1-1!DevCreateObjectQueryEx` at `0x180022e5b`

## pseudocode

```c
__int64 __fastcall DafBthSynchronize(unsigned int *a1, unsigned int *a2)
{
  _DWORD *v4; // rsi
  __int64 v5; // rcx
  signed int LastError; // eax
  int v7; // r9d
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  int v10; // edx
  int LocalDeviceInfo; // eax
  _QWORD *v12; // rcx
  int v13; // edx
  char *v14; // r15
  void **v15; // r14
  _QWORD *v16; // rbx
  int v17; // esi
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rax
  char *v22; // rcx
  int DeviceAddressAndTypeFromAepId; // eax
  int DeviceInfo; // edi
  int v25; // r15d
  int DeviceInfoList; // eax
  int v27; // r8d
  unsigned int v28; // eax
  _QWORD *v29; // rdi
  __int64 v30; // r15
  __int64 v31; // rax
  struct _BTH_DEVICE_INFO_V3 *v32; // r12
  void **v33; // r14
  char v34; // r13
  _DWORD *v35; // r15
  __int64 v36; // rax
  char *v37; // rcx
  int v38; // eax
  int OfflineAep; // eax
  unsigned int *v40; // r14
  int v41; // eax
  void *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  bool v45; // cf
  char v47; // [rsp+60h] [rbp-A0h] BYREF
  char v48; // [rsp+61h] [rbp-9Fh]
  int v49; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  __int64 v51; // [rsp+70h] [rbp-90h]
  __int64 v52; // [rsp+78h] [rbp-88h]
  _DWORD *v53; // [rsp+80h] [rbp-80h]
  __int64 v54; // [rsp+88h] [rbp-78h]
  HANDLE hHandle; // [rsp+90h] [rbp-70h]
  void *Block[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int *v57; // [rsp+A8h] [rbp-58h]
  __int64 v58; // [rsp+B0h] [rbp-50h]
  struct _BTH_DEVICE_INFO_V3 *v59; // [rsp+B8h] [rbp-48h]
  int v60; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v61[103]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v62; // [rsp+400h] [rbp+300h]
  int v63; // [rsp+410h] [rbp+310h]
  int v64; // [rsp+414h] [rbp+314h]
  __int64 v65; // [rsp+418h] [rbp+318h]
  char *v66; // [rsp+420h] [rbp+320h]
  __int64 OutBuffer; // [rsp+430h] [rbp+330h] BYREF
  __int64 v68[37]; // [rsp+438h] [rbp+338h] BYREF
  int v69; // [rsp+560h] [rbp+460h]
  int v70; // [rsp+568h] [rbp+468h]
  __int128 v71; // [rsp+56Ch] [rbp+46Ch]
  __int128 v72; // [rsp+57Ch] [rbp+47Ch]
  __int64 v73; // [rsp+58Ch] [rbp+48Ch]
  int v74; // [rsp+594h] [rbp+494h]
  int v75; // [rsp+598h] [rbp+498h]
  __int128 v76; // [rsp+5A0h] [rbp+4A0h]
  int v77; // [rsp+5B0h] [rbp+4B0h]
  int v78; // [rsp+5B4h] [rbp+4B4h]
  __int64 v79; // [rsp+5B8h] [rbp+4B8h]
  int v80; // [rsp+5C0h] [rbp+4C0h]
  int v81; // [rsp+5C4h] [rbp+4C4h]
  char *v82; // [rsp+5C8h] [rbp+4C8h]
  int v83; // [rsp+5D0h] [rbp+4D0h]
  int v84; // [rsp+5D8h] [rbp+4D8h]
  __int128 v85; // [rsp+5DCh] [rbp+4DCh]
  __int128 v86; // [rsp+5ECh] [rbp+4ECh]
  __int64 v87; // [rsp+5FCh] [rbp+4FCh]
  int v88; // [rsp+604h] [rbp+504h]
  int v89; // [rsp+608h] [rbp+508h]
  __int128 v90; // [rsp+610h] [rbp+510h]
  int v91; // [rsp+620h] [rbp+520h]
  int v92; // [rsp+624h] [rbp+524h]
  __int64 v93; // [rsp+628h] [rbp+528h]
  int v94; // [rsp+630h] [rbp+530h]
  int v95; // [rsp+634h] [rbp+534h]
  const struct _GUID *v96; // [rsp+638h] [rbp+538h]
  int v97; // [rsp+640h] [rbp+540h]
  __int128 v98; // [rsp+648h] [rbp+548h]
  int v99; // [rsp+658h] [rbp+558h]
  int v100; // [rsp+65Ch] [rbp+55Ch]
  __int64 v101; // [rsp+660h] [rbp+560h]
  __int64 v102; // [rsp+668h] [rbp+568h]
  const struct _GUID *v103; // [rsp+670h] [rbp+570h]
  int v104; // [rsp+678h] [rbp+578h]
  int v105; // [rsp+680h] [rbp+580h]
  __int128 v106; // [rsp+684h] [rbp+584h]
  __int128 v107; // [rsp+694h] [rbp+594h]
  __int64 v108; // [rsp+6A4h] [rbp+5A4h]
  int v109; // [rsp+6ACh] [rbp+5ACh]
  int v110; // [rsp+6B0h] [rbp+5B0h]
  int v111; // [rsp+6B8h] [rbp+5B8h]
  __int128 v112; // [rsp+6BCh] [rbp+5BCh]
  __int128 v113; // [rsp+6CCh] [rbp+5CCh]
  __int64 v114; // [rsp+6DCh] [rbp+5DCh]
  int v115; // [rsp+6E4h] [rbp+5E4h]

  v57 = a1;
  v52 = 0;
  hObject = 0;
  v54 = 0;
  hHandle = 0;
  v53 = 0;
  v4 = 0;
  OutBuffer = 0;
  memset_0(v68, 0, 0x11Cu);
  v47 = -1;
  v73 = 0;
  v74 = 0;
  v77 = 16;
  v71 = 0;
  v69 = 0x100000;
  v72 = 0;
  v82 = &v47;
  v87 = 0;
  v88 = 0;
  v76 = DEVPKEY_Aep_IsAssociated;
  v85 = 0;
  v91 = 5;
  v86 = 0;
  v99 = 5;
  v103 = &DAF_ProtocolId_BluetoothLE;
  v108 = 0;
  v90 = DEVPKEY_Aep_ProtocolId;
  v98 = DEVPKEY_Aep_ProtocolId;
  v109 = 0;
  v114 = 0;
  v106 = 0;
  v115 = 0;
  v107 = 0;
  v70 = 0;
  v112 = 0;
  v75 = 2;
  v113 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 17;
  v81 = 1;
  v83 = 3145728;
  v84 = 0;
  v89 = 2;
  v92 = 0;
  v93 = 0;
  v94 = 13;
  v95 = 16;
  v96 = &DAF_ProtocolId_Bluetooth;
  v97 = 2;
  v100 = 0;
  v101 = 0;
  v102 = 0x100000000DLL;
  v104 = 0x400000;
  v105 = 0;
  v110 = 0x200000;
  v111 = 0;
  v63 = 4;
  v66 = &v47;
  v62 = DEVPKEY_DasParam_AepStoreOnly;
  v64 = 17;
  v65 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  *a1 = 0;
  Block[1] = Block;
  *a2 = 0;
  Block[0] = Block;
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_126;
    v10 = 18;
    goto LABEL_10;
  }
  LocalDeviceInfo = BthDevnodeOpenInterfaceHandle(v5, 0x40000000, &hObject);
  v8 = LocalDeviceInfo;
  if ( LocalDeviceInfo < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_126;
    v13 = 19;
    goto LABEL_15;
  }
  v14 = (char *)hObject;
  LocalDeviceInfo = DafBthGetLocalDeviceInfo(hObject, &OutBuffer);
  v8 = LocalDeviceInfo;
  if ( LocalDeviceInfo < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_126;
    v13 = 20;
    goto LABEL_15;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  LocalDeviceInfo = DevCreateObjectQueryEx(5, 3, 0, 0);
  v8 = LocalDeviceInfo;
  if ( LocalDeviceInfo < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_126;
    v13 = 22;
LABEL_15:
    WPP_SF_sd(v12[2], v13, (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids, v7, LocalDeviceInfo);
    goto LABEL_126;
  }
  WaitForSingleObject(hHandle, 0x2710u);
  DevCloseObjectQuery(v52);
  v8 = v54;
  v52 = 0;
  if ( (int)v54 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_129;
    v10 = 23;
LABEL_10:
    WPP_SF_sd(v9[2], v10, (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids, v7, v8);
    goto LABEL_126;
  }
  v15 = (void **)Block[0];
  v16 = WPP_GLOBAL_Control;
  while ( v15 != Block )
  {
    v49 = 0;
    v17 = 0;
    memset_0(&v60, 0, 0x340u);
    v21 = -1;
    v51 = 0;
    do
      ++v21;
    while ( *((_WORD *)v15 + v21 + 9) );
    if ( (_DWORD)v21 == 54 )
    {
      v22 = (char *)v15 + 38;
LABEL_39:
      DeviceAddressAndTypeFromAepId = DafBthGetDeviceAddressAndTypeFromAepIdEx(v22, &v49, v61);
      v16 = WPP_GLOBAL_Control;
      DeviceInfo = DeviceAddressAndTypeFromAepId;
      v17 = v49;
      goto LABEL_44;
    }
    if ( (_DWORD)v21 == 58 )
    {
      v22 = (char *)v15 + 42;
      goto LABEL_39;
    }
    if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 2u )
    {
      WPP_SF_s(v16[2], 24, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    DeviceInfo = -2147467259;
LABEL_44:
    if ( v51 == v68[0] )
    {
      if ( DeviceInfo < 0 )
        goto LABEL_69;
      DeviceInfo = DafBthGetDeviceInfo(v14);
      if ( DeviceInfo < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        goto LABEL_69;
      }
      v25 = v60;
      if ( v17 )
        goto LABEL_55;
      if ( (v60 & 0x18) != 0 )
      {
        v16 = WPP_GLOBAL_Control;
        v14 = (char *)hObject;
        goto LABEL_74;
      }
      DeviceInfo = -2140930033;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_72;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        goto LABEL_69;
      WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v19, v20, (__int64)v15 + 18);
LABEL_55:
      if ( v17 == 1 )
      {
        if ( (v25 & 0x18) != 0 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v19, v20, (__int64)v15 + 18);
            goto LABEL_60;
          }
LABEL_61:
          if ( DeviceInfo >= 0 )
          {
            v14 = (char *)hObject;
            goto LABEL_74;
          }
LABEL_69:
          if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 2u )
            WPP_SF_sdS(v16[2], v18, v19, v20, DeviceInfo, (__int64)v15 + 18);
          goto LABEL_72;
        }
        if ( (v25 & 0x30000) == 0 )
        {
          LOBYTE(DeviceInfo) = 15;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v19, v20, (__int64)v15 + 18);
              v16 = WPP_GLOBAL_Control;
            }
            goto LABEL_69;
          }
LABEL_72:
          DafBthSyncRemoveAep((unsigned __int16 *)v15 + 9);
          v14 = (char *)hObject;
          *((_BYTE *)v15 + 16) = 1;
          ++*a2;
          goto LABEL_73;
        }
      }
LABEL_60:
      v16 = WPP_GLOBAL_Control;
      goto LABEL_61;
    }
    if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 4u )
    {
      WPP_SF_s(v16[2], 25, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
LABEL_73:
      v16 = WPP_GLOBAL_Control;
    }
LABEL_74:
    v15 = (void **)*v15;
  }
  if ( v16 != &WPP_GLOBAL_Control && *((_BYTE *)v16 + 25) >= 4u )
    WPP_SF_s(v16[2], 30, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
  DeviceInfoList = DafBthGetDeviceInfoListEx(v14);
  v4 = v53;
  v8 = DeviceInfoList;
  if ( DeviceInfoList < 0 )
    goto LABEL_126;
  v28 = 0;
  LODWORD(v51) = 0;
  if ( !v53[4] )
    goto LABEL_126;
  v29 = WPP_GLOBAL_Control;
  do
  {
    v30 = v28;
    v31 = 208LL * v28;
    v58 = v30;
    v32 = (struct _BTH_DEVICE_INFO_V3 *)&v4[v31 + 6];
    v53 = (_DWORD *)(v31 * 4);
    v59 = v32;
    if ( (*(_DWORD *)v32 & 0x30018) == 0 )
      goto LABEL_125;
    v33 = (void **)Block[0];
    v7 = 0;
    v48 = 0;
    v34 = 0;
    if ( Block[0] == Block )
      goto LABEL_104;
    v35 = v53;
    do
    {
      v49 = 0;
      memset_0(&v60, 0, 0x340u);
      v7 = 0;
      if ( *((_BYTE *)v33 + 16) )
        goto LABEL_102;
      v36 = -1;
      do
        ++v36;
      while ( *((_WORD *)v33 + v36 + 9) );
      if ( (_DWORD)v36 == 54 )
      {
        v37 = (char *)v33 + 38;
        goto LABEL_91;
      }
      if ( (_DWORD)v36 == 58 )
      {
        v37 = (char *)v33 + 42;
LABEL_91:
        v38 = DafBthGetDeviceAddressAndTypeFromAepIdEx(v37, &v49, v61);
        v7 = 0;
        v8 = v38;
        if ( v38 >= 0 && v61[0] == *(_QWORD *)((char *)v4 + (_QWORD)v35 + 32) )
        {
          if ( v49 )
          {
            if ( v49 == 1 )
              v48 = 1;
          }
          else
          {
            v34 = 1;
          }
        }
        v29 = WPP_GLOBAL_Control;
        goto LABEL_102;
      }
      if ( v29 != &WPP_GLOBAL_Control && *((_BYTE *)v29 + 25) >= 2u )
      {
        WPP_SF_s(v29[2], 31, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids);
        v29 = WPP_GLOBAL_Control;
        v7 = 0;
      }
      v8 = -2140930033;
LABEL_102:
      v33 = (void **)*v33;
    }
    while ( v33 != Block );
    v30 = v58;
    v32 = v59;
    if ( v34 )
      goto LABEL_114;
LABEL_104:
    if ( (*(_DWORD *)v32 & 0x18) == 0 || (*(_DWORD *)v32 & 0x4000) == 0 )
    {
LABEL_114:
      v40 = v57;
      goto LABEL_115;
    }
    if ( v29 != &WPP_GLOBAL_Control && *((_BYTE *)v29 + 25) >= 4u )
      WPP_SF_si(v29[2], 32, v27, 0, *(_QWORD *)&v4[208 * v30 + 8]);
    OfflineAep = DafBthSyncCreateOfflineAep(&DAF_ProtocolId_Bluetooth, v32);
    v7 = 0;
    v8 = OfflineAep;
    if ( OfflineAep < 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids,
          0,
          OfflineAep);
        goto LABEL_112;
      }
      goto LABEL_125;
    }
    v40 = v57;
    ++*v57;
    v29 = WPP_GLOBAL_Control;
LABEL_115:
    if ( !v48 && (((v4[208 * v30 + 6] & 0x30000) != 0) & _bittest(&v4[208 * v30 + 6], 0xFu)) != 0 )
    {
      if ( v29 != &WPP_GLOBAL_Control && *((_BYTE *)v29 + 25) >= 4u )
        WPP_SF_si(v29[2], 34, v27, 0, *(_QWORD *)&v4[208 * v30 + 8]);
      v41 = DafBthSyncCreateOfflineAep(&DAF_ProtocolId_BluetoothLE, v32);
      v8 = v41;
      if ( v41 >= 0 )
      {
        ++*v40;
        v29 = WPP_GLOBAL_Control;
      }
      else
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids,
            v7,
            v41);
LABEL_112:
          v29 = WPP_GLOBAL_Control;
        }
      }
    }
LABEL_125:
    v28 = v51 + 1;
    LODWORD(v51) = v28;
  }
  while ( v28 < v4[4] );
LABEL_126:
  if ( v52 )
  {
    DevCloseObjectQuery(v52);
    v52 = 0;
  }
  v14 = (char *)hObject;
LABEL_129:
  if ( hHandle )
  {
    CloseHandle(hHandle);
    hHandle = 0;
  }
  while ( 1 )
  {
    v42 = Block[0];
    if ( Block[0] == Block )
      break;
    if ( *((void ***)Block[0] + 1) != Block
      || (v43 = *(_QWORD *)Block[0], *(void **)(*(_QWORD *)Block[0] + 8LL) != Block[0]) )
    {
      __fastfail(3u);
    }
    Block[0] = *(void **)Block[0];
    *(_QWORD *)(v43 + 8) = Block;
    free(v42);
  }
  if ( v4 )
    operator delete(v4);
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v14);
  v44 = 0;
  if ( v8 )
    v45 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v45 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v44) = !v45;
    if ( v44 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        (unsigned int)WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids,
        v7,
        v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180022a74  mov     [rsp-8+arg_10], rbx
0x180022a79  push    rbp
0x180022a7a  push    rsi
0x180022a7b  push    rdi
0x180022a7c  push    r12
0x180022a7e  push    r13
0x180022a80  push    r14
0x180022a82  push    r15
0x180022a84  lea     rbp, [rsp-600h]
0x180022a8c  sub     rsp, 700h
0x180022a93  mov     rax, cs:__security_cookie
0x180022a9a  xor     rax, rsp
0x180022a9d  mov     [rbp+630h+var_40], rax
0x180022aa4  xor     edi, edi
0x180022aa6  mov     [rbp+630h+var_688], rcx
0x180022aaa  mov     r13, rdx
0x180022aad  mov     [rsp+730h+var_6B8], rdi
0x180022ab2  mov     rbx, rcx
0x180022ab5  mov     [rsp+730h+hObject], rdi
0x180022aba  xor     edx, edx; Val
0x180022abc  mov     [rbp+630h+var_6A8], rdi
0x180022ac0  lea     rcx, [rbp+630h+var_2F8]; void *
0x180022ac7  mov     [rbp+630h+hHandle], rdi
0x180022acb  mov     r8d, 11Ch; Size
0x180022ad1  mov     [rbp+630h+var_6B0], rdi
0x180022ad5  mov     esi, edi
0x180022ad7  mov     [rbp+630h+OutBuffer], rdi
0x180022ade  call    memset_0
0x180022ae3  xor     eax, eax
0x180022ae5  mov     [rsp+730h+var_6D0], 0FFh
0x180022aea  xorps   xmm0, xmm0
0x180022aed  mov     [rbp+630h+var_1A4], rax
0x180022af4  mov     [rbp+630h+var_19C], eax
0x180022afa  lea     edx, [rdi+0Dh]
0x180022afd  mov     eax, cs:dword_18003E220
0x180022b03  lea     ecx, [rdi+10h]
0x180022b06  mov     [rbp+630h+var_180], eax
0x180022b0c  lea     r8d, [rdi+11h]
0x180022b10  movups  [rbp+630h+var_1C4], xmm0
0x180022b17  lea     rax, [rsp+730h+var_6D0]
0x180022b1c  mov     [rbp+630h+var_1D0], 100000h
0x180022b26  movups  [rbp+630h+var_1B4], xmm0
0x180022b2d  mov     [rbp+630h+var_168], rax
0x180022b34  xor     eax, eax
0x180022b36  movups  xmm0, cs:DEVPKEY_Aep_IsAssociated
0x180022b3d  mov     [rbp+630h+var_134], rax
0x180022b44  lea     r12d, [rdi+1]
0x180022b48  mov     [rbp+630h+var_12C], eax
0x180022b4e  lea     r9, DAF_ProtocolId_Bluetooth
0x180022b55  mov     eax, cs:dword_18003E208
0x180022b5b  movaps  [rbp+630h+var_190], xmm0
0x180022b62  xorps   xmm0, xmm0
0x180022b65  movups  [rbp+630h+var_154], xmm0
0x180022b6c  mov     [rbp+630h+var_110], eax
0x180022b72  movups  [rbp+630h+var_144], xmm0
0x180022b79  mov     [rbp+630h+var_D8], eax
0x180022b7f  lea     rax, DAF_ProtocolId_BluetoothLE
0x180022b86  movups  xmm0, cs:DEVPKEY_Aep_ProtocolId
0x180022b8d  mov     [rbp+630h+var_C0], rax
0x180022b94  xor     eax, eax
0x180022b96  mov     [rbp+630h+var_8C], rax
0x180022b9d  movaps  [rbp+630h+var_120], xmm0
0x180022ba4  movups  [rbp+630h+var_E8], xmm0
0x180022bab  mov     [rbp+630h+var_84], eax
0x180022bb1  xorps   xmm0, xmm0
0x180022bb4  mov     [rbp+630h+var_54], rax
0x180022bbb  movups  [rbp+630h+var_AC], xmm0
0x180022bc2  mov     [rbp+630h+var_4C], eax
0x180022bc8  movups  [rbp+630h+var_9C], xmm0
0x180022bcf  mov     [rbp+630h+var_1C8], edi
0x180022bd5  movups  [rbp+630h+var_74], xmm0
0x180022bdc  mov     [rbp+630h+var_198], 2
0x180022be6  movups  [rbp+630h+var_64], xmm0
0x180022bed  mov     [rbp+630h+var_17C], edi
0x180022bf3  mov     [rbp+630h+var_178], rdi
0x180022bfa  mov     [rbp+630h+var_170], r8d
0x180022c01  mov     [rbp+630h+var_16C], r12d
0x180022c08  mov     [rbp+630h+var_160], 300000h
0x180022c12  mov     [rbp+630h+var_158], edi
0x180022c18  mov     [rbp+630h+var_128], 2
0x180022c22  mov     [rbp+630h+var_10C], edi
0x180022c28  mov     [rbp+630h+var_108], rdi
0x180022c2f  mov     [rbp+630h+var_100], edx
0x180022c35  mov     [rbp+630h+var_FC], ecx
0x180022c3b  mov     [rbp+630h+var_F8], r9
0x180022c42  mov     [rbp+630h+var_F0], 2
0x180022c4c  mov     [rbp+630h+var_D4], edi
0x180022c52  mov     [rbp+630h+var_D0], rdi
0x180022c59  mov     dword ptr [rbp+630h+var_C8], edx
0x180022c5f  mov     dword ptr [rbp+630h+var_C8+4], ecx
0x180022c65  mov     [rbp+630h+var_B8], 400000h
0x180022c6f  mov     [rbp+630h+var_B0], edi
0x180022c75  mov     [rbp+630h+var_80], 200000h
0x180022c7f  mov     [rbp+630h+var_78], edi
0x180022c85  mov     eax, cs:dword_18003E1D0
0x180022c8b  movups  xmm0, cs:DEVPKEY_DasParam_AepStoreOnly
0x180022c92  mov     [rbp+630h+var_320], eax
0x180022c98  lea     rax, [rsp+730h+var_6D0]
0x180022c9d  mov     [rbp+630h+var_310], rax
0x180022ca4  movups  [rbp+630h+var_330], xmm0
0x180022cab  mov     [rbp+630h+var_31C], r8d
0x180022cb2  mov     [rbp+630h+var_318], r12
0x180022cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cc0  lea     r14, WPP_GLOBAL_Control
0x180022cc7  cmp     rcx, r14
0x180022cca  jz      short loc_180022CE5
0x180022ccc  cmp     byte ptr [rcx+19h], 5
0x180022cd0  jb      short loc_180022CE5
0x180022cd2  mov     rcx, [rcx+10h]
0x180022cd6  mov     edx, r8d
0x180022cd9  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180022ce0  call    WPP_SF_s
0x180022ce5  lea     rax, [rbp+630h+Block]
0x180022ce9  mov     [rbx], edi
0x180022ceb  mov     [rbp+630h+var_690], rax
0x180022cef  xor     r9d, r9d; lpName
0x180022cf2  lea     rax, [rbp+630h+Block]
0x180022cf6  mov     [r13+0], edi
0x180022cfa  xor     r8d, r8d; bInitialState
0x180022cfd  mov     [rbp+630h+Block], rax
0x180022d01  mov     edx, r12d; bManualReset
0x180022d04  xor     ecx, ecx; lpEventAttributes
0x180022d06  call    cs:__imp_CreateEventW
0x180022d0d  nop     dword ptr [rax+rax+00h]
0x180022d12  mov     [rbp+630h+hHandle], rax
0x180022d16  test    rax, rax
0x180022d19  jnz     short loc_180022D6E
0x180022d1b  call    cs:__imp_GetLastError
0x180022d22  nop     dword ptr [rax+rax+00h]
0x180022d27  mov     ebx, eax
0x180022d29  test    eax, eax
0x180022d2b  jle     short loc_180022D36
0x180022d2d  movzx   ebx, ax
0x180022d30  or      ebx, 80070000h
0x180022d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d3d  cmp     rcx, r14
0x180022d40  jz      loc_180023444
0x180022d46  cmp     byte ptr [rcx+19h], 2
0x180022d4a  jb      loc_180023444
0x180022d50  mov     edx, 12h
0x180022d55  mov     dword ptr [rsp+730h+var_710], ebx
0x180022d59  mov     rcx, [rcx+10h]
0x180022d5d  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180022d64  call    WPP_SF_sd
0x180022d69  jmp     loc_180023444
0x180022d6e  lea     r8, [rsp+730h+hObject]
0x180022d73  mov     edx, 40000000h
0x180022d78  call    BthDevnodeOpenInterfaceHandle
0x180022d7d  mov     ebx, eax
0x180022d7f  test    eax, eax
0x180022d81  jns     short loc_180022DA8
0x180022d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180022d8a  cmp     rcx, r14
0x180022d8d  jz      loc_180023444
0x180022d93  cmp     byte ptr [rcx+19h], 2
0x180022d97  jb      loc_180023444
0x180022d9d  mov     edx, 13h
0x180022da2  mov     dword ptr [rsp+730h+var_710], eax
0x180022da6  jmp     short loc_180022D59
0x180022da8  mov     r15, [rsp+730h+hObject]
0x180022dad  lea     rdx, [rbp+630h+OutBuffer]; lpOutBuffer
0x180022db4  mov     rcx, r15; hFile
0x180022db7  call    DafBthGetLocalDeviceInfo
0x180022dbc  mov     ebx, eax
0x180022dbe  test    eax, eax
0x180022dc0  jns     short loc_180022DE3
0x180022dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dc9  cmp     rcx, r14
0x180022dcc  jz      loc_180023444
0x180022dd2  cmp     byte ptr [rcx+19h], 2
0x180022dd6  jb      loc_180023444
0x180022ddc  mov     edx, 14h
0x180022de1  jmp     short loc_180022DA2
0x180022de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dea  cmp     rcx, r14
0x180022ded  jz      short loc_180022E0A
0x180022def  cmp     byte ptr [rcx+19h], 4
0x180022df3  jb      short loc_180022E0A
0x180022df5  mov     rcx, [rcx+10h]
0x180022df9  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180022e00  mov     edx, 15h
0x180022e05  call    WPP_SF_s
0x180022e0a  lea     rax, [rsp+730h+var_6B8]
0x180022e0f  xor     r9d, r9d
0x180022e12  mov     [rsp+730h+var_6E0], rax
0x180022e17  xor     r8d, r8d
0x180022e1a  lea     rax, [rbp+630h+var_6A8]
0x180022e1e  mov     [rsp+730h+var_6E8], rax
0x180022e23  lea     rax, ?DafBthSyncAepQueryCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DafBthSyncAepQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180022e2a  mov     [rsp+730h+var_6F0], rax
0x180022e2f  lea     edx, [r9+3]
0x180022e33  lea     rax, [rbp+630h+var_330]
0x180022e3a  mov     [rsp+730h+var_6F8], rax
0x180022e3f  lea     ecx, [rdx+2]
0x180022e42  lea     rax, [rbp+630h+var_1D0]
0x180022e49  mov     [rsp+730h+var_700], r12d
0x180022e4e  mov     [rsp+730h+var_708], rax
0x180022e53  mov     dword ptr [rsp+730h+var_710], 7
0x180022e5b  call    cs:__imp_DevCreateObjectQueryEx
0x180022e62  nop     dword ptr [rax+rax+00h]
0x180022e67  mov     ebx, eax
0x180022e69  test    eax, eax
0x180022e6b  jns     short loc_180022E91
0x180022e6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e74  cmp     rcx, r14
0x180022e77  jz      loc_180023444
0x180022e7d  cmp     byte ptr [rcx+19h], 2
0x180022e81  jb      loc_180023444
0x180022e87  mov     edx, 16h
0x180022e8c  jmp     loc_180022DA2
0x180022e91  mov     rcx, [rbp+630h+hHandle]; hHandle
0x180022e95  mov     edx, 2710h; dwMilliseconds
0x180022e9a  call    cs:__imp_WaitForSingleObject
0x180022ea1  nop     dword ptr [rax+rax+00h]
0x180022ea6  mov     rcx, [rsp+730h+var_6B8]
0x180022eab  call    cs:__imp_DevCloseObjectQuery
0x180022eb2  nop     dword ptr [rax+rax+00h]
0x180022eb7  mov     rbx, [rbp+630h+var_6A8]
0x180022ebb  mov     [rsp+730h+var_6B8], rdi
0x180022ec0  test    ebx, ebx
0x180022ec2  jns     short loc_180022EE8
0x180022ec4  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ecb  cmp     rcx, r14
0x180022ece  jz      loc_180023464
0x180022ed4  cmp     byte ptr [rcx+19h], 2
0x180022ed8  jb      loc_180023464
0x180022ede  mov     edx, 17h
0x180022ee3  jmp     loc_180022D55
0x180022ee8  mov     r14, [rbp+630h+Block]
0x180022eec  mov     rbx, cs:WPP_GLOBAL_Control
0x180022ef3  lea     rax, [rbp+630h+Block]
0x180022ef7  cmp     r14, rax
0x180022efa  jz      loc_180023154
0x180022f00  xor     edx, edx; Val
0x180022f02  mov     [rsp+730h+var_6CC], edi
0x180022f06  mov     r8d, 340h; Size
0x180022f0c  lea     rcx, [rbp+630h+var_670]; void *
0x180022f10  mov     esi, edi
0x180022f12  call    memset_0
0x180022f17  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022f1b  mov     [rsp+730h+var_6C0], rdi
0x180022f20  lea     r12, [r14+12h]
0x180022f24  inc     rax
0x180022f27  cmp     [r12+rax*2], di
0x180022f2c  jnz     short loc_180022F24
0x180022f2e  cmp     eax, 36h ; '6'
0x180022f31  jnz     short loc_180022F39
0x180022f33  lea     rcx, [r14+26h]
0x180022f37  jmp     short loc_180022F42
0x180022f39  cmp     eax, 3Ah ; ':'
0x180022f3c  jnz     short loc_180022F64
0x180022f3e  lea     rcx, [r14+2Ah]
0x180022f42  lea     r9, [rsp+730h+var_6C0]
0x180022f47  lea     r8, [rbp+630h+var_668]
0x180022f4b  lea     rdx, [rsp+730h+var_6CC]
0x180022f50  call    DafBthGetDeviceAddressAndTypeFromAepIdEx
0x180022f55  mov     rbx, cs:WPP_GLOBAL_Control
0x180022f5c  mov     edi, eax
0x180022f5e  mov     esi, [rsp+730h+var_6CC]
0x180022f62  jmp     short loc_180022F97
0x180022f64  lea     rax, WPP_GLOBAL_Control
0x180022f6b  cmp     rbx, rax
0x180022f6e  jz      short loc_180022F92
0x180022f70  cmp     byte ptr [rbx+19h], 2
0x180022f74  jb      short loc_180022F92
0x180022f76  mov     rcx, [rbx+10h]
0x180022f7a  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180022f81  mov     edx, 18h
0x180022f86  call    WPP_SF_s
0x180022f8b  mov     rbx, cs:WPP_GLOBAL_Control
0x180022f92  mov     edi, 80004005h
0x180022f97  mov     rax, [rbp+630h+var_2F8]
0x180022f9e  cmp     [rsp+730h+var_6C0], rax
0x180022fa3  jz      short loc_180022FD9
0x180022fa5  lea     rax, WPP_GLOBAL_Control
0x180022fac  cmp     rbx, rax
0x180022faf  jz      loc_18002314A
0x180022fb5  cmp     byte ptr [rbx+19h], 4
0x180022fb9  jb      loc_18002314A
0x180022fbf  mov     rcx, [rbx+10h]
0x180022fc3  lea     r8, WPP_f9159aa5f7f033323faf00332c38ba03_Traceguids
0x180022fca  mov     edx, 19h
0x180022fcf  call    WPP_SF_s
0x180022fd4  jmp     loc_180023143
0x180022fd9  test    edi, edi
0x180022fdb  js      loc_180023109
0x180022fe1  xor     ebx, ebx
0x180022fe3  test    esi, esi
0x180022fe5  jz      short loc_180022FF9
0x180022fe7  cmp     esi, 1
0x180022fea  jz      short loc_180022FF1
0x180022fec  mov     r8d, ebx
0x180022fef  jmp     short loc_180022FFF
0x180022ff1  mov     r8d, 2
0x180022ff7  jmp     short loc_180022FFF
0x180022ff9  mov     r8d, 1
0x180022fff  mov     rdx, [rbp+630h+var_668]
0x180023003  lea     r9, [rbp+630h+var_670]
0x180023007  mov     rcx, r15; hFile
0x18002300a  call    DafBthGetDeviceInfo
  ... truncated ...
```
