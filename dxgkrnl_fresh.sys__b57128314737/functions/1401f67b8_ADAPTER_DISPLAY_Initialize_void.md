# ADAPTER_DISPLAY::Initialize(void)

- ea: `0x1401f67b8`
- end: `0x1401f75a0`
- name: `?Initialize@ADAPTER_DISPLAY@@QEAAJXZ`
- size: `3560`
- prototype: `__int64 __fastcall(ADAPTER_DISPLAY *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401d3a20`

## callees

- `0x1400091f0`
- `0x140012540`
- `0x1400146ac`
- `0x140015290`
- `0x140016388`
- `0x14001b9c0`
- `0x140035130`
- `0x14005f6a4`
- `0x14007fc10`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x140196118`
- `0x1401f67b8`
- `0x14024c6e4`
- `0x1402ca0c0`
- `0x1402f350c`
- `0x140308868`
- `0x14035fa08`
- `0x140382794`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401f6d50`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401f7055`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401f6d50`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1401f7055`
- `ntoskrnl!ObfReferenceObject` at `0x1401f755c`
- `ntoskrnl!ObfReferenceObject` at `0x1401f755c`
- `ntoskrnl!ZwClose` at `0x1401f756d`
- `ntoskrnl!ZwClose` at `0x1401f756d`
- `ntoskrnl!KeClearEvent` at `0x1401f7549`
- `ntoskrnl!KeClearEvent` at `0x1401f7549`
- `ntoskrnl!IoCreateNotificationEvent` at `0x1401f74e0`
- `ntoskrnl!IoCreateNotificationEvent` at `0x1401f74e0`
- `watchdog!WdLogSingleEntry2` at `0x1401f714e`
- `watchdog!WdLogSingleEntry2` at `0x1401f7405`
- `watchdog!WdLogSingleEntry2` at `0x1401f714e`
- `watchdog!WdLogSingleEntry2` at `0x1401f7405`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401f6865`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1401f6865`
- `watchdog!WdLogSingleEntry3` at `0x1401f69ef`
- `watchdog!WdLogSingleEntry3` at `0x1401f6e37`
- `watchdog!WdLogSingleEntry3` at `0x1401f6ec2`
- `watchdog!WdLogSingleEntry3` at `0x1401f6f4d`
- `watchdog!WdLogSingleEntry3` at `0x1401f70fd`
- `watchdog!WdLogSingleEntry3` at `0x1401f71f8`
- `watchdog!WdLogSingleEntry3` at `0x1401f69ef`
- `watchdog!WdLogSingleEntry3` at `0x1401f6e37`
- `watchdog!WdLogSingleEntry3` at `0x1401f6ec2`
- `watchdog!WdLogSingleEntry3` at `0x1401f6f4d`
- `watchdog!WdLogSingleEntry3` at `0x1401f70fd`
- `watchdog!WdLogSingleEntry3` at `0x1401f71f8`
- `watchdog!WdLogSingleEntry0` at `0x1401f6d95`
- `watchdog!WdLogSingleEntry0` at `0x1401f7090`
- `watchdog!WdLogSingleEntry0` at `0x1401f7485`
- `watchdog!WdLogSingleEntry0` at `0x1401f74fb`
- `watchdog!WdLogSingleEntry0` at `0x1401f6d95`
- `watchdog!WdLogSingleEntry0` at `0x1401f7090`
- `watchdog!WdLogSingleEntry0` at `0x1401f7485`
- `watchdog!WdLogSingleEntry0` at `0x1401f74fb`
- `watchdog!WdLogSingleEntry1` at `0x1401f68bf`
- `watchdog!WdLogSingleEntry1` at `0x1401f6d73`
- `watchdog!WdLogSingleEntry1` at `0x1401f68bf`
- `watchdog!WdLogSingleEntry1` at `0x1401f6d73`

## string_xrefs

- `0x1401f6c82`: `ShortLinkTrainingTimeout`
- `0x1401f6c8d`: `LongLinkTrainingTimeout`
- `0x1401f6e48`: `Invalid link training timeout registry value (0x%I64x, 0x%I64x) on adapter 0x%I64x, fallback to the default value.`
- `0x1401f6f5e`: `Miniport driver wants t fallback to use DdiCommitVidPn but it does not supply pfnCommitVidPn on adapter (0x%I64x%08I64x), returning 0x%I64x.`
- `0x1401f70a1`: `GetAdapter()->GetAdapterVendorId() != VENDOR_ID_QUALCOMM`
- `0x1401f7209`: `Force to stop adapter (0x%I64x%08I64x) due to target ID does not support reduced hash size and registry requested to use virtual topologies, returning 0x%I64x.`
- `0x1401f750c`: `Failed to create adapter VidPnSourceUsedBySession event object.`

## pseudocode

```c
NTSTATUS __fastcall ADAPTER_DISPLAY::Initialize(ADAPTER_DISPLAY *this)
{
  __int64 v1; // r8
  int *v2; // rdi
  int v4; // eax
  __int64 v5; // rdx
  int v6; // ecx
  NTSTATUS result; // eax
  unsigned int v8; // eax
  __int64 v9; // rsi
  __int64 v10; // rax
  unsigned __int64 v11; // kr00_8
  bool v12; // cf
  __int64 v13; // rax
  _QWORD *v14; // rax
  enum _EVENT_TYPE v15; // edx
  _QWORD *v16; // rbx
  unsigned int i; // ebx
  __int64 v18; // r15
  __int64 v19; // rsi
  enum _EVENT_TYPE v20; // edx
  __int64 v21; // rcx
  __int64 v22; // rax
  struct DXGGLOBAL *Global; // rbx
  char *v24; // rsi
  char *v25; // rbx
  char **v26; // rax
  unsigned int *v27; // r12
  unsigned int *v28; // rsi
  int RegistryValues; // eax
  int v30; // r13d
  int v31; // eax
  unsigned int v32; // eax
  _DWORD *v33; // rbx
  unsigned int v34; // ecx
  __int64 v35; // rax
  __int64 v36; // rcx
  int v37; // edx
  bool v38; // cl
  bool v39; // zf
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // r8
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
  if ( *(_DWORD *)(v1 + 2408) >= 0x5010u && !*(_BYTE *)(v1 + 209) && (*(_DWORD *)(v1 + 3104) & 8) == 0 )
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
      WdLogGlobalForLineNumber = 4754;
      *v2 = 0;
      if ( *(int *)(*((_QWORD *)this + 2) + 2864LL) >= 8704 )
        *v2 = 2;
    }
    v5 = *((_QWORD *)this + 2);
    v6 = *v2;
    if ( *(int *)(v5 + 2864) >= 9472 )
    {
      if ( (v6 & 0xC) == 0xC )
      {
        WdLogSingleEntry1(2, this);
        WdLogGlobalForLineNumber = 4783;
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
        return -1073741811;
      }
      v1 = *((_QWORD *)this + 2);
    }
    else
    {
      v6 &= 0xFFFFFFF3;
      v1 = *((_QWORD *)this + 2);
      *v2 = v6;
    }
    if ( *(int *)(v5 + 2864) < 9984 )
    {
      v6 &= ~0x10u;
      *v2 = v6;
    }
    if ( *(int *)(v5 + 2864) < 10496 || *(_QWORD *)(v5 + 832) || !*(_DWORD *)(v5 + 1984) || (v6 & 2) == 0 )
    {
      v6 &= ~0x20u;
      *v2 = v6;
    }
    if ( *(int *)(v5 + 2864) < 12288 )
    {
      v6 &= ~0x40u;
      *v2 = v6;
    }
    if ( g_bDbgForceUsb4MonitorSupport )
      *v2 = v6 | 0x40;
  }
  v8 = *(_DWORD *)(v1 + 1984);
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
    v16 = v14 + 1;
    *v14 = v9;
    `vector constructor iterator'(v14 + 1, 0xFB8u, (unsigned int)v9, (void *(*)(void *))DISPLAY_SOURCE::DISPLAY_SOURCE);
  }
  else
  {
    v16 = 0;
  }
  *((_QWORD *)this + 16) = v16;
  if ( !v16 )
  {
    WdLogSingleEntry3(6, *((unsigned int *)this + 24), *((_QWORD *)this + 2), -1073741801);
    WdLogGlobalForLineNumber = 4839;
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
    return -1073741801;
  }
  for ( i = 0; i < *((_DWORD *)this + 24); ++i )
  {
    v18 = *((_QWORD *)this + 16);
    v19 = 4024LL * i;
    *(_QWORD *)(v19 + v18 + 8) = this;
    *(_DWORD *)(v19 + v18 + 16) = i;
    *(_DWORD *)(v19 + v18 + 792) = i;
    *(_DWORD *)(v19 + v18 + 840) = i;
    *(_DWORD *)(v19 + v18 + 880) = i;
    result = DxgCreateEvent((PVOID *)(v19 + v18 + 904), v15);
    if ( result < 0 )
      return result;
    result = DxgCreateEvent((PVOID *)(v19 + v18 + 912), v20);
    if ( result < 0 )
      return result;
  }
  result = MonitorCreateMonitorManager(this, (char *)this + 112);
  if ( result >= 0 )
  {
    result = VIDPN_MGR_CLASSFACTORY::CreateVidPnMgr(this, (struct VIDPN_MGR **)this + 13);
    if ( result > -1071774937 && (unsigned int)(result + 1071774934) > 0x3FE1FCD5 )
    {
      if ( (*(_DWORD *)(*((_QWORD *)this + 2) + 444LL) & 0x100) != 0 )
      {
        v21 = *((_QWORD *)DXGGLOBAL::GetGlobal() + 128);
        v22 = *((_QWORD *)this + 2);
        *(_QWORD *)&v72.Type = v21;
        EventHandle = *(void **)(v22 + 412);
        result = CreateOutputDuplManager(
                   *((_DWORD *)this + 24),
                   0,
                   (struct _LUID *)&v72,
                   (struct _LUID *)&EventHandle,
                   (struct OUTPUTDUPL_MGR **)this + 15);
        if ( result < 0 )
          return result;
        Global = DXGGLOBAL::GetGlobal();
        v24 = (char *)((*((_QWORD *)this + 15) - 24LL) & -(__int64)(*((_QWORD *)this + 15) != 0));
        DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)&v72, (struct DXGGLOBAL *)((char *)Global + 1536), 0);
        DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)&v72);
        v25 = (char *)Global + 1584;
        v26 = (char **)*((_QWORD *)v25 + 1);
        if ( *v26 != v25 )
          __fastfail(3u);
        *(_QWORD *)v24 = v25;
        *((_QWORD *)v24 + 1) = v26;
        *v26 = v24;
        *((_QWORD *)v25 + 1) = v24;
        DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)&v72);
      }
      else
      {
        result = CreateOutputDuplManager(*((_DWORD *)this + 24), this, 0, 0, (struct OUTPUTDUPL_MGR **)this + 15);
        if ( result < 0 )
          return result;
      }
      v71 = 1;
      *((_QWORD *)this + 77) = (char *)this + 608;
      *((_QWORD *)this + 76) = (char *)this + 608;
      v27 = (unsigned int *)((char *)this + 532);
      v28 = (unsigned int *)((char *)this + 536);
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
      v30 = RegistryValues;
      if ( RegistryValues >= 0 )
      {
        v31 = v71;
      }
      else
      {
        WdLogSingleEntry1(4, RegistryValues);
        WdLogGlobalForLineNumber = 4988;
        if ( v30 != -1073741772 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 4991;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"Status == STATUS_OBJECT_NAME_NOT_FOUND",
            4991,
            0,
            0,
            0,
            0);
        }
        v31 = 1;
        *((_DWORD *)this + 132) = 0;
        v71 = 1;
        v30 = 0;
        *v27 = 200;
        *v28 = 1000;
      }
      *((_BYTE *)this + 292) = v31 == 1;
      v32 = *v28;
      if ( !*v28 || *v27 >= v32 || v32 >= 0x7530 )
      {
        WdLogSingleEntry3(2, *v27, *v27, *((_QWORD *)this + 2));
        WdLogGlobalForLineNumber = 5016;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Invalid link training timeout registry value (0x%I64x, 0x%I64x) on adapter 0x%I64x, fallback to "
                         "the default value.",
          *v27,
          *v27,
          *((_QWORD *)this + 2),
          0,
          0);
        *v27 = 200;
        *((_DWORD *)this + 134) = 1000;
      }
      v33 = (_DWORD *)((char *)this + 540);
      v34 = *((_DWORD *)this + 135);
      if ( v34 - 1000000 > 0x5E69EC0 )
      {
        if ( v34 )
        {
          WdLogSingleEntry3(2, v34, 20000000, *((_QWORD *)this + 2));
          WdLogGlobalForLineNumber = 5031;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Invalid hot-plug filter limit of %#x on adapter 0x%I64x.  Using default of %#x.",
            (unsigned int)*v33,
            20000000,
            *((_QWORD *)this + 2),
            0,
            0);
        }
        *v33 = 20000000;
      }
      if ( (*((_DWORD *)this + 132) & 1) != 0 )
      {
        v35 = *((_QWORD *)this + 2);
        if ( !*(_QWORD *)(v35 + 656) )
        {
          WdLogSingleEntry3(2, *(int *)(v35 + 416), *(unsigned int *)(v35 + 412), -1073741735);
          WdLogGlobalForLineNumber = 5048;
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
          return -1073741735;
        }
      }
      v36 = *((_QWORD *)this + 2);
      v37 = *(_DWORD *)(v36 + 420);
      if ( (*(_DWORD *)(v36 + 444) & 0x400) != 0 )
      {
        if ( v37 == 1297040209
          && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v36 + 216) + 64LL) + 40LL) + 28LL) < 0x700Au )
        {
          *((_BYTE *)this + 289) = 1;
          v38 = 1;
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
          v39 = (_DWORD)EventHandle == 0;
          *((_BYTE *)this + 289) = (_DWORD)EventHandle != 0;
          v38 = !v39;
        }
        v40 = 290;
        v41 = (__int64)this;
      }
      else
      {
        if ( v37 == 1297040209 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 5105;
          DxgkLogInternalTriageEvent(
            0,
            262146,
            -1,
            (unsigned int)L"GetAdapter()->GetAdapterVendorId() != VENDOR_ID_QUALCOMM",
            5105,
            0,
            0,
            0,
            0);
        }
        v42 = *((_QWORD *)this + 2);
        v43 = *(unsigned int *)(v42 + 412);
        v44 = *(int *)(v42 + 416);
        if ( (*v2 & 2) != 0 )
        {
          WdLogSingleEntry3(2, v44, v43, -1073741735);
          WdLogGlobalForLineNumber = 5117;
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
          return -1073741735;
        }
        WdLogSingleEntry2(4, v44, v43);
        WdLogGlobalForLineNumber = 5125;
        v38 = 0;
        *((_BYTE *)this + 289) = 0;
        v40 = (__int64)this;
        v41 = 290;
      }
      *(_BYTE *)(v41 + v40) = v38;
      v45 = *((_QWORD *)this + 2);
      if ( *(int *)(v45 + 3132) < 2000 )
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
              WdLogGlobalForLineNumber = 5151;
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
              return -1073741735;
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
      if ( *(_QWORD *)(v49 + 3256) )
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
          v30 = -1073741801;
        memset(&v72, 0, 24);
        v53 = *(int (__fastcall **)(_QWORD, struct _DXGKARG_QUERYADAPTERINFO *))(v52 + 2496);
        if ( v53 && v53(*(_QWORD *)(v52 + 2424), &v72) >= 0 )
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
      v60 = __OFSUB__(*(_DWORD *)(v58 + 2864), 8704);
      v59 = *(_DWORD *)(v58 + 2864) - 8704 < 0;
      v61 = *(_QWORD *)(v58 + 216);
      v62 = v59 ^ v60;
      LODWORD(EventHandle) = v62;
      if ( (int)DpiReadPnpRegistryValue(v61, L"NeedToSuspendVidSchBeforeSetGammaRamp", &EventHandle, 4, 2) >= 0 )
      {
        v63 = (int)EventHandle;
        if ( (_DWORD)EventHandle != v62 )
        {
          WdLogSingleEntry2(3, (unsigned int)EventHandle, *((_QWORD *)this + 2));
          WdLogGlobalForLineNumber = 5250;
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
        WdLogGlobalForLineNumber = 5263;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"NT_SUCCESS(TmpStatus)", 5263, 0, 0, 0, 0);
      }
      if ( v30 >= 0 )
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
          WdLogGlobalForLineNumber = 5274;
          DxgkLogInternalTriageEvent(
            0,
            262145,
            -1,
            (unsigned int)L"Failed to create adapter VidPnSourceUsedBySession event object.",
            5274,
            0,
            0,
            0,
            0);
          return -1073741801;
        }
      }
      return v30;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1401f67b8  push    rbp
0x1401f67ba  push    rbx
0x1401f67bb  push    rsi
0x1401f67bc  push    rdi
0x1401f67bd  push    r12
0x1401f67bf  push    r13
0x1401f67c1  push    r14
0x1401f67c3  push    r15
0x1401f67c5  lea     rbp, [rsp-138h]
0x1401f67cd  sub     rsp, 238h
0x1401f67d4  mov     rax, cs:__security_cookie
0x1401f67db  xor     rax, rsp
0x1401f67de  mov     [rbp+170h+var_50], rax
0x1401f67e5  mov     r8, [rcx+10h]
0x1401f67e9  lea     rdi, [rcx+18h]
0x1401f67ed  xor     r13d, r13d
0x1401f67f0  mov     r14, rcx
0x1401f67f3  mov     [rdi], r13d
0x1401f67f6  cmp     dword ptr [r8+968h], 5010h
0x1401f6801  lea     esi, [r13+2]
0x1401f6805  jb      loc_1401F696B
0x1401f680b  cmp     [r8+0D1h], r13b
0x1401f6812  jnz     loc_1401F696B
0x1401f6818  mov     eax, [r8+0C20h]
0x1401f681f  shr     eax, 3
0x1401f6822  test    al, 1
0x1401f6824  jnz     loc_1401F696B
0x1401f682a  lea     rdx, [rsp+270h+var_210]; struct _DXGKARG_QUERYADAPTERINFO *
0x1401f682f  mov     qword ptr [rsp+270h+var_210.Type], 10h
0x1401f6838  mov     rcx, r8; this
0x1401f683b  mov     qword ptr [rsp+270h+var_210.InputDataSize], r13
0x1401f6840  mov     qword ptr [rbp+170h+var_210.Flags], r13
0x1401f6844  mov     dword ptr [rbp+170h+var_210.hKmdProcessHandle+4], r13d
0x1401f6848  mov     [rsp+270h+var_210.pInputData], r13
0x1401f684d  mov     [rsp+270h+var_210.pOutputData], rdi
0x1401f6852  mov     [rbp+170h+var_210.OutputDataSize], 4
0x1401f6859  call    ?DdiQueryAdapterInfo@DXGADAPTER@@QEAAJPEAU_DXGKARG_QUERYADAPTERINFO@@@Z; DXGADAPTER::DdiQueryAdapterInfo(_DXGKARG_QUERYADAPTERINFO *)
0x1401f685e  test    eax, eax
0x1401f6860  jns     short loc_1401F6895
0x1401f6862  movsxd  rbx, eax
0x1401f6865  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1401f686c  nop     dword ptr [rax+rax+00h]
0x1401f6871  mov     [rax+18h], rbx
0x1401f6875  xor     eax, eax
0x1401f6877  mov     cs:WdLogGlobalForLineNumber, 1292h
0x1401f6881  mov     [rdi], eax
0x1401f6883  mov     rax, [r14+10h]
0x1401f6887  cmp     dword ptr [rax+0B30h], 2200h
0x1401f6891  jl      short loc_1401F6895
0x1401f6893  mov     [rdi], esi
0x1401f6895  mov     rdx, [r14+10h]
0x1401f6899  mov     ecx, [rdi]
0x1401f689b  cmp     dword ptr [rdx+0B30h], 2500h
0x1401f68a5  jge     short loc_1401F68B1
0x1401f68a7  and     ecx, 0FFFFFFF3h
0x1401f68aa  mov     r8, rdx
0x1401f68ad  mov     [rdi], ecx
0x1401f68af  jmp     short loc_1401F6913
0x1401f68b1  mov     eax, ecx
0x1401f68b3  and     eax, 0Ch
0x1401f68b6  cmp     al, 0Ch
0x1401f68b8  jnz     short loc_1401F690F
0x1401f68ba  mov     rdx, r14
0x1401f68bd  mov     ecx, esi
0x1401f68bf  call    cs:__imp_WdLogSingleEntry1
0x1401f68c6  nop     dword ptr [rax+rax+00h]
0x1401f68cb  mov     [rsp+270h+var_230], r13
0x1401f68d0  lea     r9, aAdapter0xI64xB; "Adapter 0x%I64x: Both HdrFP16ScanoutSup"...
0x1401f68d7  mov     [rsp+270h+var_238], r13
0x1401f68dc  or      r8d, 0FFFFFFFFh
0x1401f68e0  mov     [rsp+270h+var_240], r13
0x1401f68e5  mov     edx, 40000h
0x1401f68ea  mov     [rsp+270h+var_248], r13
0x1401f68ef  xor     ecx, ecx
0x1401f68f1  mov     [rsp+270h+var_250], r14
0x1401f68f6  mov     cs:WdLogGlobalForLineNumber, 12AFh
0x1401f6900  call    DxgkLogInternalTriageEvent
0x1401f6905  mov     eax, 0C000000Dh
0x1401f690a  jmp     loc_1401F757C
0x1401f690f  mov     r8, [r14+10h]
0x1401f6913  cmp     dword ptr [rdx+0B30h], 2700h
0x1401f691d  jge     short loc_1401F6924
0x1401f691f  and     ecx, 0FFFFFFEFh
0x1401f6922  mov     [rdi], ecx
0x1401f6924  cmp     dword ptr [rdx+0B30h], 2900h
0x1401f692e  jl      short loc_1401F6947
0x1401f6930  cmp     [rdx+340h], r13
0x1401f6937  jnz     short loc_1401F6947
0x1401f6939  cmp     [rdx+7C0h], r13d
0x1401f6940  jz      short loc_1401F6947
0x1401f6942  test    sil, cl
0x1401f6945  jnz     short loc_1401F694C
0x1401f6947  and     ecx, 0FFFFFFDFh
0x1401f694a  mov     [rdi], ecx
0x1401f694c  cmp     dword ptr [rdx+0B30h], 3000h
0x1401f6956  jge     short loc_1401F695D
0x1401f6958  and     ecx, 0FFFFFFBFh
0x1401f695b  mov     [rdi], ecx
0x1401f695d  cmp     cs:?g_bDbgForceUsb4MonitorSupport@@3IA, r13d; uint g_bDbgForceUsb4MonitorSupport
0x1401f6964  jz      short loc_1401F696B
0x1401f6966  or      ecx, 40h
0x1401f6969  mov     [rdi], ecx
0x1401f696b  mov     eax, [r8+7C0h]
0x1401f6972  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1401f6979  mov     [r14+60h], eax
0x1401f697d  mov     esi, eax
0x1401f697f  mov     r15d, 0FB8h
0x1401f6985  mov     eax, r15d
0x1401f6988  mul     rsi
0x1401f698b  lea     r8d, [rcx+41h]
0x1401f698f  mov     edx, 4B677844h
0x1401f6994  cmovb   rax, rcx
0x1401f6998  add     rax, 8
0x1401f699c  cmovb   rax, rcx
0x1401f69a0  mov     rcx, rax
0x1401f69a3  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401f69a8  test    rax, rax
0x1401f69ab  jz      short loc_1401F69CB
0x1401f69ad  lea     rbx, [rax+8]
0x1401f69b1  mov     [rax], rsi
0x1401f69b4  mov     rcx, rbx; void *
0x1401f69b7  lea     r9, ??0DISPLAY_SOURCE@@QEAA@XZ; void *(*)(void *)
0x1401f69be  mov     r8d, esi; unsigned __int64
0x1401f69c1  mov     edx, r15d; unsigned __int64
0x1401f69c4  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x1401f69c9  jmp     short loc_1401F69CE
0x1401f69cb  mov     rbx, r13
0x1401f69ce  mov     [r14+80h], rbx
0x1401f69d5  test    rbx, rbx
0x1401f69d8  jnz     short loc_1401F6A45
0x1401f69da  mov     edx, [r14+60h]
0x1401f69de  lea     ecx, [rbx+6]
0x1401f69e1  mov     r8, [r14+10h]
0x1401f69e5  mov     r12, 0FFFFFFFFC0000017h
0x1401f69ec  mov     r9, r12
0x1401f69ef  call    cs:__imp_WdLogSingleEntry3
0x1401f69f6  nop     dword ptr [rax+rax+00h]
0x1401f69fb  mov     [rsp+270h+var_230], r13
0x1401f6a00  lea     r9, aFailedToAlloca_95; "Failed to allocate 0x%I64x of display s"...
0x1401f6a07  mov     cs:WdLogGlobalForLineNumber, 12E7h
0x1401f6a11  or      r8d, 0FFFFFFFFh
0x1401f6a15  mov     rcx, [r14+10h]
0x1401f6a19  mov     edx, [r14+60h]
0x1401f6a1d  mov     [rsp+270h+var_238], r13
0x1401f6a22  mov     [rsp+270h+var_240], r12
0x1401f6a27  mov     [rsp+270h+var_248], rcx
0x1401f6a2c  xor     ecx, ecx
0x1401f6a2e  mov     [rsp+270h+var_250], rdx
0x1401f6a33  mov     edx, 40001h
0x1401f6a38  call    DxgkLogInternalTriageEvent
0x1401f6a3d  mov     eax, r12d
0x1401f6a40  jmp     loc_1401F757C
0x1401f6a45  mov     ebx, r13d
0x1401f6a48  cmp     ebx, [r14+60h]
0x1401f6a4c  jnb     short loc_1401F6AB2
0x1401f6a4e  mov     r15, [r14+80h]
0x1401f6a55  mov     eax, ebx
0x1401f6a57  imul    rsi, rax, 0FB8h
0x1401f6a5e  lea     rcx, [r15+388h]
0x1401f6a65  add     rcx, rsi; struct _KEVENT **
0x1401f6a68  mov     [rsi+r15+8], r14
0x1401f6a6d  mov     [rsi+r15+10h], ebx
0x1401f6a72  mov     [rsi+r15+318h], ebx
0x1401f6a7a  mov     [rsi+r15+348h], ebx
0x1401f6a82  mov     [rsi+r15+370h], ebx
0x1401f6a8a  call    ?DxgCreateEvent@@YAJPEAPEAU_KEVENT@@W4_EVENT_TYPE@@E@Z; DxgCreateEvent(_KEVENT * *,_EVENT_TYPE,uchar)
0x1401f6a8f  test    eax, eax
0x1401f6a91  js      loc_1401F757C
0x1401f6a97  lea     rcx, [r15+390h]
0x1401f6a9e  add     rcx, rsi; struct _KEVENT **
0x1401f6aa1  call    ?DxgCreateEvent@@YAJPEAPEAU_KEVENT@@W4_EVENT_TYPE@@E@Z; DxgCreateEvent(_KEVENT * *,_EVENT_TYPE,uchar)
0x1401f6aa6  test    eax, eax
0x1401f6aa8  js      loc_1401F757C
0x1401f6aae  inc     ebx
0x1401f6ab0  jmp     short loc_1401F6A48
0x1401f6ab2  lea     rdx, [r14+70h]; void *
0x1401f6ab6  mov     rcx, r14; struct ADAPTER_DISPLAY *
0x1401f6ab9  call    ?MonitorCreateMonitorManager@@YAJPEAVADAPTER_DISPLAY@@PEAX@Z; MonitorCreateMonitorManager(ADAPTER_DISPLAY *,void *)
0x1401f6abe  test    eax, eax
0x1401f6ac0  js      loc_1401F757C
0x1401f6ac6  lea     rdx, [r14+68h]; struct VIDPN_MGR **
0x1401f6aca  mov     rcx, r14; struct ADAPTER_DISPLAY *
0x1401f6acd  call    ?CreateVidPnMgr@VIDPN_MGR_CLASSFACTORY@@SAJQEAVADAPTER_DISPLAY@@PEAPEAVVIDPN_MGR@@@Z; VIDPN_MGR_CLASSFACTORY::CreateVidPnMgr(ADAPTER_DISPLAY * const,VIDPN_MGR * *)
0x1401f6ad2  cmp     eax, 0C01E0327h
0x1401f6ad7  jle     loc_1401F757C
0x1401f6add  lea     ecx, [rax+3FE1FCD6h]
0x1401f6ae3  cmp     ecx, 3FE1FCD5h
0x1401f6ae9  jbe     loc_1401F757C
0x1401f6aef  mov     rax, [r14+10h]
0x1401f6af3  test    dword ptr [rax+1BCh], 100h
0x1401f6afd  jz      loc_1401F6BB1
0x1401f6b03  lea     rsi, [r14+78h]
0x1401f6b07  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401f6b0c  lea     r9, [rsp+270h+EventHandle]; struct _LUID *
0x1401f6b11  mov     [rsp+270h+var_250], rsi; struct OUTPUTDUPL_MGR **
0x1401f6b16  lea     r8, [rsp+270h+var_210]; struct _LUID *
0x1401f6b1b  xor     edx, edx; struct ADAPTER_DISPLAY *
0x1401f6b1d  mov     rcx, [rax+400h]
0x1401f6b24  mov     rax, [r14+10h]
0x1401f6b28  mov     qword ptr [rsp+270h+var_210.Type], rcx
0x1401f6b2d  mov     rcx, [rax+19Ch]
0x1401f6b34  mov     [rsp+270h+EventHandle], rcx
0x1401f6b39  mov     ecx, [r14+60h]; unsigned int
0x1401f6b3d  call    ?CreateOutputDuplManager@@YAJIPEAVADAPTER_DISPLAY@@PEAU_LUID@@1PEAPEAVOUTPUTDUPL_MGR@@@Z; CreateOutputDuplManager(uint,ADAPTER_DISPLAY *,_LUID *,_LUID *,OUTPUTDUPL_MGR * *)
0x1401f6b42  test    eax, eax
0x1401f6b44  js      loc_1401F757C
0x1401f6b4a  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401f6b4f  mov     rcx, [rsi]
0x1401f6b52  mov     rbx, rax
0x1401f6b55  lea     rdx, [rcx-18h]
0x1401f6b59  neg     rcx
0x1401f6b5c  lea     rcx, [rsp+270h+var_210]; this
0x1401f6b61  sbb     rsi, rsi
0x1401f6b64  xor     r8d, r8d; unsigned __int8
0x1401f6b67  and     rsi, rdx
0x1401f6b6a  lea     rdx, [rax+600h]; struct DXGFASTMUTEX *
0x1401f6b71  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x1401f6b76  lea     rcx, [rsp+270h+var_210]; this
0x1401f6b7b  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x1401f6b80  add     rbx, 630h
0x1401f6b87  mov     rax, [rbx+8]
0x1401f6b8b  cmp     [rax], rbx
0x1401f6b8e  jz      short loc_1401F6B97
0x1401f6b90  mov     ecx, 3
0x1401f6b95  int     29h; Win8: RtlFailFast(ecx)
0x1401f6b97  mov     [rsi], rbx
0x1401f6b9a  lea     rcx, [rsp+270h+var_210]; this
0x1401f6b9f  mov     [rsi+8], rax
0x1401f6ba3  mov     [rax], rsi
0x1401f6ba6  mov     [rbx+8], rsi
0x1401f6baa  call    ??1DXGPROCESSCOPYPROTECTIONMUTEX@@QEAA@XZ; DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX(void)
0x1401f6baf  jmp     short loc_1401F6BD4
0x1401f6bb1  mov     ecx, [r14+60h]; unsigned int
0x1401f6bb5  lea     rax, [r14+78h]
0x1401f6bb9  xor     r9d, r9d; struct _LUID *
0x1401f6bbc  mov     [rsp+270h+var_250], rax; struct OUTPUTDUPL_MGR **
0x1401f6bc1  xor     r8d, r8d; struct _LUID *
0x1401f6bc4  mov     rdx, r14; struct ADAPTER_DISPLAY *
0x1401f6bc7  call    ?CreateOutputDuplManager@@YAJIPEAVADAPTER_DISPLAY@@PEAU_LUID@@1PEAPEAVOUTPUTDUPL_MGR@@@Z; CreateOutputDuplManager(uint,ADAPTER_DISPLAY *,_LUID *,_LUID *,OUTPUTDUPL_MGR * *)
0x1401f6bcc  test    eax, eax
0x1401f6bce  js      loc_1401F757C
0x1401f6bd4  lea     rax, [r14+260h]
0x1401f6bdb  mov     [rsp+270h+var_218], 1
0x1401f6be3  mov     [rax+8], rax
0x1401f6be7  lea     r13, [r14+210h]
0x1401f6bee  mov     [rax], rax
0x1401f6bf1  lea     r12, [r14+214h]
0x1401f6bf8  lea     rsi, [r14+218h]
0x1401f6bff  mov     dword ptr [r13+0], 0
0x1401f6c07  lea     r15, [r14+21Ch]
0x1401f6c0e  mov     dword ptr [r12], 0C8h
0x1401f6c16  lea     rbx, [r14+220h]
0x1401f6c1d  mov     dword ptr [rsi], 3E8h
0x1401f6c23  xor     edx, edx; Val
0x1401f6c25  mov     dword ptr [r15], 1312D00h
0x1401f6c2c  mov     r8d, 188h; Size
0x1401f6c32  mov     dword ptr [rbx], 0
0x1401f6c38  lea     rcx, [rbp+170h+var_1E0]; void *
0x1401f6c3c  call    memset
0x1401f6c41  xor     edx, edx
0x1401f6c43  mov     [rbp+170h+var_190], r13
0x1401f6c47  mov     ecx, 4000000h
0x1401f6c4c  mov     [rbp+170h+var_1B8], rdx
0x1401f6c50  mov     r8d, 120h
0x1401f6c56  mov     [rbp+170h+var_1C0], ecx
0x1401f6c59  lea     rax, aModelistcachin; "ModeListCaching"
0x1401f6c60  mov     [rbp+170h+var_1D8], r8d
0x1401f6c64  mov     [rbp+170h+var_1D0], rax
0x1401f6c68  xor     r9d, r9d
0x1401f6c6b  lea     rax, [rsp+270h+var_218]
0x1401f6c70  mov     [rbp+170h+var_1B0], edx
0x1401f6c73  mov     [rbp+170h+var_1C8], rax
0x1401f6c77  lea     rax, aSettimingsflag; "SetTimingsFlags"
0x1401f6c7e  mov     [rbp+170h+var_198], rax
0x1401f6c82  lea     rax, aShortlinktrain; "ShortLinkTrainingTimeout"
0x1401f6c89  mov     [rbp+170h+var_160], rax
0x1401f6c8d  lea     rax, aLonglinktraini; "LongLinkTrainingTimeout"
0x1401f6c94  mov     [rbp+170h+var_128], rax
0x1401f6c98  lea     rax, aHpdfilterlimit; "HPDFilterLimit"
0x1401f6c9f  mov     [rbp+170h+var_F0], rax
0x1401f6ca6  lea     rax, aEnablevirtualr; "EnableVirtualRefreshRateOnExternalMonit"...
0x1401f6cad  mov     [rbp+170h+var_1A8], rdx
0x1401f6cb1  mov     [rbp+170h+var_1A0], r8d
0x1401f6cb5  mov     [rbp+170h+var_188], ecx
0x1401f6cb8  mov     [rbp+170h+var_180], rdx
0x1401f6cbc  mov     [rbp+170h+var_178], edx
0x1401f6cbf  mov     [rbp+170h+var_170], rdx
0x1401f6cc3  mov     [rbp+170h+var_168], r8d
0x1401f6cc7  mov     [rbp+170h+var_150], ecx
0x1401f6cca  mov     [rbp+170h+var_148], rdx
0x1401f6cce  mov     [rbp+170h+var_140], edx
0x1401f6cd1  mov     [rbp+170h+var_138], rdx
0x1401f6cd5  mov     [rbp+170h+var_130], r8d
0x1401f6cd9  mov     [rbp+170h+var_118], ecx
0x1401f6cdc  mov     [rbp+170h+var_110], rdx
0x1401f6ce0  mov     [rbp+170h+var_108], edx
0x1401f6ce3  mov     [rbp+170h+var_100], rdx
0x1401f6ce7  mov     [rbp+170h+var_F8], r8d
0x1401f6ceb  mov     [rbp+170h+var_E0], ecx
0x1401f6cf1  mov     [rbp+170h+var_D8], rdx
  ... truncated ...
```
