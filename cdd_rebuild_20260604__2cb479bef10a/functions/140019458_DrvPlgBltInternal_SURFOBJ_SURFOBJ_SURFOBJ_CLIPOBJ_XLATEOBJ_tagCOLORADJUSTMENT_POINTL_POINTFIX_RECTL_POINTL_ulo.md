# DrvPlgBltInternal(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_POINTFIX *,_RECTL *,_POINTL *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))

- ea: `0x140019458`
- end: `0x14001a45b`
- name: `?DrvPlgBltInternal@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_POINTFIX@@PEAU_RECTL@@4KP6AH00012644PEAU_BRUSHOBJ@@4K@Z@Z`
- size: `4099`
- prototype: `__int64 __usercall@<rax>(struct _SURFOBJ *@<rcx>, struct _SURFOBJ *@<rdx>, struct _SURFOBJ *@<r8>, struct _CLIPOBJ *@<r9>, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _POINTFIX *, RECTL *, struct _POINTL *, unsigned int, int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))`
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x1400193e0`
- `0x1400255b0`

## callees

- `0x140001008`
- `0x140004600`
- `0x1400087ac`
- `0x140008da4`
- `0x14000be40`
- `0x14000bf90`
- `0x14000c0b0`
- `0x14000c33c`
- `0x14000c730`
- `0x14000c810`
- `0x14000cb44`
- `0x14000cec4`
- `0x14000ef80`
- `0x1400160c8`
- `0x140019458`
- `0x14001d458`
- `0x1400226b0`
- `0x1400248f8`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001978e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140019c03`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001978e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140019c03`
- `ntoskrnl!KeReleaseSemaphore` at `0x140019b5d`
- `ntoskrnl!KeReleaseSemaphore` at `0x140019d9d`
- `ntoskrnl!KeReleaseSemaphore` at `0x140019f6d`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001a1af`
- `ntoskrnl!KeReleaseSemaphore` at `0x140019b5d`
- `ntoskrnl!KeReleaseSemaphore` at `0x140019d9d`
- `ntoskrnl!KeReleaseSemaphore` at `0x140019f6d`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001a1af`
- `ntoskrnl!DbgPrint` at `0x140019e3c`
- `ntoskrnl!DbgPrint` at `0x140019e3c`
- `ntoskrnl!KdDebuggerEnabled` at `0x140019e29`
- `watchdog!WdLogSingleEntry2` at `0x14001a404`
- `watchdog!WdLogSingleEntry2` at `0x14001a404`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001a41b`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14001a41b`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400197d8`
- `watchdog!WdLogNewEntry5_WdError` at `0x140019a52`
- `watchdog!WdLogNewEntry5_WdError` at `0x140019c4b`
- `watchdog!WdLogNewEntry5_WdError` at `0x140019e63`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400197d8`
- `watchdog!WdLogNewEntry5_WdError` at `0x140019a52`
- `watchdog!WdLogNewEntry5_WdError` at `0x140019c4b`
- `watchdog!WdLogNewEntry5_WdError` at `0x140019e63`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400196a8`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400196a8`
- `watchdog!WdLogSingleEntry0` at `0x14001968f`
- `watchdog!WdLogSingleEntry0` at `0x1400197c1`
- `watchdog!WdLogSingleEntry0` at `0x14001980b`
- `watchdog!WdLogSingleEntry0` at `0x140019a3b`
- `watchdog!WdLogSingleEntry0` at `0x140019b75`
- `watchdog!WdLogSingleEntry0` at `0x140019c34`
- `watchdog!WdLogSingleEntry0` at `0x140019c7b`
- `watchdog!WdLogSingleEntry0` at `0x140019e4d`
- `watchdog!WdLogSingleEntry0` at `0x14001968f`
- `watchdog!WdLogSingleEntry0` at `0x1400197c1`
- `watchdog!WdLogSingleEntry0` at `0x14001980b`
- `watchdog!WdLogSingleEntry0` at `0x140019a3b`
- `watchdog!WdLogSingleEntry0` at `0x140019b75`
- `watchdog!WdLogSingleEntry0` at `0x140019c34`
- `watchdog!WdLogSingleEntry0` at `0x140019c7b`
- `watchdog!WdLogSingleEntry0` at `0x140019e4d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140019822`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140019c92`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140019822`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140019c92`
- `WIN32K!EngPlgBlt` at `0x14001a016`
- `WIN32K!EngPlgBlt` at `0x14001a3b8`
- `WIN32K!EngPlgBlt` at `0x14001a016`
- `WIN32K!EngPlgBlt` at `0x14001a3b8`
- `WIN32K!EngBitBlt` at `0x1400196db`
- `WIN32K!EngBitBlt` at `0x140019951`
- `WIN32K!EngReleaseSemaphore` at `0x14001a28c`
- `WIN32K!EngReleaseSemaphore` at `0x14001a2aa`
- `WIN32K!EngReleaseSemaphore` at `0x14001a28c`
- `WIN32K!EngReleaseSemaphore` at `0x14001a2aa`
- `WIN32K!EngAcquireSemaphore` at `0x14001a221`
- `WIN32K!EngAcquireSemaphore` at `0x14001a221`

## string_xrefs

- `0x140019e35`: `Ivalid pco in GDIBITMAPACCESS2::StartAccessDst`

## pseudocode

```c
__int64 __fastcall DrvPlgBltInternal(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _SURFOBJ *a3,
        struct _CLIPOBJ *a4,
        struct _XLATEOBJ *a5,
        struct tagCOLORADJUSTMENT *a6,
        struct _POINTL *a7,
        struct _POINTFIX *a8,
        RECTL *a9,
        struct _POINTL *a10,
        ULONG iMode,
        int (*a12)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))
{
  SURFOBJ *v13; // r13
  struct _POINTFIX v14; // r10
  POINTFIX v15; // r11
  int v16; // r9d
  DHPDEV dhpdev; // rdi
  int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // ebx
  int v22; // eax
  __int64 v23; // rdx
  int v24; // ecx
  int v25; // ecx
  USHORT iType; // ax
  USHORT v27; // cx
  _QWORD *v28; // rax
  DHSURF dhsurf; // r14
  DHSURF v30; // r12
  char v31; // cl
  _QWORD *v32; // rdi
  NTSTATUS v33; // ecx
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  DHSURF v36; // rdi
  RECTL *v37; // rdi
  SURFOBJ *v38; // r12
  CStagingPool *v39; // r12
  _QWORD *v40; // rax
  DHSURF v41; // rdi
  __int64 v42; // rcx
  struct _KTHREAD *v43; // rdx
  int v44; // edi
  BOOL v45; // r15d
  char v46; // cl
  void *v47; // r13
  _QWORD *v48; // r13
  NTSTATUS v49; // eax
  _QWORD *v50; // rax
  _QWORD *v51; // rax
  __int64 v52; // rcx
  struct _KTHREAD *v53; // rdx
  _QWORD *v54; // rax
  __int64 v55; // rcx
  struct _KTHREAD *v56; // rdx
  int v57; // r8d
  BOOL v58; // eax
  unsigned int v59; // r12d
  LONG lDelta; // ecx
  int v61; // eax
  DHSURF v62; // rdi
  __int64 v63; // rcx
  struct _KTHREAD *v64; // rdx
  HSEMAPHORE v66; // rsi
  int v67; // ecx
  int v68; // ecx
  BOOL v69; // eax
  _QWORD *v70; // rax
  int prcl; // [rsp+40h] [rbp-C0h]
  int v72[2]; // [rsp+60h] [rbp-A0h] BYREF
  CLIPOBJ *pco; // [rsp+68h] [rbp-98h] BYREF
  RECTL *v74; // [rsp+70h] [rbp-90h]
  SURFOBJ *v75; // [rsp+78h] [rbp-88h] BYREF
  XLATEOBJ *pxlo; // [rsp+80h] [rbp-80h]
  SURFOBJ *psoMsk; // [rsp+88h] [rbp-78h]
  _QWORD v78[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _POINTFIX v79; // [rsp+A0h] [rbp-60h]
  int v80; // [rsp+A8h] [rbp-58h]
  int v81; // [rsp+ACh] [rbp-54h]
  POINTL *pptl; // [rsp+B0h] [rbp-50h]
  POINTFIX *pptfx; // [rsp+B8h] [rbp-48h]
  POINTL *pptlBrushOrg; // [rsp+C0h] [rbp-40h]
  COLORADJUSTMENT *pca; // [rsp+C8h] [rbp-38h]
  SURFOBJ *v86; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v87; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v88; // [rsp+E8h] [rbp-18h]
  __int128 v89; // [rsp+F8h] [rbp-8h]
  __int64 v90; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v91; // [rsp+110h] [rbp+10h]
  __int64 v92; // [rsp+118h] [rbp+18h]
  int v93; // [rsp+120h] [rbp+20h]
  CLIPOBJ *v94; // [rsp+130h] [rbp+30h] BYREF
  struct _RECTL *v95; // [rsp+138h] [rbp+38h]
  struct _RECTL *v96; // [rsp+140h] [rbp+40h]
  struct _RECTL *v97; // [rsp+148h] [rbp+48h]
  __int64 v98; // [rsp+158h] [rbp+58h]
  char v99; // [rsp+160h] [rbp+60h]
  __int64 v100; // [rsp+178h] [rbp+78h]
  PVOID pvScan0; // [rsp+180h] [rbp+80h]
  DHSURF v102; // [rsp+188h] [rbp+88h]
  int v103; // [rsp+190h] [rbp+90h]
  int v104; // [rsp+194h] [rbp+94h]
  int v105; // [rsp+198h] [rbp+98h]
  int v106; // [rsp+19Ch] [rbp+9Ch]
  LONG v107; // [rsp+1A0h] [rbp+A0h]
  _QWORD v108[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  CStagingPool *v109[2]; // [rsp+1F0h] [rbp+F0h]
  struct _RECTL v110; // [rsp+200h] [rbp+100h] BYREF
  SURFOBJ *psoSrc[8]; // [rsp+210h] [rbp+110h] BYREF
  SURFOBJ *psoTrg[2]; // [rsp+250h] [rbp+150h] BYREF
  int v113; // [rsp+260h] [rbp+160h]
  void *v114; // [rsp+268h] [rbp+168h]
  char v115; // [rsp+274h] [rbp+174h] BYREF
  struct CDDPDEV *v116; // [rsp+290h] [rbp+190h]
  void *v117; // [rsp+298h] [rbp+198h]
  DHSURF v118; // [rsp+2A0h] [rbp+1A0h]
  DHSURF v119; // [rsp+2A8h] [rbp+1A8h]
  struct _RECTL *v120; // [rsp+2B0h] [rbp+1B0h]
  __int64 v121; // [rsp+2B8h] [rbp+1B8h] BYREF
  int v122; // [rsp+2C0h] [rbp+1C0h]
  __int64 v123; // [rsp+2C8h] [rbp+1C8h]
  char v124; // [rsp+2D0h] [rbp+1D0h]

  v13 = a1;
  pxlo = a5;
  pca = a6;
  pptlBrushOrg = a7;
  v86 = a2;
  pptl = a10;
  pptfx = a8;
  pco = a4;
  v14 = a8[1];
  v15 = *a8;
  v16 = a8[1].y + a8[2].y - a8->y;
  dhpdev = a1->dhpdev;
  v79 = a8[2];
  psoMsk = a3;
  v78[0] = v15;
  v78[1] = v14;
  v80 = v79.x + v14.x - v15.x;
  v81 = v16;
  v75 = a1;
  v74 = a9;
  *(_QWORD *)v72 = a12;
  v18 = (v14.x > v15.x) ^ (v14.x <= v80);
  v19 = (v14.y <= v16) ^ (unsigned int)(v14.y > v15.y);
  if ( SLODWORD(v78[v18]) > SLODWORD(v78[v18 ^ 3LL]) )
    v18 ^= 3u;
  if ( SHIDWORD(v78[v19]) > SHIDWORD(v78[(unsigned int)v19 ^ 3LL]) )
    v19 = (unsigned int)v19 ^ 3;
  v20 = v18;
  v87 = 0;
  v21 = 1;
  v92 = 0;
  v88 = 0;
  v110.left = SLODWORD(v78[v20]) >> 4;
  v110.top = SHIDWORD(v78[v19]) >> 4;
  v22 = LODWORD(v78[v20 ^ 3]) + 15;
  v93 = 1;
  v110.right = v22 >> 4;
  v110.bottom = (HIDWORD(v78[v19 ^ 3]) + 15) >> 4;
  v89 = 0;
  if ( (*((unsigned int (**)(void))dhpdev + 10))() )
  {
    v24 = a9->right - a9->left;
    v87 = 0;
    v88 = 0;
    v89 = 0;
    LODWORD(v87) = a2->iType;
    DWORD1(v87) = v13->iType;
    DWORD2(v87) = v24;
    v25 = a9->bottom - a9->top;
    LODWORD(v88) = v110.right - v110.left;
    HIDWORD(v87) = v25;
    DWORD1(v88) = v110.bottom - v110.top;
    CDDETWPROFILER::Init((CDDETWPROFILER *)&v90, (struct CDDPDEV *)dhpdev, 0xBD5u, (struct _DXGKETW_PARAMS *)&v87, 0);
  }
  iType = a2->iType;
  if ( iType == 1 || (v27 = v13->iType, v27 == 1) )
  {
    v66 = (HSEMAPHORE)*((_QWORD *)dhpdev + 365);
    v67 = 0;
    v59 = 0;
    v72[0] = 0;
    if ( v66 )
    {
      EngAcquireSemaphore(v66);
      v67 = 1;
      v72[0] = 1;
    }
    if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
    {
      if ( v66 && v67 )
        EngReleaseSemaphore(v66);
      v68 = 1;
    }
    else
    {
      CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 56LL) = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
      v68 = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) != 0;
      LODWORD(v74) = v68;
      if ( v66 && v72[0] )
      {
        EngReleaseSemaphore(v66);
        v68 = (int)v74;
      }
    }
    if ( v68 )
    {
      if ( v13->iType == 3 || a2 && a2->iType == 3 )
      {
        WdLogSingleEntry2(3, a2, v13);
        WdLogGlobalForLineNumber = 581;
        v70 = (_QWORD *)WdLogNewEntry5_WdWarning();
        v70[3] = gCddImageInfo;
        v70[4] = (unsigned int)dword_14003E570;
        v70[5] = 215857758;
        WdLogGlobalForLineNumber = 581;
        goto LABEL_131;
      }
      ReadFromFrameBuffer((struct CDDPDEV *)dhpdev, v110.left, v110.top, v110.right, v110.bottom);
      v72[0] = 0;
      CDDMULTISURFLOCK::vInit((CDDMULTISURFLOCK *)psoSrc, (struct CDDPDEV *)dhpdev, &v75, &v86, &v110, a9, v72, pco);
      if ( bIgnoreDeviceSurfaceUpdates(v13, &pco) )
      {
        CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)psoSrc);
        goto LABEL_131;
      }
      v69 = EngPlgBlt(v75, v86, psoMsk, pco, pxlo, pca, pptlBrushOrg, pptfx, a9, pptl, iMode);
      v59 = v69;
      if ( pco && v69 && v72[0] == 1 )
        vGDIDirtyUpdate((struct CDDPDEV *)dhpdev, (struct tagRECT *)&v110, pco);
      CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)psoSrc);
    }
    goto LABEL_106;
  }
  if ( iType != 3 && v27 != 3 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 561;
    v28 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v28[3] = gCddImageInfo;
    v28[4] = (unsigned int)dword_14003E570;
    v28[5] = 215857758;
    WdLogGlobalForLineNumber = 561;
  }
  dhsurf = v13->dhsurf;
  if ( a12 == EngBitBlt )
    v30 = a2->dhsurf;
  else
    v30 = 0;
  if ( dhsurf )
  {
    dhpdev = (DHPDEV)*((_QWORD *)dhsurf + 1);
  }
  else if ( v30 )
  {
    dhpdev = (DHPDEV)*((_QWORD *)v30 + 1);
  }
  CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(
    (CDDMULTIBITMAPLOCK *)v78,
    (struct CddBitmap *)v13->dhsurf,
    (struct CddBitmap *)v30);
  GDIBITMAPACCESS2::GDIBITMAPACCESS2(
    (GDIBITMAPACCESS2 *)psoSrc,
    (struct CDDPDEV *)dhpdev,
    (struct CddBitmap *)v30,
    (struct CddBitmap *)dhsurf);
  memset(v108, 0, sizeof(v108));
  *(_OWORD *)v109 = 0;
  if ( v30 )
  {
    v31 = v124;
    if ( v124 )
    {
      v32 = (_QWORD *)*((_QWORD *)v116 + 895);
      if ( (struct _KTHREAD *)v32[4] != KeGetCurrentThread() )
      {
        v33 = KeWaitForSingleObject(v32, Executive, 0, 0, 0);
        if ( v33 != 258 )
        {
          v32[4] = KeGetCurrentThread();
          if ( v33 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 618;
            v34 = (_QWORD *)WdLogNewEntry5_WdError();
            v34[3] = gCddImageInfo;
            v34[4] = (unsigned int)dword_14003E570;
            v34[5] = 215857758;
            WdLogGlobalForLineNumber = 618;
            goto LABEL_25;
          }
        }
      }
      v31 = v124;
    }
    v37 = v74;
    if ( (*(int (__fastcall **)(DHSURF, RECTL *, RECTL *, _QWORD, int, int, __int64 *, SURFOBJ **, bool))(*(_QWORD *)v30 + 56LL))(
           v30,
           v74,
           v74,
           0,
           1,
           1,
           &v121,
           psoSrc,
           v31 == 0) < 0 )
    {
LABEL_25:
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 6959;
      v35 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v35[3] = gCddImageInfo;
      v35[4] = (unsigned int)dword_14003E570;
      v35[5] = 215857758;
      WdLogGlobalForLineNumber = 6959;
      if ( v109[0] )
      {
        *(CStagingPool **)(v108[0] + 16LL) = v109[1];
        CStagingPool::ReleaseGdiSurface(v109[0], (struct CDDBITMAP_GDIDESC *)v108);
      }
      if ( v118 )
        (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v118 + 128LL))(v118, psoSrc);
      v36 = v119;
      if ( !v119 )
        goto LABEL_73;
      if ( v122 )
      {
LABEL_72:
        (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v36 + 128LL))(v36, psoTrg);
LABEL_73:
        v52 = *((_QWORD *)v116 + 895);
        v53 = *(struct _KTHREAD **)(v52 + 32);
        if ( v53 == KeGetCurrentThread() )
        {
          if ( v53 )
          {
            *(_QWORD *)(v52 + 32) = 0;
            KeReleaseSemaphore((PRKSEMAPHORE)v52, 0, 1, 0);
          }
        }
LABEL_76:
        CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v78);
LABEL_131:
        CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v90);
        return v21;
      }
LABEL_71:
      (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, void *, __int64))(*(_QWORD *)v119 + 64LL))(
        v119,
        psoTrg,
        v120,
        v117,
        v123);
      goto LABEL_72;
    }
    v118 = v30;
    v38 = psoSrc[0];
    v117 = 0;
    goto LABEL_54;
  }
  if ( *(BOOL (__stdcall **)(SURFOBJ *, SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *, POINTL *, BRUSHOBJ *, POINTL *, ROP4))v72 == EngBitBlt )
  {
    v37 = v74;
  }
  else
  {
    v39 = (CStagingPool *)(dhpdev + 1376);
    v37 = v74;
    if ( (int)CStagingPool::GetGdiSurface(
                v39,
                a2->sizlBitmap.cx,
                a2->sizlBitmap.cy,
                (const struct tagRECT *)v74,
                (struct CDDBITMAP_GDIDESC *)v108,
                1u) < 0 )
    {
      WdLogSingleEntry0(4);
      v44 = 6968;
      goto LABEL_65;
    }
    v109[0] = v39;
    v109[1] = *(CStagingPool **)(v108[0] + 16LL);
    *(_QWORD *)(v108[0] + 16LL) = 0;
    v38 = (SURFOBJ *)v108[0];
    if ( (unsigned __int64)(*(int *)(v108[0] + 64LL) * (__int64)(v37->top + 1) + 0x80000000LL) <= 0xFFFFFFFF )
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD, struct _SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, RECTL *, RECTL *, _QWORD, _QWORD, _QWORD, int))v72)(
              v108[0],
              a2,
              0,
              0,
              pxlo,
              v37,
              v37,
              0,
              0,
              0,
              52428) )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 6986;
        v40 = (_QWORD *)WdLogNewEntry5_WdError();
        v40[3] = gCddImageInfo;
        v40[4] = (unsigned int)dword_14003E570;
        v40[5] = 215857758;
        WdLogGlobalForLineNumber = 6986;
        if ( v109[0] )
        {
          *(CStagingPool **)(v108[0] + 16LL) = v109[1];
          CStagingPool::ReleaseGdiSurface(v109[0], (struct CDDBITMAP_GDIDESC *)v108);
        }
        if ( v118 )
          (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v118 + 128LL))(v118, psoSrc);
        v41 = v119;
        if ( v119 )
        {
          if ( !v122 )
            (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, void *, __int64))(*(_QWORD *)v119 + 64LL))(
              v119,
              psoTrg,
              v120,
              v117,
              v123);
          (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v41 + 128LL))(v41, psoTrg);
        }
        v42 = *((_QWORD *)v116 + 895);
        v43 = *(struct _KTHREAD **)(v42 + 32);
        if ( v43 == KeGetCurrentThread() && v43 )
        {
          *(_QWORD *)(v42 + 32) = 0;
          KeReleaseSemaphore((PRKSEMAPHORE)v42, 0, 1, 0);
        }
        v21 = 0;
        goto LABEL_76;
      }
      goto LABEL_54;
    }
  }
  v38 = a2;
LABEL_54:
  if ( dhsurf )
  {
    v45 = ((_DWORD)dhsurf[32] & 1) != 0 && !psoMsk;
    v46 = v124;
    v47 = pco;
    v75 = (SURFOBJ *)pco;
    if ( v124 )
    {
      v48 = (_QWORD *)*((_QWORD *)v116 + 895);
      if ( (struct _KTHREAD *)v48[4] != KeGetCurrentThread() )
      {
        v49 = KeWaitForSingleObject(v48, Executive, 0, 0, 0);
        if ( v49 != 258 )
        {
          v48[4] = KeGetCurrentThread();
          if ( v49 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 659;
            v50 = (_QWORD *)WdLogNewEntry5_WdError();
            v50[3] = gCddImageInfo;
            v50[4] = (unsigned int)dword_14003E570;
            v50[5] = 215857758;
            WdLogGlobalForLineNumber = 659;
LABEL_64:
            WdLogSingleEntry0(4);
            v44 = 7004;
LABEL_65:
            WdLogGlobalForLineNumber = v44;
            v51 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v51[3] = gCddImageInfo;
            v51[4] = (unsigned int)dword_14003E570;
            v51[5] = 215857758;
            WdLogGlobalForLineNumber = v44;
            if ( v109[0] )
            {
              *(CStagingPool **)(v108[0] + 16LL) = v109[1];
              CStagingPool::ReleaseGdiSurface(v109[0], (struct CDDBITMAP_GDIDESC *)v108);
            }
            if ( v118 )
              (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v118 + 128LL))(v118, psoSrc);
            v36 = v119;
            if ( !v119 )
              goto LABEL_73;
            if ( v122 )
              goto LABEL_72;
            goto LABEL_71;
          }
        }
      }
      v46 = v124;
      v47 = v75;
    }
    LOBYTE(prcl) = v46 == 0;
    if ( (*(int (__fastcall **)(DHSURF, struct _RECTL *, struct _RECTL *, void *, int, bool, char *, SURFOBJ **, int))(*(_QWORD *)dhsurf + 56LL))(
           dhsurf,
           &v110,
           &v110,
           v47,
           1,
           !v45,
           (char *)&v121 + 4,
           psoTrg,
           prcl) < 0 )
      goto LABEL_64;
    if ( v117 && v47 != v117 && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Ivalid pco in GDIBITMAPACCESS2::StartAccessDst");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 670;
      v54 = (_QWORD *)WdLogNewEntry5_WdError();
      v54[3] = gCddImageInfo;
      v54[4] = (unsigned int)dword_14003E570;
      v54[5] = 215857758;
      WdLogGlobalForLineNumber = 670;
      __debugbreak();
    }
    v117 = v47;
    v13 = psoTrg[0];
    v120 = &v110;
    v119 = dhsurf;
    v123 = 0;
    if ( v45 )
    {
      v94 = pco;
      v99 = 0;
      v95 = &v110;
      v96 = &v110;
      v97 = &v110;
      v100 = 0;
      pvScan0 = psoTrg[0]->pvScan0;
      LODWORD(v102) = psoTrg[0]->lDelta;
      HIDWORD(v102) = -251592189;
      v98 = 0;
      ClipDstRects(
        (struct CLIP_RECTS_DATA *)&v94,
        (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))FillColorKeyCallback);
    }
  }
  else
  {
    v45 = 0;
  }
  v55 = *((_QWORD *)v116 + 895);
  v56 = *(struct _KTHREAD **)(v55 + 32);
  if ( v56 == KeGetCurrentThread() && v56 )
  {
    *(_QWORD *)(v55 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v55, 0, 1, 0);
  }
  v57 = HIDWORD(v121);
  if ( v121 )
  {
    CDDPDEV::Flush(v116);
    v57 = HIDWORD(v121);
  }
  WaitForStartGdiAccessToFinish(v116, (struct CDDBITMAP_GDIDESC *)psoTrg, v57);
  WaitForStartGdiAccessToFinish(v116, (struct CDDBITMAP_GDIDESC *)psoSrc, v121);
  v58 = EngPlgBlt(v13, v38, psoMsk, pco, pxlo, pca, pptlBrushOrg, pptfx, v37, pptl, iMode);
  v59 = v58;
  if ( v45 && v58 )
  {
    v95 = (struct _RECTL *)&v115;
    v94 = pco;
    lDelta = v13->lDelta;
    v96 = &v110;
    v97 = &v110;
    pvScan0 = v114;
    v103 = v113;
    v61 = *((_DWORD *)dhsurf + 10);
    v107 = lDelta;
    v104 = v61;
    v99 = 0;
    v100 = 0;
    v105 = -251592189;
    v102 = dhsurf;
    v106 = 1;
    v98 = 0;
    ClipDstRects(
      (struct CLIP_RECTS_DATA *)&v94,
      (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::TransparentBltCallback);
    v122 = 1;
    CddBitmap::VidMemDirtyUpdate((CddBitmap *)dhsurf);
  }
  if ( v109[0] )
  {
    *(CStagingPool **)(v108[0] + 16LL) = v109[1];
    CStagingPool::ReleaseGdiSurface(v109[0], (struct CDDBITMAP_GDIDESC *)v108);
  }
  if ( v118 )
    (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v118 + 128LL))(v118, psoSrc);
  v62 = v119;
  if ( v119 )
  {
    if ( !v122 )
      (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, void *, __int64))(*(_QWORD *)v119 + 64LL))(
        v119,
        psoTrg,
        v120,
        v117,
        v123);
    (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v62 + 128LL))(v62, psoTrg);
  }
  v63 = *((_QWORD *)v116 + 895);
  v64 = *(struct _KTHREAD **)(v63 + 32);
  if ( v64 == KeGetCurrentThread() && v64 )
  {
    *(_QWORD *)(v63 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v63, 0, 1, 0);
  }
  CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v78);
LABEL_106:
  if ( !v93 )
  {
    LOBYTE(v23) = 2;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(v90 + 264))(v91, v23, v92);
  }
  return v59;
}

```

## disassembly

```asm
0x140019458  push    rbp
0x14001945a  push    rbx
0x14001945b  push    rsi
0x14001945c  push    rdi
0x14001945d  push    r12
0x14001945f  push    r13
0x140019461  push    r14
0x140019463  push    r15
0x140019465  lea     rbp, [rsp-208h]
0x14001946d  sub     rsp, 308h
0x140019474  mov     rax, cs:__security_cookie
0x14001947b  xor     rax, rsp
0x14001947e  mov     [rbp+240h+var_50], rax
0x140019485  mov     rax, [rbp+240h+arg_20]
0x14001948c  mov     r15, rdx
0x14001948f  mov     r14, [rbp+240h+arg_40]
0x140019496  mov     r13, rcx
0x140019499  mov     r12, [rbp+240h+arg_58]
0x1400194a0  mov     [rbp+240h+pxlo], rax
0x1400194a4  mov     rax, [rbp+240h+arg_28]
0x1400194ab  mov     [rbp+240h+var_278], rax
0x1400194af  mov     rax, [rbp+240h+arg_30]
0x1400194b6  mov     [rbp+240h+var_280], rax
0x1400194ba  mov     rax, [rbp+240h+arg_48]
0x1400194c1  mov     [rbp+240h+var_270], rdx
0x1400194c5  mov     rdx, [rbp+240h+arg_38]
0x1400194cc  mov     [rbp+240h+var_290], rax
0x1400194d0  mov     [rbp+240h+var_288], rdx
0x1400194d4  mov     [rsp+340h+pco], r9
0x1400194d9  mov     r10, [rdx+8]
0x1400194dd  mov     r11, [rdx]
0x1400194e0  mov     rax, [rdx+10h]
0x1400194e4  mov     r9d, [rdx+14h]
0x1400194e8  sub     r9d, [rdx+4]
0x1400194ec  add     r9d, [rdx+0Ch]
0x1400194f0  xor     edx, edx
0x1400194f2  mov     rdi, [rcx+10h]
0x1400194f6  mov     [rbp+240h+var_2A0], rax
0x1400194fa  mov     [rbp+240h+psoMsk], r8
0x1400194fe  mov     r8d, r10d
0x140019501  sub     r8d, r11d
0x140019504  mov     [rbp+240h+var_2B0], r11
0x140019508  add     r8d, eax
0x14001950b  mov     [rbp+240h+var_2A8], r10
0x14001950f  cmp     r10d, r11d
0x140019512  mov     [rbp+240h+var_298], r8d
0x140019516  mov     [rbp+240h+var_294], r9d
0x14001951a  setnle  dl
0x14001951d  mov     [rsp+340h+var_2C8], rcx
0x140019522  xor     ebx, ebx
0x140019524  mov     [rsp+340h+var_2D0], r14
0x140019529  cmp     r10d, r8d
0x14001952c  mov     qword ptr [rsp+340h+var_2E0], r12
0x140019531  mov     r8d, 3
0x140019537  setle   bl
0x14001953a  shr     r10, 20h
0x14001953e  xor     ebx, edx
0x140019540  shr     r11, 20h
0x140019544  xor     edx, edx
0x140019546  movsxd  rcx, ebx
0x140019549  cmp     r10d, r11d
0x14001954c  setnle  dl
0x14001954f  xor     eax, eax
0x140019551  cmp     r10d, r9d
0x140019554  setle   al
0x140019557  xor     edx, eax
0x140019559  mov     rax, rcx
0x14001955c  xor     rax, r8
0x14001955f  mov     eax, dword ptr [rbp+rax*8+240h+var_2B0]
0x140019563  cmp     dword ptr [rbp+rcx*8+240h+var_2B0], eax
0x140019567  jle     short loc_14001956C
0x140019569  xor     ebx, r8d
0x14001956c  mov     eax, edx
0x14001956e  xor     rax, r8
0x140019571  mov     eax, dword ptr [rbp+rax*8+240h+var_2B0+4]
0x140019575  cmp     dword ptr [rbp+rdx*8+240h+var_2B0+4], eax
0x140019579  jle     short loc_14001957E
0x14001957b  xor     edx, r8d
0x14001957e  xorps   xmm0, xmm0
0x140019581  movsxd  rcx, ebx
0x140019584  movups  [rbp+240h+var_268], xmm0
0x140019588  mov     ebx, 1
0x14001958d  mov     [rbp+240h+var_228], 0
0x140019595  movups  [rbp+240h+var_258], xmm0
0x140019599  mov     eax, dword ptr [rbp+rcx*8+240h+var_2B0]
0x14001959d  xor     rcx, r8
0x1400195a0  sar     eax, 4
0x1400195a3  mov     [rbp+240h+var_140.left], eax
0x1400195a9  mov     eax, dword ptr [rbp+rdx*8+240h+var_2B0+4]
0x1400195ad  xor     rdx, r8
0x1400195b0  sar     eax, 4
0x1400195b3  mov     [rbp+240h+var_140.top], eax
0x1400195b9  mov     eax, dword ptr [rbp+rcx*8+240h+var_2B0]
0x1400195bd  add     eax, 0Fh
0x1400195c0  mov     [rbp+240h+var_220], ebx
0x1400195c3  sar     eax, 4
0x1400195c6  mov     [rbp+240h+var_140.right], eax
0x1400195cc  mov     eax, dword ptr [rbp+rdx*8+240h+var_2B0+4]
0x1400195d0  add     eax, 0Fh
0x1400195d3  sar     eax, 4
0x1400195d6  mov     [rbp+240h+var_140.bottom], eax
0x1400195dc  movups  [rbp+240h+var_248], xmm0
0x1400195e0  mov     rax, [rdi+50h]
0x1400195e4  call    _guard_dispatch_icall
0x1400195e9  test    eax, eax
0x1400195eb  jz      short loc_14001965A
0x1400195ed  mov     ecx, [r14+8]
0x1400195f1  lea     r9, [rbp+240h+var_268]; struct _DXGKETW_PARAMS *
0x1400195f5  sub     ecx, [r14]
0x1400195f8  xorps   xmm0, xmm0
0x1400195fb  movups  [rbp+240h+var_268], xmm0
0x1400195ff  mov     r8d, 0BD5h; unsigned int
0x140019605  mov     rdx, rdi; struct CDDPDEV *
0x140019608  movups  [rbp+240h+var_258], xmm0
0x14001960c  mov     byte ptr [rsp+340h+Timeout], 0; bool
0x140019611  movups  [rbp+240h+var_248], xmm0
0x140019615  movzx   eax, word ptr [r15+4Ch]
0x14001961a  mov     dword ptr [rbp+240h+var_268], eax
0x14001961d  movzx   eax, word ptr [r13+4Ch]
0x140019622  mov     dword ptr [rbp+240h+var_268+4], eax
0x140019625  mov     eax, [rbp+240h+var_140.right]
0x14001962b  sub     eax, [rbp+240h+var_140.left]
0x140019631  mov     dword ptr [rbp+240h+var_268+8], ecx
0x140019634  mov     ecx, [r14+0Ch]
0x140019638  sub     ecx, [r14+4]
0x14001963c  mov     dword ptr [rbp+240h+var_258], eax
0x14001963f  mov     eax, [rbp+240h+var_140.bottom]
0x140019645  sub     eax, [rbp+240h+var_140.top]
0x14001964b  mov     dword ptr [rbp+240h+var_268+0Ch], ecx
0x14001964e  lea     rcx, [rbp+240h+var_238]; this
0x140019652  mov     dword ptr [rbp+240h+var_258+4], eax
0x140019655  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x14001965a  movzx   eax, word ptr [r15+4Ch]
0x14001965f  cmp     ax, bx
0x140019662  jz      loc_14001A209
0x140019668  movzx   ecx, word ptr [r13+4Ch]
0x14001966d  cmp     cx, bx
0x140019670  jz      loc_14001A209
0x140019676  mov     r9d, 3
0x14001967c  mov     esi, 0CDDBA5Eh
0x140019681  cmp     ax, r9w
0x140019685  jz      short loc_1400196D7
0x140019687  cmp     cx, r9w
0x14001968b  jz      short loc_1400196D7
0x14001968d  mov     ecx, ebx
0x14001968f  call    cs:__imp_WdLogSingleEntry0
0x140019696  nop     dword ptr [rax+rax+00h]
0x14001969b  mov     r14d, 231h
0x1400196a1  mov     cs:WdLogGlobalForLineNumber, r14d
0x1400196a8  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400196af  nop     dword ptr [rax+rax+00h]
0x1400196b4  mov     rcx, rax
0x1400196b7  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400196be  mov     [rcx+18h], rax
0x1400196c2  mov     eax, cs:dword_14003E570
0x1400196c8  mov     [rcx+20h], rax
0x1400196cc  mov     [rcx+28h], rsi
0x1400196d0  mov     cs:WdLogGlobalForLineNumber, r14d
0x1400196d7  mov     r14, [r13+0]
0x1400196db  cmp     r12, cs:__imp_EngBitBlt
0x1400196e2  jnz     short loc_1400196E9
0x1400196e4  mov     r12, [r15]
0x1400196e7  jmp     short loc_1400196EC
0x1400196e9  xor     r12d, r12d
0x1400196ec  test    r14, r14
0x1400196ef  jz      short loc_1400196F7
0x1400196f1  mov     rdi, [r14+8]
0x1400196f5  jmp     short loc_140019701
0x1400196f7  test    r12, r12
0x1400196fa  jz      short loc_140019701
0x1400196fc  mov     rdi, [r12+8]
0x140019701  mov     r8, r12; struct CddBitmap *
0x140019704  lea     rcx, [rbp+240h+var_2B0]; this
0x140019708  mov     rdx, r14; struct CddBitmap *
0x14001970b  call    ??0CDDMULTIBITMAPLOCK@@QEAA@PEAVCddBitmap@@0@Z; CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(CddBitmap *,CddBitmap *)
0x140019710  mov     r9, r14; struct CddBitmap *
0x140019713  lea     rcx, [rbp+240h+psoSrc]; this
0x14001971a  mov     r8, r12; struct CddBitmap *
0x14001971d  mov     rdx, rdi; struct CDDPDEV *
0x140019720  call    ??0GDIBITMAPACCESS2@@QEAA@PEAUCDDPDEV@@PEAVCddBitmap@@1@Z; GDIBITMAPACCESS2::GDIBITMAPACCESS2(CDDPDEV *,CddBitmap *,CddBitmap *)
0x140019725  xor     edx, edx; Val
0x140019727  lea     rcx, [rbp+240h+var_190]; void *
0x14001972e  lea     r8d, [rdx+40h]; Size
0x140019732  call    memset
0x140019737  xorps   xmm0, xmm0
0x14001973a  movdqa  xmmword ptr [rbp+240h+var_150], xmm0
0x140019742  test    r12, r12
0x140019745  jz      loc_14001994C
0x14001974b  mov     cl, [rbp+240h+var_70]
0x140019751  test    cl, cl
0x140019753  jz      loc_1400198DF
0x140019759  mov     rax, [rbp+240h+var_B0]
0x140019760  mov     rdi, [rax+1BF8h]
0x140019767  mov     rax, gs:188h
0x140019770  cmp     [rdi+20h], rax
0x140019774  jz      loc_1400198D9
0x14001977a  xor     r9d, r9d; Alertable
0x14001977d  mov     [rsp+340h+Timeout], 0; Timeout
0x140019786  xor     r8d, r8d; WaitMode
0x140019789  xor     edx, edx; WaitReason
0x14001978b  mov     rcx, rdi; Object
0x14001978e  call    cs:__imp_KeWaitForSingleObject
0x140019795  nop     dword ptr [rax+rax+00h]
0x14001979a  mov     ecx, eax
0x14001979c  cmp     eax, 102h
0x1400197a1  jz      loc_1400198D9
0x1400197a7  mov     rax, gs:188h
0x1400197b0  mov     [rdi+20h], rax
0x1400197b4  test    ecx, ecx
0x1400197b6  jns     loc_1400198D9
0x1400197bc  mov     ecx, 2
0x1400197c1  call    cs:__imp_WdLogSingleEntry0
0x1400197c8  nop     dword ptr [rax+rax+00h]
0x1400197cd  mov     edi, 26Ah
0x1400197d2  mov     cs:WdLogGlobalForLineNumber, edi
0x1400197d8  call    cs:__imp_WdLogNewEntry5_WdError
0x1400197df  nop     dword ptr [rax+rax+00h]
0x1400197e4  mov     rcx, rax
0x1400197e7  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400197ee  mov     [rcx+18h], rax
0x1400197f2  mov     eax, cs:dword_14003E570
0x1400197f8  mov     [rcx+20h], rax
0x1400197fc  mov     [rcx+28h], rsi
0x140019800  mov     cs:WdLogGlobalForLineNumber, edi
0x140019806  mov     ecx, 4
0x14001980b  call    cs:__imp_WdLogSingleEntry0
0x140019812  nop     dword ptr [rax+rax+00h]
0x140019817  mov     edi, 1B2Fh
0x14001981c  mov     cs:WdLogGlobalForLineNumber, edi
0x140019822  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140019829  nop     dword ptr [rax+rax+00h]
0x14001982e  mov     rcx, rax
0x140019831  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140019838  mov     [rcx+18h], rax
0x14001983c  mov     eax, cs:dword_14003E570
0x140019842  mov     [rcx+20h], rax
0x140019846  mov     [rcx+28h], rsi
0x14001984a  xor     esi, esi
0x14001984c  mov     cs:WdLogGlobalForLineNumber, edi
0x140019852  cmp     [rbp+240h+var_150], rsi
0x140019859  jz      short loc_140019880
0x14001985b  mov     rcx, [rbp+240h+var_190]
0x140019862  lea     rdx, [rbp+240h+var_190]; struct CDDBITMAP_GDIDESC *
0x140019869  mov     rax, [rbp+240h+var_150+8]
0x140019870  mov     [rcx+10h], rax
0x140019874  mov     rcx, [rbp+240h+var_150]; this
0x14001987b  call    ?ReleaseGdiSurface@CStagingPool@@QEAAXPEAUCDDBITMAP_GDIDESC@@@Z; CStagingPool::ReleaseGdiSurface(CDDBITMAP_GDIDESC *)
0x140019880  mov     rcx, [rbp+240h+var_A0]
0x140019887  test    rcx, rcx
0x14001988a  jz      short loc_1400198A2
0x14001988c  mov     rax, [rcx]
0x14001988f  lea     rdx, [rbp+240h+psoSrc]
0x140019896  mov     rax, [rax+80h]
0x14001989d  call    _guard_dispatch_icall
0x1400198a2  mov     rdi, [rbp+240h+var_98]
0x1400198a9  test    rdi, rdi
0x1400198ac  jz      loc_140019D6C
0x1400198b2  cmp     [rbp+240h+var_80], esi
0x1400198b8  jnz     loc_140019D53
0x1400198be  mov     rax, [rdi]
0x1400198c1  mov     r10, [rax+40h]
0x1400198c5  mov     rax, [rbp+240h+var_78]
0x1400198cc  mov     [rsp+340h+Timeout], rax
0x1400198d1  mov     rax, r10
0x1400198d4  jmp     loc_140019D36
0x1400198d9  mov     cl, [rbp+240h+var_70]
0x1400198df  mov     rax, [r12]
0x1400198e3  test    cl, cl
0x1400198e5  mov     rdi, [rsp+340h+var_2D0]
0x1400198ea  setz    cl
0x1400198ed  mov     r8, rdi
0x1400198f0  mov     byte ptr [rsp+340h+prcl], cl
0x1400198f4  xor     r9d, r9d
0x1400198f7  mov     rax, [rax+38h]
0x1400198fb  lea     rcx, [rbp+240h+psoSrc]
0x140019902  mov     [rsp+340h+pptfx], rcx
0x140019907  mov     rdx, rdi
0x14001990a  lea     rcx, [rbp+240h+var_88]
0x140019911  mov     [rsp+340h+pptlBrushOrg], rcx
0x140019916  mov     rcx, r12
0x140019919  mov     dword ptr [rsp+340h+pca], ebx
0x14001991d  mov     dword ptr [rsp+340h+Timeout], ebx
0x140019921  call    _guard_dispatch_icall
0x140019926  test    eax, eax
0x140019928  js      loc_140019806
0x14001992e  mov     [rbp+240h+var_A0], r12
0x140019935  mov     r12, [rbp+240h+psoSrc]
0x14001993c  mov     [rbp+240h+var_A8], 0
0x140019947  jmp     loc_140019B93
0x14001994c  mov     rax, qword ptr [rsp+340h+var_2E0]
0x140019951  cmp     rax, cs:__imp_EngBitBlt
0x140019958  jz      loc_140019B8B
0x14001995e  mov     r8d, [r15+24h]; int
0x140019962  lea     r12, [rdi+1580h]
0x140019969  mov     rdi, [rsp+340h+var_2D0]
0x14001996e  lea     rax, [rbp+240h+var_190]
0x140019975  mov     edx, [r15+20h]; int
0x140019979  mov     r9, rdi; struct tagRECT *
0x14001997c  mov     byte ptr [rsp+340h+pca], bl; unsigned __int8
0x140019980  mov     rcx, r12; this
  ... truncated ...
```
