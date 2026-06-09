# ADAPTER_DISPLAY::Initialize(void)

- ea: `0x1401f43d8`
- end: `0x1401f51c0`
- name: `?Initialize@ADAPTER_DISPLAY@@QEAAJXZ`
- size: `3560`
- prototype: `__int64 __fastcall(ADAPTER_DISPLAY *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401d0e20`

## callees

- `0x140009030`
- `0x140012380`
- `0x1400144ec`
- `0x1400150d0`
- `0x1400161c8`
- `0x14001b890`
- `0x140034f60`
- `0x14005f2f4`
- `0x14007f310`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140192114`
- `0x1401f43d8`
- `0x140249104`
- `0x1402c3670`
- `0x1402eca5c`
- `0x140301af8`
- `0x14035f558`
- `0x140380e28`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401f4970`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401f4c75`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401f4970`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401f4c75`
- `ntoskrnl!ObfReferenceObject` at `0x1401f517c`
- `ntoskrnl!ObfReferenceObject` at `0x1401f517c`
- `ntoskrnl!ZwClose` at `0x1401f518d`
- `ntoskrnl!ZwClose` at `0x1401f518d`
- `ntoskrnl!KeClearEvent` at `0x1401f5169`
- `ntoskrnl!KeClearEvent` at `0x1401f5169`
- `ntoskrnl!IoCreateNotificationEvent` at `0x1401f5100`
- `ntoskrnl!IoCreateNotificationEvent` at `0x1401f5100`
- `watchdog!WdLogSingleEntry2` at `0x1401f4d6e`
- `watchdog!WdLogSingleEntry2` at `0x1401f5025`
- `watchdog!WdLogSingleEntry2` at `0x1401f4d6e`
- `watchdog!WdLogSingleEntry2` at `0x1401f5025`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401f4485`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401f4485`
- `watchdog!WdLogSingleEntry3` at `0x1401f460f`
- `watchdog!WdLogSingleEntry3` at `0x1401f4a57`
- `watchdog!WdLogSingleEntry3` at `0x1401f4ae2`
- `watchdog!WdLogSingleEntry3` at `0x1401f4b6d`
- `watchdog!WdLogSingleEntry3` at `0x1401f4d1d`
- `watchdog!WdLogSingleEntry3` at `0x1401f4e18`
- `watchdog!WdLogSingleEntry3` at `0x1401f460f`
- `watchdog!WdLogSingleEntry3` at `0x1401f4a57`
- `watchdog!WdLogSingleEntry3` at `0x1401f4ae2`
- `watchdog!WdLogSingleEntry3` at `0x1401f4b6d`
- `watchdog!WdLogSingleEntry3` at `0x1401f4d1d`
- `watchdog!WdLogSingleEntry3` at `0x1401f4e18`
- `watchdog!WdLogSingleEntry0` at `0x1401f49b5`
- `watchdog!WdLogSingleEntry0` at `0x1401f4cb0`
- `watchdog!WdLogSingleEntry0` at `0x1401f50a5`
- `watchdog!WdLogSingleEntry0` at `0x1401f511b`
- `watchdog!WdLogSingleEntry0` at `0x1401f49b5`
- `watchdog!WdLogSingleEntry0` at `0x1401f4cb0`
- `watchdog!WdLogSingleEntry0` at `0x1401f50a5`
- `watchdog!WdLogSingleEntry0` at `0x1401f511b`
- `watchdog!WdLogSingleEntry1` at `0x1401f44df`
- `watchdog!WdLogSingleEntry1` at `0x1401f4993`
- `watchdog!WdLogSingleEntry1` at `0x1401f44df`
- `watchdog!WdLogSingleEntry1` at `0x1401f4993`

## string_xrefs

- `0x1401f48a2`: `ShortLinkTrainingTimeout`
- `0x1401f48ad`: `LongLinkTrainingTimeout`
- `0x1401f4a68`: `Invalid link training timeout registry value (0x%I64x, 0x%I64x) on adapter 0x%I64x, fallback to the default value.`
- `0x1401f4b7e`: `Miniport driver wants t fallback to use DdiCommitVidPn but it does not supply pfnCommitVidPn on adapter (0x%I64x%08I64x), returning 0x%I64x.`
- `0x1401f4cc1`: `GetAdapter()->GetAdapterVendorId() != VENDOR_ID_QUALCOMM`
- `0x1401f4e29`: `Force to stop adapter (0x%I64x%08I64x) due to target ID does not support reduced hash size and registry requested to use virtual topologies, returning 0x%I64x.`
- `0x1401f512c`: `Failed to create adapter VidPnSourceUsedBySession event object.`

## pseudocode

```c
__int64 __fastcall ADAPTER_DISPLAY::Initialize(ADAPTER_DISPLAY *this)
{
  __int64 v1; // r8
  int *v2; // rdi
  int v4; // eax
  __int64 v5; // rdx
  int v6; // ecx
  __int64 result; // rax
  unsigned int v8; // eax
  __int64 v9; // rsi
  __int64 v10; // rax
  unsigned __int64 v11; // kr00_8
  bool v12; // cf
  __int64 v13; // rax
  _QWORD *v14; // rax
  enum _EVENT_TYPE v15; // edx
  unsigned __int8 v16; // r8
  _QWORD *v17; // rbx
  unsigned int i; // ebx
  __int64 v19; // r15
  __int64 v20; // rsi
  enum _EVENT_TYPE v21; // edx
  unsigned __int8 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  struct DXGGLOBAL *Global; // rbx
  char *v26; // rsi
  char *v27; // rbx
  char **v28; // rax
  unsigned int *v29; // r12
  unsigned int *v30; // rsi
  int RegistryValues; // r13d
  int v32; // eax
  unsigned int v33; // eax
  _DWORD *v34; // rbx
  unsigned int v35; // ecx
  __int64 v36; // rax
  __int64 v37; // rcx
  int v38; // edx
  bool v39; // cl
  bool v40; // zf
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // rcx
  _DWORD *v47; // rcx
  struct DXGFASTMUTEX *v48; // rbx
  __int64 v49; // rax
  char *v50; // rbx
  struct DXGDODPRESENT *DodPresent; // rax
  __int64 v52; // rcx
  int (__fastcall *v53)(_QWORD, struct _DXGKARG_QUERYADAPTERINFO *); // rax
  __int64 j; // rcx
  __int64 v55; // rcx
  unsigned int k; // r10d
  __int64 v57; // rcx
  __int64 v58; // rcx
  bool v59; // sf
  bool v60; // of
  __int64 v61; // rcx
  int v62; // edi
  int v63; // ebx
  struct DXGGLOBAL *v64; // rax
  int v65; // ebx
  __int64 v66; // rdi
  DXGADAPTERSOURCEHASH *v67; // rsi
  struct DXGADAPTERSOURCEHASH::ADAPTERSOURCEHASH_ENTRY *v68; // rbx
  struct _KEVENT *v69; // rax
  void *EventHandle; // [rsp+50h] [rbp-B0h] BYREF
  int v71; // [rsp+58h] [rbp-A8h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v72; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v73[50]; // [rsp+90h] [rbp-70h] BYREF

  v1 = *((_QWORD *)this + 2);
  v2 = (int *)((char *)this + 24);
  *((_DWORD *)this + 6) = 0;
  if ( *(_DWORD *)(v1 + 2392) >= 0x5010u && !*(_BYTE *)(v1 + 209) && (*(_DWORD *)(v1 + 3088) & 8) == 0 )
  {
    *(_QWORD *)&v72.Type = 16;
    *(_QWORD *)&v72.InputDataSize = 0;
    *(_QWORD *)&v72.Flags.0 = 0;
    HIDWORD(v72.hKmdProcessHandle) = 0;
    v72.pInputData = 0;
    v72.pOutputData = (char *)this + 24;
    v72.OutputDataSize = 4;
    v4 = DXGADAPTER::DdiQueryAdapterInfo((DXGADAPTER *)v1, &v72);
    if ( v4 < 0 )
    {
      *(_QWORD *)(WdLogNewEntry5_WdTrace() + 24) = v4;
      WdLogGlobalForLineNumber = 4740;
      *v2 = 0;
      if ( *(int *)(*((_QWORD *)this + 2) + 2848LL) >= 8704 )
        *v2 = 2;
    }
    v5 = *((_QWORD *)this + 2);
    v6 = *v2;
    if ( *(int *)(v5 + 2848) >= 9472 )
    {
      if ( (v6 & 0xC) == 0xC )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 4769;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Adapter 0x%I64x: Both HdrFP16ScanoutSupport and HdrARGB10ScanoutSupport can't be set to 1 at the same time",
          (__int64)this,
          0,
          0,
          0,
          0);
        return 3221225485LL;
      }
      v1 = *((_QWORD *)this + 2);
    }
    else
    {
      v6 &= 0xFFFFFFF3;
      v1 = *((_QWORD *)this + 2);
      *v2 = v6;
    }
    if ( *(int *)(v5 + 2848) < 9984 )
    {
      v6 &= ~0x10u;
      *v2 = v6;
    }
    if ( *(int *)(v5 + 2848) < 10496 || *(_QWORD *)(v5 + 832) || !*(_DWORD *)(v5 + 1968) || (v6 & 2) == 0 )
    {
      v6 &= ~0x20u;
      *v2 = v6;
    }
    if ( *(int *)(v5 + 2848) < 12288 )
    {
      v6 &= ~0x40u;
      *v2 = v6;
    }
    if ( g_bDbgForceUsb4MonitorSupport )
      *v2 = v6 | 0x40;
  }
  v8 = *(_DWORD *)(v1 + 1968);
  *((_DWORD *)this + 24) = v8;
  v9 = v8;
  v11 = v8;
  v10 = 4024LL * v8;
  if ( !is_mul_ok(v11, 0xFB8u) )
    v10 = -1;
  v12 = __CFADD__(v10, 8);
  v13 = v10 + 8;
  if ( v12 )
    v13 = -1;
  v14 = (_QWORD *)operator new[](v13, 1265072196, 64);
  if ( v14 )
  {
    v17 = v14 + 1;
    *v14 = v9;
    `vector constructor iterator'(v14 + 1, 0xFB8u, (unsigned int)v9, (void *(*)(void *))DISPLAY_SOURCE::DISPLAY_SOURCE);
  }
  else
  {
    v17 = 0;
  }
  *((_QWORD *)this + 16) = v17;
  if ( !v17 )
  {
    WdLogSingleEntry3(6, *((unsigned int *)this + 24), *((_QWORD *)this + 2), -1073741801);
    WdLogGlobalForLineNumber = 4825;
    DxgkLogInternalTriageEvent(
      0,
      262145,
      -1,
      (unsigned int)L"Failed to allocate 0x%I64x of display sources for adapter 0x%I64x, returning 0x%I64x",
      *((unsigned int *)this + 24),
      *((_QWORD *)this + 2),
      -1073741801,
      0,
      0);
    return 3221225495LL;
  }
  for ( i = 0; i < *((_DWORD *)this + 24); ++i )
  {
    v19 = *((_QWORD *)this + 16);
    v20 = 4024LL * i;
    *(_QWORD *)(v20 + v19 + 8) = this;
    *(_DWORD *)(v20 + v19 + 16) = i;
    *(_DWORD *)(v20 + v19 + 792) = i;
    *(_DWORD *)(v20 + v19 + 840) = i;
    *(_DWORD *)(v20 + v19 + 880) = i;
    result = DxgCreateEvent((struct _KEVENT **)(v20 + v19 + 904), v15, v16);
    if ( (int)result < 0 )
      return result;
    result = DxgCreateEvent((struct _KEVENT **)(v20 + v19 + 912), v21, v22);
    if ( (int)result < 0 )
      return result;
  }
  result = MonitorCreateMonitorManager(this, (char *)this + 112);
  if ( (int)result >= 0 )
  {
    result = VIDPN_MGR_CLASSFACTORY::CreateVidPnMgr(this, (struct VIDPN_MGR **)this + 13);
    if ( (int)result > -1071774937 && (unsigned int)(result + 1071774934) > 0x3FE1FCD5 )
    {
      if ( (*(_DWORD *)(*((_QWORD *)this + 2) + 444LL) & 0x100) != 0 )
      {
        v23 = *((_QWORD *)DXGGLOBAL::GetGlobal() + 128);
        v24 = *((_QWORD *)this + 2);
        *(_QWORD *)&v72.Type = v23;
        EventHandle = *(void **)(v24 + 412);
        result = CreateOutputDuplManager(
                   *((_DWORD *)this + 24),
                   0,
                   (struct _LUID *)&v72,
                   (struct _LUID *)&EventHandle,
                   (struct OUTPUTDUPL_MGR **)this + 15);
        if ( (int)result < 0 )
          return result;
        Global = DXGGLOBAL::GetGlobal();
        v26 = (char *)((*((_QWORD *)this + 15) - 24LL) & -(__int64)(*((_QWORD *)this + 15) != 0));
        DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)&v72, (struct DXGGLOBAL *)((char *)Global + 1536), 0);
        DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v72);
        v27 = (char *)Global + 1584;
        v28 = (char **)*((_QWORD *)v27 + 1);
        if ( *v28 != v27 )
          __fastfail(3u);
        *(_QWORD *)v26 = v27;
        *((_QWORD *)v26 + 1) = v28;
        *v28 = v26;
        *((_QWORD *)v27 + 1) = v26;
        DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v72);
      }
      else
      {
        result = CreateOutputDuplManager(*((_DWORD *)this + 24), this, 0, 0, (struct OUTPUTDUPL_MGR **)this + 15);
        if ( (int)result < 0 )
          return result;
      }
      v71 = 1;
      *((_QWORD *)this + 77) = (char *)this + 608;
      *((_QWORD *)this + 76) = (char *)this + 608;
      v29 = (unsigned int *)((char *)this + 532);
      v30 = (unsigned int *)((char *)this + 536);
      *((_DWORD *)this + 132) = 0;
      *((_DWORD *)this + 133) = 200;
      *((_DWORD *)this + 134) = 1000;
      *((_DWORD *)this + 135) = 20000000;
      *((_DWORD *)this + 136) = 0;
      memset(v73, 0, 0x188u);
      v73[10] = (char *)this + 528;
      v73[5] = 0;
      LODWORD(v73[4]) = 0x4000000;
      LODWORD(v73[1]) = 288;
      v73[2] = L"ModeListCaching";
      LODWORD(v73[6]) = 0;
      v73[3] = &v71;
      v73[9] = L"SetTimingsFlags";
      v73[16] = L"ShortLinkTrainingTimeout";
      v73[23] = L"LongLinkTrainingTimeout";
      v73[30] = L"HPDFilterLimit";
      v73[7] = 0;
      LODWORD(v73[8]) = 288;
      LODWORD(v73[11]) = 0x4000000;
      v73[12] = 0;
      LODWORD(v73[13]) = 0;
      v73[14] = 0;
      LODWORD(v73[15]) = 288;
      LODWORD(v73[18]) = 0x4000000;
      v73[19] = 0;
      LODWORD(v73[20]) = 0;
      v73[21] = 0;
      LODWORD(v73[22]) = 288;
      LODWORD(v73[25]) = 0x4000000;
      v73[26] = 0;
      LODWORD(v73[27]) = 0;
      v73[28] = 0;
      LODWORD(v73[29]) = 288;
      LODWORD(v73[32]) = 0x4000000;
      v73[33] = 0;
      LODWORD(v73[34]) = 0;
      v73[35] = 0;
      LODWORD(v73[36]) = 288;
      LODWORD(v73[39]) = 0x4000000;
      v73[40] = 0;
      LODWORD(v73[41]) = 0;
      v73[37] = L"EnableVirtualRefreshRateOnExternalMonitor";
      v73[17] = (char *)this + 532;
      v73[24] = (char *)this + 536;
      v73[31] = (char *)this + 540;
      v73[38] = (char *)this + 544;
      RegistryValues = RtlQueryRegistryValuesEx(2, L"GraphicsDrivers\\DMM", v73, 0, 0);
      if ( RegistryValues >= 0 )
      {
        v32 = v71;
      }
      else
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 4974;
        if ( RegistryValues != -1073741772 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 4977;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"Status == STATUS_OBJECT_NAME_NOT_FOUND",
            4977,
            0,
            0,
            0,
            0);
        }
        v32 = 1;
        *((_DWORD *)this + 132) = 0;
        v71 = 1;
        RegistryValues = 0;
        *v29 = 200;
        *v30 = 1000;
      }
      *((_BYTE *)this + 292) = v32 == 1;
      v33 = *v30;
      if ( !*v30 || *v29 >= v33 || v33 >= 0x7530 )
      {
        WdLogSingleEntry3(2, *v29, *v29, *((_QWORD *)this + 2));
        WdLogGlobalForLineNumber = 5002;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Invalid link training timeout registry value (0x%I64x, 0x%I64x) on adapter 0x%I64x, fallback to "
                         "the default value.",
          *v29,
          *v29,
          *((_QWORD *)this + 2),
          0,
          0);
        *v29 = 200;
        *((_DWORD *)this + 134) = 1000;
      }
      v34 = (_DWORD *)((char *)this + 540);
      v35 = *((_DWORD *)this + 135);
      if ( v35 - 1000000 > 0x5E69EC0 )
      {
        if ( v35 )
        {
          WdLogSingleEntry3(2, v35, 20000000, *((_QWORD *)this + 2));
          WdLogGlobalForLineNumber = 5017;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Invalid hot-plug filter limit of %#x on adapter 0x%I64x.  Using default of %#x.",
            (unsigned int)*v34,
            20000000,
            *((_QWORD *)this + 2),
            0,
            0);
        }
        *v34 = 20000000;
      }
      if ( (*((_DWORD *)this + 132) & 1) != 0 )
      {
        v36 = *((_QWORD *)this + 2);
        if ( !*(_QWORD *)(v36 + 656) )
        {
          WdLogSingleEntry3(2, *(int *)(v36 + 416), *(unsigned int *)(v36 + 412), -1073741735);
          WdLogGlobalForLineNumber = 5034;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Miniport driver wants t fallback to use DdiCommitVidPn but it does not supply pfnCommitVidPn o"
                           "n adapter (0x%I64x%08I64x), returning 0x%I64x.",
            *(int *)(*((_QWORD *)this + 2) + 416LL),
            *(unsigned int *)(*((_QWORD *)this + 2) + 412LL),
            -1073741735,
            0,
            0);
          return 3221225561LL;
        }
      }
      v37 = *((_QWORD *)this + 2);
      v38 = *(_DWORD *)(v37 + 420);
      if ( (*(_DWORD *)(v37 + 444) & 0x400) != 0 )
      {
        if ( v38 == 1297040209
          && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v37 + 216) + 64LL) + 40LL) + 28LL) < 0x700Au )
        {
          *((_BYTE *)this + 289) = 1;
          v39 = 1;
        }
        else
        {
          LODWORD(EventHandle) = ((unsigned int)*v2 >> 1) & 1;
          memset(v73, 0, 0x188u);
          LODWORD(v73[1]) = 288;
          v73[2] = L"ForceEnableDWMClone";
          LODWORD(v73[4]) = 67108868;
          LODWORD(v73[6]) = 4;
          v73[3] = &EventHandle;
          v73[5] = &EventHandle;
          RtlQueryRegistryValuesEx(2, L"GraphicsDrivers", v73, 0, 0);
          v40 = (_DWORD)EventHandle == 0;
          *((_BYTE *)this + 289) = (_DWORD)EventHandle != 0;
          v39 = !v40;
        }
        v41 = 290;
        v42 = (__int64)this;
      }
      else
      {
        if ( v38 == 1297040209 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 5091;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"GetAdapter()->GetAdapterVendorId() != VENDOR_ID_QUALCOMM",
            5091,
            0,
            0,
            0,
            0);
        }
        v43 = *((_QWORD *)this + 2);
        v44 = *(int *)(v43 + 416);
        if ( (*v2 & 2) != 0 )
        {
          WdLogSingleEntry3(2, v44, *(unsigned int *)(v43 + 412), -1073741735);
          WdLogGlobalForLineNumber = 5103;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Force to stop DWM clone supported adapter (0x%I64x%08I64x) due to target ID does not support D"
                           "WM clone, returning 0x%I64x.",
            *(int *)(*((_QWORD *)this + 2) + 416LL),
            *(unsigned int *)(*((_QWORD *)this + 2) + 412LL),
            -1073741735,
            0,
            0);
          return 3221225561LL;
        }
        WdLogSingleEntry2(4, v44);
        WdLogGlobalForLineNumber = 5111;
        v39 = 0;
        *((_BYTE *)this + 289) = 0;
        v41 = (__int64)this;
        v42 = 290;
      }
      *(_BYTE *)(v42 + v41) = v39;
      v45 = *((_QWORD *)this + 2);
      if ( *(int *)(v45 + 3116) < 2000 )
      {
        v46 = *(_QWORD *)(v45 + 216);
        LODWORD(EventHandle) = 0;
        if ( (int)DpiReadPnpRegistryValue(v46, L"EnableVirtualTopologySupport", &EventHandle, 4, 2) >= 0 )
        {
          if ( (_DWORD)EventHandle )
          {
            v47 = (_DWORD *)*((_QWORD *)this + 2);
            if ( (v47[111] & 0x800) == 0 )
            {
              WdLogSingleEntry3(2, (int)v47[104], (unsigned int)v47[103], -1073741735);
              WdLogGlobalForLineNumber = 5137;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"Force to stop adapter (0x%I64x%08I64x) due to target ID does not support reduced hash size"
                               " and registry requested to use virtual topologies, returning 0x%I64x.",
                *(int *)(*((_QWORD *)this + 2) + 416LL),
                *(unsigned int *)(*((_QWORD *)this + 2) + 412LL),
                -1073741735,
                0,
                0);
              return 3221225561LL;
            }
            *((_BYTE *)this + 290) = 1;
            v48 = (struct DXGGLOBAL *)((char *)DXGGLOBAL::GetGlobal() + 1400);
            DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)&v72, v48, 0);
            DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v72);
            if ( *((_DWORD *)v48 + 17) != 4 )
              *((_DWORD *)v48 + 17) = 4;
            DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v72);
          }
        }
      }
      v49 = *((_QWORD *)this + 2);
      if ( *(_QWORD *)(v49 + 3240) )
      {
        v50 = (char *)this + 464;
      }
      else
      {
        DodPresent = DxgkpCreateDodPresent(this, *(_QWORD *)(v49 + 696) != 0);
        v52 = *((_QWORD *)this + 2);
        v50 = (char *)this + 464;
        *((_QWORD *)this + 58) = DodPresent;
        if ( !DodPresent )
          RegistryValues = -1073741801;
        memset(&v72, 0, 24);
        v53 = *(int (__fastcall **)(_QWORD, struct _DXGKARG_QUERYADAPTERINFO *))(v52 + 2480);
        if ( v53 && v53(*(_QWORD *)(v52 + 2408), &v72) >= 0 )
        {
          for ( j = 0; j != 4; ++j )
            *((_DWORD *)this + j + 110) = *((unsigned __int8 *)&v72.Type + j);
          *((_DWORD *)this + 115) = *((unsigned __int8 *)&v72.InputDataSize + 4);
          *((_DWORD *)this + 114) = *((unsigned __int8 *)&v72.InputDataSize + 5);
        }
        else
        {
          *((_DWORD *)this + 110) = 1;
        }
        v55 = *(_QWORD *)(*((_QWORD *)this + 2) + 216LL);
        if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v55 + 64) + 40LL) + 28LL) >= 0x3007u )
          DpiSetSchedulerCallbackState(v55, 3);
      }
      if ( *(_QWORD *)v50 )
      {
        for ( k = 0;
              k < *((_DWORD *)this + 24);
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v50 + 8LL) + 3040 * v57 + 400) = *(_QWORD *)(4024 * v57
                                                                                            + *((_QWORD *)this + 16)
                                                                                            + 912) )
        {
          v57 = k++;
        }
      }
      v58 = *((_QWORD *)this + 2);
      v60 = __OFSUB__(*(_DWORD *)(v58 + 2848), 8704);
      v59 = *(_DWORD *)(v58 + 2848) - 8704 < 0;
      v61 = *(_QWORD *)(v58 + 216);
      v62 = v59 ^ v60;
      LODWORD(EventHandle) = v62;
      if ( (int)DpiReadPnpRegistryValue(v61, L"NeedToSuspendVidSchBeforeSetGammaRamp", &EventHandle, 4, 2) >= 0 )
      {
        v63 = (int)EventHandle;
        if ( (_DWORD)EventHandle != v62 )
        {
          WdLogSingleEntry2(3, (unsigned int)EventHandle);
          WdLogGlobalForLineNumber = 5236;
        }
      }
      else
      {
        v63 = v62;
      }
      *((_BYTE *)this + 291) = v63 != 0;
      v64 = DXGGLOBAL::GetGlobal();
      v65 = *((unsigned __int8 *)this + 290);
      v66 = *((_QWORD *)this + 2);
      v67 = (struct DXGGLOBAL *)((char *)v64 + 1400);
      DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)&v72, (struct DXGGLOBAL *)((char *)v64 + 1400), 0);
      DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v72);
      v68 = DXGADAPTERSOURCEHASH::AddEntry(v67, (const struct _LUID *)(v66 + 412), 0, v65);
      DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v72);
      if ( !v68 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 5249;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(TmpStatus)", 5249, 0, 0, 0, 0);
      }
      if ( RegistryValues >= 0 )
      {
        EventHandle = 0;
        v69 = IoCreateNotificationEvent(0, &EventHandle);
        *((_QWORD *)this + 84) = v69;
        if ( v69 )
        {
          KeClearEvent(v69);
          ObfReferenceObject(*((PVOID *)this + 84));
          ZwClose(EventHandle);
        }
        else
        {
          WdLogSingleEntry0(6);
          WdLogGlobalForLineNumber = 5260;
          DxgkLogInternalTriageEvent(
            0,
            262145,
            -1,
            (unsigned int)L"Failed to create adapter VidPnSourceUsedBySession event object.",
            5260,
            0,
            0,
            0,
            0);
          return (unsigned int)-1073741801;
        }
      }
      return (unsigned int)RegistryValues;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1401f43d8  push    rbp
0x1401f43da  push    rbx
0x1401f43db  push    rsi
0x1401f43dc  push    rdi
0x1401f43dd  push    r12
0x1401f43df  push    r13
0x1401f43e1  push    r14
0x1401f43e3  push    r15
0x1401f43e5  lea     rbp, [rsp-138h]
0x1401f43ed  sub     rsp, 238h
0x1401f43f4  mov     rax, cs:__security_cookie
0x1401f43fb  xor     rax, rsp
0x1401f43fe  mov     [rbp+170h+var_50], rax
0x1401f4405  mov     r8, [rcx+10h]
0x1401f4409  lea     rdi, [rcx+18h]
0x1401f440d  xor     r13d, r13d
0x1401f4410  mov     r14, rcx
0x1401f4413  mov     [rdi], r13d
0x1401f4416  cmp     dword ptr [r8+958h], 5010h
0x1401f4421  lea     esi, [r13+2]
0x1401f4425  jb      loc_1401F458B
0x1401f442b  cmp     [r8+0D1h], r13b
0x1401f4432  jnz     loc_1401F458B
0x1401f4438  mov     eax, [r8+0C10h]
0x1401f443f  shr     eax, 3
0x1401f4442  test    al, 1
0x1401f4444  jnz     loc_1401F458B
0x1401f444a  lea     rdx, [rsp+270h+var_210]; struct _DXGKARG_QUERYADAPTERINFO *
0x1401f444f  mov     qword ptr [rsp+270h+var_210.Type], 10h
0x1401f4458  mov     rcx, r8; this
0x1401f445b  mov     qword ptr [rsp+270h+var_210.InputDataSize], r13
0x1401f4460  mov     qword ptr [rbp+170h+var_210.Flags], r13
0x1401f4464  mov     dword ptr [rbp+170h+var_210.hKmdProcessHandle+4], r13d
0x1401f4468  mov     [rsp+270h+var_210.pInputData], r13
0x1401f446d  mov     [rsp+270h+var_210.pOutputData], rdi
0x1401f4472  mov     [rbp+170h+var_210.OutputDataSize], 4
0x1401f4479  call    ?DdiQueryAdapterInfo@DXGADAPTER@@QEAAJPEAU_DXGKARG_QUERYADAPTERINFO@@@Z; DXGADAPTER::DdiQueryAdapterInfo(_DXGKARG_QUERYADAPTERINFO *)
0x1401f447e  test    eax, eax
0x1401f4480  jns     short loc_1401F44B5
0x1401f4482  movsxd  rbx, eax
0x1401f4485  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1401f448c  nop     dword ptr [rax+rax+00h]
0x1401f4491  mov     [rax+18h], rbx
0x1401f4495  xor     eax, eax
0x1401f4497  mov     cs:WdLogGlobalForLineNumber, 1284h
0x1401f44a1  mov     [rdi], eax
0x1401f44a3  mov     rax, [r14+10h]
0x1401f44a7  cmp     dword ptr [rax+0B20h], 2200h
0x1401f44b1  jl      short loc_1401F44B5
0x1401f44b3  mov     [rdi], esi
0x1401f44b5  mov     rdx, [r14+10h]
0x1401f44b9  mov     ecx, [rdi]
0x1401f44bb  cmp     dword ptr [rdx+0B20h], 2500h
0x1401f44c5  jge     short loc_1401F44D1
0x1401f44c7  and     ecx, 0FFFFFFF3h
0x1401f44ca  mov     r8, rdx
0x1401f44cd  mov     [rdi], ecx
0x1401f44cf  jmp     short loc_1401F4533
0x1401f44d1  mov     eax, ecx
0x1401f44d3  and     eax, 0Ch
0x1401f44d6  cmp     al, 0Ch
0x1401f44d8  jnz     short loc_1401F452F
0x1401f44da  mov     rdx, r14
0x1401f44dd  mov     ecx, esi
0x1401f44df  call    cs:__imp_WdLogSingleEntry1
0x1401f44e6  nop     dword ptr [rax+rax+00h]
0x1401f44eb  mov     [rsp+270h+var_230], r13
0x1401f44f0  lea     r9, aAdapter0xI64xB; "Adapter 0x%I64x: Both HdrFP16ScanoutSup"...
0x1401f44f7  mov     [rsp+270h+var_238], r13
0x1401f44fc  or      r8d, 0FFFFFFFFh
0x1401f4500  mov     [rsp+270h+var_240], r13
0x1401f4505  mov     edx, 40000h
0x1401f450a  mov     [rsp+270h+var_248], r13
0x1401f450f  xor     ecx, ecx
0x1401f4511  mov     [rsp+270h+var_250], r14
0x1401f4516  mov     cs:WdLogGlobalForLineNumber, 12A1h
0x1401f4520  call    DxgkLogInternalTriageEvent
0x1401f4525  mov     eax, 0C000000Dh
0x1401f452a  jmp     loc_1401F519C
0x1401f452f  mov     r8, [r14+10h]
0x1401f4533  cmp     dword ptr [rdx+0B20h], 2700h
0x1401f453d  jge     short loc_1401F4544
0x1401f453f  and     ecx, 0FFFFFFEFh
0x1401f4542  mov     [rdi], ecx
0x1401f4544  cmp     dword ptr [rdx+0B20h], 2900h
0x1401f454e  jl      short loc_1401F4567
0x1401f4550  cmp     [rdx+340h], r13
0x1401f4557  jnz     short loc_1401F4567
0x1401f4559  cmp     [rdx+7B0h], r13d
0x1401f4560  jz      short loc_1401F4567
0x1401f4562  test    sil, cl
0x1401f4565  jnz     short loc_1401F456C
0x1401f4567  and     ecx, 0FFFFFFDFh
0x1401f456a  mov     [rdi], ecx
0x1401f456c  cmp     dword ptr [rdx+0B20h], 3000h
0x1401f4576  jge     short loc_1401F457D
0x1401f4578  and     ecx, 0FFFFFFBFh
0x1401f457b  mov     [rdi], ecx
0x1401f457d  cmp     cs:?g_bDbgForceUsb4MonitorSupport@@3IA, r13d; uint g_bDbgForceUsb4MonitorSupport
0x1401f4584  jz      short loc_1401F458B
0x1401f4586  or      ecx, 40h
0x1401f4589  mov     [rdi], ecx
0x1401f458b  mov     eax, [r8+7B0h]
0x1401f4592  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1401f4599  mov     [r14+60h], eax
0x1401f459d  mov     esi, eax
0x1401f459f  mov     r15d, 0FB8h
0x1401f45a5  mov     eax, r15d
0x1401f45a8  mul     rsi
0x1401f45ab  lea     r8d, [rcx+41h]
0x1401f45af  mov     edx, 4B677844h
0x1401f45b4  cmovb   rax, rcx
0x1401f45b8  add     rax, 8
0x1401f45bc  cmovb   rax, rcx
0x1401f45c0  mov     rcx, rax
0x1401f45c3  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401f45c8  test    rax, rax
0x1401f45cb  jz      short loc_1401F45EB
0x1401f45cd  lea     rbx, [rax+8]
0x1401f45d1  mov     [rax], rsi
0x1401f45d4  mov     rcx, rbx; void *
0x1401f45d7  lea     r9, ??0DISPLAY_SOURCE@@QEAA@XZ; void *(*)(void *)
0x1401f45de  mov     r8d, esi; unsigned __int64
0x1401f45e1  mov     edx, r15d; unsigned __int64
0x1401f45e4  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1401f45e9  jmp     short loc_1401F45EE
0x1401f45eb  mov     rbx, r13
0x1401f45ee  mov     [r14+80h], rbx
0x1401f45f5  test    rbx, rbx
0x1401f45f8  jnz     short loc_1401F4665
0x1401f45fa  mov     edx, [r14+60h]
0x1401f45fe  lea     ecx, [rbx+6]
0x1401f4601  mov     r8, [r14+10h]
0x1401f4605  mov     r12, 0FFFFFFFFC0000017h
0x1401f460c  mov     r9, r12
0x1401f460f  call    cs:__imp_WdLogSingleEntry3
0x1401f4616  nop     dword ptr [rax+rax+00h]
0x1401f461b  mov     [rsp+270h+var_230], r13
0x1401f4620  lea     r9, aFailedToAlloca_95; "Failed to allocate 0x%I64x of display s"...
0x1401f4627  mov     cs:WdLogGlobalForLineNumber, 12D9h
0x1401f4631  or      r8d, 0FFFFFFFFh
0x1401f4635  mov     rcx, [r14+10h]
0x1401f4639  mov     edx, [r14+60h]
0x1401f463d  mov     [rsp+270h+var_238], r13
0x1401f4642  mov     [rsp+270h+var_240], r12
0x1401f4647  mov     [rsp+270h+var_248], rcx
0x1401f464c  xor     ecx, ecx
0x1401f464e  mov     [rsp+270h+var_250], rdx
0x1401f4653  mov     edx, 40001h
0x1401f4658  call    DxgkLogInternalTriageEvent
0x1401f465d  mov     eax, r12d
0x1401f4660  jmp     loc_1401F519C
0x1401f4665  mov     ebx, r13d
0x1401f4668  cmp     ebx, [r14+60h]
0x1401f466c  jnb     short loc_1401F46D2
0x1401f466e  mov     r15, [r14+80h]
0x1401f4675  mov     eax, ebx
0x1401f4677  imul    rsi, rax, 0FB8h
0x1401f467e  lea     rcx, [r15+388h]
0x1401f4685  add     rcx, rsi; struct _KEVENT **
0x1401f4688  mov     [rsi+r15+8], r14
0x1401f468d  mov     [rsi+r15+10h], ebx
0x1401f4692  mov     [rsi+r15+318h], ebx
0x1401f469a  mov     [rsi+r15+348h], ebx
0x1401f46a2  mov     [rsi+r15+370h], ebx
0x1401f46aa  call    ?DxgCreateEvent@@YAJPEAPEAU_KEVENT@@W4_EVENT_TYPE@@E@Z; DxgCreateEvent(_KEVENT * *,_EVENT_TYPE,uchar)
0x1401f46af  test    eax, eax
0x1401f46b1  js      loc_1401F519C
0x1401f46b7  lea     rcx, [r15+390h]
0x1401f46be  add     rcx, rsi; struct _KEVENT **
0x1401f46c1  call    ?DxgCreateEvent@@YAJPEAPEAU_KEVENT@@W4_EVENT_TYPE@@E@Z; DxgCreateEvent(_KEVENT * *,_EVENT_TYPE,uchar)
0x1401f46c6  test    eax, eax
0x1401f46c8  js      loc_1401F519C
0x1401f46ce  inc     ebx
0x1401f46d0  jmp     short loc_1401F4668
0x1401f46d2  lea     rdx, [r14+70h]; void *
0x1401f46d6  mov     rcx, r14; struct ADAPTER_DISPLAY *
0x1401f46d9  call    ?MonitorCreateMonitorManager@@YAJPEAVADAPTER_DISPLAY@@PEAX@Z; MonitorCreateMonitorManager(ADAPTER_DISPLAY *,void *)
0x1401f46de  test    eax, eax
0x1401f46e0  js      loc_1401F519C
0x1401f46e6  lea     rdx, [r14+68h]; struct VIDPN_MGR **
0x1401f46ea  mov     rcx, r14; struct ADAPTER_DISPLAY *
0x1401f46ed  call    ?CreateVidPnMgr@VIDPN_MGR_CLASSFACTORY@@SAJQEAVADAPTER_DISPLAY@@PEAPEAVVIDPN_MGR@@@Z; VIDPN_MGR_CLASSFACTORY::CreateVidPnMgr(ADAPTER_DISPLAY * const,VIDPN_MGR * *)
0x1401f46f2  cmp     eax, 0C01E0327h
0x1401f46f7  jle     loc_1401F519C
0x1401f46fd  lea     ecx, [rax+3FE1FCD6h]
0x1401f4703  cmp     ecx, 3FE1FCD5h
0x1401f4709  jbe     loc_1401F519C
0x1401f470f  mov     rax, [r14+10h]
0x1401f4713  test    dword ptr [rax+1BCh], 100h
0x1401f471d  jz      loc_1401F47D1
0x1401f4723  lea     rsi, [r14+78h]
0x1401f4727  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401f472c  lea     r9, [rsp+270h+EventHandle]; struct _LUID *
0x1401f4731  mov     [rsp+270h+var_250], rsi; struct OUTPUTDUPL_MGR **
0x1401f4736  lea     r8, [rsp+270h+var_210]; struct _LUID *
0x1401f473b  xor     edx, edx; struct ADAPTER_DISPLAY *
0x1401f473d  mov     rcx, [rax+400h]
0x1401f4744  mov     rax, [r14+10h]
0x1401f4748  mov     qword ptr [rsp+270h+var_210.Type], rcx
0x1401f474d  mov     rcx, [rax+19Ch]
0x1401f4754  mov     [rsp+270h+EventHandle], rcx
0x1401f4759  mov     ecx, [r14+60h]; unsigned int
0x1401f475d  call    ?CreateOutputDuplManager@@YAJIPEAVADAPTER_DISPLAY@@PEAU_LUID@@1PEAPEAVOUTPUTDUPL_MGR@@@Z; CreateOutputDuplManager(uint,ADAPTER_DISPLAY *,_LUID *,_LUID *,OUTPUTDUPL_MGR * *)
0x1401f4762  test    eax, eax
0x1401f4764  js      loc_1401F519C
0x1401f476a  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401f476f  mov     rcx, [rsi]
0x1401f4772  mov     rbx, rax
0x1401f4775  lea     rdx, [rcx-18h]
0x1401f4779  neg     rcx
0x1401f477c  lea     rcx, [rsp+270h+var_210]; this
0x1401f4781  sbb     rsi, rsi
0x1401f4784  xor     r8d, r8d; unsigned __int8
0x1401f4787  and     rsi, rdx
0x1401f478a  lea     rdx, [rax+600h]; struct DXGFASTMUTEX *
0x1401f4791  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x1401f4796  lea     rcx, [rsp+270h+var_210]; this
0x1401f479b  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1401f47a0  add     rbx, 630h
0x1401f47a7  mov     rax, [rbx+8]
0x1401f47ab  cmp     [rax], rbx
0x1401f47ae  jz      short loc_1401F47B7
0x1401f47b0  mov     ecx, 3
0x1401f47b5  int     29h; Win8: RtlFailFast(ecx)
0x1401f47b7  mov     [rsi], rbx
0x1401f47ba  lea     rcx, [rsp+270h+var_210]; this
0x1401f47bf  mov     [rsi+8], rax
0x1401f47c3  mov     [rax], rsi
0x1401f47c6  mov     [rbx+8], rsi
0x1401f47ca  call    ??1DXGPROCESSCOPYPROTECTIONMUTEX@@QEAA@XZ; DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX(void)
0x1401f47cf  jmp     short loc_1401F47F4
0x1401f47d1  mov     ecx, [r14+60h]; unsigned int
0x1401f47d5  lea     rax, [r14+78h]
0x1401f47d9  xor     r9d, r9d; struct _LUID *
0x1401f47dc  mov     [rsp+270h+var_250], rax; struct OUTPUTDUPL_MGR **
0x1401f47e1  xor     r8d, r8d; struct _LUID *
0x1401f47e4  mov     rdx, r14; struct ADAPTER_DISPLAY *
0x1401f47e7  call    ?CreateOutputDuplManager@@YAJIPEAVADAPTER_DISPLAY@@PEAU_LUID@@1PEAPEAVOUTPUTDUPL_MGR@@@Z; CreateOutputDuplManager(uint,ADAPTER_DISPLAY *,_LUID *,_LUID *,OUTPUTDUPL_MGR * *)
0x1401f47ec  test    eax, eax
0x1401f47ee  js      loc_1401F519C
0x1401f47f4  lea     rax, [r14+260h]
0x1401f47fb  mov     [rsp+270h+var_218], 1
0x1401f4803  mov     [rax+8], rax
0x1401f4807  lea     r13, [r14+210h]
0x1401f480e  mov     [rax], rax
0x1401f4811  lea     r12, [r14+214h]
0x1401f4818  lea     rsi, [r14+218h]
0x1401f481f  mov     dword ptr [r13+0], 0
0x1401f4827  lea     r15, [r14+21Ch]
0x1401f482e  mov     dword ptr [r12], 0C8h
0x1401f4836  lea     rbx, [r14+220h]
0x1401f483d  mov     dword ptr [rsi], 3E8h
0x1401f4843  xor     edx, edx; Val
0x1401f4845  mov     dword ptr [r15], 1312D00h
0x1401f484c  mov     r8d, 188h; Size
0x1401f4852  mov     dword ptr [rbx], 0
0x1401f4858  lea     rcx, [rbp+170h+var_1E0]; void *
0x1401f485c  call    memset
0x1401f4861  xor     edx, edx
0x1401f4863  mov     [rbp+170h+var_190], r13
0x1401f4867  mov     ecx, 4000000h
0x1401f486c  mov     [rbp+170h+var_1B8], rdx
0x1401f4870  mov     r8d, 120h
0x1401f4876  mov     [rbp+170h+var_1C0], ecx
0x1401f4879  lea     rax, aModelistcachin; "ModeListCaching"
0x1401f4880  mov     [rbp+170h+var_1D8], r8d
0x1401f4884  mov     [rbp+170h+var_1D0], rax
0x1401f4888  xor     r9d, r9d
0x1401f488b  lea     rax, [rsp+270h+var_218]
0x1401f4890  mov     [rbp+170h+var_1B0], edx
0x1401f4893  mov     [rbp+170h+var_1C8], rax
0x1401f4897  lea     rax, aSettimingsflag; "SetTimingsFlags"
0x1401f489e  mov     [rbp+170h+var_198], rax
0x1401f48a2  lea     rax, aShortlinktrain; "ShortLinkTrainingTimeout"
0x1401f48a9  mov     [rbp+170h+var_160], rax
0x1401f48ad  lea     rax, aLonglinktraini; "LongLinkTrainingTimeout"
0x1401f48b4  mov     [rbp+170h+var_128], rax
0x1401f48b8  lea     rax, aHpdfilterlimit; "HPDFilterLimit"
0x1401f48bf  mov     [rbp+170h+var_F0], rax
0x1401f48c6  lea     rax, aEnablevirtualr; "EnableVirtualRefreshRateOnExternalMonit"...
0x1401f48cd  mov     [rbp+170h+var_1A8], rdx
0x1401f48d1  mov     [rbp+170h+var_1A0], r8d
0x1401f48d5  mov     [rbp+170h+var_188], ecx
0x1401f48d8  mov     [rbp+170h+var_180], rdx
0x1401f48dc  mov     [rbp+170h+var_178], edx
0x1401f48df  mov     [rbp+170h+var_170], rdx
0x1401f48e3  mov     [rbp+170h+var_168], r8d
0x1401f48e7  mov     [rbp+170h+var_150], ecx
0x1401f48ea  mov     [rbp+170h+var_148], rdx
0x1401f48ee  mov     [rbp+170h+var_140], edx
0x1401f48f1  mov     [rbp+170h+var_138], rdx
0x1401f48f5  mov     [rbp+170h+var_130], r8d
0x1401f48f9  mov     [rbp+170h+var_118], ecx
0x1401f48fc  mov     [rbp+170h+var_110], rdx
0x1401f4900  mov     [rbp+170h+var_108], edx
0x1401f4903  mov     [rbp+170h+var_100], rdx
0x1401f4907  mov     [rbp+170h+var_F8], r8d
0x1401f490b  mov     [rbp+170h+var_E0], ecx
0x1401f4911  mov     [rbp+170h+var_D8], rdx
  ... truncated ...
```
