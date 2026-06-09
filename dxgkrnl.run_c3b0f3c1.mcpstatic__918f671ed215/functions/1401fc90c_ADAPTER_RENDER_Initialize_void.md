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
  unsigned __int64 v22; // rax
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
  unsigned __int64 v37; // r8
  unsigned __int16 *v38; // r13
  unsigned __int64 v39; // rbx
  unsigned __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // r15
  unsigned __int64 v43; // rax
  __int64 v44; // rax
  unsigned __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // r8
  int *v48; // rcx
  int v49; // eax
  __int64 v50; // r8
  DXGADAPTER *v51; // rcx
  unsigned int n; // r12d
  struct _DXGK_NODEMETADATA *v53; // r15
  __int64 v54; // r14
  __int64 v55; // rdx
  struct _DXGK_NODEMETADATA_FLAGS::$61C199033D6F6D75DA69F8EFC79E2D37::$C26580DEFEF05BED1260633B1DAE4A38 Value; // eax
  _DWORD *v57; // rcx
  DXGADAPTER *v58; // rcx
  __int128 v59; // xmm1
  int v60; // eax
  __int64 v61; // rbx
  struct DXGGLOBAL *Global; // rax
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // rax
  int SynchronizationObjectInternal; // eax
  int *v67; // rcx
  unsigned int NumDifferentPhysicalAdapters; // ebx
  __int64 m; // rcx
  unsigned int v70; // r12d
  unsigned __int64 v71; // rax
  _DWORD *v72; // rax
  __int64 v73; // r8
  _DWORD *v74; // r14
  unsigned int *v75; // rax
  DXGADAPTER *v76; // rcx
  char v77; // dl
  __int64 v78; // r15
  unsigned int v79; // ecx
  __int64 v80; // rbx
  const wchar_t *v81; // r9
  unsigned int v82; // [rsp+50h] [rbp-B0h] BYREF
  char v83; // [rsp+54h] [rbp-ACh]
  unsigned int AdapterInfo; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v85[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  int v86; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v87; // [rsp+68h] [rbp-98h]
  _WORD v88[4]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD *v89; // [rsp+78h] [rbp-88h]
  unsigned int v90; // [rsp+80h] [rbp-80h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v91[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v92; // [rsp+F0h] [rbp-10h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v93; // [rsp+120h] [rbp+20h] BYREF
  struct _DXGKARG_QUERYADAPTERINFO v94; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v95[2]; // [rsp+180h] [rbp+80h] BYREF
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
    v81 = L"Adapter 0x%I64x: Invalidly formatted user mode driver name, returning 0x%I64x";
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
    v81 = L"Adapter 0x%I64x: Invalidly formatted user mode display driver name, returning 0x%I64x";
    WdLogGlobalForLineNumber = 965;
LABEL_205:
    DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v81, *((_QWORD *)this + 2), -1073741438, 0, 0, 0);
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
  v85[1] = 0;
  DXGCRITICALREGION::Enter((DXGCRITICALREGION *)v85);
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
    v86 = v21;
    if ( !is_mul_ok(v21, 0x90u) )
      v22 = -1;
    v23 = operator new[](v22, 0x4B677844u, 256);
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
    v82 = 0;
    for ( i = 0; i < (unsigned int)v21; ++i )
    {
      v27 = (DXGADAPTER *)*((_QWORD *)this + 2);
      v21 = *((_QWORD *)this + 158) + 144LL * i;
      if ( (*((_DWORD *)v27 + 649) & 0x40) != 0 )
      {
        *(_QWORD *)&v92.Type = 13;
        v92.pInputData = &v90;
        *(_QWORD *)&v92.InputDataSize = 4;
        *(_QWORD *)&v92.Flags.0 = 0;
        HIDWORD(v92.hKmdProcessHandle) = 0;
        v92.pOutputData = (void *)v21;
        v92.OutputDataSize = 24;
        v90 = i;
        if ( (int)DXGADAPTER::DdiQueryAdapterInfo(v27, &v92, 0) < 0 )
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
            v82 = *(_DWORD *)(v21 + 8);
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
              v25 = v82;
              v13 = AdapterInfo;
              goto LABEL_59;
            }
            v93.pInputData = v88;
            v30 = (DXGADAPTER *)*((_QWORD *)this + 2);
            *(_QWORD *)&v93.Type = 14;
            *(_QWORD *)&v93.InputDataSize = 4;
            v93.hKmdProcessHandle = 0;
            v88[0] = j;
            v88[1] = i;
            v89 = (_DWORD *)(v21 + 4 * (j + 4LL * j + 6));
            v93.pOutputData = v89;
            *(_QWORD *)&v93.OutputDataSize = AdapterInfo < 0x5012 ? 16 : 20;
            if ( (int)DXGADAPTER::DdiQueryAdapterInfo(v30, &v93, 0) < 0 )
              break;
            if ( ((v89[4] - 1) & v89[4]) != 0 )
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
      LODWORD(v21) = v86;
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
    v82 = v34;
    if ( v34 >= DXGADAPTER::GetNumDifferentPhysicalAdapters(v35) )
    {
      if ( *(int *)(v36 + 2864) < 8960 )
        *(_DWORD *)(v36 + 2592) &= 0xFFFFF87F;
LABEL_163:
      v60 = DXGADAPTER::CheckMcdmDdiSubmission(*((DXGADAPTER **)this + 2));
      if ( v60 < 0 )
      {
LABEL_164:
        v12 = v60;
        goto LABEL_40;
      }
      if ( !*(_BYTE *)(*((_QWORD *)this + 2) + 209LL) )
      {
        v82 = 0;
        v60 = ADAPTER_RENDER::ConfigureSysMm(this, (union SYSMM_IOMMU_STATE *)&v82);
        if ( v60 < 0 )
          goto LABEL_164;
        v61 = *((_QWORD *)this + 92);
        Global = DXGGLOBAL::GetGlobal();
        v63 = (*(__int64 (__fastcall **)(ADAPTER_RENDER *, _QWORD, __int64))(*(_QWORD *)(v61 + 8) + 24LL))(
                this,
                *(_QWORD *)(*((_QWORD *)this + 2) + 216LL),
                (__int64)Global + 152);
        *((_QWORD *)this + 93) = v63;
        if ( !v63 )
          goto LABEL_39;
        v64 = 0;
        if ( (v82 & 1) != 0 )
        {
          v64 = 1;
          if ( (v82 & 2) != 0 )
            v64 = 3;
        }
        v65 = (*(__int64 (__fastcall **)(ADAPTER_RENDER *, __int64))(*(_QWORD *)(*((_QWORD *)this + 95) + 8LL) + 8LL))(
                this,
                v64);
        *((_QWORD *)this + 96) = v65;
        if ( !v65 )
          goto LABEL_39;
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)(*((_QWORD *)this + 92) + 8LL) + 32LL))(
          *((_QWORD *)this + 93),
          v65);
        (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 95) + 8LL) + 16LL))(
          *((_QWORD *)this + 96),
          *((_QWORD *)this + 93));
      }
      memset(v91, 0, sizeof(v91));
      v91[0].pInputData = (void *)0x100000003LL;
      SynchronizationObjectInternal = CreateSynchronizationObjectInternal(
                                        0,
                                        1,
                                        this,
                                        (__int64)v91,
                                        11,
                                        0,
                                        (DXGSYNCOBJECT **)this + 113,
                                        0,
                                        0);
      v54 = SynchronizationObjectInternal;
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
          v54,
          0,
          0,
          0);
LABEL_153:
        v12 = v54;
        goto LABEL_40;
      }
      v67 = (int *)*((_QWORD *)this + 2);
      if ( v67[716] < 4864 )
        goto LABEL_202;
      NumDifferentPhysicalAdapters = DXGADAPTER::GetNumDifferentPhysicalAdapters((DXGADAPTER *)v67);
      LODWORD(v87) = NumDifferentPhysicalAdapters;
      v82 = 0;
      for ( m = 0; ; m = ++v82 )
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
          DXGCRITICALREGION::~DXGCRITICALREGION((DXGCRITICALREGION *)v85);
          return 0;
        }
        v70 = *(unsigned __int16 *)(352 * m + *(_QWORD *)(*((_QWORD *)this + 2) + 3120LL));
        v71 = 4LL * *(unsigned __int16 *)(352 * m + *(_QWORD *)(*((_QWORD *)this + 2) + 3120LL));
        if ( !is_mul_ok(*(unsigned __int16 *)(352 * m + *(_QWORD *)(*((_QWORD *)this + 2) + 3120LL)), 4u) )
          v71 = -1;
        v72 = (_DWORD *)operator new[](v71, 0x4B677844u, 64);
        v74 = v72;
        if ( !v72 )
          goto LABEL_39;
        v86 = v82;
        v91[0].pOutputData = v72;
        v91[0].OutputDataSize = 4 * v70;
        v75 = &v82;
        v76 = (DXGADAPTER *)*((_QWORD *)this + 2);
        if ( NumDifferentPhysicalAdapters <= 1 )
          v75 = (unsigned int *)&v86;
        *(_QWORD *)&v91[0].Type = 10;
        *(_QWORD *)&v91[0].InputDataSize = 4;
        *(_QWORD *)&v91[0].Flags.0 = 0;
        HIDWORD(v91[0].hKmdProcessHandle) = 0;
        v91[0].pInputData = v75;
        AdapterInfo = DXGADAPTER::DdiQueryAdapterInfo(v76, v91, v73);
        if ( (AdapterInfo & 0x80000000) != 0 )
          goto LABEL_193;
        v77 = 1;
        if ( !v70 )
        {
          v2 = 0;
          goto LABEL_196;
        }
        v78 = 0;
        do
        {
          v79 = v74[v78];
          if ( v79 - 1 <= 0x1E || v79 >= 0x41 )
          {
            v80 = (unsigned int)v74[v78];
            WdLogSingleEntry3(2, this, v80, v78);
            WdLogGlobalForLineNumber = 1557;
            DxgkLogInternalTriageEvent(
              0,
              0x40000,
              -1,
              (unsigned int)L"Adapter 0x%I64x: Invalid timestamp precision. Valid domain is {0, [32-64]}. Precision=%d, Node=%d",
              (__int64)this,
              v80,
              v78,
              0,
              0);
            v77 = 0;
          }
          else if ( !v79 )
          {
            *((_BYTE *)this + 968) = 1;
          }
          ++v2;
          ++v78;
        }
        while ( v2 < v70 );
        v2 = 0;
        if ( !v77 )
        {
LABEL_193:
          DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v74);
          *((_BYTE *)this + 968) = 0;
          if ( (AdapterInfo & 0x80000000) == 0 )
          {
            v12 = -1073741438;
            WdLogSingleEntry2(2, this, -1073741438);
            v19 = L"Adapter 0x%I64x: Precision data is bad. Returning 0x%I64x";
            WdLogGlobalForLineNumber = 1597;
            goto LABEL_70;
          }
          v74 = 0;
          WdLogSingleEntry1(4, this);
          WdLogGlobalForLineNumber = 1589;
        }
LABEL_196:
        NumDifferentPhysicalAdapters = v87;
        *(_QWORD *)(352LL * v82 + *(_QWORD *)(*((_QWORD *)this + 2) + 3120LL) + 40) = v74;
      }
    }
    v38 = (unsigned __int16 *)(*(_QWORD *)(v36 + 3120) + 352LL * v34);
    AdapterInfo = *v38;
    v39 = AdapterInfo;
    v40 = 74LL * AdapterInfo;
    if ( !is_mul_ok(AdapterInfo, 0x4Au) )
      v40 = v37;
    v41 = operator new[](v40, 0x4B677844u, 256);
    v87 = v41;
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
    v89 = (_DWORD *)*((_QWORD *)this + 2);
    v43 = 44 * v39;
    if ( !is_mul_ok(v39, 0x2Cu) )
      v43 = -1;
    v44 = operator new[](v43, 0x4B677844u, 256);
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
    v46 = operator new[](v45, 0x4B677844u, 256);
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
    v48 = (int *)*((_QWORD *)this + 2);
    if ( v48[783] >= 2400 )
    {
      v86 = v34;
      v91[0].pInputData = &v86;
      *(_QWORD *)&v91[0].Type = 26;
      v91[0].pOutputData = v38 + 92;
      *(_QWORD *)&v91[0].InputDataSize = 4;
      *(_QWORD *)&v91[0].Flags.0 = 0;
      HIDWORD(v91[0].hKmdProcessHandle) = 0;
      v91[0].OutputDataSize = 28;
      v49 = DXGADAPTER::DdiQueryAdapterInfo((DXGADAPTER *)v48, v91, v47);
      if ( (int)(v49 + 0x80000000) >= 0 && v49 != -1073741637 )
      {
        WdLogSingleEntry1(3, this);
        WdLogGlobalForLineNumber = 1229;
      }
      v51 = (DXGADAPTER *)*((_QWORD *)this + 2);
      v91[0].pOutputData = v38 + 106;
      v91[0].Type = DXGKQAITYPE_GPUVERSION;
      v91[0].OutputDataSize = 128;
      if ( (int)DXGADAPTER::DdiQueryAdapterInfo(v51, v91, v50) < 0 )
      {
        WdLogSingleEntry1(3, this);
        WdLogGlobalForLineNumber = 1239;
      }
    }
    v83 = 0;
    for ( n = 0; n < AdapterInfo; ++n )
    {
      v53 = (struct _DXGK_NODEMETADATA *)(74LL * n + v42);
      LODWORD(v54) = DXGADAPTER::DdiGetNodeMetadata(*((DXGADAPTER **)this + 2), n | (v82 << 16), v53);
      if ( (int)v54 < 0 )
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
      v55 = *((_QWORD *)this + 2);
      if ( *(_DWORD *)(v55 + 2408) < 0x9000u )
      {
        v53->Flags.Value = 0;
        v42 = v87;
        goto LABEL_115;
      }
      if ( (*(_BYTE *)&v53->Flags.0 & 1) != 0 )
      {
        if ( !v53->IoMmuSupported && !*((_BYTE *)v38 + 49) )
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
        if ( (**(_DWORD **)(v55 + 3136) & 0x20000) == 0 )
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
      Value = (struct _DXGK_NODEMETADATA_FLAGS::$61C199033D6F6D75DA69F8EFC79E2D37::$C26580DEFEF05BED1260633B1DAE4A38)v53->Flags.Value;
      if ( (*(_BYTE *)&Value & 8) != 0 )
      {
        if ( *(int *)(v55 + 3132) < 3100 )
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
        if ( (**(_DWORD **)(v55 + 3136) & 0x8000000) == 0 )
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
        if ( (v89[648] & 0x800) == 0 )
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
        if ( !*(_QWORD *)(v55 + 1528)
          || !*(_QWORD *)(v55 + 1552)
          || !*(_QWORD *)(v55 + 1536)
          || !*(_QWORD *)(v55 + 1544)
          || !*(_QWORD *)(v55 + 1560) )
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
        v83 = 1;
LABEL_113:
        v42 = v87;
        goto LABEL_114;
      }
      if ( !*((_BYTE *)DXGGLOBAL::GetGlobal() + 305952) )
        goto LABEL_113;
      v42 = v87;
      if ( (*(_BYTE *)(74LL * n + v87 + 68) & 1) != 0 )
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
      v57 = v89;
      if ( *(_BYTE *)(74LL * n + v42 + 72) )
      {
        if ( (v89[649] & 0x40) == 0 )
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
        if ( (v57[649] & 0x80u) == 0 )
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
    if ( !v83 )
    {
LABEL_139:
      v34 = v82 + 1;
      continue;
    }
    break;
  }
  v58 = (DXGADAPTER *)*((_QWORD *)this + 2);
  memset(v95, 0, 28);
  memset(&v94, 0, 24);
  v94.Type = DXGKQAITYPE_NUMPOWERCOMPONENTS|0x20;
  v94.pOutputData = v95;
  *(_OWORD *)&v94.OutputDataSize = 0;
  v94.OutputDataSize = 28;
  v12 = DXGADAPTER::DdiQueryAdapterInfo(v58, &v94, v47);
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
    if ( (unsigned int)(DWORD1(v95[0]) - 1) > 0xFFF )
    {
      WdLogSingleEntry2(2, DWORD1(v95[0]), 4096);
      WdLogGlobalForLineNumber = 1397;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DoorbellSize (0x%u) must be greater than 0 and less than 0x%u.",
        DWORD1(v95[0]),
        4096,
        0,
        0,
        0);
    }
    else if ( (v95[0] & 0xFFFFFFFE) != 0 )
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
      if ( (v95[0] & 1) == 0 || (unsigned int)(DWORD2(v95[0]) - 1) <= 0xFFF )
      {
        v59 = *(_OWORD *)((char *)v95 + 12);
        *(_OWORD *)((char *)this + 1272) = v95[0];
        *(_OWORD *)((char *)this + 1284) = v59;
        goto LABEL_139;
      }
      WdLogSingleEntry2(2, DWORD2(v95[0]), 4096);
      WdLogGlobalForLineNumber = 1414;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"SecondaryDoorbellSize (0x%u) must be greater than 0 and less than 0x%u.",
        DWORD2(v95[0]),
        4096,
        0,
        0,
        0);
    }
LABEL_64:
    v12 = -1073741811;
  }
LABEL_40:
  DXGCRITICALREGION::~DXGCRITICALREGION((DXGCRITICALREGION *)v85);
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
