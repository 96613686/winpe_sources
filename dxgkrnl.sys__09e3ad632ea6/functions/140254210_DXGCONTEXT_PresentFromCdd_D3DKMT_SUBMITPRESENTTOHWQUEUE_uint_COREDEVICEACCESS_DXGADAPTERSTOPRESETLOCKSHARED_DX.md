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
  int v70; // [rsp+20h] [rbp-100h]
  int v71; // [rsp+28h] [rbp-F8h]
  int v72; // [rsp+40h] [rbp-E0h]
  unsigned int v74; // [rsp+A0h] [rbp-80h]
  struct VIDMM_DMA_BUFFER *v75; // [rsp+A8h] [rbp-78h] BYREF
  volatile signed __int32 *v76; // [rsp+B0h] [rbp-70h] BYREF
  struct VIDSCH_SUBMIT_DATA_BASE *v77[2]; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v78; // [rsp+C8h] [rbp-58h] BYREF
  struct VIDMM_DMA_BUFFER *v79; // [rsp+D0h] [rbp-50h]
  unsigned int *v80; // [rsp+D8h] [rbp-48h] BYREF
  ADAPTER_DISPLAY *v81; // [rsp+E0h] [rbp-40h]
  union _LARGE_INTEGER v82; // [rsp+E8h] [rbp-38h] BYREF
  struct DXGHWQUEUE *v83; // [rsp+F0h] [rbp-30h] BYREF
  DXGCONTEXT *v84; // [rsp+F8h] [rbp-28h]
  COREDEVICEACCESS *v85; // [rsp+100h] [rbp-20h]
  DXGADAPTERSTOPRESETLOCKSHARED *v86; // [rsp+108h] [rbp-18h]
  _BYTE v87[16]; // [rsp+110h] [rbp-10h] BYREF
  _BYTE v88[24]; // [rsp+120h] [rbp+0h] BYREF
  unsigned int *v89; // [rsp+138h] [rbp+18h]
  struct _DXGKARG_PRESENT v90; // [rsp+140h] [rbp+20h] BYREF
  _DWORD v91[16]; // [rsp+1F0h] [rbp+D0h] BYREF
  _DWORD v92[16]; // [rsp+230h] [rbp+110h] BYREF
  _DWORD v93[16]; // [rsp+270h] [rbp+150h] BYREF
  _DWORD v94[16]; // [rsp+2B0h] [rbp+190h] BYREF

  v86 = a5;
  v7 = this;
  v82.QuadPart = (LONGLONG)a6;
  v85 = a4;
  v84 = this;
  Global = (struct _LOOKASIDE_LIST_EX *)DXGGLOBAL::GetGlobal();
  v9 = (unsigned int *)ExAllocateFromLookasideListEx(Global + 12);
  v89 = v9;
  v10 = v9;
  if ( v9 )
  {
    memset(v9, 0, 0x5F8u);
    v80 = v10;
    v83 = 0;
    memmove(v10, &a2->PrivatePresentData, 0x5D8u);
    *((_QWORD *)v10 + 188) = &v83;
    if ( a2->hHwQueues )
      v12 = *a2->hHwQueues;
    else
      v12 = 0;
    DXGHWQUEUEBYHANDLE::DXGHWQUEUEBYHANDLE(
      (DXGHWQUEUEBYHANDLE *)v87,
      v12,
      *(struct DXGPROCESS **)(*((_QWORD *)v7 + 2) + 40LL),
      &v83,
      1,
      1);
    v13 = *((_QWORD *)v7 + 2);
    v79 = *(struct VIDMM_DMA_BUFFER **)(*(_QWORD *)(v13 + 40) + 88LL);
    v14 = *(ADAPTER_DISPLAY **)(*(_QWORD *)(v13 + 1896) + 3248LL);
    v81 = v14;
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
    v15 = *((_QWORD *)v10 + 9);
    if ( !v15
      || (v16 = v10 + 16, !v10[16])
      || (v17 = v10[22], (((unsigned __int8)v17 ^ (unsigned __int8)(v17 >> 1)) & 1) == 0)
      || (v17 & 0x63C) != 0 )
    {
      v11 = -1073741811;
      WdLogSingleEntry5(2, -1073741811, v7, v15, v10[16], v10[22]);
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
    memset(&v90, 0, sizeof(v90));
    v18 = v10[6];
    v77[0] = *(struct VIDSCH_SUBMIT_DATA_BASE **)(*((_QWORD *)v7 + 2) + 40LL);
    v76 = (volatile signed __int32 *)((char *)v77[0] + 248);
    DXGPUSHLOCK::AcquireShared((struct VIDSCH_SUBMIT_DATA_BASE *)((char *)v77[0] + 248));
    v19 = (v18 >> 6) & 0xFFFFFF;
    if ( v19 < *((_DWORD *)v77[0] + 74) )
    {
      v20 = *((_QWORD *)v77[0] + 35);
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
            DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v78, v22);
            _InterlockedDecrement(v76 + 4);
            ExReleasePushLockSharedEx(v76, 0);
            KeLeaveCriticalRegion();
            if ( !v78 )
            {
              v11 = -1073741811;
              WdLogSingleEntry5(2, -1073741811, v7, *((_QWORD *)v10 + 9), *v16, v10[6]);
              WdLogGlobalForLineNumber = 7322;
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
              DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v78);
LABEL_147:
              DXGHWQUEUEBYHANDLE::~DXGHWQUEUEBYHANDLE((DXGHWQUEUEBYHANDLE *)v87);
              DXGADAPTER::SubmitPresentHistoryTokenFromVm_::_45_::ENSURE_DELETE::_ENSURE_DELETE(&v80);
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
                WdLogSingleEntry4(6, -1073741801);
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
                (CVidSchSubmitData *)v77,
                *(struct ADAPTER_RENDER **)(*((_QWORD *)v7 + 2) + 16LL),
                1);
              v31 = v77[0];
              if ( !v77[0] )
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
                CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v77);
                v11 = -1073741801;
                goto LABEL_24;
              }
              *(_DWORD *)v77[0] |= 0x10000u;
              v32 = *(_DWORD *)v31;
              if ( (v10[22] & 0x4000) == 0 )
                v32 |= 1u;
              *(_DWORD *)v31 = v32 | 0x100;
              v33 = *((_QWORD *)v7 + 2);
              v34 = (struct VIDMM_DMA_POOL *)*((_QWORD *)v7 + 29);
              v75 = 0;
              v11 = VIDMM_EXPORT::VidMmAcquireDmaBuffer(
                      *(VIDMM_EXPORT **)(*(_QWORD *)(v33 + 16) + 760LL),
                      v34,
                      0,
                      1,
                      &v75);
              if ( v11 < 0 )
                goto LABEL_76;
              if ( !v75 )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 7376;
                DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"pVidMmDmaBuffer", 7376, 0, 0, 0, 0);
              }
              DXGPRESENTMUTEX::DXGPRESENTMUTEX(
                (DXGPRESENTMUTEX *)v88,
                *(struct ADAPTER_RENDER *const *)(*((_QWORD *)v7 + 2) + 16LL));
              if ( (v10[22] & 0x4000) == 0 )
              {
                v35 = v85;
                COREDEVICEACCESS::Release(v85);
                DXGADAPTERSTOPRESETLOCKSHARED::~DXGADAPTERSTOPRESETLOCKSHARED(v86);
                DXGPRESENTMUTEX::Acquire((DXGPRESENTMUTEX *)v88);
                DXGADAPTERSTOPRESETLOCKSHARED::Acquire(v86);
                v36 = COREDEVICEACCESS::AcquireShared(v35, 0);
                v11 = v36;
                if ( v36 < 0 )
                {
                  WdLogSingleEntry2(4, v36, v7);
                  WdLogGlobalForLineNumber = 7394;
                  COREDEVICEACCESS::AcquireSharedUncheck(v35, v38);
                  VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                    *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                    v75);
LABEL_75:
                  DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v88);
LABEL_76:
                  CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v77);
                  goto LABEL_24;
                }
                v39 = 0;
                if ( v79 )
                {
                  v40 = *((_QWORD *)v7 + 19);
                  if ( *(_DWORD *)(v40 + 8) != (*((unsigned int (**)(void))v79 + 1))() )
                  {
                    *(_DWORD *)(v40 + 8) = (*((__int64 (**)(void))v79 + 1))();
                    DXGDEVICE::FlushScheduler(*((_QWORD *)v7 + 2), 2, 4294967293LL, 0, v70);
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
                if ( (*(_DWORD *)(*(_QWORD *)(v78 + 48) + 4LL) & 2) != 0 )
                {
                  updated = DxgkCddUpdatePresentRects(v81, a3, (const struct tagRECT **)v10 + 9, v10 + 16);
                  v11 = updated;
                  if ( updated < 0 )
                  {
                    WdLogSingleEntry3(4, updated, *((_QWORD *)v7 + 2), a3);
                    WdLogGlobalForLineNumber = 7432;
                    v43 = *(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL);
LABEL_74:
                    VIDMM_EXPORT::VidMmReleaseDmaBuffer(*(VIDMM_EXPORT **)(v43 + 760), v75);
                    v75 = 0;
                    goto LABEL_75;
                  }
                  if ( !*v16 )
                  {
                    WdLogSingleEntry4(4, 0);
                    WdLogGlobalForLineNumber = 7447;
                    VIDMM_EXPORT::VidMmReleaseDmaBuffer(
                      *(VIDMM_EXPORT **)(*(_QWORD *)(*((_QWORD *)v7 + 2) + 16LL) + 760LL),
                      v75);
                    v75 = 0;
                    DXGPRESENTMUTEX::Release((DXGPRESENTMUTEX *)v88);
                    CVidSchSubmitData::~CVidSchSubmitData((CVidSchSubmitData *)v77);
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
              v90.DstRect = (RECT)*((_OWORD *)v10 + 2);
              v44 = *v16;
              v45 = v81;
              v90.SubRectCnt = v44;
              if ( (v10[22] & 0x4000) != 0 )
              {
                Value = v90.Flags.Value;
              }
              else
              {
                CurrentOrientation = ADAPTER_DISPLAY::GetCurrentOrientation(v81, a3, 1);
                Value = (CurrentOrientation != 1 ? 0x80 : 0) | v90.Flags.Value & 0xFFFFFF7F;
                v90.Flags.Value = Value;
              }
              v48 = v10[22];
              if ( (v48 & 1) != 0 )
              {
                v90.Flags.Value = Value | 1;
                v90.SrcRect = (RECT)*((_OWORD *)v10 + 3);
                if ( v10[5] == v10[6] )
                {
                  if ( (v10[22] & 0x4000) == 0 && ADAPTER_DISPLAY::GetVidPnSourceOwnerType(v45, a3) )
                  {
                    v11 = -1071774910;
                    WdLogSingleEntry4(4, -1071774910);
                    WdLogGlobalForLineNumber = 7505;
                    goto LABEL_73;
                  }
                  DdiSubRectList = DXGPRESENT::GetDdiSubRectList(*((DXGPRESENT **)v7 + 19), 0);
                  v90.pDstSubRects = DdiSubRectList;
                  if ( v90.DstRect.right - v90.DstRect.left != v90.SrcRect.right - v90.SrcRect.left )
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
                  if ( v90.DstRect.bottom - v90.DstRect.top != v90.SrcRect.bottom - v90.SrcRect.top )
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
                  if ( v90.SrcRect.left >= v90.SrcRect.right )
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
                  if ( v90.SrcRect.left < 0 )
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
                  v50 = 4024LL * a3;
                  if ( v90.SrcRect.right > *(_DWORD *)(v50 + *((_QWORD *)v45 + 16) + 636)
                                         - *(_DWORD *)(v50 + *((_QWORD *)v45 + 16) + 628) )
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
                  if ( v90.DstRect.top >= v90.DstRect.bottom )
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
                  if ( v90.DstRect.top < 0 )
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
                  if ( v90.SrcRect.bottom > *(_DWORD *)(v50 + *((_QWORD *)v45 + 16) + 640)
                                          - *(_DWORD *)(v50 + *((_QWORD *)v45 + 16) + 632) )
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
                  v51 = 0;
                  v74 = v90.DstRect.left - v90.SrcRect.left;
                  if ( v90.SubRectCnt )
                  {
                    v52 = v90.DstRect.top - v90.SrcRect.top;
                    do
                    {
                      v53 = v51;
                      v54 = v74 + (*v41)[v51].left;
                      DdiSubRectList[v53].left = v54;
                      v55 = v74 + (*v41)[v51].right;
                      DdiSubRectList[v53].right = v55;
                      DdiSubRectList[v53].top = v52 + (*v41)[v51].top;
                      DdiSubRectList[v53].bottom = v52 + (*v41)[v51].bottom;
                      if ( v54 >= v55 )
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
                      if ( DdiSubRectList[v51].left < v90.DstRect.left )
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
                      if ( DdiSubRectList[v51].right > v90.DstRect.right )
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
                      if ( DdiSubRectList[v51].top >= DdiSubRectList[v51].bottom )
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
                      if ( DdiSubRectList[v51].top < v90.DstRect.top )
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
                      if ( DdiSubRectList[v51].bottom > v90.DstRect.bottom )
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
                      ++v51;
                    }
                    while ( v51 < v90.SubRectCnt );
                    v10 = v89;
                    v7 = v84;
                  }
                }
                else
                {
                  v90.pDstSubRects = *v41;
                }
                for ( i = 0; i < v90.SubRectCnt; ++i )
                {
                  if ( (*v41)[i].left >= (*v41)[i].right )
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
                  if ( (*v41)[i].top >= (*v41)[i].bottom )
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
                    if ( (*v41)[i].left < v90.SrcRect.left )
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
                    if ( (*v41)[i].right > v90.SrcRect.right )
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
                    if ( (*v41)[i].top < v90.SrcRect.top )
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
                    if ( (*v41)[i].bottom > v90.SrcRect.bottom )
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
                if ( (v48 & 2) == 0 )
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
                  Value = v90.Flags.Value;
                }
                v90.Flags.Value = Value | 2;
                v90.Color = v10[7];
                v90.pDstSubRects = *v41;
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
              pDstSubRects = v90.pDstSubRects;
              SubRectCnt = v90.SubRectCnt;
              v79 = v75;
              if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20) != 0 )
                McTemplateK0ppxppttqddddddddq_EtwWriteTransfer(
                  v90.DstRect.top,
                  v90.DstRect.right,
                  v90.DstRect.left,
                  0,
                  (char)v79,
                  v71,
                  v59,
                  v57,
                  v72,
                  0,
                  *(_BYTE *)&v90.Flags.0,
                  v90.SrcRect.left,
                  v90.SrcRect.right,
                  v90.SrcRect.top,
                  v90.SrcRect.bottom,
                  v90.DstRect.left,
                  v90.DstRect.right,
                  v90.DstRect.top,
                  v90.DstRect.bottom,
                  v90.SubRectCnt);
              v62 = 0;
              if ( !SubRectCnt )
              {
LABEL_142:
                v68 = v85;
                v11 = DXGCONTEXT::SubmitPresent(
                        v7,
                        (struct _D3DKMT_PRESENT *)v10,
                        *((struct DXGHWQUEUE ***)v10 + 188),
                        v10[23],
                        (struct DXGCONTEXT **)v82.QuadPart,
                        0,
                        v10[5],
                        v10[6],
                        &v90,
                        0,
                        v75,
                        v77[0],
                        D3DDDIFMT_A8B8G8R8,
                        v85);
                if ( v11 >= 0 && v10[90] == 1 )
                {
                  v82.QuadPart = -100000;
                  v11 = SubmitPresentHistoryToken(
                          (const struct _D3DKMT_PRESENTHISTORYTOKEN *)(v10 + 90),
                          v68,
                          v86,
                          0,
                          0,
                          &v82,
                          (struct DXGK_PRESENT_PARAMS *)v10,
                          0,
                          v7,
                          0,
                          0);
                }
                goto LABEL_75;
              }
              v63 = (int)v79;
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
                    (unsigned int)v94,
                    v58 * 2,
                    v65,
                    v63,
                    SubRectCnt - v62 <= 0x10,
                    v66,
                    (__int64)v94,
                    (__int64)v93,
                    (__int64)v92,
                    (__int64)v91);
                v62 += 16;
                if ( v62 >= SubRectCnt )
                {
                  v7 = v84;
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
                v94[v67] = pDstSubRects[v58].left;
                v93[v67] = pDstSubRects[v58].right;
                v92[v67] = pDstSubRects[v58].top;
                v91[v67] = pDstSubRects[v58].bottom;
              }
              while ( v64 < v66 );
              goto LABEL_138;
            }
            v23 = v10[5];
            v77[0] = *(struct VIDSCH_SUBMIT_DATA_BASE **)(*((_QWORD *)v7 + 2) + 40LL);
            DXGPUSHLOCK::AcquireShared((struct VIDSCH_SUBMIT_DATA_BASE *)((char *)v77[0] + 248));
            v24 = (v23 >> 6) & 0xFFFFFF;
            if ( v24 < *((_DWORD *)v77[0] + 74) )
            {
              v25 = *((_QWORD *)v77[0] + 35);
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
            DXGALLOCATIONREFERENCE::DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v76, v27);
            v28 = v77[0];
            _InterlockedDecrement((volatile signed __int32 *)v77[0] + 66);
            ExReleasePushLockSharedEx((char *)v28 + 248, 0);
            KeLeaveCriticalRegion();
            if ( !v76 )
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
              DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v76);
              goto LABEL_24;
            }
            DXGALLOCATIONREFERENCE::~DXGALLOCATIONREFERENCE((DXGALLOCATIONREFERENCE *)&v76);
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
