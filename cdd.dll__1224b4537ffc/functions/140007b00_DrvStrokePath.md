# DrvStrokePath

- ea: `0x140007b00`
- end: `0x14000870e`
- name: `DrvStrokePath`
- size: `3086`
- prototype: `FN_DrvStrokePath`
- caller_count: `0`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001008`
- `0x140002470`
- `0x140004600`
- `0x140006a30`
- `0x140007b00`
- `0x14000c010`
- `0x14000c730`
- `0x14000cb44`
- `0x14000cec4`
- `0x14000df80`
- `0x14000ef80`
- `0x14000fdb0`
- `0x140015d40`
- `0x1400160c8`
- `0x140017404`
- `0x14001d458`
- `0x14001d488`
- `0x1400226b0`
- `0x1400248f8`
- `0x1400313f0`
- `0x140033db0`
- `0x140033e60`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x140007e7c`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000806c`
- `ntoskrnl!KeReleaseSemaphore` at `0x140007e7c`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000806c`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140007e92`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140008085`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140007e92`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140008085`
- `ntoskrnl!DbgPrint` at `0x140007fb0`
- `ntoskrnl!DbgPrint` at `0x140007fb0`
- `ntoskrnl!KdDebuggerEnabled` at `0x140007f9d`
- `watchdog!WdLogNewEntry5_WdError` at `0x140007fda`
- `watchdog!WdLogNewEntry5_WdError` at `0x140007fda`
- `watchdog!WdLogSingleEntry0` at `0x140007fc1`
- `watchdog!WdLogSingleEntry0` at `0x1400080f5`
- `watchdog!WdLogSingleEntry0` at `0x1400083b2`
- `watchdog!WdLogSingleEntry0` at `0x140007fc1`
- `watchdog!WdLogSingleEntry0` at `0x1400080f5`
- `watchdog!WdLogSingleEntry0` at `0x1400083b2`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000810c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400083c9`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000810c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400083c9`
- `WIN32K!EngStrokePath` at `0x14000820b`
- `WIN32K!EngStrokePath` at `0x1400084aa`
- `WIN32K!EngStrokePath` at `0x140008695`
- `WIN32K!EngStrokePath` at `0x14000820b`
- `WIN32K!EngStrokePath` at `0x1400084aa`
- `WIN32K!EngStrokePath` at `0x140008695`
- `WIN32K!PATHOBJ_vGetBounds` at `0x140007b8f`
- `WIN32K!PATHOBJ_vGetBounds` at `0x140007b8f`
- `WIN32K!EngReleaseSemaphore` at `0x1400085b2`
- `WIN32K!EngReleaseSemaphore` at `0x1400085d1`
- `WIN32K!EngReleaseSemaphore` at `0x1400085b2`
- `WIN32K!EngReleaseSemaphore` at `0x1400085d1`
- `WIN32K!EngAcquireSemaphore` at `0x140008550`
- `WIN32K!EngAcquireSemaphore` at `0x140008550`

## string_xrefs

- `0x140007fa9`: `Error submitting ColorFill command`

## pseudocode

```c
BOOL __stdcall DrvStrokePath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        XFORMOBJ *pxo,
        BRUSHOBJ *pbo,
        POINTL *pptlBrushOrg,
        LINEATTRS *plineattrs,
        MIX mix)
{
  int v9; // r14d
  int v10; // r15d
  DHPDEV dhpdev; // rbx
  struct _RECTL *p_rclBounds; // rsi
  LONG right; // r9d
  LONG bottom; // r10d
  FIX left; // edx
  FIX top; // r8d
  __int64 v17; // rdx
  int v18; // ecx
  bool v19; // zf
  DHSURF dhsurf; // rdi
  __int64 v21; // r14
  ULONG iSolidColor; // r12d
  _QWORD *v23; // rbx
  SURFOBJ *v24; // rcx
  LONG lDelta; // eax
  struct tagRECT *RectBuffer; // rcx
  int v27; // r8d
  __int64 v28; // rdi
  _QWORD *v29; // rax
  __int64 v30; // rcx
  PATHOBJ *v32; // r12
  CDDPDEV **v33; // rcx
  _QWORD *v34; // rax
  __int64 v35; // r14
  _QWORD *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  CddBitmap *v39; // rax
  _QWORD *v40; // rax
  SURFOBJ *v41; // rbx
  LONG v42; // ecx
  int v43; // eax
  CLIPOBJ *v44; // rbx
  __int64 v45; // rax
  int (__fastcall *v46)(DHSURF, struct _RECTL *, struct _RECTL *, CLIPOBJ *, int, int, SURFOBJ **, SURFOBJ **, char); // rax
  int v47; // r8d
  _QWORD *v48; // rax
  DHSURF v49; // rbx
  int v50; // eax
  DHSURF v51; // rbx
  HSEMAPHORE v52; // rdi
  int v53; // esi
  SURFOBJ *v54; // [rsp+50h] [rbp-B0h] BYREF
  enum _DXGK_GDIROP_COLORFILL v55; // [rsp+58h] [rbp-A8h] BYREF
  CLIPOBJ *pcoa; // [rsp+60h] [rbp-A0h] BYREF
  BRUSHOBJ *v57; // [rsp+68h] [rbp-98h]
  LINEATTRS *v58; // [rsp+70h] [rbp-90h]
  POINTL *v59; // [rsp+78h] [rbp-88h]
  XFORMOBJ *pxoa; // [rsp+80h] [rbp-80h]
  __int64 v61; // [rsp+88h] [rbp-78h] BYREF
  __int64 v62; // [rsp+90h] [rbp-70h]
  PATHOBJ *ppoa[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v64; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v65; // [rsp+B0h] [rbp-50h]
  __int64 v66; // [rsp+B8h] [rbp-48h]
  int v67; // [rsp+C0h] [rbp-40h]
  _BYTE v68[16]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v69; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v70; // [rsp+E8h] [rbp-18h]
  __int128 v71; // [rsp+F8h] [rbp-8h]
  SURFOBJ *psoa[8]; // [rsp+110h] [rbp+10h] BYREF
  CddBitmap *v73; // [rsp+150h] [rbp+50h]
  struct _RECTL *v74; // [rsp+158h] [rbp+58h]
  struct _RECTL v75; // [rsp+160h] [rbp+60h] BYREF
  SURFOBJ *v76[8]; // [rsp+170h] [rbp+70h] BYREF
  CLIPOBJ *v77; // [rsp+1B0h] [rbp+B0h]
  DHSURF v78; // [rsp+1B8h] [rbp+B8h]
  SURFOBJ *pvScan0; // [rsp+1C0h] [rbp+C0h]
  DHSURF v80; // [rsp+1C8h] [rbp+C8h]
  DHPDEV v81; // [rsp+1D0h] [rbp+D0h]
  int v82; // [rsp+1D8h] [rbp+D8h]
  int v83; // [rsp+1DCh] [rbp+DCh]
  enum _DXGK_GDIROP_COLORFILL v84; // [rsp+1E0h] [rbp+E0h]
  PVOID pvBits; // [rsp+1E8h] [rbp+E8h]
  LONG v86; // [rsp+1F0h] [rbp+F0h]
  struct tagRECT *v87; // [rsp+1F8h] [rbp+F8h]
  unsigned int v88[4]; // [rsp+200h] [rbp+100h]
  _RECTFX prectfx; // [rsp+210h] [rbp+110h] BYREF

  v54 = pso;
  v59 = pptlBrushOrg;
  v9 = 0;
  v58 = plineattrs;
  v10 = 0;
  ppoa[0] = ppo;
  pcoa = pco;
  dhpdev = pso->dhpdev;
  pxoa = pxo;
  v57 = pbo;
  prectfx = 0;
  v75 = 0;
  PATHOBJ_vGetBounds(ppo, &prectfx);
  p_rclBounds = &v75;
  right = (prectfx.xRight + 15) >> 4;
  bottom = (prectfx.yBottom + 15) >> 4;
  left = prectfx.xLeft >> 4;
  top = prectfx.yTop >> 4;
  v75.left = prectfx.xLeft >> 4;
  v75.top = prectfx.yTop >> 4;
  v75.right = right;
  v75.bottom = bottom;
  if ( pcoa )
  {
    if ( pcoa->iDComplexity )
    {
      p_rclBounds = &pcoa->rclBounds;
    }
    else
    {
      if ( pcoa->rclBounds.left < left )
        left = pcoa->rclBounds.left;
      v75.left = left;
      if ( pcoa->rclBounds.top < top )
        top = pcoa->rclBounds.top;
      v75.top = top;
      if ( pcoa->rclBounds.right > right )
        right = pcoa->rclBounds.right;
      v75.right = right;
      if ( pcoa->rclBounds.bottom > bottom )
        bottom = pcoa->rclBounds.bottom;
      v75.bottom = bottom;
    }
  }
  v67 = 1;
  v69 = 0;
  v66 = 0;
  v70 = 0;
  v71 = 0;
  if ( (*((unsigned int (**)(void))dhpdev + 10))() )
  {
    v70 = 0;
    v69 = 0;
    v71 = 0;
    DWORD1(v69) = pso->iType;
    LODWORD(v70) = p_rclBounds->right - p_rclBounds->left;
    v18 = p_rclBounds->bottom - p_rclBounds->top;
    v19 = pbo->iSolidColor == -1;
    LODWORD(v71) = (unsigned __int16)mix;
    DWORD1(v70) = v18;
    HIDWORD(v70) = !v19;
    CDDETWPROFILER::Init((CDDETWPROFILER *)&v64, (struct CDDPDEV *)dhpdev, 0xBCFu, (struct _DXGKETW_PARAMS *)&v69, 0);
  }
  if ( pso->iType == 1 )
  {
    v52 = (HSEMAPHORE)*((_QWORD *)dhpdev + 365);
    v53 = 0;
    if ( v52 )
    {
      EngAcquireSemaphore(v52);
      v53 = 1;
    }
    if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
    {
      if ( v52 && v53 )
        EngReleaseSemaphore(v52);
      v9 = 1;
    }
    else
    {
      CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 56LL) = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
      LOBYTE(v9) = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) != 0;
      if ( v52 && v53 )
        EngReleaseSemaphore(v52);
    }
    if ( v9 )
    {
      ReadFromFrameBuffer((struct CDDPDEV *)dhpdev, v75.left, v75.top, v75.right, v75.bottom);
      v55 = DXGK_GDIROPCF_INVALID;
      CDDSURFLOCK::vInit((CDDSURFLOCK *)v76, (struct CDDPDEV *)dhpdev, &v54, &v75, (int *)&v55, pcoa);
      if ( (unsigned int)bIgnoreDeviceSurfaceUpdates(pso, &pcoa) )
      {
        CDDSURFLOCK::vDone((CDDSURFLOCK *)v76);
        CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v64);
        return 1;
      }
      v10 = EngStrokePath(v54, ppoa[0], pcoa, pxoa, v57, v59, v58, mix);
      if ( v10 && v55 == DXGK_GDIROPCF_PATCOPY )
        vGDIDirtyUpdate((struct CDDPDEV *)dhpdev, &v75, pcoa);
      CDDSURFLOCK::vDone((CDDSURFLOCK *)v76);
    }
    goto LABEL_89;
  }
  dhsurf = pso->dhsurf;
  v21 = *((_QWORD *)pso->dhsurf + 1);
  CDDBITMAPLOCK::CDDBITMAPLOCK((CDDBITMAPLOCK *)v68, (struct CddBitmap *)pso->dhsurf);
  if ( !(*((_DWORD *)&ROP2_NEED_DEST + (((_BYTE)mix - 1) & 0xF))
       | *((_DWORD *)&ROP2_NEED_DEST + ((BYTE1(mix) - 1) & 0xF)))
    && ((_DWORD)dhsurf[32] & 1) != 0 )
  {
    v55 = DXGK_GDIROPCF_PATCOPY;
    iSolidColor = v57->iSolidColor;
    LODWORD(v54) = iSolidColor;
    if ( iSolidColor == -1 || mix != 3341 )
    {
      if ( !(unsigned int)ComputeColorFillParams(mix, (unsigned int *)&v54, &v55) )
      {
        v32 = ppoa[0];
        goto LABEL_43;
      }
      iSolidColor = (unsigned int)v54;
    }
    TempSurfObjHelper::TempSurfObjHelper((TempSurfObjHelper *)&v61, (struct CDDPDEV *)v21, (struct CddBitmap *)dhsurf);
    v23 = (_QWORD *)v61;
    v24 = *(SURFOBJ **)(v61 + 16);
    v76[0] = (SURFOBJ *)EngWritePixelCallback;
    v76[1] = (SURFOBJ *)EngFillRectCallback;
    v82 = *((_DWORD *)dhsurf + 10);
    pvBits = 0;
    v86 = 0;
    v84 = v55;
    LOBYTE(v77) = 0;
    v80 = 0;
    *(_QWORD *)v88 = 0;
    v87 = 0;
    v76[2] = 0;
    v76[3] = (SURFOBJ *)p_rclBounds;
    v76[4] = (SURFOBJ *)p_rclBounds;
    v76[5] = (SURFOBJ *)p_rclBounds;
    v81 = (DHPDEV)dhsurf;
    v83 = iSolidColor;
    pvBits = v24->pvBits;
    lDelta = v24->lDelta;
    v54 = v24;
    v86 = lDelta;
    RectBuffer = CddBitmapHw::GetRectBuffer((CddBitmapHw *)dhsurf);
    v87 = RectBuffer;
    v88[1] = (unsigned int)dhsurf[298];
    if ( !v82 )
    {
      v28 = v62;
      CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v61, *(struct CDDMUTEX **)(*(_QWORD *)(v62 + 5504) + 2904LL), v27);
      v29 = (_QWORD *)(v28 + 6296);
      v30 = *(_QWORD *)(v28 + 6296);
      if ( *(_QWORD *)(v30 + 8) == v28 + 6296 )
      {
        *v23 = v30;
        v23[1] = v29;
        *(_QWORD *)(v30 + 8) = v23;
        *v29 = v23;
        KeReleaseSemaphore(*(PRKSEMAPHORE *)(v28 + 6312), 0, 1, 0);
        if ( (_DWORD)v62 )
          ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v61);
LABEL_26:
        CDDBITMAPLOCK::~CDDBITMAPLOCK((CDDBITMAPLOCK *)v68);
        CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v64);
        return 1;
      }
LABEL_37:
      __fastfail(3u);
    }
    v32 = ppoa[0];
    if ( RectBuffer )
    {
      v10 = (*(__int64 (__fastcall **)(SURFOBJ *, PATHOBJ *, CLIPOBJ *, XFORMOBJ *, BRUSHOBJ *, POINTL *, LINEATTRS *, MIX, SURFOBJ **))(v21 + 632))(
              v54,
              ppoa[0],
              pcoa,
              pxoa,
              v57,
              v59,
              v58,
              mix,
              v76);
      if ( v10 )
      {
        if ( v88[0] )
        {
          CCommandBufferMutex::CCommandBufferMutex((CCommandBufferMutex *)ppoa, (struct CDDPDEV *)v21, 0, 0);
          v33 = *(CDDPDEV ***)(v21 + 12696);
          v76[6] = (SURFOBJ *)ppoa;
          if ( !(unsigned int)CHwCommandBuffer::AddColorFillCommand(v33, (struct COLORFILL_DATA *)&v76[2], v88[0], v87)
            && !(unsigned int)CHwCommandBuffer::AddColorFillCommand(
                                *(CDDPDEV ***)(v21 + 12696),
                                (struct COLORFILL_DATA *)&v76[2],
                                v88[0],
                                v87)
            && (*(_DWORD *)(v21 + 2744) & 0x400) == 0
            && (_BYTE)KdDebuggerEnabled )
          {
            DbgPrint("Error submitting ColorFill command");
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 2439;
            v34 = (_QWORD *)WdLogNewEntry5_WdError();
            v34[3] = gCddImageInfo;
            v34[4] = (unsigned int)dword_14003E570;
            v34[5] = 215857758;
            WdLogGlobalForLineNumber = 2439;
            __debugbreak();
          }
          CddBitmap::VidMemDirtyUpdate((CddBitmap *)dhsurf);
          CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)ppoa);
        }
      }
    }
    v35 = v62;
    CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v61, *(struct CDDMUTEX **)(*(_QWORD *)(v62 + 5504) + 2904LL), v27);
    v36 = (_QWORD *)(v35 + 6296);
    v37 = *(_QWORD *)(v35 + 6296);
    if ( *(_QWORD *)(v37 + 8) != v35 + 6296 )
      goto LABEL_37;
    *v23 = v37;
    v23[1] = v36;
    *(_QWORD *)(v37 + 8) = v23;
    *v36 = v23;
    KeReleaseSemaphore(*(PRKSEMAPHORE *)(v35 + 6312), 0, 1, 0);
    if ( (_DWORD)v62 )
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v61);
    if ( v10 )
      goto LABEL_70;
LABEL_43:
    memset(psoa, 0, sizeof(psoa));
    v38 = *(_QWORD *)dhsurf;
    v10 = 1;
    v73 = 0;
    if ( (*(int (__fastcall **)(DHSURF, struct _RECTL *, __int64, SURFOBJ **))(v38 + 96))(dhsurf, p_rclBounds, 1, psoa) < 0 )
    {
      v39 = v73;
    }
    else
    {
      v39 = (CddBitmap *)dhsurf;
      v74 = p_rclBounds;
      v73 = (CddBitmap *)dhsurf;
    }
    if ( !v39 )
    {
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 2451;
      v40 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v40[3] = gCddImageInfo;
      v40[4] = (unsigned int)dword_14003E570;
      v40[5] = 215857758;
      WdLogGlobalForLineNumber = 2451;
      if ( v73 )
      {
        (*(void (__fastcall **)(CddBitmap *, SURFOBJ **))(*(_QWORD *)v73 + 128LL))(v73, psoa);
        CddBitmap::VidMemDirtyUpdate(v73);
      }
      CDDBITMAPLOCK::~CDDBITMAPLOCK((CDDBITMAPLOCK *)v68);
      CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v64);
      return v10;
    }
    v41 = psoa[0];
    LOBYTE(v76[6]) = 0;
    v78 = 0;
    v76[0] = (SURFOBJ *)pcoa;
    v76[1] = (SURFOBJ *)p_rclBounds;
    v76[2] = (SURFOBJ *)p_rclBounds;
    v76[3] = (SURFOBJ *)p_rclBounds;
    pvScan0 = (SURFOBJ *)psoa[0]->pvScan0;
    LODWORD(v80) = psoa[0]->lDelta;
    HIDWORD(v80) = -251592189;
    v76[5] = 0;
    ClipDstRects(
      (struct CLIP_RECTS_DATA *)v76,
      (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))FillColorKeyCallback);
    v10 = EngStrokePath(v41, v32, pcoa, pxoa, v57, v59, v58, mix);
    if ( v10 )
    {
      v76[0] = (SURFOBJ *)pcoa;
      LOBYTE(v76[6]) = 0;
      v78 = 0;
      v42 = psoa[0]->lDelta;
      v76[1] = (SURFOBJ *)((char *)&psoa[4] + 4);
      pvScan0 = psoa[3];
      LODWORD(v81) = psoa[2];
      v43 = *((_DWORD *)dhsurf + 10);
      v84 = v42;
      HIDWORD(v81) = v43;
      v76[2] = (SURFOBJ *)p_rclBounds;
      v76[3] = (SURFOBJ *)p_rclBounds;
      v82 = -251592189;
      v80 = dhsurf;
      v83 = 1;
      v76[5] = 0;
      ClipDstRects(
        (struct CLIP_RECTS_DATA *)v76,
        (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::TransparentBltCallback);
    }
    if ( v73 )
    {
      (*(void (__fastcall **)(CddBitmap *, SURFOBJ **))(*(_QWORD *)v73 + 128LL))(v73, psoa);
      CddBitmap::VidMemDirtyUpdate(v73);
    }
    goto LABEL_70;
  }
  v44 = pcoa;
  memset(v76, 0, sizeof(v76));
  v45 = *(_QWORD *)dhsurf;
  v81 = 0;
  v46 = *(int (__fastcall **)(DHSURF, struct _RECTL *, struct _RECTL *, CLIPOBJ *, int, int, SURFOBJ **, SURFOBJ **, char))(v45 + 56);
  v77 = 0;
  pvScan0 = 0;
  v78 = 0;
  LODWORD(v80) = 0;
  LODWORD(v54) = 0;
  if ( v46(dhsurf, p_rclBounds, p_rclBounds, pcoa, 1, 1, &v54, v76, 1) >= 0 )
  {
    v78 = dhsurf;
    v77 = v44;
    pvScan0 = (SURFOBJ *)p_rclBounds;
    v81 = v76[0]->dhpdev;
    v76[0]->dhpdev = 0;
    v47 = (int)v54;
    if ( (_DWORD)v54 )
    {
      CDDPDEV::Flush((CDDPDEV *)v21);
      v47 = (int)v54;
    }
    WaitForStartGdiAccessToFinish((struct CDDPDEV *)v21, (struct CDDBITMAP_GDIDESC *)v76, v47);
  }
  if ( !v78 )
  {
    WdLogSingleEntry0(4);
    WdLogGlobalForLineNumber = 2497;
    v48 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v48[3] = gCddImageInfo;
    v48[4] = (unsigned int)dword_14003E570;
    v48[5] = 215857758;
    WdLogGlobalForLineNumber = 2497;
    if ( v78 )
    {
      v76[0]->dhpdev = v81;
      v49 = v78;
      if ( !(_DWORD)v80 )
        (*(void (__fastcall **)(DHSURF, SURFOBJ **, SURFOBJ *, CLIPOBJ *, _QWORD))(*(_QWORD *)v78 + 64LL))(
          v78,
          v76,
          pvScan0,
          v77,
          0);
      (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v49 + 128LL))(v49, v76);
    }
    goto LABEL_26;
  }
  v10 = EngStrokePath(v76[0], ppoa[0], pcoa, pxoa, v57, v59, v58, mix);
  v50 = (int)v80;
  if ( !v10 )
    v50 = 1;
  LODWORD(v80) = v50;
  if ( v78 )
  {
    v76[0]->dhpdev = v81;
    v51 = v78;
    if ( !(_DWORD)v80 )
      (*(void (__fastcall **)(DHSURF, SURFOBJ **, SURFOBJ *, CLIPOBJ *, _QWORD))(*(_QWORD *)v78 + 64LL))(
        v78,
        v76,
        pvScan0,
        v77,
        0);
    (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v51 + 128LL))(v51, v76);
  }
LABEL_70:
  CDDBITMAPLOCK::~CDDBITMAPLOCK((CDDBITMAPLOCK *)v68);
LABEL_89:
  if ( !v67 )
  {
    LOBYTE(v17) = 2;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(v64 + 264))(v65, v17, v66);
  }
  return v10;
}

```

## disassembly

```asm
0x140007b00  push    rbp
0x140007b02  push    rbx
0x140007b03  push    rsi
0x140007b04  push    rdi
0x140007b05  push    r12
0x140007b07  push    r13
0x140007b09  push    r14
0x140007b0b  push    r15
0x140007b0d  lea     rbp, [rsp-138h]
0x140007b15  sub     rsp, 238h
0x140007b1c  mov     rax, cs:__security_cookie
0x140007b23  xor     rax, rsp
0x140007b26  mov     [rbp+170h+var_50], rax
0x140007b2d  mov     rdi, [rbp+170h+pbo]
0x140007b34  mov     r12, rcx
0x140007b37  mov     [rsp+270h+var_220], rcx
0x140007b3c  mov     rax, rdx
0x140007b3f  mov     rcx, [rbp+170h+pptlBrushOrg]
0x140007b46  xorps   xmm0, xmm0
0x140007b49  mov     [rsp+270h+var_1F8], rcx
0x140007b4e  xorps   xmm1, xmm1
0x140007b51  mov     rcx, [rbp+170h+plineattrs]
0x140007b58  xor     r14d, r14d
0x140007b5b  mov     [rsp+270h+var_200], rcx
0x140007b60  mov     r15d, r14d
0x140007b63  mov     [rbp+170h+ppo], rdx
0x140007b67  mov     rcx, rax; ppo
0x140007b6a  mov     [rsp+270h+pco], r8
0x140007b6f  lea     rdx, [rbp+170h+prectfx]; prectfx
0x140007b76  mov     rbx, [r12+10h]
0x140007b7b  mov     [rbp+170h+pxo], r9
0x140007b7f  mov     [rsp+270h+var_208], rdi
0x140007b84  movups  xmmword ptr [rbp+170h+prectfx.xLeft], xmm0
0x140007b8b  movups  xmmword ptr [rbp+170h+var_110.left], xmm1
0x140007b8f  call    cs:__imp_PATHOBJ_vGetBounds
0x140007b96  nop     dword ptr [rax+rax+00h]
0x140007b9b  mov     r9d, [rbp+170h+prectfx.xRight]
0x140007ba2  lea     rsi, [rbp+170h+var_110]
0x140007ba6  mov     r10d, [rbp+170h+prectfx.yBottom]
0x140007bad  add     r9d, 0Fh
0x140007bb1  mov     edx, [rbp+170h+prectfx.xLeft]
0x140007bb7  add     r10d, 0Fh
0x140007bbb  mov     r8d, [rbp+170h+prectfx.yTop]
0x140007bc2  mov     rcx, [rsp+270h+pco]
0x140007bc7  sar     r9d, 4
0x140007bcb  sar     r10d, 4
0x140007bcf  sar     edx, 4
0x140007bd2  sar     r8d, 4
0x140007bd6  mov     [rbp+170h+var_110.left], edx
0x140007bd9  mov     [rbp+170h+var_110.top], r8d
0x140007bdd  mov     [rbp+170h+var_110.right], r9d
0x140007be1  mov     [rbp+170h+var_110.bottom], r10d
0x140007be5  test    rcx, rcx
0x140007be8  jz      short loc_140007C2B
0x140007bea  cmp     [rcx+14h], r14b
0x140007bee  jz      short loc_140007BF6
0x140007bf0  lea     rsi, [rcx+4]
0x140007bf4  jmp     short loc_140007C2B
0x140007bf6  mov     eax, [rcx+4]
0x140007bf9  cmp     eax, edx
0x140007bfb  cmovl   edx, eax
0x140007bfe  mov     [rbp+170h+var_110.left], edx
0x140007c01  mov     eax, [rcx+8]
0x140007c04  cmp     eax, r8d
0x140007c07  cmovl   r8d, eax
0x140007c0b  mov     [rbp+170h+var_110.top], r8d
0x140007c0f  mov     eax, [rcx+0Ch]
0x140007c12  cmp     eax, r9d
0x140007c15  cmovg   r9d, eax
0x140007c19  mov     [rbp+170h+var_110.right], r9d
0x140007c1d  mov     eax, [rcx+10h]
0x140007c20  cmp     eax, r10d
0x140007c23  cmovg   r10d, eax
0x140007c27  mov     [rbp+170h+var_110.bottom], r10d
0x140007c2b  xorps   xmm0, xmm0
0x140007c2e  mov     [rbp+170h+var_1B0], 1
0x140007c35  movups  [rbp+170h+var_198], xmm0
0x140007c39  mov     [rbp+170h+var_1B8], r14
0x140007c3d  movups  [rbp+170h+var_188], xmm0
0x140007c41  movups  [rbp+170h+var_178], xmm0
0x140007c45  mov     rax, [rbx+50h]
0x140007c49  call    _guard_dispatch_icall
0x140007c4e  mov     r13d, [rbp+170h+mix]
0x140007c55  test    eax, eax
0x140007c57  jz      short loc_140007CB0
0x140007c59  xorps   xmm0, xmm0
0x140007c5c  mov     byte ptr [rsp+270h+var_250], r14b; bool
0x140007c61  movups  [rbp+170h+var_188], xmm0
0x140007c65  lea     r9, [rbp+170h+var_198]; struct _DXGKETW_PARAMS *
0x140007c69  mov     r8d, 0BCFh; unsigned int
0x140007c6f  movups  [rbp+170h+var_198], xmm0
0x140007c73  mov     rdx, rbx; struct CDDPDEV *
0x140007c76  movups  [rbp+170h+var_178], xmm0
0x140007c7a  movzx   eax, word ptr [r12+4Ch]
0x140007c80  mov     dword ptr [rbp+170h+var_198+4], eax
0x140007c83  mov     ecx, [rsi+8]
0x140007c86  sub     ecx, [rsi]
0x140007c88  mov     dword ptr [rbp+170h+var_188], ecx
0x140007c8b  mov     ecx, [rsi+0Ch]
0x140007c8e  sub     ecx, [rsi+4]
0x140007c91  cmp     dword ptr [rdi], 0FFFFFFFFh
0x140007c94  movzx   eax, r13w
0x140007c98  mov     dword ptr [rbp+170h+var_178], eax
0x140007c9b  mov     eax, r14d
0x140007c9e  setnz   al
0x140007ca1  mov     dword ptr [rbp+170h+var_188+4], ecx
0x140007ca4  lea     rcx, [rbp+170h+var_1C8]; this
0x140007ca8  mov     dword ptr [rbp+170h+var_188+0Ch], eax
0x140007cab  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x140007cb0  mov     ecx, 1
0x140007cb5  cmp     [r12+4Ch], cx
0x140007cbb  jz      loc_14000853E
0x140007cc1  mov     rdi, [r12]
0x140007cc5  lea     rcx, [rbp+170h+var_1A8]; this
0x140007cc9  mov     rdx, rdi; struct CddBitmap *
0x140007ccc  mov     r14, [rdi+8]
0x140007cd0  call    ??0CDDBITMAPLOCK@@QEAA@PEAVCddBitmap@@@Z; CDDBITMAPLOCK::CDDBITMAPLOCK(CddBitmap *)
0x140007cd5  mov     eax, r13d
0x140007cd8  lea     ecx, [r13-1]
0x140007cdc  shr     eax, 8
0x140007cdf  lea     rdx, ?ROP2_NEED_DEST@@3PAHA; int near * ROP2_NEED_DEST
0x140007ce6  mov     r12d, 1
0x140007cec  and     ecx, 0Fh
0x140007cef  sub     eax, r12d
0x140007cf2  and     eax, 0Fh
0x140007cf5  mov     eax, [rdx+rax*4]
0x140007cf8  or      eax, [rdx+rcx*4]
0x140007cfb  jnz     loc_1400082D9
0x140007d01  mov     eax, [rdi+80h]
0x140007d07  test    r12b, al
0x140007d0a  jz      loc_1400082D9
0x140007d10  mov     rax, [rsp+270h+var_208]
0x140007d15  mov     ecx, 1
0x140007d1a  mov     [rsp+270h+var_218], ecx
0x140007d1e  mov     r12d, [rax]
0x140007d21  mov     dword ptr [rsp+270h+var_220], r12d
0x140007d26  cmp     r12d, 0FFFFFFFFh
0x140007d2a  jz      short loc_140007D35
0x140007d2c  cmp     r13d, 0D0Dh
0x140007d33  jz      short loc_140007D54
0x140007d35  lea     r8, [rsp+270h+var_218]; enum _DXGK_GDIROP_COLORFILL *
0x140007d3a  mov     ecx, r13d; unsigned int
0x140007d3d  lea     rdx, [rsp+270h+var_220]; unsigned int *
0x140007d42  call    ?ComputeColorFillParams@@YAHKAEAIAEAW4_DXGK_GDIROP_COLORFILL@@@Z; ComputeColorFillParams(ulong,uint &,_DXGK_GDIROP_COLORFILL &)
0x140007d47  test    eax, eax
0x140007d49  jz      loc_14000809B
0x140007d4f  mov     r12d, dword ptr [rsp+270h+var_220]
0x140007d54  mov     r8, rdi; struct CddBitmap *
0x140007d57  lea     rcx, [rbp+170h+var_1E8]; this
0x140007d5b  mov     rdx, r14; struct CDDPDEV *
0x140007d5e  call    ??0TempSurfObjHelper@@QEAA@PEAUCDDPDEV@@PEAVCddBitmap@@@Z; TempSurfObjHelper::TempSurfObjHelper(CDDPDEV *,CddBitmap *)
0x140007d63  mov     rbx, [rbp+170h+var_1E8]
0x140007d67  lea     rax, ?EngWritePixelCallback@@YAXPEAU_W32KCDD_ENG_CALLBACKS@@IQEAX@Z; EngWritePixelCallback(_W32KCDD_ENG_CALLBACKS *,uint,void * const)
0x140007d6e  xor     edx, edx
0x140007d70  mov     rcx, [rbx+10h]
0x140007d74  mov     [rbp+170h+var_100], rax
0x140007d78  lea     rax, ?EngFillRectCallback@@YAXPEAU_W32KCDD_ENG_CALLBACKS@@IPEBUtagRECT@@@Z; EngFillRectCallback(_W32KCDD_ENG_CALLBACKS *,uint,tagRECT const *)
0x140007d7f  mov     [rbp+170h+var_F8], rax
0x140007d83  mov     eax, [rdi+28h]
0x140007d86  mov     [rbp+170h+var_98], eax
0x140007d8c  mov     eax, [rsp+270h+var_218]
0x140007d90  mov     [rbp+170h+var_88], rdx
0x140007d97  mov     [rbp+170h+var_80], edx
0x140007d9d  mov     [rbp+170h+var_90], eax
0x140007da3  mov     byte ptr [rbp+170h+var_C0], dl
0x140007da9  mov     [rbp+170h+var_A8], rdx
0x140007db0  mov     qword ptr [rbp+170h+var_70], rdx
0x140007db7  mov     [rbp+170h+var_78], rdx
0x140007dbe  mov     [rbp+170h+var_F0], rdx
0x140007dc5  mov     [rbp+170h+var_E8], rsi
0x140007dcc  mov     [rbp+170h+var_E0], rsi
0x140007dd3  mov     [rbp+170h+var_D8], rsi
0x140007dda  mov     [rbp+170h+var_A0], rdi
0x140007de1  mov     [rbp+170h+var_94], r12d
0x140007de8  mov     rax, [rcx+30h]
0x140007dec  mov     [rbp+170h+var_88], rax
0x140007df3  mov     eax, [rcx+40h]
0x140007df6  mov     [rsp+270h+var_220], rcx
0x140007dfb  mov     rcx, rdi; this
0x140007dfe  mov     [rbp+170h+var_80], eax
0x140007e04  call    ?GetRectBuffer@CddBitmapHw@@QEAAPEAUtagRECT@@XZ; CddBitmapHw::GetRectBuffer(void)
0x140007e09  mov     rcx, rax
0x140007e0c  mov     [rbp+170h+var_78], rax
0x140007e13  mov     eax, [rdi+4A8h]
0x140007e19  mov     [rbp+170h+var_70+4], eax
0x140007e1f  cmp     [rbp+170h+var_98], r15d
0x140007e26  jnz     loc_140007EB7
0x140007e2c  mov     rdi, [rbp+170h+var_1E0]
0x140007e30  lea     rcx, [rbp+170h+var_1E8]; this
0x140007e34  mov     rdx, [rdi+1580h]
0x140007e3b  mov     rdx, [rdx+0B58h]; struct CDDMUTEX *
0x140007e42  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x140007e47  lea     rax, [rdi+1898h]
0x140007e4e  mov     rcx, [rax]
0x140007e51  cmp     [rcx+8], rax
0x140007e55  jnz     loc_140008047
0x140007e5b  mov     [rbx], rcx
0x140007e5e  xor     r9d, r9d; Wait
0x140007e61  mov     [rbx+8], rax
0x140007e65  xor     edx, edx; Increment
0x140007e67  mov     [rcx+8], rbx
0x140007e6b  mov     [rax], rbx
0x140007e6e  mov     rcx, [rdi+18A8h]; Semaphore
0x140007e75  lea     ebx, [r9+1]
0x140007e79  mov     r8d, ebx; Adjustment
0x140007e7c  call    cs:__imp_KeReleaseSemaphore
0x140007e83  nop     dword ptr [rax+rax+00h]
0x140007e88  cmp     dword ptr [rbp+170h+var_1E0], r15d
0x140007e8c  jz      short loc_140007E9E
0x140007e8e  mov     rcx, [rbp+170h+var_1E8]
0x140007e92  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140007e99  nop     dword ptr [rax+rax+00h]
0x140007e9e  lea     rcx, [rbp+170h+var_1A8]; this
0x140007ea2  call    ??1CDDBITMAPLOCK@@QEAA@XZ; CDDBITMAPLOCK::~CDDBITMAPLOCK(void)
0x140007ea7  lea     rcx, [rbp+170h+var_1C8]; this
0x140007eab  call    ??1CDDETWPROFILER@@QEAA@XZ; CDDETWPROFILER::~CDDETWPROFILER(void)
0x140007eb0  mov     eax, ebx
0x140007eb2  jmp     loc_1400086EA
0x140007eb7  mov     r12, [rbp+170h+ppo]
0x140007ebb  test    rcx, rcx
0x140007ebe  jz      loc_14000801C
0x140007ec4  mov     rax, [r14+278h]
0x140007ecb  lea     rcx, [rbp+170h+var_100]
0x140007ecf  mov     r9, [rbp+170h+pxo]
0x140007ed3  mov     rdx, r12
0x140007ed6  mov     r8, [rsp+270h+pco]
0x140007edb  mov     [rsp+270h+var_230], rcx
0x140007ee0  mov     rcx, [rsp+270h+var_200]
0x140007ee5  mov     [rsp+270h+var_238], r13d
0x140007eea  mov     [rsp+270h+var_240], rcx
0x140007eef  mov     rcx, [rsp+270h+var_1F8]
0x140007ef4  mov     [rsp+270h+var_248], rcx
0x140007ef9  mov     rcx, [rsp+270h+var_208]
0x140007efe  mov     [rsp+270h+var_250], rcx
0x140007f03  mov     rcx, [rsp+270h+var_220]
0x140007f08  call    _guard_dispatch_icall
0x140007f0d  mov     r15d, eax
0x140007f10  test    eax, eax
0x140007f12  jz      loc_14000801C
0x140007f18  cmp     [rbp+170h+var_70], 0
0x140007f1f  jz      loc_14000801C
0x140007f25  xor     r9d, r9d; unsigned __int8
0x140007f28  lea     rcx, [rbp+170h+ppo]; this
0x140007f2c  xor     r8d, r8d; unsigned __int8
0x140007f2f  mov     rdx, r14; struct CDDPDEV *
0x140007f32  call    ??0CCommandBufferMutex@@QEAA@PEAUCDDPDEV@@EE@Z; CCommandBufferMutex::CCommandBufferMutex(CDDPDEV *,uchar,uchar)
0x140007f37  mov     r9, [rbp+170h+var_78]; struct tagRECT *
0x140007f3e  lea     rax, [rbp+170h+ppo]
0x140007f42  mov     r8d, [rbp+170h+var_70]; unsigned int
0x140007f49  lea     rdx, [rbp+170h+var_F0]; struct COLORFILL_DATA *
0x140007f50  mov     rcx, [r14+3198h]; this
0x140007f57  mov     [rbp+170h+var_D0], rax
0x140007f5e  call    ?AddColorFillCommand@CHwCommandBuffer@@QEAAHPEAUCOLORFILL_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddColorFillCommand(COLORFILL_DATA *,uint,tagRECT const *)
0x140007f63  test    eax, eax
0x140007f65  jnz     loc_14000800B
0x140007f6b  mov     r9, [rbp+170h+var_78]; struct tagRECT *
0x140007f72  lea     rdx, [rbp+170h+var_F0]; struct COLORFILL_DATA *
0x140007f79  mov     r8d, [rbp+170h+var_70]; unsigned int
0x140007f80  mov     rcx, [r14+3198h]; this
0x140007f87  call    ?AddColorFillCommand@CHwCommandBuffer@@QEAAHPEAUCOLORFILL_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddColorFillCommand(COLORFILL_DATA *,uint,tagRECT const *)
0x140007f8c  test    eax, eax
0x140007f8e  jnz     short loc_14000800B
0x140007f90  test    dword ptr [r14+0AB8h], 400h
0x140007f9b  jnz     short loc_14000800B
0x140007f9d  mov     rax, cs:KdDebuggerEnabled
0x140007fa4  cmp     byte ptr [rax], 0
0x140007fa7  jz      short loc_14000800B
0x140007fa9  lea     rcx, aErrorSubmittin_2; "Error submitting ColorFill command"
0x140007fb0  call    cs:__imp_DbgPrint
0x140007fb7  nop     dword ptr [rax+rax+00h]
0x140007fbc  mov     ecx, 2
0x140007fc1  call    cs:__imp_WdLogSingleEntry0
0x140007fc8  nop     dword ptr [rax+rax+00h]
0x140007fcd  mov     r14d, 987h
0x140007fd3  mov     cs:WdLogGlobalForLineNumber, r14d
0x140007fda  call    cs:__imp_WdLogNewEntry5_WdError
0x140007fe1  nop     dword ptr [rax+rax+00h]
0x140007fe6  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140007fed  mov     [rax+18h], rcx
0x140007ff1  mov     ecx, cs:dword_14003E570
0x140007ff7  mov     [rax+20h], rcx
0x140007ffb  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140008003  mov     cs:WdLogGlobalForLineNumber, r14d
0x14000800a  int     3; Trap to Debugger
0x14000800b  mov     rcx, rdi; this
0x14000800e  call    ?VidMemDirtyUpdate@CddBitmap@@QEAAXXZ; CddBitmap::VidMemDirtyUpdate(void)
0x140008013  lea     rcx, [rbp+170h+ppo]; this
0x140008017  call    ??1CCommandBufferMutex@@QEAA@XZ; CCommandBufferMutex::~CCommandBufferMutex(void)
0x14000801c  mov     r14, [rbp+170h+var_1E0]
0x140008020  lea     rcx, [rbp+170h+var_1E8]; this
0x140008024  mov     rdx, [r14+1580h]
0x14000802b  mov     rdx, [rdx+0B58h]; struct CDDMUTEX *
0x140008032  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x140008037  lea     rax, [r14+1898h]
0x14000803e  mov     rcx, [rax]
0x140008041  cmp     [rcx+8], rax
0x140008045  jz      short loc_14000804E
0x140008047  mov     ecx, 3
0x14000804c  int     29h; Win8: RtlFailFast(ecx)
0x14000804e  mov     [rbx], rcx
  ... truncated ...
```
