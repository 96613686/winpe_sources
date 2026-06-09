# DrvStrokeAndFillPath

- ea: `0x1400235c0`
- end: `0x140023e59`
- name: `DrvStrokeAndFillPath`
- size: `2201`
- prototype: `FN_DrvStrokeAndFillPath`
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001008`
- `0x140004600`
- `0x140006a30`
- `0x140008714`
- `0x14000874c`
- `0x14000c010`
- `0x14000c730`
- `0x14000cb44`
- `0x14000cec4`
- `0x14000ef80`
- `0x1400160c8`
- `0x14001d458`
- `0x1400226b0`
- `0x1400235c0`
- `0x1400248f8`
- `0x140033db0`
- `0x140033e60`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400237d3`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400237d3`
- `watchdog!WdLogSingleEntry0` at `0x1400237ba`
- `watchdog!WdLogSingleEntry0` at `0x140023887`
- `watchdog!WdLogSingleEntry0` at `0x140023b53`
- `watchdog!WdLogSingleEntry0` at `0x1400237ba`
- `watchdog!WdLogSingleEntry0` at `0x140023887`
- `watchdog!WdLogSingleEntry0` at `0x140023b53`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002389e`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140023b6a`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002389e`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140023b6a`
- `WIN32K!EngStrokeAndFillPath` at `0x1400239ae`
- `WIN32K!EngStrokeAndFillPath` at `0x140023c4d`
- `WIN32K!EngStrokeAndFillPath` at `0x140023df6`
- `WIN32K!EngStrokeAndFillPath` at `0x1400239ae`
- `WIN32K!EngStrokeAndFillPath` at `0x140023c4d`
- `WIN32K!EngStrokeAndFillPath` at `0x140023df6`
- `WIN32K!PATHOBJ_vGetBounds` at `0x140023652`
- `WIN32K!PATHOBJ_vGetBounds` at `0x140023652`

## pseudocode

```c
BOOL __stdcall DrvStrokeAndFillPath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        XFORMOBJ *pxo,
        BRUSHOBJ *pboStroke,
        LINEATTRS *plineattrs,
        BRUSHOBJ *pboFill,
        POINTL *pptlBrushOrg,
        MIX mixFill,
        FLONG flOptions)
{
  DHPDEV dhpdev; // rdi
  BOOL v14; // esi
  LONG right; // r9d
  LONG bottom; // r10d
  FIX left; // edx
  FIX top; // r8d
  BOOL v19; // ebx
  int v20; // r8d
  DHSURF dhsurf; // rdi
  CDDPDEV *v22; // rsi
  _QWORD *v23; // rax
  __int64 v24; // rax
  CddBitmap *v25; // rax
  _QWORD *v26; // rax
  LONG lDelta; // edx
  int v28; // eax
  CLIPOBJ *v29; // r14
  __int64 v30; // rax
  int (__fastcall *v31)(DHSURF, struct _RECTL *, struct _RECTL *, CLIPOBJ *, int, int, int *, SURFOBJ **, char); // rax
  int v32; // r8d
  _QWORD *v33; // rax
  DHSURF v34; // rdi
  int v35; // eax
  DHSURF v36; // rbx
  _BOOL8 v37; // r14
  int v39; // [rsp+50h] [rbp-B0h] BYREF
  CLIPOBJ *pcoa; // [rsp+58h] [rbp-A8h] BYREF
  POINTL *v41; // [rsp+60h] [rbp-A0h]
  BRUSHOBJ *v42; // [rsp+68h] [rbp-98h]
  LINEATTRS *v43; // [rsp+70h] [rbp-90h]
  BRUSHOBJ *v44; // [rsp+78h] [rbp-88h]
  SURFOBJ *v45[2]; // [rsp+80h] [rbp-80h] BYREF
  XFORMOBJ *pxoa; // [rsp+90h] [rbp-70h]
  __int128 v47; // [rsp+98h] [rbp-68h] BYREF
  __int128 v48; // [rsp+A8h] [rbp-58h]
  __int128 v49; // [rsp+B8h] [rbp-48h]
  _BYTE v50[16]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v51; // [rsp+D8h] [rbp-28h]
  int v52; // [rsp+E0h] [rbp-20h]
  _BYTE v53[24]; // [rsp+E8h] [rbp-18h] BYREF
  SURFOBJ *psoa[8]; // [rsp+100h] [rbp+0h] BYREF
  CddBitmap *v55; // [rsp+140h] [rbp+40h]
  struct _RECTL *v56; // [rsp+148h] [rbp+48h]
  struct _RECTL rclBounds; // [rsp+150h] [rbp+50h] BYREF
  SURFOBJ *v58[8]; // [rsp+160h] [rbp+60h] BYREF
  CLIPOBJ *v59; // [rsp+1A0h] [rbp+A0h]
  DHSURF v60; // [rsp+1A8h] [rbp+A8h]
  SURFOBJ *p_rclBounds; // [rsp+1B0h] [rbp+B0h]
  DHSURF v62; // [rsp+1B8h] [rbp+B8h]
  DHPDEV v63; // [rsp+1C0h] [rbp+C0h]
  int v64; // [rsp+1C8h] [rbp+C8h]
  int v65; // [rsp+1CCh] [rbp+CCh]
  LONG v66; // [rsp+1D0h] [rbp+D0h]
  struct _RECTFX prectfx; // [rsp+1E0h] [rbp+E0h] BYREF

  v44 = pboStroke;
  v43 = plineattrs;
  v42 = pboFill;
  pcoa = pco;
  dhpdev = pso->dhpdev;
  v45[0] = pso;
  v41 = pptlBrushOrg;
  pxoa = pxo;
  prectfx = 0;
  PATHOBJ_vGetBounds(ppo, &prectfx);
  v14 = 0;
  right = (prectfx.xRight + 15) >> 4;
  bottom = (prectfx.yBottom + 15) >> 4;
  left = prectfx.xLeft >> 4;
  top = prectfx.yTop >> 4;
  rclBounds.left = prectfx.xLeft >> 4;
  rclBounds.top = prectfx.yTop >> 4;
  rclBounds.right = right;
  rclBounds.bottom = bottom;
  if ( pcoa )
  {
    if ( pcoa->iDComplexity )
    {
      rclBounds = pcoa->rclBounds;
    }
    else
    {
      if ( pcoa->rclBounds.left < left )
        left = pcoa->rclBounds.left;
      rclBounds.left = left;
      if ( pcoa->rclBounds.top < top )
        top = pcoa->rclBounds.top;
      rclBounds.top = top;
      if ( pcoa->rclBounds.right > right )
        right = pcoa->rclBounds.right;
      rclBounds.right = right;
      if ( pcoa->rclBounds.bottom > bottom )
        bottom = pcoa->rclBounds.bottom;
      rclBounds.bottom = bottom;
    }
  }
  v51 = 0;
  v47 = 0;
  v19 = 1;
  v48 = 0;
  v52 = 1;
  v49 = 0;
  if ( (*((unsigned int (**)(void))dhpdev + 10))() )
  {
    v48 = 0;
    v47 = 0;
    v49 = 0;
    DWORD1(v47) = pso->iType;
    LODWORD(v48) = rclBounds.right - rclBounds.left;
    DWORD1(v48) = rclBounds.bottom - rclBounds.top;
    LODWORD(v49) = (unsigned __int16)mixFill;
    CDDETWPROFILER::Init((CDDETWPROFILER *)v50, (struct CDDPDEV *)dhpdev, 0xBD3u, (struct _DXGKETW_PARAMS *)&v47, 0);
  }
  if ( pso->iType == 1 )
  {
    CDDDEVLOCK::CDDDEVLOCK((CDDDEVLOCK *)v53, *((HSEMAPHORE *)dhpdev + 365), v20);
    if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
    {
      LODWORD(v37) = 1;
    }
    else
    {
      CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 56LL) = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
      v37 = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) != 0;
    }
    CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v53);
    if ( v37 )
    {
      ReadFromFrameBuffer((struct CDDPDEV *)dhpdev, rclBounds.left, rclBounds.top, rclBounds.right, rclBounds.bottom);
      v39 = 0;
      CDDSURFLOCK::vInit((CDDSURFLOCK *)v58, (struct CDDPDEV *)dhpdev, v45, &rclBounds, &v39, pcoa);
      if ( (unsigned int)bIgnoreDeviceSurfaceUpdates(pso, &pcoa) )
      {
        CDDSURFLOCK::vDone((CDDSURFLOCK *)v58);
        goto LABEL_63;
      }
      v14 = EngStrokeAndFillPath(v45[0], ppo, pcoa, pxoa, v44, v43, v42, v41, mixFill, flOptions);
      if ( v14 && v39 == 1 )
        vGDIDirtyUpdate((struct CDDPDEV *)dhpdev, &rclBounds, pcoa);
      CDDSURFLOCK::vDone((CDDSURFLOCK *)v58);
    }
LABEL_62:
    v19 = v14;
    goto LABEL_63;
  }
  dhsurf = pso->dhsurf;
  CDDBITMAPLOCK::CDDBITMAPLOCK((CDDBITMAPLOCK *)v45, (struct CddBitmap *)pso->dhsurf);
  v22 = (CDDPDEV *)*((_QWORD *)dhsurf + 1);
  if ( rclBounds.left < 0
    || rclBounds.top < 0
    || rclBounds.right > *((_DWORD *)dhsurf + 4)
    || rclBounds.bottom > *((_DWORD *)dhsurf + 5)
    || rclBounds.left >= rclBounds.right
    || rclBounds.top >= rclBounds.bottom )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 6463;
    v23 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v23[3] = gCddImageInfo;
    v23[4] = (unsigned int)dword_14003E570;
    v23[5] = 215857758;
    WdLogGlobalForLineNumber = 6463;
  }
  if ( *((_DWORD *)&ROP2_NEED_DEST + (((_BYTE)mixFill - 1) & 0xF))
     | *((_DWORD *)&ROP2_NEED_DEST + ((BYTE1(mixFill) - 1) & 0xF))
    || ((_DWORD)dhsurf[32] & 1) == 0 )
  {
    v29 = pcoa;
    memset(v58, 0, sizeof(v58));
    v30 = *(_QWORD *)dhsurf;
    v63 = 0;
    v31 = *(int (__fastcall **)(DHSURF, struct _RECTL *, struct _RECTL *, CLIPOBJ *, int, int, int *, SURFOBJ **, char))(v30 + 56);
    v59 = 0;
    p_rclBounds = 0;
    v60 = 0;
    LODWORD(v62) = 0;
    v39 = 0;
    if ( v31(dhsurf, &rclBounds, &rclBounds, pcoa, 1, 1, &v39, v58, 1) >= 0 )
    {
      v60 = dhsurf;
      v59 = v29;
      p_rclBounds = (SURFOBJ *)&rclBounds;
      v63 = v58[0]->dhpdev;
      v58[0]->dhpdev = 0;
      v32 = v39;
      if ( v39 )
      {
        CDDPDEV::Flush(v22);
        v32 = v39;
      }
      WaitForStartGdiAccessToFinish(v22, (struct CDDBITMAP_GDIDESC *)v58, v32);
    }
    if ( !v60 )
    {
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 6515;
      v33 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v33[3] = gCddImageInfo;
      v33[4] = (unsigned int)dword_14003E570;
      v33[5] = 215857758;
      WdLogGlobalForLineNumber = 6515;
      if ( v60 )
      {
        v58[0]->dhpdev = v63;
        v34 = v60;
        if ( !(_DWORD)v62 )
          (*(void (__fastcall **)(DHSURF, SURFOBJ **, SURFOBJ *, CLIPOBJ *, _QWORD))(*(_QWORD *)v60 + 64LL))(
            v60,
            v58,
            p_rclBounds,
            v59,
            0);
        (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v34 + 128LL))(v34, v58);
      }
      goto LABEL_31;
    }
    v14 = EngStrokeAndFillPath(v58[0], ppo, pcoa, pxoa, v44, v43, v42, v41, mixFill, flOptions);
    v35 = (int)v62;
    if ( !v14 )
      v35 = 1;
    LODWORD(v62) = v35;
    if ( v60 )
    {
      v58[0]->dhpdev = v63;
      v36 = v60;
      if ( !(_DWORD)v62 )
        (*(void (__fastcall **)(DHSURF, SURFOBJ **, SURFOBJ *, CLIPOBJ *, _QWORD))(*(_QWORD *)v60 + 64LL))(
          v60,
          v58,
          p_rclBounds,
          v59,
          0);
      (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v36 + 128LL))(v36, v58);
    }
    goto LABEL_51;
  }
  memset(psoa, 0, sizeof(psoa));
  v24 = *(_QWORD *)dhsurf;
  v55 = 0;
  if ( (*(int (__fastcall **)(DHSURF, struct _RECTL *, __int64, SURFOBJ **))(v24 + 96))(dhsurf, &rclBounds, 1, psoa) < 0 )
  {
    v25 = v55;
  }
  else
  {
    v25 = (CddBitmap *)dhsurf;
    v55 = (CddBitmap *)dhsurf;
    v56 = &rclBounds;
  }
  if ( v25 )
  {
    v58[0] = (SURFOBJ *)pcoa;
    v58[1] = (SURFOBJ *)&rclBounds;
    v58[2] = (SURFOBJ *)&rclBounds;
    v58[3] = (SURFOBJ *)&rclBounds;
    LOBYTE(v58[6]) = 0;
    v60 = 0;
    p_rclBounds = (SURFOBJ *)psoa[0]->pvScan0;
    LODWORD(v62) = psoa[0]->lDelta;
    HIDWORD(v62) = -251592189;
    v58[5] = 0;
    ClipDstRects(
      (struct CLIP_RECTS_DATA *)v58,
      (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))FillColorKeyCallback);
    v14 = EngStrokeAndFillPath(psoa[0], ppo, pcoa, pxo, v44, v43, v42, v41, mixFill, flOptions);
    if ( v14 )
    {
      v58[0] = (SURFOBJ *)pcoa;
      LOBYTE(v58[6]) = 0;
      v60 = 0;
      lDelta = psoa[0]->lDelta;
      v58[1] = (SURFOBJ *)((char *)&psoa[4] + 4);
      v58[2] = (SURFOBJ *)&rclBounds;
      v58[3] = (SURFOBJ *)&rclBounds;
      p_rclBounds = psoa[3];
      LODWORD(v63) = psoa[2];
      v28 = *((_DWORD *)dhsurf + 10);
      v66 = lDelta;
      HIDWORD(v63) = v28;
      v64 = -251592189;
      v62 = dhsurf;
      v65 = 1;
      v58[5] = 0;
      ClipDstRects(
        (struct CLIP_RECTS_DATA *)v58,
        (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::TransparentBltCallback);
    }
    if ( v55 )
    {
      (*(void (__fastcall **)(CddBitmap *, SURFOBJ **))(*(_QWORD *)v55 + 128LL))(v55, psoa);
      CddBitmap::VidMemDirtyUpdate(v55);
    }
LABEL_51:
    CDDBITMAPLOCK::~CDDBITMAPLOCK((CDDBITMAPLOCK *)v45);
    goto LABEL_62;
  }
  WdLogSingleEntry0(4);
  WdLogGlobalForLineNumber = 6470;
  v26 = (_QWORD *)WdLogNewEntry5_WdEvent();
  v26[3] = gCddImageInfo;
  v26[4] = (unsigned int)dword_14003E570;
  v26[5] = 215857758;
  WdLogGlobalForLineNumber = 6470;
  if ( v55 )
  {
    (*(void (__fastcall **)(CddBitmap *, SURFOBJ **))(*(_QWORD *)v55 + 128LL))(v55, psoa);
    CddBitmap::VidMemDirtyUpdate(v55);
  }
LABEL_31:
  CDDBITMAPLOCK::~CDDBITMAPLOCK((CDDBITMAPLOCK *)v45);
LABEL_63:
  CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)v50);
  return v19;
}

```

## disassembly

```asm
0x1400235c0  push    rbp
0x1400235c2  push    rbx
0x1400235c3  push    rsi
0x1400235c4  push    rdi
0x1400235c5  push    r12
0x1400235c7  push    r13
0x1400235c9  push    r14
0x1400235cb  push    r15
0x1400235cd  lea     rbp, [rsp-108h]
0x1400235d5  sub     rsp, 208h
0x1400235dc  mov     rax, cs:__security_cookie
0x1400235e3  xor     rax, rsp
0x1400235e6  mov     [rbp+140h+var_50], rax
0x1400235ed  mov     rax, [rbp+140h+pboStroke]
0x1400235f4  mov     r13, rdx
0x1400235f7  mov     [rsp+240h+var_1C8], rax
0x1400235fc  lea     rdx, [rbp+140h+prectfx]; prectfx
0x140023603  mov     rax, [rbp+140h+plineattrs]
0x14002360a  mov     r12, rcx
0x14002360d  mov     [rsp+240h+var_1D0], rax
0x140023612  xorps   xmm0, xmm0
0x140023615  mov     rax, [rbp+140h+pboFill]
0x14002361c  xorps   xmm1, xmm1
0x14002361f  mov     [rsp+240h+var_1D8], rax
0x140023624  mov     r14, r9
0x140023627  mov     rax, [rbp+140h+pptlBrushOrg]
0x14002362e  mov     [rsp+240h+pco], r8
0x140023633  mov     rdi, [rcx+10h]
0x140023637  mov     [rbp+140h+var_1C0], rcx
0x14002363b  mov     rcx, r13; ppo
0x14002363e  mov     [rsp+240h+var_1E0], rax
0x140023643  mov     [rbp+140h+pxo], r9
0x140023647  movups  xmmword ptr [rbp+140h+prectfx.xLeft], xmm0
0x14002364e  movups  xmmword ptr [rbp+140h+var_F0.left], xmm1
0x140023652  call    cs:__imp_PATHOBJ_vGetBounds
0x140023659  nop     dword ptr [rax+rax+00h]
0x14002365e  mov     r9d, [rbp+140h+prectfx.xRight]
0x140023665  xor     esi, esi
0x140023667  mov     r10d, [rbp+140h+prectfx.yBottom]
0x14002366e  add     r9d, 0Fh
0x140023672  mov     edx, [rbp+140h+prectfx.xLeft]
0x140023678  add     r10d, 0Fh
0x14002367c  mov     r8d, [rbp+140h+prectfx.yTop]
0x140023683  mov     rcx, [rsp+240h+pco]
0x140023688  sar     r9d, 4
0x14002368c  sar     r10d, 4
0x140023690  sar     edx, 4
0x140023693  sar     r8d, 4
0x140023697  mov     [rbp+140h+var_F0.left], edx
0x14002369a  mov     [rbp+140h+var_F0.top], r8d
0x14002369e  mov     [rbp+140h+var_F0.right], r9d
0x1400236a2  mov     [rbp+140h+var_F0.bottom], r10d
0x1400236a6  test    rcx, rcx
0x1400236a9  jz      short loc_1400236F1
0x1400236ab  cmp     [rcx+14h], sil
0x1400236af  jz      short loc_1400236BC
0x1400236b1  movups  xmm0, xmmword ptr [rcx+4]
0x1400236b5  movdqu  xmmword ptr [rbp+140h+var_F0.left], xmm0
0x1400236ba  jmp     short loc_1400236F1
0x1400236bc  mov     eax, [rcx+4]
0x1400236bf  cmp     eax, edx
0x1400236c1  cmovl   edx, eax
0x1400236c4  mov     [rbp+140h+var_F0.left], edx
0x1400236c7  mov     eax, [rcx+8]
0x1400236ca  cmp     eax, r8d
0x1400236cd  cmovl   r8d, eax
0x1400236d1  mov     [rbp+140h+var_F0.top], r8d
0x1400236d5  mov     eax, [rcx+0Ch]
0x1400236d8  cmp     eax, r9d
0x1400236db  cmovg   r9d, eax
0x1400236df  mov     [rbp+140h+var_F0.right], r9d
0x1400236e3  mov     eax, [rcx+10h]
0x1400236e6  cmp     eax, r10d
0x1400236e9  cmovg   r10d, eax
0x1400236ed  mov     [rbp+140h+var_F0.bottom], r10d
0x1400236f1  xorps   xmm0, xmm0
0x1400236f4  mov     [rbp+140h+var_168], rsi
0x1400236f8  movups  [rbp+140h+var_1A8], xmm0
0x1400236fc  mov     ebx, 1
0x140023701  movups  [rbp+140h+var_198], xmm0
0x140023705  mov     [rbp+140h+var_160], ebx
0x140023708  movups  [rbp+140h+var_188], xmm0
0x14002370c  mov     rax, [rdi+50h]
0x140023710  call    _guard_dispatch_icall
0x140023715  mov     r15d, [rbp+140h+mixFill]
0x14002371c  test    eax, eax
0x14002371e  jz      short loc_14002376C
0x140023720  xorps   xmm0, xmm0
0x140023723  mov     byte ptr [rsp+240h+var_220], sil; bool
0x140023728  movups  [rbp+140h+var_198], xmm0
0x14002372c  lea     r9, [rbp+140h+var_1A8]; struct _DXGKETW_PARAMS *
0x140023730  mov     r8d, 0BD3h; unsigned int
0x140023736  movups  [rbp+140h+var_1A8], xmm0
0x14002373a  mov     rdx, rdi; struct CDDPDEV *
0x14002373d  lea     rcx, [rbp+140h+var_178]; this
0x140023741  movups  [rbp+140h+var_188], xmm0
0x140023745  movzx   eax, word ptr [r12+4Ch]
0x14002374b  mov     dword ptr [rbp+140h+var_1A8+4], eax
0x14002374e  mov     eax, [rbp+140h+var_F0.right]
0x140023751  sub     eax, [rbp+140h+var_F0.left]
0x140023754  mov     dword ptr [rbp+140h+var_198], eax
0x140023757  mov     eax, [rbp+140h+var_F0.bottom]
0x14002375a  sub     eax, [rbp+140h+var_F0.top]
0x14002375d  mov     dword ptr [rbp+140h+var_198+4], eax
0x140023760  movzx   eax, r15w
0x140023764  mov     dword ptr [rbp+140h+var_188], eax
0x140023767  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x14002376c  cmp     [r12+4Ch], bx
0x140023772  jz      loc_140023CDE
0x140023778  mov     rdi, [r12]
0x14002377c  lea     rcx, [rbp+140h+var_1C0]; this
0x140023780  mov     rdx, rdi; struct CddBitmap *
0x140023783  call    ??0CDDBITMAPLOCK@@QEAA@PEAVCddBitmap@@@Z; CDDBITMAPLOCK::CDDBITMAPLOCK(CddBitmap *)
0x140023788  mov     r8d, [rbp+140h+var_F0.left]
0x14002378c  xor     r12d, r12d
0x14002378f  mov     rsi, [rdi+8]
0x140023793  test    r8d, r8d
0x140023796  js      short loc_1400237B8
0x140023798  mov     eax, [rbp+140h+var_F0.top]
0x14002379b  test    eax, eax
0x14002379d  js      short loc_1400237B8
0x14002379f  mov     ecx, [rbp+140h+var_F0.right]
0x1400237a2  cmp     ecx, [rdi+10h]
0x1400237a5  jg      short loc_1400237B8
0x1400237a7  mov     edx, [rbp+140h+var_F0.bottom]
0x1400237aa  cmp     edx, [rdi+14h]
0x1400237ad  jg      short loc_1400237B8
0x1400237af  cmp     r8d, ecx
0x1400237b2  jge     short loc_1400237B8
0x1400237b4  cmp     eax, edx
0x1400237b6  jl      short loc_140023806
0x1400237b8  mov     ecx, ebx
0x1400237ba  call    cs:__imp_WdLogSingleEntry0
0x1400237c1  nop     dword ptr [rax+rax+00h]
0x1400237c6  mov     r12d, 193Fh
0x1400237cc  mov     cs:WdLogGlobalForLineNumber, r12d
0x1400237d3  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400237da  nop     dword ptr [rax+rax+00h]
0x1400237df  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400237e6  mov     [rax+18h], rcx
0x1400237ea  mov     ecx, cs:dword_14003E570
0x1400237f0  mov     [rax+20h], rcx
0x1400237f4  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400237fc  mov     cs:WdLogGlobalForLineNumber, r12d
0x140023803  xor     r12d, r12d
0x140023806  mov     eax, r15d
0x140023809  lea     ecx, [r15-1]
0x14002380d  shr     eax, 8
0x140023810  lea     rdx, ?ROP2_NEED_DEST@@3PAHA; int near * ROP2_NEED_DEST
0x140023817  sub     eax, ebx
0x140023819  and     ecx, 0Fh
0x14002381c  and     eax, 0Fh
0x14002381f  mov     eax, [rdx+rax*4]
0x140023822  or      eax, [rdx+rcx*4]
0x140023825  jnz     loc_140023A79
0x14002382b  mov     eax, [rdi+80h]
0x140023831  test    bl, al
0x140023833  jz      loc_140023A79
0x140023839  xor     edx, edx; Val
0x14002383b  lea     rcx, [rbp+140h+pso]; void *
0x14002383f  lea     r8d, [rdx+40h]; Size
0x140023843  call    memset
0x140023848  mov     rax, [rdi]
0x14002384b  lea     r9, [rbp+140h+pso]
0x14002384f  mov     r8d, ebx
0x140023852  mov     [rbp+140h+var_100], r12
0x140023856  lea     rdx, [rbp+140h+var_F0]
0x14002385a  mov     rcx, rdi
0x14002385d  mov     rax, [rax+60h]
0x140023861  call    _guard_dispatch_icall
0x140023866  test    eax, eax
0x140023868  js      short loc_14002387B
0x14002386a  mov     rax, rdi
0x14002386d  lea     rcx, [rbp+140h+var_F0]
0x140023871  mov     [rbp+140h+var_100], rax
0x140023875  mov     [rbp+140h+var_F8], rcx
0x140023879  jmp     short loc_14002387F
0x14002387b  mov     rax, [rbp+140h+var_100]
0x14002387f  test    rax, rax
0x140023882  jnz     short loc_140023900
0x140023884  lea     ecx, [rax+4]
0x140023887  call    cs:__imp_WdLogSingleEntry0
0x14002388e  nop     dword ptr [rax+rax+00h]
0x140023893  mov     edi, 1946h
0x140023898  mov     cs:WdLogGlobalForLineNumber, edi
0x14002389e  call    cs:__imp_WdLogNewEntry5_WdEvent
0x1400238a5  nop     dword ptr [rax+rax+00h]
0x1400238aa  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400238b1  mov     [rax+18h], rcx
0x1400238b5  mov     ecx, cs:dword_14003E570
0x1400238bb  mov     [rax+20h], rcx
0x1400238bf  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400238c7  mov     rcx, [rbp+140h+var_100]
0x1400238cb  mov     cs:WdLogGlobalForLineNumber, edi
0x1400238d1  test    rcx, rcx
0x1400238d4  jz      short loc_1400238F2
0x1400238d6  mov     rax, [rcx]
0x1400238d9  lea     rdx, [rbp+140h+pso]
0x1400238dd  mov     rax, [rax+80h]
0x1400238e4  call    _guard_dispatch_icall
0x1400238e9  mov     rcx, [rbp+140h+var_100]; this
0x1400238ed  call    ?VidMemDirtyUpdate@CddBitmap@@QEAAXXZ; CddBitmap::VidMemDirtyUpdate(void)
0x1400238f2  lea     rcx, [rbp+140h+var_1C0]; this
0x1400238f6  call    ??1CDDBITMAPLOCK@@QEAA@XZ; CDDBITMAPLOCK::~CDDBITMAPLOCK(void)
0x1400238fb  jmp     loc_140023E2A
0x140023900  mov     rcx, [rbp+140h+pso]
0x140023904  lea     rdx, ?FillColorKeyCallback@@YAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z; int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)
0x14002390b  mov     rax, [rsp+240h+pco]
0x140023910  mov     [rbp+140h+var_E0], rax
0x140023914  lea     rax, [rbp+140h+var_F0]
0x140023918  mov     [rbp+140h+var_D8], rax
0x14002391c  lea     rax, [rbp+140h+var_F0]
0x140023920  mov     [rbp+140h+var_D0], rax
0x140023924  lea     rax, [rbp+140h+var_F0]
0x140023928  mov     [rbp+140h+var_C8], rax
0x14002392c  mov     [rbp+140h+var_B0], r12b
0x140023933  mov     [rbp+140h+var_98], r12
0x14002393a  mov     rax, [rcx+38h]
0x14002393e  mov     [rbp+140h+var_90], rax
0x140023945  mov     eax, [rcx+40h]
0x140023948  lea     rcx, [rbp+140h+var_E0]; struct CLIP_RECTS_DATA *
0x14002394c  mov     dword ptr [rbp+140h+var_88], eax
0x140023952  mov     dword ptr [rbp+140h+var_88+4], 0F1010203h
0x14002395c  mov     [rbp+140h+var_B8], r12
0x140023963  call    ?ClipDstRects@@YAJPEAUCLIP_RECTS_DATA@@P6AJ0IPEBUtagRECT@@@Z@Z; ClipDstRects(CLIP_RECTS_DATA *,long (*)(CLIP_RECTS_DATA *,uint,tagRECT const *))
0x140023968  mov     eax, [rbp+140h+flOptions]
0x14002396e  mov     r9, r14; pxo
0x140023971  mov     r8, [rsp+240h+pco]; pco
0x140023976  mov     rdx, r13; ppo
0x140023979  mov     rcx, [rbp+140h+pso]; pso
0x14002397d  mov     [rsp+240h+var_1F8], eax; flOptions
0x140023981  mov     rax, [rsp+240h+var_1E0]
0x140023986  mov     [rsp+240h+var_200], r15d; mixFill
0x14002398b  mov     [rsp+240h+var_208], rax; pptlBrushOrg
0x140023990  mov     rax, [rsp+240h+var_1D8]
0x140023995  mov     [rsp+240h+var_210], rax; pboFill
0x14002399a  mov     rax, [rsp+240h+var_1D0]
0x14002399f  mov     [rsp+240h+var_218], rax; plineattrs
0x1400239a4  mov     rax, [rsp+240h+var_1C8]
0x1400239a9  mov     [rsp+240h+var_220], rax; pboStroke
0x1400239ae  call    cs:__imp_EngStrokeAndFillPath
0x1400239b5  nop     dword ptr [rax+rax+00h]
0x1400239ba  mov     esi, eax
0x1400239bc  test    eax, eax
0x1400239be  jz      loc_140023A4B
0x1400239c4  mov     rcx, [rsp+240h+pco]
0x1400239c9  lea     rax, [rbp+140h+var_11C]
0x1400239cd  mov     [rbp+140h+var_E0], rcx
0x1400239d1  mov     rcx, [rbp+140h+pso]
0x1400239d5  mov     [rbp+140h+var_B0], r12b
0x1400239dc  mov     [rbp+140h+var_98], r12
0x1400239e3  mov     edx, [rcx+40h]
0x1400239e6  lea     rcx, [rbp+140h+var_E0]; struct CLIP_RECTS_DATA *
0x1400239ea  mov     [rbp+140h+var_D8], rax
0x1400239ee  lea     rax, [rbp+140h+var_F0]
0x1400239f2  mov     [rbp+140h+var_D0], rax
0x1400239f6  lea     rax, [rbp+140h+var_F0]
0x1400239fa  mov     [rbp+140h+var_C8], rax
0x1400239fe  mov     rax, [rbp+140h+var_128]
0x140023a02  mov     [rbp+140h+var_90], rax
0x140023a09  mov     eax, [rbp+140h+var_130]
0x140023a0c  mov     dword ptr [rbp+140h+var_80], eax
0x140023a12  mov     eax, [rdi+28h]
0x140023a15  mov     [rbp+140h+var_70], edx
0x140023a1b  lea     rdx, ?TransparentBltCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z; int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)
0x140023a22  mov     dword ptr [rbp+140h+var_80+4], eax
0x140023a28  mov     [rbp+140h+var_78], 0F1010203h
0x140023a32  mov     [rbp+140h+var_88], rdi
0x140023a39  mov     [rbp+140h+var_74], ebx
0x140023a3f  mov     [rbp+140h+var_B8], r12
0x140023a46  call    ?ClipDstRects@@YAJPEAUCLIP_RECTS_DATA@@P6AJ0IPEBUtagRECT@@@Z@Z; ClipDstRects(CLIP_RECTS_DATA *,long (*)(CLIP_RECTS_DATA *,uint,tagRECT const *))
0x140023a4b  mov     rcx, [rbp+140h+var_100]
0x140023a4f  test    rcx, rcx
0x140023a52  jz      loc_140023CD0
0x140023a58  mov     rax, [rcx]
0x140023a5b  lea     rdx, [rbp+140h+pso]
0x140023a5f  mov     rax, [rax+80h]
0x140023a66  call    _guard_dispatch_icall
0x140023a6b  mov     rcx, [rbp+140h+var_100]; this
0x140023a6f  call    ?VidMemDirtyUpdate@CddBitmap@@QEAAXXZ; CddBitmap::VidMemDirtyUpdate(void)
0x140023a74  jmp     loc_140023CD0
0x140023a79  mov     r14, [rsp+240h+pco]
0x140023a7e  lea     rcx, [rbp+140h+var_E0]; void *
0x140023a82  xor     edx, edx; Val
0x140023a84  lea     r8d, [rdx+40h]; Size
0x140023a88  call    memset
0x140023a8d  mov     rax, [rdi]
0x140023a90  lea     rcx, [rbp+140h+var_E0]
0x140023a94  mov     byte ptr [rsp+240h+var_200], bl
0x140023a98  lea     r8, [rbp+140h+var_F0]
0x140023a9c  mov     [rsp+240h+var_208], rcx
0x140023aa1  lea     rdx, [rbp+140h+var_F0]
0x140023aa5  lea     rcx, [rsp+240h+var_1F0]
0x140023aaa  mov     [rbp+140h+var_80], r12
0x140023ab1  mov     rax, [rax+38h]
0x140023ab5  mov     r9, r14
0x140023ab8  mov     [rsp+240h+var_210], rcx
0x140023abd  mov     rcx, rdi
0x140023ac0  mov     dword ptr [rsp+240h+var_218], ebx
0x140023ac4  mov     dword ptr [rsp+240h+var_220], ebx
  ... truncated ...
```
