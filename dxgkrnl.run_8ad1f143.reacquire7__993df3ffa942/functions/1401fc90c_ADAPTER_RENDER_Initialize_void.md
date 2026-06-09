# ADAPTER_RENDER::Initialize(void)

- ea: `0x1401fc90c`
- end: `0x1401fe0a4`
- name: `?Initialize@ADAPTER_RENDER@@QEAAJXZ`
- size: `6040`
- prototype: `__int64 __fastcall(ADAPTER_RENDER *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1401fa368`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140012540`
- `0x14001b9c0`
- `0x14002ff90`
- `0x140033b60`
- `0x140033d80`
- `0x140038538`
- `0x14003f9c0`
- `0x1400443c0`
- `0x14004b598`
- `0x1400782ec`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`
- `0x1401cd600`
- `0x1401d7b80`
- `0x1401fc90c`
- `0x1401fe0ac`
- `0x1401fe480`
- `0x14035fa08`
- `0x1403b7b70`
- `0x1403cf890`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x1401fdfd2`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401fdfd2`
- `ntoskrnl!KeInitializeTimer` at `0x1401fdf99`
- `ntoskrnl!KeInitializeTimer` at `0x1401fdf99`
- `ntoskrnl!KeInitializeDpc` at `0x1401fdfb6`
- `ntoskrnl!KeInitializeDpc` at `0x1401fdfb6`
- `ntoskrnl!wcsstr` at `0x1401fc9c3`
- `ntoskrnl!wcsstr` at `0x1401fc9de`
- `ntoskrnl!wcsstr` at `0x1401fc9ff`
- `ntoskrnl!wcsstr` at `0x1401fc9c3`
- `ntoskrnl!wcsstr` at `0x1401fc9de`
- `ntoskrnl!wcsstr` at `0x1401fc9ff`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1401fcbcd`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1401fcbcd`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1401fcc9e`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1401fcc9e`
- `watchdog!WdLogSingleEntry2` at `0x1401fcc0f`
- `watchdog!WdLogSingleEntry2` at `0x1401fcd67`
- `watchdog!WdLogSingleEntry2` at `0x1401fcfda`
- `watchdog!WdLogSingleEntry2` at `0x1401fd034`
- `watchdog!WdLogSingleEntry2` at `0x1401fd07d`
- `watchdog!WdLogSingleEntry2` at `0x1401fd147`
- `watchdog!WdLogSingleEntry2` at `0x1401fd666`
- `watchdog!WdLogSingleEntry2` at `0x1401fd6a9`
- `watchdog!WdLogSingleEntry2` at `0x1401fd72a`
- `watchdog!WdLogSingleEntry2` at `0x1401fd76d`
- `watchdog!WdLogSingleEntry2` at `0x1401fd7b0`
- `watchdog!WdLogSingleEntry2` at `0x1401fd833`
- `watchdog!WdLogSingleEntry2` at `0x1401fd876`
- `watchdog!WdLogSingleEntry2` at `0x1401fd8b9`
- `watchdog!WdLogSingleEntry2` at `0x1401fd8fc`
- `watchdog!WdLogSingleEntry2` at `0x1401fd93f`
- `watchdog!WdLogSingleEntry2` at `0x1401fd9dc`
- `watchdog!WdLogSingleEntry2` at `0x1401fda72`
- `watchdog!WdLogSingleEntry2` at `0x1401fdd28`
- `watchdog!WdLogSingleEntry2` at `0x1401fdf4a`
- `watchdog!WdLogSingleEntry2` at `0x1401fe002`
- `watchdog!WdLogSingleEntry2` at `0x1401fe034`
- `watchdog!WdLogSingleEntry2` at `0x1401fcc0f`
- `watchdog!WdLogSingleEntry2` at `0x1401fcd67`
- `watchdog!WdLogSingleEntry2` at `0x1401fcfda`
- `watchdog!WdLogSingleEntry2` at `0x1401fd034`
- `watchdog!WdLogSingleEntry2` at `0x1401fd07d`
- `watchdog!WdLogSingleEntry2` at `0x1401fd147`
- `watchdog!WdLogSingleEntry2` at `0x1401fd666`
- `watchdog!WdLogSingleEntry2` at `0x1401fd6a9`
- `watchdog!WdLogSingleEntry2` at `0x1401fd72a`
- `watchdog!WdLogSingleEntry2` at `0x1401fd76d`
- `watchdog!WdLogSingleEntry2` at `0x1401fd7b0`
- `watchdog!WdLogSingleEntry2` at `0x1401fd833`
- `watchdog!WdLogSingleEntry2` at `0x1401fd876`
- `watchdog!WdLogSingleEntry2` at `0x1401fd8b9`
- `watchdog!WdLogSingleEntry2` at `0x1401fd8fc`
- `watchdog!WdLogSingleEntry2` at `0x1401fd93f`
- `watchdog!WdLogSingleEntry2` at `0x1401fd9dc`
- `watchdog!WdLogSingleEntry2` at `0x1401fda72`
- `watchdog!WdLogSingleEntry2` at `0x1401fdd28`
- `watchdog!WdLogSingleEntry2` at `0x1401fdf4a`
- `watchdog!WdLogSingleEntry2` at `0x1401fe002`
- `watchdog!WdLogSingleEntry2` at `0x1401fe034`
- `watchdog!WdLogSingleEntry3` at `0x1401fccbf`
- `watchdog!WdLogSingleEntry3` at `0x1401fde6b`
- `watchdog!WdLogSingleEntry3` at `0x1401fccbf`
- `watchdog!WdLogSingleEntry3` at `0x1401fde6b`
- `watchdog!WdLogSingleEntry0` at `0x1401fcdeb`
- `watchdog!WdLogSingleEntry0` at `0x1401fd0a1`
- `watchdog!WdLogSingleEntry0` at `0x1401fd0f6`
- `watchdog!WdLogSingleEntry0` at `0x1401fd6e6`
- `watchdog!WdLogSingleEntry0` at `0x1401fcdeb`
- `watchdog!WdLogSingleEntry0` at `0x1401fd0a1`
- `watchdog!WdLogSingleEntry0` at `0x1401fd0f6`
- `watchdog!WdLogSingleEntry0` at `0x1401fd6e6`
- `watchdog!WdLogSingleEntry1` at `0x1401fd31f`
- `watchdog!WdLogSingleEntry1` at `0x1401fd365`
- `watchdog!WdLogSingleEntry1` at `0x1401fd7f0`
- `watchdog!WdLogSingleEntry1` at `0x1401fd97f`
- `watchdog!WdLogSingleEntry1` at `0x1401fda26`
- `watchdog!WdLogSingleEntry1` at `0x1401fdab8`
- `watchdog!WdLogSingleEntry1` at `0x1401fdaf6`
- `watchdog!WdLogSingleEntry1` at `0x1401fdb39`
- `watchdog!WdLogSingleEntry1` at `0x1401fdb7e`
- `watchdog!WdLogSingleEntry1` at `0x1401fdef2`
- `watchdog!WdLogSingleEntry1` at `0x1401fd31f`
- `watchdog!WdLogSingleEntry1` at `0x1401fd365`
- `watchdog!WdLogSingleEntry1` at `0x1401fd7f0`
- `watchdog!WdLogSingleEntry1` at `0x1401fd97f`
- `watchdog!WdLogSingleEntry1` at `0x1401fda26`
- `watchdog!WdLogSingleEntry1` at `0x1401fdab8`
- `watchdog!WdLogSingleEntry1` at `0x1401fdaf6`
- `watchdog!WdLogSingleEntry1` at `0x1401fdb39`
- `watchdog!WdLogSingleEntry1` at `0x1401fdb7e`
- `watchdog!WdLogSingleEntry1` at `0x1401fdef2`

## string_xrefs

- `0x1401fd0af`: `GpuMmu.PageDirectoryCount is invalid. It should be from 2 to DXGK_MAX_PAGE_TABLE_LEVEL_COUNT\n`
- `0x1401fd089`: `Adapter 0x%I64x: Failed to query page table level descriptor, returning 0x%I64x`
- `0x1401fdd39`: `Adapter 0x%I64x: CreateSynchronizationObjectInternal failed. Returning 0x%I64x`

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
  *((_OWORD *)this + 34) = *(_OWORD *)(v3 + 1920);
  *((_OWORD *)this + 35) = *(_OWORD *)(v3 + 1952);
  *((_OWORD *)this + 36) = *(_OWORD *)(v3 + 1968);
  *((_OWORD *)this + 37) = *(_OWORD *)(v3 + 1936);
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
  *((_OWORD *)this + 38) = *(_OWORD *)(v7 + 2064);
  *((_OWORD *)this + 39) = *(_OWORD *)(v7 + 2080);
  *((_OWORD *)this + 42) = *(_OWORD *)(v7 + 2000);
  *(_OWORD *)((char *)this + 696) = *(_OWORD *)(v7 + 2024);
  *((_DWORD *)this + 172) = *(_DWORD *)(v7 + 2016);
  *((_DWORD *)this + 173) = *(_DWORD *)(v7 + 2020);
  *((_DWORD *)this + 178) = *(_DWORD *)(v7 + 2040);
  *((_DWORD *)this + 179) = *(_DWORD *)(v7 + 2044);
  *((_OWORD *)this + 40) = *(_OWORD *)(v7 + 2096);
  *((_OWORD *)this + 41) = *(_OWORD *)(v7 + 2112);
  if ( (int)ADAPTER_RENDER::InitializeUserModeDriverNames(
              this,
              (struct _UNICODE_STRING *)(v7 + 1880),
              (struct _UNICODE_STRING *)this + 20) < 0
    || (int)ADAPTER_RENDER::InitializeUserModeDriverNames(
              this,
              (struct _UNICODE_STRING *)(*((_QWORD *)this + 2) + 1896LL),
              (struct _UNICODE_STRING *)this + 26) < 0 )
  {
    v12 = -1073741438;
    WdLogSingleEntry2(2, *((_QWORD *)this + 2), -1073741438);
    v79 = L"Adapter 0x%I64x: Invalidly formatted user mode driver name, returning 0x%I64x";
    WdLogGlobalForLineNumber = 932;
    goto LABEL_205;
  }
  if ( (int)ADAPTER_RENDER::InitializeDisplayUserModeDriverNames(
              this,
              (struct _UNICODE_STRING *)(*((_QWORD *)this + 2) + 2192LL),
              (struct _UNICODE_STRING *)this + 32) < 0
    || (int)ADAPTER_RENDER::InitializeDisplayUserModeDriverNames(
              this,
              (struct _UNICODE_STRING *)(*((_QWORD *)this + 2) + 2208LL),
              (struct _UNICODE_STRING *)this + 33) < 0 )
  {
    v12 = -1073741438;
    WdLogSingleEntry2(2, *((_QWORD *)this + 2), -1073741438);
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
      if ( *(_WORD *)(v9 + 2152) )
        *v8 = *(_OWORD *)(v9 + 2152);
    }
  }
  if ( *((_WORD *)this + 208) )
  {
    if ( **((_WORD **)this + 53) == 35 )
    {
      v10 = *((_QWORD *)this + 2);
      if ( *(_WORD *)(v10 + 2168) )
        *((_OWORD *)this + 26) = *(_OWORD *)(v10 + 2168);
    }
  }
  ExInitializeRundownProtection((PEX_RUNDOWN_REF)this + 173);
  v11 = *((_QWORD *)this + 2);
  if ( !*(_BYTE *)(v11 + 209) && !*((_WORD *)this + 160) && (*(_DWORD *)(v11 + 3104) & 8) == 0 )
  {
    v12 = -1073741438;
    WdLogSingleEntry2(2, *((_QWORD *)this + 2), -1073741438);
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
      WdLogSingleEntry2(2, this, -1073741438);
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
      if ( (*((_DWORD *)v27 + 649) & 0x40) != 0 )
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
          WdLogSingleEntry2(2, this, -1073741438);
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
              WdLogSingleEntry2(2, 12, 63);
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
              WdLogSingleEntry2(2, this, j);
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
          WdLogSingleEntry2(2, this, -1073741438);
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
  if ( *(int *)(*((_QWORD *)this + 2) + 2864LL) < 4864 )
    goto LABEL_163;
  v34 = 0;
  while ( 2 )
  {
    v35 = (DXGADAPTER *)*((_QWORD *)this + 2);
    v80 = v34;
    if ( v34 >= DXGADAPTER::GetNumDifferentPhysicalAdapters(v35) )
    {
      if ( *(int *)(v36 + 2864) < 8960 )
        *(_DWORD *)(v36 + 2592) &= 0xFFFFF87F;
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
        WdLogSingleEntry2(2, this, SynchronizationObjectInternal);
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
      if ( v66[716] < 4864 )
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
        v69 = *(unsigned __int16 *)(352 * m + *(_QWORD *)(*((_QWORD *)this + 2) + 3120LL));
        v70 = 4LL * *(unsigned __int16 *)(352 * m + *(_QWORD *)(*((_QWORD *)this + 2) + 3120LL));
        if ( !is_mul_ok(*(unsigned __int16 *)(352 * m + *(_QWORD *)(*((_QWORD *)this + 2) + 3120LL)), 4u) )
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
            WdLogSingleEntry2(2, this, -1073741438);
            v19 = L"Adapter 0x%I64x: Precision data is bad. Returning 0x%I64x";
            WdLogGlobalForLineNumber = 1597;
            goto LABEL_70;
          }
          v72 = 0;
          WdLogSingleEntry1(4, this);
          WdLogGlobalForLineNumber = 1589;
        }
LABEL_196:
        NumDifferentPhysicalAdapters = v85;
        *(_QWORD *)(352LL * v80 + *(_QWORD *)(*((_QWORD *)this + 2) + 3120LL) + 40) = v72;
      }
    }
    v38 = (unsigned __int16 *)(*(_QWORD *)(v36 + 3120) + 352LL * v34);
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
      WdLogSingleEntry1(6, this);
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
      WdLogSingleEntry1(6, this);
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
      WdLogSingleEntry1(6, this);
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
    if ( v47[783] >= 2400 )
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
        WdLogSingleEntry1(3, this);
        WdLogGlobalForLineNumber = 1229;
      }
      v49 = (DXGADAPTER *)*((_QWORD *)this + 2);
      v89[0].pOutputData = v38 + 106;
      v89[0].Type = DXGKQAITYPE_GPUVERSION;
      v89[0].OutputDataSize = 128;
      if ( (int)DXGADAPTER::DdiQueryAdapterInfo(v49, v89) < 0 )
      {
        WdLogSingleEntry1(3, this);
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
        WdLogSingleEntry1(2, this);
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
      if ( *(_DWORD *)(v53 + 2408) < 0x9000u )
      {
        v51->Flags.Value = 0;
        v42 = v85;
        goto LABEL_115;
      }
      if ( (*(_BYTE *)&v51->Flags.0 & 1) != 0 )
      {
        if ( !v51->IoMmuSupported && !*((_BYTE *)v38 + 49) )
        {
          WdLogSingleEntry2(2, this, n);
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
        if ( (**(_DWORD **)(v53 + 3136) & 0x20000) == 0 )
        {
          WdLogSingleEntry2(2, this, n);
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
        if ( *(int *)(v53 + 3132) < 3100 )
        {
          WdLogSingleEntry1(2, this);
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
          WdLogSingleEntry2(2, this, n);
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
        if ( (**(_DWORD **)(v53 + 3136) & 0x8000000) == 0 )
        {
          WdLogSingleEntry2(2, this, n);
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
        if ( (v87[648] & 0x800) == 0 )
        {
          WdLogSingleEntry2(2, this, n);
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
        WdLogSingleEntry2(2, this, n);
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
        if ( (v87[649] & 0x40) == 0 )
        {
          WdLogSingleEntry2(2, this, n);
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
          WdLogSingleEntry2(2, this, n);
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
        if ( n == v38[1] && !*(_BYTE *)(*((_QWORD *)this + 2) + 3169LL) )
          *((_BYTE *)v38 + 48) = 1;
        *((_BYTE *)v38 + 49) = 1;
      }
      if ( *(_BYTE *)(74LL * n + v42 + 73) )
      {
        if ( (v55[649] & 0x80u) == 0 )
        {
          WdLogSingleEntry2(2, this, n);
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
          WdLogSingleEntry2(2, this, n);
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
        if ( n == v38[1] && !*(_BYTE *)(*((_QWORD *)this + 2) + 3169LL) )
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
    WdLogSingleEntry1(2, this);
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
      WdLogSingleEntry2(2, DWORD1(v93[0]), 4096);
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
      WdLogSingleEntry1(2, -1073741811);
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
      WdLogSingleEntry2(2, DWORD2(v93[0]), 4096);
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
0x1401fc90c  push    rbp
0x1401fc90e  push    rbx
0x1401fc90f  push    rsi
0x1401fc910  push    rdi
0x1401fc911  push    r12
0x1401fc913  push    r13
0x1401fc915  push    r14
0x1401fc917  push    r15
0x1401fc919  lea     rbp, [rsp-2C8h]
0x1401fc921  sub     rsp, 3C8h
0x1401fc928  mov     rax, cs:__security_cookie
0x1401fc92f  xor     rax, rsp
0x1401fc932  mov     [rbp+300h+var_50], rax
0x1401fc939  mov     rdi, rcx
0x1401fc93c  xor     r13d, r13d
0x1401fc93f  mov     rcx, [rcx+10h]
0x1401fc943  movups  xmm0, xmmword ptr [rcx+780h]
0x1401fc94a  movdqu  xmmword ptr [rdi+220h], xmm0
0x1401fc952  movups  xmm1, xmmword ptr [rcx+7A0h]
0x1401fc959  movdqu  xmmword ptr [rdi+230h], xmm1
0x1401fc961  movups  xmm0, xmmword ptr [rcx+7B0h]
0x1401fc968  movdqu  xmmword ptr [rdi+240h], xmm0
0x1401fc970  movups  xmm1, xmmword ptr [rcx+790h]
0x1401fc977  movdqu  xmmword ptr [rdi+250h], xmm1
0x1401fc97f  cmp     [rdi+250h], r13w
0x1401fc987  jz      loc_1401FCA51
0x1401fc98d  mov     rcx, [rcx+0D8h]
0x1401fc994  lea     r8, [rsp+400h+var_3A8]
0x1401fc999  lea     rdx, [rbp+300h+Str]
0x1401fc9a0  mov     [rsp+400h+var_3A8], 208h
0x1401fc9a8  call    DpiGetDriverStorePath
0x1401fc9ad  test    eax, eax
0x1401fc9af  js      loc_1401FCA51
0x1401fc9b5  lea     rdx, aFilerepository_0; "FileRepository"
0x1401fc9bc  lea     rcx, [rbp+300h+Str]; Str
0x1401fc9c3  call    cs:__imp_wcsstr
0x1401fc9ca  nop     dword ptr [rax+rax+00h]
0x1401fc9cf  test    rax, rax
0x1401fc9d2  jz      short loc_1401FCA51
0x1401fc9d4  lea     rdx, Source; "\\"
0x1401fc9db  mov     rcx, rax; Str
0x1401fc9de  call    cs:__imp_wcsstr
0x1401fc9e5  nop     dword ptr [rax+rax+00h]
0x1401fc9ea  test    rax, rax
0x1401fc9ed  jz      short loc_1401FCA51
0x1401fc9ef  lea     rdx, [rax+2]; SubStr
0x1401fc9f3  test    rdx, rdx
0x1401fc9f6  jz      short loc_1401FCA51
0x1401fc9f8  mov     rcx, [rdi+258h]; Str
0x1401fc9ff  call    cs:__imp_wcsstr
0x1401fca06  nop     dword ptr [rax+rax+00h]
0x1401fca0b  test    rax, rax
0x1401fca0e  jnz     short loc_1401FCA51
0x1401fca10  cmp     [rdi+230h], r13w
0x1401fca18  jz      short loc_1401FCA29
0x1401fca1a  mov     [rdi+230h], r13w
0x1401fca22  mov     [rdi+238h], r13
0x1401fca29  cmp     [rdi+240h], r13w
0x1401fca31  jz      short loc_1401FCA42
0x1401fca33  mov     [rdi+240h], r13w
0x1401fca3b  mov     [rdi+248h], r13
0x1401fca42  mov     [rdi+250h], r13w
0x1401fca4a  mov     [rdi+258h], r13
0x1401fca51  mov     rdx, [rdi+10h]
0x1401fca55  lea     rbx, [rdi+140h]
0x1401fca5c  mov     r8, rbx; struct _UNICODE_STRING *
0x1401fca5f  mov     rcx, rdi; this
0x1401fca62  movups  xmm0, xmmword ptr [rdx+810h]
0x1401fca69  movdqu  xmmword ptr [rdi+260h], xmm0
0x1401fca71  movups  xmm1, xmmword ptr [rdx+820h]
0x1401fca78  movdqu  xmmword ptr [rdi+270h], xmm1
0x1401fca80  movups  xmm0, xmmword ptr [rdx+7D0h]
0x1401fca87  movdqu  xmmword ptr [rdi+2A0h], xmm0
0x1401fca8f  movups  xmm1, xmmword ptr [rdx+7E8h]
0x1401fca96  movdqu  xmmword ptr [rdi+2B8h], xmm1
0x1401fca9e  mov     eax, [rdx+7E0h]
0x1401fcaa4  mov     [rdi+2B0h], eax
0x1401fcaaa  mov     eax, [rdx+7E4h]
0x1401fcab0  mov     [rdi+2B4h], eax
0x1401fcab6  mov     eax, [rdx+7F8h]
0x1401fcabc  mov     [rdi+2C8h], eax
0x1401fcac2  mov     eax, [rdx+7FCh]
0x1401fcac8  mov     [rdi+2CCh], eax
0x1401fcace  movups  xmm0, xmmword ptr [rdx+830h]
0x1401fcad5  movdqu  xmmword ptr [rdi+280h], xmm0
0x1401fcadd  movups  xmm1, xmmword ptr [rdx+840h]
0x1401fcae4  add     rdx, 758h; struct _UNICODE_STRING *
0x1401fcaeb  movdqu  xmmword ptr [rdi+290h], xmm1
0x1401fcaf3  call    ?InitializeUserModeDriverNames@ADAPTER_RENDER@@AEAAJPEAU_UNICODE_STRING@@0@Z; ADAPTER_RENDER::InitializeUserModeDriverNames(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401fcaf8  test    eax, eax
0x1401fcafa  js      loc_1401FE021
0x1401fcb00  mov     rdx, [rdi+10h]
0x1401fcb04  lea     r8, [rdi+1A0h]; struct _UNICODE_STRING *
0x1401fcb0b  add     rdx, 768h; struct _UNICODE_STRING *
0x1401fcb12  mov     rcx, rdi; this
0x1401fcb15  call    ?InitializeUserModeDriverNames@ADAPTER_RENDER@@AEAAJPEAU_UNICODE_STRING@@0@Z; ADAPTER_RENDER::InitializeUserModeDriverNames(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401fcb1a  test    eax, eax
0x1401fcb1c  js      loc_1401FE021
0x1401fcb22  mov     rdx, [rdi+10h]
0x1401fcb26  lea     r8, [rdi+200h]; struct _UNICODE_STRING *
0x1401fcb2d  add     rdx, 890h; struct _UNICODE_STRING *
0x1401fcb34  mov     rcx, rdi; this
0x1401fcb37  call    ?InitializeDisplayUserModeDriverNames@ADAPTER_RENDER@@AEAAJPEAU_UNICODE_STRING@@0@Z; ADAPTER_RENDER::InitializeDisplayUserModeDriverNames(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401fcb3c  test    eax, eax
0x1401fcb3e  js      loc_1401FDFEF
0x1401fcb44  mov     rdx, [rdi+10h]
0x1401fcb48  lea     r8, [rdi+210h]; struct _UNICODE_STRING *
0x1401fcb4f  add     rdx, 8A0h; struct _UNICODE_STRING *
0x1401fcb56  mov     rcx, rdi; this
0x1401fcb59  call    ?InitializeDisplayUserModeDriverNames@ADAPTER_RENDER@@AEAAJPEAU_UNICODE_STRING@@0@Z; ADAPTER_RENDER::InitializeDisplayUserModeDriverNames(_UNICODE_STRING *,_UNICODE_STRING *)
0x1401fcb5e  test    eax, eax
0x1401fcb60  js      loc_1401FDFEF
0x1401fcb66  cmp     [rbx], r13w
0x1401fcb6a  jbe     short loc_1401FCB92
0x1401fcb6c  mov     rax, [rdi+148h]
0x1401fcb73  cmp     word ptr [rax], 23h ; '#'
0x1401fcb77  jnz     short loc_1401FCB92
0x1401fcb79  mov     rax, [rdi+10h]
0x1401fcb7d  cmp     [rax+868h], r13w
0x1401fcb85  jbe     short loc_1401FCB92
0x1401fcb87  movups  xmm0, xmmword ptr [rax+868h]
0x1401fcb8e  movdqu  xmmword ptr [rbx], xmm0
0x1401fcb92  cmp     [rdi+1A0h], r13w
0x1401fcb9a  jbe     short loc_1401FCBC6
0x1401fcb9c  mov     rax, [rdi+1A8h]
0x1401fcba3  cmp     word ptr [rax], 23h ; '#'
0x1401fcba7  jnz     short loc_1401FCBC6
0x1401fcba9  mov     rax, [rdi+10h]
0x1401fcbad  cmp     [rax+878h], r13w
0x1401fcbb5  jbe     short loc_1401FCBC6
0x1401fcbb7  movups  xmm0, xmmword ptr [rax+878h]
0x1401fcbbe  movdqu  xmmword ptr [rdi+1A0h], xmm0
0x1401fcbc6  lea     rcx, [rdi+568h]; RunRef
0x1401fcbcd  call    cs:__imp_ExInitializeRundownProtection
0x1401fcbd4  nop     dword ptr [rax+rax+00h]
0x1401fcbd9  mov     rcx, [rdi+10h]
0x1401fcbdd  cmp     [rcx+0D1h], r13b
0x1401fcbe4  jnz     short loc_1401FCC4E
0x1401fcbe6  cmp     [rdi+140h], r13w
0x1401fcbee  jnz     short loc_1401FCC4E
0x1401fcbf0  mov     eax, [rcx+0C20h]
0x1401fcbf6  shr     eax, 3
0x1401fcbf9  test    al, 1
0x1401fcbfb  jnz     short loc_1401FCC4E
0x1401fcbfd  mov     rdx, rcx
0x1401fcc00  mov     rbx, 0FFFFFFFFC0000182h
0x1401fcc07  mov     r8, rbx
0x1401fcc0a  mov     ecx, 2
0x1401fcc0f  call    cs:__imp_WdLogSingleEntry2
0x1401fcc16  nop     dword ptr [rax+rax+00h]
0x1401fcc1b  mov     [rsp+400h+var_3C0], r13
0x1401fcc20  lea     r9, aAdapter0xI64xI_3; "Adapter 0x%I64x: Invalid user mode driv"...
0x1401fcc27  mov     qword ptr [rsp+400h+Depth], r13
0x1401fcc2c  mov     qword ptr [rsp+400h+Tag], r13
0x1401fcc31  mov     cs:WdLogGlobalForLineNumber, 3D6h
0x1401fcc3b  mov     rcx, [rdi+10h]
0x1401fcc3f  mov     [rsp+400h+Size], rbx
0x1401fcc44  mov     qword ptr [rsp+400h+Flags], rcx
0x1401fcc49  jmp     loc_1401FE06E
0x1401fcc4e  mov     rax, [rcx+0D8h]
0x1401fcc55  mov     rcx, [rax+40h]
0x1401fcc59  mov     rax, [rcx+28h]
0x1401fcc5d  mov     rcx, rdi; this
0x1401fcc60  mov     r15d, [rax+1Ch]
0x1401fcc64  mov     [rsp+400h+var_3A8], r15d
0x1401fcc69  call    ?GetVidSchSibmitDataSize@ADAPTER_RENDER@@QEAAIXZ; ADAPTER_RENDER::GetVidSchSibmitDataSize(void)
0x1401fcc6e  mov     r9d, eax
0x1401fcc71  lea     rcx, [rdi+590h]; Lookaside
0x1401fcc78  mov     [rsp+400h+Depth], r13w; Depth
0x1401fcc7e  mov     r14d, 4B677844h
0x1401fcc84  mov     [rsp+400h+Tag], r14d; Tag
0x1401fcc89  xor     r8d, r8d; Free
0x1401fcc8c  mov     [rsp+400h+Size], r9; Size
0x1401fcc91  xor     edx, edx; Allocate
0x1401fcc93  mov     r9d, 200h; PoolType
0x1401fcc99  mov     [rsp+400h+Flags], r13d; Flags
0x1401fcc9e  call    cs:__imp_ExInitializeLookasideListEx
0x1401fcca5  nop     dword ptr [rax+rax+00h]
0x1401fccaa  test    eax, eax
0x1401fccac  jns     short loc_1401FCCDF
0x1401fccae  xor     r9d, r9d
0x1401fccb1  mov     r8, 0FFFFFFFFC0000017h
0x1401fccb8  mov     rdx, rdi
0x1401fccbb  lea     ecx, [r9+3]
0x1401fccbf  call    cs:__imp_WdLogSingleEntry3
0x1401fccc6  nop     dword ptr [rax+rax+00h]
0x1401fcccb  mov     eax, 0C0000017h
0x1401fccd0  mov     cs:WdLogGlobalForLineNumber, 3E0h
0x1401fccda  jmp     loc_1401FE080
0x1401fccdf  lea     rcx, [rsp+400h+var_3A4]; this
0x1401fcce4  mov     byte ptr [rdi+559h], 1
0x1401fcceb  mov     [rsp+400h+var_3A3], r13b
0x1401fccf0  call    ?Enter@DXGCRITICALREGION@@QEAAXXZ; DXGCRITICALREGION::Enter(void)
0x1401fccf5  mov     rcx, [rdi+10h]; this
0x1401fccf9  cmp     [rcx+0D1h], r13b
0x1401fcd00  jnz     loc_1401FCD98
0x1401fcd06  call    ?IsDxgmms2@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsDxgmms2(void)
0x1401fcd0b  mov     bl, al
0x1401fcd0d  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401fcd12  mov     cl, bl
0x1401fcd14  neg     cl
0x1401fcd16  sbb     rcx, rcx
0x1401fcd19  and     ecx, 8
0x1401fcd1c  mov     rcx, [rax+rcx+108h]
0x1401fcd24  mov     [rdi+2F8h], rcx
0x1401fcd2b  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x1401fcd30  neg     bl
0x1401fcd32  sbb     rcx, rcx
0x1401fcd35  and     ecx, 8
0x1401fcd38  mov     rdx, [rax+rcx+118h]
0x1401fcd40  mov     [rdi+2E0h], rdx
0x1401fcd47  cmp     [rdi+2F8h], r13
0x1401fcd4e  jz      short loc_1401FCD55
0x1401fcd50  test    rdx, rdx
0x1401fcd53  jnz     short loc_1401FCD98
0x1401fcd55  mov     rbx, 0FFFFFFFFC0000182h
0x1401fcd5c  mov     rdx, rdi
0x1401fcd5f  mov     r8, rbx
0x1401fcd62  mov     ecx, 2
0x1401fcd67  call    cs:__imp_WdLogSingleEntry2
0x1401fcd6e  nop     dword ptr [rax+rax+00h]
0x1401fcd73  mov     [rsp+400h+var_3C0], r13
0x1401fcd78  lea     r9, aAdapter0xI64xU_0; "Adapter 0x%I64x: Unsupported display dr"...
0x1401fcd7f  mov     qword ptr [rsp+400h+Depth], r13
0x1401fcd84  mov     qword ptr [rsp+400h+Tag], r13
0x1401fcd89  mov     cs:WdLogGlobalForLineNumber, 3FDh
0x1401fcd93  jmp     loc_1401FD175
0x1401fcd98  mov     rbx, [rdi+10h]
0x1401fcd9c  mov     rcx, rbx; this
0x1401fcd9f  call    ?IsGpuVirtualAddressingSupported@DXGADAPTER@@QEBAEXZ; DXGADAPTER::IsGpuVirtualAddressingSupported(void)
0x1401fcda4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1401fcda8  mov     esi, 2
0x1401fcdad  test    al, al
0x1401fcdaf  jz      loc_1401FD1BD
0x1401fcdb5  mov     ebx, [rbx+128h]
0x1401fcdbb  mov     eax, 90h
0x1401fcdc0  mul     rbx
0x1401fcdc3  mov     edx, r14d
0x1401fcdc6  mov     [rsp+400h+var_3A0], ebx
0x1401fcdca  cmovb   rax, r8
0x1401fcdce  mov     r8d, 100h
0x1401fcdd4  mov     rcx, rax
0x1401fcdd7  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1401fcddc  mov     [rdi+4F0h], rax
0x1401fcde3  test    rax, rax
0x1401fcde6  jnz     short loc_1401FCE46
0x1401fcde8  lea     ecx, [rsi+4]
0x1401fcdeb  call    cs:__imp_WdLogSingleEntry0
0x1401fcdf2  nop     dword ptr [rax+rax+00h]
0x1401fcdf7  mov     [rsp+400h+var_3C0], r13
0x1401fcdfc  lea     r9, aFailedToAlloca_53; "Failed to allocate m_pGpuMmuCaps"
0x1401fce03  mov     qword ptr [rsp+400h+Depth], r13
0x1401fce08  mov     eax, 40Ch
0x1401fce0d  mov     qword ptr [rsp+400h+Tag], r13
0x1401fce12  mov     [rsp+400h+Size], r13
0x1401fce17  mov     qword ptr [rsp+400h+Flags], rax
0x1401fce1c  mov     cs:WdLogGlobalForLineNumber, eax
0x1401fce22  or      r8d, 0FFFFFFFFh
0x1401fce26  mov     edx, 40001h
0x1401fce2b  xor     ecx, ecx
0x1401fce2d  call    DxgkLogInternalTriageEvent
0x1401fce32  mov     ebx, 0C0000017h
0x1401fce37  lea     rcx, [rsp+400h+var_3A4]; this
0x1401fce3c  call    ??1DXGCRITICALREGION@@QEAA@XZ; DXGCRITICALREGION::~DXGCRITICALREGION(void)
0x1401fce41  jmp     loc_1401FE07E
0x1401fce46  xor     r8d, r8d
0x1401fce49  mov     r13d, 3Fh ; '?'
0x1401fce4f  mov     r14d, r8d
0x1401fce52  mov     [rsp+400h+var_3B0], r8d
0x1401fce57  mov     r12d, r8d
0x1401fce5a  cmp     r12d, ebx
0x1401fce5d  jnb     loc_1401FD194
0x1401fce63  mov     rcx, [rdi+10h]; this
0x1401fce67  mov     eax, r12d
0x1401fce6a  lea     rbx, [rax+rax*8]
0x1401fce6e  mov     eax, [rcx+0A24h]
0x1401fce74  shl     rbx, 4
0x1401fce78  add     rbx, [rdi+4F0h]
0x1401fce7f  test    al, 40h
0x1401fce81  jz      loc_1401FCFAE
0x1401fce87  lea     rax, [rbp+300h+var_380]
0x1401fce8b  mov     qword ptr [rbp+300h+var_310.Type], 0Dh
0x1401fce93  lea     rdx, [rbp+300h+var_310]; struct _DXGKARG_QUERYADAPTERINFO *
0x1401fce97  mov     [rbp+300h+var_310.pInputData], rax
0x1401fce9b  mov     qword ptr [rbp+300h+var_310.InputDataSize], 4
0x1401fcea3  mov     qword ptr [rbp+300h+var_310.Flags], r8
0x1401fcea7  mov     dword ptr [rbp+300h+var_310.hKmdProcessHandle+4], r8d
0x1401fceab  mov     [rbp+300h+var_310.pOutputData], rbx
0x1401fceaf  mov     [rbp+300h+var_310.OutputDataSize], 18h
0x1401fceb6  mov     [rbp+300h+var_380], r12d
0x1401fceba  call    ?DdiQueryAdapterInfo@DXGADAPTER@@QEAAJPEAU_DXGKARG_QUERYADAPTERINFO@@@Z; DXGADAPTER::DdiQueryAdapterInfo(_DXGKARG_QUERYADAPTERINFO *)
0x1401fcebf  xor     r8d, r8d
0x1401fcec2  test    eax, eax
0x1401fcec4  js      loc_1401FD138
0x1401fceca  mov     ecx, [rbx+8]
0x1401fcecd  test    r14d, r14d
0x1401fced0  jnz     short loc_1401FCEE4
0x1401fced2  lea     eax, [rcx-0Dh]
0x1401fced5  cmp     eax, 32h ; '2'
0x1401fced8  ja      loc_1401FCFCB
  ... truncated ...
```
