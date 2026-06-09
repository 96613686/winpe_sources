# DrvStretchBltROPInternal(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong,_BRUSHOBJ *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong),int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong))

- ea: `0x1400161b0`
- end: `0x14001732a`
- name: `?DrvStretchBltROPInternal@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54KPEAU_BRUSHOBJ@@KP6AH0001254464K@ZP6AH0001234554K@Z@Z`
- size: `4474`
- prototype: `int(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int, struct _BRUSHOBJ *, unsigned int, int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int), int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int))`
- caller_count: `2`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x140016110`
- `0x1400261a0`

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
- `0x14000ef80`
- `0x1400160c8`
- `0x1400161b0`
- `0x14001d458`
- `0x1400200e8`
- `0x1400224a0`
- `0x1400226b0`
- `0x1400248f8`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140016611`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016b8a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016611`
- `ntoskrnl!KeWaitForSingleObject` at `0x140016b8a`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400169c7`
- `ntoskrnl!KeReleaseSemaphore` at `0x140016d21`
- `ntoskrnl!KeReleaseSemaphore` at `0x140016e96`
- `ntoskrnl!KeReleaseSemaphore` at `0x140017044`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400169c7`
- `ntoskrnl!KeReleaseSemaphore` at `0x140016d21`
- `ntoskrnl!KeReleaseSemaphore` at `0x140016e96`
- `ntoskrnl!KeReleaseSemaphore` at `0x140017044`
- `ntoskrnl!DbgPrint` at `0x140016dd6`
- `ntoskrnl!DbgPrint` at `0x140016dd6`
- `ntoskrnl!KdDebuggerEnabled` at `0x140016dc3`
- `watchdog!WdLogSingleEntry2` at `0x1400172ce`
- `watchdog!WdLogSingleEntry2` at `0x1400172ce`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x1400172e5`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x1400172e5`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001665a`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400168c2`
- `watchdog!WdLogNewEntry5_WdError` at `0x140016bd2`
- `watchdog!WdLogNewEntry5_WdError` at `0x140016dff`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001665a`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400168c2`
- `watchdog!WdLogNewEntry5_WdError` at `0x140016bd2`
- `watchdog!WdLogNewEntry5_WdError` at `0x140016dff`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001635b`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001635b`
- `watchdog!WdLogSingleEntry0` at `0x140016345`
- `watchdog!WdLogSingleEntry0` at `0x140016643`
- `watchdog!WdLogSingleEntry0` at `0x14001668d`
- `watchdog!WdLogSingleEntry0` at `0x1400168ab`
- `watchdog!WdLogSingleEntry0` at `0x1400169eb`
- `watchdog!WdLogSingleEntry0` at `0x140016bbb`
- `watchdog!WdLogSingleEntry0` at `0x140016c05`
- `watchdog!WdLogSingleEntry0` at `0x140016de6`
- `watchdog!WdLogSingleEntry0` at `0x140016345`
- `watchdog!WdLogSingleEntry0` at `0x140016643`
- `watchdog!WdLogSingleEntry0` at `0x14001668d`
- `watchdog!WdLogSingleEntry0` at `0x1400168ab`
- `watchdog!WdLogSingleEntry0` at `0x1400169eb`
- `watchdog!WdLogSingleEntry0` at `0x140016bbb`
- `watchdog!WdLogSingleEntry0` at `0x140016c05`
- `watchdog!WdLogSingleEntry0` at `0x140016de6`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400166a4`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140016a02`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140016c1c`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400166a4`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140016a02`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140016c1c`
- `WIN32K!EngStretchBltROP` at `0x140016f4b`
- `WIN32K!EngStretchBltROP` at `0x14001728d`
- `WIN32K!EngStretchBltROP` at `0x140016f4b`
- `WIN32K!EngStretchBltROP` at `0x14001728d`
- `WIN32K!EngBitBlt` at `0x14001639d`
- `WIN32K!EngBitBlt` at `0x1400167c8`
- `WIN32K!EngReleaseSemaphore` at `0x140017117`
- `WIN32K!EngReleaseSemaphore` at `0x140017132`
- `WIN32K!EngReleaseSemaphore` at `0x140017117`
- `WIN32K!EngReleaseSemaphore` at `0x140017132`
- `WIN32K!EngAcquireSemaphore` at `0x1400170b2`
- `WIN32K!EngAcquireSemaphore` at `0x1400170b2`

## string_xrefs

- `0x140016dcf`: `Ivalid pco in GDIBITMAPACCESS2::StartAccessDst`

## pseudocode

```c
__int64 __fastcall DrvStretchBltROPInternal(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _SURFOBJ *a3,
        struct _CLIPOBJ *a4,
        struct _XLATEOBJ *a5,
        struct tagCOLORADJUSTMENT *a6,
        struct _POINTL *a7,
        struct _RECTL *prclDest,
        struct _RECTL *a9,
        struct _POINTL *a10,
        ULONG iMode,
        struct _BRUSHOBJ *a12,
        DWORD a13,
        int (*a14)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int),
        int (*a15)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int))
{
  int v17; // edi
  int v18; // r15d
  DHPDEV dhpdev; // rbx
  int v20; // edx
  int v21; // esi
  unsigned int (*v22)(void); // rax
  __int64 v23; // rdx
  USHORT iType; // ax
  USHORT v25; // cx
  _QWORD *v26; // rax
  DHSURF dhsurf; // rdx
  DHSURF v28; // r13
  int v29; // ecx
  LONG right; // eax
  LONG bottom; // eax
  BOOL v32; // ecx
  BOOL v33; // r9d
  bool v34; // zf
  ULONG v35; // ecx
  int v36; // edx
  int v37; // r11d
  int v38; // r15d
  unsigned int v39; // eax
  unsigned int v40; // edi
  SURFOBJ *v41; // rdi
  char v42; // cl
  _QWORD *v43; // rbx
  NTSTATUS v44; // ecx
  _QWORD *v45; // rax
  _QWORD *v46; // rax
  SURFOBJ *v47; // rbx
  SURFOBJ *v48; // rbx
  RECTL *v49; // r13
  CStagingPool *v50; // rbx
  _QWORD *v51; // rax
  SURFOBJ *v52; // rbx
  __int64 v53; // rcx
  struct _KTHREAD *v54; // rdx
  _QWORD *v55; // rax
  SURFOBJ *v56; // rbx
  __int64 v57; // rcx
  struct _KTHREAD *v58; // rdx
  CLIPOBJ *v59; // r14
  unsigned __int8 v60; // r15
  char v61; // cl
  unsigned __int8 v62; // dl
  _QWORD *v63; // rdi
  NTSTATUS v64; // eax
  _QWORD *v65; // rax
  _QWORD *v66; // rax
  struct _KTHREAD *v67; // rdx
  _QWORD *v68; // rax
  SURFOBJ *v69; // rdi
  __int64 v70; // rcx
  struct _KTHREAD *v71; // rdx
  int v72; // r8d
  BOOL v73; // eax
  int v74; // ecx
  unsigned int v75; // esi
  SURFOBJ *v76; // rbx
  __int64 v77; // rcx
  struct _KTHREAD *v78; // rdx
  HSEMAPHORE v80; // rdi
  int v81; // r15d
  BOOL v82; // r13d
  struct _SURFOBJ *v83; // r15
  DWORD v84; // esi
  RECTL *v85; // r14
  _QWORD *v86; // rax
  int prclSrc; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v88; // [rsp+70h] [rbp-90h]
  int v89; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD rop4; // [rsp+78h] [rbp-88h]
  int v91; // [rsp+7Ch] [rbp-84h]
  CLIPOBJ *pco; // [rsp+80h] [rbp-80h] BYREF
  RECTL *v93; // [rsp+88h] [rbp-78h]
  SURFOBJ *v94; // [rsp+90h] [rbp-70h] BYREF
  int v95; // [rsp+98h] [rbp-68h]
  int v96; // [rsp+9Ch] [rbp-64h]
  SURFOBJ *v97; // [rsp+A0h] [rbp-60h] BYREF
  int (*v98)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // [rsp+A8h] [rbp-58h]
  XLATEOBJ *pxlo; // [rsp+B0h] [rbp-50h]
  struct _SURFOBJ *v100; // [rsp+B8h] [rbp-48h]
  SURFOBJ *psoMask; // [rsp+C0h] [rbp-40h]
  BRUSHOBJ *pbo; // [rsp+C8h] [rbp-38h]
  POINTL *pptlMask; // [rsp+D0h] [rbp-30h]
  POINTL *pptlHTOrg; // [rsp+D8h] [rbp-28h]
  COLORADJUSTMENT *pca; // [rsp+E0h] [rbp-20h]
  __int128 v106; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v107; // [rsp+F8h] [rbp-8h]
  __int128 v108; // [rsp+108h] [rbp+8h]
  __int64 v109; // [rsp+118h] [rbp+18h] BYREF
  unsigned int v110; // [rsp+120h] [rbp+20h]
  __int64 v111; // [rsp+128h] [rbp+28h]
  int v112; // [rsp+130h] [rbp+30h]
  _BYTE v113[24]; // [rsp+138h] [rbp+38h] BYREF
  SURFOBJ *psoSrc[8]; // [rsp+150h] [rbp+50h] BYREF
  CStagingPool *v115[2]; // [rsp+190h] [rbp+90h]
  struct _RECTL v116; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v117[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  SURFOBJ *psoDest[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  struct CDDPDEV *v119; // [rsp+230h] [rbp+130h]
  CLIPOBJ *v120; // [rsp+238h] [rbp+138h]
  DHSURF v121; // [rsp+240h] [rbp+140h]
  SURFOBJ *v122; // [rsp+248h] [rbp+148h]
  struct _RECTL *v123; // [rsp+250h] [rbp+150h]
  __int64 v124; // [rsp+258h] [rbp+158h] BYREF
  int v125; // [rsp+260h] [rbp+160h]
  __int64 v126; // [rsp+268h] [rbp+168h]
  char v127; // [rsp+270h] [rbp+170h]

  pxlo = a5;
  v17 = prclDest->right - prclDest->left;
  v18 = prclDest->bottom - prclDest->top;
  pca = a6;
  pptlHTOrg = a7;
  pptlMask = a10;
  pbo = a12;
  pco = a4;
  dhpdev = a1->dhpdev;
  rop4 = a13;
  v94 = a2;
  v100 = a1;
  v98 = a14;
  v106 = 0;
  psoMask = a3;
  v20 = a9->right - a9->left;
  v21 = a9->bottom - a9->top;
  v107 = 0;
  v93 = a9;
  v108 = 0;
  v22 = (unsigned int (*)(void))*((_QWORD *)dhpdev + 10);
  v97 = a1;
  v95 = v20;
  v96 = v21;
  v91 = v17;
  v112 = 1;
  v111 = 0;
  if ( v22() )
  {
    *((_QWORD *)&v108 + 1) = 0;
    LODWORD(v106) = a2->iType;
    DWORD1(v106) = a1->iType;
    *((_QWORD *)&v106 + 1) = __PAIR64__(v21, v95);
    LODWORD(v108) = (unsigned __int16)rop4;
    *(_QWORD *)((char *)&v108 + 4) = (unsigned __int16)iMode;
    v107 = __PAIR64__(v18, v17);
    CDDETWPROFILER::Init((CDDETWPROFILER *)&v109, (struct CDDPDEV *)dhpdev, 0xBD4u, (struct _DXGKETW_PARAMS *)&v106, 0);
  }
  iType = a2->iType;
  if ( iType == 1 || (v25 = a1->iType, v25 == 1) )
  {
    v80 = (HSEMAPHORE)*((_QWORD *)dhpdev + 365);
    v75 = 0;
    v81 = 0;
    if ( v80 )
    {
      EngAcquireSemaphore(v80);
      v81 = 1;
    }
    if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
    {
      if ( v80 && v81 )
        EngReleaseSemaphore(v80);
      v82 = 1;
    }
    else
    {
      CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
      v23 = *((_QWORD *)dhpdev + 349);
      *(_QWORD *)(v23 + 56) = *(_QWORD *)(v23 + 48);
      v82 = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) != 0;
      if ( v80 && v81 )
        EngReleaseSemaphore(v80);
    }
    if ( !v82 )
      goto LABEL_143;
    v83 = v100;
    if ( v100->iType == 3 || a2 && a2->iType == 3 )
    {
      WdLogSingleEntry2(3, a2, v100);
      WdLogGlobalForLineNumber = 581;
      v86 = (_QWORD *)WdLogNewEntry5_WdWarning();
      v86[3] = gCddImageInfo;
      v86[4] = (unsigned int)dword_14003E570;
      v86[5] = 215857758;
      WdLogGlobalForLineNumber = 581;
    }
    else
    {
      v84 = rop4;
      if ( ((*((_BYTE *)qword_140039D10 + (unsigned __int8)rop4) | *((_BYTE *)qword_140039D10 + BYTE1(rop4))) & 0xB2) != 0 )
        ReadFromFrameBuffer((struct CDDPDEV *)dhpdev, prclDest->left, prclDest->top, prclDest->right, prclDest->bottom);
      v85 = v93;
      v89 = 0;
      CDDMULTISURFLOCK::vInit((CDDMULTISURFLOCK *)v117, (struct CDDPDEV *)dhpdev, &v97, &v94, prclDest, v93, &v89, pco);
      if ( !bIgnoreDeviceSurfaceUpdates(v83, &pco) )
      {
        if ( psoMask && psoMask->iType )
        {
          DbgLog("Found a non STYPE_BITMAP psoMask\n");
          __debugbreak();
        }
        v75 = EngStretchBltROP(v97, v94, psoMask, pco, pxlo, pca, pptlHTOrg, prclDest, v85, pptlMask, iMode, pbo, v84);
        if ( v75 && v89 == 1 )
          vGDIDirtyUpdate((struct CDDPDEV *)dhpdev, (struct tagRECT *)prclDest, pco);
        CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)v117);
        goto LABEL_143;
      }
      CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)v117);
    }
    v40 = 1;
    goto LABEL_173;
  }
  if ( iType != 3 && v25 != 3 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 561;
    v26 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v26[3] = gCddImageInfo;
    v26[4] = (unsigned int)dword_14003E570;
    v26[5] = 215857758;
    WdLogGlobalForLineNumber = 561;
  }
  dhsurf = a1->dhsurf;
  v94 = (SURFOBJ *)a1->dhsurf;
  if ( v98 == EngBitBlt )
    v28 = a2->dhsurf;
  else
    v28 = 0;
  if ( dhsurf )
  {
    dhpdev = (DHPDEV)*((_QWORD *)dhsurf + 1);
  }
  else if ( v28 )
  {
    dhpdev = (DHPDEV)*((_QWORD *)v28 + 1);
  }
  v29 = v91;
  if ( v91 >= 0 )
  {
    v116.left = prclDest->left;
    right = prclDest->right;
    v89 = 0;
  }
  else
  {
    v29 = -v91;
    v116.left = prclDest->right;
    right = prclDest->left;
    v89 = 1;
  }
  v116.right = right;
  v91 = v29;
  if ( v18 >= 0 )
  {
    v116.top = prclDest->top;
    bottom = prclDest->bottom;
    LODWORD(v97) = 0;
  }
  else
  {
    v18 = -v18;
    v116.top = prclDest->bottom;
    bottom = prclDest->top;
    LODWORD(v97) = 1;
  }
  v116.bottom = bottom;
  CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(
    (CDDMULTIBITMAPLOCK *)v113,
    (struct CddBitmap *)dhsurf,
    (struct CddBitmap *)v28);
  v32 = v91 < v95 || v18 < v96;
  v33 = v91 > v95 || v18 > v96;
  v34 = !v32;
  v35 = iMode;
  if ( v34 )
  {
    if ( iMode != 4 )
      v35 = 3;
    iMode = v35;
  }
  v36 = v94 && ((__int64)v94[1].pvBits & 1) != 0 && !psoMask && v35 == 3 && rop4 == 52428;
  v37 = v89;
  if ( v89 | (unsigned int)v97 )
    v36 = ((_DWORD)dhpdev[475] & 0x200000) != 0 ? v36 : 0;
  if ( v93->bottom - v93->top > *((_DWORD *)dhpdev + 619) || v93->right - v93->left > *((_DWORD *)dhpdev + 618) )
    v36 = 0;
  v38 = 0;
  DWORD2(v107) = v36;
  v89 = 0;
  if ( v36 )
  {
    v39 = StretchBltAccelerated(
            (struct CDDPDEV *)dhpdev,
            v100,
            a2,
            pco,
            pxlo,
            &v116,
            v93,
            iMode,
            v37,
            (int)v97,
            v33,
            &v89,
            v98,
            a15);
    v38 = v89;
    v40 = v39;
    if ( !v89 )
      goto LABEL_114;
  }
  v41 = v94;
  GDIBITMAPACCESS2::GDIBITMAPACCESS2(
    (GDIBITMAPACCESS2 *)v117,
    (struct CDDPDEV *)dhpdev,
    (struct CddBitmap *)v28,
    (struct CddBitmap *)v94);
  memset(psoSrc, 0, sizeof(psoSrc));
  *(_OWORD *)v115 = 0;
  if ( v28 )
  {
    v42 = v127;
    if ( v127 )
    {
      v43 = (_QWORD *)*((_QWORD *)v119 + 895);
      if ( (struct _KTHREAD *)v43[4] != KeGetCurrentThread() )
      {
        v44 = KeWaitForSingleObject(v43, Executive, 0, 0, 0);
        if ( v44 != 258 )
        {
          v43[4] = KeGetCurrentThread();
          if ( v44 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 618;
            v45 = (_QWORD *)WdLogNewEntry5_WdError();
            v45[3] = gCddImageInfo;
            v45[4] = (unsigned int)dword_14003E570;
            v45[5] = 215857758;
            WdLogGlobalForLineNumber = 618;
            goto LABEL_53;
          }
        }
      }
      v42 = v127;
    }
    LOBYTE(prclSrc) = v42 == 0;
    if ( (*(int (__fastcall **)(DHSURF, RECTL *, RECTL *, _QWORD, int, int, __int64 *, _QWORD *, int))(*(_QWORD *)v28 + 56LL))(
           v28,
           v93,
           v93,
           0,
           1,
           1,
           &v124,
           v117,
           prclSrc) < 0 )
    {
LABEL_53:
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 6741;
      v46 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v46[3] = gCddImageInfo;
      v46[4] = (unsigned int)dword_14003E570;
      v46[5] = 215857758;
      WdLogGlobalForLineNumber = 6741;
      if ( v115[0] )
      {
        psoSrc[0]->dhpdev = (DHPDEV)v115[1];
        CStagingPool::ReleaseGdiSurface(v115[0], (struct CDDBITMAP_GDIDESC *)psoSrc);
      }
      if ( v121 )
        (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v121 + 128LL))(v121, v117);
      v47 = v122;
      if ( !v122 )
        goto LABEL_109;
      if ( v125 )
      {
LABEL_108:
        (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v47->dhsurf + 16))(v47, psoDest);
LABEL_109:
        v57 = *((_QWORD *)v119 + 895);
        v67 = *(struct _KTHREAD **)(v57 + 32);
        if ( v67 != KeGetCurrentThread() || !v67 )
          goto LABEL_113;
        *(_QWORD *)(v57 + 32) = 0;
LABEL_112:
        KeReleaseSemaphore((PRKSEMAPHORE)v57, 0, 1, 0);
LABEL_113:
        v40 = 1;
LABEL_114:
        CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v113);
LABEL_173:
        CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v109);
        return v40;
      }
LABEL_107:
      (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))v122->dhsurf + 8))(
        v122,
        psoDest,
        v123,
        v120,
        v126);
      goto LABEL_108;
    }
    v48 = (SURFOBJ *)v117[0];
    v121 = v28;
    v120 = 0;
  }
  else
  {
    if ( v98 != EngBitBlt )
    {
      v49 = v93;
      v50 = (CStagingPool *)(dhpdev + 1376);
      if ( (int)CStagingPool::GetGdiSurface(
                  v50,
                  a2->sizlBitmap.cx,
                  a2->sizlBitmap.cy,
                  (const struct tagRECT *)v93,
                  (struct CDDBITMAP_GDIDESC *)psoSrc,
                  1u) < 0 )
      {
        WdLogSingleEntry0(4);
        WdLogGlobalForLineNumber = 6750;
        v55 = (_QWORD *)WdLogNewEntry5_WdEvent();
        v55[3] = gCddImageInfo;
        v55[4] = (unsigned int)dword_14003E570;
        v55[5] = 215857758;
        WdLogGlobalForLineNumber = 6750;
        if ( v115[0] )
        {
          psoSrc[0]->dhpdev = (DHPDEV)v115[1];
          CStagingPool::ReleaseGdiSurface(v115[0], (struct CDDBITMAP_GDIDESC *)psoSrc);
        }
        if ( v121 )
          (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v121 + 128LL))(v121, v117);
        v56 = v122;
        if ( v122 )
        {
          if ( !v125 )
            (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))v122->dhsurf + 8))(
              v122,
              psoDest,
              v123,
              v120,
              v126);
          (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v56->dhsurf + 16))(v56, psoDest);
        }
        v57 = *((_QWORD *)v119 + 895);
        v58 = *(struct _KTHREAD **)(v57 + 32);
        if ( v58 != KeGetCurrentThread() || !v58 )
          goto LABEL_113;
        *(_QWORD *)(v57 + 32) = 0;
        goto LABEL_112;
      }
      v115[0] = v50;
      v115[1] = (CStagingPool *)psoSrc[0]->dhpdev;
      psoSrc[0]->dhpdev = 0;
      v48 = psoSrc[0];
      if ( (unsigned __int64)(psoSrc[0]->lDelta * (__int64)(v49->top + 1) + 0x80000000LL) > 0xFFFFFFFF )
        v38 = 1;
      if ( v38 )
      {
        v48 = a2;
      }
      else if ( !((unsigned int (__fastcall *)(SURFOBJ *, struct _SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, RECTL *, RECTL *, _QWORD, _QWORD, _QWORD, int))v98)(
                   psoSrc[0],
                   a2,
                   0,
                   0,
                   pxlo,
                   v49,
                   v49,
                   0,
                   0,
                   0,
                   52428) )
      {
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 6768;
        v51 = (_QWORD *)WdLogNewEntry5_WdError();
        v51[3] = gCddImageInfo;
        v51[4] = (unsigned int)dword_14003E570;
        v51[5] = 215857758;
        WdLogGlobalForLineNumber = 6768;
        if ( v115[0] )
        {
          psoSrc[0]->dhpdev = (DHPDEV)v115[1];
          CStagingPool::ReleaseGdiSurface(v115[0], (struct CDDBITMAP_GDIDESC *)psoSrc);
        }
        if ( v121 )
          (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v121 + 128LL))(v121, v117);
        v52 = v122;
        if ( v122 )
        {
          if ( !v125 )
            (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))v122->dhsurf + 8))(
              v122,
              psoDest,
              v123,
              v120,
              v126);
          (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v52->dhsurf + 16))(v52, psoDest);
        }
        v53 = *((_QWORD *)v119 + 895);
        v54 = *(struct _KTHREAD **)(v53 + 32);
        if ( v54 == KeGetCurrentThread() && v54 )
        {
          *(_QWORD *)(v53 + 32) = 0;
          KeReleaseSemaphore((PRKSEMAPHORE)v53, 0, 1, 0);
        }
        v40 = 0;
        goto LABEL_114;
      }
      goto LABEL_95;
    }
    v48 = a2;
  }
  v49 = v93;
LABEL_95:
  if ( v41 )
  {
    v59 = pco;
    v60 = *((_BYTE *)qword_140039D10 + BYTE1(rop4));
    v61 = v127;
    v62 = *((_BYTE *)qword_140039D10 + (unsigned __int8)rop4);
    v88 = v62;
    if ( v127 )
    {
      v63 = (_QWORD *)*((_QWORD *)v119 + 895);
      if ( (struct _KTHREAD *)v63[4] != KeGetCurrentThread() )
      {
        v64 = KeWaitForSingleObject(v63, Executive, 0, 0, 0);
        if ( v64 != 258 )
        {
          v63[4] = KeGetCurrentThread();
          if ( v64 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 659;
            v65 = (_QWORD *)WdLogNewEntry5_WdError();
            v65[3] = gCddImageInfo;
            v65[4] = (unsigned int)dword_14003E570;
            v65[5] = 215857758;
            WdLogGlobalForLineNumber = 659;
            goto LABEL_101;
          }
        }
        v62 = v88;
      }
      v61 = v127;
      v41 = v94;
    }
    LOBYTE(prclSrc) = v61 == 0;
    if ( (*((int (__fastcall **)(SURFOBJ *, struct _RECTL *, struct _RECTL *, CLIPOBJ *, int, int, char *, SURFOBJ **, int))v41->dhsurf
          + 7))(
           v41,
           &v116,
           &v116,
           v59,
           1,
           (v60 | v62) & 0xB2,
           (char *)&v124 + 4,
           psoDest,
           prclSrc) < 0 )
    {
LABEL_101:
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 6784;
      v66 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v66[3] = gCddImageInfo;
      v66[4] = (unsigned int)dword_14003E570;
      v66[5] = 215857758;
      WdLogGlobalForLineNumber = 6784;
      if ( v115[0] )
      {
        psoSrc[0]->dhpdev = (DHPDEV)v115[1];
        CStagingPool::ReleaseGdiSurface(v115[0], (struct CDDBITMAP_GDIDESC *)psoSrc);
      }
      if ( v121 )
        (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v121 + 128LL))(v121, v117);
      v47 = v122;
      if ( !v122 )
        goto LABEL_109;
      if ( v125 )
        goto LABEL_108;
      goto LABEL_107;
    }
    if ( v120 && v59 != v120 && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Ivalid pco in GDIBITMAPACCESS2::StartAccessDst");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 670;
      v68 = (_QWORD *)WdLogNewEntry5_WdError();
      v68[3] = gCddImageInfo;
      v68[4] = (unsigned int)dword_14003E570;
      v68[5] = 215857758;
      WdLogGlobalForLineNumber = 670;
      __debugbreak();
    }
    v122 = v41;
    v69 = psoDest[0];
    v123 = &v116;
    v120 = v59;
    v126 = 0;
  }
  else
  {
    v69 = v100;
  }
  v70 = *((_QWORD *)v119 + 895);
  v71 = *(struct _KTHREAD **)(v70 + 32);
  if ( v71 == KeGetCurrentThread() && v71 )
  {
    *(_QWORD *)(v70 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v70, 0, 1, 0);
  }
  v72 = HIDWORD(v124);
  if ( v124 )
  {
    CDDPDEV::Flush(v119);
    v72 = HIDWORD(v124);
  }
  WaitForStartGdiAccessToFinish(v119, (struct CDDBITMAP_GDIDESC *)psoDest, v72);
  WaitForStartGdiAccessToFinish(v119, (struct CDDBITMAP_GDIDESC *)v117, v124);
  v73 = EngStretchBltROP(v69, v48, psoMask, pco, pxlo, pca, pptlHTOrg, prclDest, v49, pptlMask, iMode, pbo, rop4);
  v74 = v125;
  v75 = v73;
  if ( !v73 )
    v74 = 1;
  v125 = v74;
  if ( v115[0] )
  {
    psoSrc[0]->dhpdev = (DHPDEV)v115[1];
    CStagingPool::ReleaseGdiSurface(v115[0], (struct CDDBITMAP_GDIDESC *)psoSrc);
  }
  if ( v121 )
    (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v121 + 128LL))(v121, v117);
  v76 = v122;
  if ( v122 )
  {
    if ( !v125 )
      (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))v122->dhsurf + 8))(
        v122,
        psoDest,
        v123,
        v120,
        v126);
    (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v76->dhsurf + 16))(v76, psoDest);
  }
  v77 = *((_QWORD *)v119 + 895);
  v78 = *(struct _KTHREAD **)(v77 + 32);
  if ( v78 == KeGetCurrentThread() && v78 )
  {
    *(_QWORD *)(v77 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v77, 0, 1, 0);
  }
  CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v113);
LABEL_143:
  if ( !v112 )
  {
    LOBYTE(v23) = 2;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(v109 + 264))(v110, v23, v111);
  }
  return v75;
}

```

## disassembly

```asm
0x1400161b0  push    rbp
0x1400161b2  push    rbx
0x1400161b3  push    rsi
0x1400161b4  push    rdi
0x1400161b5  push    r12
0x1400161b7  push    r13
0x1400161b9  push    r14
0x1400161bb  push    r15
0x1400161bd  lea     rbp, [rsp-1A8h]
0x1400161c5  sub     rsp, 2A8h
0x1400161cc  mov     rax, cs:__security_cookie
0x1400161d3  xor     rax, rsp
0x1400161d6  mov     [rbp+1E0h+var_50], rax
0x1400161dd  mov     r12, [rbp+1E0h+arg_38]
0x1400161e4  mov     r13, rcx
0x1400161e7  mov     rax, [rbp+1E0h+arg_20]
0x1400161ee  xorps   xmm0, xmm0
0x1400161f1  mov     [rbp+1E0h+pxlo], rax
0x1400161f5  mov     r14, rdx
0x1400161f8  mov     rax, [rbp+1E0h+arg_28]
0x1400161ff  mov     edi, [r12+8]
0x140016204  sub     edi, [r12]
0x140016208  mov     r15d, [r12+0Ch]
0x14001620d  sub     r15d, [r12+4]
0x140016212  mov     [rbp+1E0h+var_200], rax
0x140016216  mov     rax, [rbp+1E0h+arg_30]
0x14001621d  mov     [rbp+1E0h+var_208], rax
0x140016221  mov     rax, [rbp+1E0h+arg_48]
0x140016228  mov     [rbp+1E0h+var_210], rax
0x14001622c  mov     rax, [rbp+1E0h+arg_58]
0x140016233  mov     [rbp+1E0h+var_218], rax
0x140016237  mov     eax, [rbp+1E0h+arg_60]
0x14001623d  mov     [rbp+1E0h+pco], r9
0x140016241  mov     rbx, [r13+10h]
0x140016245  mov     [rsp+2E0h+var_268], eax
0x140016249  mov     rax, [rbp+1E0h+arg_68]
0x140016250  mov     [rbp+1E0h+var_250], rdx
0x140016254  mov     [rbp+1E0h+var_228], rcx
0x140016258  mov     rcx, [rbp+1E0h+arg_40]
0x14001625f  mov     [rbp+1E0h+var_238], rax
0x140016263  movups  [rbp+1E0h+var_1F8], xmm0
0x140016267  mov     [rbp+1E0h+psoMask], r8
0x14001626b  mov     edx, [rcx+8]
0x14001626e  mov     esi, [rcx+0Ch]
0x140016271  sub     edx, [rcx]
0x140016273  sub     esi, [rcx+4]
0x140016276  movups  [rbp+1E0h+var_1E8], xmm0
0x14001627a  mov     [rbp+1E0h+var_258], rcx
0x14001627e  movups  [rbp+1E0h+var_1D8], xmm0
0x140016282  mov     rax, [rbx+50h]
0x140016286  mov     [rbp+1E0h+var_240], r13
0x14001628a  mov     [rbp+1E0h+var_248], edx
0x14001628d  mov     [rbp+1E0h+var_244], esi
0x140016290  mov     [rsp+2E0h+var_264], edi
0x140016294  mov     [rbp+1E0h+var_1B0], 1
0x14001629b  mov     [rbp+1E0h+var_1B8], 0
0x1400162a3  call    _guard_dispatch_icall
0x1400162a8  test    eax, eax
0x1400162aa  jz      short loc_14001630B
0x1400162ac  mov     qword ptr [rbp+1E0h+var_1E8+8], 0
0x1400162b4  lea     r9, [rbp+1E0h+var_1F8]; struct _DXGKETW_PARAMS *
0x1400162b8  mov     qword ptr [rbp+1E0h+var_1D8+8], 0
0x1400162c0  lea     rcx, [rbp+1E0h+var_1C8]; this
0x1400162c4  movzx   eax, word ptr [r14+4Ch]
0x1400162c9  mov     r8d, 0BD4h; unsigned int
0x1400162cf  mov     dword ptr [rbp+1E0h+var_1F8], eax
0x1400162d2  mov     rdx, rbx; struct CDDPDEV *
0x1400162d5  movzx   eax, word ptr [r13+4Ch]
0x1400162da  mov     dword ptr [rbp+1E0h+var_1F8+4], eax
0x1400162dd  mov     eax, [rbp+1E0h+var_248]
0x1400162e0  mov     dword ptr [rbp+1E0h+var_1F8+8], eax
0x1400162e3  movzx   eax, word ptr [rsp+2E0h+var_268]
0x1400162e8  mov     dword ptr [rbp+1E0h+var_1D8], eax
0x1400162eb  mov     eax, [rbp+1E0h+arg_50]
0x1400162f1  movzx   eax, ax
0x1400162f4  mov     dword ptr [rbp+1E0h+var_1D8+4], eax
0x1400162f7  mov     dword ptr [rbp+1E0h+var_1F8+0Ch], esi
0x1400162fa  mov     dword ptr [rbp+1E0h+var_1E8], edi
0x1400162fd  mov     dword ptr [rbp+1E0h+var_1E8+4], r15d
0x140016301  mov     byte ptr [rsp+2E0h+Timeout], 0; bool
0x140016306  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x14001630b  movzx   eax, word ptr [r14+4Ch]
0x140016310  mov     r8d, 1
0x140016316  cmp     ax, r8w
0x14001631a  jz      loc_14001709E
0x140016320  movzx   ecx, word ptr [r13+4Ch]
0x140016325  cmp     cx, r8w
0x140016329  jz      loc_14001709E
0x14001632f  lea     edi, [r8+2]
0x140016333  mov     esi, 0CDDBA5Eh
0x140016338  cmp     ax, di
0x14001633b  jz      short loc_140016391
0x14001633d  cmp     cx, di
0x140016340  jz      short loc_140016391
0x140016342  mov     ecx, r8d
0x140016345  call    cs:__imp_WdLogSingleEntry0
0x14001634c  nop     dword ptr [rax+rax+00h]
0x140016351  mov     cs:WdLogGlobalForLineNumber, 231h
0x14001635b  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140016362  nop     dword ptr [rax+rax+00h]
0x140016367  mov     rcx, rax
0x14001636a  lea     r8d, [rdi-2]
0x14001636e  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140016375  mov     [rcx+18h], rax
0x140016379  mov     eax, cs:dword_14003E570
0x14001637f  mov     [rcx+20h], rax
0x140016383  mov     [rcx+28h], rsi
0x140016387  mov     cs:WdLogGlobalForLineNumber, 231h
0x140016391  mov     rax, [rbp+1E0h+var_238]
0x140016395  mov     rdx, [r13+0]; struct CddBitmap *
0x140016399  mov     [rbp+1E0h+var_250], rdx
0x14001639d  cmp     rax, cs:__imp_EngBitBlt
0x1400163a4  jnz     short loc_1400163AB
0x1400163a6  mov     r13, [r14]
0x1400163a9  jmp     short loc_1400163AE
0x1400163ab  xor     r13d, r13d
0x1400163ae  test    rdx, rdx
0x1400163b1  jz      short loc_1400163B9
0x1400163b3  mov     rbx, [rdx+8]
0x1400163b7  jmp     short loc_1400163C2
0x1400163b9  test    r13, r13
0x1400163bc  jz      short loc_1400163C2
0x1400163be  mov     rbx, [r13+8]
0x1400163c2  mov     ecx, [rsp+2E0h+var_264]
0x1400163c6  test    ecx, ecx
0x1400163c8  jns     short loc_1400163E2
0x1400163ca  mov     eax, [r12+8]
0x1400163cf  neg     ecx
0x1400163d1  mov     [rbp+1E0h+var_140.left], eax
0x1400163d7  mov     eax, [r12]
0x1400163db  mov     [rsp+2E0h+var_26C], r8d
0x1400163e0  jmp     short loc_1400163F9
0x1400163e2  mov     eax, [r12]
0x1400163e6  mov     [rbp+1E0h+var_140.left], eax
0x1400163ec  mov     eax, [r12+8]
0x1400163f1  mov     [rsp+2E0h+var_26C], 0
0x1400163f9  mov     [rbp+1E0h+var_140.right], eax
0x1400163ff  mov     [rsp+2E0h+var_264], ecx
0x140016403  test    r15d, r15d
0x140016406  jns     short loc_140016421
0x140016408  mov     eax, [r12+0Ch]
0x14001640d  neg     r15d
0x140016410  mov     [rbp+1E0h+var_140.top], eax
0x140016416  mov     eax, [r12+4]
0x14001641b  mov     dword ptr [rbp+1E0h+var_240], r8d
0x14001641f  jmp     short loc_140016438
0x140016421  mov     eax, [r12+4]
0x140016426  mov     [rbp+1E0h+var_140.top], eax
0x14001642c  mov     eax, [r12+0Ch]
0x140016431  mov     dword ptr [rbp+1E0h+var_240], 0
0x140016438  mov     r8, r13; struct CddBitmap *
0x14001643b  mov     [rbp+1E0h+var_140.bottom], eax
0x140016441  lea     rcx, [rbp+1E0h+var_1A8]; this
0x140016445  call    ??0CDDMULTIBITMAPLOCK@@QEAA@PEAVCddBitmap@@0@Z; CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(CddBitmap *,CddBitmap *)
0x14001644a  mov     eax, [rsp+2E0h+var_264]
0x14001644e  mov     r8d, [rbp+1E0h+var_248]
0x140016452  mov     edx, [rbp+1E0h+var_244]
0x140016455  cmp     eax, r8d
0x140016458  jl      short loc_140016467
0x14001645a  cmp     r15d, edx
0x14001645d  jl      short loc_140016467
0x14001645f  xor     ecx, ecx
0x140016461  lea     r10d, [rcx+1]
0x140016465  jmp     short loc_140016470
0x140016467  mov     r10d, 1
0x14001646d  mov     ecx, r10d
0x140016470  cmp     eax, r8d
0x140016473  jg      short loc_14001647F
0x140016475  cmp     r15d, edx
0x140016478  jg      short loc_14001647F
0x14001647a  xor     r9d, r9d
0x14001647d  jmp     short loc_140016482
0x14001647f  mov     r9d, r10d
0x140016482  test    ecx, ecx
0x140016484  mov     ecx, [rbp+1E0h+arg_50]
0x14001648a  jnz     short loc_140016498
0x14001648c  cmp     ecx, 4
0x14001648f  cmovnz  ecx, edi
0x140016492  mov     [rbp+1E0h+arg_50], ecx
0x140016498  mov     rax, [rbp+1E0h+var_250]
0x14001649c  test    rax, rax
0x14001649f  jz      short loc_1400164C6
0x1400164a1  mov     eax, [rax+80h]
0x1400164a7  test    r10b, al
0x1400164aa  jz      short loc_1400164C6
0x1400164ac  cmp     [rbp+1E0h+psoMask], 0
0x1400164b1  jnz     short loc_1400164C6
0x1400164b3  cmp     ecx, edi
0x1400164b5  jnz     short loc_1400164C6
0x1400164b7  cmp     [rsp+2E0h+var_268], 0CCCCh
0x1400164bf  jnz     short loc_1400164C6
0x1400164c1  mov     edx, r10d
0x1400164c4  jmp     short loc_1400164C8
0x1400164c6  xor     edx, edx
0x1400164c8  mov     r10d, dword ptr [rbp+1E0h+var_240]
0x1400164cc  mov     eax, r10d
0x1400164cf  mov     r11d, [rsp+2E0h+var_26C]
0x1400164d4  or      eax, r11d
0x1400164d7  jz      short loc_1400164EA
0x1400164d9  mov     eax, [rbx+76Ch]
0x1400164df  and     eax, 200000h
0x1400164e4  neg     eax
0x1400164e6  sbb     eax, eax
0x1400164e8  and     edx, eax
0x1400164ea  mov     r8, [rbp+1E0h+var_258]
0x1400164ee  mov     ecx, [r8+0Ch]
0x1400164f2  sub     ecx, [r8+4]
0x1400164f6  cmp     ecx, [rbx+9ACh]
0x1400164fc  jg      short loc_14001650D
0x1400164fe  mov     ecx, [r8+8]
0x140016502  sub     ecx, [r8]
0x140016505  cmp     ecx, [rbx+9A8h]
0x14001650b  jle     short loc_14001650F
0x14001650d  xor     edx, edx
0x14001650f  xor     r15d, r15d
0x140016512  mov     dword ptr [rbp+1E0h+var_1E8+8], edx
0x140016515  mov     [rsp+2E0h+var_26C], r15d
0x14001651a  test    edx, edx
0x14001651c  jz      short loc_140016593
0x14001651e  mov     rax, [rbp+1E0h+arg_70]
0x140016525  mov     rcx, rbx; struct CDDPDEV *
0x140016528  mov     rdx, [rbp+1E0h+var_228]; struct _SURFOBJ *
0x14001652c  mov     [rsp+2E0h+var_278], rax; int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int)
0x140016531  mov     rax, [rbp+1E0h+var_238]
0x140016535  mov     qword ptr [rsp+2E0h+rop4], rax; int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int)
0x14001653a  lea     rax, [rsp+2E0h+var_26C]
0x14001653f  mov     [rsp+2E0h+pbo], rax; int *
0x140016544  mov     eax, [rbp+1E0h+arg_50]
0x14001654a  mov     [rsp+2E0h+iMode], r9d; int
0x14001654f  mov     r9, [rbp+1E0h+pco]; struct _CLIPOBJ *
0x140016553  mov     dword ptr [rsp+2E0h+pptlMask], r10d; int
0x140016558  mov     dword ptr [rsp+2E0h+prclSrc], r11d; int
0x14001655d  mov     dword ptr [rsp+2E0h+prclDest], eax; unsigned int
0x140016561  lea     rax, [rbp+1E0h+var_140]
0x140016568  mov     [rsp+2E0h+pptlHTOrg], r8; struct _RECTL *
0x14001656d  mov     r8, r14; struct _SURFOBJ *
0x140016570  mov     [rsp+2E0h+pca], rax; struct _RECTL *
0x140016575  mov     rax, [rbp+1E0h+pxlo]
0x140016579  mov     [rsp+2E0h+Timeout], rax; struct _XLATEOBJ *
0x14001657e  call    ?StretchBltAccelerated@@YAHPEAUCDDPDEV@@PEAU_SURFOBJ@@1PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@4IHHHPEAHP6AH111234PEAU_POINTL@@6PEAU_BRUSHOBJ@@6K@ZP6AH11123PEAUtagCOLORADJUSTMENT@@6446K@Z@Z; StretchBltAccelerated(CDDPDEV *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_RECTL *,uint,int,int,int,int *,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong),int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong))
0x140016583  mov     r15d, [rsp+2E0h+var_26C]
0x140016588  mov     edi, eax
0x14001658a  test    r15d, r15d
0x14001658d  jz      loc_140016D32
0x140016593  mov     rdi, [rbp+1E0h+var_250]
0x140016597  lea     rcx, [rbp+1E0h+var_130]; this
0x14001659e  mov     r9, rdi; struct CddBitmap *
0x1400165a1  mov     r8, r13; struct CddBitmap *
0x1400165a4  mov     rdx, rbx; struct CDDPDEV *
0x1400165a7  call    ??0GDIBITMAPACCESS2@@QEAA@PEAUCDDPDEV@@PEAVCddBitmap@@1@Z; GDIBITMAPACCESS2::GDIBITMAPACCESS2(CDDPDEV *,CddBitmap *,CddBitmap *)
0x1400165ac  xor     edx, edx; Val
0x1400165ae  lea     rcx, [rbp+1E0h+psoSrc]; void *
0x1400165b2  lea     r8d, [rdx+40h]; Size
0x1400165b6  call    memset
0x1400165bb  xorps   xmm0, xmm0
0x1400165be  movdqa  xmmword ptr [rbp+1E0h+var_150], xmm0
0x1400165c6  test    r13, r13
0x1400165c9  jz      loc_1400167C4
0x1400165cf  mov     cl, [rbp+1E0h+var_70]
0x1400165d5  xor     r15d, r15d
0x1400165d8  test    cl, cl
0x1400165da  jz      loc_14001675A
0x1400165e0  mov     rax, [rbp+1E0h+var_B0]
0x1400165e7  mov     rbx, [rax+1BF8h]
0x1400165ee  mov     rax, gs:188h
0x1400165f7  cmp     [rbx+20h], rax
0x1400165fb  jz      loc_140016754
0x140016601  xor     r9d, r9d; Alertable
0x140016604  mov     [rsp+2E0h+Timeout], r15; Timeout
0x140016609  xor     r8d, r8d; WaitMode
0x14001660c  xor     edx, edx; WaitReason
0x14001660e  mov     rcx, rbx; Object
0x140016611  call    cs:__imp_KeWaitForSingleObject
0x140016618  nop     dword ptr [rax+rax+00h]
0x14001661d  mov     ecx, eax
0x14001661f  cmp     eax, 102h
0x140016624  jz      loc_140016754
0x14001662a  mov     rax, gs:188h
0x140016633  mov     [rbx+20h], rax
0x140016637  test    ecx, ecx
0x140016639  jns     loc_140016754
0x14001663f  lea     ecx, [r15+2]
0x140016643  call    cs:__imp_WdLogSingleEntry0
0x14001664a  nop     dword ptr [rax+rax+00h]
0x14001664f  mov     ebx, 26Ah
0x140016654  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001665a  call    cs:__imp_WdLogNewEntry5_WdError
0x140016661  nop     dword ptr [rax+rax+00h]
0x140016666  mov     rcx, rax
0x140016669  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140016670  mov     [rcx+18h], rax
0x140016674  mov     eax, cs:dword_14003E570
0x14001667a  mov     [rcx+20h], rax
0x14001667e  mov     [rcx+28h], rsi
0x140016682  mov     cs:WdLogGlobalForLineNumber, ebx
0x140016688  mov     ecx, 4
0x14001668d  call    cs:__imp_WdLogSingleEntry0
0x140016694  nop     dword ptr [rax+rax+00h]
0x140016699  mov     ebx, 1A55h
0x14001669e  mov     cs:WdLogGlobalForLineNumber, ebx
  ... truncated ...
```
