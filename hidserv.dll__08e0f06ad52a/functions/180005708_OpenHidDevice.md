# OpenHidDevice

- ea: `0x180005708`
- end: `0x18000645a`
- name: `OpenHidDevice`
- size: `3410`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180006460`

## callees

- `0x1800025b8`
- `0x1800025e0`
- `0x180005708`
- `0x180006a64`
- `0x180006b9c`
- `0x180006cb4`
- `0x180006dc8`
- `0x180006e68`
- `0x180006ef0`
- `0x180006f5c`
- `0x180006fd8`
- `0x180007064`
- `0x180008450`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000577d`
- `KERNEL32!LocalAlloc` at `0x1800057f7`
- `KERNEL32!LocalAlloc` at `0x180005dc8`
- `KERNEL32!LocalAlloc` at `0x180005f23`
- `KERNEL32!LocalAlloc` at `0x180005f9a`
- `KERNEL32!LocalAlloc` at `0x180006014`
- `KERNEL32!LocalAlloc` at `0x1800060d7`
- `KERNEL32!LocalAlloc` at `0x1800061bd`
- `KERNEL32!LocalAlloc` at `0x1800061df`
- `KERNEL32!LocalAlloc` at `0x18000577d`
- `KERNEL32!LocalAlloc` at `0x1800057f7`
- `KERNEL32!LocalAlloc` at `0x180005dc8`
- `KERNEL32!LocalAlloc` at `0x180005f23`
- `KERNEL32!LocalAlloc` at `0x180005f9a`
- `KERNEL32!LocalAlloc` at `0x180006014`
- `KERNEL32!LocalAlloc` at `0x1800060d7`
- `KERNEL32!LocalAlloc` at `0x1800061bd`
- `KERNEL32!LocalAlloc` at `0x1800061df`
- `KERNEL32!LocalFree` at `0x1800062c5`
- `KERNEL32!LocalFree` at `0x1800062ce`
- `KERNEL32!LocalFree` at `0x1800062d9`
- `KERNEL32!LocalFree` at `0x1800062e4`
- `KERNEL32!LocalFree` at `0x1800063a7`
- `KERNEL32!LocalFree` at `0x1800063b9`
- `KERNEL32!LocalFree` at `0x1800063d4`
- `KERNEL32!LocalFree` at `0x1800063dd`
- `KERNEL32!LocalFree` at `0x1800063eb`
- `KERNEL32!LocalFree` at `0x180006407`
- `KERNEL32!LocalFree` at `0x180006415`
- `KERNEL32!LocalFree` at `0x180006446`
- `KERNEL32!LocalFree` at `0x18000644f`
- `KERNEL32!LocalFree` at `0x1800062c5`
- `KERNEL32!LocalFree` at `0x1800062ce`
- `KERNEL32!LocalFree` at `0x1800062d9`
- `KERNEL32!LocalFree` at `0x1800062e4`
- `KERNEL32!LocalFree` at `0x1800063a7`
- `KERNEL32!LocalFree` at `0x1800063b9`
- `KERNEL32!LocalFree` at `0x1800063d4`
- `KERNEL32!LocalFree` at `0x1800063dd`
- `KERNEL32!LocalFree` at `0x1800063eb`
- `KERNEL32!LocalFree` at `0x180006407`
- `KERNEL32!LocalFree` at `0x180006415`
- `KERNEL32!LocalFree` at `0x180006446`
- `KERNEL32!LocalFree` at `0x18000644f`
- `KERNEL32!CloseHandle` at `0x180006438`
- `KERNEL32!CloseHandle` at `0x180006438`
- `KERNEL32!GetLastError` at `0x1800058ba`
- `KERNEL32!GetLastError` at `0x180005a2a`
- `KERNEL32!GetLastError` at `0x180005b8c`
- `KERNEL32!GetLastError` at `0x180005c2e`
- `KERNEL32!GetLastError` at `0x180005c9a`
- `KERNEL32!GetLastError` at `0x180005d05`
- `KERNEL32!GetLastError` at `0x1800058ba`
- `KERNEL32!GetLastError` at `0x180005a2a`
- `KERNEL32!GetLastError` at `0x180005b8c`
- `KERNEL32!GetLastError` at `0x180005c2e`
- `KERNEL32!GetLastError` at `0x180005c9a`
- `KERNEL32!GetLastError` at `0x180005d05`
- `KERNEL32!CompareStringW` at `0x1800059b0`
- `KERNEL32!CompareStringW` at `0x1800059b0`
- `KERNEL32!CreateFileW` at `0x180005b7c`
- `KERNEL32!CreateFileW` at `0x180005b7c`
- `HID!HidP_GetCaps` at `0x180005cfb`
- `HID!HidP_GetCaps` at `0x180005cfb`
- `HID!HidP_MaxUsageListLength` at `0x1800061a6`
- `HID!HidP_MaxUsageListLength` at `0x1800061a6`
- `HID!HidP_GetButtonCaps` at `0x180006097`
- `HID!HidP_GetButtonCaps` at `0x180006097`
- `HID!HidD_GetAttributes` at `0x180005c90`
- `HID!HidD_GetAttributes` at `0x180005c90`
- `HID!HidP_GetLinkCollectionNodes` at `0x180005e89`
- `HID!HidP_GetLinkCollectionNodes` at `0x180005e89`
- `HID!HidP_GetValueCaps` at `0x1800060b4`
- `HID!HidP_GetValueCaps` at `0x1800060b4`
- `HID!HidD_GetPreparsedData` at `0x180005c24`
- `HID!HidD_GetPreparsedData` at `0x180005c24`
- `HID!HidD_FreePreparsedData` at `0x180006424`
- `HID!HidD_FreePreparsedData` at `0x180006424`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x18000597c`
- `CFGMGR32!CM_Get_DevNode_Registry_PropertyW` at `0x18000597c`
- `CFGMGR32!CM_Get_Parent` at `0x1800058ed`
- `CFGMGR32!CM_Get_Parent` at `0x180005910`
- `CFGMGR32!CM_Get_Parent` at `0x1800058ed`
- `CFGMGR32!CM_Get_Parent` at `0x180005910`
- `CFGMGR32!CM_Get_Child` at `0x18000592a`
- `CFGMGR32!CM_Get_Child` at `0x18000592a`
- `CFGMGR32!CM_Get_Sibling` at `0x18000594c`
- `CFGMGR32!CM_Get_Sibling` at `0x18000594c`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x180005a15`
- `DEVOBJ!DevObjGetDeviceInterfaceProperty` at `0x180005a15`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800057e8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000587e`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800057e8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000587e`

## string_xrefs

- `0x180005bda`: `CreateFile`
- `0x180005c7c`: `HidD_GetPreparsedData`
- `0x180005e26`: `LocalAlloc|LinkCollectionNodes`

## pseudocode

```c
__int64 __fastcall OpenHidDevice(__int64 a1, __int64 a2, _QWORD *a3)
{
  char *v5; // rdi
  __int64 v6; // r9
  __int64 result; // rax
  HLOCAL v8; // r15
  unsigned int v9; // ebx
  _DWORD *v10; // rax
  __int64 v11; // r9
  WCHAR *v12; // r13
  __int64 v13; // rbx
  DWORD LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  DEVNODE v17; // ecx
  __int64 v18; // rax
  int v19; // r12d
  DWORD v20; // eax
  int v21; // r8d
  DWORD v22; // r15d
  __int64 v23; // r8
  __int64 v24; // rdx
  const WCHAR *v25; // rsi
  HANDLE FileW; // rax
  int v27; // edx
  int v28; // r8d
  DWORD v29; // eax
  int v30; // r8d
  __int64 v31; // r9
  DWORD v32; // r15d
  const char *v33; // rdx
  __int64 v34; // r8
  PHIDP_PREPARSED_DATA *v35; // r15
  DWORD v36; // eax
  int v37; // r8d
  DWORD v38; // eax
  int v39; // r8d
  int v40; // r8d
  DWORD v41; // eax
  int v42; // r8d
  __int16 v43; // ax
  __int64 v44; // rdx
  __int64 v45; // rax
  struct _HIDP_LINK_COLLECTION_NODE *v46; // rax
  int v47; // r8d
  unsigned __int8 v48; // r15
  _QWORD *v49; // rcx
  _DWORD *v50; // r13
  HLOCAL v51; // rax
  int v52; // r8d
  int v53; // r8d
  struct _HIDP_BUTTON_CAPS *v54; // r15
  int v55; // r8d
  __int64 v56; // r9
  struct _HIDP_VALUE_CAPS *v57; // r13
  __int64 v58; // rdx
  _WORD *v59; // rax
  int v60; // r8d
  __int64 v61; // r9
  _WORD *v62; // r15
  bool v63; // cf
  unsigned __int8 v64; // dl
  _WORD *v65; // r8
  __int16 v66; // ax
  ULONG v67; // eax
  HLOCAL v68; // rax
  int v69; // r8d
  HLOCAL v70; // rax
  unsigned __int8 i; // r12
  __int64 v72; // rsi
  __int16 LinkCollection; // ax
  _QWORD *v74; // rcx
  int v75; // edx
  unsigned __int8 j; // bl
  void *v77; // rcx
  void *v78; // rcx
  void *v79; // rcx
  struct _HIDP_PREPARSED_DATA *v80; // rcx
  char *v81; // rcx
  unsigned __int16 v82; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v83; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v84; // [rsp+50h] [rbp-B0h]
  USHORT ButtonCapsLength[2]; // [rsp+54h] [rbp-ACh] BYREF
  DEVNODE pdnDevInst; // [rsp+58h] [rbp-A8h] BYREF
  SIZE_T uBytes; // [rsp+5Ch] [rbp-A4h] BYREF
  ULONG pulLength; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v89; // [rsp+68h] [rbp-98h] BYREF
  ULONG LinkCollectionNodesLength; // [rsp+6Ch] [rbp-94h] BYREF
  HLOCAL v91; // [rsp+70h] [rbp-90h]
  HLOCAL hMem; // [rsp+78h] [rbp-88h]
  _QWORD *v93; // [rsp+80h] [rbp-80h]
  __int128 v94; // [rsp+88h] [rbp-78h] BYREF
  DEVINST dnDevInst[4]; // [rsp+98h] [rbp-68h]
  __int128 v96; // [rsp+A8h] [rbp-58h]
  WCHAR Buffer[512]; // [rsp+C0h] [rbp-40h] BYREF

  v93 = a3;
  uBytes = 0;
  ButtonCapsLength[0] = 0;
  v89 = 0;
  v82 = 0;
  pulLength = 0;
  v94 = 0;
  pdnDevInst = 0;
  *(_OWORD *)dnDevInst = 0;
  v96 = 0;
  v5 = (char *)LocalAlloc(0x40u, 0xD0u);
  if ( v5 )
  {
    v83 = 0;
    v8 = 0;
    DevObjGetDeviceInterfaceDetail(a1, a2, 0, 0, &uBytes, 0);
    v9 = uBytes;
    v10 = LocalAlloc(0x40u, (unsigned int)uBytes);
    v91 = v10;
    v12 = (WCHAR *)v10;
    if ( !v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, v11);
      }
      goto LABEL_190;
    }
    *v10 = 8;
    LODWORD(v94) = 48;
    dnDevInst[1] = 0;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(a1, a2, v10, v9, &uBytes, &v94) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_D(v13, 20, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, LastError);
      }
      goto LABEL_190;
    }
    *((_DWORD *)v5 + 25) = dnDevInst[1];
    if ( !CM_Get_Parent((PDEVINST)&uBytes + 1, dnDevInst[1], 0)
      && !CM_Get_Parent(&pdnDevInst, HIDWORD(uBytes), 0)
      && !CM_Get_Child(&pdnDevInst, pdnDevInst, 0) )
    {
      v17 = pdnDevInst;
      if ( pdnDevInst == HIDWORD(uBytes) )
      {
        if ( CM_Get_Sibling(&pdnDevInst, pdnDevInst, 0) )
          goto LABEL_27;
        v17 = pdnDevInst;
      }
      pulLength = 1024;
      if ( !CM_Get_DevNode_Registry_PropertyW(v17, 8u, 0, Buffer, &pulLength, 0)
        && pulLength == 12
        && CompareStringW(0x7Fu, 1u, Buffer, 12, L"MEDIA", -1) == 2 )
      {
        v5[204] = 1;
      }
    }
LABEL_27:
    v18 = HidDeviceList;
    if ( HidDeviceList )
    {
      while ( *(_DWORD *)(v18 + 100) != *((_DWORD *)v5 + 25) )
      {
        v18 = *(_QWORD *)v18;
        if ( !v18 )
          goto LABEL_30;
      }
      *(_DWORD *)(v18 + 104) = 1;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v16, v12 + 2);
      }
      goto LABEL_190;
    }
LABEL_30:
    v19 = 0;
    *((_DWORD *)v5 + 26) = 1;
    if ( (unsigned int)DevObjGetDeviceInterfaceProperty(
                         a1,
                         a2,
                         &DEVPKEY_DeviceInterface_HID_UsagePage,
                         &v89,
                         &v82,
                         2,
                         0,
                         0) )
    {
      v23 = v89;
      if ( v89 == 5 )
      {
        v25 = v12 + 2;
        if ( v82 != 12 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v89, v82, (__int64)(v12 + 2));
          }
          goto LABEL_190;
        }
        v19 = 1;
LABEL_53:
        FileW = CreateFileW(v25, 0x80000000, 3u, 0, 3u, 0x40000000u, 0);
        *((_QWORD *)v5 + 1) = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          v29 = GetLastError();
          v32 = v29;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v30, v29, (__int64)v25);
          }
          if ( !v19 || v82 != 12 )
            goto LABEL_189;
          v33 = "CreateFile";
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, v28, (_DWORD)FileW, (__int64)v25);
          }
          v35 = (PHIDP_PREPARSED_DATA *)(v5 + 16);
          if ( HidD_GetPreparsedData(*((HANDLE *)v5 + 1), (PHIDP_PREPARSED_DATA *)v5 + 2) )
          {
            if ( HidD_GetAttributes(*((HANDLE *)v5 + 1), (PHIDD_ATTRIBUTES)(v5 + 88)) )
            {
              if ( HidP_GetCaps(*v35, (PHIDP_CAPS)(v5 + 24)) )
              {
                v43 = *((_WORD *)v5 + 13);
                if ( v19 )
                {
                  v44 = v82;
                  if ( v43 != v82 )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_DDS(*((_QWORD *)WPP_GLOBAL_Control + 2), v82, v40, v82, v43, (__int64)v25);
                      v44 = v82;
                    }
                    TelemetryUsagePageMismatched(v25, v44, *((unsigned __int16 *)v5 + 13));
                  }
                }
                else if ( v43 != 12 )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    WPP_SF_DS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      31,
                      v40,
                      *((unsigned __int16 *)v5 + 13),
                      (__int64)v25);
                  }
                  goto LABEL_189;
                }
                v45 = *((unsigned __int16 *)v5 + 34);
                LinkCollectionNodesLength = *((unsigned __int16 *)v5 + 34);
                v46 = (struct _HIDP_LINK_COLLECTION_NODE *)LocalAlloc(0x40u, 24 * v45);
                v83 = v46;
                if ( v46 )
                {
                  HidP_GetLinkCollectionNodes(v46, &LinkCollectionNodesLength, *v35);
                  v48 = 0;
                  if ( *((_WORD *)v5 + 34) )
                  {
                    v49 = WPP_GLOBAL_Control;
                    v50 = v83;
                    do
                    {
                      if ( v49 != &WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 2) != 0 && *((_BYTE *)v49 + 25) >= 4u )
                      {
                        WPP_SF_dDDDD(
                          v49[2],
                          3LL * v48,
                          LOWORD(v50[6 * v48]),
                          v48,
                          LOBYTE(v50[6 * v48 + 3]),
                          (v50[6 * v48 + 3] >> 8) & 1,
                          HIWORD(v50[6 * v48]),
                          LOWORD(v50[6 * v48]));
                        v49 = WPP_GLOBAL_Control;
                      }
                      ++v48;
                    }
                    while ( v48 < (unsigned int)*((_WORD *)v5 + 34) );
                    v12 = (WCHAR *)v91;
                  }
                  v51 = LocalAlloc(0x40u, *((unsigned __int16 *)v5 + 14));
                  *((_QWORD *)v5 + 23) = v51;
                  if ( v51 )
                  {
                    hMem = LocalAlloc(0x40u, 72LL * *((unsigned __int16 *)v5 + 35));
                    v54 = (struct _HIDP_BUTTON_CAPS *)hMem;
                    if ( hMem )
                    {
                      v57 = (struct _HIDP_VALUE_CAPS *)LocalAlloc(0x40u, 72LL * *((unsigned __int16 *)v5 + 36));
                      if ( v57 )
                      {
                        ButtonCapsLength[0] = *((_WORD *)v5 + 35);
                        HidP_GetButtonCaps(HidP_Input, v54, ButtonCapsLength, *((PHIDP_PREPARSED_DATA *)v5 + 2));
                        ButtonCapsLength[0] = *((_WORD *)v5 + 36);
                        HidP_GetValueCaps(HidP_Input, v57, ButtonCapsLength, *((PHIDP_PREPARSED_DATA *)v5 + 2));
                        v58 = *((unsigned __int16 *)v5 + 34) + (unsigned int)*((unsigned __int16 *)v5 + 36);
                        *((_DWORD *)v5 + 50) = v58;
                        v59 = LocalAlloc(0x40u, 40 * v58);
                        v61 = 0;
                        *((_QWORD *)v5 + 24) = v59;
                        v62 = v59;
                        if ( v59 )
                        {
                          v63 = *((_WORD *)v5 + 34) != 0;
                          v64 = 0;
                          while ( 1 )
                          {
                            v84 = v64;
                            if ( !v63 )
                            {
                              for ( i = 0; i < (unsigned int)*((_WORD *)v5 + 36); v62 += 20 )
                              {
                                v72 = i;
                                if ( v57[i].IsRange
                                  && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                                {
                                  WPP_SF_(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    40,
                                    WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids,
                                    0);
                                }
                                *(_BYTE *)v62 = 0;
                                v62[3] = v57[i].LinkUsage;
                                v62[1] = v57[i].LinkUsagePage;
                                LinkCollection = v57[i].LinkCollection;
                                if ( !LinkCollection )
                                  LinkCollection = -1;
                                v62[2] = LinkCollection;
                                ++i;
                                *((_DWORD *)v62 + 7) = v57[v72].LogicalMax - v57[v72].LogicalMin;
                                *((_DWORD *)v62 + 2) = 1114112;
                                v62[8] = v57[v72].Range.UsageMin;
                              }
                              LocalFree(hMem);
                              LocalFree(v57);
                              LocalFree(v83);
                              LocalFree(v91);
                              result = 1;
                              *v93 = v5;
                              return result;
                            }
                            v65 = v83;
                            *(_BYTE *)v62 = 1;
                            v62[3] = v65[12 * v64];
                            v62[1] = v65[12 * v64 + 1];
                            v66 = v64;
                            if ( !v64 )
                              v66 = -1;
                            v62[2] = v66;
                            *((_DWORD *)v62 + 2) = 1114112;
                            v67 = HidP_MaxUsageListLength(
                                    HidP_Input,
                                    *((_WORD *)v5 + 13),
                                    *((PHIDP_PREPARSED_DATA *)v5 + 2))
                                + 1;
                            *((_DWORD *)v62 + 4) = v67;
                            v68 = LocalAlloc(0x40u, 4LL * v67);
                            *((_QWORD *)v62 + 3) = v68;
                            if ( !v68 )
                              break;
                            v70 = LocalAlloc(0x40u, 4LL * *((unsigned int *)v62 + 4));
                            *((_QWORD *)v62 + 4) = v70;
                            if ( !v70 )
                            {
                              v74 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                              {
                                v75 = 39;
LABEL_176:
                                WPP_SF_DS(v74[2], v75, v69, *((_DWORD *)v62 + 4), (__int64)v25);
                                goto LABEL_177;
                              }
                              goto LABEL_177;
                            }
                            v62 += 20;
                            v64 = v84 + 1;
                            v63 = (unsigned __int8)(v84 + 1) < (unsigned int)*((_WORD *)v5 + 34);
                          }
                          v74 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            v75 = 38;
                            goto LABEL_176;
                          }
LABEL_177:
                          if ( v19 && v82 == 12 )
                            TelemetryFailedOnConsumerControl(
                              v25,
                              "LocalAlloc|ButtonData",
                              *((unsigned int *)v62 + 4),
                              0);
                          for ( j = 0; j < (unsigned int)*((_WORD *)v5 + 34); v62 += 20 )
                          {
                            v77 = (void *)*((_QWORD *)v62 + 3);
                            if ( v77 )
                              LocalFree(v77);
                            v78 = (void *)*((_QWORD *)v62 + 4);
                            if ( v78 )
                              LocalFree(v78);
                            ++j;
                          }
                          LocalFree(v62);
                        }
                        else
                        {
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v60, *((_DWORD *)v5 + 50), (__int64)v25);
                          }
                          if ( v19 && v82 == 12 )
                            TelemetryFailedOnConsumerControl(
                              v25,
                              "LocalAlloc|InputData",
                              *((unsigned int *)v5 + 50),
                              v61);
                        }
                        LocalFree(v57);
                        v54 = (struct _HIDP_BUTTON_CAPS *)hMem;
                      }
                      else
                      {
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                        {
                          WPP_SF_DS(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            36,
                            v55,
                            *((unsigned __int16 *)v5 + 36),
                            (__int64)v25);
                        }
                        if ( v19 && v82 == 12 )
                          TelemetryFailedOnConsumerControl(
                            v25,
                            "LocalAlloc|InputValueCaps",
                            *((unsigned __int16 *)v5 + 36),
                            v56);
                      }
                      LocalFree(v54);
                      v12 = (WCHAR *)v91;
                      goto LABEL_189;
                    }
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_DS(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        35,
                        v53,
                        *((unsigned __int16 *)v5 + 35),
                        (__int64)v25);
                    }
                    if ( !v19 || v82 != 12 )
                    {
LABEL_189:
                      v8 = v83;
LABEL_190:
                      v79 = (void *)*((_QWORD *)v5 + 23);
                      if ( v79 )
                        LocalFree(v79);
                      if ( v8 )
                        LocalFree(v8);
                      v80 = (struct _HIDP_PREPARSED_DATA *)*((_QWORD *)v5 + 2);
                      if ( v80 )
                        HidD_FreePreparsedData(v80);
                      v81 = (char *)*((_QWORD *)v5 + 1);
                      if ( (unsigned __int64)(v81 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                        CloseHandle(v81);
                      if ( v12 )
                        LocalFree(v12);
                      LocalFree(v5);
                      return 0;
                    }
                    v34 = *((unsigned __int16 *)v5 + 35);
                    v33 = "LocalAlloc|InputButtonCaps";
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_DS(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        34,
                        v52,
                        *((unsigned __int16 *)v5 + 14),
                        (__int64)v25);
                    }
                    if ( !v19 || v82 != 12 )
                      goto LABEL_189;
                    v34 = *((unsigned __int16 *)v5 + 14);
                    v33 = "LocalAlloc|InputReport";
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_DS(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      32,
                      v47,
                      *((unsigned __int16 *)v5 + 34),
                      (__int64)v25);
                  }
                  if ( !v19 || v82 != 12 )
                    goto LABEL_189;
                  v34 = *((unsigned __int16 *)v5 + 34);
                  v33 = "LocalAlloc|LinkCollectionNodes";
                }
LABEL_62:
                TelemetryFailedOnConsumerControl(v25, v33, v34, v31);
                goto LABEL_189;
              }
              v41 = GetLastError();
              v32 = v41;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, v42, v41, (__int64)v25);
              }
              if ( !v19 || v82 != 12 )
                goto LABEL_189;
              v33 = "HidP_GetCaps";
            }
            else
            {
              v38 = GetLastError();
              v32 = v38;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v39, v38, (__int64)v25);
              }
              if ( !v19 || v82 != 12 )
                goto LABEL_189;
              v33 = "HidD_GetAttributes";
            }
          }
          else
          {
            v36 = GetLastError();
            v32 = v36;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v37, v36, (__int64)v25);
            }
            if ( !v19 || v82 != 12 )
              goto LABEL_189;
            v33 = "HidD_GetPreparsedData";
          }
        }
        v34 = v32;
        goto LABEL_62;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v89, v89, (__int64)(v12 + 2));
        v23 = v89;
      }
      v24 = 0;
    }
    else
    {
      v20 = GetLastError();
      v22 = v20;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), (_DWORD)v12 + 4, v21, v20, (__int64)(v12 + 2));
      }
      v23 = 0;
      v24 = v22;
    }
    v25 = v12 + 2;
    TelemetryGetDeviceInterfacePropertyFailed(v12 + 2, v24, v23);
    goto LABEL_53;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, v6);
  }
  return 0;
}

```

## disassembly

```asm
0x180005708  mov     [rsp-8+arg_18], rbx
0x18000570d  push    rbp
0x18000570e  push    rsi
0x18000570f  push    rdi
0x180005710  push    r12
0x180005712  push    r13
0x180005714  push    r14
0x180005716  push    r15
0x180005718  lea     rbp, [rsp-3D0h]
0x180005720  sub     rsp, 4D0h
0x180005727  mov     rax, cs:__security_cookie
0x18000572e  xor     rax, rsp
0x180005731  mov     [rbp+400h+var_40], rax
0x180005738  xor     ebx, ebx
0x18000573a  mov     [rbp+400h+var_480], r8
0x18000573e  xorps   xmm0, xmm0
0x180005741  mov     dword ptr [rsp+500h+uBytes], ebx
0x180005745  mov     r14, rdx
0x180005748  mov     [rsp+500h+ButtonCapsLength], bx
0x18000574d  mov     rsi, rcx
0x180005750  mov     [rsp+500h+var_498], ebx
0x180005754  lea     r12d, [rbx+40h]
0x180005758  mov     [rsp+500h+var_4C0], bx
0x18000575d  mov     ecx, r12d; uFlags
0x180005760  mov     dword ptr [rsp+500h+uBytes+4], ebx
0x180005764  mov     edx, 0D0h; uBytes
0x180005769  mov     [rsp+500h+var_49C], ebx
0x18000576d  movups  [rbp+400h+var_478], xmm0
0x180005771  mov     [rsp+500h+pdnDevInst], ebx
0x180005775  movups  xmmword ptr [rbp+400h+dnDevInst], xmm0
0x180005779  movups  [rbp+400h+var_458], xmm0
0x18000577d  call    cs:__imp_LocalAlloc
0x180005783  mov     rdi, rax
0x180005786  test    rax, rax
0x180005789  jnz     short loc_1800057C5
0x18000578b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005792  lea     r14, WPP_GLOBAL_Control
0x180005799  cmp     rcx, r14
0x18000579c  jz      short loc_1800057BE
0x18000579e  lea     ebx, [rax+2]
0x1800057a1  test    [rcx+1Ch], bl
0x1800057a4  jz      short loc_1800057BE
0x1800057a6  cmp     [rcx+19h], bl
0x1800057a9  jb      short loc_1800057BE
0x1800057ab  mov     rcx, [rcx+10h]
0x1800057af  lea     edx, [rax+12h]
0x1800057b2  lea     r8, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x1800057b9  call    WPP_SF_
0x1800057be  xor     eax, eax
0x1800057c0  jmp     loc_1800062F6
0x1800057c5  lea     rax, [rsp+500h+uBytes]
0x1800057ca  mov     qword ptr [rsp+500h+ulFlags], rbx
0x1800057cf  xor     r9d, r9d
0x1800057d2  mov     [rsp+500h+pulLength], rax
0x1800057d7  xor     r8d, r8d
0x1800057da  mov     [rsp+500h+var_4B8], rbx
0x1800057df  mov     rdx, r14
0x1800057e2  mov     rcx, rsi
0x1800057e5  mov     r15, rbx
0x1800057e8  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800057ee  mov     ebx, dword ptr [rsp+500h+uBytes]
0x1800057f2  mov     ecx, r12d; uFlags
0x1800057f5  mov     edx, ebx; uBytes
0x1800057f7  call    cs:__imp_LocalAlloc
0x1800057fd  mov     [rsp+500h+var_490], rax
0x180005802  mov     r13, rax
0x180005805  test    rax, rax
0x180005808  jnz     short loc_18000584E
0x18000580a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005811  lea     r14, WPP_GLOBAL_Control
0x180005818  cmp     rcx, r14
0x18000581b  jz      loc_1800063FB
0x180005821  lea     ebx, [rax+2]
0x180005824  test    [rcx+1Ch], bl
0x180005827  jz      loc_1800063FB
0x18000582d  cmp     [rcx+19h], bl
0x180005830  jb      loc_1800063FB
0x180005836  mov     rcx, [rcx+10h]
0x18000583a  lea     edx, [rax+13h]
0x18000583d  lea     r8, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x180005844  call    WPP_SF_
0x180005849  jmp     loc_1800063FB
0x18000584e  mov     dword ptr [rax], 8
0x180005854  mov     r9d, ebx
0x180005857  lea     rax, [rbp+400h+var_478]
0x18000585b  mov     dword ptr [rbp+400h+var_478], 30h ; '0'
0x180005862  mov     qword ptr [rsp+500h+ulFlags], rax
0x180005867  mov     r8, r13
0x18000586a  lea     rax, [rsp+500h+uBytes]
0x18000586f  mov     [rbp+400h+dnDevInst+4], r15d
0x180005873  mov     rdx, r14
0x180005876  mov     [rsp+500h+pulLength], rax
0x18000587b  mov     rcx, rsi
0x18000587e  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180005884  test    eax, eax
0x180005886  jnz     short loc_1800058DC
0x180005888  mov     rax, cs:WPP_GLOBAL_Control
0x18000588f  lea     r14, WPP_GLOBAL_Control
0x180005896  cmp     rax, r14
0x180005899  jz      loc_1800063FB
0x18000589f  mov     ebx, 2
0x1800058a4  test    [rax+1Ch], bl
0x1800058a7  jz      loc_1800063FB
0x1800058ad  cmp     [rax+19h], bl
0x1800058b0  jb      loc_1800063FB
0x1800058b6  mov     rbx, [rax+10h]
0x1800058ba  call    cs:__imp_GetLastError
0x1800058c0  mov     edx, 14h
0x1800058c5  lea     r8, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x1800058cc  mov     r9d, eax
0x1800058cf  mov     rcx, rbx
0x1800058d2  call    WPP_SF_D
0x1800058d7  jmp     loc_1800063FB
0x1800058dc  mov     eax, [rbp+400h+dnDevInst+4]
0x1800058df  lea     rcx, [rsp+500h+uBytes+4]; pdnDevInst
0x1800058e4  mov     [rdi+64h], eax
0x1800058e7  xor     r8d, r8d; ulFlags
0x1800058ea  mov     edx, [rbp+400h+dnDevInst+4]; dnDevInst
0x1800058ed  call    cs:__imp_CM_Get_Parent
0x1800058f3  mov     ebx, 2
0x1800058f8  lea     r12d, [rbx+0Ah]
0x1800058fc  test    eax, eax
0x1800058fe  jnz     loc_1800059C1
0x180005904  mov     edx, dword ptr [rsp+500h+uBytes+4]; dnDevInst
0x180005908  lea     rcx, [rsp+500h+pdnDevInst]; pdnDevInst
0x18000590d  xor     r8d, r8d; ulFlags
0x180005910  call    cs:__imp_CM_Get_Parent
0x180005916  test    eax, eax
0x180005918  jnz     loc_1800059C1
0x18000591e  mov     edx, [rsp+500h+pdnDevInst]; dnDevInst
0x180005922  lea     rcx, [rsp+500h+pdnDevInst]; pdnDevInst
0x180005927  xor     r8d, r8d; ulFlags
0x18000592a  call    cs:__imp_CM_Get_Child
0x180005930  test    eax, eax
0x180005932  jnz     loc_1800059C1
0x180005938  mov     ecx, [rsp+500h+pdnDevInst]
0x18000593c  cmp     ecx, dword ptr [rsp+500h+uBytes+4]
0x180005940  jnz     short loc_18000595A
0x180005942  mov     edx, ecx; dnDevInst
0x180005944  xor     r8d, r8d; ulFlags
0x180005947  lea     rcx, [rsp+500h+pdnDevInst]; pdnDevInst
0x18000594c  call    cs:__imp_CM_Get_Sibling
0x180005952  test    eax, eax
0x180005954  jnz     short loc_1800059C1
0x180005956  mov     ecx, [rsp+500h+pdnDevInst]; dnDevInst
0x18000595a  xor     r8d, r8d; pulRegDataType
0x18000595d  mov     [rsp+500h+ulFlags], r15d; ulFlags
0x180005962  lea     rax, [rsp+500h+var_49C]
0x180005967  mov     [rsp+500h+var_49C], 400h
0x18000596f  lea     r9, [rbp+400h+Buffer]; Buffer
0x180005973  mov     [rsp+500h+pulLength], rax; pulLength
0x180005978  lea     edx, [r8+8]; ulProperty
0x18000597c  call    cs:__imp_CM_Get_DevNode_Registry_PropertyW
0x180005982  test    eax, eax
0x180005984  jnz     short loc_1800059C1
0x180005986  cmp     [rsp+500h+var_49C], r12d
0x18000598b  jnz     short loc_1800059C1
0x18000598d  mov     edx, 1; dwCmpFlags
0x180005992  mov     [rsp+500h+ulFlags], 0FFFFFFFFh; cchCount2
0x18000599a  lea     rax, String2; "MEDIA"
0x1800059a1  mov     r9d, r12d; cchCount1
0x1800059a4  lea     r8, [rbp+400h+Buffer]; lpString1
0x1800059a8  mov     [rsp+500h+pulLength], rax; lpString2
0x1800059ad  lea     ecx, [rdx+7Eh]; Locale
0x1800059b0  call    cs:__imp_CompareStringW
0x1800059b6  cmp     eax, ebx
0x1800059b8  jnz     short loc_1800059C1
0x1800059ba  mov     byte ptr [rdi+0CCh], 1
0x1800059c1  mov     rax, cs:HidDeviceList
0x1800059c8  test    rax, rax
0x1800059cb  jz      short loc_1800059E1
0x1800059cd  mov     ecx, [rdi+64h]
0x1800059d0  cmp     [rax+64h], ecx
0x1800059d3  jz      loc_180005A75
0x1800059d9  mov     rax, [rax]
0x1800059dc  test    rax, rax
0x1800059df  jnz     short loc_1800059D0
0x1800059e1  xor     r12d, r12d
0x1800059e4  mov     dword ptr [rdi+68h], 1
0x1800059eb  mov     [rsp+500h+var_4C8], r12d
0x1800059f0  lea     rax, [rsp+500h+var_4C0]
0x1800059f5  mov     [rsp+500h+hTemplateFile], r12
0x1800059fa  lea     r9, [rsp+500h+var_498]
0x1800059ff  mov     [rsp+500h+ulFlags], ebx
0x180005a03  lea     r8, DEVPKEY_DeviceInterface_HID_UsagePage
0x180005a0a  mov     rdx, r14
0x180005a0d  mov     [rsp+500h+pulLength], rax
0x180005a12  mov     rcx, rsi
0x180005a15  call    cs:__imp_DevObjGetDeviceInterfaceProperty
0x180005a1b  lea     r14, WPP_GLOBAL_Control
0x180005a22  test    eax, eax
0x180005a24  jnz     loc_180005AB8
0x180005a2a  call    cs:__imp_GetLastError
0x180005a30  mov     r15d, eax
0x180005a33  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a3a  cmp     rcx, r14
0x180005a3d  jz      short loc_180005A5E
0x180005a3f  test    [rcx+1Ch], bl
0x180005a42  jz      short loc_180005A5E
0x180005a44  cmp     [rcx+19h], bl
0x180005a47  jb      short loc_180005A5E
0x180005a49  mov     rcx, [rcx+10h]
0x180005a4d  lea     rdx, [r13+4]
0x180005a51  mov     r9d, eax
0x180005a54  mov     [rsp+500h+pulLength], rdx
0x180005a59  call    WPP_SF_dS
0x180005a5e  xor     r8d, r8d
0x180005a61  mov     edx, r15d
0x180005a64  lea     rsi, [r13+4]
0x180005a68  mov     rcx, rsi
0x180005a6b  call    TelemetryGetDeviceInterfacePropertyFailed
0x180005a70  jmp     loc_180005B54
0x180005a75  mov     dword ptr [rax+68h], 1
0x180005a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a83  lea     r14, WPP_GLOBAL_Control
0x180005a8a  cmp     rcx, r14
0x180005a8d  jz      loc_1800063FB
0x180005a93  test    [rcx+1Ch], bl
0x180005a96  jz      loc_1800063FB
0x180005a9c  cmp     byte ptr [rcx+19h], 4
0x180005aa0  jb      loc_1800063FB
0x180005aa6  mov     rcx, [rcx+10h]
0x180005aaa  lea     r9, [r13+4]
0x180005aae  call    WPP_SF_S
0x180005ab3  jmp     loc_1800063FB
0x180005ab8  mov     r8d, [rsp+500h+var_498]
0x180005abd  cmp     r8d, 5
0x180005ac1  jz      short loc_180005AFF
0x180005ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005aca  cmp     rcx, r14
0x180005acd  jz      short loc_180005AF8
0x180005acf  test    [rcx+1Ch], bl
0x180005ad2  jz      short loc_180005AF8
0x180005ad4  cmp     [rcx+19h], bl
0x180005ad7  jb      short loc_180005AF8
0x180005ad9  mov     rcx, [rcx+10h]
0x180005add  lea     rax, [r13+4]
0x180005ae1  mov     edx, 17h
0x180005ae6  mov     [rsp+500h+pulLength], rax
0x180005aeb  mov     r9d, r8d
0x180005aee  call    WPP_SF_DS
0x180005af3  mov     r8d, [rsp+500h+var_498]
0x180005af8  xor     edx, edx
0x180005afa  jmp     loc_180005A64
0x180005aff  mov     eax, 0Ch
0x180005b04  lea     rsi, [r13+4]
0x180005b08  cmp     [rsp+500h+var_4C0], ax
0x180005b0d  jz      short loc_180005B4E
0x180005b0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b16  cmp     rcx, r14
0x180005b19  jz      loc_1800063FB
0x180005b1f  test    [rcx+1Ch], bl
0x180005b22  jz      loc_1800063FB
0x180005b28  cmp     byte ptr [rcx+19h], 4
0x180005b2c  jb      loc_1800063FB
0x180005b32  movzx   r9d, [rsp+500h+var_4C0]
0x180005b38  lea     edx, [rax+0Ch]
0x180005b3b  mov     rcx, [rcx+10h]
0x180005b3f  mov     [rsp+500h+pulLength], rsi
0x180005b44  call    WPP_SF_DS
0x180005b49  jmp     loc_1800063FB
0x180005b4e  mov     r12d, 1
0x180005b54  mov     eax, 3
0x180005b59  mov     [rsp+500h+hTemplateFile], 0; hTemplateFile
0x180005b62  mov     r8d, eax; dwShareMode
0x180005b65  mov     [rsp+500h+ulFlags], 40000000h; dwFlagsAndAttributes
0x180005b6d  xor     r9d, r9d; lpSecurityAttributes
0x180005b70  mov     dword ptr [rsp+500h+pulLength], eax; dwCreationDisposition
0x180005b74  mov     edx, 80000000h; dwDesiredAccess
0x180005b79  mov     rcx, rsi; lpFileName
0x180005b7c  call    cs:__imp_CreateFileW
0x180005b82  mov     [rdi+8], rax
0x180005b86  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005b8a  jnz     short loc_180005BF1
0x180005b8c  call    cs:__imp_GetLastError
0x180005b92  mov     r15d, eax
0x180005b95  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b9c  cmp     rcx, r14
0x180005b9f  jz      short loc_180005BC1
0x180005ba1  test    [rcx+1Ch], bl
0x180005ba4  jz      short loc_180005BC1
0x180005ba6  cmp     [rcx+19h], bl
0x180005ba9  jb      short loc_180005BC1
0x180005bab  mov     rcx, [rcx+10h]
0x180005baf  mov     edx, 19h
0x180005bb4  mov     r9d, eax
0x180005bb7  mov     [rsp+500h+pulLength], rsi
0x180005bbc  call    WPP_SF_DS
0x180005bc1  test    r12d, r12d
0x180005bc4  jz      loc_1800063F6
0x180005bca  mov     eax, 0Ch
0x180005bcf  cmp     [rsp+500h+var_4C0], ax
0x180005bd4  jnz     loc_1800063F6
0x180005bda  lea     rdx, aCreatefile; "CreateFile"
0x180005be1  mov     r8d, r15d
0x180005be4  mov     rcx, rsi
0x180005be7  call    TelemetryFailedOnConsumerControl
0x180005bec  jmp     loc_1800063F6
0x180005bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180005bf8  cmp     rcx, r14
  ... truncated ...
```
