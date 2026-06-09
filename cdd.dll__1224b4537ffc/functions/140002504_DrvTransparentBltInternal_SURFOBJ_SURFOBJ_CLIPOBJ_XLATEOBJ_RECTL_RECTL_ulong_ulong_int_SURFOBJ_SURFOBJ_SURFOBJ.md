# DrvTransparentBltInternal(_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_RECTL *,ulong,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))

- ea: `0x140002504`
- end: `0x140003831`
- name: `?DrvTransparentBltInternal@@YAHPEAU_SURFOBJ@@0PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@3KKP6AH000123PEAU_POINTL@@4PEAU_BRUSHOBJ@@4K@Z@Z`
- size: `4909`
- prototype: `int(struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _RECTL *, unsigned int, unsigned int, int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))`
- caller_count: `2`
- callee_count: `23`
- tags: `installer_update`

## callers

- `0x1400024b0`
- `0x1400267f0`

## callees

- `0x140001008`
- `0x140002470`
- `0x140002504`
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
- `0x14001d458`
- `0x14001f778`
- `0x1400226b0`
- `0x1400248f8`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140002cb8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003155`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002cb8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140003155`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400030c7`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400032ec`
- `ntoskrnl!KeReleaseSemaphore` at `0x140003439`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400035c2`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400030c7`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400032ec`
- `ntoskrnl!KeReleaseSemaphore` at `0x140003439`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400035c2`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140002a70`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140002b7d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140002a70`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140002b7d`
- `ntoskrnl!DbgPrint` at `0x14000337d`
- `ntoskrnl!DbgPrint` at `0x14000337d`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000336a`
- `watchdog!WdLogSingleEntry2` at `0x1400037da`
- `watchdog!WdLogSingleEntry2` at `0x1400037da`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x1400037f1`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x1400037f1`
- `watchdog!WdLogNewEntry5_WdError` at `0x140002851`
- `watchdog!WdLogNewEntry5_WdError` at `0x140002d02`
- `watchdog!WdLogNewEntry5_WdError` at `0x140002fc6`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400031a0`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400033a4`
- `watchdog!WdLogNewEntry5_WdError` at `0x140002851`
- `watchdog!WdLogNewEntry5_WdError` at `0x140002d02`
- `watchdog!WdLogNewEntry5_WdError` at `0x140002fc6`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400031a0`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400033a4`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000264c`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000264c`
- `watchdog!WdLogSingleEntry0` at `0x140002633`
- `watchdog!WdLogSingleEntry0` at `0x14000283a`
- `watchdog!WdLogSingleEntry0` at `0x1400028eb`
- `watchdog!WdLogSingleEntry0` at `0x140002912`
- `watchdog!WdLogSingleEntry0` at `0x140002a1d`
- `watchdog!WdLogSingleEntry0` at `0x140002ceb`
- `watchdog!WdLogSingleEntry0` at `0x140002d35`
- `watchdog!WdLogSingleEntry0` at `0x140002faf`
- `watchdog!WdLogSingleEntry0` at `0x1400030e5`
- `watchdog!WdLogSingleEntry0` at `0x140003189`
- `watchdog!WdLogSingleEntry0` at `0x1400031d3`
- `watchdog!WdLogSingleEntry0` at `0x14000338e`
- `watchdog!WdLogSingleEntry0` at `0x140002633`
- `watchdog!WdLogSingleEntry0` at `0x14000283a`
- `watchdog!WdLogSingleEntry0` at `0x1400028eb`
- `watchdog!WdLogSingleEntry0` at `0x140002912`
- `watchdog!WdLogSingleEntry0` at `0x140002a1d`
- `watchdog!WdLogSingleEntry0` at `0x140002ceb`
- `watchdog!WdLogSingleEntry0` at `0x140002d35`
- `watchdog!WdLogSingleEntry0` at `0x140002faf`
- `watchdog!WdLogSingleEntry0` at `0x1400030e5`
- `watchdog!WdLogSingleEntry0` at `0x140003189`
- `watchdog!WdLogSingleEntry0` at `0x1400031d3`
- `watchdog!WdLogSingleEntry0` at `0x14000338e`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140002929`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140002a34`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140002d4c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400031ea`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140002929`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140002a34`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140002d4c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400031ea`
- `WIN32K!EngTransparentBlt` at `0x1400034c2`
- `WIN32K!EngTransparentBlt` at `0x14000379b`
- `WIN32K!EngTransparentBlt` at `0x1400034c2`
- `WIN32K!EngTransparentBlt` at `0x14000379b`
- `WIN32K!XLATEOBJ_iXlate` at `0x14000279a`
- `WIN32K!XLATEOBJ_iXlate` at `0x14000279a`
- `WIN32K!EngBitBlt` at `0x140002683`
- `WIN32K!EngBitBlt` at `0x140002ed7`
- `WIN32K!EngReleaseSemaphore` at `0x140003699`
- `WIN32K!EngReleaseSemaphore` at `0x1400036b8`
- `WIN32K!EngReleaseSemaphore` at `0x140003699`
- `WIN32K!EngReleaseSemaphore` at `0x1400036b8`
- `WIN32K!EngAcquireSemaphore` at `0x140003632`
- `WIN32K!EngAcquireSemaphore` at `0x140003632`

## string_xrefs

- `0x140003376`: `Ivalid pco in GDIBITMAPACCESS2::StartAccessDst`

## pseudocode

```c
__int64 __fastcall DrvTransparentBltInternal(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XLATEOBJ *a4,
        struct _RECTL *prclDst,
        struct _RECTL *a6,
        ULONG iColor,
        ULONG ulReserved,
        int (*a9)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))
{
  SURFOBJ *v9; // r14
  DHPDEV dhpdev; // rdi
  unsigned int v12; // ebx
  unsigned int (*v13)(void); // rax
  int v14; // ecx
  unsigned int iType; // eax
  __int64 v16; // rdx
  USHORT v17; // ax
  _QWORD *v18; // rax
  DHSURF dhsurf; // r15
  DHSURF v20; // r12
  BOOL v21; // r8d
  XLATEOBJ *v22; // r8
  ULONG v23; // eax
  __int64 v24; // r10
  _QWORD *v25; // rax
  RECTL *v26; // r9
  SURFOBJ *v27; // r8
  unsigned int v28; // edx
  ULONG v29; // r11d
  unsigned int v30; // r10d
  int v31; // edi
  _QWORD *v32; // rax
  int v33; // ecx
  _QWORD *v34; // rax
  bool v35; // zf
  char v36; // cl
  _QWORD *v37; // rdi
  NTSTATUS v38; // ecx
  _QWORD *v39; // rax
  _QWORD *v40; // rax
  DHSURF v41; // rdi
  __int64 v42; // rcx
  struct _KTHREAD *v43; // rdx
  RECTL *prclSrc; // rdi
  CStagingPool *v45; // r12
  SURFOBJ *v46; // r12
  _QWORD *v47; // rax
  DHSURF v48; // rdi
  __int64 v49; // rcx
  struct _KTHREAD *v50; // rdx
  int v51; // edi
  char v52; // cl
  void *v53; // r12
  _QWORD *v54; // r12
  NTSTATUS v55; // ecx
  _QWORD *v56; // rax
  _QWORD *v57; // rax
  DHSURF v58; // rdi
  struct _KTHREAD *v59; // rdx
  _QWORD *v60; // rax
  SURFOBJ *v61; // rsi
  __int64 v62; // rcx
  struct _KTHREAD *v63; // rdx
  int v64; // r8d
  int v65; // ecx
  DHSURF v66; // rdi
  __int64 v67; // rcx
  struct _KTHREAD *v68; // rdx
  unsigned int v69; // esi
  HSEMAPHORE v71; // rsi
  int v72; // r12d
  BOOL v73; // ecx
  struct _SURFOBJ *v74; // rsi
  _QWORD *v75; // rax
  int v76; // [rsp+40h] [rbp-C0h]
  BOOL v77; // [rsp+60h] [rbp-A0h]
  unsigned int v78; // [rsp+60h] [rbp-A0h]
  unsigned int iTransColor; // [rsp+64h] [rbp-9Ch]
  int v80; // [rsp+68h] [rbp-98h] BYREF
  CLIPOBJ *pco; // [rsp+70h] [rbp-90h] BYREF
  int v82; // [rsp+78h] [rbp-88h]
  unsigned int StagingVidMemAllocation; // [rsp+7Ch] [rbp-84h]
  RECTL *v84; // [rsp+80h] [rbp-80h]
  unsigned int v85; // [rsp+88h] [rbp-78h]
  XLATEOBJ *pxlo; // [rsp+90h] [rbp-70h]
  SURFOBJ *v87; // [rsp+98h] [rbp-68h] BYREF
  SURFOBJ *v88; // [rsp+A0h] [rbp-60h] BYREF
  BOOL (__stdcall *v89)(SURFOBJ *, SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *, POINTL *, BRUSHOBJ *, POINTL *, ROP4); // [rsp+A8h] [rbp-58h]
  struct _SURFOBJ *v90; // [rsp+B0h] [rbp-50h]
  __int64 v91; // [rsp+B8h] [rbp-48h] BYREF
  int v92; // [rsp+C0h] [rbp-40h]
  _OWORD v93[3]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v94; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v95; // [rsp+100h] [rbp+0h]
  __int64 v96; // [rsp+108h] [rbp+8h]
  int v97; // [rsp+110h] [rbp+10h]
  _BYTE v98[24]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v99[8]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v100; // [rsp+170h] [rbp+70h]
  SURFOBJ *v101; // [rsp+180h] [rbp+80h]
  DHSURF v102; // [rsp+188h] [rbp+88h]
  unsigned int v103; // [rsp+190h] [rbp+90h]
  int v104; // [rsp+194h] [rbp+94h]
  int v105; // [rsp+198h] [rbp+98h]
  __int64 v106; // [rsp+19Ch] [rbp+9Ch]
  char v107; // [rsp+1A4h] [rbp+A4h]
  _QWORD v108[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  CStagingPool *v109[2]; // [rsp+1F0h] [rbp+F0h]
  SURFOBJ *psoSrc[8]; // [rsp+200h] [rbp+100h] BYREF
  SURFOBJ *psoDst[8]; // [rsp+240h] [rbp+140h] BYREF
  struct CDDPDEV *v112; // [rsp+280h] [rbp+180h]
  void *v113; // [rsp+288h] [rbp+188h]
  DHSURF v114; // [rsp+290h] [rbp+190h]
  DHSURF v115; // [rsp+298h] [rbp+198h]
  struct _RECTL *v116; // [rsp+2A0h] [rbp+1A0h]
  __int64 v117; // [rsp+2A8h] [rbp+1A8h] BYREF
  int v118; // [rsp+2B0h] [rbp+1B0h]
  __int64 v119; // [rsp+2B8h] [rbp+1B8h]
  char v120; // [rsp+2C0h] [rbp+1C0h]
  __int64 v121; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v122; // [rsp+2E8h] [rbp+1E8h]
  int v123; // [rsp+2ECh] [rbp+1ECh]

  v9 = a2;
  v89 = a9;
  pco = a3;
  dhpdev = a1->dhpdev;
  v77 = 0;
  v12 = 1;
  v96 = 0;
  memset(v93, 0, sizeof(v93));
  v97 = 1;
  pxlo = a4;
  v13 = (unsigned int (*)(void))*((_QWORD *)dhpdev + 10);
  v90 = a1;
  v84 = a6;
  v87 = a1;
  v88 = a2;
  if ( v13() )
  {
    v14 = a6->right - a6->left;
    memset((char *)&v93[1] + 8, 0, 24);
    LODWORD(v93[0]) = v9->iType;
    iType = a1->iType;
    HIDWORD(v93[0]) = a6->bottom - a6->top;
    LODWORD(v93[1]) = prclDst->right - prclDst->left;
    DWORD1(v93[1]) = prclDst->bottom - prclDst->top;
    *(_QWORD *)((char *)v93 + 4) = __PAIR64__(v14, iType);
    CDDETWPROFILER::Init((CDDETWPROFILER *)&v94, (struct CDDPDEV *)dhpdev, 0xBD9u, (struct _DXGKETW_PARAMS *)v93, 0);
  }
  v16 = v9->iType;
  if ( (_WORD)v16 == 1 || (v17 = a1->iType, v17 == 1) )
  {
    v71 = (HSEMAPHORE)*((_QWORD *)dhpdev + 365);
    v72 = 0;
    if ( v71 )
    {
      EngAcquireSemaphore(*((HSEMAPHORE *)dhpdev + 365));
      v72 = 1;
    }
    if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
    {
      if ( v71 && v72 )
        EngReleaseSemaphore(v71);
      v73 = 1;
    }
    else
    {
      CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
      v16 = *((_QWORD *)dhpdev + 349);
      *(_QWORD *)(v16 + 56) = *(_QWORD *)(v16 + 48);
      v73 = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) != 0;
      StagingVidMemAllocation = v73;
      if ( v71 && v72 )
      {
        EngReleaseSemaphore(v71);
        v73 = StagingVidMemAllocation;
      }
    }
    if ( !v73 )
      goto LABEL_143;
    v74 = v90;
    if ( v90->iType == 3 || v9 && v9->iType == 3 )
    {
      WdLogSingleEntry2(3, v9, v90);
      WdLogGlobalForLineNumber = 581;
      v75 = (_QWORD *)WdLogNewEntry5_WdWarning();
      v75[3] = gCddImageInfo;
      v75[4] = (unsigned int)dword_14003E570;
      v75[5] = 215857758;
      WdLogGlobalForLineNumber = 581;
    }
    else
    {
      ReadFromFrameBuffer((struct CDDPDEV *)dhpdev, prclDst->left, prclDst->top, prclDst->right, prclDst->bottom);
      v80 = 0;
      CDDMULTISURFLOCK::vInit((CDDMULTISURFLOCK *)psoSrc, (struct CDDPDEV *)dhpdev, &v87, &v88, prclDst, a6, &v80, pco);
      if ( !bIgnoreDeviceSurfaceUpdates(v74, &pco) )
      {
        v69 = EngTransparentBlt(v87, v88, pco, pxlo, prclDst, a6, iColor, ulReserved);
        if ( v69 && v80 == 1 )
          vGDIDirtyUpdate((struct CDDPDEV *)dhpdev, (struct tagRECT *)prclDst, pco);
        CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)psoSrc);
        goto LABEL_144;
      }
      CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)psoSrc);
    }
LABEL_168:
    CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v94);
    return v12;
  }
  if ( (_WORD)v16 != 3 && v17 != 3 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 561;
    v18 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v18[3] = gCddImageInfo;
    v18[4] = (unsigned int)dword_14003E570;
    v18[5] = 215857758;
    WdLogGlobalForLineNumber = 561;
  }
  dhsurf = a1->dhsurf;
  if ( v89 == EngBitBlt )
    v20 = v9->dhsurf;
  else
    v20 = 0;
  if ( dhsurf )
  {
    dhpdev = (DHPDEV)*((_QWORD *)dhsurf + 1);
  }
  else if ( v20 )
  {
    dhpdev = (DHPDEV)*((_QWORD *)v20 + 1);
  }
  CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v98, (struct CddBitmap *)dhsurf, (struct CddBitmap *)v20);
  v21 = dhsurf && ((_DWORD)dhsurf[32] & 1) != 0;
  v82 = 0;
  if ( v84->bottom - v84->top > *((_DWORD *)dhpdev + 619) || v84->right - v84->left > *((_DWORD *)dhpdev + 618) )
    v21 = 0;
  if ( !v21 )
  {
    iTransColor = iColor;
    goto LABEL_56;
  }
  DWORD2(v93[1]) = 1;
  v80 = *((_DWORD *)dhsurf + 10);
  memset(v108, 0, sizeof(v108));
  *(_OWORD *)v109 = 0;
  if ( v20 )
  {
    v28 = *((_DWORD *)v20 + 10);
    v78 = v28;
    if ( v28 )
    {
      v29 = iColor;
      v30 = 0;
      v26 = v84;
      v27 = (SURFOBJ *)v20;
      iTransColor = iColor;
      v88 = (SURFOBJ *)v20;
      goto LABEL_42;
    }
    WdLogSingleEntry0(4);
    v31 = 2686;
LABEL_38:
    WdLogGlobalForLineNumber = v31;
    v32 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v32[3] = gCddImageInfo;
    v32[4] = (unsigned int)dword_14003E570;
    v32[5] = 215857758;
    WdLogGlobalForLineNumber = v31;
LABEL_39:
    if ( v109[0] )
    {
      *(CStagingPool **)(v108[0] + 16LL) = v109[1];
      CStagingPool::ReleaseGdiSurface(v109[0], (struct CDDBITMAP_GDIDESC *)v108);
    }
    goto LABEL_115;
  }
  if ( (int)CStagingPool::GetGdiSurface(
              (CStagingPool *)(dhpdev + 1376),
              v9->sizlBitmap.cx,
              v9->sizlBitmap.cy,
              (const struct tagRECT *)v84,
              (struct CDDBITMAP_GDIDESC *)v108,
              1u) < 0 )
  {
    WdLogSingleEntry0(4);
    v31 = 2644;
    goto LABEL_38;
  }
  v22 = pxlo;
  v109[0] = (CStagingPool *)(dhpdev + 1376);
  v109[1] = *(CStagingPool **)(v108[0] + 16LL);
  *(_QWORD *)(v108[0] + 16LL) = 0;
  if ( v22 )
  {
    v23 = XLATEOBJ_iXlate(v22, iColor);
    v22 = pxlo;
  }
  else
  {
    v23 = iColor;
  }
  v24 = v108[0];
  iTransColor = v23;
  if ( (unsigned __int64)(*(int *)(v108[0] + 64LL) * (__int64)(v84->top + 1) + 0x80000000LL) > 0xFFFFFFFF )
  {
    v82 = 1;
    goto LABEL_51;
  }
  if ( !((unsigned int (__fastcall *)(_QWORD, SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, RECTL *, RECTL *, _QWORD, _QWORD, _QWORD, int))v89)(
          v108[0],
          v9,
          0,
          0,
          v22,
          v84,
          v84,
          0,
          0,
          0,
          52428) )
  {
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 2670;
    v25 = (_QWORD *)WdLogNewEntry5_WdError();
    v25[3] = gCddImageInfo;
    v25[4] = (unsigned int)dword_14003E570;
    v25[5] = 215857758;
    WdLogGlobalForLineNumber = 2670;
    if ( v109[0] )
    {
      *(CStagingPool **)(v108[0] + 16LL) = v109[1];
      CStagingPool::ReleaseGdiSurface(v109[0], (struct CDDBITMAP_GDIDESC *)v108);
    }
    v12 = 0;
    goto LABEL_115;
  }
  v26 = (RECTL *)((char *)&v108[4] + 4);
  v27 = (SURFOBJ *)v108[3];
  v28 = v108[2];
  v29 = iTransColor;
  v30 = *(_DWORD *)(v108[0] + 64LL);
  v78 = v108[2];
  v88 = (SURFOBJ *)v108[3];
LABEL_42:
  v122 = prclDst->right - prclDst->left;
  v33 = prclDst->bottom - prclDst->top;
  v85 = v30;
  v87 = (SURFOBJ *)v26;
  v121 = 0;
  v123 = v33;
  if ( v20 == dhsurf && ((_DWORD)dhpdev[475] & 0x20) != 0 )
  {
    CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v91, *((struct CDDMUTEX **)dhpdev + 364), (int)v27);
    StagingVidMemAllocation = CddBitmapStagingVidMem::GetStagingVidMemAllocation(
                                *((CddBitmapStagingVidMem **)dhpdev + 687),
                                (const struct tagRECT *)prclDst);
    if ( !StagingVidMemAllocation )
    {
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 2704;
      v34 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v35 = v92 == 0;
      v34[3] = gCddImageInfo;
      v34[4] = (unsigned int)dword_14003E570;
      v34[5] = 215857758;
      WdLogGlobalForLineNumber = 2704;
      if ( !v35 )
        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v91);
      goto LABEL_39;
    }
    v99[0] = pco;
    v99[1] = v87;
    v99[3] = &v121;
    v101 = v88;
    v102 = (DHSURF)*((_QWORD *)dhpdev + 687);
    v103 = v78;
    LOBYTE(v99[6]) = 0;
    v107 = 0;
    v104 = StagingVidMemAllocation;
    v99[5] = 0;
    v106 = v85;
    v99[2] = prclDst;
    *((_QWORD *)&v100 + 1) = dhpdev;
    v105 = 1;
    ClipDstRects(
      (struct CLIP_RECTS_DATA *)v99,
      (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::BitBltCallback);
    v99[0] = pco;
    LOBYTE(v99[6]) = 0;
    v99[1] = &v121;
    v105 = iTransColor;
    v101 = (SURFOBJ *)*((_QWORD *)dhpdev + 687);
    v103 = StagingVidMemAllocation;
    *((_QWORD *)&v100 + 1) = 0;
    v106 = 0;
    v99[5] = 0;
    v104 = v80;
    v99[2] = prclDst;
    v99[3] = prclDst;
    v102 = dhsurf;
    ClipDstRects(
      (struct CLIP_RECTS_DATA *)v99,
      (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::TransparentBltCallback);
    if ( v92 )
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v91);
  }
  else
  {
    LOBYTE(v99[6]) = 0;
    *((_QWORD *)&v100 + 1) = 0;
    v99[0] = pco;
    LODWORD(v106) = 0;
    v99[5] = 0;
    v103 = v28;
    v104 = v80;
    v99[1] = v26;
    v99[2] = prclDst;
    v99[3] = prclDst;
    v105 = v29;
    v101 = v27;
    v102 = dhsurf;
    HIDWORD(v106) = v30;
    ClipDstRects(
      (struct CLIP_RECTS_DATA *)v99,
      (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::TransparentBltCallback);
  }
  CddBitmap::VidMemDirtyUpdate((CddBitmap *)dhsurf);
  v24 = v108[0];
  v77 = 1;
LABEL_51:
  if ( v109[0] )
  {
    *(CStagingPool **)(v24 + 16) = v109[1];
    CStagingPool::ReleaseGdiSurface(v109[0], (struct CDDBITMAP_GDIDESC *)v108);
  }
  if ( !v82 )
    goto LABEL_142;
LABEL_56:
  GDIBITMAPACCESS2::GDIBITMAPACCESS2(
    (GDIBITMAPACCESS2 *)psoSrc,
    (struct CDDPDEV *)dhpdev,
    (struct CddBitmap *)v20,
    (struct CddBitmap *)dhsurf);
  memset(v99, 0, sizeof(v99));
  v100 = 0;
  if ( v20 )
  {
    v36 = v120;
    if ( v120 )
    {
      v37 = (_QWORD *)*((_QWORD *)v112 + 895);
      if ( (struct _KTHREAD *)v37[4] != KeGetCurrentThread() )
      {
        v38 = KeWaitForSingleObject(v37, Executive, 0, 0, 0);
        if ( v38 != 258 )
        {
          v37[4] = KeGetCurrentThread();
          if ( v38 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 618;
            v39 = (_QWORD *)WdLogNewEntry5_WdError();
            v39[3] = gCddImageInfo;
            v39[4] = (unsigned int)dword_14003E570;
            v39[5] = 215857758;
            WdLogGlobalForLineNumber = 618;
LABEL_62:
            WdLogSingleEntry0(4);
            WdLogGlobalForLineNumber = 2778;
            v40 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v40[3] = gCddImageInfo;
            v40[4] = (unsigned int)dword_14003E570;
            v40[5] = 215857758;
            WdLogGlobalForLineNumber = 2778;
            if ( (_QWORD)v100 )
            {
              *(_QWORD *)(v99[0] + 16LL) = *((_QWORD *)&v100 + 1);
              CStagingPool::ReleaseGdiSurface((CStagingPool *)v100, (struct CDDBITMAP_GDIDESC *)v99);
            }
            if ( v114 )
              (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v114 + 128LL))(v114, psoSrc);
            v41 = v115;
            if ( v115 )
            {
              if ( !v118 )
                (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, void *, __int64))(*(_QWORD *)v115 + 64LL))(
                  v115,
                  psoDst,
                  v116,
                  v113,
                  v119);
              (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v41 + 128LL))(v41, psoDst);
            }
            v42 = *((_QWORD *)v112 + 895);
            v43 = *(struct _KTHREAD **)(v42 + 32);
            if ( v43 != KeGetCurrentThread() || !v43 )
              goto LABEL_115;
            *(_QWORD *)(v42 + 32) = 0;
LABEL_114:
            KeReleaseSemaphore((PRKSEMAPHORE)v42, 0, 1, 0);
LABEL_115:
            CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v98);
            goto LABEL_168;
          }
        }
      }
      v36 = v120;
    }
    prclSrc = v84;
    LOBYTE(v76) = v36 == 0;
    if ( (*(int (__fastcall **)(DHSURF, RECTL *, RECTL *, _QWORD, int, int, __int64 *, SURFOBJ **, int))(*(_QWORD *)v20 + 56LL))(
           v20,
           v84,
           v84,
           0,
           1,
           1,
           &v117,
           psoSrc,
           v76) < 0 )
      goto LABEL_62;
    v9 = psoSrc[0];
    v114 = v20;
    v113 = 0;
    psoSrc[0]->fjBitmap |= 0x100u;
  }
  else if ( v89 == EngBitBlt )
  {
    prclSrc = v84;
  }
  else
  {
    v45 = (CStagingPool *)(dhpdev + 1376);
    prclSrc = v84;
    if ( (int)CStagingPool::GetGdiSurface(
                v45,
                v9->sizlBitmap.cx,
                v9->sizlBitmap.cy,
                (const struct tagRECT *)v84,
                (struct CDDBITMAP_GDIDESC *)v99,
                1u) < 0 )
    {
      WdLogSingleEntry0(4);
      v51 = 2788;
LABEL_103:
      WdLogGlobalForLineNumber = v51;
      v57 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v57[3] = gCddImageInfo;
      v57[4] = (unsigned int)dword_14003E570;
      v57[5] = 215857758;
      WdLogGlobalForLineNumber = v51;
      if ( (_QWORD)v100 )
      {
        *(_QWORD *)(v99[0] + 16LL) = *((_QWORD *)&v100 + 1);
        CStagingPool::ReleaseGdiSurface((CStagingPool *)v100, (struct CDDBITMAP_GDIDESC *)v99);
      }
      if ( v114 )
        (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v114 + 128LL))(v114, psoSrc);
      v58 = v115;
      if ( v115 )
      {
        if ( !v118 )
          (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, void *, __int64))(*(_QWORD *)v115 + 64LL))(
            v115,
            psoDst,
            v116,
            v113,
            v119);
        (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v58 + 128LL))(v58, psoDst);
      }
      v42 = *((_QWORD *)v112 + 895);
      v59 = *(struct _KTHREAD **)(v42 + 32);
      if ( v59 != KeGetCurrentThread() || !v59 )
        goto LABEL_115;
      *(_QWORD *)(v42 + 32) = 0;
      goto LABEL_114;
    }
    *(_QWORD *)&v100 = v45;
    *((_QWORD *)&v100 + 1) = *(_QWORD *)(v99[0] + 16LL);
    *(_QWORD *)(v99[0] + 16LL) = 0;
    v46 = (SURFOBJ *)v99[0];
    if ( (unsigned __int64)(*(int *)(v99[0] + 64LL) * (__int64)(prclSrc->top + 1) + 0x80000000LL) <= 0xFFFFFFFF && !v82 )
    {
      if ( !((unsigned int (__fastcall *)(_QWORD, SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, RECTL *, RECTL *, _QWORD, _QWORD, _QWORD, int))v89)(
              v99[0],
              v9,
              0,
              0,
              pxlo,
              prclSrc,
              prclSrc,
              0,
              0,
              0,
              52428) )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 2806;
        v47 = (_QWORD *)WdLogNewEntry5_WdError();
        v47[3] = gCddImageInfo;
        v47[4] = (unsigned int)dword_14003E570;
        v47[5] = 215857758;
        WdLogGlobalForLineNumber = 2806;
        if ( (_QWORD)v100 )
        {
          *(_QWORD *)(v99[0] + 16LL) = *((_QWORD *)&v100 + 1);
          CStagingPool::ReleaseGdiSurface((CStagingPool *)v100, (struct CDDBITMAP_GDIDESC *)v99);
        }
        if ( v114 )
          (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v114 + 128LL))(v114, psoSrc);
        v48 = v115;
        if ( v115 )
        {
          if ( !v118 )
            (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, void *, __int64))(*(_QWORD *)v115 + 64LL))(
              v115,
              psoDst,
              v116,
              v113,
              v119);
          (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v48 + 128LL))(v48, psoDst);
        }
        v49 = *((_QWORD *)v112 + 895);
        v50 = *(struct _KTHREAD **)(v49 + 32);
        if ( v50 == KeGetCurrentThread() && v50 )
        {
          *(_QWORD *)(v49 + 32) = 0;
          KeReleaseSemaphore((PRKSEMAPHORE)v49, 0, 1, 0);
        }
        v12 = 0;
        goto LABEL_115;
      }
      v9 = v46;
    }
  }
  if ( dhsurf )
  {
    v52 = v120;
    v53 = pco;
    v90 = (struct _SURFOBJ *)pco;
    if ( v120 )
    {
      v54 = (_QWORD *)*((_QWORD *)v112 + 895);
      if ( (struct _KTHREAD *)v54[4] != KeGetCurrentThread() )
      {
        v55 = KeWaitForSingleObject(v54, Executive, 0, 0, 0);
        if ( v55 != 258 )
        {
          v54[4] = KeGetCurrentThread();
          if ( v55 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 659;
            v56 = (_QWORD *)WdLogNewEntry5_WdError();
            v56[3] = gCddImageInfo;
            v56[4] = (unsigned int)dword_14003E570;
            v56[5] = 215857758;
            WdLogGlobalForLineNumber = 659;
LABEL_102:
            WdLogSingleEntry0(4);
            v51 = 2822;
            goto LABEL_103;
          }
        }
      }
      v52 = v120;
      v53 = v90;
    }
    LOBYTE(v76) = v52 == 0;
    if ( (*(int (__fastcall **)(DHSURF, struct _RECTL *, struct _RECTL *, void *, int, int, char *, SURFOBJ **, int))(*(_QWORD *)dhsurf + 56LL))(
           dhsurf,
           prclDst,
           prclDst,
           v53,
           1,
           1,
           (char *)&v117 + 4,
           psoDst,
           v76) < 0 )
      goto LABEL_102;
    if ( v113 && v53 != v113 && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Ivalid pco in GDIBITMAPACCESS2::StartAccessDst");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 670;
      v60 = (_QWORD *)WdLogNewEntry5_WdError();
      v60[3] = gCddImageInfo;
      v60[4] = (unsigned int)dword_14003E570;
      v60[5] = 215857758;
      WdLogGlobalForLineNumber = 670;
      __debugbreak();
    }
    v61 = psoDst[0];
    v115 = dhsurf;
    v116 = prclDst;
    v113 = v53;
    v119 = 0;
  }
  else
  {
    v61 = v90;
  }
  v62 = *((_QWORD *)v112 + 895);
  v63 = *(struct _KTHREAD **)(v62 + 32);
  if ( v63 == KeGetCurrentThread() && v63 )
  {
    *(_QWORD *)(v62 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v62, 0, 1, 0);
  }
  v64 = HIDWORD(v117);
  if ( v117 )
  {
    CDDPDEV::Flush(v112);
    v64 = HIDWORD(v117);
  }
  WaitForStartGdiAccessToFinish(v112, (struct CDDBITMAP_GDIDESC *)psoDst, v64);
  WaitForStartGdiAccessToFinish(v112, (struct CDDBITMAP_GDIDESC *)psoSrc, v117);
  v77 = EngTransparentBlt(v61, v9, pco, pxlo, prclDst, prclSrc, iTransColor, ulReserved);
  v9->fjBitmap &= ~0x100u;
  v65 = v118;
  if ( !v77 )
    v65 = 1;
  v118 = v65;
  if ( (_QWORD)v100 )
  {
    *(_QWORD *)(v99[0] + 16LL) = *((_QWORD *)&v100 + 1);
    CStagingPool::ReleaseGdiSurface((CStagingPool *)v100, (struct CDDBITMAP_GDIDESC *)v99);
  }
  if ( v114 )
    (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v114 + 128LL))(v114, psoSrc);
  v66 = v115;
  if ( v115 )
  {
    if ( !v118 )
      (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, void *, __int64))(*(_QWORD *)v115 + 64LL))(
        v115,
        psoDst,
        v116,
        v113,
        v119);
    (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v66 + 128LL))(v66, psoDst);
  }
  v67 = *((_QWORD *)v112 + 895);
  v68 = *(struct _KTHREAD **)(v67 + 32);
  if ( v68 == KeGetCurrentThread() && v68 )
  {
    *(_QWORD *)(v67 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v67, 0, 1, 0);
  }
LABEL_142:
  CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v98);
LABEL_143:
  v69 = v77;
LABEL_144:
  if ( !v97 )
  {
    LOBYTE(v16) = 2;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(v94 + 264))(v95, v16, v96);
  }
  return v69;
}

```

## disassembly

```asm
0x140002504  push    rbp
0x140002506  push    rbx
0x140002507  push    rsi
0x140002508  push    rdi
0x140002509  push    r12
0x14000250b  push    r13
0x14000250d  push    r14
0x14000250f  push    r15
0x140002511  lea     rbp, [rsp-208h]
0x140002519  sub     rsp, 308h
0x140002520  mov     rax, cs:__security_cookie
0x140002527  xor     rax, rsp
0x14000252a  mov     [rbp+240h+var_50], rax
0x140002531  mov     rax, [rbp+240h+arg_40]
0x140002538  xorps   xmm0, xmm0
0x14000253b  mov     r15, [rbp+240h+arg_28]
0x140002542  mov     r14, rdx
0x140002545  mov     r13, [rbp+240h+prclDst]
0x14000254c  mov     r12, rcx
0x14000254f  mov     [rbp+240h+var_298], rax
0x140002553  xor     eax, eax
0x140002555  mov     [rsp+340h+pco], r8
0x14000255a  mov     rdi, [rcx+10h]
0x14000255e  mov     [rsp+340h+var_2E0], eax
0x140002562  lea     ebx, [rax+1]
0x140002565  mov     [rbp+240h+var_238], rax
0x140002569  movups  [rbp+240h+var_278], xmm0
0x14000256d  mov     [rbp+240h+var_230], ebx
0x140002570  movups  [rbp+240h+var_268], xmm0
0x140002574  mov     [rbp+240h+pxlo], r9
0x140002578  movups  [rbp+240h+var_258], xmm0
0x14000257c  mov     rax, [rdi+50h]
0x140002580  mov     [rbp+240h+var_290], rcx
0x140002584  mov     [rbp+240h+var_2C0], r15
0x140002588  mov     [rbp+240h+var_2A8], rcx
0x14000258c  mov     [rbp+240h+var_2A0], rdx
0x140002590  call    _guard_dispatch_icall
0x140002595  test    eax, eax
0x140002597  jz      short loc_140002600
0x140002599  mov     ecx, [r15+8]
0x14000259d  lea     r9, [rbp+240h+var_278]; struct _DXGKETW_PARAMS *
0x1400025a1  sub     ecx, [r15]
0x1400025a4  xorps   xmm0, xmm0
0x1400025a7  movdqu  [rbp+240h+var_268+8], xmm0
0x1400025ac  mov     qword ptr [rbp+240h+var_258+8], 0
0x1400025b4  mov     r8d, 0BD9h; unsigned int
0x1400025ba  movzx   eax, word ptr [r14+4Ch]
0x1400025bf  mov     rdx, rdi; struct CDDPDEV *
0x1400025c2  mov     dword ptr [rbp+240h+var_278], eax
0x1400025c5  movzx   eax, word ptr [r12+4Ch]
0x1400025cb  mov     dword ptr [rbp+240h+var_278+8], ecx
0x1400025ce  mov     ecx, [r15+0Ch]
0x1400025d2  sub     ecx, [r15+4]
0x1400025d6  mov     dword ptr [rbp+240h+var_278+0Ch], ecx
0x1400025d9  mov     ecx, [r13+8]
0x1400025dd  sub     ecx, [r13+0]
0x1400025e1  mov     dword ptr [rbp+240h+var_268], ecx
0x1400025e4  mov     ecx, [r13+0Ch]
0x1400025e8  sub     ecx, [r13+4]
0x1400025ec  mov     dword ptr [rbp+240h+var_268+4], ecx
0x1400025ef  lea     rcx, [rbp+240h+var_248]; this
0x1400025f3  mov     dword ptr [rbp+240h+var_278+4], eax
0x1400025f6  mov     byte ptr [rsp+340h+Timeout], 0; bool
0x1400025fb  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x140002600  movzx   edx, word ptr [r14+4Ch]
0x140002605  cmp     dx, bx
0x140002608  jz      loc_140003620
0x14000260e  movzx   eax, word ptr [r12+4Ch]
0x140002614  cmp     ax, bx
0x140002617  jz      loc_140003620
0x14000261d  mov     ecx, 3
0x140002622  mov     esi, 0CDDBA5Eh
0x140002627  cmp     dx, cx
0x14000262a  jz      short loc_14000267B
0x14000262c  cmp     ax, cx
0x14000262f  jz      short loc_14000267B
0x140002631  mov     ecx, ebx
0x140002633  call    cs:__imp_WdLogSingleEntry0
0x14000263a  nop     dword ptr [rax+rax+00h]
0x14000263f  mov     r15d, 231h
0x140002645  mov     cs:WdLogGlobalForLineNumber, r15d
0x14000264c  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140002653  nop     dword ptr [rax+rax+00h]
0x140002658  mov     rcx, rax
0x14000265b  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140002662  mov     [rcx+18h], rax
0x140002666  mov     eax, cs:dword_14003E570
0x14000266c  mov     [rcx+20h], rax
0x140002670  mov     [rcx+28h], rsi
0x140002674  mov     cs:WdLogGlobalForLineNumber, r15d
0x14000267b  mov     rax, [rbp+240h+var_298]
0x14000267f  mov     r15, [r12]
0x140002683  cmp     rax, cs:__imp_EngBitBlt
0x14000268a  jnz     short loc_140002691
0x14000268c  mov     r12, [r14]
0x14000268f  jmp     short loc_140002694
0x140002691  xor     r12d, r12d
0x140002694  test    r15, r15
0x140002697  jz      short loc_14000269F
0x140002699  mov     rdi, [r15+8]
0x14000269d  jmp     short loc_1400026A9
0x14000269f  test    r12, r12
0x1400026a2  jz      short loc_1400026A9
0x1400026a4  mov     rdi, [r12+8]
0x1400026a9  mov     r8, r12; struct CddBitmap *
0x1400026ac  lea     rcx, [rbp+240h+var_228]; this
0x1400026b0  mov     rdx, r15; struct CddBitmap *
0x1400026b3  call    ??0CDDMULTIBITMAPLOCK@@QEAA@PEAVCddBitmap@@0@Z; CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(CddBitmap *,CddBitmap *)
0x1400026b8  test    r15, r15
0x1400026bb  jz      short loc_1400026CD
0x1400026bd  mov     eax, [r15+80h]
0x1400026c4  test    bl, al
0x1400026c6  jz      short loc_1400026CD
0x1400026c8  mov     r8d, ebx
0x1400026cb  jmp     short loc_1400026D0
0x1400026cd  xor     r8d, r8d
0x1400026d0  mov     rdx, [rbp+240h+var_2C0]
0x1400026d4  mov     [rsp+340h+var_2C8], 0
0x1400026dc  mov     ecx, [rdx+0Ch]
0x1400026df  sub     ecx, [rdx+4]
0x1400026e2  cmp     ecx, [rdi+9ACh]
0x1400026e8  jg      short loc_1400026F7
0x1400026ea  mov     ecx, [rdx+8]
0x1400026ed  sub     ecx, [rdx]
0x1400026ef  cmp     ecx, [rdi+9A8h]
0x1400026f5  jle     short loc_1400026FA
0x1400026f7  xor     r8d, r8d
0x1400026fa  test    r8d, r8d
0x1400026fd  jz      loc_140002C36
0x140002703  xor     edx, edx; Val
0x140002705  mov     dword ptr [rbp+240h+var_268+8], ebx
0x140002708  mov     eax, [r15+28h]
0x14000270c  lea     rcx, [rbp+240h+var_190]; void *
0x140002713  mov     [rsp+340h+var_2D8], eax
0x140002717  lea     r8d, [rdx+40h]; Size
0x14000271b  call    memset
0x140002720  xorps   xmm0, xmm0
0x140002723  movdqa  xmmword ptr [rbp+240h+var_150], xmm0
0x14000272b  test    r12, r12
0x14000272e  jnz     loc_1400028FE
0x140002734  mov     r9, [rbp+240h+var_2C0]; struct tagRECT *
0x140002738  lea     rcx, [rbp+240h+var_190]
0x14000273f  mov     r8d, [r14+24h]; int
0x140002743  mov     edx, [r14+20h]; int
0x140002747  mov     byte ptr [rsp+340h+prclSrc], bl; unsigned __int8
0x14000274b  mov     [rsp+340h+Timeout], rcx; struct CDDBITMAP_GDIDESC *
0x140002750  lea     rcx, [rdi+1580h]; this
0x140002757  call    ?GetGdiSurface@CStagingPool@@QEAAJHHPEBUtagRECT@@PEAUCDDBITMAP_GDIDESC@@E@Z; CStagingPool::GetGdiSurface(int,int,tagRECT const *,CDDBITMAP_GDIDESC *,uchar)
0x14000275c  test    eax, eax
0x14000275e  js      loc_1400028E6
0x140002764  mov     rcx, [rbp+240h+var_190]
0x14000276b  lea     rax, [rdi+1580h]
0x140002772  mov     r8, [rbp+240h+pxlo]
0x140002776  mov     [rbp+240h+var_150], rax
0x14000277d  mov     rax, [rcx+10h]
0x140002781  mov     [rbp+240h+var_150+8], rax
0x140002788  mov     [rcx+10h], r12
0x14000278c  test    r8, r8
0x14000278f  jz      short loc_1400027AC
0x140002791  mov     edx, [rbp+240h+iColor]; iColor
0x140002797  mov     rcx, r8; pxlo
0x14000279a  call    cs:__imp_XLATEOBJ_iXlate
0x1400027a1  nop     dword ptr [rax+rax+00h]
0x1400027a6  mov     r8, [rbp+240h+pxlo]
0x1400027aa  jmp     short loc_1400027B2
0x1400027ac  mov     eax, [rbp+240h+iColor]
0x1400027b2  mov     rdx, [rbp+240h+var_2C0]
0x1400027b6  mov     r10, [rbp+240h+var_190]
0x1400027bd  mov     [rsp+340h+var_2DC], eax
0x1400027c1  mov     eax, [rdx+4]
0x1400027c4  add     eax, ebx
0x1400027c6  movsxd  rcx, eax
0x1400027c9  movsxd  rax, dword ptr [r10+40h]
0x1400027cd  imul    rcx, rax
0x1400027d1  mov     eax, 80000000h
0x1400027d6  add     rax, rcx
0x1400027d9  mov     ecx, 0FFFFFFFFh
0x1400027de  cmp     rax, rcx
0x1400027e1  jbe     short loc_1400027EC
0x1400027e3  mov     [rsp+340h+var_2C8], ebx
0x1400027e7  jmp     loc_140002C02
0x1400027ec  mov     rax, [rbp+240h+var_298]
0x1400027f0  xor     r9d, r9d
0x1400027f3  mov     [rsp+340h+var_2F0], 0CCCCh
0x1400027fb  mov     rcx, r10
0x1400027fe  mov     [rsp+340h+var_2F8], 0
0x140002807  mov     [rsp+340h+var_300], 0
0x140002810  mov     qword ptr [rsp+340h+ulReserved], 0
0x140002819  mov     qword ptr [rsp+340h+iTransColor], rdx
0x14000281e  mov     [rsp+340h+prclSrc], rdx
0x140002823  mov     rdx, r14
0x140002826  mov     [rsp+340h+Timeout], r8
0x14000282b  xor     r8d, r8d
0x14000282e  call    _guard_dispatch_icall
0x140002833  test    eax, eax
0x140002835  jnz     short loc_1400028B5
0x140002837  lea     ecx, [rax+2]
0x14000283a  call    cs:__imp_WdLogSingleEntry0
0x140002841  nop     dword ptr [rax+rax+00h]
0x140002846  mov     ebx, 0A6Eh
0x14000284b  mov     cs:WdLogGlobalForLineNumber, ebx
0x140002851  call    cs:__imp_WdLogNewEntry5_WdError
0x140002858  nop     dword ptr [rax+rax+00h]
0x14000285d  mov     rcx, rax
0x140002860  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140002867  mov     [rcx+18h], rax
0x14000286b  mov     eax, cs:dword_14003E570
0x140002871  mov     [rcx+20h], rax
0x140002875  mov     [rcx+28h], rsi
0x140002879  cmp     [rbp+240h+var_150], 0
0x140002881  mov     cs:WdLogGlobalForLineNumber, ebx
0x140002887  jz      short loc_1400028AE
0x140002889  mov     rcx, [rbp+240h+var_190]
0x140002890  lea     rdx, [rbp+240h+var_190]; struct CDDBITMAP_GDIDESC *
0x140002897  mov     rax, [rbp+240h+var_150+8]
0x14000289e  mov     [rcx+10h], rax
0x1400028a2  mov     rcx, [rbp+240h+var_150]; this
0x1400028a9  call    ?ReleaseGdiSurface@CStagingPool@@QEAAXPEAUCDDBITMAP_GDIDESC@@@Z; CStagingPool::ReleaseGdiSurface(CDDBITMAP_GDIDESC *)
0x1400028ae  xor     ebx, ebx
0x1400028b0  jmp     loc_1400032F8
0x1400028b5  mov     rax, [rbp+240h+var_190]
0x1400028bc  lea     r9, [rbp+240h+var_16C]
0x1400028c3  mov     r8, [rbp+240h+var_178]
0x1400028ca  mov     edx, [rbp+240h+var_180]
0x1400028d0  mov     r11d, [rsp+340h+var_2DC]
0x1400028d5  mov     r10d, [rax+40h]
0x1400028d9  mov     [rsp+340h+var_2E0], edx
0x1400028dd  mov     [rbp+240h+var_2A0], r8
0x1400028e1  jmp     loc_1400029A9
0x1400028e6  mov     ecx, 4
0x1400028eb  call    cs:__imp_WdLogSingleEntry0
0x1400028f2  nop     dword ptr [rax+rax+00h]
0x1400028f7  mov     edi, 0A54h
0x1400028fc  jmp     short loc_140002923
0x1400028fe  mov     edx, [r12+28h]
0x140002903  mov     [rsp+340h+var_2E0], edx
0x140002907  test    edx, edx
0x140002909  jnz     loc_14000298F
0x14000290f  lea     ecx, [rdx+4]
0x140002912  call    cs:__imp_WdLogSingleEntry0
0x140002919  nop     dword ptr [rax+rax+00h]
0x14000291e  mov     edi, 0A7Eh
0x140002923  mov     cs:WdLogGlobalForLineNumber, edi
0x140002929  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140002930  nop     dword ptr [rax+rax+00h]
0x140002935  mov     rcx, rax
0x140002938  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000293f  mov     [rcx+18h], rax
0x140002943  mov     eax, cs:dword_14003E570
0x140002949  mov     [rcx+20h], rax
0x14000294d  mov     [rcx+28h], rsi
0x140002951  mov     cs:WdLogGlobalForLineNumber, edi
0x140002957  cmp     [rbp+240h+var_150], 0
0x14000295f  jz      loc_1400032F8
0x140002965  mov     rcx, [rbp+240h+var_190]
0x14000296c  lea     rdx, [rbp+240h+var_190]; struct CDDBITMAP_GDIDESC *
0x140002973  mov     rax, [rbp+240h+var_150+8]
0x14000297a  mov     [rcx+10h], rax
0x14000297e  mov     rcx, [rbp+240h+var_150]; this
0x140002985  call    ?ReleaseGdiSurface@CStagingPool@@QEAAXPEAUCDDBITMAP_GDIDESC@@@Z; CStagingPool::ReleaseGdiSurface(CDDBITMAP_GDIDESC *)
0x14000298a  jmp     loc_1400032F8
0x14000298f  mov     r11d, [rbp+240h+iColor]
0x140002996  xor     r10d, r10d
0x140002999  mov     r9, [rbp+240h+var_2C0]
0x14000299d  mov     r8, r12; int
0x1400029a0  mov     [rsp+340h+var_2DC], r11d
0x1400029a5  mov     [rbp+240h+var_2A0], r12
0x1400029a9  mov     ecx, [r13+8]
0x1400029ad  sub     ecx, [r13+0]
0x1400029b1  mov     [rbp+240h+var_58], ecx
0x1400029b7  mov     ecx, [r13+0Ch]
0x1400029bb  sub     ecx, [r13+4]
0x1400029bf  mov     [rbp+240h+var_2B8], r10d
0x1400029c3  mov     [rbp+240h+var_2A8], r9
0x1400029c7  mov     [rbp+240h+var_60], 0
0x1400029d2  mov     [rbp+240h+var_54], ecx
0x1400029d8  cmp     r12, r15
0x1400029db  jnz     loc_140002B8B
0x1400029e1  mov     eax, [rdi+76Ch]
0x1400029e7  test    al, 20h
0x1400029e9  jz      loc_140002B8B
0x1400029ef  mov     rdx, [rdi+0B60h]; struct CDDMUTEX *
0x1400029f6  lea     rcx, [rbp+240h+var_288]; this
0x1400029fa  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x1400029ff  mov     rcx, [rdi+1578h]; this
0x140002a06  mov     rdx, r13; struct tagRECT *
0x140002a09  call    ?GetStagingVidMemAllocation@CddBitmapStagingVidMem@@QEAAIPEBUtagRECT@@@Z; CddBitmapStagingVidMem::GetStagingVidMemAllocation(tagRECT const *)
0x140002a0e  xor     edx, edx
0x140002a10  mov     [rsp+340h+var_2C4], eax
0x140002a14  mov     ecx, eax
0x140002a16  test    eax, eax
0x140002a18  jnz     short loc_140002A81
0x140002a1a  lea     ecx, [rax+4]
0x140002a1d  call    cs:__imp_WdLogSingleEntry0
0x140002a24  nop     dword ptr [rax+rax+00h]
0x140002a29  mov     edi, 0A90h
0x140002a2e  mov     cs:WdLogGlobalForLineNumber, edi
0x140002a34  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140002a3b  nop     dword ptr [rax+rax+00h]
0x140002a40  cmp     [rbp+240h+var_280], 0
  ... truncated ...
```
