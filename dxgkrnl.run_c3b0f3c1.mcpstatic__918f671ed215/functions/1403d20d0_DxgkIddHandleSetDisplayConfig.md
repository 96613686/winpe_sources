# DxgkIddHandleSetDisplayConfig

- ea: `0x1403d20d0`
- end: `0x1403d3400`
- name: `DxgkIddHandleSetDisplayConfig`
- size: `4912`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, unsigned int *, unsigned int, _DWORD *, _DWORD *, int *)`
- caller_count: `1`
- callee_count: `49`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1403d14cc`

## callees

- `0x1400091f0`
- `0x140012540`
- `0x140015940`
- `0x140015a70`
- `0x140015ad0`
- `0x1400169f0`
- `0x140017274`
- `0x140018190`
- `0x14001b9c0`
- `0x14001f630`
- `0x14002ddf0`
- `0x14002ee60`
- `0x140032730`
- `0x140035f90`
- `0x140041db4`
- `0x1400496ac`
- `0x14004a320`
- `0x14004a714`
- `0x14004b0d4`
- `0x14004bf5c`
- `0x140062234`
- `0x140062b40`
- `0x14006f95c`
- `0x14006fb70`
- `0x1400a0bd0`
- `0x1400a1000`
- `0x14019301c`
- `0x140221264`
- `0x14022173c`
- `0x140221c50`
- `0x140260960`
- `0x140260b80`
- `0x1402b5b80`
- `0x1402f3dd8`
- `0x1402f4228`
- `0x1402f5ad8`
- `0x1402f5ed4`
- `0x1402f60b8`
- `0x1402f6260`
- `0x1402f63bc`
- `0x140312414`
- `0x140329ff0`
- `0x140348378`
- `0x140348478`
- `0x1403a0cac`
- `0x1403c298c`
- `0x1403d20d0`
- `0x1403d34c4`
- `0x1403f5478`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403d212b`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1403d212b`
- `ntoskrnl!KeReadStateEvent` at `0x1403d2ee6`
- `ntoskrnl!KeReadStateEvent` at `0x1403d2f5a`
- `ntoskrnl!KeReadStateEvent` at `0x1403d2ee6`
- `ntoskrnl!KeReadStateEvent` at `0x1403d2f5a`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403d2ddc`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403d2ddc`
- `ntoskrnl!ObfDereferenceObject` at `0x1403d24e6`
- `ntoskrnl!ObfDereferenceObject` at `0x1403d2553`
- `ntoskrnl!ObfDereferenceObject` at `0x1403d2e9c`
- `ntoskrnl!ObfDereferenceObject` at `0x1403d24e6`
- `ntoskrnl!ObfDereferenceObject` at `0x1403d2553`
- `ntoskrnl!ObfDereferenceObject` at `0x1403d2e9c`
- `ntoskrnl!ObfReferenceObject` at `0x1403d24ae`
- `ntoskrnl!ObfReferenceObject` at `0x1403d24ae`
- `ntoskrnl!PsGetProcessSessionId` at `0x1403d2deb`
- `ntoskrnl!PsGetProcessSessionId` at `0x1403d2deb`
- `ntoskrnl!DbgPrintEx` at `0x1403d2f19`
- `ntoskrnl!DbgPrintEx` at `0x1403d2f19`
- `watchdog!WdIsDebuggerPresent` at `0x1403d2efd`
- `watchdog!WdIsDebuggerPresent` at `0x1403d2efd`
- `watchdog!WdLogSingleEntry2` at `0x1403d219f`
- `watchdog!WdLogSingleEntry2` at `0x1403d221e`
- `watchdog!WdLogSingleEntry2` at `0x1403d2302`
- `watchdog!WdLogSingleEntry2` at `0x1403d23f7`
- `watchdog!WdLogSingleEntry2` at `0x1403d247d`
- `watchdog!WdLogSingleEntry2` at `0x1403d24fb`
- `watchdog!WdLogSingleEntry2` at `0x1403d268a`
- `watchdog!WdLogSingleEntry2` at `0x1403d26e8`
- `watchdog!WdLogSingleEntry2` at `0x1403d2771`
- `watchdog!WdLogSingleEntry2` at `0x1403d2e2f`
- `watchdog!WdLogSingleEntry2` at `0x1403d31e9`
- `watchdog!WdLogSingleEntry2` at `0x1403d3214`
- `watchdog!WdLogSingleEntry2` at `0x1403d328a`
- `watchdog!WdLogSingleEntry2` at `0x1403d32bb`
- `watchdog!WdLogSingleEntry2` at `0x1403d32ec`
- `watchdog!WdLogSingleEntry2` at `0x1403d3316`
- `watchdog!WdLogSingleEntry2` at `0x1403d3347`
- `watchdog!WdLogSingleEntry2` at `0x1403d337b`
- `watchdog!WdLogSingleEntry2` at `0x1403d33a5`
- `watchdog!WdLogSingleEntry2` at `0x1403d219f`
- `watchdog!WdLogSingleEntry2` at `0x1403d221e`
- `watchdog!WdLogSingleEntry2` at `0x1403d2302`
- `watchdog!WdLogSingleEntry2` at `0x1403d23f7`
- `watchdog!WdLogSingleEntry2` at `0x1403d247d`
- `watchdog!WdLogSingleEntry2` at `0x1403d24fb`
- `watchdog!WdLogSingleEntry2` at `0x1403d268a`
- `watchdog!WdLogSingleEntry2` at `0x1403d26e8`
- `watchdog!WdLogSingleEntry2` at `0x1403d2771`
- `watchdog!WdLogSingleEntry2` at `0x1403d2e2f`
- `watchdog!WdLogSingleEntry2` at `0x1403d31e9`
- `watchdog!WdLogSingleEntry2` at `0x1403d3214`
- `watchdog!WdLogSingleEntry2` at `0x1403d328a`
- `watchdog!WdLogSingleEntry2` at `0x1403d32bb`
- `watchdog!WdLogSingleEntry2` at `0x1403d32ec`
- `watchdog!WdLogSingleEntry2` at `0x1403d3316`
- `watchdog!WdLogSingleEntry2` at `0x1403d3347`
- `watchdog!WdLogSingleEntry2` at `0x1403d337b`
- `watchdog!WdLogSingleEntry2` at `0x1403d33a5`
- `watchdog!WdLogSingleEntry3` at `0x1403d2296`
- `watchdog!WdLogSingleEntry3` at `0x1403d257b`
- `watchdog!WdLogSingleEntry3` at `0x1403d2b38`
- `watchdog!WdLogSingleEntry3` at `0x1403d2c7c`
- `watchdog!WdLogSingleEntry3` at `0x1403d2ce8`
- `watchdog!WdLogSingleEntry3` at `0x1403d2d1a`
- `watchdog!WdLogSingleEntry3` at `0x1403d2d53`
- `watchdog!WdLogSingleEntry3` at `0x1403d2d95`
- `watchdog!WdLogSingleEntry3` at `0x1403d2296`
- `watchdog!WdLogSingleEntry3` at `0x1403d257b`
- `watchdog!WdLogSingleEntry3` at `0x1403d2b38`
- `watchdog!WdLogSingleEntry3` at `0x1403d2c7c`
- `watchdog!WdLogSingleEntry3` at `0x1403d2ce8`
- `watchdog!WdLogSingleEntry3` at `0x1403d2d1a`
- `watchdog!WdLogSingleEntry3` at `0x1403d2d53`
- `watchdog!WdLogSingleEntry3` at `0x1403d2d95`
- `watchdog!WdLogSingleEntry0` at `0x1403d295d`
- `watchdog!WdLogSingleEntry0` at `0x1403d2a1f`
- `watchdog!WdLogSingleEntry0` at `0x1403d2ad9`
- `watchdog!WdLogSingleEntry0` at `0x1403d2fc9`
- `watchdog!WdLogSingleEntry0` at `0x1403d295d`
- `watchdog!WdLogSingleEntry0` at `0x1403d2a1f`
- `watchdog!WdLogSingleEntry0` at `0x1403d2ad9`
- `watchdog!WdLogSingleEntry0` at `0x1403d2fc9`
- `watchdog!WdLogSingleEntry1` at `0x1403d3093`
- `watchdog!WdLogSingleEntry1` at `0x1403d31af`
- `watchdog!WdLogSingleEntry1` at `0x1403d3093`
- `watchdog!WdLogSingleEntry1` at `0x1403d31af`

## string_xrefs

- `0x1403d21b0`: `Input buffer size (0x%I64x) was too small for DXGK_IDD_SET_DISPLAY_CONFIGURATION, returning 0x%I64x.`
- `0x1403d22a6`: `Input buffer (size = 0x%I64x) was too small for 0x%I64x paths of DXGK_IDD_PATH_CONFIG, returning 0x%I64x.`
- `0x1403d222e`: `IddSetDisplayConfig has too many paths (0x%I64x), returning 0x%I64x.`
- `0x1403d2403`: `Caller specified PathCount exceeds the number of VidPn sourrce on adapter (0x%I64x), returning 0x%I64x.`
- `0x1403d2313`: `Output buffer size (0x%I64x) was too small for DXGK_IDD_SET_DISPLAY_CONFIGURATION_OUTPUT, returning 0x%I64x.`
- `0x1403d269b`: `Some but not all paths contained a mode in DXGK_IDD_SET_DISPLAY_CONFIGURATION on adapter 0x%I64x, returning 0x%I64x.`
- `0x1403d258c`: `Failed to wait for all pending connection changes to be completed on adapter 0x%I64x with ntStatus 0x%I64x, returning 0x%I64x.`
- `0x1403d2c88`: `Failed to set monitor DPI override on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).`
- `0x1403d26f9`: `Did not find primary path from DXGK_IDD_SET_DISPLAY_CONFIGURATION on adapter 0x%I64x, returning 0x%I64x.`
- `0x1403d2d30`: `Failed to set monitor colorimetry override on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).`
- `0x1403d2cf4`: `Failed to set monitor size override on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).`
- `0x1403d296b`: `!MonitorAndLinkCaps.HDR10`
- `0x1403d2b4e`: `Failed to set monitor color mode on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).`
- `0x1403d2aea`: `NT_SUCCESS(TempStatus)`
- `0x1403d2dab`: `Failed to set monitor mapping override on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).`
- `0x1403d2d69`: `Failed to set monitor SDR white level override on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).`
- `0x1403d32c7`: `Sending SetDisplayConfig ALPC message from display broker disabled session 0x%I64x, returning 0x%I64x.`
- `0x1403d2fda`: `Cannot allocate buffer to hold the SetDisplayConfig ALPC message`
- `0x1403d3224`: `Failed to send Display broker message in session 0x%I64x, status 0x%I64x`
- `0x1403d30a4`: `Failed to initialize display broker message, (Status = 0x%I64x).`

## pseudocode

```c
__int64 __fastcall DxgkIddHandleSetDisplayConfig(
        unsigned int a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned int a4,
        _DWORD *a5,
        _DWORD *a6,
        int *a7)
{
  unsigned __int64 v9; // rsi
  __int64 result; // rax
  __int64 v11; // rcx
  unsigned int v12; // edx
  struct _LUID *v13; // rdx
  int v14; // r8d
  int v15; // r15d
  struct _LUID v16; // rcx
  const wchar_t *v17; // r9
  int v18; // r9d
  void *v19; // rsi
  __int64 v20; // r12
  int v21; // eax
  unsigned int v22; // esi
  int v23; // eax
  struct DXGGLOBAL *Global; // rax
  __int64 i; // rax
  unsigned int *v26; // r15
  __int64 v27; // r12
  unsigned int *v28; // r13
  int v29; // eax
  int v30; // eax
  unsigned int v31; // ecx
  DXGK_STANDARD_COLORIMETRY_FLAGS v32; // eax
  int v33; // eax
  unsigned int v34; // edx
  int MonitorHandle; // eax
  void *v36; // r8
  unsigned int v37; // eax
  int IsMonitorAndLinkHDRCapable; // eax
  int v39; // r13d
  int IsMonitorAndDriverWCGCapable; // eax
  int v41; // r13d
  int v42; // eax
  __int64 v43; // rbx
  int v44; // eax
  char *v45; // rax
  unsigned int v46; // r13d
  __int64 v47; // rcx
  struct DXGGLOBAL *v48; // rax
  int v49; // eax
  __int64 v50; // rbx
  const wchar_t *v51; // r9
  __int64 v52; // rcx
  __int64 v53; // rbx
  __int64 v54; // rcx
  __int64 CurrentProcess; // rax
  int ProcessSessionId; // eax
  __int64 v57; // r12
  struct DXGGLOBAL *v58; // rax
  int v59; // eax
  const wchar_t *v60; // r9
  DXGGLOBAL *v61; // rax
  struct DXGSESSIONDATA *SessionData; // rax
  __int64 v63; // rcx
  __int64 v64; // r15
  __int64 v65; // rax
  __int64 v66; // rbx
  int v67; // eax
  unsigned int v68; // r15d
  int v69; // eax
  int v70; // eax
  int v71; // ebx
  struct _LUID *v72[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v73; // [rsp+60h] [rbp-A0h] BYREF
  bool v74; // [rsp+61h] [rbp-9Fh] BYREF
  __int64 v75; // [rsp+68h] [rbp-98h] BYREF
  char v76; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v77[24]; // [rsp+78h] [rbp-88h] BYREF
  int v78; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v79; // [rsp+98h] [rbp-68h] BYREF
  unsigned int *v80; // [rsp+A0h] [rbp-60h] BYREF
  DXGSESSIONDATA *v81; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v82; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v83; // [rsp+B8h] [rbp-48h] BYREF
  struct HDXGMONITOR__ *v84; // [rsp+C0h] [rbp-40h] BYREF
  int v85; // [rsp+C8h] [rbp-38h] BYREF
  int v86; // [rsp+CCh] [rbp-34h] BYREF
  int v87; // [rsp+D0h] [rbp-30h] BYREF
  PVOID Object; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v89[48]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v90; // [rsp+110h] [rbp+10h] BYREF
  char v91[8]; // [rsp+118h] [rbp+18h] BYREF
  __int64 v92; // [rsp+120h] [rbp+20h]
  unsigned __int64 CurrentProcessSessionId; // [rsp+128h] [rbp+28h] BYREF
  union _LARGE_INTEGER v94; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v95; // [rsp+138h] [rbp+38h] BYREF
  __int64 v96; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v97; // [rsp+148h] [rbp+48h]
  __int64 v98; // [rsp+150h] [rbp+50h] BYREF
  unsigned int v99; // [rsp+158h] [rbp+58h]
  unsigned int v100; // [rsp+15Ch] [rbp+5Ch]
  _DXGK_COLORIMETRY v101; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v102[2]; // [rsp+198h] [rbp+98h] BYREF
  _QWORD v103[3]; // [rsp+1A8h] [rbp+A8h] BYREF
  _QWORD v104[6]; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+1F0h] [rbp+F0h] BYREF
  char v106; // [rsp+220h] [rbp+120h]
  _BYTE v107[144]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v108[88]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v90 = 0;
  Object = a3;
  v9 = a2;
  v79 = a1;
  v81 = 0;
  CurrentProcessSessionId = (unsigned int)PsGetCurrentProcessSessionId();
  v104[1] = &v90;
  v104[2] = &CurrentProcessSessionId;
  v104[3] = &v81;
  v104[4] = &v79;
  v104[0] = a7;
  DXGKCALLONEXIT__lambda_ee7824d0677b80b9c05e9ff72fc1715b_(v89, v104);
  *a7 = -1073741823;
  if ( (unsigned int)v9 < 4 )
  {
    WdLogSingleEntry2(2, (unsigned int)v9, -1073741789);
    WdLogGlobalForLineNumber = 770;
    result = DxgkLogInternalTriageEvent(
               0,
               0x40000,
               -1,
               (unsigned int)L"Input buffer size (0x%I64x) was too small for DXGK_IDD_SET_DISPLAY_CONFIGURATION, returning 0x%I64x.",
               v9,
               -1073741789,
               0,
               0,
               0);
    *a7 = -1073741789;
    if ( v89[40] )
      return lambda_ee7824d0677b80b9c05e9ff72fc1715b_::operator()(v89);
    return result;
  }
  v80 = a3;
  v11 = *a3;
  if ( (unsigned int)v11 >= 0x10 )
  {
    WdLogSingleEntry2(2, (unsigned int)v11, -1073741811);
    WdLogGlobalForLineNumber = 783;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"IddSetDisplayConfig has too many paths (0x%I64x), returning 0x%I64x.",
      *v80,
      -1073741811,
      0,
      0,
      0);
    *a7 = -1073741811;
    return DXGKCALLONEXIT__lambda_ee7824d0677b80b9c05e9ff72fc1715b____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v89);
  }
  if ( v9 < 132 * v11 + 4 )
  {
    WdLogSingleEntry3(2, v9, *a3, -1073741789);
    WdLogGlobalForLineNumber = 797;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Input buffer (size = 0x%I64x) was too small for 0x%I64x paths of DXGK_IDD_PATH_CONFIG, returning 0x%I64x.",
      v9,
      *v80,
      -1073741789,
      0,
      0);
LABEL_8:
    *a7 = -1073741789;
    return DXGKCALLONEXIT__lambda_ee7824d0677b80b9c05e9ff72fc1715b____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v89);
  }
  if ( a4 < 8 )
  {
    WdLogSingleEntry2(2, v9, -1073741789);
    WdLogGlobalForLineNumber = 809;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Output buffer size (0x%I64x) was too small for DXGK_IDD_SET_DISPLAY_CONFIGURATION_OUTPUT, returning 0x%I64x.",
      v9,
      -1073741789,
      0,
      0,
      0);
    goto LABEL_8;
  }
  v12 = v79;
  *a5 = 0;
  *a6 = 8;
  v72[0] = 0;
  DXGADAPTER_REFERENCE::AssignByHandle((struct DXGADAPTER **)v72, v12);
  if ( !v72[0] )
  {
    if ( (unsigned int)Feature_DcuNoBugCheckOnNoAdapter__private_IsEnabledDeviceUsageNoInline() )
    {
      WdLogSingleEntry2(3, v79, -1071775725);
      WdLogGlobalForLineNumber = 829;
      v71 = -1071775725;
    }
    else
    {
      v71 = -1073741811;
      WdLogSingleEntry2(3, v79, -1073741811);
      WdLogGlobalForLineNumber = 836;
    }
    *a7 = v71;
    goto LABEL_150;
  }
  v90 = *(_QWORD *)&v72[0][51].HighPart;
  v82 = 0;
  DXGADAPTER::IsAdapterSessionized((DXGADAPTER *)v72[0], v13, 0, &v82);
  v15 = v14 + 1;
  CurrentProcessSessionId = v82;
  DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(
    (DXGADAPTERSTOPRESETLOCKSHARED *)v77,
    (struct DXGADAPTER *)v72[0],
    v14 + 1);
  if ( v72[0][25].LowPart != v15 || BYTE1(v72[0][393].LowPart) )
  {
    WdLogSingleEntry2(3, v72[0], -1071775725);
    WdLogGlobalForLineNumber = 855;
    goto LABEL_26;
  }
  v16 = v72[0][406];
  if ( !*(_QWORD *)&v16 || (v72[0][55].HighPart & 0x100) == 0 )
  {
    WdLogSingleEntry2(2, v72[0], -1073741811);
    v17 = L"Caller specified adapter (0x%I64x) is not a indirect display adapter, returning 0x%I64x.";
    WdLogGlobalForLineNumber = 864;
    goto LABEL_18;
  }
  if ( *v80 > *(_DWORD *)(*(_QWORD *)&v16 + 96LL) )
  {
    WdLogSingleEntry2((unsigned int)(v15 + 1), v72[0], -1073741811);
    v17 = L"Caller specified PathCount exceeds the number of VidPn sourrce on adapter (0x%I64x), returning 0x%I64x.";
    WdLogGlobalForLineNumber = 873;
LABEL_18:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v17, (__int64)v72[0], -1073741811, 0, 0, 0);
    *a7 = -1073741811;
    goto LABEL_19;
  }
  v83 = 0;
  if ( !DXGADAPTER::IsAdapterSessionized((DXGADAPTER *)v72[0], v72[0], &v83, 0) )
  {
    WdLogSingleEntry2((unsigned int)(v18 + 2), v72[0], -1073741811);
    v17 = L"Caller specified adapter (0x%I64x) is not a sessionized adapter, returning 0x%I64x.";
    WdLogGlobalForLineNumber = 888;
    goto LABEL_18;
  }
  v19 = (void *)v72[0][27];
  ObfReferenceObject(v19);
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v77);
  v20 = v83;
  v21 = DxgkWaitForPnPTransitionDone(0, 0, v83, 2);
  *a7 = v21;
  if ( v21 < 0 )
  {
    ObfDereferenceObject(v19);
    WdLogSingleEntry2(2, (unsigned int)v20, *a7);
    WdLogGlobalForLineNumber = 923;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to wait for all pending PnP transition to be done in session 0x%I64x (ntStatus = 0x%I64x).",
      v20,
      *a7,
      0,
      0,
      0);
    goto LABEL_19;
  }
  *a7 = DpiFdoWaitConnectionChangeComplete(v19);
  ObfDereferenceObject(v19);
  if ( *a7 < 0 )
  {
    WdLogSingleEntry3(2, v72[0], *a7, -1071775725);
    WdLogGlobalForLineNumber = 945;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed to wait for all pending connection changes to be completed on adapter 0x%I64x with ntStatus 0"
                     "x%I64x, returning 0x%I64x.",
      (__int64)v72[0],
      *a7,
      -1071775725,
      0,
      0);
LABEL_26:
    *a7 = -1071775725;
    goto LABEL_19;
  }
  DXGADAPTERSTOPRESETLOCKSHARED::Acquire((DXGADAPTERSTOPRESETLOCKSHARED *)v77);
  if ( v72[0][25].LowPart != v15 || BYTE1(v72[0][393].LowPart) )
  {
    WdLogSingleEntry2(3, v72[0], -1071775725);
    WdLogGlobalForLineNumber = 962;
    goto LABEL_26;
  }
  v78 = 0;
  v103[0] = v72;
  v22 = 0;
  v73 = 0;
  v103[1] = &v78;
  v103[2] = &v73;
  while ( v22 < *v80 )
  {
    v23 = lambda_a67ab94360878e3eb2134876255634af_::operator()(v103, v22, &v80[33 * v22 + 1]);
    *a7 = v23;
    if ( v23 < 0 )
      goto LABEL_19;
    v22 += v15;
  }
  if ( v78 )
  {
    if ( v78 != *v80 )
    {
      *a7 = -1073741811;
      WdLogSingleEntry2(2, v72[0], -1073741811);
      WdLogGlobalForLineNumber = 1060;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Some but not all paths contained a mode in DXGK_IDD_SET_DISPLAY_CONFIGURATION on adapter 0x%I64x, "
                       "returning 0x%I64x.",
        (__int64)v72[0],
        *a7,
        0,
        0,
        0);
      goto LABEL_19;
    }
    if ( !v73 )
    {
      *a7 = -1073741811;
      WdLogSingleEntry2(2, v72[0], -1073741811);
      WdLogGlobalForLineNumber = 1069;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Did not find primary path from DXGK_IDD_SET_DISPLAY_CONFIGURATION on adapter 0x%I64x, returning 0x%I64x.",
        (__int64)v72[0],
        *a7,
        0,
        0,
        0);
      goto LABEL_19;
    }
    Global = DXGGLOBAL::GetGlobal();
    REMOTEMONITORMAPPING::Clear((struct DXGGLOBAL *)((char *)Global + 305272), 0);
  }
  COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v107, (struct DXGADAPTER *const)v72[0], 0);
  if ( COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v107, 0) < 0 )
  {
    WdLogSingleEntry2(3, SHIDWORD(v90), (unsigned int)v90);
    WdLogGlobalForLineNumber = 1083;
    goto LABEL_41;
  }
  for ( i = 0; ; i = (unsigned int)(v75 + 1) )
  {
    v26 = v80;
    LODWORD(v75) = i;
    if ( (unsigned int)i >= *v80 )
      break;
    v27 = 33 * i;
    v28 = &v80[33 * i];
    if ( (v28[1] & 2) != 0 )
    {
      v29 = MonitorSetScaleFactorOverride(v72[0], v28[4], v80[v27 + 14]);
      *a7 = v29;
      if ( v29 < 0 )
      {
        v50 = (unsigned int)v75;
        WdLogSingleEntry3(2, v28[4], (unsigned int)v75, v29);
        v51 = L"Failed to set monitor DPI override on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).";
        WdLogGlobalForLineNumber = 1103;
LABEL_104:
        v52 = v28[4];
LABEL_105:
        DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v51, v52, v50, *a7, 0, 0);
        goto LABEL_41;
      }
    }
    if ( (v26[v27 + 1] & 4) != 0 )
    {
      v30 = MonitorSetPhysicalSizeOverride(v72[0], v28[4], v26[v27 + 15], v26[v27 + 16]);
      *a7 = v30;
      if ( v30 < 0 )
      {
        v50 = (unsigned int)v75;
        WdLogSingleEntry3(2, v28[4], (unsigned int)v75, v30);
        v51 = L"Failed to set monitor size override on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).";
        WdLogGlobalForLineNumber = 1119;
        goto LABEL_104;
      }
    }
    if ( (v26[v27 + 1] & 8) != 0 )
    {
      v31 = v26[v27 + 29];
      v101.RedPoint = *(D3DKMDT_2DOFFSET *)&v26[v27 + 17];
      v101.GreenPoint = *(D3DKMDT_2DOFFSET *)&v26[v27 + 19];
      v101.BluePoint = *(D3DKMDT_2DOFFSET *)&v26[v27 + 21];
      v101.WhitePoint = *(D3DKMDT_2DOFFSET *)&v26[v27 + 23];
      v101.MinLuminance = v26[v27 + 25];
      v101.MaxLuminance = v26[v27 + 26];
      v101.MaxFullFrameLuminance = v26[v27 + 27];
      v101.FormatBitDepths.Value = v26[v27 + 28];
      v32.Value = (v31 & 1) != 0;
      v101.StandardColorimetryFlags = v32;
      if ( (v31 & 2) != 0 )
      {
        v32.Value |= 2u;
        v101.StandardColorimetryFlags = v32;
      }
      if ( (v31 & 4) != 0 )
        v101.StandardColorimetryFlags.Value = v32.Value | 4;
      v33 = MonitorSetDriverColorimetryOverride(v72[0], v28[4], &v101);
      *a7 = v33;
      if ( v33 < 0 )
      {
        v50 = (unsigned int)v75;
        WdLogSingleEntry3(2, v28[4], (unsigned int)v75, v33);
        WdLogGlobalForLineNumber = 1159;
        v51 = L"Failed to set monitor colorimetry override on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).";
        v52 = v26[v27 + 4];
        goto LABEL_105;
      }
      *a7 = MonitorSetLastWireformat(v72[0], v28[4], (union _D3DKMDT_WIRE_FORMAT_AND_PREFERENCE)v26[v27 + 28]);
    }
    if ( (v26[v27 + 1] & 1) != 0 )
    {
      v34 = v28[4];
      v84 = 0;
      MonitorHandle = MonitorGetMonitorHandle(v72[0], v34, 0, DxgkIddHandleSetDisplayConfig, &v84);
      *a7 = MonitorHandle;
      if ( MonitorHandle >= 0 )
      {
        v37 = v26[v27 + 13];
        if ( v37 == 3 )
        {
          v86 = 0;
          v85 = 0;
          IsMonitorAndLinkHDRCapable = MonitorIsMonitorAndLinkHDRCapable(
                                         v84,
                                         (union MONITOR_AND_LINK_HDR_CAPS *)&v86,
                                         (enum MonitorAndLinkHDRIncapableReason *)&v85);
          v39 = v85;
          *a7 = IsMonitorAndLinkHDRCapable;
          if ( v39 )
          {
            if ( (v86 & 1) != 0 )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 1182;
              DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!MonitorAndLinkCaps.HDR10", 1182, 0, 0, 0, 0);
            }
            *a7 = -1073741637;
            if ( (v39 & 2) != 0 )
              *a5 |= 1u;
            if ( (v39 & 4) != 0 )
              *a5 |= 2u;
            if ( (v39 & 8) != 0 )
              *a5 |= 8u;
            if ( (v39 & 0x10) != 0 )
              *a5 |= 0x10u;
            if ( (v39 & 0x20) != 0 )
              *a5 |= 0x20u;
            goto LABEL_81;
          }
        }
        else if ( v37 == 2 )
        {
          v74 = 0;
          v87 = 0;
          IsMonitorAndDriverWCGCapable = MonitorIsMonitorAndDriverWCGCapable(
                                           v84,
                                           &v74,
                                           (enum MonitorAndLinkWCGIncapableReason *)&v87);
          v41 = v87;
          *a7 = IsMonitorAndDriverWCGCapable;
          if ( v41 )
          {
            if ( v74 )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 1220;
              DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"!MonitorAndDriverWCGCapable", 1220, 0, 0, 0, 0);
            }
            *a7 = -1073741637;
            if ( (v41 & 2) != 0 )
              *a5 |= 4u;
            if ( (v41 & 4) != 0 )
              *a5 |= 0x40u;
            if ( (v41 & 8) != 0 )
              *a5 |= 0x80u;
LABEL_81:
            a5[1] = v75;
          }
        }
        if ( *a7 >= 0 )
        {
          v42 = MonitorEnableDisableHdr(v84, v26[v27 + 13] == 3);
          *a7 = v42;
          if ( v42 >= 0 )
            *a7 = MonitorEnableDisableWcg(v84, v26[v27 + 13] == 2);
        }
        if ( MonitorReleaseMonitorHandle(v72[0], v84, v36) < 0 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 1253;
          DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(TempStatus)", 1253, 0, 0, 0, 0);
        }
      }
      if ( *a7 < 0 )
      {
        v43 = (unsigned int)v75;
        WdLogSingleEntry3(2, v26[v27 + 4], (unsigned int)v75, *a7);
        WdLogGlobalForLineNumber = 1261;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to set monitor color mode on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).",
          v26[v27 + 4],
          v43,
          *a7,
          0,
          0);
        goto LABEL_41;
      }
    }
    if ( (v26[v27 + 1] & 0x10) != 0 )
    {
      v44 = MonitorSetSDRWhiteLevelOverride(v72[0], v26[v27 + 4], v26[v27 + 30]);
      *a7 = v44;
      if ( v44 < 0 )
      {
        v53 = (unsigned int)v75;
        WdLogSingleEntry3(2, v26[v27 + 4], (unsigned int)v75, v44);
        WdLogGlobalForLineNumber = 1277;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Failed to set monitor SDR white level override on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).",
          v26[v27 + 4],
          v53,
          *a7,
          0,
          0);
        goto LABEL_41;
      }
    }
    if ( v78 == *v80 )
    {
      if ( !(unsigned int)Feature_VAIL_Fake_Monitor_Projection__private_IsEnabledDeviceUsageNoInline()
        || v26[v27 + 31]
        || v26[v27 + 32]
        || v26[v27 + 33] )
      {
        v46 = v75;
      }
      else
      {
        v45 = (char *)Object;
        v46 = v75;
        v47 = 132LL * (unsigned int)v75;
        *(_DWORD *)((char *)Object + v47 + 124) = 1;
        *(_DWORD *)&v45[v47 + 128] = 1;
        *(_DWORD *)&v45[v47 + 132] = v46;
      }
      if ( v26[v27 + 31] || v26[v27 + 32] || v26[v27 + 33] )
      {
        v98 = *(_QWORD *)&v26[v27 + 2];
        v99 = v26[v27 + 4];
        v96 = *(_QWORD *)&v26[v27 + 31];
        v97 = v26[v27 + 33];
        v100 = v46;
        v48 = DXGGLOBAL::GetGlobal();
        v49 = REMOTEMONITORMAPPING::AddMapping(
                (struct DXGGLOBAL *)((char *)v48 + 305272),
                (struct REMOTEMONITORMAPPING::PATH_IDENTIFIER_HOST *)&v96,
                (struct REMOTEMONITORMAPPING::PATH_IDENTIFIER_GUEST *)&v98);
        *a7 = v49;
        if ( v49 < 0 )
        {
          v50 = v46;
          WdLogSingleEntry3(2, v26[v27 + 4], v46, v49);
          WdLogGlobalForLineNumber = 1312;
          v51 = L"Failed to set monitor mapping override on target 0x%I64x on path 0x%I64x, (Status = 0x%I64x).";
          v52 = v26[v27 + 4];
          goto LABEL_105;
        }
      }
    }
  }
  COREADAPTERACCESS::Release((COREADAPTERACCESS *)v107);
  if ( v78 )
  {
    v106 = 0;
    CurrentProcess = PsGetCurrentProcess(v54);
    ProcessSessionId = PsGetProcessSessionId(CurrentProcess);
    v57 = v83;
    if ( ProcessSessionId != v83 )
    {
      Object = 0;
      v58 = DXGGLOBAL::GetGlobal();
      v59 = DXGSESSIONMGR::ReferenceSessionCSRSSProcess(
              *((DXGSESSIONMGR **)v58 + 123),
              v57,
              (struct _KPROCESS **)&Object);
      *a7 = v59;
      if ( v59 < 0 )
      {
        WdLogSingleEntry2(2, (unsigned int)v57, v59);
        v60 = L"Failed to get CSRSS process from session 0x%I64x, (Status = 0x%I64x).";
        WdLogGlobalForLineNumber = 1343;
        goto LABEL_114;
      }
      CPROCESSATTACHHELPER::Attach(&ApcState, (PRKPROCESS)Object);
      ObfDereferenceObject(Object);
    }
    v61 = DXGGLOBAL::GetGlobal();
    SessionData = DXGGLOBAL::GetSessionData(v61);
    v81 = SessionData;
    if ( *((_BYTE *)SessionData + 18992) && *((_BYTE *)SessionData + 18496) )
    {
      if ( !KeReadStateEvent(*(PRKEVENT *)(*(_QWORD *)&v72[0][406] + 672LL)) )
      {
        LOBYTE(v63) = 1;
        if ( (unsigned __int8)WdIsDebuggerPresent(v63) )
        {
          DbgPrintEx(0x65u, 0, "Breaking in to allow debug of missing GDOs when PnP transition is done.");
          __debugbreak();
        }
        v82 = 0;
        DxgkLogCodePointPacketForSession(114, v57, 0, 0, 0, 0);
      }
      if ( !KeReadStateEvent(*(PRKEVENT *)(*(_QWORD *)&v72[0][406] + 672LL)) )
      {
        v82 = 0;
        DxgkLogCodePointPacketForSession(114, v57, 0, 0, 0, 0);
      }
      memset(v108, 0, sizeof(v108));
      v64 = 216LL * *v80;
      v65 = operator new[](v64 + 112, 1265072196, 256);
      v66 = v65;
      if ( v65 )
      {
        v75 = v65;
        *(_QWORD *)v65 = &rc_buffer<DispBroker::AlpcRequest<7>>::`vftable';
        *(_QWORD *)v65 = &rc_buffer<DispBroker::AlpcRequest<7>>::`vftable';
        *(_DWORD *)(v65 + 8) = 1;
        v76 = 0;
        v91[0] = 0;
        CDisplayScenarioContextScope::ContextScopeConstructor((CDisplayScenarioContextScope *)v91, 0, 0x47u, 0);
        v102[0] = &v80;
        v102[1] = &v76;
        v67 = InitDisplayBrokerMessage_DispBroker::AlpcRequest_7___lambda_2b0a0ae50116c8aa91dc0eedbc3a4823___DxgkSampleDisplayState_(
                v66 + 16,
                v92,
                v102,
                (unsigned int)v64);
        *a7 = v67;
        if ( v67 >= 0 )
        {
          v68 = DXGSESSIONDATA::CacheIddDisplayConfigRequest(v81, &v75);
          DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v77);
          v95 = 88;
          v94.QuadPart = (-(__int64)(g_bSkuSupportMultipleUsers != 0) & 0xFFFFFFFF8EC04D00uLL) - 100000000;
          *a7 = DxgkSendDisplayBrokerMessage(
                  0x120000u,
                  (struct _PORT_MESSAGE *)(v66 + 16),
                  0,
                  (struct _PORT_MESSAGE *)v108,
                  &v95,
                  0,
                  &v94);
          DXGADAPTERSTOPRESETLOCKSHARED::Acquire((DXGADAPTERSTOPRESETLOCKSHARED *)v77);
          if ( v72[0][25].LowPart != 1 || BYTE1(v72[0][393].LowPart) )
          {
            WdLogSingleEntry2(3, v72[0], -1071775725);
            WdLogGlobalForLineNumber = 1647;
            *a7 = -1071775725;
          }
          else
          {
            v69 = *a7;
            if ( *a7 == -1073741772 )
            {
              WdLogSingleEntry1(3, *(unsigned int *)v81);
              WdLogGlobalForLineNumber = 1660;
              *a7 = 0;
            }
            else if ( v69 == 192 )
            {
              *a7 = -1073741749;
              WdLogSingleEntry2(3, *(unsigned int *)v81, -1073741749);
              WdLogGlobalForLineNumber = 1668;
            }
            else if ( v69 >= 0 )
            {
              v70 = *(_DWORD *)&v108[80];
              if ( *(int *)&v108[80] >= 0 )
              {
                DXGSESSIONDATA::SetDisplayConfigDone(v81, v68);
                v70 = *(_DWORD *)&v108[80];
              }
              *a7 = v70;
            }
            else
            {
              WdLogSingleEntry2(2, *(unsigned int *)v81, *a7);
              WdLogGlobalForLineNumber = 1674;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"Failed to send Display broker message in session 0x%I64x, status 0x%I64x",
                *(unsigned int *)v81,
                *a7,
                0,
                0,
                0);
            }
          }
        }
        else
        {
          WdLogSingleEntry1(2, v67);
          WdLogGlobalForLineNumber = 1601;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Failed to initialize display broker message, (Status = 0x%I64x).",
            *a7,
            0,
            0,
            0,
            0);
        }
        CDisplayScenarioContextScope::~CDisplayScenarioContextScope((CDisplayScenarioContextScope *)v91);
        auto_rc<rc_buffer<DispBroker::AlpcRequest<7>>>::reset(&v75, 0);
      }
      else
      {
        WdLogSingleEntry0(6);
        WdLogGlobalForLineNumber = 1435;
        DxgkLogInternalTriageEvent(
          0,
          262145,
          -1,
          (unsigned int)L"Cannot allocate buffer to hold the SetDisplayConfig ALPC message",
          1435,
          0,
          0,
          0,
          0);
        *a7 = -1073741801;
      }
    }
    else
    {
      *a7 = -1071775725;
      WdLogSingleEntry2(2, v57, -1071775725);
      v60 = L"Sending SetDisplayConfig ALPC message from display broker disabled session 0x%I64x, returning 0x%I64x.";
      WdLogGlobalForLineNumber = 1365;
LABEL_114:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v60, v57, *a7, 0, 0, 0);
    }
    CPROCESSATTACHHELPER::Detach((CPROCESSATTACHHELPER *)&ApcState);
  }
LABEL_41:
  COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v107);
LABEL_19:
  DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED((DXGADAPTERSTOPRESETLOCKSHARED *)v77);
LABEL_150:
  DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v72, 0);
  return DXGKCALLONEXIT__lambda_ee7824d0677b80b9c05e9ff72fc1715b____::_2_::DXGKCALLONEXIT::_DXGKCALLONEXIT(v89);
}

```

## disassembly

```asm
0x1403d20d0  mov     [rsp-8+arg_18], rbx
0x1403d20d5  push    rbp
0x1403d20d6  push    rsi
0x1403d20d7  push    rdi
0x1403d20d8  push    r12
0x1403d20da  push    r13
0x1403d20dc  push    r14
0x1403d20de  push    r15
0x1403d20e0  lea     rbp, [rsp-230h]
0x1403d20e8  sub     rsp, 330h
0x1403d20ef  mov     rax, cs:__security_cookie
0x1403d20f6  xor     rax, rsp
0x1403d20f9  mov     [rbp+260h+var_40], rax
0x1403d2100  mov     rbx, [rbp+260h+arg_20]
0x1403d2107  xor     r13d, r13d
0x1403d210a  mov     r15, [rbp+260h+arg_28]
0x1403d2111  mov     r14d, r9d
0x1403d2114  mov     rdi, [rbp+260h+arg_30]
0x1403d211b  mov     r12, r8
0x1403d211e  mov     [rbp+260h+var_250], r13
0x1403d2122  mov     [rbp+260h+Object], r8
0x1403d2126  mov     esi, edx
0x1403d2128  mov     [rbp+260h+var_2C8], ecx
0x1403d212b  call    cs:__imp_PsGetCurrentProcessSessionId
0x1403d2132  nop     dword ptr [rax+rax+00h]
0x1403d2137  lea     rdx, [rbp+260h+var_1A0]
0x1403d213e  mov     [rbp+260h+var_2B8], r13
0x1403d2142  mov     eax, eax
0x1403d2144  lea     rcx, [rbp+260h+var_280]
0x1403d2148  mov     [rbp+260h+var_238], rax
0x1403d214c  lea     rax, [rbp+260h+var_250]
0x1403d2150  mov     [rbp+260h+var_198], rax
0x1403d2157  lea     rax, [rbp+260h+var_238]
0x1403d215b  mov     [rbp+260h+var_190], rax
0x1403d2162  lea     rax, [rbp+260h+var_2B8]
0x1403d2166  mov     [rbp+260h+var_188], rax
0x1403d216d  lea     rax, [rbp+260h+var_2C8]
0x1403d2171  mov     [rbp+260h+var_180], rax
0x1403d2178  mov     [rbp+260h+var_1A0], rdi
0x1403d217f  call    DXGKCALLONEXIT__lambda_ee7824d0677b80b9c05e9ff72fc1715b___; DXGKCALLONEXIT__lambda_ee7824d0677b80b9c05e9ff72fc1715b_
0x1403d2184  mov     dword ptr [rdi], 0C0000001h
0x1403d218a  cmp     esi, 4
0x1403d218d  jnb     short loc_1403D2200
0x1403d218f  mov     r15, 0FFFFFFFFC0000023h
0x1403d2196  lea     ecx, [r13+2]
0x1403d219a  mov     r8, r15
0x1403d219d  mov     edx, esi
0x1403d219f  call    cs:__imp_WdLogSingleEntry2
0x1403d21a6  nop     dword ptr [rax+rax+00h]
0x1403d21ab  mov     [rsp+360h+var_320], r13
0x1403d21b0  lea     r9, aInputBufferSiz_1; "Input buffer size (0x%I64x) was too sma"...
0x1403d21b7  mov     [rsp+360h+var_328], r13
0x1403d21bc  or      r8d, 0FFFFFFFFh
0x1403d21c0  mov     [rsp+360h+var_330], r13
0x1403d21c5  mov     edx, 40000h
0x1403d21ca  mov     [rsp+360h+var_338], r15
0x1403d21cf  xor     ecx, ecx
0x1403d21d1  mov     [rsp+360h+var_340], rsi
0x1403d21d6  mov     cs:WdLogGlobalForLineNumber, 302h
0x1403d21e0  call    DxgkLogInternalTriageEvent
0x1403d21e5  mov     [rdi], r15d
0x1403d21e8  cmp     [rbp+260h+var_258], r13b
0x1403d21ec  jz      loc_1403D33D5
0x1403d21f2  lea     rcx, [rbp+260h+var_280]
0x1403d21f6  call    _lambda_ee7824d0677b80b9c05e9ff72fc1715b___operator__
0x1403d21fb  jmp     loc_1403D33D5
0x1403d2200  mov     [rbp+260h+var_2C0], r12
0x1403d2204  mov     ecx, [r12]
0x1403d2208  cmp     ecx, 10h
0x1403d220b  jb      short loc_1403D2271
0x1403d220d  mov     edx, ecx
0x1403d220f  mov     rbx, 0FFFFFFFFC000000Dh
0x1403d2216  mov     r8, rbx
0x1403d2219  mov     ecx, 2
0x1403d221e  call    cs:__imp_WdLogSingleEntry2
0x1403d2225  nop     dword ptr [rax+rax+00h]
0x1403d222a  mov     rax, [rbp+260h+var_2C0]
0x1403d222e  lea     r9, aIddsetdisplayc; "IddSetDisplayConfig has too many paths "...
0x1403d2235  mov     [rsp+360h+var_320], r13
0x1403d223a  or      r8d, 0FFFFFFFFh
0x1403d223e  mov     [rsp+360h+var_328], r13
0x1403d2243  mov     edx, 40000h
0x1403d2248  mov     cs:WdLogGlobalForLineNumber, 30Fh
0x1403d2252  mov     ecx, [rax]
0x1403d2254  mov     [rsp+360h+var_330], r13
0x1403d2259  mov     [rsp+360h+var_338], rbx
0x1403d225e  mov     [rsp+360h+var_340], rcx
0x1403d2263  xor     ecx, ecx
0x1403d2265  call    DxgkLogInternalTriageEvent
0x1403d226a  mov     [rdi], ebx
0x1403d226c  jmp     loc_1403D33CC
0x1403d2271  imul    rax, rcx, 84h
0x1403d2278  add     rax, 4
0x1403d227c  cmp     rsi, rax
0x1403d227f  jnb     short loc_1403D22EA
0x1403d2281  mov     r8, rcx
0x1403d2284  mov     r15, 0FFFFFFFFC0000023h
0x1403d228b  mov     r9, r15
0x1403d228e  mov     rdx, rsi
0x1403d2291  mov     ecx, 2
0x1403d2296  call    cs:__imp_WdLogSingleEntry3
0x1403d229d  nop     dword ptr [rax+rax+00h]
0x1403d22a2  mov     rax, [rbp+260h+var_2C0]
0x1403d22a6  lea     r9, aInputBufferSiz_0; "Input buffer (size = 0x%I64x) was too s"...
0x1403d22ad  mov     [rsp+360h+var_320], r13
0x1403d22b2  mov     [rsp+360h+var_328], r13
0x1403d22b7  mov     cs:WdLogGlobalForLineNumber, 31Dh
0x1403d22c1  mov     ecx, [rax]
0x1403d22c3  mov     [rsp+360h+var_330], r15
0x1403d22c8  mov     [rsp+360h+var_338], rcx
0x1403d22cd  or      r8d, 0FFFFFFFFh
0x1403d22d1  mov     [rsp+360h+var_340], rsi
0x1403d22d6  mov     edx, 40000h
0x1403d22db  xor     ecx, ecx
0x1403d22dd  call    DxgkLogInternalTriageEvent
0x1403d22e2  mov     [rdi], r15d
0x1403d22e5  jmp     loc_1403D33CC
0x1403d22ea  cmp     r14d, 8
0x1403d22ee  jnb     short loc_1403D2335
0x1403d22f0  mov     r15, 0FFFFFFFFC0000023h
0x1403d22f7  mov     rdx, rsi
0x1403d22fa  mov     r8, r15
0x1403d22fd  mov     ecx, 2
0x1403d2302  call    cs:__imp_WdLogSingleEntry2
0x1403d2309  nop     dword ptr [rax+rax+00h]
0x1403d230e  mov     [rsp+360h+var_320], r13
0x1403d2313  lea     r9, aOutputBufferSi; "Output buffer size (0x%I64x) was too sm"...
0x1403d231a  mov     [rsp+360h+var_328], r13
0x1403d231f  mov     [rsp+360h+var_330], r13
0x1403d2324  mov     [rsp+360h+var_338], r15
0x1403d2329  mov     cs:WdLogGlobalForLineNumber, 329h
0x1403d2333  jmp     short loc_1403D22CD
0x1403d2335  mov     edx, [rbp+260h+var_2C8]; unsigned int
0x1403d2338  lea     rcx, [rsp+360h+var_310]; this
0x1403d233d  mov     [rbx], r13d
0x1403d2340  mov     dword ptr [r15], 8
0x1403d2347  mov     [rsp+360h+var_310], r13
0x1403d234c  call    ?AssignByHandle@DXGADAPTER_REFERENCE@@QEAA_NI@Z; DXGADAPTER_REFERENCE::AssignByHandle(uint)
0x1403d2351  mov     rcx, [rsp+360h+var_310]; this
0x1403d2356  test    rcx, rcx
0x1403d2359  jz      loc_1403D3362
0x1403d235f  mov     rax, [rcx+19Ch]
0x1403d2366  lea     r9, [rbp+260h+var_2B0]; unsigned __int64 *
0x1403d236a  xor     r8d, r8d; unsigned int *
0x1403d236d  mov     [rbp+260h+var_250], rax
0x1403d2371  mov     [rbp+260h+var_2B0], r13
0x1403d2375  call    ?IsAdapterSessionized@DXGADAPTER@@QEBA_NPEAU_LUID@@PEAIPEA_K@Z; DXGADAPTER::IsAdapterSessionized(_LUID *,uint *,unsigned __int64 *)
0x1403d237a  mov     rcx, [rbp+260h+var_2B0]
0x1403d237e  lea     r15d, [r8+1]
0x1403d2382  mov     rdx, [rsp+360h+var_310]; struct DXGADAPTER *
0x1403d2387  mov     r8b, r15b; unsigned __int8
0x1403d238a  mov     [rbp+260h+var_238], rcx
0x1403d238e  lea     rcx, [rsp+360h+var_2E8]; this
0x1403d2393  call    ??0DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@PEAVDXGADAPTER@@E@Z; DXGADAPTERSTOPRESETLOCKSHARED::DXGADAPTERSTOPRESETLOCKSHARED(DXGADAPTER *,uchar)
0x1403d2398  mov     rax, [rsp+360h+var_310]
0x1403d239d  mov     ecx, [rax+0C8h]
0x1403d23a3  mov     rdx, [rsp+360h+var_310]; struct _LUID *
0x1403d23a8  cmp     ecx, r15d
0x1403d23ab  jnz     loc_1403D3338
0x1403d23b1  cmp     [rdx+0C49h], r13b
0x1403d23b8  jnz     loc_1403D3338
0x1403d23be  mov     rcx, [rdx+0CB0h]
0x1403d23c5  test    rcx, rcx
0x1403d23c8  jz      loc_1403D3307
0x1403d23ce  test    dword ptr [rdx+1BCh], 100h
0x1403d23d8  jz      loc_1403D3307
0x1403d23de  mov     rax, [rbp+260h+var_2C0]
0x1403d23e2  mov     ecx, [rcx+60h]
0x1403d23e5  cmp     [rax], ecx
0x1403d23e7  jbe     short loc_1403D2453
0x1403d23e9  mov     rbx, 0FFFFFFFFC000000Dh
0x1403d23f0  lea     ecx, [r15+1]
0x1403d23f4  mov     r8, rbx
0x1403d23f7  call    cs:__imp_WdLogSingleEntry2
0x1403d23fe  nop     dword ptr [rax+rax+00h]
0x1403d2403  lea     r9, aCallerSpecifie_9; "Caller specified PathCount exceeds the "...
0x1403d240a  mov     cs:WdLogGlobalForLineNumber, 369h
0x1403d2414  mov     rax, [rsp+360h+var_310]
0x1403d2419  or      r8d, 0FFFFFFFFh
0x1403d241d  mov     [rsp+360h+var_320], r13
0x1403d2422  mov     edx, 40000h
0x1403d2427  mov     [rsp+360h+var_328], r13
0x1403d242c  xor     ecx, ecx
0x1403d242e  mov     [rsp+360h+var_330], r13
0x1403d2433  mov     [rsp+360h+var_338], rbx
0x1403d2438  mov     [rsp+360h+var_340], rax
0x1403d243d  call    DxgkLogInternalTriageEvent
0x1403d2442  mov     [rdi], ebx
0x1403d2444  lea     rcx, [rsp+360h+var_2E8]; this
0x1403d2449  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1403d244e  jmp     loc_1403D33C0
0x1403d2453  xor     r9d, r9d; unsigned __int64 *
0x1403d2456  mov     [rbp+260h+var_2A8], r13d
0x1403d245a  lea     r8, [rbp+260h+var_2A8]; unsigned int *
0x1403d245e  mov     rcx, rdx; this
0x1403d2461  call    ?IsAdapterSessionized@DXGADAPTER@@QEBA_NPEAU_LUID@@PEAIPEA_K@Z; DXGADAPTER::IsAdapterSessionized(_LUID *,uint *,unsigned __int64 *)
0x1403d2466  test    al, al
0x1403d2468  jnz     short loc_1403D249F
0x1403d246a  mov     rdx, [rsp+360h+var_310]
0x1403d246f  lea     ecx, [r9+2]
0x1403d2473  mov     rbx, 0FFFFFFFFC000000Dh
0x1403d247a  mov     r8, rbx
0x1403d247d  call    cs:__imp_WdLogSingleEntry2
0x1403d2484  nop     dword ptr [rax+rax+00h]
0x1403d2489  lea     r9, aCallerSpecifie_14; "Caller specified adapter (0x%I64x) is n"...
0x1403d2490  mov     cs:WdLogGlobalForLineNumber, 378h
0x1403d249a  jmp     loc_1403D2414
0x1403d249f  mov     rax, [rsp+360h+var_310]
0x1403d24a4  mov     rsi, [rax+0D8h]
0x1403d24ab  mov     rcx, rsi; Object
0x1403d24ae  call    cs:__imp_ObfReferenceObject
0x1403d24b5  nop     dword ptr [rax+rax+00h]
0x1403d24ba  lea     rcx, [rsp+360h+var_2E8]; this
0x1403d24bf  call    ??1DXGADAPTERSTOPRESETLOCKSHARED@@QEAA@XZ; DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(void)
0x1403d24c4  mov     r12d, [rbp+260h+var_2A8]
0x1403d24c8  mov     r14d, 2
0x1403d24ce  mov     r9d, r14d
0x1403d24d1  mov     r8d, r12d
0x1403d24d4  xor     edx, edx
0x1403d24d6  xor     ecx, ecx
0x1403d24d8  call    DxgkWaitForPnPTransitionDone
0x1403d24dd  mov     [rdi], eax
0x1403d24df  mov     rcx, rsi; Object
0x1403d24e2  test    eax, eax
0x1403d24e4  jns     short loc_1403D2549
0x1403d24e6  call    cs:__imp_ObfDereferenceObject
0x1403d24ed  nop     dword ptr [rax+rax+00h]
0x1403d24f2  movsxd  r8, dword ptr [rdi]
0x1403d24f5  mov     edx, r12d
0x1403d24f8  mov     ecx, r14d
0x1403d24fb  call    cs:__imp_WdLogSingleEntry2
0x1403d2502  nop     dword ptr [rax+rax+00h]
0x1403d2507  mov     [rsp+360h+var_320], r13
0x1403d250c  lea     r9, aFailedToWaitFo_3; "Failed to wait for all pending PnP tran"...
0x1403d2513  mov     [rsp+360h+var_328], r13
0x1403d2518  mov     [rsp+360h+var_330], r13
0x1403d251d  mov     cs:WdLogGlobalForLineNumber, 39Bh
0x1403d2527  movsxd  rax, dword ptr [rdi]
0x1403d252a  mov     [rsp+360h+var_338], rax
0x1403d252f  mov     [rsp+360h+var_340], r12
0x1403d2534  or      r8d, 0FFFFFFFFh
0x1403d2538  mov     edx, 40000h
0x1403d253d  xor     ecx, ecx
0x1403d253f  call    DxgkLogInternalTriageEvent
0x1403d2544  jmp     loc_1403D2444
0x1403d2549  call    DpiFdoWaitConnectionChangeComplete
0x1403d254e  mov     rcx, rsi; Object
0x1403d2551  mov     [rdi], eax
0x1403d2553  call    cs:__imp_ObfDereferenceObject
0x1403d255a  nop     dword ptr [rax+rax+00h]
0x1403d255f  movsxd  rax, dword ptr [rdi]
0x1403d2562  test    eax, eax
0x1403d2564  jns     short loc_1403D25D1
0x1403d2566  mov     rdx, [rsp+360h+var_310]
0x1403d256b  mov     r15, 0FFFFFFFFC01E0013h
0x1403d2572  mov     r9, r15
0x1403d2575  mov     r8, rax
0x1403d2578  mov     ecx, r14d
0x1403d257b  call    cs:__imp_WdLogSingleEntry3
0x1403d2582  nop     dword ptr [rax+rax+00h]
0x1403d2587  mov     [rsp+360h+var_320], r13
0x1403d258c  lea     r9, aFailedToWaitFo; "Failed to wait for all pending connecti"...
0x1403d2593  mov     [rsp+360h+var_328], r13
0x1403d2598  or      r8d, 0FFFFFFFFh
0x1403d259c  mov     cs:WdLogGlobalForLineNumber, 3B1h
0x1403d25a6  mov     edx, 40000h
0x1403d25ab  movsxd  rax, dword ptr [rdi]
0x1403d25ae  xor     ecx, ecx
0x1403d25b0  mov     [rsp+360h+var_330], r15
0x1403d25b5  mov     [rsp+360h+var_338], rax
0x1403d25ba  mov     rax, [rsp+360h+var_310]
0x1403d25bf  mov     [rsp+360h+var_340], rax
0x1403d25c4  call    DxgkLogInternalTriageEvent
0x1403d25c9  mov     [rdi], r15d
0x1403d25cc  jmp     loc_1403D2444
0x1403d25d1  lea     rcx, [rsp+360h+var_2E8]; this
0x1403d25d6  call    ?Acquire@DXGADAPTERSTOPRESETLOCKSHARED@@QEAAXXZ; DXGADAPTERSTOPRESETLOCKSHARED::Acquire(void)
0x1403d25db  mov     rax, [rsp+360h+var_310]
0x1403d25e0  mov     ecx, [rax+0C8h]
0x1403d25e6  mov     rdx, [rsp+360h+var_310]
0x1403d25eb  cmp     ecx, r15d
0x1403d25ee  jnz     loc_1403D32DD
0x1403d25f4  cmp     [rdx+0C49h], r13b
0x1403d25fb  jnz     loc_1403D32DD
0x1403d2601  lea     rax, [rsp+360h+var_310]
0x1403d2606  mov     [rbp+260h+var_2D0], r13d
0x1403d260a  mov     [rbp+260h+var_1B8], rax
0x1403d2611  mov     esi, r13d
0x1403d2614  lea     rax, [rbp+260h+var_2D0]
0x1403d2618  mov     [rsp+360h+var_300], r13b
0x1403d261d  mov     [rbp+260h+var_1B0], rax
0x1403d2624  lea     rax, [rsp+360h+var_300]
0x1403d2629  mov     [rbp+260h+var_1A8], rax
0x1403d2630  mov     rdx, [rbp+260h+var_2C0]
0x1403d2634  mov     ecx, [rdx]
0x1403d2636  cmp     esi, ecx
0x1403d2638  jnb     short loc_1403D2667
0x1403d263a  mov     eax, esi
0x1403d263c  lea     rcx, [rbp+260h+var_1B8]
0x1403d2643  imul    r8, rax, 84h
  ... truncated ...
```
