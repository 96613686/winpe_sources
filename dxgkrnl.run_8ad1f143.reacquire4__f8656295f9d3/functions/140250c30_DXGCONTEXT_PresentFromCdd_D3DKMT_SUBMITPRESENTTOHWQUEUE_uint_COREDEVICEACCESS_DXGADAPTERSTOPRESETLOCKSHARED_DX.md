# DXGCONTEXT::PresentFromCdd(_D3DKMT_SUBMITPRESENTTOHWQUEUE *,uint,COREDEVICEACCESS *,DXGADAPTERSTOPRESETLOCKSHARED *,DXGCONTEXT * *)

- ea: `0x140250c30`
- end: `0x1402521dc`
- name: `?PresentFromCdd@DXGCONTEXT@@QEAAJPEAU_D3DKMT_SUBMITPRESENTTOHWQUEUE@@IPEAVCOREDEVICEACCESS@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAPEAV1@@Z`
- size: `5548`
- prototype: `__int64 __usercall@<rax>(DXGCONTEXT *__hidden this@<rcx>, struct _D3DKMT_SUBMITPRESENTTOHWQUEUE *@<rdx>, unsigned int@<r8d>, struct COREDEVICEACCESS *@<r9>, struct DXGADAPTERSTOPRESETLOCKSHARED *, struct DXGCONTEXT **)`
- caller_count: `3`
- callee_count: `41`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401977b0`
- `0x1401aa504`
- `0x1402103f0`

## callees

- `0x140012380`
- `0x140014790`
- `0x140014c4c`
- `0x1400158b0`
- `0x140015dbc`
- `0x140016830`
- `0x14001b890`
- `0x14001c490`
- `0x14001d070`
- `0x14001e47c`
- `0x14001e8dc`
- `0x14001f120`
- `0x14002d9f0`
- `0x14002da40`
- `0x140033e60`
- `0x140034740`
- `0x1400391ac`
- `0x14003c104`
- `0x140040a68`
- `0x1400475cc`
- `0x140049224`
- `0x14004f3ec`
- `0x1400555e4`
- `0x140079990`
- `0x1400a0100`
- `0x1400a01e0`
- `0x1400a0240`
- `0x1400a0540`
- `0x140250c30`
- `0x140252dac`
- `0x140313c5c`
- `0x140327c10`
- `0x140329000`
- `0x140383d54`
- `0x14038d6a0`
- `0x140390a24`
- `0x1403981a4`
- `0x1403a6b38`
- `0x1403d014c`
- `0x1403de9dc`
- `0x140403500`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140250f6f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402510f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140250f6f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402510f4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140250f63`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1402510e8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140250f63`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1402510e8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140250c91`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140250c91`
- `watchdog!WdLogSingleEntry4` at `0x140251351`
- `watchdog!WdLogSingleEntry4` at `0x14025148c`
- `watchdog!WdLogSingleEntry4` at `0x1402515cc`
- `watchdog!WdLogSingleEntry4` at `0x140251351`
- `watchdog!WdLogSingleEntry4` at `0x14025148c`
- `watchdog!WdLogSingleEntry4` at `0x1402515cc`
- `watchdog!WdLogSingleEntry2` at `0x1402512eb`
- `watchdog!WdLogSingleEntry2` at `0x1402512eb`
- `watchdog!WdLogSingleEntry3` at `0x14025111b`
- `watchdog!WdLogSingleEntry3` at `0x14025144d`
- `watchdog!WdLogSingleEntry3` at `0x14025111b`
- `watchdog!WdLogSingleEntry3` at `0x14025144d`
- `watchdog!WdLogSingleEntry0` at `0x140250da9`
- `watchdog!WdLogSingleEntry0` at `0x140250e00`
- `watchdog!WdLogSingleEntry0` at `0x140250f05`
- `watchdog!WdLogSingleEntry0` at `0x140251083`
- `watchdog!WdLogSingleEntry0` at `0x140251241`
- `watchdog!WdLogSingleEntry0` at `0x140251646`
- `watchdog!WdLogSingleEntry0` at `0x1402516a1`
- `watchdog!WdLogSingleEntry0` at `0x1402516f4`
- `watchdog!WdLogSingleEntry0` at `0x140251745`
- `watchdog!WdLogSingleEntry0` at `0x1402517b5`
- `watchdog!WdLogSingleEntry0` at `0x140251808`
- `watchdog!WdLogSingleEntry0` at `0x140251859`
- `watchdog!WdLogSingleEntry0` at `0x1402518c0`
- `watchdog!WdLogSingleEntry0` at `0x140251978`
- `watchdog!WdLogSingleEntry0` at `0x1402519ce`
- `watchdog!WdLogSingleEntry0` at `0x140251a25`
- `watchdog!WdLogSingleEntry0` at `0x140251a7e`
- `watchdog!WdLogSingleEntry0` at `0x140251ad5`
- `watchdog!WdLogSingleEntry0` at `0x140251b2c`
- `watchdog!WdLogSingleEntry0` at `0x140251bbe`
- `watchdog!WdLogSingleEntry0` at `0x140251c17`
- `watchdog!WdLogSingleEntry0` at `0x140251c7b`
- `watchdog!WdLogSingleEntry0` at `0x140251cd3`
- `watchdog!WdLogSingleEntry0` at `0x140251d2b`
- `watchdog!WdLogSingleEntry0` at `0x140251d83`
- `watchdog!WdLogSingleEntry0` at `0x140251de2`
- `watchdog!WdLogSingleEntry0` at `0x1402520d8`
- `watchdog!WdLogSingleEntry0` at `0x140250da9`
- `watchdog!WdLogSingleEntry0` at `0x140250e00`
- `watchdog!WdLogSingleEntry0` at `0x140250f05`
- `watchdog!WdLogSingleEntry0` at `0x140251083`
- `watchdog!WdLogSingleEntry0` at `0x140251241`
- `watchdog!WdLogSingleEntry0` at `0x140251646`
- `watchdog!WdLogSingleEntry0` at `0x1402516a1`
- `watchdog!WdLogSingleEntry0` at `0x1402516f4`
- `watchdog!WdLogSingleEntry0` at `0x140251745`
- `watchdog!WdLogSingleEntry0` at `0x1402517b5`
- `watchdog!WdLogSingleEntry0` at `0x140251808`
- `watchdog!WdLogSingleEntry0` at `0x140251859`
- `watchdog!WdLogSingleEntry0` at `0x1402518c0`
- `watchdog!WdLogSingleEntry0` at `0x140251978`
- `watchdog!WdLogSingleEntry0` at `0x1402519ce`
- `watchdog!WdLogSingleEntry0` at `0x140251a25`
- `watchdog!WdLogSingleEntry0` at `0x140251a7e`
- `watchdog!WdLogSingleEntry0` at `0x140251ad5`
- `watchdog!WdLogSingleEntry0` at `0x140251b2c`
- `watchdog!WdLogSingleEntry0` at `0x140251bbe`
- `watchdog!WdLogSingleEntry0` at `0x140251c17`
- `watchdog!WdLogSingleEntry0` at `0x140251c7b`
- `watchdog!WdLogSingleEntry0` at `0x140251cd3`
- `watchdog!WdLogSingleEntry0` at `0x140251d2b`
- `watchdog!WdLogSingleEntry0` at `0x140251d83`
- `watchdog!WdLogSingleEntry0` at `0x140251de2`
- `watchdog!WdLogSingleEntry0` at `0x1402520d8`
- `watchdog!WdLogSingleEntry5` at `0x140250fab`
- `watchdog!WdLogSingleEntry5` at `0x140252155`
- `watchdog!WdLogSingleEntry5` at `0x140250fab`
- `watchdog!WdLogSingleEntry5` at `0x140252155`
- `watchdog!WdLogSingleEntry1` at `0x140250cb9`
- `watchdog!WdLogSingleEntry1` at `0x140250cb9`

## string_xrefs

- `0x140250cca`: `Failed to allocate memory for present parameters. Returing 0x%I64x`

## pseudocode

```c
__int64 __fastcall DXGCONTEXT::PresentFromCdd(
        DXGCONTEXT *this,
        struct _D3DKMT_SUBMITPRESENTTOHWQUEUE *a2,
        unsigned int a3,
        struct COREDEVICEACCESS *a4,
        struct DXGADAPTERSTOPRESETLOCKSHARED *a5,
        struct DXGCONTEXT **a6)
{
  DXGCONTEXT *v7; // rsi
  struct _LOOKASIDE_LIST_EX *Global; // rax
  unsigned int *v9; // rax
  unsigned int *v10; // rdi
  int v11; // ebx
  D3DKMT_HANDLE v12; // edx
  __int64 v13; // rcx
  ADAPTER_DISPLAY *v14; // rax
  __int64 v15; // r9
  unsigned int *v16; // r13
  unsigned int v17; // ecx
  unsigned int v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // r8
  int v21; // ecx
  struct DXGALLOCATION *v22; // rdx
  unsigned int v23; // ebx
  unsigned int v24; // eax
  __int64 v25; // r8
  int v26; // ecx
  struct DXGALLOCATION *v27; // rdx
  struct VIDSCH_SUBMIT_DATA_BASE *v28; // rax
  DXGPRESENT *v29; // rax
  DXGPRESENT *v30; // rax
  struct VIDSCH_SUBMIT_DATA_BASE *v31; // rdx
  int v32; // ecx
  __int64 v33; // rax
  struct VIDMM_DMA_POOL *v34; // rdx
  COREDEVICEACCESS *v35; // r12
  int v36; // eax
  struct DXGPRESENTMUTEX *v37; // r8
  const char *v38; // rdx
  unsigned __int8 v39; // bl
  __int64 v40; // r12
  const RECT **v41; // r12
  int updated; // eax
  __int64 v43; // rcx
  UINT v44; // eax
  ADAPTER_DISPLAY *v45; // r13
  int CurrentOrientation; // eax
  UINT Value; // eax
  unsigned int v48; // ecx
  const RECT *DdiSubRectList; // r15
  __int64 v50; // rbx
  UINT v51; // r13d
  int v52; // edi
  __int64 v53; // rbx
  LONG v54; // r8d
  LONG v55; // edx
  UINT i; // r15d
  char v57; // r12
  __int64 v58; // rdx
  char v59; // r13
  const RECT *pDstSubRects; // r15
  UINT SubRectCnt; // r14d
  UINT v62; // ebx
  int v63; // esi
  unsigned int v64; // r9d
  UINT v65; // r8d
  unsigned int v66; // r10d
  __int64 v67; // rcx
  struct COREDEVICEACCESS *v68; // r14
  int v70; // [rsp+28h] [rbp-F8h]
  int v71; // [rsp+40h] [rbp-E0h]
  unsigned int v73; // [rsp+A0h] [rbp-80h]
  struct VIDMM_DMA_BUFFER *v74; // [rsp+A8h] [rbp-78h] BYREF
  volatile signed __int32 *v75; // [rsp+B0h] [rbp-70h] BYREF
  struct VIDSCH_SUBMIT_DATA_BASE *v76[2]; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v77; // [rsp+C8h] [rbp-58h] BYREF
  struct VIDMM_DMA_BUFFER *v78; // [rsp+D0h] [rbp-50h]
  unsigned int *v79; // [rsp+D8h] [rbp-48h] BYREF
  ADAPTER_DISPLAY *v80; // [rsp+E0h] [rbp-40h]
  union _LARGE_INTEGER v81; // [rsp+E8h] [rbp-38h] BYREF
  struct DXGHWQUEUE *v82; // [rsp+F0h] [rbp-30h] BYREF
  DXGCONTEXT *v83; // [rsp+F8h] [rbp-28h]
  COREDEVICEACCESS *v84; // [rsp+100h] [rbp-20h]
  DXGADAPTERSTOPRESETLOCKSHARED *v85; // [rsp+108h] [rbp-18h]
  _BYTE v86[16]; // [rsp+110h] [rbp-10h] BYREF
  _BYTE v87[24]; // [rsp+120h] [rbp+0h] BYREF
  unsigned int *v88; // [rsp+138h] [rbp+18h]
  struct _DXGKARG_PRESENT v89; // [rsp+140h] [rbp+20h] BYREF
  _DWORD v90[16]; // [rsp+1F0h] [rbp+D0h] BYREF
  _DWORD v91[16]; // [rsp+230h] [rbp+110h] BYREF
  _DWORD v92[16]; // [rsp+270h] [rbp+150h] BYREF
  _DWORD v93[16]; // [rsp+2B0h] [rbp+190h] BYREF

  v85 = a5;
  v7 = this;
  v81.QuadPart = (LONGLONG)a6;
  v84 = a4;
  v83 = this;
  Global = (struct _LOOKASIDE_LIST_EX *)DXGGLOBAL::GetGlobal();
  v9 = (unsigned int *)ExAllocateFromLookasideListEx(Global + 12);
  v88 = v9;
  v10 = v9;
  if ( v9 )
  {
    memset(v9, 0, 0x5F8u);
    v79 = v10;
    v82 = 0;
    memmove(v10, &a2->PrivatePresentData, 0x5D8u);
    *((_QWORD *)v10 + 188) = &v82;
    if ( a2->hHwQueues )
      v12 = *a2->hHwQueues;
    else
      v12 = 0;
    DXGHWQUEUEBYHANDLE::DXGHWQUEUEBYHANDLE(
      (DXGHWQUEUEBYHANDLE *)v86,
      v12,
      *(struct DXGPROCESS **)(*((_QWORD *)v7 + 2) + 40LL),
      &v82,
      1,
      1);
    v13 = *((_QWORD *)v7 + 2);
    v78 = *(struct VIDMM_DMA_BUFFER **)(*(_QWORD *)(v13 + 40) + 88LL);
    v14 = *(ADAPTER_DISPLAY **)(*(_QWORD *)(v13 + 1896) + 3232LL);
    v80 = v14;
    if ( !v14 || !ADAPTER_DISPLAY::IsCoreResourceSharedOwner(v14) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 7045;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"(pDisplayCore != NULL) && pDisplayCore->IsCoreResourceSharedOwner()",
        7045,
        0,
        0,
        0,
        0);
    }
    if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(*(ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL)) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 7046;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
        7046,
        0,
        0,
        0,
        0);
    }
    v15 = *((_QWORD *)v10 + 9);
    if ( !v15
      || (v16 = v10 + 16, !v10[16])
      || (v17 = v10[22], (((unsigned __int8)v17 ^ (unsigned __int8)(v17 >> 1)) & 1) == 0)
      || (v17 & 0x63C) != 0 )
    {
      v11 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, v7, v15, v10[16], v10[22]);
      WdLogGlobalForLineNumber = 7061;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"ret = 0x%I64x 0x%I64x failed with invalid parameters 0x%I64x 0x%I64x 0x%I64x",
        -1073741811,
        (__int64)v7,
        *((_QWORD *)v10 + 9),
        v10[16],
        v10[22]);
      goto LABEL_147;
    }
    memset(&v89, 0, sizeof(v89));
    v18 = v10[6];
    v76[0] = *(struct VIDSCH_SUBMIT_DATA_BASE **)(*((_QWORD *)v7 + 2) + 40LL);
    v75 = (volatile signed __int32 *)((char *)v76[0] + 248);
    DXGPUSHLOCK::AcquireShared((struct VIDSCH_SUBMIT_DATA_BASE *)((char *)v76[0] + 248));
    v19 = (v18 >> 6) & 0xFFFFFF;
    if ( v19 < *((_DWORD *)v76[0] + 74) )
    {
      v20 = *((_QWORD *)v76[0] + 35);
      if ( ((v18 >> 25) & 0x60) == (*(_BYTE *)(v20 + 16LL * v19 + 8) & 0x60)
        && (*(_DWORD *)(v20 + 16LL * v19 + 8) & 0x2000) == 0 )
      {
        v21 = *(_DWORD *)(v20 + 16LL * v19 + 8) & 0x1F;
        if ( v21 )
        {
          if ( v21 == 5 )
          {
            v22 = *(struct DXGALLOCATION **)(v20 + 16LL * v19);
LABEL_22:
            DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v77, v22);
            _InterlockedDecrement(v75 + 4);
            ExReleasePushLockSharedEx(v75, 0);
            KeLeaveCriticalRegion();
            if ( !v77 )
            {
              v11 = -1073741811;
              WdLogSingleEntry5(2, -1073741811, v7, *((_QWORD *)v10 + 9), *v16, v10[6]);
              WdLogGlobalForLineNumber = 7074;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"0x%I64x 0x%I64x fails Present invalid parameters 0x%I64x 0x%I64x 0x%I64x",
                -1073741811,
                (__int64)v7,
                *((_QWORD *)v10 + 9),
                *v16,
                v10[6]);
LABEL_24:
              DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v77);
LABEL_147:
              DXGHWQUEUEBYHANDLE::~DXGHWQUEUEBYHANDLE((DXGHWQUEUEBYHANDLE *)v86);
              DXGADAPTER::SubmitPresentHistoryTokenFromVm_::_45_::ENSURE_DELETE::_ENSURE_DELETE(&v79);
              return (unsigned int)v11;
            }
            if ( (v10[22] & 1) == 0 )
            {
LABEL_38:
              if ( !*((_QWORD *)v7 + 19) )
              {
                v29 = (DXGPRESENT *)DXGQUOTAALLOCATOR<256,1265072196>::operator new(1648);
                if ( v29 )
                {
                  v30 = DXGPRESENT::DXGPRESENT(v29, 1u);
                  *((_QWORD *)v7 + 19) = v30;
                  if ( v30 )
                    goto LABEL_41;
                }
                else
                {
                  *((_QWORD *)v7 + 19) = 0;
                }
                v11 = -1073741801;
                WdLogSingleEntry4(
                  6,
                  -1073741801,
                  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL),
                  *(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL),
                  v7);
                WdLogGlobalForLineNumber = 7101;
                DxgkLogInternalTriageEvent(
                  0,
                  262145,
                  -1,
                  (unsigned int)L"0x%I64x Out of memory allocating DXGPRESENT, 0x%I64x 0x%I64x 0x%I64x",
                  -1073741801,
                  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 16LL),
                  *(_QWORD *)(*((_QWORD *)v7 + 2) + 40LL),
                  (__int64)v7,
                  0);
                goto LABEL_24;
              }
LABEL_41:
              CVidSchSubmitData::CVidSchSubmitData(
                (CVidSchSubmitData *)v76,
                *(struct ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL),
                1);
              v31 = v76[0];
              if ( !v76[0] )
              {
                WdLogSingleEntry0(6);
                WdLogGlobalForLineNumber = 7110;
                DxgkLogInternalTriageEvent(
                  0,
                  262145,
                  -1,
                  (unsigned int)L"Failed to allocate VidSchSubmitData",
                  7110,
                  0,
                  0,
                  0,
                  0);
                CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v76);
                v11 = -1073741801;
                goto LABEL_24;
              }
              *(_DWORD *)v76[0] |= 0x10000u;
              v32 = *(_DWORD *)v31;
              if ( (v10[22] & 0x4000) == 0 )
                v32 |= 1u;
              *(_DWORD *)v31 = v32 | 0x100;
              v33 = *((_QWORD *)v7 + 2);
              v34 = (struct VIDMM_DMA_POOL *)*((_QWORD *)v7 + 29);
              v74 = 0;
              v11 = VIDMM_EXPORT::VidMmAcquireDmaBuffer(
                      *(VIDMM_EXPORT **)(*(_QWORD *)(v33 + 16) + 760LL),
                      v34,
                      0,
                      1,
                      &v74);
              if ( v11 < 0 )
                goto LABEL_76;
              if ( !v74 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 7128;
                DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pVidMmDmaBuffer", 7128, 0, 0, 0, 0);
              }
              DXGPRESENTMUTEX::DXGPRESENTMUTEX(
                (DXGPRESENTMUTEX *)v87,
                *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
              if ( (v10[22] & 0x4000) == 0 )
              {
                v35 = v84;
                COREDEVICEACCESS::Release(v84);
                DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v85);
                DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v87);
                DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v85);
                v36 = COREDEVICEACCESS::AcquireShared(v35, 0);
                v11 = v36;
                if ( v36 < 0 )
                {
                  WdLogSingleEntry2(4, v36);
                  WdLogGlobalForLineNumber = 7146;
                  COREDEVICEACCESS::AcquireSharedUncheck(v35, v38);
                  VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                    *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                    v74);
LABEL_75:
                  DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v87);
LABEL_76:
                  CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v76);
                  goto LABEL_24;
                }
                v39 = 0;
                if ( v78 )
                {
                  v40 = *((_QWORD *)v7 + 19);
                  if ( *(_DWORD *)(v40 + 8) != (*((unsigned int (**)(void))v78 + 1))() )
                  {
                    *(_DWORD *)(v40 + 8) = (*((__int64 (**)(void))v78 + 1))();
                    DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 2, 4294967293LL);
                    v39 = 1;
                  }
                }
                DXGDEVICE::SynchronizePresentToPrimary(*((DXGDEVICE **)v7 + 2), v7, v37, v39);
              }
              if ( (v10[22] & 1) == 0 || v10[5] == v10[6] )
              {
                v41 = (const RECT **)(v10 + 18);
              }
              else
              {
                v41 = (const RECT **)(v10 + 18);
                if ( (*(_DWORD *)(*(_QWORD *)(v77 + 48) + 4LL) & 2) != 0 )
                {
                  updated = DxgkCddUpdatePresentRects(v80, a3, (const struct tagRECT **)v10 + 9, v10 + 16);
                  v11 = updated;
                  if ( updated < 0 )
                  {
                    WdLogSingleEntry3(4, updated, *((_QWORD *)v7 + 2), a3);
                    WdLogGlobalForLineNumber = 7184;
                    v43 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
LABEL_74:
                    VIDMM_EXPORT::VidMmReleaseDmaBuffer(*(VIDMM_EXPORT **)(v43 + 760), v74);
                    v74 = 0;
                    goto LABEL_75;
                  }
                  if ( !*v16 )
                  {
                    WdLogSingleEntry4(4, 0, *((_QWORD *)v7 + 2), v10[6], a3);
                    WdLogGlobalForLineNumber = 7199;
                    VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                      *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                      v74);
                    v74 = 0;
                    DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v87);
                    CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v76);
                    v11 = 0;
                    goto LABEL_24;
                  }
                }
              }
              v11 = DXGPRESENT::GrowRectList(*((DXGPRESENT **)v7 + 19), *v16);
              if ( v11 < 0 )
              {
LABEL_73:
                v43 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
                goto LABEL_74;
              }
              v89.DstRect = (RECT)*((_OWORD *)v10 + 2);
              v44 = *v16;
              v45 = v80;
              v89.SubRectCnt = v44;
              if ( (v10[22] & 0x4000) != 0 )
              {
                Value = v89.Flags.Value;
              }
              else
              {
                CurrentOrientation = ADAPTER_DISPLAY::GetCurrentOrientation(v80, a3, 1);
                Value = (CurrentOrientation != 1 ? 0x80 : 0) | v89.Flags.Value & 0xFFFFFF7F;
                v89.Flags.Value = Value;
              }
              v48 = v10[22];
              if ( (v48 & 1) != 0 )
              {
                v89.Flags.Value = Value | 1;
                v89.SrcRect = (RECT)*((_OWORD *)v10 + 3);
                if ( v10[5] == v10[6] )
                {
                  if ( (v10[22] & 0x4000) == 0 && ADAPTER_DISPLAY::GetVidPnSourceOwnerType(v45, a3) )
                  {
                    v11 = -1071774910;
                    WdLogSingleEntry4(4, -1071774910, *((_QWORD *)v7 + 2), v10[6], a3);
                    WdLogGlobalForLineNumber = 7257;
                    goto LABEL_73;
                  }
                  DdiSubRectList = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
                  v89.pDstSubRects = DdiSubRectList;
                  if ( v89.DstRect.right - v89.DstRect.left != v89.SrcRect.right - v89.SrcRect.left )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7276;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.DstRect.right - PresentDdiArg.DstRect.left == PresentDdiArg.SrcRect.ri"
                                     "ght - PresentDdiArg.SrcRect.left",
                      7276,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v89.DstRect.bottom - v89.DstRect.top != v89.SrcRect.bottom - v89.SrcRect.top )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7279;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.DstRect.bottom - PresentDdiArg.DstRect.top == PresentDdiArg.SrcRect.bo"
                                     "ttom - PresentDdiArg.SrcRect.top",
                      7279,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v89.SrcRect.left >= v89.SrcRect.right )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7281;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.SrcRect.left < PresentDdiArg.SrcRect.right",
                      7281,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v89.SrcRect.left < 0 )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7282;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.SrcRect.left >= 0",
                      7282,
                      0,
                      0,
                      0,
                      0);
                  }
                  v50 = 4024LL * a3;
                  if ( v89.SrcRect.right > *(_DWORD *)(v50 + *((_QWORD *)v45 + 16) + 636)
                                         - *(_DWORD *)(v50 + *((_QWORD *)v45 + 16) + 628) )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7283;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.SrcRect.right <= pDisplayCore->GetContentRect(VidPnSourceId)->right - "
                                     "pDisplayCore->GetContentRect(VidPnSourceId)->left",
                      7283,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v89.DstRect.top >= v89.DstRect.bottom )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7285;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.DstRect.top < PresentDdiArg.DstRect.bottom",
                      7285,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v89.DstRect.top < 0 )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7286;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.DstRect.top >= 0",
                      7286,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v89.SrcRect.bottom > *(_DWORD *)(v50 + *((_QWORD *)v45 + 16) + 640)
                                          - *(_DWORD *)(v50 + *((_QWORD *)v45 + 16) + 632) )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7287;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.SrcRect.bottom <= pDisplayCore->GetContentRect(VidPnSourceId)->bottom "
                                     "- pDisplayCore->GetContentRect(VidPnSourceId)->top",
                      7287,
                      0,
                      0,
                      0,
                      0);
                  }
                  v51 = 0;
                  v73 = v89.DstRect.left - v89.SrcRect.left;
                  if ( v89.SubRectCnt )
                  {
                    v52 = v89.DstRect.top - v89.SrcRect.top;
                    do
                    {
                      v53 = v51;
                      v54 = v73 + (*v41)[v51].left;
                      DdiSubRectList[v53].left = v54;
                      v55 = v73 + (*v41)[v51].right;
                      DdiSubRectList[v53].right = v55;
                      DdiSubRectList[v53].top = v52 + (*v41)[v51].top;
                      DdiSubRectList[v53].bottom = v52 + (*v41)[v51].bottom;
                      if ( v54 >= v55 )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7299;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].left < pDstSubRects[i].right",
                          7299,
                          0,
                          0,
                          0,
                          0);
                      }
                      if ( DdiSubRectList[v51].left < v89.DstRect.left )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7300;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].left >= PresentDdiArg.DstRect.left",
                          7300,
                          0,
                          0,
                          0,
                          0);
                      }
                      if ( DdiSubRectList[v51].right > v89.DstRect.right )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7301;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].right <= PresentDdiArg.DstRect.right",
                          7301,
                          0,
                          0,
                          0,
                          0);
                      }
                      if ( DdiSubRectList[v51].top >= DdiSubRectList[v51].bottom )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7302;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].top < pDstSubRects[i].bottom",
                          7302,
                          0,
                          0,
                          0,
                          0);
                      }
                      if ( DdiSubRectList[v51].top < v89.DstRect.top )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7303;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].top >= PresentDdiArg.DstRect.top",
                          7303,
                          0,
                          0,
                          0,
                          0);
                      }
                      if ( DdiSubRectList[v51].bottom > v89.DstRect.bottom )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7304;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].bottom <= PresentDdiArg.DstRect.bottom",
                          7304,
                          0,
                          0,
                          0,
                          0);
                      }
                      ++v51;
                    }
                    while ( v51 < v89.SubRectCnt );
                    v10 = v88;
                    v7 = v83;
                  }
                }
                else
                {
                  v89.pDstSubRects = *v41;
                }
                for ( i = 0; i < v89.SubRectCnt; ++i )
                {
                  if ( (*v41)[i].left >= (*v41)[i].right )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7315;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"pPresent->pSrcSubRects[i].left < pPresent->pSrcSubRects[i].right",
                      7315,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( (*v41)[i].top >= (*v41)[i].bottom )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7316;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"pPresent->pSrcSubRects[i].top < pPresent->pSrcSubRects[i].bottom",
                      7316,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( (v10[22] & 0x4000) == 0 )
                  {
                    if ( (*v41)[i].left < v89.SrcRect.left )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 7321;
                      DxgkLogInternalTriageEvent(
                        0,
                        262146,
                        -1,
                        (unsigned int)L"pPresent->pSrcSubRects[i].left >= PresentDdiArg.SrcRect.left",
                        7321,
                        0,
                        0,
                        0,
                        0);
                    }
                    if ( (*v41)[i].right > v89.SrcRect.right )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 7322;
                      DxgkLogInternalTriageEvent(
                        0,
                        262146,
                        -1,
                        (unsigned int)L"pPresent->pSrcSubRects[i].right <= PresentDdiArg.SrcRect.right",
                        7322,
                        0,
                        0,
                        0,
                        0);
                    }
                    if ( (*v41)[i].top < v89.SrcRect.top )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 7323;
                      DxgkLogInternalTriageEvent(
                        0,
                        262146,
                        -1,
                        (unsigned int)L"pPresent->pSrcSubRects[i].top >= PresentDdiArg.SrcRect.top",
                        7323,
                        0,
                        0,
                        0,
                        0);
                    }
                    if ( (*v41)[i].bottom > v89.SrcRect.bottom )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 7324;
                      DxgkLogInternalTriageEvent(
                        0,
                        262146,
                        -1,
                        (unsigned int)L"pPresent->pSrcSubRects[i].bottom <= PresentDdiArg.SrcRect.bottom",
                        7324,
                        0,
                        0,
                        0,
                        0);
                    }
                  }
                }
              }
              else
              {
                if ( (v48 & 2) == 0 )
                {
                  WdLogSingleEntry0(1);
                  WdLogGlobalForLineNumber = 7331;
                  DxgkLogInternalTriageEvent(
                    0,
                    262146,
                    -1,
                    (unsigned int)L"pPresent->Flags.ColorFill",
                    7331,
                    0,
                    0,
                    0,
                    0);
                  Value = v89.Flags.Value;
                }
                v89.Flags.Value = Value | 2;
                v89.Color = v10[7];
                v89.pDstSubRects = *v41;
              }
              if ( !bTracingEnabled )
                goto LABEL_142;
              v57 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                       *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                       *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                       v10[6]);
              v59 = (unsigned __int8)VIDMM_EXPORT::VidMmETWAllocationHandle(
                                       *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                                       *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                                       v10[5]);
              pDstSubRects = v89.pDstSubRects;
              SubRectCnt = v89.SubRectCnt;
              v78 = v74;
              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
                McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                  v89.DstRect.top,
                  v89.DstRect.right,
                  v89.DstRect.left,
                  0,
                  (char)v78,
                  v70,
                  v59,
                  v57,
                  v71,
                  0,
                  *(_BYTE *)&v89.Flags.0,
                  v89.SrcRect.left,
                  v89.SrcRect.right,
                  v89.SrcRect.top,
                  v89.SrcRect.bottom,
                  v89.DstRect.left,
                  v89.DstRect.right,
                  v89.DstRect.top,
                  v89.DstRect.bottom,
                  v89.SubRectCnt);
              v62 = 0;
              if ( !SubRectCnt )
              {
LABEL_142:
                v68 = v84;
                v11 = DXGCONTEXT::SubmitPresent(
                        v7,
                        (const struct _D3DKMT_PRESENT *)v10,
                        *((struct DXGHWQUEUE ***)v10 + 188),
                        v10[23],
                        (struct DXGCONTEXT **)v81.QuadPart,
                        0,
                        v10[5],
                        v10[6],
                        &v89,
                        0,
                        v74,
                        v76[0],
                        D3DDDIFMT_A8B8G8R8,
                        v84);
                if ( v11 >= 0 && v10[90] == 1 )
                {
                  v81.QuadPart = -100000;
                  v11 = SubmitPresentHistoryToken(
                          (const struct _D3DKMT_PRESENTHISTORYTOKEN *)(v10 + 90),
                          v68,
                          v85,
                          0,
                          0,
                          &v81,
                          (struct DXGK_PRESENT_PARAMS *)v10,
                          0,
                          v7,
                          0,
                          0);
                }
                goto LABEL_75;
              }
              v63 = (int)v78;
              while ( 1 )
              {
                v64 = 0;
                v65 = SubRectCnt - v62;
                if ( SubRectCnt - v62 > 0x10 )
                  break;
                v66 = SubRectCnt - v62;
                if ( v65 )
                  goto LABEL_137;
LABEL_138:
                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                  McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                    (unsigned int)v93,
                    v58 * 2,
                    v65,
                    v63,
                    SubRectCnt - v62 <= 0x10,
                    v66,
                    (__int64)v93,
                    (__int64)v92,
                    (__int64)v91,
                    (__int64)v90);
                v62 += 16;
                if ( v62 >= SubRectCnt )
                {
                  v7 = v83;
                  goto LABEL_142;
                }
              }
              v66 = 16;
              do
              {
LABEL_137:
                v67 = v64;
                v58 = v64 + v62;
                ++v64;
                v93[v67] = pDstSubRects[v58].left;
                v92[v67] = pDstSubRects[v58].right;
                v91[v67] = pDstSubRects[v58].top;
                v90[v67] = pDstSubRects[v58].bottom;
              }
              while ( v64 < v66 );
              goto LABEL_138;
            }
            v23 = v10[5];
            v76[0] = *(struct VIDSCH_SUBMIT_DATA_BASE **)(*((_QWORD *)v7 + 2) + 40LL);
            DXGPUSHLOCK::AcquireShared((struct VIDSCH_SUBMIT_DATA_BASE *)((char *)v76[0] + 248));
            v24 = (v23 >> 6) & 0xFFFFFF;
            if ( v24 < *((_DWORD *)v76[0] + 74) )
            {
              v25 = *((_QWORD *)v76[0] + 35);
              if ( ((v23 >> 25) & 0x60) == (*(_BYTE *)(v25 + 16LL * v24 + 8) & 0x60)
                && (*(_DWORD *)(v25 + 16LL * v24 + 8) & 0x2000) == 0 )
              {
                v26 = *(_DWORD *)(v25 + 16LL * v24 + 8) & 0x1F;
                if ( v26 )
                {
                  if ( v26 == 5 )
                  {
                    v27 = *(struct DXGALLOCATION **)(v25 + 16LL * v24);
                    goto LABEL_34;
                  }
                  WdLogSingleEntry0(2);
                  WdLogGlobalForLineNumber = 318;
                  DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
                }
              }
            }
            v27 = 0;
LABEL_34:
            DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v75, v27);
            v28 = v76[0];
            _InterlockedDecrement((volatile signed __int32 *)v76[0] + 66);
            ExReleasePushLockSharedEx((char *)v28 + 248, 0);
            KeLeaveCriticalRegion();
            if ( !v75 )
            {
              v11 = -1073741811;
              WdLogSingleEntry3(2, -1073741811, v7, v10[5]);
              WdLogGlobalForLineNumber = 7087;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"0x%I64x 0x%I64x fails Present invalid source allocation 0x%I64x",
                -1073741811,
                (__int64)v7,
                v10[5],
                0,
                0);
              DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v75);
              goto LABEL_24;
            }
            DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v75);
            goto LABEL_38;
          }
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 318;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        }
      }
    }
    v22 = 0;
    goto LABEL_22;
  }
  v11 = -1073741801;
  WdLogSingleEntry1(6);
  WdLogGlobalForLineNumber = 7013;
  DxgkLogInternalTriageEvent(
    0,
    262145,
    -1,
    (unsigned int)L"Failed to allocate memory for present parameters. Returing 0x%I64x",
    -1073741801,
    0,
    0,
    0,
    0);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140250c30  push    rbp
0x140250c32  push    rbx
0x140250c33  push    rsi
0x140250c34  push    rdi
0x140250c35  push    r12
0x140250c37  push    r13
0x140250c39  push    r14
0x140250c3b  push    r15
0x140250c3d  lea     rbp, [rsp-1E8h]
0x140250c45  sub     rsp, 308h
0x140250c4c  mov     rax, cs:__security_cookie
0x140250c53  xor     rax, rsp
0x140250c56  mov     [rbp+220h+var_50], rax
0x140250c5d  mov     rax, [rbp+220h+arg_20]
0x140250c64  mov     rbx, rdx
0x140250c67  mov     [rbp+220h+var_238], rax
0x140250c6b  mov     rsi, rcx
0x140250c6e  mov     rax, [rbp+220h+arg_28]
0x140250c75  mov     qword ptr [rbp+220h+var_258], rax
0x140250c79  mov     [rbp+220h+var_240], r9
0x140250c7d  mov     [rbp+220h+var_2A0], r8d
0x140250c81  mov     [rbp+220h+var_248], rcx
0x140250c85  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x140250c8a  lea     rcx, [rax+480h]; Lookaside
0x140250c91  call    cs:__imp_ExAllocateFromLookasideListEx
0x140250c98  nop     dword ptr [rax+rax+00h]
0x140250c9d  xor     r15d, r15d
0x140250ca0  mov     [rbp+220h+var_208], rax
0x140250ca4  mov     rdi, rax
0x140250ca7  test    rax, rax
0x140250caa  jnz     short loc_140250D04
0x140250cac  mov     rbx, 0FFFFFFFFC0000017h
0x140250cb3  lea     ecx, [rax+6]
0x140250cb6  mov     rdx, rbx
0x140250cb9  call    cs:__imp_WdLogSingleEntry1
0x140250cc0  nop     dword ptr [rax+rax+00h]
0x140250cc5  mov     [rsp+340h+var_300], r15
0x140250cca  lea     r9, aFailedToAlloca_26; "Failed to allocate memory for present p"...
0x140250cd1  mov     [rsp+340h+var_308], r15
0x140250cd6  or      r8d, 0FFFFFFFFh
0x140250cda  mov     [rsp+340h+var_310], r15
0x140250cdf  mov     edx, 40001h
0x140250ce4  mov     [rsp+340h+var_318], r15
0x140250ce9  xor     ecx, ecx
0x140250ceb  mov     [rsp+340h+var_320], rbx
0x140250cf0  mov     cs:WdLogGlobalForLineNumber, 1B65h
0x140250cfa  call    DxgkLogInternalTriageEvent
0x140250cff  jmp     loc_1402521B6
0x140250d04  xor     edx, edx; Val
0x140250d06  mov     r8d, 5F8h; Size
0x140250d0c  mov     rcx, rdi; void *
0x140250d0f  call    memset
0x140250d14  mov     rcx, rdi; void *
0x140250d17  mov     [rbp+220h+var_268], rdi
0x140250d1b  lea     rdx, [rbx+8]; Src
0x140250d1f  mov     [rbp+220h+var_250], r15
0x140250d23  mov     r8d, 5D8h; Size
0x140250d29  call    memmove
0x140250d2e  lea     rax, [rbp+220h+var_250]
0x140250d32  mov     [rdi+5E0h], rax
0x140250d39  mov     rax, [rsi+10h]
0x140250d3d  mov     rdx, [rbx]
0x140250d40  mov     r8, [rax+28h]; struct DXGPROCESS *
0x140250d44  test    rdx, rdx
0x140250d47  jz      short loc_140250D4D
0x140250d49  mov     edx, [rdx]
0x140250d4b  jmp     short loc_140250D50
0x140250d4d  mov     edx, r15d; unsigned int
0x140250d50  mov     ebx, 1
0x140250d55  lea     r9, [rbp+220h+var_250]; struct DXGHWQUEUE **
0x140250d59  mov     byte ptr [rsp+340h+var_318], bl; bool
0x140250d5d  lea     rcx, [rbp+220h+var_230]; this
0x140250d61  mov     byte ptr [rsp+340h+var_320], bl; bool
0x140250d65  call    ??0DXGHWQUEUEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGHWQUEUE@@_N2@Z; DXGHWQUEUEBYHANDLE::DXGHWQUEUEBYHANDLE(uint,DXGPROCESS *,DXGHWQUEUE * *,bool,bool)
0x140250d6a  mov     rcx, [rsi+10h]
0x140250d6e  or      r14d, 0FFFFFFFFh
0x140250d72  mov     r12d, 40002h
0x140250d78  mov     rax, [rcx+28h]
0x140250d7c  mov     rax, [rax+58h]
0x140250d80  mov     [rbp+220h+var_270], rax
0x140250d84  mov     rax, [rcx+768h]
0x140250d8b  mov     rax, [rax+0CA0h]
0x140250d92  mov     [rbp+220h+var_260], rax
0x140250d96  test    rax, rax
0x140250d99  jz      short loc_140250DA7
0x140250d9b  mov     rcx, rax; this
0x140250d9e  call    ?IsCoreResourceSharedOwner@ADAPTER_DISPLAY@@QEBAEXZ; ADAPTER_DISPLAY::IsCoreResourceSharedOwner(void)
0x140250da3  test    al, al
0x140250da5  jnz     short loc_140250DED
0x140250da7  mov     ecx, ebx
0x140250da9  call    cs:__imp_WdLogSingleEntry0
0x140250db0  nop     dword ptr [rax+rax+00h]
0x140250db5  mov     [rsp+340h+var_300], r15
0x140250dba  lea     r9, aPdisplaycoreNu; "(pDisplayCore != NULL) && pDisplayCore-"...
0x140250dc1  mov     [rsp+340h+var_308], r15
0x140250dc6  mov     eax, 1B85h
0x140250dcb  mov     [rsp+340h+var_310], r15
0x140250dd0  mov     r8d, r14d
0x140250dd3  mov     [rsp+340h+var_318], r15
0x140250dd8  mov     edx, r12d
0x140250ddb  xor     ecx, ecx
0x140250ddd  mov     [rsp+340h+var_320], rax
0x140250de2  mov     cs:WdLogGlobalForLineNumber, eax
0x140250de8  call    DxgkLogInternalTriageEvent
0x140250ded  mov     rcx, [rsi+10h]
0x140250df1  mov     rcx, [rcx+10h]; this
0x140250df5  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x140250dfa  test    al, al
0x140250dfc  jnz     short loc_140250E44
0x140250dfe  mov     ecx, ebx
0x140250e00  call    cs:__imp_WdLogSingleEntry0
0x140250e07  nop     dword ptr [rax+rax+00h]
0x140250e0c  mov     [rsp+340h+var_300], r15
0x140250e11  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x140250e18  mov     [rsp+340h+var_308], r15
0x140250e1d  mov     eax, 1B86h
0x140250e22  mov     [rsp+340h+var_310], r15
0x140250e27  mov     r8d, r14d
0x140250e2a  mov     [rsp+340h+var_318], r15
0x140250e2f  mov     edx, r12d
0x140250e32  xor     ecx, ecx
0x140250e34  mov     [rsp+340h+var_320], rax
0x140250e39  mov     cs:WdLogGlobalForLineNumber, eax
0x140250e3f  call    DxgkLogInternalTriageEvent
0x140250e44  mov     r9, [rdi+48h]
0x140250e48  test    r9, r9
0x140250e4b  jz      loc_140252133
0x140250e51  lea     r13, [rdi+40h]
0x140250e55  cmp     [r13+0], r15d
0x140250e59  jz      loc_140252133
0x140250e5f  mov     ecx, [rdi+58h]
0x140250e62  mov     eax, ecx
0x140250e64  shr     eax, 1
0x140250e66  xor     eax, ecx
0x140250e68  test    bl, al
0x140250e6a  jz      loc_140252133
0x140250e70  test    ecx, 63Ch
0x140250e76  jnz     loc_140252133
0x140250e7c  xor     edx, edx; Val
0x140250e7e  lea     rcx, [rbp+220h+var_200]; void *
0x140250e82  mov     r8d, 0A8h; Size
0x140250e88  call    memset
0x140250e8d  mov     rax, [rsi+10h]
0x140250e91  mov     ebx, [rdi+18h]
0x140250e94  mov     rax, [rax+28h]
0x140250e98  mov     [rbp+220h+var_288], rax
0x140250e9c  lea     rcx, [rax+0F8h]; this
0x140250ea3  mov     [rbp+220h+var_290], rcx
0x140250ea7  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x140250eac  mov     rcx, [rbp+220h+var_288]
0x140250eb0  mov     eax, ebx
0x140250eb2  shr     eax, 6
0x140250eb5  mov     r15d, 2
0x140250ebb  and     eax, 0FFFFFFh
0x140250ec0  mov     r12d, 40000h
0x140250ec6  cmp     eax, [rcx+128h]
0x140250ecc  jnb     short loc_140250F4B
0x140250ece  mov     r8, [rcx+118h]
0x140250ed5  mov     edx, eax
0x140250ed7  add     rdx, rdx
0x140250eda  shr     ebx, 19h
0x140250edd  and     ebx, 60h
0x140250ee0  mov     ecx, [r8+rdx*8+8]
0x140250ee5  mov     eax, ecx
0x140250ee7  and     eax, 60h
0x140250eea  cmp     bl, al
0x140250eec  jnz     short loc_140250F4B
0x140250eee  bt      ecx, 0Dh
0x140250ef2  jb      short loc_140250F4B
0x140250ef4  and     ecx, 1Fh
0x140250ef7  jz      short loc_140250F4B
0x140250ef9  cmp     ecx, 5
0x140250efc  jz      loc_140251007
0x140250f02  mov     ecx, r15d
0x140250f05  call    cs:__imp_WdLogSingleEntry0
0x140250f0c  nop     dword ptr [rax+rax+00h]
0x140250f11  xor     eax, eax
0x140250f13  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x140250f1a  mov     [rsp+340h+var_300], rax
0x140250f1f  mov     ecx, 13Eh
0x140250f24  mov     [rsp+340h+var_308], rax
0x140250f29  mov     r8d, r14d
0x140250f2c  mov     [rsp+340h+var_310], rax
0x140250f31  mov     edx, r12d
0x140250f34  mov     [rsp+340h+var_318], rax
0x140250f39  mov     [rsp+340h+var_320], rcx
0x140250f3e  mov     cs:WdLogGlobalForLineNumber, ecx
0x140250f44  xor     ecx, ecx
0x140250f46  call    DxgkLogInternalTriageEvent
0x140250f4b  xor     edx, edx; struct DXGALLOCATION *
0x140250f4d  lea     rcx, [rbp+220h+var_278]; this
0x140250f51  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x140250f56  mov     rax, [rbp+220h+var_290]
0x140250f5a  xor     edx, edx
0x140250f5c  mov     rcx, rax
0x140250f5f  lock dec dword ptr [rax+10h]
0x140250f63  call    cs:__imp_ExReleasePushLockSharedEx
0x140250f6a  nop     dword ptr [rax+rax+00h]
0x140250f6f  call    cs:__imp_KeLeaveCriticalRegion
0x140250f76  nop     dword ptr [rax+rax+00h]
0x140250f7b  cmp     [rbp+220h+var_278], 0
0x140250f80  jnz     loc_140251010
0x140250f86  mov     ecx, [r13+0]
0x140250f8a  mov     rbx, 0FFFFFFFFC000000Dh
0x140250f91  mov     eax, [rdi+18h]
0x140250f94  mov     r8, rsi
0x140250f97  mov     r9, [rdi+48h]
0x140250f9b  mov     rdx, rbx
0x140250f9e  mov     [rsp+340h+var_318], rax
0x140250fa3  mov     [rsp+340h+var_320], rcx
0x140250fa8  mov     ecx, r15d
0x140250fab  call    cs:__imp_WdLogSingleEntry5
0x140250fb2  nop     dword ptr [rax+rax+00h]
0x140250fb7  mov     cs:WdLogGlobalForLineNumber, 1BA2h
0x140250fc1  lea     r9, a0xI64x0xI64xFa_0; "0x%I64x 0x%I64x fails Present invalid p"...
0x140250fc8  mov     ecx, [r13+0]
0x140250fcc  mov     edx, r12d
0x140250fcf  mov     eax, [rdi+18h]
0x140250fd2  mov     [rsp+340h+var_300], rax
0x140250fd7  mov     [rsp+340h+var_308], rcx
0x140250fdc  mov     rcx, [rdi+48h]
0x140250fe0  mov     [rsp+340h+var_310], rcx
0x140250fe5  mov     [rsp+340h+var_318], rsi
0x140250fea  mov     r8d, r14d
0x140250fed  mov     [rsp+340h+var_320], rbx
0x140250ff2  xor     ecx, ecx
0x140250ff4  call    DxgkLogInternalTriageEvent
0x140250ff9  lea     rcx, [rbp+220h+var_278]; this
0x140250ffd  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x140251002  jmp     loc_1402521A4
0x140251007  mov     rdx, [r8+rdx*8]
0x14025100b  jmp     loc_140250F4D
0x140251010  mov     eax, [rdi+58h]
0x140251013  test    al, 1
0x140251015  jz      loc_140251189
0x14025101b  mov     rax, [rsi+10h]
0x14025101f  mov     ebx, [rdi+14h]
0x140251022  mov     rax, [rax+28h]
0x140251026  mov     [rbp+220h+var_288], rax
0x14025102a  lea     rcx, [rax+0F8h]; this
0x140251031  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x140251036  mov     rcx, [rbp+220h+var_288]
0x14025103a  mov     eax, ebx
0x14025103c  shr     eax, 6
0x14025103f  and     eax, 0FFFFFFh
0x140251044  cmp     eax, [rcx+128h]
0x14025104a  jnb     short loc_1402510C9
0x14025104c  mov     r8, [rcx+118h]
0x140251053  mov     edx, eax
0x140251055  add     rdx, rdx
0x140251058  shr     ebx, 19h
0x14025105b  and     ebx, 60h
0x14025105e  mov     ecx, [r8+rdx*8+8]
0x140251063  mov     eax, ecx
0x140251065  and     eax, 60h
0x140251068  cmp     bl, al
0x14025106a  jnz     short loc_1402510C9
0x14025106c  bt      ecx, 0Dh
0x140251070  jb      short loc_1402510C9
0x140251072  and     ecx, 1Fh
0x140251075  jz      short loc_1402510C9
0x140251077  cmp     ecx, 5
0x14025107a  jz      loc_140251177
0x140251080  mov     ecx, r15d
0x140251083  call    cs:__imp_WdLogSingleEntry0
0x14025108a  nop     dword ptr [rax+rax+00h]
0x14025108f  xor     eax, eax
0x140251091  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x140251098  mov     [rsp+340h+var_300], rax
0x14025109d  mov     ecx, 13Eh
0x1402510a2  mov     [rsp+340h+var_308], rax
0x1402510a7  mov     r8d, r14d
0x1402510aa  mov     [rsp+340h+var_310], rax
0x1402510af  mov     edx, r12d
0x1402510b2  mov     [rsp+340h+var_318], rax
0x1402510b7  mov     [rsp+340h+var_320], rcx
0x1402510bc  mov     cs:WdLogGlobalForLineNumber, ecx
0x1402510c2  xor     ecx, ecx
0x1402510c4  call    DxgkLogInternalTriageEvent
0x1402510c9  xor     edx, edx; struct DXGALLOCATION *
0x1402510cb  lea     rcx, [rbp+220h+var_290]; this
0x1402510cf  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x1402510d4  mov     rax, [rbp+220h+var_288]
0x1402510d8  xor     edx, edx
0x1402510da  lock dec dword ptr [rax+108h]
0x1402510e1  lea     rcx, [rax+0F8h]
0x1402510e8  call    cs:__imp_ExReleasePushLockSharedEx
0x1402510ef  nop     dword ptr [rax+rax+00h]
0x1402510f4  call    cs:__imp_KeLeaveCriticalRegion
0x1402510fb  nop     dword ptr [rax+rax+00h]
0x140251100  cmp     [rbp+220h+var_290], 0
0x140251105  jnz     short loc_140251180
0x140251107  mov     r9d, [rdi+14h]
0x14025110b  mov     rbx, 0FFFFFFFFC000000Dh
0x140251112  mov     rdx, rbx
0x140251115  mov     r8, rsi
0x140251118  mov     ecx, r15d
0x14025111b  call    cs:__imp_WdLogSingleEntry3
0x140251122  nop     dword ptr [rax+rax+00h]
0x140251127  mov     [rsp+340h+var_300], 0
  ... truncated ...
```
