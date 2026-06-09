# DXGCONTEXT::PresentFromCdd(_D3DKMT_SUBMITPRESENTTOHWQUEUE *,uint,COREDEVICEACCESS *,DXGADAPTERSTOPRESETLOCKSHARED *,DXGCONTEXT * *)

- ea: `0x140254210`
- end: `0x1402557bc`
- name: `?PresentFromCdd@DXGCONTEXT@@QEAAJPEAU_D3DKMT_SUBMITPRESENTTOHWQUEUE@@IPEAVCOREDEVICEACCESS@@PEAVDXGADAPTERSTOPRESETLOCKSHARED@@PEAPEAV1@@Z`
- size: `5548`
- prototype: `__int64 __usercall@<rax>(DXGCONTEXT *__hidden this@<rcx>, struct _D3DKMT_SUBMITPRESENTTOHWQUEUE *@<rdx>, unsigned int@<r8d>, struct COREDEVICEACCESS *@<r9>, struct DXGADAPTERSTOPRESETLOCKSHARED *, struct DXGCONTEXT **)`
- caller_count: `3`
- callee_count: `41`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14019b7b0`
- `0x1401ae414`
- `0x140212a40`

## callees

- `0x140012540`
- `0x140014950`
- `0x140014e0c`
- `0x140015a70`
- `0x140015f7c`
- `0x1400169f0`
- `0x14001b9c0`
- `0x14001c5c0`
- `0x14001d1a0`
- `0x14001e64c`
- `0x14001eaac`
- `0x14001f2f0`
- `0x14002dbc0`
- `0x14002dc10`
- `0x140034030`
- `0x140034910`
- `0x14003940c`
- `0x14003c364`
- `0x140040cc8`
- `0x1400477c4`
- `0x140049424`
- `0x14004f5ec`
- `0x140055854`
- `0x14007a0a0`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x140254210`
- `0x1402564e0`
- `0x14031a9cc`
- `0x14032e980`
- `0x14032fd70`
- `0x14034aed4`
- `0x1403850e8`
- `0x14038c6d4`
- `0x14038fb34`
- `0x1403a7918`
- `0x1403d056c`
- `0x1403dedfc`
- `0x140401110`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025454f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402546d4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14025454f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402546d4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140254543`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1402546c8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140254543`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1402546c8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140254271`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140254271`
- `watchdog!WdLogSingleEntry4` at `0x140254931`
- `watchdog!WdLogSingleEntry4` at `0x140254a6c`
- `watchdog!WdLogSingleEntry4` at `0x140254bac`
- `watchdog!WdLogSingleEntry4` at `0x140254931`
- `watchdog!WdLogSingleEntry4` at `0x140254a6c`
- `watchdog!WdLogSingleEntry4` at `0x140254bac`
- `watchdog!WdLogSingleEntry2` at `0x1402548cb`
- `watchdog!WdLogSingleEntry2` at `0x1402548cb`
- `watchdog!WdLogSingleEntry3` at `0x1402546fb`
- `watchdog!WdLogSingleEntry3` at `0x140254a2d`
- `watchdog!WdLogSingleEntry3` at `0x1402546fb`
- `watchdog!WdLogSingleEntry3` at `0x140254a2d`
- `watchdog!WdLogSingleEntry0` at `0x140254389`
- `watchdog!WdLogSingleEntry0` at `0x1402543e0`
- `watchdog!WdLogSingleEntry0` at `0x1402544e5`
- `watchdog!WdLogSingleEntry0` at `0x140254663`
- `watchdog!WdLogSingleEntry0` at `0x140254821`
- `watchdog!WdLogSingleEntry0` at `0x140254c26`
- `watchdog!WdLogSingleEntry0` at `0x140254c81`
- `watchdog!WdLogSingleEntry0` at `0x140254cd4`
- `watchdog!WdLogSingleEntry0` at `0x140254d25`
- `watchdog!WdLogSingleEntry0` at `0x140254d95`
- `watchdog!WdLogSingleEntry0` at `0x140254de8`
- `watchdog!WdLogSingleEntry0` at `0x140254e39`
- `watchdog!WdLogSingleEntry0` at `0x140254ea0`
- `watchdog!WdLogSingleEntry0` at `0x140254f58`
- `watchdog!WdLogSingleEntry0` at `0x140254fae`
- `watchdog!WdLogSingleEntry0` at `0x140255005`
- `watchdog!WdLogSingleEntry0` at `0x14025505e`
- `watchdog!WdLogSingleEntry0` at `0x1402550b5`
- `watchdog!WdLogSingleEntry0` at `0x14025510c`
- `watchdog!WdLogSingleEntry0` at `0x14025519e`
- `watchdog!WdLogSingleEntry0` at `0x1402551f7`
- `watchdog!WdLogSingleEntry0` at `0x14025525b`
- `watchdog!WdLogSingleEntry0` at `0x1402552b3`
- `watchdog!WdLogSingleEntry0` at `0x14025530b`
- `watchdog!WdLogSingleEntry0` at `0x140255363`
- `watchdog!WdLogSingleEntry0` at `0x1402553c2`
- `watchdog!WdLogSingleEntry0` at `0x1402556b8`
- `watchdog!WdLogSingleEntry0` at `0x140254389`
- `watchdog!WdLogSingleEntry0` at `0x1402543e0`
- `watchdog!WdLogSingleEntry0` at `0x1402544e5`
- `watchdog!WdLogSingleEntry0` at `0x140254663`
- `watchdog!WdLogSingleEntry0` at `0x140254821`
- `watchdog!WdLogSingleEntry0` at `0x140254c26`
- `watchdog!WdLogSingleEntry0` at `0x140254c81`
- `watchdog!WdLogSingleEntry0` at `0x140254cd4`
- `watchdog!WdLogSingleEntry0` at `0x140254d25`
- `watchdog!WdLogSingleEntry0` at `0x140254d95`
- `watchdog!WdLogSingleEntry0` at `0x140254de8`
- `watchdog!WdLogSingleEntry0` at `0x140254e39`
- `watchdog!WdLogSingleEntry0` at `0x140254ea0`
- `watchdog!WdLogSingleEntry0` at `0x140254f58`
- `watchdog!WdLogSingleEntry0` at `0x140254fae`
- `watchdog!WdLogSingleEntry0` at `0x140255005`
- `watchdog!WdLogSingleEntry0` at `0x14025505e`
- `watchdog!WdLogSingleEntry0` at `0x1402550b5`
- `watchdog!WdLogSingleEntry0` at `0x14025510c`
- `watchdog!WdLogSingleEntry0` at `0x14025519e`
- `watchdog!WdLogSingleEntry0` at `0x1402551f7`
- `watchdog!WdLogSingleEntry0` at `0x14025525b`
- `watchdog!WdLogSingleEntry0` at `0x1402552b3`
- `watchdog!WdLogSingleEntry0` at `0x14025530b`
- `watchdog!WdLogSingleEntry0` at `0x140255363`
- `watchdog!WdLogSingleEntry0` at `0x1402553c2`
- `watchdog!WdLogSingleEntry0` at `0x1402556b8`
- `watchdog!WdLogSingleEntry5` at `0x14025458b`
- `watchdog!WdLogSingleEntry5` at `0x140255735`
- `watchdog!WdLogSingleEntry5` at `0x14025458b`
- `watchdog!WdLogSingleEntry5` at `0x140255735`
- `watchdog!WdLogSingleEntry1` at `0x140254299`
- `watchdog!WdLogSingleEntry1` at `0x140254299`

## string_xrefs

- `0x1402542aa`: `Failed to allocate memory for present parameters. Returing 0x%I64x`

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
  unsigned int *v15; // r13
  unsigned int v16; // ecx
  unsigned int v17; // ebx
  unsigned int v18; // eax
  __int64 v19; // r8
  int v20; // ecx
  struct DXGALLOCATION *v21; // rdx
  unsigned int v22; // ebx
  unsigned int v23; // eax
  __int64 v24; // r8
  int v25; // ecx
  struct DXGALLOCATION *v26; // rdx
  struct VIDSCH_SUBMIT_DATA_BASE *v27; // rax
  DXGPRESENT *v28; // rax
  DXGPRESENT *v29; // rax
  struct VIDSCH_SUBMIT_DATA_BASE *v30; // rdx
  int v31; // ecx
  __int64 v32; // rax
  struct VIDMM_DMA_POOL *v33; // rdx
  COREDEVICEACCESS *v34; // r12
  int v35; // eax
  struct DXGPRESENTMUTEX *v36; // r8
  const char *v37; // rdx
  unsigned __int8 v38; // bl
  __int64 v39; // r12
  const RECT **v40; // r12
  int updated; // eax
  __int64 v42; // rcx
  UINT v43; // eax
  ADAPTER_DISPLAY *v44; // r13
  int CurrentOrientation; // eax
  UINT Value; // eax
  unsigned int v47; // ecx
  const RECT *DdiSubRectList; // r15
  __int64 v49; // rbx
  UINT v50; // r13d
  int v51; // edi
  __int64 v52; // rbx
  LONG v53; // r8d
  LONG v54; // edx
  UINT i; // r15d
  __int64 v56; // rdx
  const RECT *pDstSubRects; // r15
  UINT SubRectCnt; // r14d
  UINT v59; // ebx
  int v60; // esi
  unsigned int v61; // r9d
  UINT v62; // r8d
  unsigned int v63; // r10d
  __int64 v64; // rcx
  struct COREDEVICEACCESS *v65; // r14
  char v67; // [rsp+20h] [rbp-100h]
  unsigned int v69; // [rsp+A0h] [rbp-80h]
  struct VIDMM_DMA_BUFFER *v70; // [rsp+A8h] [rbp-78h] BYREF
  volatile signed __int32 *v71; // [rsp+B0h] [rbp-70h] BYREF
  struct VIDSCH_SUBMIT_DATA_BASE *v72[2]; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v73; // [rsp+C8h] [rbp-58h] BYREF
  struct VIDMM_DMA_BUFFER *v74; // [rsp+D0h] [rbp-50h]
  unsigned int *v75; // [rsp+D8h] [rbp-48h] BYREF
  ADAPTER_DISPLAY *v76; // [rsp+E0h] [rbp-40h]
  union _LARGE_INTEGER v77; // [rsp+E8h] [rbp-38h] BYREF
  struct DXGHWQUEUE *v78; // [rsp+F0h] [rbp-30h] BYREF
  DXGCONTEXT *v79; // [rsp+F8h] [rbp-28h]
  COREDEVICEACCESS *v80; // [rsp+100h] [rbp-20h]
  DXGADAPTERSTOPRESETLOCKSHARED *v81; // [rsp+108h] [rbp-18h]
  _BYTE v82[16]; // [rsp+110h] [rbp-10h] BYREF
  _BYTE v83[24]; // [rsp+120h] [rbp+0h] BYREF
  unsigned int *v84; // [rsp+138h] [rbp+18h]
  struct _DXGKARG_PRESENT v85; // [rsp+140h] [rbp+20h] BYREF
  _DWORD v86[16]; // [rsp+1F0h] [rbp+D0h] BYREF
  _DWORD v87[16]; // [rsp+230h] [rbp+110h] BYREF
  _DWORD v88[16]; // [rsp+270h] [rbp+150h] BYREF
  _DWORD v89[16]; // [rsp+2B0h] [rbp+190h] BYREF

  v81 = a5;
  v7 = this;
  v77.QuadPart = (LONGLONG)a6;
  v80 = a4;
  v79 = this;
  Global = (struct _LOOKASIDE_LIST_EX *)DXGGLOBAL::GetGlobal();
  v9 = (unsigned int *)ExAllocateFromLookasideListEx(Global + 12);
  v84 = v9;
  v10 = v9;
  if ( v9 )
  {
    memset(v9, 0, 0x5F8u);
    v75 = v10;
    v78 = 0;
    memmove(v10, &a2->PrivatePresentData, 0x5D8u);
    *((_QWORD *)v10 + 188) = &v78;
    if ( a2->hHwQueues )
      v12 = *a2->hHwQueues;
    else
      v12 = 0;
    DXGHWQUEUEBYHANDLE::DXGHWQUEUEBYHANDLE(
      (DXGHWQUEUEBYHANDLE *)v82,
      v12,
      *(struct DXGPROCESS **)(*((_QWORD *)v7 + 2) + 40LL),
      &v78,
      1,
      1);
    v13 = *((_QWORD *)v7 + 2);
    v74 = *(struct VIDMM_DMA_BUFFER **)(*(_QWORD *)(v13 + 40) + 88LL);
    v14 = *(ADAPTER_DISPLAY **)(*(_QWORD *)(v13 + 1896) + 3248LL);
    v76 = v14;
    if ( !v14 || !ADAPTER_DISPLAY::IsCoreResourceSharedOwner(v14) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 7293;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"(pDisplayCore != NULL) && pDisplayCore->IsCoreResourceSharedOwner()",
        7293,
        0,
        0,
        0,
        0);
    }
    if ( !ADAPTER_RENDER::IsCoreResourceSharedOwner(*(ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL)) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 7294;
      DxgkLogInternalTriageEvent(
        0,
        262146,
        -1,
        (unsigned int)L"GetRenderCore()->IsCoreResourceSharedOwner()",
        7294,
        0,
        0,
        0,
        0);
    }
    if ( !*((_QWORD *)v10 + 9)
      || (v15 = v10 + 16, !v10[16])
      || (v16 = v10[22], (((unsigned __int8)v16 ^ (unsigned __int8)(v16 >> 1)) & 1) == 0)
      || (v16 & 0x63C) != 0 )
    {
      v11 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, v7);
      WdLogGlobalForLineNumber = 7309;
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
    memset(&v85, 0, sizeof(v85));
    v17 = v10[6];
    v72[0] = *(struct VIDSCH_SUBMIT_DATA_BASE **)(*((_QWORD *)v7 + 2) + 40LL);
    v71 = (volatile signed __int32 *)((char *)v72[0] + 248);
    DXGPUSHLOCK::AcquireShared((struct VIDSCH_SUBMIT_DATA_BASE *)((char *)v72[0] + 248));
    v18 = (v17 >> 6) & 0xFFFFFF;
    if ( v18 < *((_DWORD *)v72[0] + 74) )
    {
      v19 = *((_QWORD *)v72[0] + 35);
      if ( ((v17 >> 25) & 0x60) == (*(_BYTE *)(v19 + 16LL * v18 + 8) & 0x60)
        && (*(_DWORD *)(v19 + 16LL * v18 + 8) & 0x2000) == 0 )
      {
        v20 = *(_DWORD *)(v19 + 16LL * v18 + 8) & 0x1F;
        if ( v20 )
        {
          if ( v20 == 5 )
          {
            v21 = *(struct DXGALLOCATION **)(v19 + 16LL * v18);
LABEL_22:
            DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v73, v21);
            _InterlockedDecrement(v71 + 4);
            ExReleasePushLockSharedEx(v71, 0);
            KeLeaveCriticalRegion();
            if ( !v73 )
            {
              v11 = -1073741811;
              WdLogSingleEntry5(2, -1073741811, v7);
              WdLogGlobalForLineNumber = 7322;
              DxgkLogInternalTriageEvent(
                0,
                0x40000,
                -1,
                (unsigned int)L"0x%I64x 0x%I64x fails Present invalid parameters 0x%I64x 0x%I64x 0x%I64x",
                -1073741811,
                (__int64)v7,
                *((_QWORD *)v10 + 9),
                *v15,
                v10[6]);
LABEL_24:
              DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v73);
LABEL_147:
              DXGHWQUEUEBYHANDLE::~DXGHWQUEUEBYHANDLE((DXGHWQUEUEBYHANDLE *)v82);
              DXGADAPTER::SubmitPresentHistoryTokenFromVm_::_45_::ENSURE_DELETE::_ENSURE_DELETE(&v75);
              return (unsigned int)v11;
            }
            if ( (v10[22] & 1) == 0 )
            {
LABEL_38:
              if ( !*((_QWORD *)v7 + 19) )
              {
                v28 = (DXGPRESENT *)DXGQUOTAALLOCATOR<256,1265072196>::operator new(1648);
                if ( v28 )
                {
                  v29 = DXGPRESENT::DXGPRESENT(v28, 1u);
                  *((_QWORD *)v7 + 19) = v29;
                  if ( v29 )
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
                WdLogGlobalForLineNumber = 7349;
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
                (CVidSchSubmitData *)v72,
                *(struct ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL),
                1);
              v30 = v72[0];
              if ( !v72[0] )
              {
                WdLogSingleEntry0(6);
                WdLogGlobalForLineNumber = 7358;
                DxgkLogInternalTriageEvent(
                  0,
                  262145,
                  -1,
                  (unsigned int)L"Failed to allocate VidSchSubmitData",
                  7358,
                  0,
                  0,
                  0,
                  0);
                CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v72);
                v11 = -1073741801;
                goto LABEL_24;
              }
              *(_DWORD *)v72[0] |= 0x10000u;
              v31 = *(_DWORD *)v30;
              if ( (v10[22] & 0x4000) == 0 )
                v31 |= 1u;
              *(_DWORD *)v30 = v31 | 0x100;
              v32 = *((_QWORD *)v7 + 2);
              v33 = (struct VIDMM_DMA_POOL *)*((_QWORD *)v7 + 29);
              v70 = 0;
              v11 = VIDMM_EXPORT::VidMmAcquireDmaBuffer(
                      *(VIDMM_EXPORT **)(*(_QWORD *)(v32 + 16) + 760LL),
                      v33,
                      0,
                      1,
                      &v70);
              if ( v11 < 0 )
                goto LABEL_76;
              if ( !v70 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 7376;
                DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pVidMmDmaBuffer", 7376, 0, 0, 0, 0);
              }
              DXGPRESENTMUTEX::DXGPRESENTMUTEX(
                (DXGPRESENTMUTEX *)v83,
                *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
              if ( (v10[22] & 0x4000) == 0 )
              {
                v34 = v80;
                COREDEVICEACCESS::Release(v80);
                DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v81);
                DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v83);
                DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v81);
                v35 = COREDEVICEACCESS::AcquireShared(v34, 0);
                v11 = v35;
                if ( v35 < 0 )
                {
                  WdLogSingleEntry2(4, v35, v7);
                  WdLogGlobalForLineNumber = 7394;
                  COREDEVICEACCESS::AcquireSharedUncheck(v34, v37);
                  VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                    *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                    v70);
LABEL_75:
                  DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v83);
LABEL_76:
                  CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v72);
                  goto LABEL_24;
                }
                v38 = 0;
                if ( v74 )
                {
                  v39 = *((_QWORD *)v7 + 19);
                  if ( *(_DWORD *)(v39 + 8) != (*((unsigned int (**)(void))v74 + 1))() )
                  {
                    *(_DWORD *)(v39 + 8) = (*((__int64 (**)(void))v74 + 1))();
                    DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 2, 4294967293LL, 0, v67);
                    v38 = 1;
                  }
                }
                DXGDEVICE::SynchronizePresentToPrimary(*((DXGDEVICE **)v7 + 2), v7, v36, v38);
              }
              if ( (v10[22] & 1) == 0 || v10[5] == v10[6] )
              {
                v40 = (const RECT **)(v10 + 18);
              }
              else
              {
                v40 = (const RECT **)(v10 + 18);
                if ( (*(_DWORD *)(*(_QWORD *)(v73 + 48) + 4LL) & 2) != 0 )
                {
                  updated = DxgkCddUpdatePresentRects(v76, a3, (const struct tagRECT **)v10 + 9, v10 + 16);
                  v11 = updated;
                  if ( updated < 0 )
                  {
                    WdLogSingleEntry3(4, updated, *((_QWORD *)v7 + 2), a3);
                    WdLogGlobalForLineNumber = 7432;
                    v42 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
LABEL_74:
                    VIDMM_EXPORT::VidMmReleaseDmaBuffer(*(VIDMM_EXPORT **)(v42 + 760), v70);
                    v70 = 0;
                    goto LABEL_75;
                  }
                  if ( !*v15 )
                  {
                    WdLogSingleEntry4(4, 0, *((_QWORD *)v7 + 2), v10[6], a3);
                    WdLogGlobalForLineNumber = 7447;
                    VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                      *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                      v70);
                    v70 = 0;
                    DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v83);
                    CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v72);
                    v11 = 0;
                    goto LABEL_24;
                  }
                }
              }
              v11 = DXGPRESENT::GrowRectList(*((DXGPRESENT **)v7 + 19), *v15);
              if ( v11 < 0 )
              {
LABEL_73:
                v42 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
                goto LABEL_74;
              }
              v85.DstRect = (RECT)*((_OWORD *)v10 + 2);
              v43 = *v15;
              v44 = v76;
              v85.SubRectCnt = v43;
              if ( (v10[22] & 0x4000) != 0 )
              {
                Value = v85.Flags.Value;
              }
              else
              {
                CurrentOrientation = ADAPTER_DISPLAY::GetCurrentOrientation(v76, a3, 1);
                Value = (CurrentOrientation != 1 ? 0x80 : 0) | v85.Flags.Value & 0xFFFFFF7F;
                v85.Flags.Value = Value;
              }
              v47 = v10[22];
              if ( (v47 & 1) != 0 )
              {
                v85.Flags.Value = Value | 1;
                v85.SrcRect = (RECT)*((_OWORD *)v10 + 3);
                if ( v10[5] == v10[6] )
                {
                  if ( (v10[22] & 0x4000) == 0 && ADAPTER_DISPLAY::GetVidPnSourceOwnerType(v44, a3) )
                  {
                    v11 = -1071774910;
                    WdLogSingleEntry4(4, -1071774910, *((_QWORD *)v7 + 2), v10[6], a3);
                    WdLogGlobalForLineNumber = 7505;
                    goto LABEL_73;
                  }
                  DdiSubRectList = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
                  v85.pDstSubRects = DdiSubRectList;
                  if ( v85.DstRect.right - v85.DstRect.left != v85.SrcRect.right - v85.SrcRect.left )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7524;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.DstRect.right - PresentDdiArg.DstRect.left == PresentDdiArg.SrcRect.ri"
                                     "ght - PresentDdiArg.SrcRect.left",
                      7524,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v85.DstRect.bottom - v85.DstRect.top != v85.SrcRect.bottom - v85.SrcRect.top )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7527;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.DstRect.bottom - PresentDdiArg.DstRect.top == PresentDdiArg.SrcRect.bo"
                                     "ttom - PresentDdiArg.SrcRect.top",
                      7527,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v85.SrcRect.left >= v85.SrcRect.right )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7529;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.SrcRect.left < PresentDdiArg.SrcRect.right",
                      7529,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v85.SrcRect.left < 0 )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7530;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.SrcRect.left >= 0",
                      7530,
                      0,
                      0,
                      0,
                      0);
                  }
                  v49 = 4024LL * a3;
                  if ( v85.SrcRect.right > *(_DWORD *)(v49 + *((_QWORD *)v44 + 16) + 636)
                                         - *(_DWORD *)(v49 + *((_QWORD *)v44 + 16) + 628) )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7531;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.SrcRect.right <= pDisplayCore->GetContentRect(VidPnSourceId)->right - "
                                     "pDisplayCore->GetContentRect(VidPnSourceId)->left",
                      7531,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v85.DstRect.top >= v85.DstRect.bottom )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7533;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.DstRect.top < PresentDdiArg.DstRect.bottom",
                      7533,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v85.DstRect.top < 0 )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7534;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.DstRect.top >= 0",
                      7534,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( v85.SrcRect.bottom > *(_DWORD *)(v49 + *((_QWORD *)v44 + 16) + 640)
                                          - *(_DWORD *)(v49 + *((_QWORD *)v44 + 16) + 632) )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7535;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"PresentDdiArg.SrcRect.bottom <= pDisplayCore->GetContentRect(VidPnSourceId)->bottom "
                                     "- pDisplayCore->GetContentRect(VidPnSourceId)->top",
                      7535,
                      0,
                      0,
                      0,
                      0);
                  }
                  v50 = 0;
                  v69 = v85.DstRect.left - v85.SrcRect.left;
                  if ( v85.SubRectCnt )
                  {
                    v51 = v85.DstRect.top - v85.SrcRect.top;
                    do
                    {
                      v52 = v50;
                      v53 = v69 + (*v40)[v50].left;
                      DdiSubRectList[v52].left = v53;
                      v54 = v69 + (*v40)[v50].right;
                      DdiSubRectList[v52].right = v54;
                      DdiSubRectList[v52].top = v51 + (*v40)[v50].top;
                      DdiSubRectList[v52].bottom = v51 + (*v40)[v50].bottom;
                      if ( v53 >= v54 )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7547;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].left < pDstSubRects[i].right",
                          7547,
                          0,
                          0,
                          0,
                          0);
                      }
                      if ( DdiSubRectList[v50].left < v85.DstRect.left )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7548;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].left >= PresentDdiArg.DstRect.left",
                          7548,
                          0,
                          0,
                          0,
                          0);
                      }
                      if ( DdiSubRectList[v50].right > v85.DstRect.right )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7549;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].right <= PresentDdiArg.DstRect.right",
                          7549,
                          0,
                          0,
                          0,
                          0);
                      }
                      if ( DdiSubRectList[v50].top >= DdiSubRectList[v50].bottom )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7550;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].top < pDstSubRects[i].bottom",
                          7550,
                          0,
                          0,
                          0,
                          0);
                      }
                      if ( DdiSubRectList[v50].top < v85.DstRect.top )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7551;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].top >= PresentDdiArg.DstRect.top",
                          7551,
                          0,
                          0,
                          0,
                          0);
                      }
                      if ( DdiSubRectList[v50].bottom > v85.DstRect.bottom )
                      {
                        WdLogSingleEntry0(1);
                        WdLogGlobalForLineNumber = 7552;
                        DxgkLogInternalTriageEvent(
                          0,
                          262146,
                          -1,
                          (unsigned int)L"pDstSubRects[i].bottom <= PresentDdiArg.DstRect.bottom",
                          7552,
                          0,
                          0,
                          0,
                          0);
                      }
                      ++v50;
                    }
                    while ( v50 < v85.SubRectCnt );
                    v10 = v84;
                    v7 = v79;
                  }
                }
                else
                {
                  v85.pDstSubRects = *v40;
                }
                for ( i = 0; i < v85.SubRectCnt; ++i )
                {
                  if ( (*v40)[i].left >= (*v40)[i].right )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7563;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"pPresent->pSrcSubRects[i].left < pPresent->pSrcSubRects[i].right",
                      7563,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( (*v40)[i].top >= (*v40)[i].bottom )
                  {
                    WdLogSingleEntry0(1);
                    WdLogGlobalForLineNumber = 7564;
                    DxgkLogInternalTriageEvent(
                      0,
                      262146,
                      -1,
                      (unsigned int)L"pPresent->pSrcSubRects[i].top < pPresent->pSrcSubRects[i].bottom",
                      7564,
                      0,
                      0,
                      0,
                      0);
                  }
                  if ( (v10[22] & 0x4000) == 0 )
                  {
                    if ( (*v40)[i].left < v85.SrcRect.left )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 7569;
                      DxgkLogInternalTriageEvent(
                        0,
                        262146,
                        -1,
                        (unsigned int)L"pPresent->pSrcSubRects[i].left >= PresentDdiArg.SrcRect.left",
                        7569,
                        0,
                        0,
                        0,
                        0);
                    }
                    if ( (*v40)[i].right > v85.SrcRect.right )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 7570;
                      DxgkLogInternalTriageEvent(
                        0,
                        262146,
                        -1,
                        (unsigned int)L"pPresent->pSrcSubRects[i].right <= PresentDdiArg.SrcRect.right",
                        7570,
                        0,
                        0,
                        0,
                        0);
                    }
                    if ( (*v40)[i].top < v85.SrcRect.top )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 7571;
                      DxgkLogInternalTriageEvent(
                        0,
                        262146,
                        -1,
                        (unsigned int)L"pPresent->pSrcSubRects[i].top >= PresentDdiArg.SrcRect.top",
                        7571,
                        0,
                        0,
                        0,
                        0);
                    }
                    if ( (*v40)[i].bottom > v85.SrcRect.bottom )
                    {
                      WdLogSingleEntry0(1);
                      WdLogGlobalForLineNumber = 7572;
                      DxgkLogInternalTriageEvent(
                        0,
                        262146,
                        -1,
                        (unsigned int)L"pPresent->pSrcSubRects[i].bottom <= PresentDdiArg.SrcRect.bottom",
                        7572,
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
                if ( (v47 & 2) == 0 )
                {
                  WdLogSingleEntry0(1);
                  WdLogGlobalForLineNumber = 7579;
                  DxgkLogInternalTriageEvent(
                    0,
                    262146,
                    -1,
                    (unsigned int)L"pPresent->Flags.ColorFill",
                    7579,
                    0,
                    0,
                    0,
                    0);
                  Value = v85.Flags.Value;
                }
                v85.Flags.Value = Value | 2;
                v85.Color = v10[7];
                v85.pDstSubRects = *v40;
              }
              if ( !bTracingEnabled )
                goto LABEL_142;
              VIDMM_EXPORT::VidMmETWAllocationHandle(
                *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                v10[6]);
              VIDMM_EXPORT::VidMmETWAllocationHandle(
                *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                *(struct VIDMM_GLOBAL **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 768LL),
                v10[5]);
              pDstSubRects = v85.pDstSubRects;
              SubRectCnt = v85.SubRectCnt;
              v74 = v70;
              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
                McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                  v85.DstRect.top,
                  v85.DstRect.right,
                  v85.DstRect.left,
                  0,
                  (char)v74);
              v59 = 0;
              if ( !SubRectCnt )
              {
LABEL_142:
                v65 = v80;
                v11 = DXGCONTEXT::SubmitPresent(
                        v7,
                        (const struct _D3DKMT_PRESENT *)v10,
                        *((struct DXGHWQUEUE ***)v10 + 188),
                        v10[23],
                        (struct DXGCONTEXT **)v77.QuadPart,
                        0,
                        v10[5],
                        v10[6],
                        &v85,
                        0,
                        v70,
                        v72[0],
                        D3DDDIFMT_A8B8G8R8,
                        v80);
                if ( v11 >= 0 && v10[90] == 1 )
                {
                  v77.QuadPart = -100000;
                  v11 = SubmitPresentHistoryToken(
                          (struct _D3DKMT_PRESENTHISTORYTOKEN *)(v10 + 90),
                          v65,
                          v81,
                          0,
                          0,
                          &v77,
                          (struct DXGK_PRESENT_PARAMS *)v10,
                          0,
                          v7,
                          0,
                          0);
                }
                goto LABEL_75;
              }
              v60 = (int)v74;
              while ( 1 )
              {
                v61 = 0;
                v62 = SubRectCnt - v59;
                if ( SubRectCnt - v59 > 0x10 )
                  break;
                v63 = SubRectCnt - v59;
                if ( v62 )
                  goto LABEL_137;
LABEL_138:
                if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x40) != 0 )
                  McTemplateK0ptqDR2DR2DR2DR2_EtwWriteTransfer(
                    (unsigned int)v89,
                    v56 * 2,
                    v62,
                    v60,
                    SubRectCnt - v59 <= 0x10,
                    v63,
                    (__int64)v89,
                    (__int64)v88,
                    (__int64)v87,
                    (__int64)v86);
                v59 += 16;
                if ( v59 >= SubRectCnt )
                {
                  v7 = v79;
                  goto LABEL_142;
                }
              }
              v63 = 16;
              do
              {
LABEL_137:
                v64 = v61;
                v56 = v61 + v59;
                ++v61;
                v89[v64] = pDstSubRects[v56].left;
                v88[v64] = pDstSubRects[v56].right;
                v87[v64] = pDstSubRects[v56].top;
                v86[v64] = pDstSubRects[v56].bottom;
              }
              while ( v61 < v63 );
              goto LABEL_138;
            }
            v22 = v10[5];
            v72[0] = *(struct VIDSCH_SUBMIT_DATA_BASE **)(*((_QWORD *)v7 + 2) + 40LL);
            DXGPUSHLOCK::AcquireShared((struct VIDSCH_SUBMIT_DATA_BASE *)((char *)v72[0] + 248));
            v23 = (v22 >> 6) & 0xFFFFFF;
            if ( v23 < *((_DWORD *)v72[0] + 74) )
            {
              v24 = *((_QWORD *)v72[0] + 35);
              if ( ((v22 >> 25) & 0x60) == (*(_BYTE *)(v24 + 16LL * v23 + 8) & 0x60)
                && (*(_DWORD *)(v24 + 16LL * v23 + 8) & 0x2000) == 0 )
              {
                v25 = *(_DWORD *)(v24 + 16LL * v23 + 8) & 0x1F;
                if ( v25 )
                {
                  if ( v25 == 5 )
                  {
                    v26 = *(struct DXGALLOCATION **)(v24 + 16LL * v23);
                    goto LABEL_34;
                  }
                  WdLogSingleEntry0(2);
                  WdLogGlobalForLineNumber = 318;
                  DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
                }
              }
            }
            v26 = 0;
LABEL_34:
            DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v71, v26);
            v27 = v72[0];
            _InterlockedDecrement((volatile signed __int32 *)v72[0] + 66);
            ExReleasePushLockSharedEx((char *)v27 + 248, 0);
            KeLeaveCriticalRegion();
            if ( !v71 )
            {
              v11 = -1073741811;
              WdLogSingleEntry3(2, -1073741811, v7, v10[5]);
              WdLogGlobalForLineNumber = 7335;
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
              DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v71);
              goto LABEL_24;
            }
            DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v71);
            goto LABEL_38;
          }
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 318;
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"Handle type mismatch", 318, 0, 0, 0, 0);
        }
      }
    }
    v21 = 0;
    goto LABEL_22;
  }
  v11 = -1073741801;
  WdLogSingleEntry1(6, -1073741801);
  WdLogGlobalForLineNumber = 7261;
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
0x140254210  push    rbp
0x140254212  push    rbx
0x140254213  push    rsi
0x140254214  push    rdi
0x140254215  push    r12
0x140254217  push    r13
0x140254219  push    r14
0x14025421b  push    r15
0x14025421d  lea     rbp, [rsp-1E8h]
0x140254225  sub     rsp, 308h
0x14025422c  mov     rax, cs:__security_cookie
0x140254233  xor     rax, rsp
0x140254236  mov     [rbp+220h+var_50], rax
0x14025423d  mov     rax, [rbp+220h+arg_20]
0x140254244  mov     rbx, rdx
0x140254247  mov     [rbp+220h+var_238], rax
0x14025424b  mov     rsi, rcx
0x14025424e  mov     rax, [rbp+220h+arg_28]
0x140254255  mov     qword ptr [rbp+220h+var_258], rax
0x140254259  mov     [rbp+220h+var_240], r9
0x14025425d  mov     [rbp+220h+var_2A0], r8d
0x140254261  mov     [rbp+220h+var_248], rcx
0x140254265  call    ?GetGlobal@DXGGLOBAL@@SAPEAV1@XZ; DXGGLOBAL::GetGlobal(void)
0x14025426a  lea     rcx, [rax+480h]; Lookaside
0x140254271  call    cs:__imp_ExAllocateFromLookasideListEx
0x140254278  nop     dword ptr [rax+rax+00h]
0x14025427d  xor     r15d, r15d
0x140254280  mov     [rbp+220h+var_208], rax
0x140254284  mov     rdi, rax
0x140254287  test    rax, rax
0x14025428a  jnz     short loc_1402542E4
0x14025428c  mov     rbx, 0FFFFFFFFC0000017h
0x140254293  lea     ecx, [rax+6]
0x140254296  mov     rdx, rbx
0x140254299  call    cs:__imp_WdLogSingleEntry1
0x1402542a0  nop     dword ptr [rax+rax+00h]
0x1402542a5  mov     [rsp+340h+var_300], r15
0x1402542aa  lea     r9, aFailedToAlloca_26; "Failed to allocate memory for present p"...
0x1402542b1  mov     [rsp+340h+var_308], r15
0x1402542b6  or      r8d, 0FFFFFFFFh
0x1402542ba  mov     [rsp+340h+var_310], r15
0x1402542bf  mov     edx, 40001h
0x1402542c4  mov     [rsp+340h+var_318], r15
0x1402542c9  xor     ecx, ecx
0x1402542cb  mov     [rsp+340h+var_320], rbx
0x1402542d0  mov     cs:WdLogGlobalForLineNumber, 1C5Dh
0x1402542da  call    DxgkLogInternalTriageEvent
0x1402542df  jmp     loc_140255796
0x1402542e4  xor     edx, edx; Val
0x1402542e6  mov     r8d, 5F8h; Size
0x1402542ec  mov     rcx, rdi; void *
0x1402542ef  call    memset
0x1402542f4  mov     rcx, rdi; void *
0x1402542f7  mov     [rbp+220h+var_268], rdi
0x1402542fb  lea     rdx, [rbx+8]; Src
0x1402542ff  mov     [rbp+220h+var_250], r15
0x140254303  mov     r8d, 5D8h; Size
0x140254309  call    memmove
0x14025430e  lea     rax, [rbp+220h+var_250]
0x140254312  mov     [rdi+5E0h], rax
0x140254319  mov     rax, [rsi+10h]
0x14025431d  mov     rdx, [rbx]
0x140254320  mov     r8, [rax+28h]; struct DXGPROCESS *
0x140254324  test    rdx, rdx
0x140254327  jz      short loc_14025432D
0x140254329  mov     edx, [rdx]
0x14025432b  jmp     short loc_140254330
0x14025432d  mov     edx, r15d; unsigned int
0x140254330  mov     ebx, 1
0x140254335  lea     r9, [rbp+220h+var_250]; struct DXGHWQUEUE **
0x140254339  mov     byte ptr [rsp+340h+var_318], bl; bool
0x14025433d  lea     rcx, [rbp+220h+var_230]; this
0x140254341  mov     byte ptr [rsp+340h+var_320], bl; bool
0x140254345  call    ??0DXGHWQUEUEBYHANDLE@@QEAA@IPEAVDXGPROCESS@@PEAPEAVDXGHWQUEUE@@_N2@Z; DXGHWQUEUEBYHANDLE::DXGHWQUEUEBYHANDLE(uint,DXGPROCESS *,DXGHWQUEUE * *,bool,bool)
0x14025434a  mov     rcx, [rsi+10h]
0x14025434e  or      r14d, 0FFFFFFFFh
0x140254352  mov     r12d, 40002h
0x140254358  mov     rax, [rcx+28h]
0x14025435c  mov     rax, [rax+58h]
0x140254360  mov     [rbp+220h+var_270], rax
0x140254364  mov     rax, [rcx+768h]
0x14025436b  mov     rax, [rax+0CB0h]
0x140254372  mov     [rbp+220h+var_260], rax
0x140254376  test    rax, rax
0x140254379  jz      short loc_140254387
0x14025437b  mov     rcx, rax; this
0x14025437e  call    ?IsCoreResourceSharedOwner@ADAPTER_DISPLAY@@QEBAEXZ; ADAPTER_DISPLAY::IsCoreResourceSharedOwner(void)
0x140254383  test    al, al
0x140254385  jnz     short loc_1402543CD
0x140254387  mov     ecx, ebx
0x140254389  call    cs:__imp_WdLogSingleEntry0
0x140254390  nop     dword ptr [rax+rax+00h]
0x140254395  mov     [rsp+340h+var_300], r15
0x14025439a  lea     r9, aPdisplaycoreNu; "(pDisplayCore != NULL) && pDisplayCore-"...
0x1402543a1  mov     [rsp+340h+var_308], r15
0x1402543a6  mov     eax, 1C7Dh
0x1402543ab  mov     [rsp+340h+var_310], r15
0x1402543b0  mov     r8d, r14d
0x1402543b3  mov     [rsp+340h+var_318], r15
0x1402543b8  mov     edx, r12d
0x1402543bb  xor     ecx, ecx
0x1402543bd  mov     [rsp+340h+var_320], rax
0x1402543c2  mov     cs:WdLogGlobalForLineNumber, eax
0x1402543c8  call    DxgkLogInternalTriageEvent
0x1402543cd  mov     rcx, [rsi+10h]
0x1402543d1  mov     rcx, [rcx+10h]; this
0x1402543d5  call    ?IsCoreResourceSharedOwner@ADAPTER_RENDER@@QEBAEXZ; ADAPTER_RENDER::IsCoreResourceSharedOwner(void)
0x1402543da  test    al, al
0x1402543dc  jnz     short loc_140254424
0x1402543de  mov     ecx, ebx
0x1402543e0  call    cs:__imp_WdLogSingleEntry0
0x1402543e7  nop     dword ptr [rax+rax+00h]
0x1402543ec  mov     [rsp+340h+var_300], r15
0x1402543f1  lea     r9, aGetrendercoreI_1; "GetRenderCore()->IsCoreResourceSharedOw"...
0x1402543f8  mov     [rsp+340h+var_308], r15
0x1402543fd  mov     eax, 1C7Eh
0x140254402  mov     [rsp+340h+var_310], r15
0x140254407  mov     r8d, r14d
0x14025440a  mov     [rsp+340h+var_318], r15
0x14025440f  mov     edx, r12d
0x140254412  xor     ecx, ecx
0x140254414  mov     [rsp+340h+var_320], rax
0x140254419  mov     cs:WdLogGlobalForLineNumber, eax
0x14025441f  call    DxgkLogInternalTriageEvent
0x140254424  mov     r9, [rdi+48h]
0x140254428  test    r9, r9
0x14025442b  jz      loc_140255713
0x140254431  lea     r13, [rdi+40h]
0x140254435  cmp     [r13+0], r15d
0x140254439  jz      loc_140255713
0x14025443f  mov     ecx, [rdi+58h]
0x140254442  mov     eax, ecx
0x140254444  shr     eax, 1
0x140254446  xor     eax, ecx
0x140254448  test    bl, al
0x14025444a  jz      loc_140255713
0x140254450  test    ecx, 63Ch
0x140254456  jnz     loc_140255713
0x14025445c  xor     edx, edx; Val
0x14025445e  lea     rcx, [rbp+220h+var_200]; void *
0x140254462  mov     r8d, 0A8h; Size
0x140254468  call    memset
0x14025446d  mov     rax, [rsi+10h]
0x140254471  mov     ebx, [rdi+18h]
0x140254474  mov     rax, [rax+28h]
0x140254478  mov     [rbp+220h+var_288], rax
0x14025447c  lea     rcx, [rax+0F8h]; this
0x140254483  mov     [rbp+220h+var_290], rcx
0x140254487  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x14025448c  mov     rcx, [rbp+220h+var_288]
0x140254490  mov     eax, ebx
0x140254492  shr     eax, 6
0x140254495  mov     r15d, 2
0x14025449b  and     eax, 0FFFFFFh
0x1402544a0  mov     r12d, 40000h
0x1402544a6  cmp     eax, [rcx+128h]
0x1402544ac  jnb     short loc_14025452B
0x1402544ae  mov     r8, [rcx+118h]
0x1402544b5  mov     edx, eax
0x1402544b7  add     rdx, rdx
0x1402544ba  shr     ebx, 19h
0x1402544bd  and     ebx, 60h
0x1402544c0  mov     ecx, [r8+rdx*8+8]
0x1402544c5  mov     eax, ecx
0x1402544c7  and     eax, 60h
0x1402544ca  cmp     bl, al
0x1402544cc  jnz     short loc_14025452B
0x1402544ce  bt      ecx, 0Dh
0x1402544d2  jb      short loc_14025452B
0x1402544d4  and     ecx, 1Fh
0x1402544d7  jz      short loc_14025452B
0x1402544d9  cmp     ecx, 5
0x1402544dc  jz      loc_1402545E7
0x1402544e2  mov     ecx, r15d
0x1402544e5  call    cs:__imp_WdLogSingleEntry0
0x1402544ec  nop     dword ptr [rax+rax+00h]
0x1402544f1  xor     eax, eax
0x1402544f3  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x1402544fa  mov     [rsp+340h+var_300], rax
0x1402544ff  mov     ecx, 13Eh
0x140254504  mov     [rsp+340h+var_308], rax
0x140254509  mov     r8d, r14d
0x14025450c  mov     [rsp+340h+var_310], rax
0x140254511  mov     edx, r12d
0x140254514  mov     [rsp+340h+var_318], rax
0x140254519  mov     [rsp+340h+var_320], rcx
0x14025451e  mov     cs:WdLogGlobalForLineNumber, ecx
0x140254524  xor     ecx, ecx
0x140254526  call    DxgkLogInternalTriageEvent
0x14025452b  xor     edx, edx; struct DXGALLOCATION *
0x14025452d  lea     rcx, [rbp+220h+var_278]; this
0x140254531  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x140254536  mov     rax, [rbp+220h+var_290]
0x14025453a  xor     edx, edx
0x14025453c  mov     rcx, rax
0x14025453f  lock dec dword ptr [rax+10h]
0x140254543  call    cs:__imp_ExReleasePushLockSharedEx
0x14025454a  nop     dword ptr [rax+rax+00h]
0x14025454f  call    cs:__imp_KeLeaveCriticalRegion
0x140254556  nop     dword ptr [rax+rax+00h]
0x14025455b  cmp     [rbp+220h+var_278], 0
0x140254560  jnz     loc_1402545F0
0x140254566  mov     ecx, [r13+0]
0x14025456a  mov     rbx, 0FFFFFFFFC000000Dh
0x140254571  mov     eax, [rdi+18h]
0x140254574  mov     r8, rsi
0x140254577  mov     r9, [rdi+48h]
0x14025457b  mov     rdx, rbx
0x14025457e  mov     [rsp+340h+var_318], rax
0x140254583  mov     [rsp+340h+var_320], rcx
0x140254588  mov     ecx, r15d
0x14025458b  call    cs:__imp_WdLogSingleEntry5
0x140254592  nop     dword ptr [rax+rax+00h]
0x140254597  mov     cs:WdLogGlobalForLineNumber, 1C9Ah
0x1402545a1  lea     r9, a0xI64x0xI64xFa_0; "0x%I64x 0x%I64x fails Present invalid p"...
0x1402545a8  mov     ecx, [r13+0]
0x1402545ac  mov     edx, r12d
0x1402545af  mov     eax, [rdi+18h]
0x1402545b2  mov     [rsp+340h+var_300], rax
0x1402545b7  mov     [rsp+340h+var_308], rcx
0x1402545bc  mov     rcx, [rdi+48h]
0x1402545c0  mov     [rsp+340h+var_310], rcx
0x1402545c5  mov     [rsp+340h+var_318], rsi
0x1402545ca  mov     r8d, r14d
0x1402545cd  mov     [rsp+340h+var_320], rbx
0x1402545d2  xor     ecx, ecx
0x1402545d4  call    DxgkLogInternalTriageEvent
0x1402545d9  lea     rcx, [rbp+220h+var_278]; this
0x1402545dd  call    ??1DXGALLOCATIONREFERENCE@@QEAA@XZ; DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE(void)
0x1402545e2  jmp     loc_140255784
0x1402545e7  mov     rdx, [r8+rdx*8]
0x1402545eb  jmp     loc_14025452D
0x1402545f0  mov     eax, [rdi+58h]
0x1402545f3  test    al, 1
0x1402545f5  jz      loc_140254769
0x1402545fb  mov     rax, [rsi+10h]
0x1402545ff  mov     ebx, [rdi+14h]
0x140254602  mov     rax, [rax+28h]
0x140254606  mov     [rbp+220h+var_288], rax
0x14025460a  lea     rcx, [rax+0F8h]; this
0x140254611  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x140254616  mov     rcx, [rbp+220h+var_288]
0x14025461a  mov     eax, ebx
0x14025461c  shr     eax, 6
0x14025461f  and     eax, 0FFFFFFh
0x140254624  cmp     eax, [rcx+128h]
0x14025462a  jnb     short loc_1402546A9
0x14025462c  mov     r8, [rcx+118h]
0x140254633  mov     edx, eax
0x140254635  add     rdx, rdx
0x140254638  shr     ebx, 19h
0x14025463b  and     ebx, 60h
0x14025463e  mov     ecx, [r8+rdx*8+8]
0x140254643  mov     eax, ecx
0x140254645  and     eax, 60h
0x140254648  cmp     bl, al
0x14025464a  jnz     short loc_1402546A9
0x14025464c  bt      ecx, 0Dh
0x140254650  jb      short loc_1402546A9
0x140254652  and     ecx, 1Fh
0x140254655  jz      short loc_1402546A9
0x140254657  cmp     ecx, 5
0x14025465a  jz      loc_140254757
0x140254660  mov     ecx, r15d
0x140254663  call    cs:__imp_WdLogSingleEntry0
0x14025466a  nop     dword ptr [rax+rax+00h]
0x14025466f  xor     eax, eax
0x140254671  lea     r9, aHandleTypeMism; "Handle type mismatch"
0x140254678  mov     [rsp+340h+var_300], rax
0x14025467d  mov     ecx, 13Eh
0x140254682  mov     [rsp+340h+var_308], rax
0x140254687  mov     r8d, r14d
0x14025468a  mov     [rsp+340h+var_310], rax
0x14025468f  mov     edx, r12d
0x140254692  mov     [rsp+340h+var_318], rax
0x140254697  mov     [rsp+340h+var_320], rcx
0x14025469c  mov     cs:WdLogGlobalForLineNumber, ecx
0x1402546a2  xor     ecx, ecx
0x1402546a4  call    DxgkLogInternalTriageEvent
0x1402546a9  xor     edx, edx; struct DXGALLOCATION *
0x1402546ab  lea     rcx, [rbp+220h+var_290]; this
0x1402546af  call    ??0DXGALLOCATIONREFERENCE@@QEAA@PEAVDXGALLOCATION@@@Z; DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE(DXGALLOCATION *)
0x1402546b4  mov     rax, [rbp+220h+var_288]
0x1402546b8  xor     edx, edx
0x1402546ba  lock dec dword ptr [rax+108h]
0x1402546c1  lea     rcx, [rax+0F8h]
0x1402546c8  call    cs:__imp_ExReleasePushLockSharedEx
0x1402546cf  nop     dword ptr [rax+rax+00h]
0x1402546d4  call    cs:__imp_KeLeaveCriticalRegion
0x1402546db  nop     dword ptr [rax+rax+00h]
0x1402546e0  cmp     [rbp+220h+var_290], 0
0x1402546e5  jnz     short loc_140254760
0x1402546e7  mov     r9d, [rdi+14h]
0x1402546eb  mov     rbx, 0FFFFFFFFC000000Dh
0x1402546f2  mov     rdx, rbx
0x1402546f5  mov     r8, rsi
0x1402546f8  mov     ecx, r15d
0x1402546fb  call    cs:__imp_WdLogSingleEntry3
0x140254702  nop     dword ptr [rax+rax+00h]
0x140254707  mov     [rsp+340h+var_300], 0
  ... truncated ...
```
