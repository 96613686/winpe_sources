# BthServClientUninstallDevice(void *,ushort *)

- ea: `0x18001b3b0`
- end: `0x18001c176`
- name: `?BthServClientUninstallDevice@@YAJPEAXPEAG@Z`
- size: `3526`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180013ec0`
- `0x180027c48`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x180012004`
- `0x1800120b8`
- `0x18001245c`
- `0x180014050`
- `0x180017944`
- `0x18001b3b0`
- `0x18001c17c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001be15`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001be15`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b5ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b5ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001be77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c0de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c0de`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ba73`
- `OLEAUT32!__imp_SysAllocString` at `0x18001bb84`
- `OLEAUT32!__imp_SysAllocString` at `0x18001bc8c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ba73`
- `OLEAUT32!__imp_SysAllocString` at `0x18001bb84`
- `OLEAUT32!__imp_SysAllocString` at `0x18001bc8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c073`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c091`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c0ac`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c073`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c091`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c0ac`
- `OLEAUT32!__imp_VariantInit` at `0x18001b8d2`
- `OLEAUT32!__imp_VariantInit` at `0x18001b8f5`
- `OLEAUT32!__imp_VariantInit` at `0x18001b918`
- `OLEAUT32!__imp_VariantInit` at `0x18001b93b`
- `OLEAUT32!__imp_VariantInit` at `0x18001b8d2`
- `OLEAUT32!__imp_VariantInit` at `0x18001b8f5`
- `OLEAUT32!__imp_VariantInit` at `0x18001b918`
- `OLEAUT32!__imp_VariantInit` at `0x18001b93b`
- `OLEAUT32!__imp_VariantClear` at `0x18001b9cd`
- `OLEAUT32!__imp_VariantClear` at `0x18001b9de`
- `OLEAUT32!__imp_VariantClear` at `0x18001b9ef`
- `OLEAUT32!__imp_VariantClear` at `0x18001ba00`
- `OLEAUT32!__imp_VariantClear` at `0x18001b9cd`
- `OLEAUT32!__imp_VariantClear` at `0x18001b9de`
- `OLEAUT32!__imp_VariantClear` at `0x18001b9ef`
- `OLEAUT32!__imp_VariantClear` at `0x18001ba00`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b7da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001b7da`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18001b747`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x18001b747`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001b69d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001b69d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c0c3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001c0c3`

## string_xrefs

- `0x18001b575`: `Global\BTH_UNINSTALL_DEVICE_%s`
- `0x18001bb7d`: `Microsoft\Windows\Bluetooth\UninstallDeviceTask`
- `0x18001bd42`: `Microsoft\Windows\Bluetooth\UninstallDeviceTask`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall BthServClientUninstallDevice(void *a1, char *a2)
{
  HANDLE EventW; // r12
  OLECHAR *v4; // r14
  OLECHAR *v5; // r13
  OLECHAR *v6; // r15
  int v7; // edx
  int v8; // r8d
  char v9; // di
  _BYTE *v10; // rcx
  __int64 v11; // r8
  OLECHAR *v12; // rdx
  OLECHAR v13; // ax
  OLECHAR *v14; // rax
  int v15; // ebx
  int v16; // edx
  signed int LastError; // eax
  int v18; // edx
  int v19; // edx
  int v20; // esi
  bool v21; // dl
  int v22; // edx
  __int64 (__fastcall *v23)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  char v24; // si
  BSTR v25; // rax
  char v26; // dl
  bool v27; // r8
  int v28; // edx
  BSTR v29; // rax
  int v30; // edx
  BSTR v31; // rax
  int v32; // edx
  __int64 v33; // rax
  int v34; // edx
  DWORD v35; // eax
  int v36; // edx
  bool v37; // r14
  int v38; // r8d
  int v39; // edx
  char v40; // dl
  bool v41; // r8
  __int64 *v42; // rdx
  int dwAuthnLevel; // [rsp+20h] [rbp-E0h]
  DWORD dwImpLevel; // [rsp+28h] [rbp-D8h]
  DWORD dwImpLevela; // [rsp+28h] [rbp-D8h]
  int pAuthList; // [rsp+30h] [rbp-D0h]
  int dwCapabilities; // [rsp+38h] [rbp-C8h]
  int v49; // [rsp+60h] [rbp-A0h]
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  __int64 v51; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v52; // [rsp+78h] [rbp-88h] BYREF
  __int64 v53; // [rsp+80h] [rbp-80h] BYREF
  IRecordInfo *v54; // [rsp+88h] [rbp-78h]
  IRecordInfo *pRecInfo; // [rsp+90h] [rbp-70h]
  IRecordInfo *v56; // [rsp+98h] [rbp-68h]
  VARIANTARG v57; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v58; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v59; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG v60; // [rsp+F8h] [rbp-8h] BYREF
  VARIANTARG v61; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG pvarg; // [rsp+128h] [rbp+28h] BYREF
  __int128 v63; // [rsp+140h] [rbp+40h]
  __int128 v64; // [rsp+150h] [rbp+50h]
  __int128 v65; // [rsp+160h] [rbp+60h]
  __int128 v66; // [rsp+170h] [rbp+70h] BYREF
  IRecordInfo *v67; // [rsp+180h] [rbp+80h]
  __int128 v68; // [rsp+190h] [rbp+90h] BYREF
  IRecordInfo *v69; // [rsp+1A0h] [rbp+A0h]
  __int128 v70; // [rsp+1B0h] [rbp+B0h] BYREF
  IRecordInfo *v71; // [rsp+1C0h] [rbp+C0h]
  OLECHAR psz[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  WCHAR Name[264]; // [rsp+250h] [rbp+150h] BYREF

  v49 = 0;
  EventW = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  memset(&v57, 0, sizeof(v57));
  ppv = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  memset_0(psz, 0, 0x7Cu);
  v9 = 1;
  v10 = WPP_GLOBAL_Control;
  LOBYTE(v7) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqi(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      dwAuthnLevel,
      dwImpLevel,
      10,
      (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  v11 = 62;
  v12 = psz;
  do
  {
    if ( v11 == -2147483584 )
      break;
    v13 = *(OLECHAR *)((char *)v12 + a2 - (char *)psz);
    if ( !v13 )
      break;
    *v12++ = v13;
    --v11;
  }
  while ( v11 );
  v14 = v12 - 1;
  if ( v11 )
    v14 = v12;
  *v14 = 0;
  if ( !v11 )
  {
    v15 = -2147024809;
    LOBYTE(v12) = v10 != (_BYTE *)&WPP_GLOBAL_Control && v10[25] >= 3u;
    if ( !(_BYTE)v12 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_160;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sS(
      *((_QWORD *)v10 + 2),
      (_DWORD)v12,
      v11,
      *((_QWORD *)v10 + 5),
      dwAuthnLevel,
      dwImpLevel,
      11,
      (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
    goto LABEL_22;
  }
  memset_0(Name, 0, 0x208u);
  if ( (int)StringCbPrintfW(Name, 0x208u, L"Global\\BTH_UNINSTALL_DEVICE_%s", psz) < 0 )
  {
    v15 = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v16) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
    {
      LOBYTE(v16) = 0;
    }
    v11 = (__int64)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v16 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_160;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sdS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      dwAuthnLevel,
      dwImpLevel,
      pAuthList,
      dwCapabilities);
    goto LABEL_22;
  }
  EventW = CreateEventW(0, 1, 0, Name);
  if ( !EventW )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v18) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
    {
      LOBYTE(v18) = 0;
    }
    v11 = (__int64)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v18 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_160;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
    goto LABEL_22;
  }
  v15 = CoInitializeEx(0, 0);
  if ( v15 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v19) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
    {
      LOBYTE(v19) = 0;
    }
    v11 = (__int64)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v19 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_160;
    goto LABEL_45;
  }
  v20 = 1;
  v49 = 1;
  v15 = CoInitializeSecurity(0, -1, 0, 0, 6u, 3u, 0, 0, 0);
  if ( v15 == -2147417831 )
  {
    v21 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( v21 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  else if ( v15 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    LOBYTE(v19) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    v11 = (__int64)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v19 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_160;
    goto LABEL_45;
  }
  v15 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  if ( v15 >= 0 )
  {
    v23 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
    VariantInit(&pvarg);
    v63 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v61);
    v64 = *(_OWORD *)&v61.vt;
    v56 = v61.pRecInfo;
    VariantInit(&v60);
    v65 = *(_OWORD *)&v60.vt;
    v54 = v60.pRecInfo;
    VariantInit(&v59);
    v66 = v63;
    v67 = pRecInfo;
    v68 = v64;
    v69 = v56;
    v70 = v65;
    v71 = v54;
    v58 = v59;
    v15 = v23(ppv, &v58, &v70, &v68);
    VariantClear(&v59);
    VariantClear(&v60);
    VariantClear(&v61);
    VariantClear(&pvarg);
    v24 = 0;
    if ( v15 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v19) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v19) = 0;
      }
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v19 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_160;
LABEL_45:
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v10 + 2), v19, v11, *((_QWORD *)v10 + 5));
LABEL_22:
      v10 = WPP_GLOBAL_Control;
LABEL_160:
      if ( ppv )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        v10 = WPP_GLOBAL_Control;
      }
      v20 = v49;
      goto LABEL_163;
    }
    v25 = SysAllocString(L"\\");
    v5 = v25;
    if ( !v25 )
    {
      v15 = -2147024882;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v26 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
        v26 = 0;
      v27 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v26 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_160;
      goto LABEL_84;
    }
    v15 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, v25, &v51);
    if ( v15 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v28) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v28) = 0;
      }
      if ( (_BYTE)v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
        v10 = WPP_GLOBAL_Control;
      }
      v51 = 0;
      goto LABEL_160;
    }
    v29 = SysAllocString(L"Microsoft\\Windows\\Bluetooth\\UninstallDeviceTask");
    v4 = v29;
    v54 = (IRecordInfo *)v29;
    if ( !v29 )
    {
      v15 = -2147024882;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v26 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
        v26 = 0;
      v27 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v26 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_160;
      goto LABEL_84;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 **))(*(_QWORD *)v51 + 104LL))(v51, v29, &v52);
    if ( v15 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v30) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v30) = 0;
      }
      if ( (_BYTE)v30 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
        v10 = WPP_GLOBAL_Control;
      }
      v52 = 0;
      goto LABEL_160;
    }
    v31 = SysAllocString(psz);
    v6 = v31;
    if ( !v31 )
    {
      v15 = -2147024882;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v26 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
        v26 = 0;
      v27 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v26 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_160;
LABEL_84:
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v10 + 2), v26, v27, *((_QWORD *)v10 + 5));
      goto LABEL_22;
    }
    v57.vt = 8;
    v57.llVal = (LONGLONG)v31;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v32) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
    {
      LOBYTE(v32) = 0;
    }
    if ( (_BYTE)v32 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v32,
        v11,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (unsigned int)&v66,
        dwImpLevela,
        24,
        (__int64)WPP_de60693e10d239c68dd665456eff7b53_Traceguids);
    }
    v33 = *v52;
    v58 = v57;
    v15 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64 *))(v33 + 96))(v52, &v58, &v53);
    if ( v15 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v34) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v34) = 0;
      }
      if ( (_BYTE)v34 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
        v10 = WPP_GLOBAL_Control;
      }
      v53 = 0;
      goto LABEL_160;
    }
    v35 = WaitForSingleObject(EventW, 0x3A98u);
    if ( v35 )
    {
      if ( v35 != 258 )
      {
        if ( v35 == -1 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            v24 = 1;
          v37 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          if ( v24 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            GetLastError();
            LOBYTE(v38) = v37;
            LOBYTE(v39) = v24;
            WPP_RECORDER_AND_TRACE_SF_sD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v39,
              v38,
              *((_QWORD *)WPP_GLOBAL_Control + 5));
            v10 = WPP_GLOBAL_Control;
          }
          v4 = (OLECHAR *)v54;
        }
        else
        {
          v10 = WPP_GLOBAL_Control;
        }
        if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v36) = 1, v10[25] < 4u) )
          LOBYTE(v36) = 0;
        if ( !(_BYTE)v36 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_159;
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v10 + 2), v36, v11, *((_QWORD *)v10 + 5));
LABEL_158:
        v10 = WPP_GLOBAL_Control;
LABEL_159:
        v15 = 0;
        goto LABEL_160;
      }
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v40 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
        v40 = 0;
      v41 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v40 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_159;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (v40 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
        v40 = 0;
      v41 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v40 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_159;
    }
    WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v10 + 2), v40, v41, *((_QWORD *)v10 + 5));
    goto LABEL_158;
  }
  v10 = WPP_GLOBAL_Control;
  LOBYTE(v22) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
  if ( (_BYTE)v22 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
    v10 = WPP_GLOBAL_Control;
  }
  ppv = 0;
LABEL_163:
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v52 )
  {
    (*(void (__fastcall **)(__int64 *))(*v52 + 16))(v52);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    SysFreeString(v6);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    SysFreeString(v4);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    SysFreeString(v5);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v20 )
  {
    CoUninitialize();
    v10 = WPP_GLOBAL_Control;
  }
  if ( EventW )
  {
    CloseHandle(EventW);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || v10[25] < 4u )
    v9 = 0;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v42 = WPP_de60693e10d239c68dd665456eff7b53_Traceguids;
    LOBYTE(v42) = v9;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)v10 + 2), (_DWORD)v42, v11, *((_QWORD *)v10 + 5));
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001b3b0  mov     [rsp-8+arg_10], rbx
0x18001b3b5  push    rbp
0x18001b3b6  push    rsi
0x18001b3b7  push    rdi
0x18001b3b8  push    r12
0x18001b3ba  push    r13
0x18001b3bc  push    r14
0x18001b3be  push    r15
0x18001b3c0  lea     rbp, [rsp-370h]
0x18001b3c8  sub     rsp, 470h
0x18001b3cf  mov     rax, cs:__security_cookie
0x18001b3d6  xor     rax, rsp
0x18001b3d9  mov     [rbp+3A0h+var_40], rax
0x18001b3e0  mov     rsi, rdx
0x18001b3e3  mov     rbx, rcx
0x18001b3e6  xor     ecx, ecx
0x18001b3e8  mov     [rsp+4A0h+var_440], ecx
0x18001b3ec  mov     r12d, ecx
0x18001b3ef  mov     r14d, ecx
0x18001b3f2  mov     r13d, ecx
0x18001b3f5  mov     r15d, ecx
0x18001b3f8  xorps   xmm0, xmm0
0x18001b3fb  xor     eax, eax
0x18001b3fd  movups  [rbp+3A0h+var_400], xmm0
0x18001b401  mov     [rbp+3A0h+var_3F0], rax
0x18001b405  mov     [rsp+4A0h+ppv], rcx
0x18001b40a  mov     [rsp+4A0h+var_430], rcx
0x18001b40f  mov     [rsp+4A0h+var_428], rcx
0x18001b414  mov     [rbp+3A0h+var_420], rcx
0x18001b418  xor     edx, edx; Val
0x18001b41a  lea     r8d, [rcx+7Ch]; Size
0x18001b41e  lea     rcx, [rbp+3A0h+psz]; void *
0x18001b425  call    memset_0
0x18001b42a  lea     r10, WPP_GLOBAL_Control
0x18001b431  lea     edi, [r15+1]
0x18001b435  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b43c  cmp     rcx, r10
0x18001b43f  jz      short loc_18001B44C
0x18001b441  cmp     byte ptr [rcx+19h], 4
0x18001b445  jb      short loc_18001B44C
0x18001b447  mov     dl, dil
0x18001b44a  jmp     short loc_18001B450
0x18001b44c  xor     eax, eax
0x18001b44e  mov     dl, al
0x18001b450  lea     r11, WPP_RECORDER_INITIALIZED
0x18001b457  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x18001b45e  setnz   r8b
0x18001b462  lea     r9, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x18001b469  test    dl, dl
0x18001b46b  jnz     short loc_18001B472
0x18001b46d  test    r8b, r8b
0x18001b470  jz      short loc_18001B4AA
0x18001b472  mov     [rsp+4A0h+var_450], rsi
0x18001b477  mov     [rsp+4A0h+var_458], rbx
0x18001b47c  mov     qword ptr [rsp+4A0h+dwCapabilities], r9
0x18001b481  mov     word ptr [rsp+4A0h+pAuthList], 0Ah
0x18001b488  mov     r9, [rcx+28h]
0x18001b48c  mov     rcx, [rcx+10h]
0x18001b490  call    WPP_RECORDER_AND_TRACE_SF_sqi
0x18001b495  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b49c  lea     r10, WPP_GLOBAL_Control
0x18001b4a3  lea     r11, WPP_RECORDER_INITIALIZED
0x18001b4aa  mov     r8d, 3Eh ; '>'
0x18001b4b0  lea     rdx, [rbp+3A0h+psz]
0x18001b4b7  lea     rax, [rbp+3A0h+psz]
0x18001b4be  mov     r9, rsi
0x18001b4c1  sub     r9, rax
0x18001b4c4  xor     ebx, ebx
0x18001b4c6  lea     rax, [r8+7FFFFFC0h]
0x18001b4cd  test    rax, rax
0x18001b4d0  jz      short loc_18001B4E8
0x18001b4d2  movzx   eax, word ptr [r9+rdx]
0x18001b4d7  test    ax, ax
0x18001b4da  jz      short loc_18001B4E8
0x18001b4dc  mov     [rdx], ax
0x18001b4df  add     rdx, 2
0x18001b4e3  sub     r8, rdi
0x18001b4e6  jnz     short loc_18001B4C6
0x18001b4e8  lea     rax, [rdx-2]
0x18001b4ec  test    r8, r8
0x18001b4ef  cmovnz  rax, rdx
0x18001b4f3  mov     [rax], bx
0x18001b4f6  jnz     short loc_18001B558
0x18001b4f8  mov     ebx, 80070057h
0x18001b4fd  cmp     rcx, r10
0x18001b500  jz      short loc_18001B50D
0x18001b502  cmp     byte ptr [rcx+19h], 3
0x18001b506  jb      short loc_18001B50D
0x18001b508  mov     dl, dil
0x18001b50b  jmp     short loc_18001B50F
0x18001b50d  xor     dl, dl
0x18001b50f  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x18001b516  setnz   r8b
0x18001b51a  test    dl, dl
0x18001b51c  jnz     short loc_18001B527
0x18001b51e  test    r8b, r8b
0x18001b521  jz      loc_18001BFE8
0x18001b527  mov     [rsp+4A0h+var_458], rsi
0x18001b52c  lea     r9, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x18001b533  mov     qword ptr [rsp+4A0h+dwCapabilities], r9
0x18001b538  mov     word ptr [rsp+4A0h+pAuthList], 0Bh
0x18001b53f  mov     r9, [rcx+28h]
0x18001b543  mov     rcx, [rcx+10h]
0x18001b547  call    WPP_RECORDER_AND_TRACE_SF_sS
0x18001b54c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b553  jmp     loc_18001BFE8
0x18001b558  mov     ebx, 208h
0x18001b55d  mov     r8d, ebx; Size
0x18001b560  xor     edx, edx; Val
0x18001b562  lea     rcx, [rbp+3A0h+Name]; void *
0x18001b569  call    memset_0
0x18001b56e  lea     r9, [rbp+3A0h+psz]
0x18001b575  lea     r8, aGlobalBthUnins; "Global\\BTH_UNINSTALL_DEVICE_%s"
0x18001b57c  mov     edx, ebx; unsigned __int64
0x18001b57e  lea     rcx, [rbp+3A0h+Name]; unsigned __int16 *
0x18001b585  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b58a  xor     esi, esi
0x18001b58c  test    eax, eax
0x18001b58e  jns     short loc_18001B5F1
0x18001b590  mov     ebx, 80070057h
0x18001b595  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b59c  lea     rax, WPP_GLOBAL_Control
0x18001b5a3  cmp     rcx, rax
0x18001b5a6  jz      short loc_18001B5B1
0x18001b5a8  cmp     byte ptr [rcx+19h], 3
0x18001b5ac  mov     dl, dil
0x18001b5af  jnb     short loc_18001B5B4
0x18001b5b1  mov     dl, sil
0x18001b5b4  lea     r8, WPP_RECORDER_INITIALIZED
0x18001b5bb  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18001b5c2  setnz   r8b
0x18001b5c6  test    dl, dl
0x18001b5c8  jnz     short loc_18001B5D3
0x18001b5ca  test    r8b, r8b
0x18001b5cd  jz      loc_18001BFE8
0x18001b5d3  lea     rax, [rbp+3A0h+psz]
0x18001b5da  mov     [rsp+4A0h+var_450], rax
0x18001b5df  mov     r9, [rcx+28h]
0x18001b5e3  mov     rcx, [rcx+10h]
0x18001b5e7  call    WPP_RECORDER_AND_TRACE_SF_sdS
0x18001b5ec  jmp     loc_18001B54C
0x18001b5f1  lea     r9, [rbp+3A0h+Name]; lpName
0x18001b5f8  xor     r8d, r8d; bInitialState
0x18001b5fb  mov     edx, edi; bManualReset
0x18001b5fd  xor     ecx, ecx; lpEventAttributes
0x18001b5ff  call    cs:__imp_CreateEventW
0x18001b606  nop     dword ptr [rax+rax+00h]
0x18001b60b  mov     r12, rax
0x18001b60e  test    rax, rax
0x18001b611  jnz     loc_18001B699
0x18001b617  call    cs:__imp_GetLastError
0x18001b61e  nop     dword ptr [rax+rax+00h]
0x18001b623  mov     ebx, eax
0x18001b625  test    eax, eax
0x18001b627  jle     short loc_18001B632
0x18001b629  movzx   ebx, ax
0x18001b62c  or      ebx, 80070000h
0x18001b632  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b639  lea     rax, WPP_GLOBAL_Control
0x18001b640  cmp     rcx, rax
0x18001b643  jz      short loc_18001B64E
0x18001b645  cmp     byte ptr [rcx+19h], 3
0x18001b649  mov     dl, dil
0x18001b64c  jnb     short loc_18001B651
0x18001b64e  mov     dl, sil
0x18001b651  lea     r8, WPP_RECORDER_INITIALIZED
0x18001b658  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18001b65f  setnz   r8b
0x18001b663  test    dl, dl
0x18001b665  jnz     short loc_18001B670
0x18001b667  test    r8b, r8b
0x18001b66a  jz      loc_18001BFE8
0x18001b670  mov     dword ptr [rsp+4A0h+var_458], ebx
0x18001b674  lea     r9, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x18001b67b  mov     qword ptr [rsp+4A0h+dwCapabilities], r9
0x18001b680  mov     word ptr [rsp+4A0h+pAuthList], 0Dh
0x18001b687  mov     r9, [rcx+28h]
0x18001b68b  mov     rcx, [rcx+10h]
0x18001b68f  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001b694  jmp     loc_18001B54C
0x18001b699  xor     edx, edx; dwCoInit
0x18001b69b  xor     ecx, ecx; pvReserved
0x18001b69d  call    cs:__imp_CoInitializeEx
0x18001b6a4  nop     dword ptr [rax+rax+00h]
0x18001b6a9  mov     ebx, eax
0x18001b6ab  test    eax, eax
0x18001b6ad  jns     short loc_18001B716
0x18001b6af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6b6  lea     rax, WPP_GLOBAL_Control
0x18001b6bd  cmp     rcx, rax
0x18001b6c0  jz      short loc_18001B6CB
0x18001b6c2  cmp     byte ptr [rcx+19h], 3
0x18001b6c6  mov     dl, dil
0x18001b6c9  jnb     short loc_18001B6CE
0x18001b6cb  mov     dl, sil
0x18001b6ce  lea     r8, WPP_RECORDER_INITIALIZED
0x18001b6d5  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18001b6dc  setnz   r8b
0x18001b6e0  test    dl, dl
0x18001b6e2  jnz     short loc_18001B6ED
0x18001b6e4  test    r8b, r8b
0x18001b6e7  jz      loc_18001BFE8
0x18001b6ed  mov     dword ptr [rsp+4A0h+var_458], ebx
0x18001b6f1  lea     r9, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x18001b6f8  mov     qword ptr [rsp+4A0h+dwCapabilities], r9
0x18001b6fd  mov     word ptr [rsp+4A0h+pAuthList], 0Eh
0x18001b704  mov     r9, [rcx+28h]
0x18001b708  mov     rcx, [rcx+10h]
0x18001b70c  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18001b711  jmp     loc_18001B54C
0x18001b716  mov     esi, edi
0x18001b718  mov     [rsp+4A0h+var_440], edi
0x18001b71c  xor     eax, eax
0x18001b71e  mov     [rsp+4A0h+pReserved3], rax; pReserved3
0x18001b723  mov     [rsp+4A0h+dwCapabilities], eax; dwCapabilities
0x18001b727  mov     [rsp+4A0h+pAuthList], rax; pAuthList
0x18001b72c  mov     [rsp+4A0h+dwImpLevel], 3; dwImpLevel
0x18001b734  mov     [rsp+4A0h+dwAuthnLevel], 6; dwAuthnLevel
0x18001b73c  xor     r9d, r9d; pReserved1
0x18001b73f  xor     r8d, r8d; asAuthSvc
0x18001b742  or      edx, 0FFFFFFFFh; cAuthSvc
0x18001b745  xor     ecx, ecx; pSecDesc
0x18001b747  call    cs:__imp_CoInitializeSecurity
0x18001b74e  nop     dword ptr [rax+rax+00h]
0x18001b753  mov     ebx, eax
0x18001b755  cmp     eax, 80010119h
0x18001b75a  jnz     loc_18001B80E
0x18001b760  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b767  lea     rax, WPP_GLOBAL_Control
0x18001b76e  cmp     rcx, rax
0x18001b771  jz      short loc_18001B77E
0x18001b773  cmp     byte ptr [rcx+19h], 3
0x18001b777  jb      short loc_18001B77E
0x18001b779  mov     dl, dil
0x18001b77c  jmp     short loc_18001B782
0x18001b77e  xor     eax, eax
0x18001b780  mov     dl, al
0x18001b782  lea     r8, WPP_RECORDER_INITIALIZED
0x18001b789  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18001b790  setnz   r8b
0x18001b794  test    dl, dl
0x18001b796  jnz     short loc_18001B79D
0x18001b798  test    r8b, r8b
0x18001b79b  jz      short loc_18001B7BD
0x18001b79d  lea     r9, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x18001b7a4  mov     qword ptr [rsp+4A0h+dwCapabilities], r9
0x18001b7a9  mov     word ptr [rsp+4A0h+pAuthList], 0Fh
0x18001b7b0  mov     r9, [rcx+28h]
0x18001b7b4  mov     rcx, [rcx+10h]
0x18001b7b8  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b7bd  lea     rax, [rsp+4A0h+ppv]
0x18001b7c2  mov     qword ptr [rsp+4A0h+dwAuthnLevel], rax; ppv
0x18001b7c7  lea     r9, IID_ITaskService; riid
0x18001b7ce  mov     r8d, edi; dwClsContext
0x18001b7d1  xor     edx, edx; pUnkOuter
0x18001b7d3  lea     rcx, CLSID_TaskScheduler; rclsid
0x18001b7da  call    cs:__imp_CoCreateInstance
0x18001b7e1  nop     dword ptr [rax+rax+00h]
0x18001b7e6  mov     ebx, eax
0x18001b7e8  test    eax, eax
0x18001b7ea  jns     loc_18001B8C2
0x18001b7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7f7  lea     rax, WPP_GLOBAL_Control
0x18001b7fe  cmp     rcx, rax
0x18001b801  jz      short loc_18001B870
0x18001b803  cmp     byte ptr [rcx+19h], 3
0x18001b807  jb      short loc_18001B870
0x18001b809  mov     dl, dil
0x18001b80c  jmp     short loc_18001B872
0x18001b80e  test    ebx, ebx
0x18001b810  jns     short loc_18001B7BD
0x18001b812  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b819  lea     rax, WPP_GLOBAL_Control
0x18001b820  cmp     rcx, rax
0x18001b823  jz      short loc_18001B830
0x18001b825  cmp     byte ptr [rcx+19h], 3
0x18001b829  jb      short loc_18001B830
0x18001b82b  mov     dl, dil
0x18001b82e  jmp     short loc_18001B835
0x18001b830  xor     esi, esi
0x18001b832  mov     dl, sil
0x18001b835  lea     r8, WPP_RECORDER_INITIALIZED
0x18001b83c  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18001b843  setnz   r8b
0x18001b847  test    dl, dl
0x18001b849  jnz     short loc_18001B854
0x18001b84b  test    r8b, r8b
0x18001b84e  jz      loc_18001BFE8
0x18001b854  mov     dword ptr [rsp+4A0h+var_458], ebx
0x18001b858  lea     r9, WPP_de60693e10d239c68dd665456eff7b53_Traceguids
0x18001b85f  mov     qword ptr [rsp+4A0h+dwCapabilities], r9
0x18001b864  mov     word ptr [rsp+4A0h+pAuthList], 10h
0x18001b86b  jmp     loc_18001B704
0x18001b870  xor     dl, dl
0x18001b872  lea     rax, WPP_RECORDER_INITIALIZED
0x18001b879  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001b880  setnz   r8b
0x18001b884  test    dl, dl
0x18001b886  jnz     short loc_18001B88D
0x18001b888  test    r8b, r8b
  ... truncated ...
```
