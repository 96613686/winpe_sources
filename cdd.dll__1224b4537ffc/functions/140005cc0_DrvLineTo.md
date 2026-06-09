# DrvLineTo

- ea: `0x140005cc0`
- end: `0x140006a1e`
- name: `DrvLineTo`
- size: `3422`
- prototype: `FN_DrvLineTo`
- caller_count: `0`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001008`
- `0x140002470`
- `0x140004600`
- `0x140005cc0`
- `0x140006a30`
- `0x140008714`
- `0x14000874c`
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

- `ntoskrnl!KeReleaseSemaphore` at `0x1400060ff`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400062d8`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400060ff`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400062d8`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140006119`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400062ee`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140006119`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400062ee`
- `ntoskrnl!DbgPrint` at `0x140006217`
- `ntoskrnl!DbgPrint` at `0x140006217`
- `ntoskrnl!KdDebuggerEnabled` at `0x140006204`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000623e`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000623e`
- `watchdog!WdLogSingleEntry0` at `0x140006228`
- `watchdog!WdLogSingleEntry0` at `0x14000636f`
- `watchdog!WdLogSingleEntry0` at `0x140006714`
- `watchdog!WdLogSingleEntry0` at `0x140006228`
- `watchdog!WdLogSingleEntry0` at `0x14000636f`
- `watchdog!WdLogSingleEntry0` at `0x140006714`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140006386`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000672b`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140006386`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000672b`
- `WIN32K!EngLineTo` at `0x140006470`
- `WIN32K!EngLineTo` at `0x140006803`
- `WIN32K!EngLineTo` at `0x1400069b2`
- `WIN32K!EngLineTo` at `0x140006470`
- `WIN32K!EngLineTo` at `0x140006803`
- `WIN32K!EngLineTo` at `0x1400069b2`
- `WIN32K!EngReleaseSemaphore` at `0x1400066c6`
- `WIN32K!EngReleaseSemaphore` at `0x1400066c6`

## string_xrefs

- `0x140006210`: `Error submitting ColorFill command`

## pseudocode

```c
BOOL __stdcall DrvLineTo(
        SURFOBJ *pso,
        CLIPOBJ *pco,
        BRUSHOBJ *pbo,
        LONG x1,
        LONG y1,
        LONG x2,
        LONG y2,
        RECTL *prclBounds,
        MIX mix)
{
  BOOL v9; // ebx
  DHPDEV dhpdev; // rsi
  int v11; // r12d
  unsigned int (*v12)(void); // rax
  int v13; // r8d
  int iType; // eax
  int v15; // eax
  DHSURF dhsurf; // rsi
  SURFOBJ *v17; // r9
  int v18; // eax
  _DXGK_GDIROP_COLORFILL v19; // r8d
  ULONG iSolidColor; // ecx
  MIX v21; // r10d
  BRUSHOBJ *v22; // r11
  unsigned int v23; // eax
  _QWORD *v25; // r12
  __int64 v26; // rcx
  int v27; // eax
  struct tagRECT *RectBuffer; // rcx
  int v29; // r8d
  __int64 v30; // rdi
  _QWORD *v31; // rax
  __int64 v32; // rcx
  _QWORD *v33; // rax
  __int64 v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rax
  CddBitmap *v38; // rax
  _QWORD *v39; // rax
  unsigned int v40; // eax
  SURFOBJ *v41; // r15
  int v42; // r14d
  LONG left; // eax
  LONG right; // ecx
  __int64 v45; // rdx
  LONG top; // eax
  LONG bottom; // ecx
  int v48; // r8d
  HSEMAPHORE v49; // rcx
  _QWORD *v50; // rax
  DHSURF v51; // rdi
  int v52; // r14d
  int v53; // eax
  DHSURF v54; // rbx
  int v55; // [rsp+60h] [rbp-A0h] BYREF
  int v56[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v57; // [rsp+70h] [rbp-90h] BYREF
  CLIPOBJ *pcoa; // [rsp+78h] [rbp-88h] BYREF
  SURFOBJ *psoa; // [rsp+80h] [rbp-80h] BYREF
  int v60; // [rsp+88h] [rbp-78h]
  _DXGK_GDIROP_COLORFILL v61[2]; // [rsp+90h] [rbp-70h] BYREF
  enum _DXGK_GDIROP_COLORFILL v62[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v63; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-50h]
  CLIPOBJ *v65; // [rsp+C0h] [rbp-40h] BYREF
  void (__fastcall *p_pboa)(struct _W32KCDD_ENG_CALLBACKS *, unsigned int, const struct tagRECT *); // [rsp+C8h] [rbp-38h]
  void *v67; // [rsp+D0h] [rbp-30h] BYREF
  void *v68; // [rsp+D8h] [rbp-28h]
  RECTL *v69; // [rsp+E0h] [rbp-20h]
  RECTL *v70; // [rsp+E8h] [rbp-18h]
  enum _DXGK_GDIROP_COLORFILL *v71; // [rsp+F0h] [rbp-10h]
  char v72; // [rsp+100h] [rbp+0h]
  __int64 v73; // [rsp+108h] [rbp+8h]
  DHSURF v74; // [rsp+110h] [rbp+10h]
  unsigned __int64 v75; // [rsp+118h] [rbp+18h]
  DHSURF v76; // [rsp+120h] [rbp+20h]
  int v77; // [rsp+128h] [rbp+28h]
  unsigned int v78; // [rsp+12Ch] [rbp+2Ch]
  enum _DXGK_GDIROP_COLORFILL lDelta; // [rsp+130h] [rbp+30h]
  __int64 v80; // [rsp+138h] [rbp+38h]
  int v81; // [rsp+140h] [rbp+40h]
  struct tagRECT *v82; // [rsp+148h] [rbp+48h]
  unsigned int v83[4]; // [rsp+150h] [rbp+50h]
  int v84; // [rsp+160h] [rbp+60h] BYREF
  __int64 v85; // [rsp+168h] [rbp+68h]
  __int64 v86; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v87; // [rsp+178h] [rbp+78h]
  __int64 v88; // [rsp+180h] [rbp+80h]
  int v89; // [rsp+188h] [rbp+88h]
  __int128 v90; // [rsp+190h] [rbp+90h] BYREF
  __int128 v91; // [rsp+1A0h] [rbp+A0h]
  __int128 v92; // [rsp+1B0h] [rbp+B0h]
  _QWORD v93[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  CddBitmap *v94; // [rsp+200h] [rbp+100h]
  RECTL *v95; // [rsp+208h] [rbp+108h]
  BRUSHOBJ *pboa; // [rsp+210h] [rbp+110h] BYREF
  LONG v97; // [rsp+218h] [rbp+118h]
  LONG v98; // [rsp+21Ch] [rbp+11Ch]
  __m128i v99; // [rsp+220h] [rbp+120h] BYREF
  SURFOBJ *v100[8]; // [rsp+230h] [rbp+130h] BYREF
  SURFOBJ *v101; // [rsp+270h] [rbp+170h]
  DHSURF v102; // [rsp+278h] [rbp+178h]
  __int64 v103; // [rsp+280h] [rbp+180h]
  int v104; // [rsp+288h] [rbp+188h]
  DHPDEV v105; // [rsp+290h] [rbp+190h]

  pcoa = pco;
  v9 = 1;
  dhpdev = pso->dhpdev;
  v11 = x1;
  v90 = 0;
  v56[0] = x1;
  v91 = 0;
  pboa = pbo;
  v92 = 0;
  v12 = (unsigned int (*)(void))*((_QWORD *)dhpdev + 10);
  psoa = pso;
  *(_QWORD *)v62 = pso;
  v55 = 0;
  v89 = 1;
  v88 = 0;
  if ( v12() )
  {
    LODWORD(v90) = 0;
    *((_QWORD *)&v90 + 1) = 0;
    DWORD2(v91) = 0;
    *((_QWORD *)&v92 + 1) = 0;
    iType = psoa->iType;
    LODWORD(v91) = prclBounds->right - prclBounds->left;
    DWORD1(v91) = prclBounds->bottom - prclBounds->top;
    DWORD1(v90) = iType;
    LODWORD(v92) = (unsigned __int16)mix;
    if ( v11 == x2 || (v15 = 0, y1 == y2) )
      v15 = 1;
    DWORD1(v92) = v15;
    HIDWORD(v91) = pboa->iSolidColor != -1;
    CDDETWPROFILER::Init((CDDETWPROFILER *)&v86, (struct CDDPDEV *)dhpdev, 0xBD1u, (struct _DXGKETW_PARAMS *)&v90, 0);
  }
  if ( psoa->iType == 1 )
  {
    CDDDEVLOCK::CDDDEVLOCK((CDDDEVLOCK *)&v63, *((HSEMAPHORE *)dhpdev + 365), v13);
    if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
    {
      v56[0] = 1;
    }
    else
    {
      CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 56LL) = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
      v56[0] = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) != 0;
    }
    CDDDEVLOCK::vUnlock((CDDDEVLOCK *)&v63);
    if ( v56[0] )
    {
      ReadFromFrameBuffer(
        (struct CDDPDEV *)dhpdev,
        prclBounds->left,
        prclBounds->top,
        prclBounds->right,
        prclBounds->bottom);
      v56[0] = 0;
      CDDSURFLOCK::vInit((CDDSURFLOCK *)v100, (struct CDDPDEV *)dhpdev, (struct _SURFOBJ **)v62, prclBounds, v56, pcoa);
      if ( bIgnoreDeviceSurfaceUpdates(psoa, &pcoa) )
      {
        CDDSURFLOCK::vDone((CDDSURFLOCK *)v100);
        goto LABEL_30;
      }
      v52 = EngLineTo(*(SURFOBJ **)v62, pcoa, pboa, v11, y1, x2, y2, prclBounds, mix);
      if ( v52 && v56[0] == 1 )
        vGDIDirtyUpdate((struct CDDPDEV *)dhpdev, (struct tagRECT *)prclBounds, pcoa);
      CDDSURFLOCK::vDone((CDDSURFLOCK *)v100);
    }
    else
    {
      v52 = v55;
    }
  }
  else
  {
    dhsurf = psoa->dhsurf;
    CDDBITMAPLOCK::CDDBITMAPLOCK((CDDBITMAPLOCK *)&v84, (struct CddBitmap *)psoa->dhsurf);
    v17 = (SURFOBJ *)*((_QWORD *)dhsurf + 1);
    v18 = *((_DWORD *)dhsurf + 32);
    psoa = v17;
    if ( (v18 & 1) != 0 )
    {
      if ( v11 == x2 || y1 == y2 )
      {
        v19 = DXGK_GDIROPCF_PATCOPY;
        v61[0] = DXGK_GDIROPCF_PATCOPY;
        iSolidColor = pboa->iSolidColor;
        v57 = iSolidColor;
        if ( iSolidColor != -1 && mix == 3341 )
        {
LABEL_14:
          if ( v11 > x2 )
          {
            v97 = v11 + 1;
            if ( y1 == y2 )
            {
              LODWORD(pboa) = x2 + 1;
              goto LABEL_20;
            }
            LODWORD(pboa) = x2;
          }
          else
          {
            LODWORD(pboa) = v11;
            if ( y1 == y2 )
            {
              v97 = x2;
              goto LABEL_23;
            }
            v97 = x2 + 1;
          }
          if ( y1 > y2 )
          {
            v98 = y1 + 1;
            if ( v11 == x2 )
              HIDWORD(pboa) = y2 + 1;
            else
              HIDWORD(pboa) = y2;
            goto LABEL_28;
          }
LABEL_23:
          if ( v11 == x2 )
          {
            HIDWORD(pboa) = y1;
            v98 = y2;
            goto LABEL_28;
          }
LABEL_20:
          HIDWORD(pboa) = y1;
          v98 = y2 + 1;
LABEL_28:
          LOBYTE(v71) = 0;
          p_pboa = (void (__fastcall *)(struct _W32KCDD_ENG_CALLBACKS *, unsigned int, const struct tagRECT *))&pboa;
          v73 = 0;
          v67 = &pboa;
          v68 = &pboa;
          v23 = *((_DWORD *)dhsurf + 10);
          v70 = 0;
          v75 = __PAIR64__(iSolidColor, v23);
          v65 = pcoa;
          v74 = dhsurf;
          LODWORD(v76) = v19;
          ClipDstRects(
            (struct CLIP_RECTS_DATA *)&v65,
            (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::ColorFillCallback);
          CddBitmap::VidMemDirtyUpdate((CddBitmap *)dhsurf);
          DWORD2(v91) = 1;
LABEL_29:
          CDDBITMAPLOCK::~CDDBITMAPLOCK((CDDBITMAPLOCK *)&v84);
LABEL_30:
          CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v86);
          return v9;
        }
        if ( (unsigned int)ComputeColorFillParams(mix, &v57, v61) )
        {
          iSolidColor = v57;
          v19 = v61[0];
          goto LABEL_14;
        }
      }
      else
      {
        v21 = mix;
        v22 = pboa;
      }
      if ( !(*((_DWORD *)&ROP2_NEED_DEST + (((_BYTE)v21 - 1) & 0xF))
           | *((_DWORD *)&ROP2_NEED_DEST + ((BYTE1(v21) - 1) & 0xF))) )
      {
        v57 = v22->iSolidColor;
        v61[0] = v57;
        v62[0] = DXGK_GDIROPCF_PATCOPY;
        if ( v57 == -1 || v21 != 3341 )
        {
          if ( !(unsigned int)ComputeColorFillParams(v21, (unsigned int *)v61, v62) )
            goto LABEL_57;
          v57 = v61[0];
        }
        TempSurfObjHelper::TempSurfObjHelper(
          (TempSurfObjHelper *)&v63,
          (struct CDDPDEV *)v17,
          (struct CddBitmap *)dhsurf);
        v25 = v63;
        v26 = v63[2];
        v65 = (CLIPOBJ *)EngWritePixelCallback;
        p_pboa = EngFillRectCallback;
        v77 = *((_DWORD *)dhsurf + 10);
        v78 = v57;
        v80 = 0;
        v81 = 0;
        lDelta = v62[0];
        v72 = 0;
        v75 = 0;
        *(_QWORD *)v83 = 0;
        v82 = 0;
        v67 = 0;
        v68 = prclBounds;
        v69 = prclBounds;
        v70 = prclBounds;
        v76 = dhsurf;
        v80 = *(_QWORD *)(v26 + 48);
        v27 = *(_DWORD *)(v26 + 64);
        *(_QWORD *)v61 = v26;
        v81 = v27;
        RectBuffer = CddBitmapHw::GetRectBuffer((CddBitmapHw *)dhsurf);
        v82 = RectBuffer;
        v83[1] = (unsigned int)dhsurf[298];
        if ( !v77 )
        {
          v30 = v64;
          CGuardMutexEx::CGuardMutexEx(
            (CGuardMutexEx *)&v63,
            *(struct CDDMUTEX **)(*(_QWORD *)(v64 + 5504) + 2904LL),
            v29);
          v31 = (_QWORD *)(v30 + 6296);
          v32 = *(_QWORD *)(v30 + 6296);
          if ( *(_QWORD *)(v32 + 8) == v30 + 6296 )
          {
            *v25 = v32;
            v25[1] = v31;
            *(_QWORD *)(v32 + 8) = v25;
            *v31 = v25;
            KeReleaseSemaphore(*(PRKSEMAPHORE *)(v30 + 6312), 0, 1, 0);
            if ( (_DWORD)v64 )
              ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v63);
            goto LABEL_29;
          }
LABEL_52:
          __fastfail(3u);
        }
        if ( RectBuffer )
        {
          v55 = (*(__int64 (__fastcall **)(_QWORD, CLIPOBJ *, BRUSHOBJ *, _QWORD, LONG, LONG, LONG, RECTL *, MIX, CLIPOBJ **))&psoa[7].lDelta)(
                  *(_QWORD *)v61,
                  pcoa,
                  pboa,
                  (unsigned int)v56[0],
                  y1,
                  x2,
                  y2,
                  prclBounds,
                  mix,
                  &v65);
          if ( v55 )
          {
            if ( v83[0] )
            {
              CCommandBufferMutex::CCommandBufferMutex((CCommandBufferMutex *)v62, (struct _KTHREAD **)psoa, 0, 0);
              v71 = v62;
              if ( !(unsigned int)CHwCommandBuffer::AddColorFillCommand(
                                    (CDDPDEV **)psoa[158].pvScan0,
                                    (struct COLORFILL_DATA *)&v67,
                                    v83[0],
                                    v82)
                && !(unsigned int)CHwCommandBuffer::AddColorFillCommand(
                                    (CDDPDEV **)psoa[158].pvScan0,
                                    (struct COLORFILL_DATA *)&v67,
                                    v83[0],
                                    v82)
                && ((__int64)psoa[34].hdev & 0x400) == 0
                && (_BYTE)KdDebuggerEnabled )
              {
                DbgPrint("Error submitting ColorFill command");
                WdLogSingleEntry0(2);
                WdLogGlobalForLineNumber = 6091;
                v33 = (_QWORD *)WdLogNewEntry5_WdError();
                v33[3] = gCddImageInfo;
                v33[4] = (unsigned int)dword_14003E570;
                v33[5] = 215857758;
                WdLogGlobalForLineNumber = 6091;
                __debugbreak();
              }
              CddBitmap::VidMemDirtyUpdate((CddBitmap *)dhsurf);
              CCommandBufferMutex::~CCommandBufferMutex((CCommandBufferMutex *)v62);
            }
          }
        }
        CGuardMutexEx::CGuardMutexEx(
          (CGuardMutexEx *)&psoa,
          *(struct CDDMUTEX **)(*(_QWORD *)(v64 + 5504) + 2904LL),
          v29);
        v34 = v64;
        v35 = (_QWORD *)(v64 + 6296);
        v36 = *(_QWORD *)(v64 + 6296);
        if ( *(_QWORD *)(v36 + 8) != v64 + 6296 )
          goto LABEL_52;
        *v25 = v36;
        v25[1] = v35;
        *(_QWORD *)(v36 + 8) = v25;
        *v35 = v25;
        KeReleaseSemaphore(*(PRKSEMAPHORE *)(v34 + 6312), 0, 1, 0);
        if ( v60 )
          ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(psoa);
        if ( v55 )
        {
          v42 = v55;
LABEL_68:
          v9 = v42;
          goto LABEL_29;
        }
        v11 = v56[0];
LABEL_57:
        memset(v93, 0, sizeof(v93));
        v37 = *(_QWORD *)dhsurf;
        v94 = 0;
        if ( (*(int (__fastcall **)(DHSURF, RECTL *, __int64, _QWORD *))(v37 + 96))(dhsurf, prclBounds, 1, v93) < 0 )
        {
          v38 = v94;
        }
        else
        {
          v38 = (CddBitmap *)dhsurf;
          v95 = prclBounds;
          v94 = (CddBitmap *)dhsurf;
        }
        if ( !v38 )
        {
          WdLogSingleEntry0(4);
          WdLogGlobalForLineNumber = 6106;
          v39 = (_QWORD *)WdLogNewEntry5_WdEvent();
          v39[3] = gCddImageInfo;
          v39[4] = (unsigned int)dword_14003E570;
          v39[5] = 215857758;
          WdLogGlobalForLineNumber = 6106;
          if ( v94 )
          {
            (*(void (__fastcall **)(CddBitmap *, _QWORD *))(*(_QWORD *)v94 + 128LL))(v94, v93);
            CddBitmap::VidMemDirtyUpdate(v94);
          }
          goto LABEL_29;
        }
        v65 = pcoa;
        psoa = (SURFOBJ *)v93[0];
        v74 = *(DHSURF *)(v93[0] + 48LL);
        v40 = *(_DWORD *)(v93[0] + 64LL);
        LOBYTE(v71) = 0;
        v73 = 0;
        v70 = 0;
        p_pboa = (void (__fastcall *)(struct _W32KCDD_ENG_CALLBACKS *, unsigned int, const struct tagRECT *))prclBounds;
        v67 = prclBounds;
        v68 = prclBounds;
        v75 = v40 | 0xF101020300000000uLL;
        ClipDstRects(
          (struct CLIP_RECTS_DATA *)&v65,
          (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))FillColorKeyCallback);
        v41 = psoa;
        v42 = EngLineTo(psoa, pcoa, pboa, v11, y1, x2, y2, prclBounds, mix);
        if ( v42 )
        {
          v65 = pcoa;
          lDelta = v41->lDelta;
          p_pboa = (void (__fastcall *)(struct _W32KCDD_ENG_CALLBACKS *, unsigned int, const struct tagRECT *))((char *)&v93[4] + 4);
          v74 = (DHSURF)v93[3];
          LODWORD(v76) = v93[2];
          HIDWORD(v76) = dhsurf[10];
          LOBYTE(v71) = 0;
          v73 = 0;
          v67 = prclBounds;
          v68 = prclBounds;
          v77 = -251592189;
          v75 = (unsigned __int64)dhsurf;
          v78 = 1;
          v70 = 0;
          ClipDstRects(
            (struct CLIP_RECTS_DATA *)&v65,
            (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::TransparentBltCallback);
        }
        if ( v94 )
        {
          (*(void (__fastcall **)(CddBitmap *, _QWORD *))(*(_QWORD *)v94 + 128LL))(v94, v93);
          CddBitmap::VidMemDirtyUpdate(v94);
        }
        goto LABEL_68;
      }
    }
    *(_QWORD *)v56 = prclBounds;
    *(_QWORD *)v62 = pcoa;
    v99 = 0;
    if ( pcoa && pcoa->iDComplexity )
    {
      v99 = *(__m128i *)prclBounds;
      left = pcoa->rclBounds.left;
      right = v99.m128i_i32[2];
      v45 = (unsigned int)_mm_cvtsi128_si32(v99);
      if ( (int)v45 <= left )
        v45 = (unsigned int)left;
      v99.m128i_i32[0] = v45;
      if ( v99.m128i_i32[2] >= pcoa->rclBounds.right )
        right = pcoa->rclBounds.right;
      v99.m128i_i32[2] = right;
      if ( (int)v45 >= right )
        goto LABEL_117;
      top = pcoa->rclBounds.top;
      v45 = v99.m128i_u32[1];
      bottom = v99.m128i_i32[3];
      if ( v99.m128i_i32[1] <= top )
        v45 = (unsigned int)top;
      v99.m128i_i32[1] = v45;
      if ( v99.m128i_i32[3] >= pcoa->rclBounds.bottom )
        bottom = pcoa->rclBounds.bottom;
      v99.m128i_i32[3] = bottom;
      if ( (int)v45 >= bottom )
      {
LABEL_117:
        if ( v84 )
        {
          v49 = *(HSEMAPHORE *)(v85 + 192);
          *(_QWORD *)(v85 + 536) = 0;
          if ( v49 )
            EngReleaseSemaphore(v49);
        }
        if ( !v89 )
        {
          LOBYTE(v45) = 2;
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(v86 + 264))(v87, v45, v88);
        }
        return v9;
      }
      *(_QWORD *)v56 = &v99;
    }
    memset(v100, 0, sizeof(v100));
    v105 = 0;
    v101 = 0;
    v103 = 0;
    v102 = 0;
    v104 = 0;
    v55 = 0;
    if ( (*(int (__fastcall **)(DHSURF, _QWORD, _QWORD, _QWORD, int, int, int *, SURFOBJ **, char))(*(_QWORD *)dhsurf
                                                                                                  + 56LL))(
           dhsurf,
           *(_QWORD *)v56,
           *(_QWORD *)v56,
           *(_QWORD *)v62,
           1,
           1,
           &v55,
           v100,
           1) >= 0 )
    {
      v101 = *(SURFOBJ **)v62;
      v102 = dhsurf;
      v103 = *(_QWORD *)v56;
      v105 = v100[0]->dhpdev;
      v100[0]->dhpdev = 0;
      v48 = v55;
      if ( v55 )
      {
        CDDPDEV::Flush((CDDPDEV *)psoa);
        v48 = v55;
      }
      WaitForStartGdiAccessToFinish((struct CDDPDEV *)psoa, (struct CDDBITMAP_GDIDESC *)v100, v48);
    }
    if ( !v102 )
    {
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 6170;
      v50 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v50[3] = gCddImageInfo;
      v50[4] = (unsigned int)dword_14003E570;
      v50[5] = 215857758;
      WdLogGlobalForLineNumber = 6170;
      if ( v102 )
      {
        v100[0]->dhpdev = v105;
        v51 = v102;
        if ( !v104 )
          (*(void (__fastcall **)(DHSURF, SURFOBJ **, __int64, SURFOBJ *, _QWORD))(*(_QWORD *)v102 + 64LL))(
            v102,
            v100,
            v103,
            v101,
            0);
        (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v51 + 128LL))(v51, v100);
      }
      goto LABEL_29;
    }
    v52 = EngLineTo(v100[0], pcoa, pboa, v11, y1, x2, y2, prclBounds, mix);
    v53 = v104;
    if ( !v52 )
      v53 = 1;
    v104 = v53;
    if ( v102 )
    {
      v100[0]->dhpdev = v105;
      v54 = v102;
      if ( !v104 )
        (*(void (__fastcall **)(DHSURF, SURFOBJ **, __int64, SURFOBJ *, _QWORD))(*(_QWORD *)v102 + 64LL))(
          v102,
          v100,
          v103,
          v101,
          0);
      (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v54 + 128LL))(v54, v100);
    }
    CDDBITMAPLOCK::~CDDBITMAPLOCK((CDDBITMAPLOCK *)&v84);
  }
  CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v86);
  return v52;
}

```

## disassembly

```asm
0x140005cc0  push    rbp
0x140005cc2  push    rbx
0x140005cc3  push    rsi
0x140005cc4  push    rdi
0x140005cc5  push    r12
0x140005cc7  push    r13
0x140005cc9  push    r14
0x140005ccb  push    r15
0x140005ccd  lea     rbp, [rsp-1B8h]
0x140005cd5  sub     rsp, 2B8h
0x140005cdc  mov     rax, cs:__security_cookie
0x140005ce3  xor     rax, rsp
0x140005ce6  mov     [rbp+1F0h+var_50], rax
0x140005ced  mov     rdi, [rbp+1F0h+prclBounds]
0x140005cf4  xorps   xmm0, xmm0
0x140005cf7  mov     [rsp+2F0h+pco], rdx
0x140005cfc  mov     ebx, 1
0x140005d01  mov     rsi, [rcx+10h]
0x140005d05  mov     r12d, r9d
0x140005d08  movups  [rbp+1F0h+var_160], xmm0
0x140005d0f  mov     [rsp+2F0h+var_288], r9d
0x140005d14  movups  [rbp+1F0h+var_150], xmm0
0x140005d1b  mov     [rbp+1F0h+pbo], r8
0x140005d22  movups  [rbp+1F0h+var_140], xmm0
0x140005d29  mov     rax, [rsi+50h]
0x140005d2d  mov     [rbp+1F0h+pso], rcx
0x140005d31  mov     qword ptr [rbp+1F0h+var_258], rcx
0x140005d35  mov     [rsp+2F0h+var_290], 0
0x140005d3d  mov     [rbp+1F0h+var_168], ebx
0x140005d43  mov     [rbp+1F0h+var_170], 0
0x140005d4e  call    _guard_dispatch_icall
0x140005d53  mov     r14d, [rbp+1F0h+y2]
0x140005d5a  xor     edx, edx
0x140005d5c  mov     r15d, [rbp+1F0h+x2]
0x140005d63  mov     r13d, [rbp+1F0h+y1]
0x140005d6a  test    eax, eax
0x140005d6c  jz      loc_140005E07
0x140005d72  mov     rcx, [rbp+1F0h+pso]
0x140005d76  mov     dword ptr [rbp+1F0h+var_160], edx
0x140005d7c  mov     qword ptr [rbp+1F0h+var_160+8], rdx
0x140005d83  mov     dword ptr [rbp+1F0h+var_150+8], edx
0x140005d89  mov     qword ptr [rbp+1F0h+var_140+8], rdx
0x140005d90  movzx   eax, word ptr [rcx+4Ch]
0x140005d94  mov     ecx, [rdi+8]
0x140005d97  sub     ecx, [rdi]
0x140005d99  mov     dword ptr [rbp+1F0h+var_150], ecx
0x140005d9f  mov     ecx, [rdi+0Ch]
0x140005da2  sub     ecx, [rdi+4]
0x140005da5  mov     dword ptr [rbp+1F0h+var_150+4], ecx
0x140005dab  mov     ecx, [rbp+1F0h+mix]
0x140005db1  mov     dword ptr [rbp+1F0h+var_160+4], eax
0x140005db7  movzx   eax, cx
0x140005dba  mov     dword ptr [rbp+1F0h+var_140], eax
0x140005dc0  cmp     r12d, r15d
0x140005dc3  jz      short loc_140005DCC
0x140005dc5  mov     eax, edx
0x140005dc7  cmp     r13d, r14d
0x140005dca  jnz     short loc_140005DCE
0x140005dcc  mov     eax, ebx
0x140005dce  mov     r8, [rbp+1F0h+pbo]
0x140005dd5  lea     r9, [rbp+1F0h+var_160]; struct _DXGKETW_PARAMS *
0x140005ddc  mov     dword ptr [rbp+1F0h+var_140+4], eax
0x140005de2  lea     rcx, [rbp+1F0h+var_180]; this
0x140005de6  mov     eax, edx
0x140005de8  mov     byte ptr [rsp+2F0h+var_2D0], dl; bool
0x140005dec  mov     rdx, rsi; struct CDDPDEV *
0x140005def  cmp     dword ptr [r8], 0FFFFFFFFh
0x140005df3  mov     r8d, 0BD1h; unsigned int
0x140005df9  setnz   al
0x140005dfc  mov     dword ptr [rbp+1F0h+var_150+0Ch], eax
0x140005e02  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x140005e07  mov     rax, [rbp+1F0h+pso]
0x140005e0b  cmp     [rax+4Ch], bx
0x140005e0f  jz      loc_14000689E
0x140005e15  mov     rsi, [rax]
0x140005e18  lea     rcx, [rbp+1F0h+var_190]; this
0x140005e1c  mov     rdx, rsi; struct CddBitmap *
0x140005e1f  call    ??0CDDBITMAPLOCK@@QEAA@PEAVCddBitmap@@@Z; CDDBITMAPLOCK::CDDBITMAPLOCK(CddBitmap *)
0x140005e24  mov     r9, [rsi+8]
0x140005e28  mov     eax, [rsi+80h]
0x140005e2e  mov     [rbp+1F0h+pso], r9
0x140005e32  test    bl, al
0x140005e34  jz      loc_14000652A
0x140005e3a  cmp     r12d, r15d
0x140005e3d  jz      short loc_140005E48
0x140005e3f  cmp     r13d, r14d
0x140005e42  jnz     loc_140005FA7
0x140005e48  mov     r11, [rbp+1F0h+pbo]
0x140005e4f  mov     r8d, ebx
0x140005e52  mov     r10d, [rbp+1F0h+mix]
0x140005e59  mov     [rbp+1F0h+var_260], ebx
0x140005e5c  mov     ecx, [r11]
0x140005e5f  mov     [rsp+2F0h+var_280], ecx
0x140005e63  cmp     ecx, 0FFFFFFFFh
0x140005e66  jz      short loc_140005E71
0x140005e68  cmp     r10d, 0D0Dh
0x140005e6f  jz      short loc_140005E92
0x140005e71  lea     r8, [rbp+1F0h+var_260]; enum _DXGK_GDIROP_COLORFILL *
0x140005e75  mov     ecx, r10d; unsigned int
0x140005e78  lea     rdx, [rsp+2F0h+var_280]; unsigned int *
0x140005e7d  call    ?ComputeColorFillParams@@YAHKAEAIAEAW4_DXGK_GDIROP_COLORFILL@@@Z; ComputeColorFillParams(ulong,uint &,_DXGK_GDIROP_COLORFILL &)
0x140005e82  test    eax, eax
0x140005e84  jz      loc_140005FB5
0x140005e8a  mov     ecx, [rsp+2F0h+var_280]
0x140005e8e  mov     r8d, [rbp+1F0h+var_260]
0x140005e92  mov     r9, [rsp+2F0h+pco]
0x140005e97  cmp     r12d, r15d
0x140005e9a  jg      short loc_140005EBD
0x140005e9c  mov     dword ptr [rbp+1F0h+pbo], r12d
0x140005ea3  cmp     r13d, r14d
0x140005ea6  jnz     short loc_140005EB1
0x140005ea8  mov     [rbp+1F0h+var_D8], r15d
0x140005eaf  jmp     short loc_140005EF6
0x140005eb1  lea     eax, [r15+1]
0x140005eb5  mov     [rbp+1F0h+var_D8], eax
0x140005ebb  jmp     short loc_140005EF1
0x140005ebd  lea     edx, [r12+1]
0x140005ec2  mov     [rbp+1F0h+var_D8], edx
0x140005ec8  cmp     r13d, r14d
0x140005ecb  jnz     short loc_140005EEA
0x140005ecd  lea     eax, [r15+1]
0x140005ed1  mov     dword ptr [rbp+1F0h+pbo], eax
0x140005ed7  lea     eax, [r14+1]
0x140005edb  mov     dword ptr [rbp+1F0h+pbo+4], r13d
0x140005ee2  mov     [rbp+1F0h+var_D4], eax
0x140005ee8  jmp     short loc_140005F2D
0x140005eea  mov     dword ptr [rbp+1F0h+pbo], r15d
0x140005ef1  cmp     r13d, r14d
0x140005ef4  jg      short loc_140005F0B
0x140005ef6  cmp     r12d, r15d
0x140005ef9  jnz     short loc_140005ED7
0x140005efb  mov     dword ptr [rbp+1F0h+pbo+4], r13d
0x140005f02  mov     [rbp+1F0h+var_D4], r14d
0x140005f09  jmp     short loc_140005F2D
0x140005f0b  inc     r13d
0x140005f0e  mov     [rbp+1F0h+var_D4], r13d
0x140005f15  cmp     r12d, r15d
0x140005f18  jnz     short loc_140005F26
0x140005f1a  lea     eax, [r14+1]
0x140005f1e  mov     dword ptr [rbp+1F0h+pbo+4], eax
0x140005f24  jmp     short loc_140005F2D
0x140005f26  mov     dword ptr [rbp+1F0h+pbo+4], r14d
0x140005f2d  xor     edx, edx
0x140005f2f  mov     dword ptr [rbp+1F0h+var_1D8+4], ecx
0x140005f32  lea     rax, [rbp+1F0h+pbo]
0x140005f39  mov     byte ptr [rbp+1F0h+var_200], dl
0x140005f3c  mov     [rbp+1F0h+var_228], rax
0x140005f40  lea     rcx, [rbp+1F0h+var_230]; struct CLIP_RECTS_DATA *
0x140005f44  lea     rax, [rbp+1F0h+pbo]
0x140005f4b  mov     [rbp+1F0h+var_1E8], rdx
0x140005f4f  mov     [rbp+1F0h+var_220], rax
0x140005f53  lea     rax, [rbp+1F0h+pbo]
0x140005f5a  mov     [rbp+1F0h+var_218], rax
0x140005f5e  mov     eax, [rsi+28h]
0x140005f61  mov     [rbp+1F0h+var_208], rdx
0x140005f65  lea     rdx, ?ColorFillCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z; int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)
0x140005f6c  mov     dword ptr [rbp+1F0h+var_1D8], eax
0x140005f6f  mov     [rbp+1F0h+var_230], r9
0x140005f73  mov     [rbp+1F0h+var_1E0], rsi
0x140005f77  mov     dword ptr [rbp+1F0h+var_1D0], r8d
0x140005f7b  call    ?ClipDstRects@@YAJPEAUCLIP_RECTS_DATA@@P6AJ0IPEBUtagRECT@@@Z@Z; ClipDstRects(CLIP_RECTS_DATA *,long (*)(CLIP_RECTS_DATA *,uint,tagRECT const *))
0x140005f80  mov     rcx, rsi; this
0x140005f83  call    ?VidMemDirtyUpdate@CddBitmap@@QEAAXXZ; CddBitmap::VidMemDirtyUpdate(void)
0x140005f88  mov     dword ptr [rbp+1F0h+var_150+8], ebx
0x140005f8e  lea     rcx, [rbp+1F0h+var_190]; this
0x140005f92  call    ??1CDDBITMAPLOCK@@QEAA@XZ; CDDBITMAPLOCK::~CDDBITMAPLOCK(void)
0x140005f97  lea     rcx, [rbp+1F0h+var_180]; this
0x140005f9b  call    ??1CDDETWPROFILER@@QEAA@XZ; CDDETWPROFILER::~CDDETWPROFILER(void)
0x140005fa0  mov     eax, ebx
0x140005fa2  jmp     loc_1400069FA
0x140005fa7  mov     r10d, [rbp+1F0h+mix]
0x140005fae  mov     r11, [rbp+1F0h+pbo]
0x140005fb5  mov     eax, r10d
0x140005fb8  lea     ecx, [r10-1]
0x140005fbc  shr     eax, 8
0x140005fbf  lea     rdx, ?ROP2_NEED_DEST@@3PAHA; int near * ROP2_NEED_DEST
0x140005fc6  sub     eax, ebx
0x140005fc8  and     ecx, 0Fh
0x140005fcb  and     eax, 0Fh
0x140005fce  mov     eax, [rdx+rax*4]
0x140005fd1  or      eax, [rdx+rcx*4]
0x140005fd4  jnz     loc_14000652A
0x140005fda  mov     eax, [r11]
0x140005fdd  mov     [rsp+2F0h+var_280], eax
0x140005fe1  mov     [rbp+1F0h+var_260], eax
0x140005fe4  mov     [rbp+1F0h+var_258], ebx
0x140005fe7  cmp     eax, 0FFFFFFFFh
0x140005fea  jz      short loc_140005FF5
0x140005fec  cmp     r10d, 0D0Dh
0x140005ff3  jz      short loc_140006014
0x140005ff5  lea     r8, [rbp+1F0h+var_258]; enum _DXGK_GDIROP_COLORFILL *
0x140005ff9  mov     ecx, r10d; unsigned int
0x140005ffc  lea     rdx, [rbp+1F0h+var_260]; unsigned int *
0x140006000  call    ?ComputeColorFillParams@@YAHKAEAIAEAW4_DXGK_GDIROP_COLORFILL@@@Z; ComputeColorFillParams(ulong,uint &,_DXGK_GDIROP_COLORFILL &)
0x140006005  test    eax, eax
0x140006007  jz      loc_14000630A
0x14000600d  mov     eax, [rbp+1F0h+var_260]
0x140006010  mov     [rsp+2F0h+var_280], eax
0x140006014  mov     r8, rsi; struct CddBitmap *
0x140006017  lea     rcx, [rbp+1F0h+var_248]; this
0x14000601b  mov     rdx, r9; struct CDDPDEV *
0x14000601e  call    ??0TempSurfObjHelper@@QEAA@PEAUCDDPDEV@@PEAVCddBitmap@@@Z; TempSurfObjHelper::TempSurfObjHelper(CDDPDEV *,CddBitmap *)
0x140006023  mov     r12, [rbp+1F0h+var_248]
0x140006027  lea     rax, ?EngWritePixelCallback@@YAXPEAU_W32KCDD_ENG_CALLBACKS@@IQEAX@Z; EngWritePixelCallback(_W32KCDD_ENG_CALLBACKS *,uint,void * const)
0x14000602e  xor     edx, edx
0x140006030  mov     rcx, [r12+10h]
0x140006035  mov     [rbp+1F0h+var_230], rax
0x140006039  lea     rax, ?EngFillRectCallback@@YAXPEAU_W32KCDD_ENG_CALLBACKS@@IPEBUtagRECT@@@Z; EngFillRectCallback(_W32KCDD_ENG_CALLBACKS *,uint,tagRECT const *)
0x140006040  mov     [rbp+1F0h+var_228], rax
0x140006044  mov     eax, [rsi+28h]
0x140006047  mov     [rbp+1F0h+var_1C8], eax
0x14000604a  mov     eax, [rsp+2F0h+var_280]
0x14000604e  mov     [rbp+1F0h+var_1C4], eax
0x140006051  mov     eax, [rbp+1F0h+var_258]
0x140006054  mov     [rbp+1F0h+var_1B8], rdx
0x140006058  mov     [rbp+1F0h+var_1B0], edx
0x14000605b  mov     [rbp+1F0h+var_1C0], eax
0x14000605e  mov     [rbp+1F0h+var_1F0], dl
0x140006061  mov     [rbp+1F0h+var_1D8], rdx
0x140006065  mov     qword ptr [rbp+1F0h+var_1A0], rdx
0x140006069  mov     [rbp+1F0h+var_1A8], rdx
0x14000606d  mov     [rbp+1F0h+var_220], rdx
0x140006071  mov     [rbp+1F0h+var_218], rdi
0x140006075  mov     [rbp+1F0h+var_210], rdi
0x140006079  mov     [rbp+1F0h+var_208], rdi
0x14000607d  mov     [rbp+1F0h+var_1D0], rsi
0x140006081  mov     rax, [rcx+30h]
0x140006085  mov     [rbp+1F0h+var_1B8], rax
0x140006089  mov     eax, [rcx+40h]
0x14000608c  mov     qword ptr [rbp+1F0h+var_260], rcx
0x140006090  mov     rcx, rsi; this
0x140006093  mov     [rbp+1F0h+var_1B0], eax
0x140006096  call    ?GetRectBuffer@CddBitmapHw@@QEAAPEAUtagRECT@@XZ; CddBitmapHw::GetRectBuffer(void)
0x14000609b  cmp     [rbp+1F0h+var_1C8], 0
0x14000609f  mov     rcx, rax
0x1400060a2  mov     [rbp+1F0h+var_1A8], rax
0x1400060a6  mov     eax, [rsi+4A8h]
0x1400060ac  mov     [rbp+1F0h+var_1A0+4], eax
0x1400060af  jnz     short loc_14000612A
0x1400060b1  mov     rdi, [rbp+1F0h+var_240]
0x1400060b5  lea     rcx, [rbp+1F0h+var_248]; this
0x1400060b9  mov     rdx, [rdi+1580h]
0x1400060c0  mov     rdx, [rdx+0B58h]; struct CDDMUTEX *
0x1400060c7  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x1400060cc  lea     rax, [rdi+1898h]
0x1400060d3  mov     rcx, [rax]
0x1400060d6  cmp     [rcx+8], rax
0x1400060da  jnz     loc_1400062B2
0x1400060e0  mov     [r12], rcx
0x1400060e4  xor     r9d, r9d; Wait
0x1400060e7  mov     [r12+8], rax
0x1400060ec  mov     r8d, ebx; Adjustment
0x1400060ef  mov     [rcx+8], r12
0x1400060f3  xor     edx, edx; Increment
0x1400060f5  mov     [rax], r12
0x1400060f8  mov     rcx, [rdi+18A8h]; Semaphore
0x1400060ff  call    cs:__imp_KeReleaseSemaphore
0x140006106  nop     dword ptr [rax+rax+00h]
0x14000610b  cmp     dword ptr [rbp+1F0h+var_240], 0
0x14000610f  jz      loc_140005F8E
0x140006115  mov     rcx, [rbp+1F0h+var_248]
0x140006119  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140006120  nop     dword ptr [rax+rax+00h]
0x140006125  jmp     loc_140005F8E
0x14000612a  test    rcx, rcx
0x14000612d  jz      loc_140006283
0x140006133  mov     rax, [rbp+1F0h+pso]
0x140006137  lea     rcx, [rbp+1F0h+var_230]
0x14000613b  mov     r9d, [rsp+2F0h+var_288]
0x140006140  mov     r8, [rbp+1F0h+pbo]
0x140006147  mov     rdx, [rsp+2F0h+pco]
0x14000614c  mov     rax, [rax+270h]
0x140006153  mov     [rsp+2F0h+var_2A8], rcx
0x140006158  mov     ecx, [rbp+1F0h+mix]
0x14000615e  mov     [rsp+2F0h+var_2B0], ecx
0x140006162  mov     rcx, qword ptr [rbp+1F0h+var_260]
0x140006166  mov     [rsp+2F0h+var_2B8], rdi
0x14000616b  mov     [rsp+2F0h+var_2C0], r14d
0x140006170  mov     [rsp+2F0h+var_2C8], r15d
0x140006175  mov     [rsp+2F0h+var_2D0], r13d
0x14000617a  call    _guard_dispatch_icall
0x14000617f  mov     [rsp+2F0h+var_290], eax
0x140006183  test    eax, eax
0x140006185  jz      loc_140006283
0x14000618b  cmp     [rbp+1F0h+var_1A0], 0
0x14000618f  jz      loc_140006283
0x140006195  mov     rdx, [rbp+1F0h+pso]; struct CDDPDEV *
0x140006199  lea     rcx, [rbp+1F0h+var_258]; this
0x14000619d  xor     r9d, r9d; unsigned __int8
0x1400061a0  xor     r8d, r8d; unsigned __int8
0x1400061a3  call    ??0CCommandBufferMutex@@QEAA@PEAUCDDPDEV@@EE@Z; CCommandBufferMutex::CCommandBufferMutex(CDDPDEV *,uchar,uchar)
0x1400061a8  mov     r9, [rbp+1F0h+var_1A8]; struct tagRECT *
0x1400061ac  lea     rax, [rbp+1F0h+var_258]
0x1400061b0  mov     r8d, [rbp+1F0h+var_1A0]; unsigned int
0x1400061b4  lea     rdx, [rbp+1F0h+var_220]; struct COLORFILL_DATA *
0x1400061b8  mov     [rbp+1F0h+var_200], rax
0x1400061bc  mov     rax, [rbp+1F0h+pso]
0x1400061c0  mov     rcx, [rax+3198h]; this
0x1400061c7  call    ?AddColorFillCommand@CHwCommandBuffer@@QEAAHPEAUCOLORFILL_DATA@@IPEBUtagRECT@@@Z; CHwCommandBuffer::AddColorFillCommand(COLORFILL_DATA *,uint,tagRECT const *)
0x1400061cc  test    eax, eax
  ... truncated ...
```
