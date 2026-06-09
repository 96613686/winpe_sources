# ADAPTER_RENDER::Initialize(void)

- ea: `0x1401fa52c`
- end: `0x1401fbcc4`
- name: `?Initialize@ADAPTER_RENDER@@QEAAJXZ`
- size: `6040`
- prototype: `__int64 __fastcall(ADAPTER_RENDER *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1401f7f88`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140012380`
- `0x14001b890`
- `0x14002fdc0`
- `0x140033990`
- `0x140033bb0`
- `0x1400382d8`
- `0x14003f760`
- `0x140044160`
- `0x14004b398`
- `0x140077c4c`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0540`
- `0x1401caa00`
- `0x1401d4f80`
- `0x1401fa52c`
- `0x1401fbccc`
- `0x1401fc0a0`
- `0x14035f558`
- `0x1403aee14`
- `0x1403cf470`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1401fbbf2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401fbbf2`
- `ntoskrnl!KeInitializeTimer` at `0x1401fbbb9`
- `ntoskrnl!KeInitializeTimer` at `0x1401fbbb9`
- `ntoskrnl!KeInitializeDpc` at `0x1401fbbd6`
- `ntoskrnl!KeInitializeDpc` at `0x1401fbbd6`
- `ntoskrnl!wcsstr` at `0x1401fa5e3`
- `ntoskrnl!wcsstr` at `0x1401fa5fe`
- `ntoskrnl!wcsstr` at `0x1401fa61f`
- `ntoskrnl!wcsstr` at `0x1401fa5e3`
- `ntoskrnl!wcsstr` at `0x1401fa5fe`
- `ntoskrnl!wcsstr` at `0x1401fa61f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1401fa7ed`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1401fa7ed`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1401fa8be`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1401fa8be`
- `watchdog!WdLogSingleEntry2` at `0x1401fa82f`
- `watchdog!WdLogSingleEntry2` at `0x1401fa987`
- `watchdog!WdLogSingleEntry2` at `0x1401fabfa`
- `watchdog!WdLogSingleEntry2` at `0x1401fac54`
- `watchdog!WdLogSingleEntry2` at `0x1401fac9d`
- `watchdog!WdLogSingleEntry2` at `0x1401fad67`
- `watchdog!WdLogSingleEntry2` at `0x1401fb286`
- `watchdog!WdLogSingleEntry2` at `0x1401fb2c9`
- `watchdog!WdLogSingleEntry2` at `0x1401fb34a`
- `watchdog!WdLogSingleEntry2` at `0x1401fb38d`
- `watchdog!WdLogSingleEntry2` at `0x1401fb3d0`
- `watchdog!WdLogSingleEntry2` at `0x1401fb453`
- `watchdog!WdLogSingleEntry2` at `0x1401fb496`
- `watchdog!WdLogSingleEntry2` at `0x1401fb4d9`
- `watchdog!WdLogSingleEntry2` at `0x1401fb51c`
- `watchdog!WdLogSingleEntry2` at `0x1401fb55f`
- `watchdog!WdLogSingleEntry2` at `0x1401fb5fc`
- `watchdog!WdLogSingleEntry2` at `0x1401fb692`
- `watchdog!WdLogSingleEntry2` at `0x1401fb948`
- `watchdog!WdLogSingleEntry2` at `0x1401fbb6a`
- `watchdog!WdLogSingleEntry2` at `0x1401fbc22`
- `watchdog!WdLogSingleEntry2` at `0x1401fbc54`
- `watchdog!WdLogSingleEntry2` at `0x1401fa82f`
- `watchdog!WdLogSingleEntry2` at `0x1401fa987`
- `watchdog!WdLogSingleEntry2` at `0x1401fabfa`
- `watchdog!WdLogSingleEntry2` at `0x1401fac54`
- `watchdog!WdLogSingleEntry2` at `0x1401fac9d`
- `watchdog!WdLogSingleEntry2` at `0x1401fad67`
- `watchdog!WdLogSingleEntry2` at `0x1401fb286`
- `watchdog!WdLogSingleEntry2` at `0x1401fb2c9`
- `watchdog!WdLogSingleEntry2` at `0x1401fb34a`
- `watchdog!WdLogSingleEntry2` at `0x1401fb38d`
- `watchdog!WdLogSingleEntry2` at `0x1401fb3d0`
- `watchdog!WdLogSingleEntry2` at `0x1401fb453`
- `watchdog!WdLogSingleEntry2` at `0x1401fb496`
- `watchdog!WdLogSingleEntry2` at `0x1401fb4d9`
- `watchdog!WdLogSingleEntry2` at `0x1401fb51c`
- `watchdog!WdLogSingleEntry2` at `0x1401fb55f`
- `watchdog!WdLogSingleEntry2` at `0x1401fb5fc`
- `watchdog!WdLogSingleEntry2` at `0x1401fb692`
- `watchdog!WdLogSingleEntry2` at `0x1401fb948`
- `watchdog!WdLogSingleEntry2` at `0x1401fbb6a`
- `watchdog!WdLogSingleEntry2` at `0x1401fbc22`
- `watchdog!WdLogSingleEntry2` at `0x1401fbc54`
- `watchdog!WdLogSingleEntry3` at `0x1401fa8df`
- `watchdog!WdLogSingleEntry3` at `0x1401fba8b`
- `watchdog!WdLogSingleEntry3` at `0x1401fa8df`
- `watchdog!WdLogSingleEntry3` at `0x1401fba8b`
- `watchdog!WdLogSingleEntry0` at `0x1401faa0b`
- `watchdog!WdLogSingleEntry0` at `0x1401facc1`
- `watchdog!WdLogSingleEntry0` at `0x1401fad16`
- `watchdog!WdLogSingleEntry0` at `0x1401fb306`
- `watchdog!WdLogSingleEntry0` at `0x1401faa0b`
- `watchdog!WdLogSingleEntry0` at `0x1401facc1`
- `watchdog!WdLogSingleEntry0` at `0x1401fad16`
- `watchdog!WdLogSingleEntry0` at `0x1401fb306`
- `watchdog!WdLogSingleEntry1` at `0x1401faf3f`
- `watchdog!WdLogSingleEntry1` at `0x1401faf85`
- `watchdog!WdLogSingleEntry1` at `0x1401fb410`
- `watchdog!WdLogSingleEntry1` at `0x1401fb59f`
- `watchdog!WdLogSingleEntry1` at `0x1401fb646`
- `watchdog!WdLogSingleEntry1` at `0x1401fb6d8`
- `watchdog!WdLogSingleEntry1` at `0x1401fb716`
- `watchdog!WdLogSingleEntry1` at `0x1401fb759`
- `watchdog!WdLogSingleEntry1` at `0x1401fb79e`
- `watchdog!WdLogSingleEntry1` at `0x1401fbb12`
- `watchdog!WdLogSingleEntry1` at `0x1401faf3f`
- `watchdog!WdLogSingleEntry1` at `0x1401faf85`
- `watchdog!WdLogSingleEntry1` at `0x1401fb410`
- `watchdog!WdLogSingleEntry1` at `0x1401fb59f`
- `watchdog!WdLogSingleEntry1` at `0x1401fb646`
- `watchdog!WdLogSingleEntry1` at `0x1401fb6d8`
- `watchdog!WdLogSingleEntry1` at `0x1401fb716`
- `watchdog!WdLogSingleEntry1` at `0x1401fb759`
- `watchdog!WdLogSingleEntry1` at `0x1401fb79e`
- `watchdog!WdLogSingleEntry1` at `0x1401fbb12`

## string_xrefs

- `0x1401faccf`: `GpuMmu.PageDirectoryCount is invalid. It should be from 2 to DXGK_MAX_PAGE_TABLE_LEVEL_COUNT\n`
- `0x1401faca9`: `Adapter 0x%I64x: Failed to query page table level descriptor, returning 0x%I64x`
- `0x1401fb959`: `Adapter 0x%I64x: CreateSynchronizationObjectInternal failed. Returning 0x%I64x`

## pseudocode

```c
__int64 __fastcall ADAPTER_RENDER::Initialize(ADAPTER_RENDER *this)
{
  unsigned int v2; // r13d
  __int64 v3; // rcx
  __int64 v4; // rcx
  wchar_t *v5; // rax
  wchar_t *v6; // rax
  __int64 v7; // rdx
  _OWORD *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  unsigned int v13; // r15d
  unsigned int VidSchSibmitDataSize; // eax
  __int64 result; // rax
  DXGADAPTER *v16; // rcx
  unsigned __int8 IsDxgmms2; // bl
  __int64 v18; // rdx
  const wchar_t *v19; // r9
  unsigned int *v20; // rbx
  unsigned __int64 v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rax
  unsigned int v24; // r13d
  unsigned int v25; // r14d
  unsigned int i; // r12d
  DXGADAPTER *v27; // rcx
  int v28; // ecx
  unsigned int j; // r14d
  DXGADAPTER *v30; // rcx
  unsigned int v31; // eax
  unsigned int k; // edx
  __int64 v33; // rax
  unsigned int v34; // r12d
  DXGADAPTER *v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // r8
  unsigned __int16 *v38; // r13
  unsigned __int64 v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // r15
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  int *v47; // rcx
  int v48; // eax
  DXGADAPTER *v49; // rcx
  unsigned int n; // r12d
  struct _DXGK_NODEMETADATA *v51; // r15
  __int64 v52; // r14
  __int64 v53; // rdx
  struct _DXGK_NODEMETADATA_FLAGS::$61C199033D6F6D75DA69F8EFC79E2D37::$C26580DEFEF05BED1260633B1DAE4A38 Value; // eax
  _DWORD *v55; // rcx
  DXGADAPTER *v56; // rcx
  __int128 v57; // xmm1
  int v58; // eax
  __int64 v59; // rbx
  struct DXGGLOBAL *Global; // rax
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // rdx
  int SynchronizationObjectInternal; // eax
  int *v66; // rcx
  unsigned int NumDifferentPhysicalAdapters; // ebx
  __int64 m; // rcx
  unsigned int v69; // r12d
  __int64 v70; // rax
  _DWORD *v71; // rax
  _DWORD *v72; // r14
  unsigned int *v73; // rax
  DXGADAPTER *v74; // rcx
  char v75; // dl
  __int64 v76; // r15
  unsigned int v77; // ecx
  __int64 v78; // rbx
  const wchar_t *v79; // r9
  unsigned int v80; // [rsp+50h] [rbp-B0h] BYREF
  char v81; // [rsp+54h] [rbp-ACh]
  unsigned int AdapterInfo; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v83[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  int v84; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v85; // [rsp+68h] [rbp-98h]
  _WORD v86[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v87; // [rsp+78h] [rbp-88h]
  unsigned int v88; // [rsp+80h] [rbp-80h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v89[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v90; // [rsp+F0h] [rbp-10h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v91; // [rsp+120h] [rbp+20h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v92; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v93[2]; // [rsp+180h] [rbp+80h] BYREF
  wchar_t Str[264]; // [rsp+1A0h] [rbp+A0h] BYREF

  v2 = 0;
  v3 = *((_QWORD *)this + 2);
  *((_OWORD *)this + 34) = *(_OWORD *)(v3 + 1904);
  *((_OWORD *)this + 35) = *(_OWORD *)(v3 + 1936);
  *((_OWORD *)this + 36) = *(_OWORD *)(v3 + 1952);
  *((_OWORD *)this + 37) = *(_OWORD *)(v3 + 1920);
  if ( *((_WORD *)this + 296) )
  {
    v4 = *(_QWORD *)(v3 + 216);
    AdapterInfo = 520;
    if ( (int)DpiGetDriverStorePath(v4, Str, &AdapterInfo) >= 0 )
    {
      v5 = wcsstr(Str, L"FileRepository");
      if ( v5 )
      {
        v6 = wcsstr(v5, L"\\");
        if ( v6 )
        {
          if ( v6 != (wchar_t *)-2LL && !wcsstr(*((const wchar_t **)this + 75), v6 + 1) )
          {
            if ( *((_WORD *)this + 280) )
            {
              *((_WORD *)this + 280) = 0;
              *((_QWORD *)this + 71) = 0;
            }
            if ( *((_WORD *)this + 288) )
            {
              *((_WORD *)this + 288) = 0;
              *((_QWORD *)this + 73) = 0;
            }
            *((_WORD *)this + 296) = 0;
            *((_QWORD *)this + 75) = 0;
          }
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 2);
  v8 = (_OWORD *)((char *)this + 320);
  *((_OWORD *)this + 38) = *(_OWORD *)(v7 + 2048);
  *((_OWORD *)this + 39) = *(_OWORD *)(v7 + 2064);
  *((_OWORD *)this + 42) = *(_OWORD *)(v7 + 1984);
  *(_OWORD *)((char *)this + 696) = *(_OWORD *)(v7 + 2008);
  *((_DWORD *)this + 172) = *(_DWORD *)(v7 + 2000);
  *((_DWORD *)this + 173) = *(_DWORD *)(v7 + 2004);
  *((_DWORD *)this + 178) = *(_DWORD *)(v7 + 2024);
  *((_DWORD *)this + 179) = *(_DWORD *)(v7 + 2028);
  *((_OWORD *)this + 40) = *(_OWORD *)(v7 + 2080);
  *((_OWORD *)this + 41) = *(_OWORD *)(v7 + 2096);
  if ( (int)ADAPTER_RENDER::InitializeUserModeDriverNames(
              this,
              (struct _UNICODE_STRING *)(v7 + 1864),
              (struct _UNICODE_STRING *)this + 20) < 0
    || (int)ADAPTER_RENDER::InitializeUserModeDriverNames(
              this,
              (struct _UNICODE_STRING *)(*((_QWORD *)this + 2) + 1880LL),
              (struct _UNICODE_STRING *)this + 26) < 0 )
  {
    v12 = -1073741438;
    WdLogSingleEntry2(2, *((_QWORD *)this + 2));
    v79 = L"Adapter 0x%I64x: Invalidly formatted user mode driver name, returning 0x%I64x";
    WdLogGlobalForLineNumber = 932;
    goto LABEL_205;
  }
  if ( (int)ADAPTER_RENDER::InitializeDisplayUserModeDriverNames(
              this,
              (struct _UNICODE_STRING *)(*((_QWORD *)this + 2) + 2176LL),
              (struct _UNICODE_STRING *)this + 32) < 0
    || (int)ADAPTER_RENDER::InitializeDisplayUserModeDriverNames(
              this,
              (struct _UNICODE_STRING *)(*((_QWORD *)this + 2) + 2192LL),
              (struct _UNICODE_STRING *)this + 33) < 0 )
  {
    v12 = -1073741438;
    WdLogSingleEntry2(2, *((_QWORD *)this + 2));
    v79 = L"Adapter 0x%I64x: Invalidly formatted user mode display driver name, returning 0x%I64x";
    WdLogGlobalForLineNumber = 965;
LABEL_205:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v79, *((_QWORD *)this + 2), -1073741438, 0, 0, 0);
    return v12;
  }
  if ( *(_WORD *)v8 )
  {
    if ( **((_WORD **)this + 41) == 35 )
    {
      v9 = *((_QWORD *)this + 2);
      if ( *(_WORD *)(v9 + 2136) )
        *v8 = *(_OWORD *)(v9 + 2136);
    }
  }
  if ( *((_WORD *)this + 208) )
  {
    if ( **((_WORD **)this + 53) == 35 )
    {
      v10 = *((_QWORD *)this + 2);
      if ( *(_WORD *)(v10 + 2152) )
        *((_OWORD *)this + 26) = *(_OWORD *)(v10 + 2152);
    }
  }
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)this + 173);
  v11 = *((_QWORD *)this + 2);
  if ( !*(_BYTE *)(v11 + 209) && !*((_WORD *)this + 160) && (*(_DWORD *)(v11 + 3088) & 8) == 0 )
  {
    v12 = -1073741438;
    WdLogSingleEntry2(2, *((_QWORD *)this + 2));
    WdLogGlobalForLineNumber = 982;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Adapter 0x%I64x: Invalid user mode driver name, returning 0x%I64x",
      *((_QWORD *)this + 2),
      -1073741438,
      0,
      0,
      0);
    return v12;
  }
  v13 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 216) + 64LL) + 40LL) + 28LL);
  AdapterInfo = v13;
  VidSchSibmitDataSize = ADAPTER_RENDER::GetVidSchSibmitDataSize(this);
  if ( ExInitializeLookasideListEx(
         (PLOOKASIDE_LIST_EX)((char *)this + 1424),
         0,
         0,
         (POOL_TYPE)512,
         0,
         VidSchSibmitDataSize,
         0x4B677844u,
         0) < 0 )
  {
    WdLogSingleEntry3(3, this, -1073741801, 0);
    result = 3221225495LL;
    WdLogGlobalForLineNumber = 992;
    return result;
  }
  *((_BYTE *)this + 1369) = 1;
  v83[1] = 0;
  DXGCRITICALREGION::Enter((DXGCRITICALREGION *)v83);
  v16 = (DXGADAPTER *)*((_QWORD *)this + 2);
  if ( !*((_BYTE *)v16 + 209) )
  {
    IsDxgmms2 = DXGADAPTER::IsDxgmms2(v16);
    *((_QWORD *)this + 95) = *(_QWORD *)((char *)DXGGLOBAL::GetGlobal() + (IsDxgmms2 != 0 ? 8 : 0) + 264);
    v18 = *(_QWORD *)((char *)DXGGLOBAL::GetGlobal() + (IsDxgmms2 != 0 ? 8 : 0) + 280);
    *((_QWORD *)this + 92) = v18;
    if ( !*((_QWORD *)this + 95) || !v18 )
    {
      v12 = -1073741438;
      WdLogSingleEntry2(2, this);
      v19 = L"Adapter 0x%I64x: Unsupported display driver model, returning 0x%I64x";
      WdLogGlobalForLineNumber = 1021;
LABEL_70:
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v19, (__int64)this, -1073741438, 0, 0, 0);
      goto LABEL_40;
    }
  }
  v20 = (unsigned int *)*((_QWORD *)this + 2);
  if ( DXGADAPTER::IsGpuVirtualAddressingSupported((DXGADAPTER *)v20) )
  {
    v21 = v20[74];
    v22 = 144 * v21;
    v84 = v21;
    if ( !is_mul_ok(v21, 0x90u) )
      v22 = -1;
    v23 = operator new[](v22, 1265072196, 256);
    *((_QWORD *)this + 158) = v23;
    if ( !v23 )
    {
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 1036;
      DxgkLogInternalTriageEvent(0, 262145, -1, (unsigned int)L"Failed to allocate m_pGpuMmuCaps", 1036, 0, 0, 0, 0);
LABEL_39:
      v12 = -1073741801;
      goto LABEL_40;
    }
    v24 = 63;
    v25 = 0;
    v80 = 0;
    for ( i = 0; i < (unsigned int)v21; ++i )
    {
      v27 = (DXGADAPTER *)*((_QWORD *)this + 2);
      v21 = *((_QWORD *)this + 158) + 144LL * i;
      if ( (*((_DWORD *)v27 + 645) & 0x40) != 0 )
      {
        *(_QWORD *)&v90.Type = 13;
        v90.pInputData = &v88;
        *(_QWORD *)&v90.InputDataSize = 4;
        *(_QWORD *)&v90.Flags.0 = 0;
        HIDWORD(v90.hKmdProcessHandle) = 0;
        v90.pOutputData = (void *)v21;
        v90.OutputDataSize = 24;
        v88 = i;
        if ( (int)DXGADAPTER::DdiQueryAdapterInfo(v27, &v90) < 0 )
        {
          v12 = -1073741438;
          WdLogSingleEntry2(2, this);
          v19 = L"Adapter 0x%I64x: Failed to query GpuMmu caps, returning 0x%I64x";
          WdLogGlobalForLineNumber = 1065;
        }
        else
        {
          v28 = *(_DWORD *)(v21 + 8);
          if ( v25 )
          {
            if ( v28 != v25 )
            {
              WdLogSingleEntry0(2);
              WdLogGlobalForLineNumber = 1083;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"Virtual address bit count must be the same on all physical adapters",
                1083,
                0,
                0,
                0,
                0);
              goto LABEL_64;
            }
          }
          else
          {
            if ( (unsigned int)(v28 - 13) > 0x32 )
            {
              WdLogSingleEntry2(2, 12);
              WdLogGlobalForLineNumber = 1075;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"GpuMmu.VirtualAddressBitCount is invalid. It should be from %d to %d",
                12,
                63,
                0,
                0,
                0);
              goto LABEL_64;
            }
            v80 = *(_DWORD *)(v21 + 8);
          }
          if ( (unsigned int)(*(_DWORD *)(v21 + 16) - 2) > 4 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 1091;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"GpuMmu.PageDirectoryCount is invalid. It should be from 2 to DXGK_MAX_PAGE_TABLE_LEVEL_COUNT\n",
              1091,
              0,
              0,
              0,
              0);
            v12 = -1073741438;
            goto LABEL_40;
          }
          if ( v13 < 0x5014 )
            *(_DWORD *)v21 &= ~0x20u;
          for ( j = 0; ; ++j )
          {
            if ( j >= *(_DWORD *)(v21 + 16) )
            {
              v25 = v80;
              v13 = AdapterInfo;
              goto LABEL_59;
            }
            v91.pInputData = v86;
            v30 = (DXGADAPTER *)*((_QWORD *)this + 2);
            *(_QWORD *)&v91.Type = 14;
            *(_QWORD *)&v91.InputDataSize = 4;
            v91.hKmdProcessHandle = 0;
            v86[0] = j;
            v86[1] = i;
            v87 = (_DWORD *)(v21 + 4 * (j + 4LL * j + 6));
            v91.pOutputData = v87;
            *(_QWORD *)&v91.OutputDataSize = AdapterInfo < 0x5012 ? 16 : 20;
            if ( (int)DXGADAPTER::DdiQueryAdapterInfo(v30, &v91) < 0 )
              break;
            if ( ((v87[4] - 1) & v87[4]) != 0 )
            {
              WdLogSingleEntry2(2, this);
              WdLogGlobalForLineNumber = 1143;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"Adapter 0x%I64x: Page table alignment of level %d must be power of 2",
                (__int64)this,
                j,
                0,
                0,
                0);
              goto LABEL_64;
            }
          }
          v12 = -1073741438;
          WdLogSingleEntry2(2, this);
          v19 = L"Adapter 0x%I64x: Failed to query page table level descriptor, returning 0x%I64x";
          WdLogGlobalForLineNumber = 1138;
        }
        goto LABEL_70;
      }
      *(_DWORD *)(v21 + 8) = 63;
LABEL_59:
      v31 = *(_DWORD *)(v21 + 8);
      LODWORD(v21) = v84;
      if ( v24 >= v31 )
        v24 = v31;
    }
    for ( k = 0; k < (unsigned int)v21; *(_DWORD *)(*((_QWORD *)this + 158) + 144 * v33 + 8) = v24 )
      v33 = k++;
    v2 = 0;
  }
  if ( *(int *)(*((_QWORD *)this + 2) + 2848LL) < 4864 )
    goto LABEL_163;
  v34 = 0;
  while ( 2 )
  {
    v35 = (DXGADAPTER *)*((_QWORD *)this + 2);
    v80 = v34;
    if ( v34 >= DXGADAPTER::GetNumDifferentPhysicalAdapters(v35) )
    {
      if ( *(int *)(v36 + 2848) < 8960 )
        *(_DWORD *)(v36 + 2576) &= 0xFFFFF87F;
LABEL_163:
      v58 = DXGADAPTER::CheckMcdmDdiSubmission(*((DXGADAPTER **)this + 2));
      if ( v58 < 0 )
      {
LABEL_164:
        v12 = v58;
        goto LABEL_40;
      }
      if ( !*(_BYTE *)(*((_QWORD *)this + 2) + 209LL) )
      {
        v80 = 0;
        v58 = ADAPTER_RENDER::ConfigureSysMm(this, (union SYSMM_IOMMU_STATE *)&v80);
        if ( v58 < 0 )
          goto LABEL_164;
        v59 = *((_QWORD *)this + 92);
        Global = DXGGLOBAL::GetGlobal();
        v61 = (*(__int64 (__fastcall **)(ADAPTER_RENDER *, _QWORD, __int64))(*(_QWORD *)(v59 + 8) + 24LL))(
                this,
                *(_QWORD *)(*((_QWORD *)this + 2) + 216LL),
                (__int64)Global + 152);
        *((_QWORD *)this + 93) = v61;
        if ( !v61 )
          goto LABEL_39;
        v62 = 0;
        if ( (v80 & 1) != 0 )
        {
          v62 = 1;
          if ( (v80 & 2) != 0 )
            v62 = 3;
        }
        v63 = (*(__int64 (__fastcall **)(ADAPTER_RENDER *, __int64))(*(_QWORD *)(*((_QWORD *)this + 95) + 8LL) + 8LL))(
                this,
                v62);
        *((_QWORD *)this + 96) = v63;
        if ( !v63 )
          goto LABEL_39;
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(*((_QWORD *)this + 92) + 8LL) + 32LL))(
          *((_QWORD *)this + 93),
          v63);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 95) + 8LL) + 16LL))(
          *((_QWORD *)this + 96),
          *((_QWORD *)this + 93));
      }
      memset(v89, 0, sizeof(v89));
      LOBYTE(v64) = 1;
      v89[0].pInputData = (void *)0x100000003LL;
      SynchronizationObjectInternal = CreateSynchronizationObjectInternal(
                                        0,
                                        v64,
                                        this,
                                        v89,
                                        11,
                                        0,
                                        (char *)this + 904,
                                        0,
                                        0);
      v52 = SynchronizationObjectInternal;
      if ( SynchronizationObjectInternal < 0 )
      {
        WdLogSingleEntry2(2, this);
        WdLogGlobalForLineNumber = 1509;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Adapter 0x%I64x: CreateSynchronizationObjectInternal failed. Returning 0x%I64x",
          (__int64)this,
          v52,
          0,
          0,
          0);
LABEL_153:
        v12 = v52;
        goto LABEL_40;
      }
      v66 = (int *)*((_QWORD *)this + 2);
      if ( v66[712] < 4864 )
        goto LABEL_202;
      NumDifferentPhysicalAdapters = DXGADAPTER::GetNumDifferentPhysicalAdapters((DXGADAPTER *)v66);
      LODWORD(v85) = NumDifferentPhysicalAdapters;
      v80 = 0;
      for ( m = 0; ; m = ++v80 )
      {
        if ( (unsigned int)m >= NumDifferentPhysicalAdapters )
        {
          if ( ADAPTER_RENDER::IsClockCalibrationSupported(this) )
          {
            *((_QWORD *)this + 129) = -500000;
            KeInitializeTimer((PKTIMER)((char *)this + 1040));
            KeInitializeDpc((PRKDPC)((char *)this + 1104), DxgkpCalibrateGpuTimerDpc, this);
          }
          if ( *((_BYTE *)this + 968) )
            KeInitializeSpinLock((PKSPIN_LOCK)this + 157);
LABEL_202:
          DXGCRITICALREGION::~DXGCRITICALREGION((DXGCRITICALREGION *)v83);
          return 0;
        }
        v69 = *(unsigned __int16 *)(352 * m + *(_QWORD *)(*((_QWORD *)this + 2) + 3104LL));
        v70 = 4LL * *(unsigned __int16 *)(352 * m + *(_QWORD *)(*((_QWORD *)this + 2) + 3104LL));
        if ( !is_mul_ok(*(unsigned __int16 *)(352 * m + *(_QWORD *)(*((_QWORD *)this + 2) + 3104LL)), 4u) )
          v70 = -1;
        v71 = (_DWORD *)operator new[](v70, 1265072196, 64);
        v72 = v71;
        if ( !v71 )
          goto LABEL_39;
        v84 = v80;
        v89[0].pOutputData = v71;
        v89[0].OutputDataSize = 4 * v69;
        v73 = &v80;
        v74 = (DXGADAPTER *)*((_QWORD *)this + 2);
        if ( NumDifferentPhysicalAdapters <= 1 )
          v73 = (unsigned int *)&v84;
        *(_QWORD *)&v89[0].Type = 10;
        *(_QWORD *)&v89[0].InputDataSize = 4;
        *(_QWORD *)&v89[0].Flags.0 = 0;
        HIDWORD(v89[0].hKmdProcessHandle) = 0;
        v89[0].pInputData = v73;
        AdapterInfo = DXGADAPTER::DdiQueryAdapterInfo(v74, v89);
        if ( (AdapterInfo & 0x80000000) != 0 )
          goto LABEL_193;
        v75 = 1;
        if ( !v69 )
        {
          v2 = 0;
          goto LABEL_196;
        }
        v76 = 0;
        do
        {
          v77 = v72[v76];
          if ( v77 - 1 <= 0x1E || v77 >= 0x41 )
          {
            v78 = (unsigned int)v72[v76];
            WdLogSingleEntry3(2, this, v78, v76);
            WdLogGlobalForLineNumber = 1557;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Adapter 0x%I64x: Invalid timestamp precision. Valid domain is {0, [32-64]}. Precision=%d, Node=%d",
              (__int64)this,
              v78,
              v76,
              0,
              0);
            v75 = 0;
          }
          else if ( !v77 )
          {
            *((_BYTE *)this + 968) = 1;
          }
          ++v2;
          ++v76;
        }
        while ( v2 < v69 );
        v2 = 0;
        if ( !v75 )
        {
LABEL_193:
          DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v72);
          *((_BYTE *)this + 968) = 0;
          if ( (AdapterInfo & 0x80000000) == 0 )
          {
            v12 = -1073741438;
            WdLogSingleEntry2(2, this);
            v19 = L"Adapter 0x%I64x: Precision data is bad. Returning 0x%I64x";
            WdLogGlobalForLineNumber = 1597;
            goto LABEL_70;
          }
          v72 = 0;
          WdLogSingleEntry1(4);
          WdLogGlobalForLineNumber = 1589;
        }
LABEL_196:
        NumDifferentPhysicalAdapters = v85;
        *(_QWORD *)(352LL * v80 + *(_QWORD *)(*((_QWORD *)this + 2) + 3104LL) + 40) = v72;
      }
    }
    v38 = (unsigned __int16 *)(*(_QWORD *)(v36 + 3104) + 352LL * v34);
    AdapterInfo = *v38;
    v39 = AdapterInfo;
    v40 = 74LL * AdapterInfo;
    if ( !is_mul_ok(AdapterInfo, 0x4Au) )
      v40 = v37;
    v41 = operator new[](v40, 1265072196, 256);
    v85 = v41;
    v42 = v41;
    if ( !v41 )
    {
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 1187;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"Adapter 0x%I64x: Failed to allocate pNodeMetadata",
        (__int64)this,
        0,
        0,
        0,
        0);
      goto LABEL_39;
    }
    *((_QWORD *)v38 + 4) = v41;
    v87 = (_DWORD *)*((_QWORD *)this + 2);
    v43 = 44 * v39;
    if ( !is_mul_ok(v39, 0x2Cu) )
      v43 = -1;
    v44 = operator new[](v43, 1265072196, 256);
    if ( !v44 )
    {
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 1198;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"Adapter 0x%I64x: Failed to allocate pNodePerfData",
        (__int64)this,
        0,
        0,
        0,
        0);
      goto LABEL_39;
    }
    *((_QWORD *)v38 + 13) = v44;
    v45 = 8 * v39;
    if ( !is_mul_ok(v39, 8u) )
      v45 = -1;
    v46 = operator new[](v45, 1265072196, 256);
    if ( !v46 )
    {
      WdLogSingleEntry1(6);
      WdLogGlobalForLineNumber = 1208;
      DxgkLogInternalTriageEvent(
        0,
        262145,
        -1,
        (unsigned int)L"Adapter 0x%I64x: Failed to allocate pNodePerfDataQueryTimes",
        (__int64)this,
        0,
        0,
        0,
        0);
      goto LABEL_39;
    }
    *((_QWORD *)v38 + 14) = v46;
    v47 = (int *)*((_QWORD *)this + 2);
    if ( v47[779] >= 2400 )
    {
      v84 = v34;
      v89[0].pInputData = &v84;
      *(_QWORD *)&v89[0].Type = 26;
      v89[0].pOutputData = v38 + 92;
      *(_QWORD *)&v89[0].InputDataSize = 4;
      *(_QWORD *)&v89[0].Flags.0 = 0;
      HIDWORD(v89[0].hKmdProcessHandle) = 0;
      v89[0].OutputDataSize = 28;
      v48 = DXGADAPTER::DdiQueryAdapterInfo((DXGADAPTER *)v47, v89);
      if ( (int)(v48 + 0x80000000) >= 0 && v48 != -1073741637 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1229;
      }
      v49 = (DXGADAPTER *)*((_QWORD *)this + 2);
      v89[0].pOutputData = v38 + 106;
      v89[0].Type = DXGKQAITYPE_GPUVERSION;
      v89[0].OutputDataSize = 128;
      if ( (int)DXGADAPTER::DdiQueryAdapterInfo(v49, v89) < 0 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 1239;
      }
    }
    v81 = 0;
    for ( n = 0; n < AdapterInfo; ++n )
    {
      v51 = (struct _DXGK_NODEMETADATA *)(74LL * n + v42);
      LODWORD(v52) = DXGADAPTER::DdiGetNodeMetadata(*((DXGADAPTER **)this + 2), n | (v80 << 16), v51);
      if ( (int)v52 < 0 )
      {
        WdLogSingleEntry1(2);
        WdLogGlobalForLineNumber = 1250;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Adapter 0x%I64x: Driver reported failure getting node metadata with valid parameters.",
          (__int64)this,
          0,
          0,
          0,
          0);
        goto LABEL_153;
      }
      v53 = *((_QWORD *)this + 2);
      if ( *(_DWORD *)(v53 + 2392) < 0x9000u )
      {
        v51->Flags.Value = 0;
        v42 = v85;
        goto LABEL_115;
      }
      if ( (*(_BYTE *)&v51->Flags.0 & 1) != 0 )
      {
        if ( !v51->IoMmuSupported && !*((_BYTE *)v38 + 49) )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 1267;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x, Node 0x%I64x: Driver reported ContextScheduling support for a node, but it do"
                           "esn't support GPU VA.",
            (__int64)this,
            n,
            0,
            0,
            0);
          goto LABEL_64;
        }
        if ( (**(_DWORD **)(v53 + 3120) & 0x20000) == 0 )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 1273;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x, Node 0x%I64x: Driver reported ContextScheduling support for a node, but the O"
                           "S didn't allow HwSch to be enabled.",
            (__int64)this,
            n,
            0,
            0,
            0);
          goto LABEL_64;
        }
        *((_BYTE *)this + 1880) = 1;
      }
      Value = (struct _DXGK_NODEMETADATA_FLAGS::$61C199033D6F6D75DA69F8EFC79E2D37::$C26580DEFEF05BED1260633B1DAE4A38)v51->Flags.Value;
      if ( (*(_BYTE *)&Value & 8) != 0 )
      {
        if ( *(int *)(v53 + 3116) < 3100 )
        {
          WdLogSingleEntry1(2);
          WdLogGlobalForLineNumber = 1285;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x: UserModeSubmission is only supported on WDDM3.1 and above.",
            (__int64)this,
            0,
            0,
            0,
            0);
          goto LABEL_64;
        }
        if ( (*(_BYTE *)&Value & 1) == 0 )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 1291;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x, Node 0x%I64x: Driver reported UserModeSubmission support for a node which doe"
                           "sn't support ContextScheduling.",
            (__int64)this,
            n,
            0,
            0,
            0);
          goto LABEL_64;
        }
        if ( (**(_DWORD **)(v53 + 3120) & 0x8000000) == 0 )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 1297;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x, Node 0x%I64x: Driver reported UserModeSubmission support, but the OS didn't a"
                           "llow UserModeSubmission to be enabled.",
            (__int64)this,
            n,
            0,
            0,
            0);
          goto LABEL_64;
        }
        if ( (v87[644] & 0x800) == 0 )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 1303;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x, Node 0x%I64x: Driver reported UserModeSubmission support, but NativeGpuFence cap is not set.",
            (__int64)this,
            n,
            0,
            0,
            0);
          goto LABEL_64;
        }
        if ( !*(_QWORD *)(v53 + 1528)
          || !*(_QWORD *)(v53 + 1552)
          || !*(_QWORD *)(v53 + 1536)
          || !*(_QWORD *)(v53 + 1544)
          || !*(_QWORD *)(v53 + 1560) )
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 1315;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Driver reports UserModeSubmission support, but does not support all relevant Doorbell DDIs.",
            1315,
            0,
            0,
            0,
            0);
          goto LABEL_64;
        }
        v81 = 1;
LABEL_113:
        v42 = v85;
        goto LABEL_114;
      }
      if ( !*((_BYTE *)DXGGLOBAL::GetGlobal() + 305952) )
        goto LABEL_113;
      v42 = v85;
      if ( (*(_BYTE *)(74LL * n + v85 + 68) & 1) != 0 )
      {
        *((_DWORD *)this + 318) |= 1u;
        *((_DWORD *)this + 319) = 512;
        *((_DWORD *)this + 320) = 512;
      }
LABEL_114:
      if ( (*(_DWORD *)(74LL * n + v42 + 68) & 0xFFC0) != 0 )
      {
        WdLogSingleEntry2(2, this);
        WdLogGlobalForLineNumber = 1335;
        DxgkLogInternalTriageEvent(
          0,
          0x40000,
          -1,
          (unsigned int)L"Adapter 0x%I64x, Node 0x%I64x: Driver should not set reserved bits.",
          (__int64)this,
          n,
          0,
          0,
          0);
        goto LABEL_64;
      }
LABEL_115:
      v55 = v87;
      if ( *(_BYTE *)(74LL * n + v42 + 72) )
      {
        if ( (v87[645] & 0x40) == 0 )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 1344;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x, Node 0x%I64x: Driver reported GpuMmu support for a node, but the adapter caps do not match.",
            (__int64)this,
            n,
            0,
            0,
            0);
          goto LABEL_64;
        }
        if ( (*((_DWORD *)v38 + 4) & 0xC0) != 0 )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 1349;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x, Node 0x%I64x: Driver set GpuMmuSupported, but adapter requires GpuVaIoMmu",
            (__int64)this,
            n,
            0,
            0,
            0);
          goto LABEL_64;
        }
        if ( n == v38[1] && !*(_BYTE *)(*((_QWORD *)this + 2) + 3153LL) )
          *((_BYTE *)v38 + 48) = 1;
        *((_BYTE *)v38 + 49) = 1;
      }
      if ( *(_BYTE *)(74LL * n + v42 + 73) )
      {
        if ( (v55[645] & 0x80u) == 0 )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 1363;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x, Node 0x%I64x: Driver reported IoMmu support for a node, but the adapter caps do not match.",
            (__int64)this,
            n,
            0,
            0,
            0);
          goto LABEL_64;
        }
        if ( (*((_DWORD *)v38 + 4) & 0xC0) != 0 )
        {
          WdLogSingleEntry2(2, this);
          WdLogGlobalForLineNumber = 1368;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Adapter 0x%I64x, Node 0x%I64x: Driver set IoMmuSupported, but adapter requires GpuVaIoMmu",
            (__int64)this,
            n,
            0,
            0,
            0);
          goto LABEL_64;
        }
        if ( n == v38[1] && !*(_BYTE *)(*((_QWORD *)this + 2) + 3153LL) )
          *((_BYTE *)v38 + 48) = 1;
      }
    }
    v2 = 0;
    if ( !v81 )
    {
LABEL_139:
      v34 = v80 + 1;
      continue;
    }
    break;
  }
  v56 = (DXGADAPTER *)*((_QWORD *)this + 2);
  memset(v93, 0, 28);
  memset(&v92, 0, 24);
  v92.Type = DXGKQAITYPE_NUMPOWERCOMPONENTS|0x20;
  v92.pOutputData = v93;
  *(_OWORD *)&v92.OutputDataSize = 0;
  v92.OutputDataSize = 28;
  v12 = DXGADAPTER::DdiQueryAdapterInfo(v56, &v92);
  if ( (v12 & 0x80000000) != 0 )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 1389;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Adapter 0x%I64x: Driver reported failure getting User mode submission Caps.",
      (__int64)this,
      0,
      0,
      0,
      0);
  }
  else
  {
    if ( (unsigned int)(DWORD1(v93[0]) - 1) > 0xFFF )
    {
      WdLogSingleEntry2(2, DWORD1(v93[0]));
      WdLogGlobalForLineNumber = 1397;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DoorbellSize (0x%u) must be greater than 0 and less than 0x%u.",
        DWORD1(v93[0]),
        4096,
        0,
        0,
        0);
    }
    else if ( (v93[0] & 0xFFFFFFFE) != 0 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 1404;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DXGKQAITYPE_USERMODESUBMISSION_CAPS: Driver should not set reserved bits, returning 0x%I64x.",
        -1073741811,
        0,
        0,
        0,
        0);
    }
    else
    {
      if ( (v93[0] & 1) == 0 || (unsigned int)(DWORD2(v93[0]) - 1) <= 0xFFF )
      {
        v57 = *(_OWORD *)((char *)v93 + 12);
        *(_OWORD *)((char *)this + 1272) = v93[0];
        *(_OWORD *)((char *)this + 1284) = v57;
        goto LABEL_139;
      }
      WdLogSingleEntry2(2, DWORD2(v93[0]));
      WdLogGlobalForLineNumber = 1414;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"SecondaryDoorbellSize (0x%u) must be greater than 0 and less than 0x%u.",
        DWORD2(v93[0]),
        4096,
        0,
        0,
        0);
    }
LABEL_64:
    v12 = -1073741811;
  }
LABEL_40:
  DXGCRITICALREGION::~DXGCRITICALREGION((DXGCRITICALREGION *)v83);
  return v12;
}

```

## disassembly

```asm
0x1401fa52c  push    rbp
0x1401fa52e  push    rbx
0x1401fa52f  push    rsi
0x1401fa530  push    rdi
0x1401fa531  push    r12
0x1401fa533  push    r13
0x1401fa535  push    r14
0x1401fa537  push    r15
0x1401fa539  lea     rbp, [rsp-2C8h]
0x1401fa541  sub     rsp, 3C8h
0x1401fa548  mov     rax, cs:__security_cookie
0x1401fa54f  xor     rax, rsp
0x1401fa552  mov     [rbp+300h+var_50], rax
0x1401fa559  mov     rdi, rcx
0x1401fa55c  xor     r13d, r13d
0x1401fa55f  mov     rcx, [rcx+10h]
0x1401fa563  movups  xmm0, xmmword ptr [rcx+770h]
0x1401fa56a  movdqu  xmmword ptr [rdi+220h], xmm0
0x1401fa572  movups  xmm1, xmmword ptr [rcx+790h]
0x1401fa579  movdqu  xmmword ptr [rdi+230h], xmm1
0x1401fa581  movups  xmm0, xmmword ptr [rcx+7A0h]
0x1401fa588  movdqu  xmmword ptr [rdi+240h], xmm0
0x1401fa590  movups  xmm1, xmmword ptr [rcx+780h]
0x1401fa597  movdqu  xmmword ptr [rdi+250h], xmm1
0x1401fa59f  cmp     [rdi+250h], r13w
0x1401fa5a7  jz      loc_1401FA671
0x1401fa5ad  mov     rcx, [rcx+0D8h]
0x1401fa5b4  lea     r8, [rsp+400h+var_3A8]
0x1401fa5b9  lea     rdx, [rbp+300h+Str]
0x1401fa5c0  mov     [rsp+400h+var_3A8], 208h
0x1401fa5c8  call    DpiGetDriverStorePath
0x1401fa5cd  test    eax, eax
0x1401fa5cf  js      loc_1401FA671
0x1401fa5d5  lea     rdx, aFilerepository_0; "FileRepository"
0x1401fa5dc  lea     rcx, [rbp+300h+Str]; Str
0x1401fa5e3  call    cs:__imp_wcsstr
0x1401fa5ea  nop     dword ptr [rax+rax+00h]
0x1401fa5ef  test    rax, rax
0x1401fa5f2  jz      short loc_1401FA671
0x1401fa5f4  lea     rdx, Source; "\\"
0x1401fa5fb  mov     rcx, rax; Str
0x1401fa5fe  call    cs:__imp_wcsstr
0x1401fa605  nop     dword ptr [rax+rax+00h]
0x1401fa60a  test    rax, rax
0x1401fa60d  jz      short loc_1401FA671
0x1401fa60f  lea     rdx, [rax+2]; SubStr
0x1401fa613  test    rdx, rdx
0x1401fa616  jz      short loc_1401FA671
0x1401fa618  mov     rcx, [rdi+258h]; Str
0x1401fa61f  call    cs:__imp_wcsstr
0x1401fa626  nop     dword ptr [rax+rax+00h]
0x1401fa62b  test    rax, rax
0x1401fa62e  jnz     short loc_1401FA671
0x1401fa630  cmp     [rdi+230h], r13w
0x1401fa638  jz      short loc_1401FA649
0x1401fa63a  mov     [rdi+230h], r13w
0x1401fa642  mov     [rdi+238h], r13
0x1401fa649  cmp     [rdi+240h], r13w
0x1401fa651  jz      short loc_1401FA662
0x1401fa653  mov     [rdi+240h], r13w
0x1401fa65b  mov     [rdi+248h], r13
0x1401fa662  mov     [rdi+250h], r13w
0x1401fa66a  mov     [rdi+258h], r13
0x1401fa671  mov     rdx, [rdi+10h]
0x1401fa675  lea     rbx, [rdi+140h]
0x1401fa67c  mov     r8, rbx; struct _UNICODE_STRING *
0x1401fa67f  mov     rcx, rdi; this
0x1401fa682  movups  xmm0, xmmword ptr [rdx+800h]
0x1401fa689  movdqu  xmmword ptr [rdi+260h], xmm0
0x1401fa691  movups  xmm1, xmmword ptr [rdx+810h]
0x1401fa698  movdqu  xmmword ptr [rdi+270h], xmm1
0x1401fa6a0  movups  xmm0, xmmword ptr [rdx+7C0h]
0x1401fa6a7  movdqu  xmmword ptr [rdi+2A0h], xmm0
0x1401fa6af  movups  xmm1, xmmword ptr [rdx+7D8h]
0x1401fa6b6  movdqu  xmmword ptr [rdi+2B8h], xmm1
0x1401fa6be  mov     eax, [rdx+7D0h]
0x1401fa6c4  mov     [rdi+2B0h], eax
0x1401fa6ca  mov     eax, [rdx+7D4h]
0x1401fa6d0  mov     [rdi+2B4h], eax
0x1401fa6d6  mov     eax, [rdx+7E8h]
0x1401fa6dc  mov     [rdi+2C8h], eax
0x1401fa6e2  mov     eax, [rdx+7ECh]
0x1401fa6e8  mov     [rdi+2CCh], eax
0x1401fa6ee  movups  xmm0, xmmword ptr [rdx+820h]
0x1401fa6f5  movdqu  xmmword ptr [rdi+280h], xmm0
0x1401fa6fd  movups  xmm1, xmmword ptr [rdx+830h]
0x1401fa704  add     rdx, 748h; struct _UNICODE_STRING *
0x1401fa70b  movdqu  xmmword ptr [rdi+290h], xmm1
0x1401fa713  call    ?InitializeUserModeDriverNames@ADAPTER_RENDER@@AEAAJPEAU_UNICODE_STRING@@0@Z; ADAPTER_RENDER::InitializeUserModeDriverNames(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401fa718  test    eax, eax
0x1401fa71a  js      loc_1401FBC41
0x1401fa720  mov     rdx, [rdi+10h]
0x1401fa724  lea     r8, [rdi+1A0h]; struct _UNICODE_STRING *
0x1401fa72b  add     rdx, 758h; struct _UNICODE_STRING *
0x1401fa732  mov     rcx, rdi; this
0x1401fa735  call    ?InitializeUserModeDriverNames@ADAPTER_RENDER@@AEAAJPEAU_UNICODE_STRING@@0@Z; ADAPTER_RENDER::InitializeUserModeDriverNames(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401fa73a  test    eax, eax
0x1401fa73c  js      loc_1401FBC41
0x1401fa742  mov     rdx, [rdi+10h]
0x1401fa746  lea     r8, [rdi+200h]; struct _UNICODE_STRING *
0x1401fa74d  add     rdx, 880h; struct _UNICODE_STRING *
0x1401fa754  mov     rcx, rdi; this
0x1401fa757  call    ?InitializeDisplayUserModeDriverNames@ADAPTER_RENDER@@AEAAJPEAU_UNICODE_STRING@@0@Z; ADAPTER_RENDER::InitializeDisplayUserModeDriverNames(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401fa75c  test    eax, eax
0x1401fa75e  js      loc_1401FBC0F
0x1401fa764  mov     rdx, [rdi+10h]
0x1401fa768  lea     r8, [rdi+210h]; struct _UNICODE_STRING *
0x1401fa76f  add     rdx, 890h; struct _UNICODE_STRING *
0x1401fa776  mov     rcx, rdi; this
0x1401fa779  call    ?InitializeDisplayUserModeDriverNames@ADAPTER_RENDER@@AEAAJPEAU_UNICODE_STRING@@0@Z; ADAPTER_RENDER::InitializeDisplayUserModeDriverNames(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401fa77e  test    eax, eax
0x1401fa780  js      loc_1401FBC0F
0x1401fa786  cmp     [rbx], r13w
0x1401fa78a  jbe     short loc_1401FA7B2
0x1401fa78c  mov     rax, [rdi+148h]
0x1401fa793  cmp     word ptr [rax], 23h ; '#'
0x1401fa797  jnz     short loc_1401FA7B2
0x1401fa799  mov     rax, [rdi+10h]
0x1401fa79d  cmp     [rax+858h], r13w
0x1401fa7a5  jbe     short loc_1401FA7B2
0x1401fa7a7  movups  xmm0, xmmword ptr [rax+858h]
0x1401fa7ae  movdqu  xmmword ptr [rbx], xmm0
0x1401fa7b2  cmp     [rdi+1A0h], r13w
0x1401fa7ba  jbe     short loc_1401FA7E6
0x1401fa7bc  mov     rax, [rdi+1A8h]
0x1401fa7c3  cmp     word ptr [rax], 23h ; '#'
0x1401fa7c7  jnz     short loc_1401FA7E6
0x1401fa7c9  mov     rax, [rdi+10h]
0x1401fa7cd  cmp     [rax+868h], r13w
0x1401fa7d5  jbe     short loc_1401FA7E6
0x1401fa7d7  movups  xmm0, xmmword ptr [rax+868h]
0x1401fa7de  movdqu  xmmword ptr [rdi+1A0h], xmm0
0x1401fa7e6  lea     rcx, [rdi+568h]; RunRef
0x1401fa7ed  call    cs:__imp_ExInitializeRundownProtection
0x1401fa7f4  nop     dword ptr [rax+rax+00h]
0x1401fa7f9  mov     rcx, [rdi+10h]
0x1401fa7fd  cmp     [rcx+0D1h], r13b
0x1401fa804  jnz     short loc_1401FA86E
0x1401fa806  cmp     [rdi+140h], r13w
0x1401fa80e  jnz     short loc_1401FA86E
0x1401fa810  mov     eax, [rcx+0C10h]
0x1401fa816  shr     eax, 3
0x1401fa819  test    al, 1
0x1401fa81b  jnz     short loc_1401FA86E
0x1401fa81d  mov     rdx, rcx
0x1401fa820  mov     rbx, 0FFFFFFFFC0000182h
0x1401fa827  mov     r8, rbx
0x1401fa82a  mov     ecx, 2
0x1401fa82f  call    cs:__imp_WdLogSingleEntry2
0x1401fa836  nop     dword ptr [rax+rax+00h]
0x1401fa83b  mov     [rsp+400h+var_3C0], r13
0x1401fa840  lea     r9, aAdapter0xI64xI_3; "Adapter 0x%I64x: Invalid user mode driv"...
0x1401fa847  mov     qword ptr [rsp+400h+Depth], r13
0x1401fa84c  mov     qword ptr [rsp+400h+Tag], r13
0x1401fa851  mov     cs:WdLogGlobalForLineNumber, 3D6h
0x1401fa85b  mov     rcx, [rdi+10h]
0x1401fa85f  mov     [rsp+400h+Size], rbx
0x1401fa864  mov     qword ptr [rsp+400h+Flags], rcx
0x1401fa869  jmp     loc_1401FBC8E
0x1401fa86e  mov     rax, [rcx+0D8h]
0x1401fa875  mov     rcx, [rax+40h]
0x1401fa879  mov     rax, [rcx+28h]
0x1401fa87d  mov     rcx, rdi; this
0x1401fa880  mov     r15d, [rax+1Ch]
0x1401fa884  mov     [rsp+400h+var_3A8], r15d
0x1401fa889  call    ?GetVidSchSibmitDataSize@ADAPTER_RENDER@@QEAAIXZ; ADAPTER_RENDER::GetVidSchSibmitDataSize(void)
0x1401fa88e  mov     r9d, eax
0x1401fa891  lea     rcx, [rdi+590h]; Lookaside
0x1401fa898  mov     [rsp+400h+Depth], r13w; Depth
0x1401fa89e  mov     r14d, 4B677844h
0x1401fa8a4  mov     [rsp+400h+Tag], r14d; Tag
0x1401fa8a9  xor     r8d, r8d; Free
0x1401fa8ac  mov     [rsp+400h+Size], r9; Size
0x1401fa8b1  xor     edx, edx; Allocate
0x1401fa8b3  mov     r9d, 200h; PoolType
0x1401fa8b9  mov     [rsp+400h+Flags], r13d; Flags
0x1401fa8be  call    cs:__imp_ExInitializeLookasideListEx
0x1401fa8c5  nop     dword ptr [rax+rax+00h]
0x1401fa8ca  test    eax, eax
0x1401fa8cc  jns     short loc_1401FA8FF
0x1401fa8ce  xor     r9d, r9d
0x1401fa8d1  mov     r8, 0FFFFFFFFC0000017h
0x1401fa8d8  mov     rdx, rdi
0x1401fa8db  lea     ecx, [r9+3]
0x1401fa8df  call    cs:__imp_WdLogSingleEntry3
0x1401fa8e6  nop     dword ptr [rax+rax+00h]
0x1401fa8eb  mov     eax, 0C0000017h
0x1401fa8f0  mov     cs:WdLogGlobalForLineNumber, 3E0h
0x1401fa8fa  jmp     loc_1401FBCA0
0x1401fa8ff  lea     rcx, [rsp+400h+var_3A4]; this
0x1401fa904  mov     byte ptr [rdi+559h], 1
0x1401fa90b  mov     [rsp+400h+var_3A3], r13b
0x1401fa910  call    ?Enter@DXGCRITICALREGION@@QEAAXXZ; DXGCRITICALREGION::Enter(void)
0x1401fa915  mov     rcx, [rdi+10h]; this
0x1401fa919  cmp     [rcx+0D1h], r13b
0x1401fa920  jnz     loc_1401FA9B8
0x1401fa926  call    ?IsDxgmms2@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDxgmms2(void)
0x1401fa92b  mov     bl, al
0x1401fa92d  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401fa932  mov     cl, bl
0x1401fa934  neg     cl
0x1401fa936  sbb     rcx, rcx
0x1401fa939  and     ecx, 8
0x1401fa93c  mov     rcx, [rax+rcx+108h]
0x1401fa944  mov     [rdi+2F8h], rcx
0x1401fa94b  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401fa950  neg     bl
0x1401fa952  sbb     rcx, rcx
0x1401fa955  and     ecx, 8
0x1401fa958  mov     rdx, [rax+rcx+118h]
0x1401fa960  mov     [rdi+2E0h], rdx
0x1401fa967  cmp     [rdi+2F8h], r13
0x1401fa96e  jz      short loc_1401FA975
0x1401fa970  test    rdx, rdx
0x1401fa973  jnz     short loc_1401FA9B8
0x1401fa975  mov     rbx, 0FFFFFFFFC0000182h
0x1401fa97c  mov     rdx, rdi
0x1401fa97f  mov     r8, rbx
0x1401fa982  mov     ecx, 2
0x1401fa987  call    cs:__imp_WdLogSingleEntry2
0x1401fa98e  nop     dword ptr [rax+rax+00h]
0x1401fa993  mov     [rsp+400h+var_3C0], r13
0x1401fa998  lea     r9, aAdapter0xI64xU_0; "Adapter 0x%I64x: Unsupported display dr"...
0x1401fa99f  mov     qword ptr [rsp+400h+Depth], r13
0x1401fa9a4  mov     qword ptr [rsp+400h+Tag], r13
0x1401fa9a9  mov     cs:WdLogGlobalForLineNumber, 3FDh
0x1401fa9b3  jmp     loc_1401FAD95
0x1401fa9b8  mov     rbx, [rdi+10h]
0x1401fa9bc  mov     rcx, rbx; this
0x1401fa9bf  call    ?IsGpuVirtualAddressingSupported@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsGpuVirtualAddressingSupported(void)
0x1401fa9c4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1401fa9c8  mov     esi, 2
0x1401fa9cd  test    al, al
0x1401fa9cf  jz      loc_1401FADDD
0x1401fa9d5  mov     ebx, [rbx+128h]
0x1401fa9db  mov     eax, 90h
0x1401fa9e0  mul     rbx
0x1401fa9e3  mov     edx, r14d
0x1401fa9e6  mov     [rsp+400h+var_3A0], ebx
0x1401fa9ea  cmovb   rax, r8
0x1401fa9ee  mov     r8d, 100h
0x1401fa9f4  mov     rcx, rax
0x1401fa9f7  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401fa9fc  mov     [rdi+4F0h], rax
0x1401faa03  test    rax, rax
0x1401faa06  jnz     short loc_1401FAA66
0x1401faa08  lea     ecx, [rsi+4]
0x1401faa0b  call    cs:__imp_WdLogSingleEntry0
0x1401faa12  nop     dword ptr [rax+rax+00h]
0x1401faa17  mov     [rsp+400h+var_3C0], r13
0x1401faa1c  lea     r9, aFailedToAlloca_53; "Failed to allocate m_pGpuMmuCaps"
0x1401faa23  mov     qword ptr [rsp+400h+Depth], r13
0x1401faa28  mov     eax, 40Ch
0x1401faa2d  mov     qword ptr [rsp+400h+Tag], r13
0x1401faa32  mov     [rsp+400h+Size], r13
0x1401faa37  mov     qword ptr [rsp+400h+Flags], rax
0x1401faa3c  mov     cs:WdLogGlobalForLineNumber, eax
0x1401faa42  or      r8d, 0FFFFFFFFh
0x1401faa46  mov     edx, 40001h
0x1401faa4b  xor     ecx, ecx
0x1401faa4d  call    DxgkLogInternalTriageEvent
0x1401faa52  mov     ebx, 0C0000017h
0x1401faa57  lea     rcx, [rsp+400h+var_3A4]; this
0x1401faa5c  call    ??1DXGCRITICALREGION@@QEAA@XZ; DXGCRITICALREGION::~DXGCRITICALREGION(void)
0x1401faa61  jmp     loc_1401FBC9E
0x1401faa66  xor     r8d, r8d
0x1401faa69  mov     r13d, 3Fh ; '?'
0x1401faa6f  mov     r14d, r8d
0x1401faa72  mov     [rsp+400h+var_3B0], r8d
0x1401faa77  mov     r12d, r8d
0x1401faa7a  cmp     r12d, ebx
0x1401faa7d  jnb     loc_1401FADB4
0x1401faa83  mov     rcx, [rdi+10h]; this
0x1401faa87  mov     eax, r12d
0x1401faa8a  lea     rbx, [rax+rax*8]
0x1401faa8e  mov     eax, [rcx+0A14h]
0x1401faa94  shl     rbx, 4
0x1401faa98  add     rbx, [rdi+4F0h]
0x1401faa9f  test    al, 40h
0x1401faaa1  jz      loc_1401FABCE
0x1401faaa7  lea     rax, [rbp+300h+var_380]
0x1401faaab  mov     qword ptr [rbp+300h+var_310.Type], 0Dh
0x1401faab3  lea     rdx, [rbp+300h+var_310]; struct _DXGKARG_QUERYADAPTERINFO *
0x1401faab7  mov     [rbp+300h+var_310.pInputData], rax
0x1401faabb  mov     qword ptr [rbp+300h+var_310.InputDataSize], 4
0x1401faac3  mov     qword ptr [rbp+300h+var_310.Flags], r8
0x1401faac7  mov     dword ptr [rbp+300h+var_310.hKmdProcessHandle+4], r8d
0x1401faacb  mov     [rbp+300h+var_310.pOutputData], rbx
0x1401faacf  mov     [rbp+300h+var_310.OutputDataSize], 18h
0x1401faad6  mov     [rbp+300h+var_380], r12d
0x1401faada  call    ?DdiQueryAdapterInfo@DXGADAPTER@@QEAAJPEAU_DXGKARG_QUERYADAPTERINFO@@@Z; DXGADAPTER::DdiQueryAdapterInfo(_DXGKARG_QUERYADAPTERINFO *)
0x1401faadf  xor     r8d, r8d
0x1401faae2  test    eax, eax
0x1401faae4  js      loc_1401FAD58
0x1401faaea  mov     ecx, [rbx+8]
0x1401faaed  test    r14d, r14d
0x1401faaf0  jnz     short loc_1401FAB04
0x1401faaf2  lea     eax, [rcx-0Dh]
0x1401faaf5  cmp     eax, 32h ; '2'
0x1401faaf8  ja      loc_1401FABEB
  ... truncated ...
```
