# DrvBitBltInternal(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))

- ea: `0x14000919c`
- end: `0x14000a24e`
- name: `?DrvBitBltInternal@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@4PEAU_BRUSHOBJ@@4KP6AH0001234454K@Z@Z`
- size: `4274`
- prototype: `int __fastcall(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, RECTL *prclTrg, POINTL *pptlSrc, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, struct CDDPDEV *, int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))`
- caller_count: `5`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400090c0`
- `0x140009140`
- `0x14000919c`
- `0x140025c90`
- `0x140026d40`

## callees

- `0x140001008`
- `0x140002470`
- `0x140008714`
- `0x14000874c`
- `0x140008774`
- `0x1400087ac`
- `0x140008da4`
- `0x14000919c`
- `0x14000a254`
- `0x14000d63c`
- `0x14000fbb4`
- `0x140010670`
- `0x14001d458`
- `0x1400224a0`
- `0x1400226b0`
- `0x14002292c`
- `0x1400248f8`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000983c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000999c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140009fd0`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000983c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14000999c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140009fd0`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400097ef`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400098a1`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140009a6d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140009f09`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000a02c`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400097ef`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400098a1`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140009a6d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140009f09`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000a02c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009e68`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a154`
- `ntoskrnl!KeGetCurrentIrql` at `0x140009e68`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a154`
- `ntoskrnl!KeSetEvent` at `0x14000a1c0`
- `ntoskrnl!KeSetEvent` at `0x14000a1c0`
- `watchdog!WdLogSingleEntry2` at `0x14000a1e2`
- `watchdog!WdLogSingleEntry2` at `0x14000a1e2`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14000a1f9`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x14000a1f9`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400093bd`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140009e90`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000a17d`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400093bd`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140009e90`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000a17d`
- `watchdog!WdLogSingleEntry0` at `0x1400093a6`
- `watchdog!WdLogSingleEntry0` at `0x140009e7a`
- `watchdog!WdLogSingleEntry0` at `0x14000a166`
- `watchdog!WdLogSingleEntry0` at `0x1400093a6`
- `watchdog!WdLogSingleEntry0` at `0x140009e7a`
- `watchdog!WdLogSingleEntry0` at `0x14000a166`
- `WIN32K!CddEngOffsetRgn` at `0x1400099c9`
- `WIN32K!CddEngOffsetRgn` at `0x140009a18`
- `WIN32K!CddEngOffsetRgn` at `0x1400099c9`
- `WIN32K!CddEngOffsetRgn` at `0x140009a18`
- `WIN32K!CddEngCopyRgn` at `0x14000991c`
- `WIN32K!CddEngCopyRgn` at `0x14000991c`
- `WIN32K!EngBitBlt` at `0x140009976`
- `WIN32K!EngBitBlt` at `0x140009f96`
- `WIN32K!EngBitBlt` at `0x14000a114`
- `WIN32K!EngBitBlt` at `0x14000935e`
- `WIN32K!EngBitBlt` at `0x140009434`
- `WIN32K!EngBitBlt` at `0x140009976`
- `WIN32K!EngBitBlt` at `0x140009f96`
- `WIN32K!EngBitBlt` at `0x14000a114`
- `WIN32K!CddEngCombineRgn` at `0x14000986f`
- `WIN32K!CddEngCombineRgn` at `0x1400099f5`
- `WIN32K!CddEngCombineRgn` at `0x140009a42`
- `WIN32K!CddEngCombineRgn` at `0x140009ffa`
- `WIN32K!CddEngCombineRgn` at `0x14000986f`
- `WIN32K!CddEngCombineRgn` at `0x1400099f5`
- `WIN32K!CddEngCombineRgn` at `0x140009a42`
- `WIN32K!CddEngCombineRgn` at `0x140009ffa`
- `WIN32K!EngLockSurface` at `0x14000948c`
- `WIN32K!EngLockSurface` at `0x14000948c`
- `WIN32K!EngCreateBitmap` at `0x140009470`
- `WIN32K!EngCreateBitmap` at `0x140009470`
- `WIN32K!EngDeleteSurface` at `0x14000958e`
- `WIN32K!EngDeleteSurface` at `0x14000958e`
- `WIN32K!EngUnlockSurface` at `0x14000957e`
- `WIN32K!EngUnlockSurface` at `0x14000957e`
- `WIN32K!CddEngDeleteRgn` at `0x1400098c3`
- `WIN32K!CddEngDeleteRgn` at `0x1400098c3`
- `WIN32K!CddEngCreateRectRgn` at `0x1400098f9`
- `WIN32K!CddEngCreateRectRgn` at `0x1400098f9`

## pseudocode

```c
int __fastcall DrvBitBltInternal(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _SURFOBJ *a3,
        struct _CLIPOBJ *a4,
        struct _XLATEOBJ *a5,
        RECTL *prclTrg,
        POINTL *pptlSrc,
        struct _POINTL *a8,
        struct _BRUSHOBJ *a9,
        struct _POINTL *a10,
        struct CDDPDEV *a11,
        int (*a12)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))
{
  int (*v13)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // r9
  struct _SURFOBJ *v14; // r13
  ROP4 v16; // ecx
  int v17; // esi
  DHPDEV dhpdev; // rdi
  __int64 p_iType; // rax
  int v21; // r8d
  int v22; // eax
  SURFOBJ *v23; // r11
  __int64 v24; // rbx
  int v25; // r8d
  USHORT iType; // r10
  USHORT v27; // r11
  _QWORD *v28; // rax
  SIZEL sizlBitmap; // rbx
  BOOL v30; // edi
  HSURF Bitmap; // rax
  SURFOBJ *v32; // rax
  SURFOBJ *v33; // rbx
  USHORT v34; // cx
  int v35; // eax
  LONG v36; // edx
  LONG v37; // edx
  LONG v38; // ecx
  LONG right; // edx
  int v40; // eax
  LONG x; // r9d
  LONG y; // r10d
  int v43; // ecx
  bool v44; // cc
  LONG top; // r8d
  LONG bottom; // edx
  int v47; // ecx
  SURFOBJ *v48; // rbx
  int v49; // r8d
  int v50; // r13d
  int v51; // r15d
  __int64 v52; // r8
  _QWORD *v53; // rbx
  __int64 v54; // rcx
  BOOL v55; // ebx
  _QWORD *v56; // r15
  _QWORD *v57; // rbx
  __int64 v58; // rcx
  CDDDEVLOCK *v59; // rcx
  LONG v60; // edx
  int v61; // eax
  LONG v62; // r9d
  LONG v63; // r10d
  int v64; // ecx
  LONG v65; // r8d
  LONG v66; // edx
  int v67; // ecx
  int v68; // r8d
  ROP4 v69; // ebx
  __int64 v70; // rbx
  LONG v71; // edx
  int v72; // eax
  LONG v73; // r9d
  LONG v74; // r10d
  int v75; // ecx
  LONG v76; // r8d
  LONG v77; // edx
  int v78; // ecx
  unsigned int v79; // r9d
  ULONG iSolidColor; // eax
  int v81; // r8d
  _QWORD *v82; // rax
  bool v83; // sf
  int v84; // eax
  BOOL v85; // ebx
  _QWORD *v86; // rbx
  __int64 v87; // rcx
  BOOL v88; // eax
  BOOL v89; // ebx
  _QWORD *v90; // rax
  _QWORD *v91; // rax
  struct CDDPDEV *rop4; // [rsp+50h] [rbp-B0h]
  struct CDDPDEV *rop4a; // [rsp+50h] [rbp-B0h]
  CLIPOBJ *pco; // [rsp+70h] [rbp-90h] BYREF
  ROP4 v95; // [rsp+78h] [rbp-88h]
  SURFOBJ *pso; // [rsp+80h] [rbp-80h] BYREF
  USHORT *v97; // [rsp+88h] [rbp-78h]
  int v98; // [rsp+90h] [rbp-70h]
  SURFOBJ *psoSrc; // [rsp+98h] [rbp-68h] BYREF
  int v100; // [rsp+A0h] [rbp-60h] BYREF
  __int64 RectRgn; // [rsp+A8h] [rbp-58h] BYREF
  BRUSHOBJ *pbo; // [rsp+B0h] [rbp-50h]
  SURFOBJ *psoMask; // [rsp+B8h] [rbp-48h]
  POINTL *pptlBrush; // [rsp+C0h] [rbp-40h]
  POINTL *pptlMask; // [rsp+C8h] [rbp-38h]
  HSURF hsurf; // [rsp+D0h] [rbp-30h]
  XLATEOBJ *pxlo; // [rsp+D8h] [rbp-28h]
  SURFOBJ *v108; // [rsp+E0h] [rbp-20h]
  struct _RECTL v109; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v110[16]; // [rsp+F8h] [rbp-8h] BYREF
  struct _RECTL v111; // [rsp+108h] [rbp+8h] BYREF
  struct _RECTL v112; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v113[16]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v114[16]; // [rsp+138h] [rbp+38h] BYREF
  _BYTE v115[16]; // [rsp+148h] [rbp+48h] BYREF
  POINTL v116; // [rsp+158h] [rbp+58h] BYREF
  __int64 v117; // [rsp+160h] [rbp+60h] BYREF
  int v118; // [rsp+168h] [rbp+68h]
  __int64 v119; // [rsp+170h] [rbp+70h] BYREF
  int v120; // [rsp+178h] [rbp+78h]
  RECTL v121; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v122[224]; // [rsp+190h] [rbp+90h] BYREF

  v13 = a12;
  v14 = a2;
  v16 = (unsigned int)a11;
  pptlMask = a8;
  psoSrc = (SURFOBJ *)a12;
  psoMask = a3;
  pbo = a9;
  pco = a4;
  pxlo = a5;
  pptlBrush = a10;
  v95 = (unsigned int)a11;
  if ( !a2 )
  {
    v17 = 1;
    if ( a1->iType != 1 )
      return ColorFillBitmap(
               (struct CDDPDEV *)(unsigned int)a11,
               a1,
               a3,
               a4,
               a5,
               prclTrg,
               a8,
               a9,
               a10,
               (unsigned int)a11);
    dhpdev = a1->dhpdev;
    p_iType = 76;
    goto LABEL_5;
  }
  dhpdev = a2->dhpdev;
  if ( !dhpdev || a12 != EngBitBlt )
    dhpdev = a1->dhpdev;
  p_iType = (__int64)&a2->iType;
  v17 = 1;
  iType = a2->iType;
  v97 = &a2->iType;
  if ( iType == 1 )
  {
LABEL_5:
    v97 = (USHORT *)p_iType;
LABEL_6:
    if ( a1->iType == 3 || a2 && *(_WORD *)p_iType == 3 )
    {
      WdLogSingleEntry2(3, a2, a1);
      WdLogGlobalForLineNumber = 581;
      v91 = (_QWORD *)WdLogNewEntry5_WdWarning();
      v91[3] = gCddImageInfo;
      v91[4] = (unsigned int)dword_14003E570;
      v91[5] = 215857758;
      WdLogGlobalForLineNumber = 581;
      return v17;
    }
    LODWORD(hsurf) = 0;
    memset(v122, 0, 0xD8u);
    v108 = v14;
    v98 = 0;
    v22 = 0;
    pso = 0;
    v23 = v14;
    psoSrc = 0;
    v100 = 0;
    RectRgn = 0;
    if ( v14 )
    {
      if ( *v97 == 1 )
      {
        dhpdev = v14->dhpdev;
        CDDDEVLOCK::CDDDEVLOCK((CDDDEVLOCK *)v114, *((HSEMAPHORE *)dhpdev + 365), v21);
        if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
        {
          CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v114);
        }
        else
        {
          CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
          *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
          *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 56LL) = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
          v24 = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
          CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v114);
          if ( !v24 )
          {
            v17 = 0;
            goto LABEL_174;
          }
        }
        CDDDEVLOCK::CDDDEVLOCK((CDDDEVLOCK *)v110, *((HSEMAPHORE *)dhpdev + 365), v25);
        v34 = a1->iType;
        if ( v34 == 1 && ((_DWORD)dhpdev[686] & 0x20) != 0 )
        {
          LODWORD(hsurf) = 1;
        }
        else
        {
          LODWORD(hsurf) = 0;
          if ( v34 != 1 )
          {
LABEL_91:
            v14 = (struct _SURFOBJ *)*((_QWORD *)dhpdev + 349);
            ReadFromFrameBuffer(
              (struct CDDPDEV *)dhpdev,
              pptlSrc->x,
              pptlSrc->y,
              pptlSrc->x + prclTrg->right - prclTrg->left,
              pptlSrc->y + prclTrg->bottom - prclTrg->top);
            CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v110);
            v22 = v98;
            v23 = v108;
            a4 = pco;
            goto LABEL_93;
          }
        }
        if ( !*((_BYTE *)dhpdev + 2714) && v95 == 52428 )
        {
          v35 = *((_DWORD *)dhpdev + 475);
          if ( (v35 & 1) == 0 )
          {
            if ( (v35 & 2) == 0
              || (v36 = prclTrg->right, pptlSrc->x >= v36)
              || prclTrg->left >= v36 + pptlSrc->x - prclTrg->left
              || (v37 = prclTrg->bottom, v38 = pptlSrc->y, v38 >= v37)
              || prclTrg->top >= v37 + v38 - prclTrg->top )
            {
              CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v110);
              if ( pptlSrc )
              {
                right = prclTrg->right;
                v40 = prclTrg->left - right;
                x = pptlSrc->x;
                y = pptlSrc->y;
                v43 = right - prclTrg->left;
                v44 = right < prclTrg->left;
                v109.left = pptlSrc->x;
                top = prclTrg->top;
                bottom = prclTrg->bottom;
                if ( v44 )
                  v43 = v40;
                v109.top = y;
                v109.right = x + v43;
                v47 = bottom - top;
                if ( bottom < top )
                  v47 = top - bottom;
                v109.bottom = y + v47;
              }
              else
              {
                *(_QWORD *)&v109.right = 0;
                *(_QWORD *)&v109.left = 0;
              }
              if ( a1 != v14 )
              {
                DbgLog("DrvBitBlt:DoScreenToScreenBlt psoDstOrg != psoSrcOrg\n");
                __debugbreak();
              }
              pso = a1;
              psoSrc = v14;
              CDDMULTISURFLOCK::vInit(
                (CDDMULTISURFLOCK *)v122,
                (struct CDDPDEV *)dhpdev,
                &pso,
                &pso,
                prclTrg,
                &v109,
                &v100,
                pco);
              v48 = psoMask;
              if ( psoMask && psoMask->iType )
              {
                DbgLog("Found a non STYPE_BITMAP psoMask\n");
                __debugbreak();
              }
              if ( (unsigned int)bIgnoreDeviceSurfaceUpdates(a1, &pco) )
                goto LABEL_89;
              v98 = 1;
              CDDDEVLOCK::vLock((CDDDEVLOCK *)v110);
              if ( (unsigned int)ClipRect((struct CDDPDEV *)dhpdev, (struct tagRECT *)prclTrg, pco) > 1 )
              {
                CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v117, *((struct CDDMUTEX **)dhpdev + 686), v49);
                *((_QWORD *)dhpdev + 346) = prclTrg;
                *((_QWORD *)dhpdev + 347) = pptlSrc;
                *((_QWORD *)dhpdev + 345) = pco;
                CddIssueCommand(dhpdev, 2);
                if ( v118 )
                  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v117);
                if ( !*((_BYTE *)dhpdev + 2714) )
                {
                  v50 = 0;
                  v51 = 0;
                  if ( *((_BYTE *)dhpdev + 2718) )
                  {
                    if ( (++*((_DWORD *)dhpdev + 675) & (_DWORD)dhpdev[676]) != 0 )
                    {
                      v51 = 1;
                      RectRgn = *((_QWORD *)dhpdev + 354);
                      *((_QWORD *)dhpdev + 354) = 0;
                      if ( RectRgn || (RectRgn = CddEngCreateRectRgn(0, 0, 0, 0), v50 = 1, RectRgn) )
                        CddEngCopyRgn(&RectRgn, *((_QWORD *)dhpdev + 353));
                      CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v110);
                      v55 = EngBitBlt(pso, pso, v48, pco, pxlo, prclTrg, pptlSrc, pptlMask, pbo, pptlBrush, 0xCCCCu);
                      CDDDEVLOCK::vLock((CDDDEVLOCK *)v110);
                      if ( v55 )
                      {
                        ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)dhpdev + 360));
                        if ( *((_BYTE *)dhpdev + 2713) )
                        {
                          if ( (unsigned int)CddEngOffsetRgn(
                                               RectRgn,
                                               (unsigned int)(pptlSrc->x - prclTrg->left),
                                               (unsigned int)(pptlSrc->y - prclTrg->top)) > 1 )
                          {
                            v56 = dhpdev + 704;
                            if ( (unsigned int)CddEngCombineRgn(dhpdev + 704, *((_QWORD *)dhpdev + 359), RectRgn, 1) > 1
                              && (unsigned int)CddEngOffsetRgn(
                                                 *v56,
                                                 (unsigned int)(prclTrg->left - pptlSrc->x),
                                                 (unsigned int)(prclTrg->top - pptlSrc->y)) > 1 )
                            {
                              v57 = dhpdev + 706;
                              if ( (unsigned int)CddEngCombineRgn(dhpdev + 706, *((_QWORD *)dhpdev + 359), *v56, 2) )
                              {
                                v58 = *((_QWORD *)dhpdev + 359);
                                *((_QWORD *)dhpdev + 359) = *v57;
                                *v57 = v58;
                              }
                            }
                          }
                        }
                        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)dhpdev + 360));
LABEL_75:
                        if ( v50 == 1 )
                          CddEngDeleteRgn(RectRgn);
                        else
                          *((_QWORD *)dhpdev + 354) = RectRgn;
LABEL_89:
                        v59 = (CDDDEVLOCK *)v110;
LABEL_90:
                        CDDDEVLOCK::vUnlock(v59);
                        goto LABEL_174;
                      }
                    }
                    else
                    {
                      *((_BYTE *)dhpdev + 2718) = 0;
                    }
                  }
                  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)dhpdev + 360));
                  v52 = RectRgn;
                  if ( !v51 )
                    v52 = *((_QWORD *)dhpdev + 353);
                  v53 = dhpdev + 704;
                  if ( (unsigned int)CddEngCombineRgn(dhpdev + 704, *((_QWORD *)dhpdev + 359), v52, 2) )
                  {
                    v54 = *((_QWORD *)dhpdev + 359);
                    *((_QWORD *)dhpdev + 359) = *v53;
                    *v53 = v54;
                    *((_BYTE *)dhpdev + 2713) = 1;
                  }
                  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)dhpdev + 360));
                  if ( !v51 )
                    goto LABEL_89;
                  goto LABEL_75;
                }
              }
            }
          }
        }
        goto LABEL_91;
      }
      v22 = 0;
    }
LABEL_93:
    LODWORD(v97) = 0;
    if ( a1->iType != 1 )
    {
LABEL_118:
      if ( !v98 )
      {
        if ( pptlSrc && v14 )
        {
          v71 = prclTrg->right;
          v72 = prclTrg->left - v71;
          v73 = pptlSrc->x;
          v74 = pptlSrc->y;
          v75 = v71 - prclTrg->left;
          v44 = v71 < prclTrg->left;
          v112.left = pptlSrc->x;
          v76 = prclTrg->top;
          v77 = prclTrg->bottom;
          if ( v44 )
            v75 = v72;
          v112.top = v74;
          v112.right = v73 + v75;
          v78 = v77 - v76;
          if ( v77 < v76 )
            v78 = v76 - v77;
          v112.bottom = v74 + v78;
        }
        else
        {
          *(_QWORD *)&v112.right = 0;
          *(_QWORD *)&v112.left = 0;
        }
        psoSrc = v108;
        pso = a1;
        CDDMULTISURFLOCK::vInit(
          (CDDMULTISURFLOCK *)v122,
          (struct CDDPDEV *)dhpdev,
          &pso,
          &psoSrc,
          prclTrg,
          &v112,
          &v100,
          a4);
        if ( (unsigned int)bIgnoreDeviceSurfaceUpdates(a1, &pco) )
          goto LABEL_174;
        if ( psoMask && psoMask->iType )
        {
          DbgLog("Found a non STYPE_BITMAP psoMask\n");
          __debugbreak();
        }
        a4 = pco;
      }
      v88 = EngBitBlt(pso, psoSrc, psoMask, a4, pxlo, prclTrg, pptlSrc, pptlMask, pbo, pptlBrush, v95);
      v89 = v88;
      if ( (_DWORD)v97 )
      {
        if ( v88 )
        {
          if ( v100 )
          {
            vGDIDirtyUpdate((struct CDDPDEV *)dhpdev, prclTrg, pco);
            if ( (_DWORD)hsurf )
            {
              if ( KeGetCurrentIrql() )
              {
                WdLogSingleEntry0(1);
                WdLogGlobalForLineNumber = 772;
                v90 = (_QWORD *)WdLogNewEntry5_WdAssertion();
                v90[3] = gCddImageInfo;
                v90[4] = (unsigned int)dword_14003E570;
                v90[5] = 215857758;
                WdLogGlobalForLineNumber = 772;
              }
              GetConnectedStandbyProcessName((struct CDDPDEV *)dhpdev);
              KeSetEvent(*((PRKEVENT *)dhpdev + 328), 0, 0);
            }
          }
        }
      }
      v17 = v89;
LABEL_174:
      CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)v122);
      return v17;
    }
    dhpdev = a1->dhpdev;
    if ( !v22 )
    {
      if ( pptlSrc && v14 )
      {
        v60 = prclTrg->right;
        v61 = prclTrg->left - v60;
        v62 = pptlSrc->x;
        v63 = pptlSrc->y;
        v64 = v60 - prclTrg->left;
        v44 = v60 < prclTrg->left;
        v111.left = pptlSrc->x;
        v65 = prclTrg->top;
        v66 = prclTrg->bottom;
        if ( v44 )
          v64 = v61;
        v111.top = v63;
        v111.right = v62 + v64;
        v67 = v66 - v65;
        if ( v66 < v65 )
          v67 = v65 - v66;
        v111.bottom = v63 + v67;
      }
      else
      {
        *(_QWORD *)&v111.right = 0;
        *(_QWORD *)&v111.left = 0;
      }
      pso = a1;
      psoSrc = v23;
      CDDMULTISURFLOCK::vInit(
        (CDDMULTISURFLOCK *)v122,
        (struct CDDPDEV *)dhpdev,
        &pso,
        &psoSrc,
        prclTrg,
        &v111,
        &v100,
        a4);
      if ( psoMask && psoMask->iType )
      {
        DbgLog("Found a non STYPE_BITMAP psoMask\n");
        __debugbreak();
      }
      if ( (unsigned int)bIgnoreDeviceSurfaceUpdates(a1, &pco) )
        goto LABEL_174;
      v98 = 1;
    }
    CDDDEVLOCK::CDDDEVLOCK((CDDDEVLOCK *)v113, *((HSEMAPHORE *)dhpdev + 365), v21);
    v69 = v95;
    if ( v95 == 61680 && (*((unsigned int (__fastcall **)(BRUSHOBJ *))dhpdev + 76))(pbo) )
      goto LABEL_159;
    CDDDEVLOCK::CDDDEVLOCK((CDDDEVLOCK *)v115, *((HSEMAPHORE *)dhpdev + 365), v68);
    if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
    {
      CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v115);
    }
    else
    {
      CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 56LL) = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
      v70 = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
      CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v115);
      if ( !v70 )
      {
        CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v113);
        v17 = 0;
        goto LABEL_174;
      }
      v69 = v95;
    }
    LODWORD(v97) = 1;
    if ( ((*((_BYTE *)qword_140039D10 + (unsigned __int8)v69) | *((_BYTE *)qword_140039D10 + BYTE1(v69))) & 0xB2) != 0 )
    {
      ReadFromFrameBuffer((struct CDDPDEV *)dhpdev, prclTrg->left, prclTrg->top, prclTrg->right, prclTrg->bottom);
LABEL_117:
      CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v113);
      a4 = pco;
      goto LABEL_118;
    }
    if ( ((_DWORD)dhpdev[686] & 2) != 0 || pco && pco->iDComplexity == 3 )
      goto LABEL_117;
    if ( v69 )
    {
      if ( v69 == 3855 || v69 == 61680 )
      {
        iSolidColor = pbo->iSolidColor;
        if ( pbo->iSolidColor == -1 )
          goto LABEL_117;
        LODWORD(v97) = 0;
        v79 = ~iSolidColor;
        if ( (v69 & 1) == 0 )
          v79 = iSolidColor;
        goto LABEL_134;
      }
      if ( v69 != 0xFFFF )
        goto LABEL_117;
    }
    LODWORD(v97) = 0;
    v79 = -(v69 != 0);
LABEL_134:
    *((_DWORD *)dhpdev + 696) = v79;
    switch ( *(_DWORD *)(*((_QWORD *)dhpdev + 349) + 72LL) )
    {
      case 4:
        *((_DWORD *)dhpdev + 696) = (255 * (v79 & 0x1F) / 0x1F)
                                  | (((255 * ((v79 >> 5) & 0x3F) / 0x3F)
                                    | ((255 * (unsigned int)((unsigned __int16)v79 >> 11) / 0x1F) << 8)) << 8);
        break;
      case 5:
        *((_BYTE *)dhpdev + 2787) = 0;
        break;
      case 6:
        break;
      default:
        LODWORD(v97) = 1;
        goto LABEL_117;
    }
    if ( KeGetCurrentIrql() )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 5438;
      v82 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v82[3] = gCddImageInfo;
      v82[4] = (unsigned int)dword_14003E570;
      v82[5] = 215857758;
      WdLogGlobalForLineNumber = 5438;
    }
    CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v119, *((struct CDDMUTEX **)dhpdev + 686), v81);
    *((_QWORD *)dhpdev + 346) = prclTrg;
    *((_QWORD *)dhpdev + 345) = pco;
    v83 = (int)CddIssueCommand(dhpdev, 3) < 0;
    v84 = (int)v97;
    if ( v83 )
      v84 = 1;
    LODWORD(v97) = v84;
    if ( v120 )
    {
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v119);
      v84 = (int)v97;
    }
    if ( v84 )
      goto LABEL_117;
    if ( !*((_BYTE *)dhpdev + 2718) )
      goto LABEL_155;
    if ( (++*((_DWORD *)dhpdev + 675) & (_DWORD)dhpdev[676]) == 0 )
    {
      *((_BYTE *)dhpdev + 2718) = 0;
      goto LABEL_155;
    }
    CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v113);
    v85 = EngBitBlt(pso, psoSrc, psoMask, pco, pxlo, prclTrg, pptlSrc, pptlMask, pbo, pptlBrush, v69);
    CDDDEVLOCK::vLock((CDDDEVLOCK *)v113);
    if ( !v85 )
    {
LABEL_155:
      if ( (unsigned int)ClipRect((struct CDDPDEV *)dhpdev, (struct tagRECT *)prclTrg, pco) > 1 )
      {
        ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*((_QWORD *)dhpdev + 360));
        v86 = dhpdev + 704;
        if ( (unsigned int)CddEngCombineRgn(dhpdev + 704, *((_QWORD *)dhpdev + 359), *((_QWORD *)dhpdev + 353), 2) )
        {
          v87 = *((_QWORD *)dhpdev + 359);
          *((_QWORD *)dhpdev + 359) = *v86;
          *v86 = v87;
          *((_BYTE *)dhpdev + 2713) = 1;
        }
        ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*((_QWORD *)dhpdev + 360));
      }
    }
LABEL_159:
    v59 = (CDDDEVLOCK *)v113;
    goto LABEL_90;
  }
  v27 = a1->iType;
  if ( v27 == 1 )
    goto LABEL_6;
  if ( iType != 3 && v27 != 3 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 561;
    v28 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    a3 = psoMask;
    v13 = (int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))psoSrc;
    v28[3] = gCddImageInfo;
    v28[4] = (unsigned int)dword_14003E570;
    v16 = v95;
    v28[5] = 215857758;
    p_iType = (__int64)&v14->iType;
    WdLogGlobalForLineNumber = 561;
    a4 = pco;
  }
  if ( a1->iType != 3
    || *(_WORD *)p_iType != 3
    || !a1->dhsurf
    || !v14->dhsurf
    || v13 != EngBitBlt
    || *((_QWORD *)a1->dhsurf + 1) == *((_QWORD *)v14->dhsurf + 1) )
  {
    return BitBltBitmap(
             (unsigned int (**)(void))dhpdev,
             a1,
             v14,
             a3,
             a4,
             pxlo,
             prclTrg,
             pptlSrc,
             pptlMask,
             pbo,
             pptlBrush,
             v16,
             v13);
  }
  sizlBitmap = v14->sizlBitmap;
  v108 = (SURFOBJ *)sizlBitmap;
  v30 = 0;
  Bitmap = (HSURF)EngCreateBitmap(sizlBitmap, 4 * sizlBitmap.cx, 6u, 1u, 0);
  hsurf = Bitmap;
  if ( Bitmap )
  {
    v32 = EngLockSurface(Bitmap);
    pso = v32;
    if ( v32 )
    {
      *(_QWORD *)&v121.right = __PAIR64__(HIDWORD(v108), sizlBitmap.cx);
      LODWORD(rop4) = v95;
      *(_QWORD *)&v121.left = 0;
      v116 = 0;
      if ( (unsigned int)DrvBitBltInternal(
                           v32,
                           v14,
                           psoMask,
                           0,
                           0,
                           &v121,
                           &v116,
                           pptlMask,
                           pbo,
                           pptlBrush,
                           rop4,
                           (int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))psoSrc) )
      {
        LODWORD(rop4a) = v95;
        v33 = pso;
        v30 = DrvBitBltInternal(
                a1,
                pso,
                psoMask,
                pco,
                pxlo,
                prclTrg,
                pptlSrc,
                pptlMask,
                pbo,
                pptlBrush,
                rop4a,
                (int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))psoSrc) != 0;
      }
      else
      {
        v33 = pso;
      }
      EngUnlockSurface(v33);
    }
    EngDeleteSurface(hsurf);
  }
  return v30;
}

```

## disassembly

```asm
0x14000919c  push    rbp
0x14000919e  push    rbx
0x14000919f  push    rsi
0x1400091a0  push    rdi
0x1400091a1  push    r12
0x1400091a3  push    r13
0x1400091a5  push    r14
0x1400091a7  push    r15
0x1400091a9  lea     rbp, [rsp-188h]
0x1400091b1  sub     rsp, 288h
0x1400091b8  mov     rax, cs:__security_cookie
0x1400091bf  xor     rax, rsp
0x1400091c2  mov     [rbp+1C0h+var_50], rax
0x1400091c9  mov     rax, [rbp+1C0h+arg_40]
0x1400091d0  mov     rbx, r9
0x1400091d3  mov     r9, [rbp+1C0h+arg_58]
0x1400091da  mov     r13, rdx
0x1400091dd  mov     rdx, [rbp+1C0h+arg_38]
0x1400091e4  mov     r15, rcx
0x1400091e7  mov     r11, [rbp+1C0h+arg_20]
0x1400091ee  mov     r10, [rbp+1C0h+arg_48]
0x1400091f5  mov     ecx, dword ptr [rbp+1C0h+arg_50]; struct CDDPDEV *
0x1400091fb  mov     r14, [rbp+1C0h+arg_28]
0x140009202  mov     r12, [rbp+1C0h+arg_30]
0x140009209  mov     [rbp+1C0h+var_1F8], rdx
0x14000920d  mov     [rbp+1C0h+psoSrc], r9
0x140009211  mov     [rbp+1C0h+psoMask], r8
0x140009215  mov     [rbp+1C0h+var_210], rax
0x140009219  mov     [rsp+2C0h+pco], rbx
0x14000921e  mov     [rbp+1C0h+pxlo], r11
0x140009222  mov     [rbp+1C0h+var_200], r10
0x140009226  mov     [rsp+2C0h+var_248], ecx
0x14000922a  test    r13, r13
0x14000922d  jnz     loc_140009355
0x140009233  lea     esi, [r13+1]
0x140009237  cmp     [r15+4Ch], si
0x14000923c  jz      short loc_14000926B
0x14000923e  mov     dword ptr [rsp+2C0h+pptlBrush], ecx; unsigned int
0x140009242  mov     r9, rbx; struct _CLIPOBJ *
0x140009245  mov     [rsp+2C0h+pbo], r10; struct _POINTL *
0x14000924a  mov     [rsp+2C0h+pptlMask], rax; struct _BRUSHOBJ *
0x14000924f  mov     [rsp+2C0h+pptlSrc], rdx; struct _POINTL *
0x140009254  mov     rdx, r15; struct _SURFOBJ *
0x140009257  mov     [rsp+2C0h+prclTrg], r14; struct _RECTL *
0x14000925c  mov     [rsp+2C0h+pvBits], r11; struct _XLATEOBJ *
0x140009261  call    ?ColorFillBitmap@@YAHPEAUCDDPDEV@@PEAU_SURFOBJ@@1PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@PEAU_BRUSHOBJ@@5K@Z; ColorFillBitmap(CDDPDEV *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong)
0x140009266  jmp     loc_14000A22A
0x14000926b  mov     rdi, [r15+10h]
0x14000926f  lea     rax, [r13+4Ch]
0x140009273  mov     [rbp+1C0h+var_238], rax
0x140009277  mov     ecx, 3
0x14000927c  cmp     [r15+4Ch], cx
0x140009281  jz      loc_14000A1DC
0x140009287  xor     edx, edx; Val
0x140009289  test    r13, r13
0x14000928c  jz      short loc_140009297
0x14000928e  cmp     [rax], cx
0x140009291  jz      loc_14000A1DC
0x140009297  mov     r8d, 0D8h; Size
0x14000929d  mov     dword ptr [rbp+1C0h+hsurf], edx
0x1400092a0  lea     rcx, [rbp+1C0h+var_130]; void *
0x1400092a7  call    memset
0x1400092ac  xor     ecx, ecx
0x1400092ae  mov     [rbp+1C0h+var_1E0], r13
0x1400092b2  mov     [rbp+1C0h+var_230], ecx
0x1400092b5  mov     eax, ecx
0x1400092b7  mov     [rbp+1C0h+pso], rcx
0x1400092bb  mov     r11, r13
0x1400092be  mov     [rbp+1C0h+psoSrc], rcx
0x1400092c2  mov     [rbp+1C0h+var_220], ecx
0x1400092c5  mov     [rbp+1C0h+var_218], rcx
0x1400092c9  test    r13, r13
0x1400092cc  jz      loc_140009AE3
0x1400092d2  mov     rax, [rbp+1C0h+var_238]
0x1400092d6  cmp     [rax], si
0x1400092d9  jnz     loc_140009AE1
0x1400092df  mov     rdi, [r13+10h]
0x1400092e3  lea     rcx, [rbp+1C0h+var_188]; this
0x1400092e7  mov     rdx, [rdi+0B68h]; HSEMAPHORE
0x1400092ee  call    ??0CDDDEVLOCK@@QEAA@PEAUHSEMAPHORE__@@H@Z; CDDDEVLOCK::CDDDEVLOCK(HSEMAPHORE__ *,int)
0x1400092f3  mov     rax, [rdi+0AE8h]
0x1400092fa  xor     ebx, ebx
0x1400092fc  cmp     [rax+30h], rbx
0x140009300  jnz     loc_1400095F3
0x140009306  mov     rcx, rdi; struct CDDPDEV *
0x140009309  call    ?CddAllocShadowSysMem@@YAXQEAUCDDPDEV@@@Z; CddAllocShadowSysMem(CDDPDEV * const)
0x14000930e  mov     rcx, [rdi+0AE8h]
0x140009315  mov     rax, [rdi+9F8h]
0x14000931c  mov     [rcx+30h], rax
0x140009320  mov     rcx, [rdi+0AE8h]
0x140009327  mov     rax, [rcx+30h]
0x14000932b  mov     [rcx+38h], rax
0x14000932f  lea     rcx, [rbp+1C0h+var_188]; this
0x140009333  mov     rax, [rdi+0AE8h]
0x14000933a  mov     rbx, [rax+30h]
0x14000933e  call    ?vUnlock@CDDDEVLOCK@@QEAAXXZ; CDDDEVLOCK::vUnlock(void)
0x140009343  xor     eax, eax
0x140009345  test    rbx, rbx
0x140009348  jnz     loc_1400095FE
0x14000934e  mov     esi, eax
0x140009350  jmp     loc_14000A1CE
0x140009355  mov     rdi, [r13+10h]
0x140009359  test    rdi, rdi
0x14000935c  jz      short loc_140009367
0x14000935e  cmp     r9, cs:__imp_EngBitBlt
0x140009365  jz      short loc_14000936B
0x140009367  mov     rdi, [r15+10h]
0x14000936b  lea     rax, [r13+4Ch]
0x14000936f  mov     esi, 1
0x140009374  movzx   r10d, word ptr [rax]
0x140009378  mov     [rbp+1C0h+var_238], rax
0x14000937c  cmp     r10w, si
0x140009380  jz      loc_140009273
0x140009386  movzx   r11d, word ptr [r15+4Ch]
0x14000938b  cmp     r11w, si
0x14000938f  jz      loc_140009277
0x140009395  lea     edx, [rsi+2]
0x140009398  cmp     r10w, dx
0x14000939c  jz      short loc_140009404
0x14000939e  cmp     r11w, dx
0x1400093a2  jz      short loc_140009404
0x1400093a4  mov     ecx, esi
0x1400093a6  call    cs:__imp_WdLogSingleEntry0
0x1400093ad  nop     dword ptr [rax+rax+00h]
0x1400093b2  mov     ebx, 231h
0x1400093b7  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400093bd  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400093c4  nop     dword ptr [rax+rax+00h]
0x1400093c9  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400093d0  lea     edx, [rsi+2]
0x1400093d3  mov     r8, [rbp+1C0h+psoMask]
0x1400093d7  mov     r9, [rbp+1C0h+psoSrc]
0x1400093db  mov     [rax+18h], rcx
0x1400093df  mov     ecx, cs:dword_14003E570
0x1400093e5  mov     [rax+20h], rcx
0x1400093e9  mov     ecx, [rsp+2C0h+var_248]
0x1400093ed  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400093f5  lea     rax, [r13+4Ch]
0x1400093f9  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400093ff  mov     rbx, [rsp+2C0h+pco]
0x140009404  cmp     [r15+4Ch], dx
0x140009409  jnz     loc_1400095A1
0x14000940f  cmp     [rax], dx
0x140009412  jnz     loc_1400095A1
0x140009418  mov     rdx, [r15]
0x14000941b  xor     r10d, r10d
0x14000941e  test    rdx, rdx
0x140009421  jz      loc_1400095A1
0x140009427  mov     rax, [r13+0]
0x14000942b  test    rax, rax
0x14000942e  jz      loc_1400095A1
0x140009434  cmp     r9, cs:__imp_EngBitBlt
0x14000943b  jnz     loc_1400095A1
0x140009441  mov     rax, [rax+8]
0x140009445  cmp     [rdx+8], rax
0x140009449  jz      loc_1400095A1
0x14000944f  mov     rbx, [r13+20h]
0x140009453  lea     r8d, [r10+6]; iFormat
0x140009457  mov     r9d, esi; fl
0x14000945a  mov     [rbp+1C0h+var_1E0], rbx
0x14000945e  mov     rcx, rbx; sizl
0x140009461  mov     [rsp+2C0h+pvBits], r10; pvBits
0x140009466  mov     edi, r10d
0x140009469  lea     edx, ds:0[rbx*4]; lWidth
0x140009470  call    cs:__imp_EngCreateBitmap
0x140009477  nop     dword ptr [rax+rax+00h]
0x14000947c  mov     [rbp+1C0h+hsurf], rax
0x140009480  test    rax, rax
0x140009483  jz      loc_14000959A
0x140009489  mov     rcx, rax; hsurf
0x14000948c  call    cs:__imp_EngLockSurface
0x140009493  nop     dword ptr [rax+rax+00h]
0x140009498  xor     edx, edx
0x14000949a  mov     [rbp+1C0h+pso], rax
0x14000949e  test    rax, rax
0x1400094a1  jz      loc_14000958A
0x1400094a7  mov     ecx, dword ptr [rbp+1C0h+var_1E0+4]
0x1400094aa  xor     r9d, r9d; struct _CLIPOBJ *
0x1400094ad  mov     r8, [rbp+1C0h+psoMask]; struct _SURFOBJ *
0x1400094b1  mov     [rbp+1C0h+var_140.bottom], ecx
0x1400094b7  mov     rcx, [rbp+1C0h+psoSrc]
0x1400094bb  mov     [rsp+2C0h+var_268], rcx; int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int)
0x1400094c0  mov     rcx, [rbp+1C0h+var_200]
0x1400094c4  mov     [rbp+1C0h+var_140.right], ebx
0x1400094ca  mov     ebx, [rsp+2C0h+var_248]
0x1400094ce  mov     [rsp+2C0h+rop4], ebx; struct CDDPDEV *
0x1400094d2  mov     [rsp+2C0h+pptlBrush], rcx; struct _POINTL *
0x1400094d7  mov     rcx, [rbp+1C0h+var_210]
0x1400094db  mov     [rsp+2C0h+pbo], rcx; struct _BRUSHOBJ *
0x1400094e0  mov     rcx, [rbp+1C0h+var_1F8]
0x1400094e4  mov     [rsp+2C0h+pptlMask], rcx; struct _POINTL *
0x1400094e9  lea     rcx, [rbp+1C0h+var_168]
0x1400094ed  mov     [rsp+2C0h+pptlSrc], rcx; POINTL *
0x1400094f2  lea     rcx, [rbp+1C0h+var_140]
0x1400094f9  mov     [rsp+2C0h+prclTrg], rcx; RECTL *
0x1400094fe  mov     rcx, rax; struct _SURFOBJ *
0x140009501  mov     [rsp+2C0h+pvBits], rdx; struct _XLATEOBJ *
0x140009506  mov     qword ptr [rbp+1C0h+var_140.left], rdx
0x14000950d  mov     qword ptr [rbp+1C0h+var_168.x], rdx
0x140009511  mov     rdx, r13; struct _SURFOBJ *
0x140009514  call    ?DrvBitBltInternal@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@4PEAU_BRUSHOBJ@@4KP6AH0001234454K@Z@Z; DrvBitBltInternal(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))
0x140009519  test    eax, eax
0x14000951b  jz      short loc_140009577
0x14000951d  mov     rax, [rbp+1C0h+psoSrc]
0x140009521  mov     rcx, r15; struct _SURFOBJ *
0x140009524  mov     r9, [rsp+2C0h+pco]; struct _CLIPOBJ *
0x140009529  mov     r8, [rbp+1C0h+psoMask]; struct _SURFOBJ *
0x14000952d  mov     [rsp+2C0h+var_268], rax; int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int)
0x140009532  mov     rax, [rbp+1C0h+var_200]
0x140009536  mov     [rsp+2C0h+rop4], ebx; struct CDDPDEV *
0x14000953a  mov     rbx, [rbp+1C0h+pso]
0x14000953e  mov     [rsp+2C0h+pptlBrush], rax; struct _POINTL *
0x140009543  mov     rdx, rbx; struct _SURFOBJ *
0x140009546  mov     rax, [rbp+1C0h+var_210]
0x14000954a  mov     [rsp+2C0h+pbo], rax; struct _BRUSHOBJ *
0x14000954f  mov     rax, [rbp+1C0h+var_1F8]
0x140009553  mov     [rsp+2C0h+pptlMask], rax; struct _POINTL *
0x140009558  mov     rax, [rbp+1C0h+pxlo]
0x14000955c  mov     [rsp+2C0h+pptlSrc], r12; POINTL *
0x140009561  mov     [rsp+2C0h+prclTrg], r14; RECTL *
0x140009566  mov     [rsp+2C0h+pvBits], rax; struct _XLATEOBJ *
0x14000956b  call    ?DrvBitBltInternal@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@4PEAU_BRUSHOBJ@@4KP6AH0001234454K@Z@Z; DrvBitBltInternal(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))
0x140009570  test    eax, eax
0x140009572  cmovnz  edi, esi
0x140009575  jmp     short loc_14000957B
0x140009577  mov     rbx, [rbp+1C0h+pso]
0x14000957b  mov     rcx, rbx; pso
0x14000957e  call    cs:__imp_EngUnlockSurface
0x140009585  nop     dword ptr [rax+rax+00h]
0x14000958a  mov     rcx, [rbp+1C0h+hsurf]; hsurf
0x14000958e  call    cs:__imp_EngDeleteSurface
0x140009595  nop     dword ptr [rax+rax+00h]
0x14000959a  mov     eax, edi
0x14000959c  jmp     loc_14000A22A
0x1400095a1  mov     rax, [rbp+1C0h+var_200]
0x1400095a5  mov     rdx, r15; struct _SURFOBJ *
0x1400095a8  mov     [rsp+2C0h+var_260], r9; int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int)
0x1400095ad  mov     r9, r8; struct _SURFOBJ *
0x1400095b0  mov     dword ptr [rsp+2C0h+var_268], ecx; unsigned int
0x1400095b4  mov     r8, r13; struct _SURFOBJ *
0x1400095b7  mov     qword ptr [rsp+2C0h+rop4], rax; struct _POINTL *
0x1400095bc  mov     rcx, rdi; struct CDDPDEV *
0x1400095bf  mov     rax, [rbp+1C0h+var_210]
0x1400095c3  mov     [rsp+2C0h+pptlBrush], rax; struct _BRUSHOBJ *
0x1400095c8  mov     rax, [rbp+1C0h+var_1F8]
0x1400095cc  mov     [rsp+2C0h+pbo], rax; struct _POINTL *
0x1400095d1  mov     rax, [rbp+1C0h+pxlo]
0x1400095d5  mov     [rsp+2C0h+pptlMask], r12; struct _POINTL *
0x1400095da  mov     [rsp+2C0h+pptlSrc], r14; RECTL *
0x1400095df  mov     [rsp+2C0h+prclTrg], rax; struct _XLATEOBJ *
0x1400095e4  mov     [rsp+2C0h+pvBits], rbx; struct _CLIPOBJ *
0x1400095e9  call    ?BitBltBitmap@@YAHPEAUCDDPDEV@@PEAU_SURFOBJ@@11PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@5PEAU_BRUSHOBJ@@5KP6AH1112345565K@Z@Z; BitBltBitmap(CDDPDEV *,_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))
0x1400095ee  jmp     loc_14000A22A
0x1400095f3  lea     rcx, [rbp+1C0h+var_188]; this
0x1400095f7  call    ?vUnlock@CDDDEVLOCK@@QEAAXXZ; CDDDEVLOCK::vUnlock(void)
0x1400095fc  jmp     short loc_140009600
0x1400095fe  xor     ebx, ebx
0x140009600  mov     rdx, [rdi+0B68h]; HSEMAPHORE
0x140009607  lea     rcx, [rbp+1C0h+var_1C8]; this
0x14000960b  call    ??0CDDDEVLOCK@@QEAA@PEAUHSEMAPHORE__@@H@Z; CDDDEVLOCK::CDDDEVLOCK(HSEMAPHORE__ *,int)
0x140009610  movzx   ecx, word ptr [r15+4Ch]
0x140009615  cmp     si, cx
0x140009618  jnz     short loc_140009629
0x14000961a  mov     eax, [rdi+0AB8h]
0x140009620  test    al, 20h
0x140009622  jz      short loc_140009629
0x140009624  mov     dword ptr [rbp+1C0h+hsurf], esi
0x140009627  jmp     short loc_140009635
0x140009629  mov     dword ptr [rbp+1C0h+hsurf], ebx
0x14000962c  cmp     cx, si
0x14000962f  jnz     loc_140009A97
0x140009635  cmp     [rdi+0A9Ah], bl
0x14000963b  jnz     loc_140009A97
0x140009641  cmp     [rsp+2C0h+var_248], 0CCCCh
0x140009649  jnz     loc_140009A97
0x14000964f  mov     eax, [rdi+76Ch]
0x140009655  test    sil, al
0x140009658  jnz     loc_140009A97
0x14000965e  test    al, 2
0x140009660  jz      short loc_140009696
0x140009662  mov     edx, [r14+8]
0x140009666  mov     ecx, [r12]
0x14000966a  cmp     ecx, edx
0x14000966c  jge     short loc_140009696
0x14000966e  mov     eax, [r14]
0x140009671  sub     ecx, eax
0x140009673  add     ecx, edx
0x140009675  cmp     eax, ecx
0x140009677  jge     short loc_140009696
0x140009679  mov     edx, [r14+0Ch]
0x14000967d  mov     ecx, [r12+4]
0x140009682  cmp     ecx, edx
0x140009684  jge     short loc_140009696
0x140009686  mov     eax, [r14+4]
0x14000968a  sub     ecx, eax
0x14000968c  add     ecx, edx
0x14000968e  cmp     eax, ecx
0x140009690  jl      loc_140009A97
0x140009696  lea     rcx, [rbp+1C0h+var_1C8]; this
0x14000969a  call    ?vUnlock@CDDDEVLOCK@@QEAAXXZ; CDDDEVLOCK::vUnlock(void)
  ... truncated ...
```
