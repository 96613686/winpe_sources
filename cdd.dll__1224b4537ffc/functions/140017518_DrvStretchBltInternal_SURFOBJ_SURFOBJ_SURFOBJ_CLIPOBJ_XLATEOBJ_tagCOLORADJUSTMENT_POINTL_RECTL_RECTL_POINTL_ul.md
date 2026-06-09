# DrvStretchBltInternal(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))

- ea: `0x140017518`
- end: `0x14001863c`
- name: `?DrvStretchBltInternal@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAUtagCOLORADJUSTMENT@@PEAU_POINTL@@PEAU_RECTL@@54KP6AH00012544PEAU_BRUSHOBJ@@4K@Z@Z`
- size: `4388`
- prototype: `int(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int, int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))`
- caller_count: `2`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x1400174a0`
- `0x140027370`

## callees

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
- `0x140017518`
- `0x14001d458`
- `0x1400200e8`
- `0x1400226b0`
- `0x1400248f8`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140017976`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017f30`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017976`
- `ntoskrnl!KeWaitForSingleObject` at `0x140017f30`
- `ntoskrnl!KeReleaseSemaphore` at `0x140017d90`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400180cb`
- `ntoskrnl!KeReleaseSemaphore` at `0x140018223`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400183c8`
- `ntoskrnl!KeReleaseSemaphore` at `0x140017d90`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400180cb`
- `ntoskrnl!KeReleaseSemaphore` at `0x140018223`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400183c8`
- `ntoskrnl!DbgPrint` at `0x14001816a`
- `ntoskrnl!DbgPrint` at `0x14001816a`
- `ntoskrnl!KdDebuggerEnabled` at `0x140018157`
- `watchdog!WdLogSingleEntry2` at `0x1400185e0`
- `watchdog!WdLogSingleEntry2` at `0x1400185e0`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x1400185f7`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x1400185f7`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400179bf`
- `watchdog!WdLogNewEntry5_WdError` at `0x140017c8b`
- `watchdog!WdLogNewEntry5_WdError` at `0x140017f78`
- `watchdog!WdLogNewEntry5_WdError` at `0x140018192`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400179bf`
- `watchdog!WdLogNewEntry5_WdError` at `0x140017c8b`
- `watchdog!WdLogNewEntry5_WdError` at `0x140017f78`
- `watchdog!WdLogNewEntry5_WdError` at `0x140018192`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400176b2`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400176b2`
- `watchdog!WdLogSingleEntry0` at `0x140017699`
- `watchdog!WdLogSingleEntry0` at `0x1400179a8`
- `watchdog!WdLogSingleEntry0` at `0x1400179f6`
- `watchdog!WdLogSingleEntry0` at `0x140017c74`
- `watchdog!WdLogSingleEntry0` at `0x140017db1`
- `watchdog!WdLogSingleEntry0` at `0x140017f61`
- `watchdog!WdLogSingleEntry0` at `0x140017fa8`
- `watchdog!WdLogSingleEntry0` at `0x14001817b`
- `watchdog!WdLogSingleEntry0` at `0x140017699`
- `watchdog!WdLogSingleEntry0` at `0x1400179a8`
- `watchdog!WdLogSingleEntry0` at `0x1400179f6`
- `watchdog!WdLogSingleEntry0` at `0x140017c74`
- `watchdog!WdLogSingleEntry0` at `0x140017db1`
- `watchdog!WdLogSingleEntry0` at `0x140017f61`
- `watchdog!WdLogSingleEntry0` at `0x140017fa8`
- `watchdog!WdLogSingleEntry0` at `0x14001817b`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140017a0d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140017dc8`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140017fbf`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140017a0d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140017dc8`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140017fbf`
- `WIN32K!EngStretchBlt` at `0x1400182cb`
- `WIN32K!EngStretchBlt` at `0x14001859f`
- `WIN32K!EngStretchBlt` at `0x140017883`
- `WIN32K!EngStretchBlt` at `0x1400182cb`
- `WIN32K!EngStretchBlt` at `0x14001859f`
- `WIN32K!EngBitBlt` at `0x1400176f0`
- `WIN32K!EngBitBlt` at `0x140017878`
- `WIN32K!EngBitBlt` at `0x140017b95`
- `WIN32K!EngReleaseSemaphore` at `0x14001849b`
- `WIN32K!EngReleaseSemaphore` at `0x1400184b6`
- `WIN32K!EngReleaseSemaphore` at `0x14001849b`
- `WIN32K!EngReleaseSemaphore` at `0x1400184b6`
- `WIN32K!EngAcquireSemaphore` at `0x140018436`
- `WIN32K!EngAcquireSemaphore` at `0x140018436`

## string_xrefs

- `0x140018163`: `Ivalid pco in GDIBITMAPACCESS2::StartAccessDst`

## pseudocode

```c
__int64 __fastcall DrvStretchBltInternal(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _SURFOBJ *a3,
        struct _CLIPOBJ *a4,
        struct _XLATEOBJ *a5,
        struct tagCOLORADJUSTMENT *a6,
        struct _POINTL *a7,
        struct _RECTL *a8,
        struct _RECTL *a9,
        struct _POINTL *a10,
        ULONG iMode,
        int (*a12)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))
{
  SURFOBJ *v13; // r15
  int v14; // r13d
  DHPDEV dhpdev; // rbx
  int v16; // edx
  int v17; // esi
  int v18; // edi
  unsigned int (*v19)(void); // rax
  __int64 v20; // rdx
  USHORT iType; // cx
  USHORT v22; // ax
  _QWORD *v23; // rax
  DHSURF dhsurf; // r14
  struct CddBitmap *v25; // r13
  int v26; // ecx
  LONG right; // eax
  int v28; // ecx
  LONG bottom; // eax
  BOOL v30; // edx
  BOOL v31; // r8d
  unsigned int v32; // r11d
  int v33; // edx
  int v34; // r10d
  int v35; // r14d
  int (*v36)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int); // rax
  unsigned int v37; // eax
  unsigned int v38; // edi
  SURFOBJ *v39; // rdi
  char v40; // cl
  _QWORD *v41; // rbx
  NTSTATUS v42; // ecx
  _QWORD *v43; // rax
  _QWORD *v44; // rax
  SURFOBJ *v45; // rbx
  __int64 v46; // rcx
  struct _KTHREAD *v47; // rdx
  int (*v48)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // r13
  CStagingPool *v49; // rbx
  SURFOBJ *v50; // rbx
  _QWORD *v51; // rax
  SURFOBJ *v52; // rbx
  __int64 v53; // rcx
  struct _KTHREAD *v54; // rdx
  _QWORD *v55; // rax
  SURFOBJ *v56; // rbx
  struct _KTHREAD *v57; // rdx
  char v58; // cl
  CLIPOBJ *v59; // r14
  BOOL v60; // r13d
  _QWORD *v61; // rbx
  NTSTATUS v62; // eax
  _QWORD *v63; // rax
  _QWORD *v64; // rax
  SURFOBJ *v65; // rbx
  struct _KTHREAD *v66; // rdx
  _QWORD *v67; // rax
  SURFOBJ *v68; // rbx
  __int64 v69; // rcx
  struct _KTHREAD *v70; // rdx
  int v71; // r8d
  BOOL v72; // eax
  int v73; // ecx
  unsigned int v74; // esi
  SURFOBJ *v75; // rbx
  __int64 v76; // rcx
  struct _KTHREAD *v77; // rdx
  HSEMAPHORE v79; // rdi
  int v80; // r14d
  BOOL v81; // r13d
  struct _SURFOBJ *v82; // r14
  RECTL *v83; // rdi
  _QWORD *v84; // rax
  int prclSrc; // [rsp+40h] [rbp-C0h]
  int v86; // [rsp+70h] [rbp-90h] BYREF
  int v87; // [rsp+74h] [rbp-8Ch]
  int v88; // [rsp+78h] [rbp-88h]
  CLIPOBJ *pco; // [rsp+80h] [rbp-80h] BYREF
  int v90; // [rsp+88h] [rbp-78h]
  int v91; // [rsp+8Ch] [rbp-74h]
  SURFOBJ *v92; // [rsp+90h] [rbp-70h] BYREF
  RECTL *prclDest; // [rsp+98h] [rbp-68h]
  XLATEOBJ *pxlo; // [rsp+A0h] [rbp-60h]
  SURFOBJ *psoMask; // [rsp+A8h] [rbp-58h]
  SURFOBJ *v96; // [rsp+B0h] [rbp-50h] BYREF
  int (*v97)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int); // [rsp+B8h] [rbp-48h]
  struct _SURFOBJ *v98; // [rsp+C0h] [rbp-40h]
  POINTL *pptlMask; // [rsp+C8h] [rbp-38h]
  POINTL *pptlHTOrg; // [rsp+D0h] [rbp-30h]
  COLORADJUSTMENT *pca; // [rsp+D8h] [rbp-28h]
  __int128 v102; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v103; // [rsp+F0h] [rbp-10h]
  __int128 v104; // [rsp+100h] [rbp+0h]
  __int64 v105; // [rsp+110h] [rbp+10h] BYREF
  unsigned int v106; // [rsp+118h] [rbp+18h]
  __int64 v107; // [rsp+120h] [rbp+20h]
  int v108; // [rsp+128h] [rbp+28h]
  _BYTE v109[32]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v110[8]; // [rsp+150h] [rbp+50h] BYREF
  CStagingPool *v111[2]; // [rsp+190h] [rbp+90h]
  struct _RECTL v112; // [rsp+1A0h] [rbp+A0h] BYREF
  SURFOBJ *psoSrc[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  SURFOBJ *psoDest[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  struct CDDPDEV *v115; // [rsp+230h] [rbp+130h]
  CLIPOBJ *v116; // [rsp+238h] [rbp+138h]
  struct CddBitmap *v117; // [rsp+240h] [rbp+140h]
  SURFOBJ *v118; // [rsp+248h] [rbp+148h]
  struct _RECTL *v119; // [rsp+250h] [rbp+150h]
  __int64 v120; // [rsp+258h] [rbp+158h] BYREF
  int v121; // [rsp+260h] [rbp+160h]
  __int64 v122; // [rsp+268h] [rbp+168h]
  char v123; // [rsp+270h] [rbp+170h]

  pxlo = a5;
  v13 = a2;
  v14 = a9->bottom - a9->top;
  pca = a6;
  pptlHTOrg = a7;
  pco = a4;
  dhpdev = a1->dhpdev;
  pptlMask = a10;
  v92 = a2;
  v16 = a9->right - a9->left;
  v98 = a1;
  v97 = a12;
  v102 = 0;
  psoMask = a3;
  v17 = a8->right - a8->left;
  v18 = a8->bottom - a8->top;
  v103 = 0;
  prclDest = a8;
  v104 = 0;
  v19 = (unsigned int (*)(void))*((_QWORD *)dhpdev + 10);
  v96 = a1;
  v90 = v16;
  v91 = v14;
  v88 = v17;
  v87 = v18;
  v108 = 1;
  v107 = 0;
  if ( v19() )
  {
    *(_QWORD *)((char *)&v104 + 4) = 0;
    HIDWORD(v104) = 0;
    LODWORD(v102) = v13->iType;
    DWORD1(v102) = a1->iType;
    *((_QWORD *)&v102 + 1) = __PAIR64__(v14, v90);
    LODWORD(v104) = iMode;
    v103 = __PAIR64__(v18, v17);
    CDDETWPROFILER::Init((CDDETWPROFILER *)&v105, (struct CDDPDEV *)dhpdev, 0xBD6u, (struct _DXGKETW_PARAMS *)&v102, 0);
  }
  iType = v13->iType;
  if ( iType == 1 || (v22 = a1->iType, v22 == 1) )
  {
    v79 = (HSEMAPHORE)*((_QWORD *)dhpdev + 365);
    v74 = 0;
    v80 = 0;
    if ( v79 )
    {
      EngAcquireSemaphore(v79);
      v80 = 1;
    }
    if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
    {
      if ( v79 && v80 )
        EngReleaseSemaphore(v79);
      v81 = 1;
    }
    else
    {
      CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
      v20 = *((_QWORD *)dhpdev + 349);
      *(_QWORD *)(v20 + 56) = *(_QWORD *)(v20 + 48);
      v81 = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) != 0;
      if ( v79 && v80 )
        EngReleaseSemaphore(v79);
    }
    if ( !v81 )
      goto LABEL_146;
    v82 = v98;
    if ( v98->iType == 3 || v13 && v13->iType == 3 )
    {
      WdLogSingleEntry2(3, v13, v98);
      WdLogGlobalForLineNumber = 581;
      v84 = (_QWORD *)WdLogNewEntry5_WdWarning();
      v84[3] = gCddImageInfo;
      v84[4] = (unsigned int)dword_14003E570;
      v84[5] = 215857758;
      WdLogGlobalForLineNumber = 581;
    }
    else
    {
      v83 = prclDest;
      v86 = 0;
      CDDMULTISURFLOCK::vInit((CDDMULTISURFLOCK *)psoSrc, (struct CDDPDEV *)dhpdev, &v96, &v92, prclDest, a9, &v86, pco);
      if ( !bIgnoreDeviceSurfaceUpdates(v82, &pco) )
      {
        v74 = EngStretchBlt(v96, v92, psoMask, pco, pxlo, pca, pptlHTOrg, v83, a9, pptlMask, iMode);
        if ( v74 && v86 == 1 )
          vGDIDirtyUpdate((struct CDDPDEV *)dhpdev, (struct tagRECT *)v83, pco);
        CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)psoSrc);
        goto LABEL_146;
      }
      CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)psoSrc);
    }
    v38 = 1;
    goto LABEL_171;
  }
  if ( iType != 3 && v22 != 3 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 561;
    v23 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v23[3] = gCddImageInfo;
    v23[4] = (unsigned int)dword_14003E570;
    v23[5] = 215857758;
    WdLogGlobalForLineNumber = 561;
  }
  dhsurf = a1->dhsurf;
  v96 = (SURFOBJ *)dhsurf;
  if ( v97 == EngBitBlt )
    v25 = (struct CddBitmap *)v13->dhsurf;
  else
    v25 = 0;
  if ( dhsurf )
  {
    dhpdev = (DHPDEV)*((_QWORD *)dhsurf + 1);
  }
  else if ( v25 )
  {
    dhpdev = (DHPDEV)*((_QWORD *)v25 + 1);
  }
  v26 = v88;
  if ( v88 >= 0 )
  {
    v112.left = prclDest->left;
    right = prclDest->right;
    v86 = 0;
  }
  else
  {
    v26 = -v88;
    v112.left = prclDest->right;
    right = prclDest->left;
    v86 = 1;
  }
  v88 = v26;
  v28 = v87;
  v112.right = right;
  if ( v87 >= 0 )
  {
    v112.top = prclDest->top;
    bottom = prclDest->bottom;
    LODWORD(v92) = 0;
  }
  else
  {
    v28 = -v87;
    v112.top = prclDest->bottom;
    bottom = prclDest->top;
    LODWORD(v92) = 1;
  }
  v87 = v28;
  v112.bottom = bottom;
  CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v109, (struct CddBitmap *)dhsurf, v25);
  v30 = v88 < v90 || v87 < v91;
  v31 = v88 > v90 || v87 > v91;
  v32 = iMode;
  if ( !v30 )
  {
    if ( iMode != 4 )
      v32 = 3;
    iMode = v32;
  }
  v33 = dhsurf && ((_DWORD)dhsurf[32] & 1) != 0 && !psoMask && v32 == 3;
  v34 = v86;
  if ( v86 | (unsigned int)v92 )
    v33 = ((_DWORD)dhpdev[475] & 0x200000) != 0 ? v33 : 0;
  if ( a9->bottom - a9->top > *((_DWORD *)dhpdev + 619) || a9->right - a9->left > *((_DWORD *)dhpdev + 618) )
  {
    v35 = 0;
  }
  else
  {
    v35 = 0;
    v86 = 0;
    if ( v33 )
    {
      v36 = 0;
      if ( v97 == EngBitBlt )
        v36 = EngStretchBlt;
      DWORD2(v103) = 1;
      v37 = StretchBltAccelerated(
              (struct CDDPDEV *)dhpdev,
              v98,
              v13,
              pco,
              pxlo,
              &v112,
              a9,
              v32,
              v34,
              (int)v92,
              v31,
              &v86,
              v97,
              v36);
      v35 = v86;
      v38 = v37;
      if ( !v86 )
        goto LABEL_118;
    }
  }
  v39 = v96;
  GDIBITMAPACCESS2::GDIBITMAPACCESS2((GDIBITMAPACCESS2 *)psoSrc, (struct CDDPDEV *)dhpdev, v25, (struct CddBitmap *)v96);
  memset(v110, 0, sizeof(v110));
  *(_OWORD *)v111 = 0;
  if ( v25 )
  {
    v40 = v123;
    if ( v123 )
    {
      v41 = (_QWORD *)*((_QWORD *)v115 + 895);
      if ( (struct _KTHREAD *)v41[4] != KeGetCurrentThread() )
      {
        v42 = KeWaitForSingleObject(v41, Executive, 0, 0, 0);
        if ( v42 != 258 )
        {
          v41[4] = KeGetCurrentThread();
          if ( v42 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 618;
            v43 = (_QWORD *)WdLogNewEntry5_WdError();
            v43[3] = gCddImageInfo;
            v43[4] = (unsigned int)dword_14003E570;
            v43[5] = 215857758;
            WdLogGlobalForLineNumber = 618;
LABEL_55:
            WdLogSingleEntry0(4);
            WdLogGlobalForLineNumber = 3871;
            v44 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v44[3] = gCddImageInfo;
            v44[4] = (unsigned int)dword_14003E570;
            v44[5] = 215857758;
            WdLogGlobalForLineNumber = 3871;
            if ( v111[0] )
            {
              *(CStagingPool **)(v110[0] + 16LL) = v111[1];
              CStagingPool::ReleaseGdiSurface(v111[0], (struct CDDBITMAP_GDIDESC *)v110);
            }
            if ( v117 )
              (*(void (__fastcall **)(struct CddBitmap *, SURFOBJ **))(*(_QWORD *)v117 + 128LL))(v117, psoSrc);
            v45 = v118;
            if ( v118 )
            {
              if ( !v121 )
                (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))v118->dhsurf + 8))(
                  v118,
                  psoDest,
                  v119,
                  v116,
                  v122);
              (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v45->dhsurf + 16))(v45, psoDest);
            }
            v46 = *((_QWORD *)v115 + 895);
            v47 = *(struct _KTHREAD **)(v46 + 32);
            if ( v47 != KeGetCurrentThread() || !v47 )
              goto LABEL_117;
            *(_QWORD *)(v46 + 32) = 0;
LABEL_116:
            KeReleaseSemaphore((PRKSEMAPHORE)v46, 0, 1, 0);
LABEL_117:
            v38 = 1;
LABEL_118:
            CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v109);
LABEL_171:
            CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v105);
            return v38;
          }
        }
      }
      v40 = v123;
    }
    LOBYTE(prclSrc) = v40 == 0;
    if ( (*(int (__fastcall **)(struct CddBitmap *, struct _RECTL *, struct _RECTL *, _QWORD, int, int, __int64 *, SURFOBJ **, int))(*(_QWORD *)v25 + 56LL))(
           v25,
           a9,
           a9,
           0,
           1,
           1,
           &v120,
           psoSrc,
           prclSrc) < 0 )
      goto LABEL_55;
    v13 = psoSrc[0];
    v117 = v25;
    v116 = 0;
  }
  else
  {
    v48 = v97;
    if ( v97 != EngBitBlt )
    {
      v49 = (CStagingPool *)(dhpdev + 1376);
      if ( (int)CStagingPool::GetGdiSurface(
                  v49,
                  v13->sizlBitmap.cx,
                  v13->sizlBitmap.cy,
                  (const struct tagRECT *)a9,
                  (struct CDDBITMAP_GDIDESC *)v110,
                  1u) < 0 )
      {
        WdLogSingleEntry0(4);
        WdLogGlobalForLineNumber = 3880;
        v55 = (_QWORD *)WdLogNewEntry5_WdEvent();
        v55[3] = gCddImageInfo;
        v55[4] = (unsigned int)dword_14003E570;
        v55[5] = 215857758;
        WdLogGlobalForLineNumber = 3880;
        if ( v111[0] )
        {
          *(CStagingPool **)(v110[0] + 16LL) = v111[1];
          CStagingPool::ReleaseGdiSurface(v111[0], (struct CDDBITMAP_GDIDESC *)v110);
        }
        if ( v117 )
          (*(void (__fastcall **)(struct CddBitmap *, SURFOBJ **))(*(_QWORD *)v117 + 128LL))(v117, psoSrc);
        v56 = v118;
        if ( v118 )
        {
          if ( !v121 )
            (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))v118->dhsurf + 8))(
              v118,
              psoDest,
              v119,
              v116,
              v122);
          (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v56->dhsurf + 16))(v56, psoDest);
        }
        v46 = *((_QWORD *)v115 + 895);
        v57 = *(struct _KTHREAD **)(v46 + 32);
        if ( v57 != KeGetCurrentThread() || !v57 )
          goto LABEL_117;
        *(_QWORD *)(v46 + 32) = 0;
        goto LABEL_116;
      }
      v111[0] = v49;
      v111[1] = *(CStagingPool **)(v110[0] + 16LL);
      *(_QWORD *)(v110[0] + 16LL) = 0;
      v50 = (SURFOBJ *)v110[0];
      if ( (unsigned __int64)(*(int *)(v110[0] + 64LL) * (__int64)(a9->top + 1) + 0x80000000LL) > 0xFFFFFFFF )
        v35 = 1;
      if ( !v35 )
      {
        if ( !((unsigned int (__fastcall *)(_QWORD, SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, struct _RECTL *, struct _RECTL *, _QWORD, _QWORD, _QWORD, int))v48)(
                v110[0],
                v13,
                0,
                0,
                pxlo,
                a9,
                a9,
                0,
                0,
                0,
                52428) )
        {
          WdLogSingleEntry0(2);
          WdLogGlobalForLineNumber = 3898;
          v51 = (_QWORD *)WdLogNewEntry5_WdError();
          v51[3] = gCddImageInfo;
          v51[4] = (unsigned int)dword_14003E570;
          v51[5] = 215857758;
          WdLogGlobalForLineNumber = 3898;
          if ( v111[0] )
          {
            *(CStagingPool **)(v110[0] + 16LL) = v111[1];
            CStagingPool::ReleaseGdiSurface(v111[0], (struct CDDBITMAP_GDIDESC *)v110);
          }
          if ( v117 )
            (*(void (__fastcall **)(struct CddBitmap *, SURFOBJ **))(*(_QWORD *)v117 + 128LL))(v117, psoSrc);
          v52 = v118;
          if ( v118 )
          {
            if ( !v121 )
              (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))v118->dhsurf + 8))(
                v118,
                psoDest,
                v119,
                v116,
                v122);
            (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v52->dhsurf + 16))(v52, psoDest);
          }
          v53 = *((_QWORD *)v115 + 895);
          v54 = *(struct _KTHREAD **)(v53 + 32);
          if ( v54 == KeGetCurrentThread() && v54 )
          {
            *(_QWORD *)(v53 + 32) = 0;
            KeReleaseSemaphore((PRKSEMAPHORE)v53, 0, 1, 0);
          }
          v38 = 0;
          goto LABEL_118;
        }
        v13 = v50;
      }
    }
  }
  if ( v39 )
  {
    v58 = v123;
    v59 = pco;
    v60 = psoMask != 0;
    if ( v123 )
    {
      v61 = (_QWORD *)*((_QWORD *)v115 + 895);
      if ( (struct _KTHREAD *)v61[4] != KeGetCurrentThread() )
      {
        v62 = KeWaitForSingleObject(v61, Executive, 0, 0, 0);
        if ( v62 != 258 )
        {
          v61[4] = KeGetCurrentThread();
          if ( v62 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 659;
            v63 = (_QWORD *)WdLogNewEntry5_WdError();
            v63[3] = gCddImageInfo;
            v63[4] = (unsigned int)dword_14003E570;
            v63[5] = 215857758;
            WdLogGlobalForLineNumber = 659;
LABEL_105:
            WdLogSingleEntry0(4);
            WdLogGlobalForLineNumber = 3915;
            v64 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v64[3] = gCddImageInfo;
            v64[4] = (unsigned int)dword_14003E570;
            v64[5] = 215857758;
            WdLogGlobalForLineNumber = 3915;
            if ( v111[0] )
            {
              *(CStagingPool **)(v110[0] + 16LL) = v111[1];
              CStagingPool::ReleaseGdiSurface(v111[0], (struct CDDBITMAP_GDIDESC *)v110);
            }
            if ( v117 )
              (*(void (__fastcall **)(struct CddBitmap *, SURFOBJ **))(*(_QWORD *)v117 + 128LL))(v117, psoSrc);
            v65 = v118;
            if ( v118 )
            {
              if ( !v121 )
                (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))v118->dhsurf + 8))(
                  v118,
                  psoDest,
                  v119,
                  v116,
                  v122);
              (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v65->dhsurf + 16))(v65, psoDest);
            }
            v46 = *((_QWORD *)v115 + 895);
            v66 = *(struct _KTHREAD **)(v46 + 32);
            if ( v66 != KeGetCurrentThread() || !v66 )
              goto LABEL_117;
            *(_QWORD *)(v46 + 32) = 0;
            goto LABEL_116;
          }
        }
      }
      v58 = v123;
    }
    LOBYTE(prclSrc) = v58 == 0;
    if ( (*((int (__fastcall **)(SURFOBJ *, struct _RECTL *, struct _RECTL *, CLIPOBJ *, int, BOOL, char *, SURFOBJ **, int))v39->dhsurf
          + 7))(
           v39,
           &v112,
           &v112,
           v59,
           1,
           v60,
           (char *)&v120 + 4,
           psoDest,
           prclSrc) < 0 )
      goto LABEL_105;
    if ( v116 && v59 != v116 && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Ivalid pco in GDIBITMAPACCESS2::StartAccessDst");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 670;
      v67 = (_QWORD *)WdLogNewEntry5_WdError();
      v67[3] = gCddImageInfo;
      v67[4] = (unsigned int)dword_14003E570;
      v67[5] = 215857758;
      WdLogGlobalForLineNumber = 670;
      __debugbreak();
    }
    v68 = psoDest[0];
    v116 = v59;
    v122 = 0;
    v118 = v39;
    v119 = &v112;
  }
  else
  {
    v68 = v98;
  }
  v69 = *((_QWORD *)v115 + 895);
  v70 = *(struct _KTHREAD **)(v69 + 32);
  if ( v70 == KeGetCurrentThread() && v70 )
  {
    *(_QWORD *)(v69 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v69, 0, 1, 0);
  }
  v71 = HIDWORD(v120);
  if ( v120 )
  {
    CDDPDEV::Flush(v115);
    v71 = HIDWORD(v120);
  }
  WaitForStartGdiAccessToFinish(v115, (struct CDDBITMAP_GDIDESC *)psoDest, v71);
  WaitForStartGdiAccessToFinish(v115, (struct CDDBITMAP_GDIDESC *)psoSrc, v120);
  v72 = EngStretchBlt(v68, v13, psoMask, pco, pxlo, pca, pptlHTOrg, prclDest, a9, pptlMask, iMode);
  v73 = v121;
  v74 = v72;
  if ( !v72 )
    v73 = 1;
  v121 = v73;
  if ( v111[0] )
  {
    *(CStagingPool **)(v110[0] + 16LL) = v111[1];
    CStagingPool::ReleaseGdiSurface(v111[0], (struct CDDBITMAP_GDIDESC *)v110);
  }
  if ( v117 )
    (*(void (__fastcall **)(struct CddBitmap *, SURFOBJ **))(*(_QWORD *)v117 + 128LL))(v117, psoSrc);
  v75 = v118;
  if ( v118 )
  {
    if ( !v121 )
      (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))v118->dhsurf + 8))(
        v118,
        psoDest,
        v119,
        v116,
        v122);
    (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v75->dhsurf + 16))(v75, psoDest);
  }
  v76 = *((_QWORD *)v115 + 895);
  v77 = *(struct _KTHREAD **)(v76 + 32);
  if ( v77 == KeGetCurrentThread() && v77 )
  {
    *(_QWORD *)(v76 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v76, 0, 1, 0);
  }
  CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v109);
LABEL_146:
  if ( !v108 )
  {
    LOBYTE(v20) = 2;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(v105 + 264))(v106, v20, v107);
  }
  return v74;
}

```

## disassembly

```asm
0x140017518  push    rbp
0x14001751a  push    rbx
0x14001751b  push    rsi
0x14001751c  push    rdi
0x14001751d  push    r12
0x14001751f  push    r13
0x140017521  push    r14
0x140017523  push    r15
0x140017525  lea     rbp, [rsp-1A8h]
0x14001752d  sub     rsp, 2A8h
0x140017534  mov     rax, cs:__security_cookie
0x14001753b  xor     rax, rsp
0x14001753e  mov     [rbp+1E0h+var_50], rax
0x140017545  mov     r12, [rbp+1E0h+arg_40]
0x14001754c  mov     r14, rcx
0x14001754f  mov     rax, [rbp+1E0h+arg_20]
0x140017556  xorps   xmm0, xmm0
0x140017559  mov     [rbp+1E0h+pxlo], rax
0x14001755d  mov     r15, rdx
0x140017560  mov     rax, [rbp+1E0h+arg_28]
0x140017567  mov     r13d, [r12+0Ch]
0x14001756c  sub     r13d, [r12+4]
0x140017571  mov     [rbp+1E0h+var_208], rax
0x140017575  mov     rax, [rbp+1E0h+arg_30]
0x14001757c  mov     [rbp+1E0h+var_210], rax
0x140017580  mov     rax, [rbp+1E0h+arg_48]
0x140017587  mov     [rbp+1E0h+pco], r9
0x14001758b  mov     rbx, [r14+10h]
0x14001758f  mov     [rbp+1E0h+var_218], rax
0x140017593  mov     rax, [rbp+1E0h+arg_58]
0x14001759a  mov     [rbp+1E0h+var_250], rdx
0x14001759e  mov     edx, [r12+8]
0x1400175a3  sub     edx, [r12]
0x1400175a7  mov     [rbp+1E0h+var_220], rcx
0x1400175ab  mov     rcx, [rbp+1E0h+arg_38]
0x1400175b2  mov     [rbp+1E0h+var_228], rax
0x1400175b6  movups  [rbp+1E0h+var_200], xmm0
0x1400175ba  mov     [rbp+1E0h+psoMask], r8
0x1400175be  mov     esi, [rcx+8]
0x1400175c1  mov     edi, [rcx+0Ch]
0x1400175c4  sub     esi, [rcx]
0x1400175c6  sub     edi, [rcx+4]
0x1400175c9  movups  [rbp+1E0h+var_1F0], xmm0
0x1400175cd  mov     [rbp+1E0h+var_248], rcx
0x1400175d1  movups  [rbp+1E0h+var_1E0], xmm0
0x1400175d5  mov     rax, [rbx+50h]
0x1400175d9  mov     [rbp+1E0h+var_230], r14
0x1400175dd  mov     [rbp+1E0h+var_258], edx
0x1400175e0  mov     [rbp+1E0h+var_254], r13d
0x1400175e4  mov     [rsp+2E0h+var_268], esi
0x1400175e8  mov     [rsp+2E0h+var_26C], edi
0x1400175ec  mov     [rbp+1E0h+var_1B8], 1
0x1400175f3  mov     [rbp+1E0h+var_1C0], 0
0x1400175fb  call    _guard_dispatch_icall
0x140017600  test    eax, eax
0x140017602  jz      short loc_14001765F
0x140017604  mov     qword ptr [rbp+1E0h+var_1F0+8], 0
0x14001760c  lea     r9, [rbp+1E0h+var_200]; struct _DXGKETW_PARAMS *
0x140017610  mov     qword ptr [rbp+1E0h+var_1E0+4], 0
0x140017618  lea     rcx, [rbp+1E0h+var_1D0]; this
0x14001761c  mov     dword ptr [rbp+1E0h+var_1E0+0Ch], 0
0x140017623  mov     r8d, 0BD6h; unsigned int
0x140017629  movzx   eax, word ptr [r15+4Ch]
0x14001762e  mov     rdx, rbx; struct CDDPDEV *
0x140017631  mov     dword ptr [rbp+1E0h+var_200], eax
0x140017634  movzx   eax, word ptr [r14+4Ch]
0x140017639  mov     dword ptr [rbp+1E0h+var_200+4], eax
0x14001763c  mov     eax, [rbp+1E0h+var_258]
0x14001763f  mov     dword ptr [rbp+1E0h+var_200+8], eax
0x140017642  mov     eax, [rbp+1E0h+arg_50]
0x140017648  mov     dword ptr [rbp+1E0h+var_1E0], eax
0x14001764b  mov     dword ptr [rbp+1E0h+var_200+0Ch], r13d
0x14001764f  mov     dword ptr [rbp+1E0h+var_1F0], esi
0x140017652  mov     dword ptr [rbp+1E0h+var_1F0+4], edi
0x140017655  mov     byte ptr [rsp+2E0h+Timeout], 0; bool
0x14001765a  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x14001765f  movzx   ecx, word ptr [r15+4Ch]
0x140017664  mov     r8d, 1
0x14001766a  cmp     cx, r8w
0x14001766e  jz      loc_140018422
0x140017674  movzx   eax, word ptr [r14+4Ch]
0x140017679  cmp     ax, r8w
0x14001767d  jz      loc_140018422
0x140017683  lea     edi, [r8+2]
0x140017687  mov     esi, 0CDDBA5Eh
0x14001768c  cmp     cx, di
0x14001768f  jz      short loc_1400176E5
0x140017691  cmp     ax, di
0x140017694  jz      short loc_1400176E5
0x140017696  mov     ecx, r8d
0x140017699  call    cs:__imp_WdLogSingleEntry0
0x1400176a0  nop     dword ptr [rax+rax+00h]
0x1400176a5  mov     r13d, 231h
0x1400176ab  mov     cs:WdLogGlobalForLineNumber, r13d
0x1400176b2  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400176b9  nop     dword ptr [rax+rax+00h]
0x1400176be  mov     rcx, rax
0x1400176c1  lea     r8d, [rdi-2]
0x1400176c5  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400176cc  mov     [rcx+18h], rax
0x1400176d0  mov     eax, cs:dword_14003E570
0x1400176d6  mov     [rcx+20h], rax
0x1400176da  mov     [rcx+28h], rsi
0x1400176de  mov     cs:WdLogGlobalForLineNumber, r13d
0x1400176e5  mov     rax, [rbp+1E0h+var_228]
0x1400176e9  mov     r14, [r14]
0x1400176ec  mov     [rbp+1E0h+var_230], r14
0x1400176f0  cmp     rax, cs:__imp_EngBitBlt
0x1400176f7  jnz     short loc_1400176FE
0x1400176f9  mov     r13, [r15]
0x1400176fc  jmp     short loc_140017701
0x1400176fe  xor     r13d, r13d
0x140017701  test    r14, r14
0x140017704  jz      short loc_14001770C
0x140017706  mov     rbx, [r14+8]
0x14001770a  jmp     short loc_140017715
0x14001770c  test    r13, r13
0x14001770f  jz      short loc_140017715
0x140017711  mov     rbx, [r13+8]
0x140017715  mov     ecx, [rsp+2E0h+var_268]
0x140017719  mov     rdx, [rbp+1E0h+var_248]
0x14001771d  test    ecx, ecx
0x14001771f  jns     short loc_140017735
0x140017721  mov     eax, [rdx+8]
0x140017724  neg     ecx
0x140017726  mov     [rbp+1E0h+var_140.left], eax
0x14001772c  mov     eax, [rdx]
0x14001772e  mov     [rsp+2E0h+var_270], r8d
0x140017733  jmp     short loc_140017748
0x140017735  mov     eax, [rdx]
0x140017737  mov     [rbp+1E0h+var_140.left], eax
0x14001773d  mov     eax, [rdx+8]
0x140017740  mov     [rsp+2E0h+var_270], 0
0x140017748  mov     [rsp+2E0h+var_268], ecx
0x14001774c  mov     ecx, [rsp+2E0h+var_26C]
0x140017750  mov     [rbp+1E0h+var_140.right], eax
0x140017756  test    ecx, ecx
0x140017758  jns     short loc_14001776E
0x14001775a  mov     eax, [rdx+0Ch]
0x14001775d  neg     ecx
0x14001775f  mov     [rbp+1E0h+var_140.top], eax
0x140017765  mov     eax, [rdx+4]
0x140017768  mov     dword ptr [rbp+1E0h+var_250], r8d
0x14001776c  jmp     short loc_140017781
0x14001776e  mov     eax, [rdx+4]
0x140017771  mov     [rbp+1E0h+var_140.top], eax
0x140017777  mov     eax, [rdx+0Ch]
0x14001777a  mov     dword ptr [rbp+1E0h+var_250], 0
0x140017781  mov     [rsp+2E0h+var_26C], ecx
0x140017785  mov     r8, r13; struct CddBitmap *
0x140017788  lea     rcx, [rbp+1E0h+var_1B0]; this
0x14001778c  mov     [rbp+1E0h+var_140.bottom], eax
0x140017792  mov     rdx, r14; struct CddBitmap *
0x140017795  call    ??0CDDMULTIBITMAPLOCK@@QEAA@PEAVCddBitmap@@0@Z; CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(CddBitmap *,CddBitmap *)
0x14001779a  mov     ecx, [rsp+2E0h+var_268]
0x14001779e  mov     r9d, [rbp+1E0h+var_258]
0x1400177a2  mov     eax, [rsp+2E0h+var_26C]
0x1400177a6  mov     r8d, [rbp+1E0h+var_254]
0x1400177aa  cmp     ecx, r9d
0x1400177ad  jl      short loc_1400177BC
0x1400177af  cmp     eax, r8d
0x1400177b2  jl      short loc_1400177BC
0x1400177b4  xor     edx, edx
0x1400177b6  lea     r10d, [rdx+1]
0x1400177ba  jmp     short loc_1400177C5
0x1400177bc  mov     r10d, 1
0x1400177c2  mov     edx, r10d
0x1400177c5  cmp     ecx, r9d
0x1400177c8  jg      short loc_1400177D4
0x1400177ca  cmp     eax, r8d
0x1400177cd  jg      short loc_1400177D4
0x1400177cf  xor     r8d, r8d
0x1400177d2  jmp     short loc_1400177D7
0x1400177d4  mov     r8d, r10d
0x1400177d7  mov     r11d, [rbp+1E0h+arg_50]
0x1400177de  test    edx, edx
0x1400177e0  jnz     short loc_1400177F1
0x1400177e2  cmp     r11d, 4
0x1400177e6  cmovnz  r11d, edi
0x1400177ea  mov     [rbp+1E0h+arg_50], r11d
0x1400177f1  test    r14, r14
0x1400177f4  jz      short loc_140017813
0x1400177f6  mov     eax, [r14+80h]
0x1400177fd  test    r10b, al
0x140017800  jz      short loc_140017813
0x140017802  cmp     [rbp+1E0h+psoMask], 0
0x140017807  jnz     short loc_140017813
0x140017809  cmp     r11d, edi
0x14001780c  jnz     short loc_140017813
0x14001780e  mov     edx, r10d
0x140017811  jmp     short loc_140017815
0x140017813  xor     edx, edx
0x140017815  mov     r9d, dword ptr [rbp+1E0h+var_250]
0x140017819  mov     eax, r9d
0x14001781c  mov     r10d, [rsp+2E0h+var_270]
0x140017821  or      eax, r10d
0x140017824  jz      short loc_140017837
0x140017826  mov     eax, [rbx+76Ch]
0x14001782c  and     eax, 200000h
0x140017831  neg     eax
0x140017833  sbb     eax, eax
0x140017835  and     edx, eax
0x140017837  mov     ecx, [r12+0Ch]
0x14001783c  sub     ecx, [r12+4]
0x140017841  cmp     ecx, [rbx+9ACh]
0x140017847  jg      loc_1400178F5
0x14001784d  mov     ecx, [r12+8]
0x140017852  sub     ecx, [r12]
0x140017856  cmp     ecx, [rbx+9A8h]
0x14001785c  jg      loc_1400178F5
0x140017862  xor     r14d, r14d
0x140017865  mov     [rsp+2E0h+var_270], r14d
0x14001786a  test    edx, edx
0x14001786c  jz      loc_1400178F8
0x140017872  mov     rcx, [rbp+1E0h+var_228]
0x140017876  xor     eax, eax
0x140017878  cmp     rcx, cs:__imp_EngBitBlt
0x14001787f  mov     rdx, [rbp+1E0h+var_220]; struct _SURFOBJ *
0x140017883  cmovz   rax, cs:__imp_EngStretchBlt
0x14001788b  mov     [rsp+2E0h+var_278], rax; int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct tagCOLORADJUSTMENT *, struct _POINTL *, struct _RECTL *, struct _RECTL *, struct _POINTL *, unsigned int)
0x140017890  lea     rax, [rsp+2E0h+var_270]
0x140017895  mov     [rsp+2E0h+var_280], rcx; int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int)
0x14001789a  mov     rcx, rbx; struct CDDPDEV *
0x14001789d  mov     [rsp+2E0h+var_288], rax; int *
0x1400178a2  lea     rax, [rbp+1E0h+var_140]
0x1400178a9  mov     [rsp+2E0h+iMode], r8d; int
0x1400178ae  mov     r8, r15; struct _SURFOBJ *
0x1400178b1  mov     dword ptr [rsp+2E0h+pptlMask], r9d; int
0x1400178b6  mov     r9, [rbp+1E0h+pco]; struct _CLIPOBJ *
0x1400178ba  mov     dword ptr [rsp+2E0h+prclSrc], r10d; int
0x1400178bf  mov     dword ptr [rsp+2E0h+prclDest], r11d; unsigned int
0x1400178c4  mov     [rsp+2E0h+pptlHTOrg], r12; struct _RECTL *
0x1400178c9  mov     [rsp+2E0h+pca], rax; struct _RECTL *
0x1400178ce  mov     rax, [rbp+1E0h+pxlo]
0x1400178d2  mov     [rsp+2E0h+Timeout], rax; struct _XLATEOBJ *
0x1400178d7  mov     dword ptr [rbp+1E0h+var_1F0+8], 1
0x1400178de  call    ?StretchBltAccelerated@@YAHPEAUCDDPDEV@@PEAU_SURFOBJ@@1PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@4IHHHPEAHP6AH111234PEAU_POINTL@@6PEAU_BRUSHOBJ@@6K@ZP6AH11123PEAUtagCOLORADJUSTMENT@@6446K@Z@Z; StretchBltAccelerated(CDDPDEV *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_RECTL *,uint,int,int,int,int *,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong),int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,tagCOLORADJUSTMENT *,_POINTL *,_RECTL *,_RECTL *,_POINTL *,ulong))
0x1400178e3  mov     r14d, [rsp+2E0h+var_270]
0x1400178e8  mov     edi, eax
0x1400178ea  test    r14d, r14d
0x1400178ed  jz      loc_1400180DC
0x1400178f3  jmp     short loc_1400178F8
0x1400178f5  xor     r14d, r14d
0x1400178f8  mov     rdi, [rbp+1E0h+var_230]
0x1400178fc  lea     rcx, [rbp+1E0h+psoSrc]; this
0x140017903  mov     r9, rdi; struct CddBitmap *
0x140017906  mov     r8, r13; struct CddBitmap *
0x140017909  mov     rdx, rbx; struct CDDPDEV *
0x14001790c  call    ??0GDIBITMAPACCESS2@@QEAA@PEAUCDDPDEV@@PEAVCddBitmap@@1@Z; GDIBITMAPACCESS2::GDIBITMAPACCESS2(CDDPDEV *,CddBitmap *,CddBitmap *)
0x140017911  xor     edx, edx; Val
0x140017913  lea     rcx, [rbp+1E0h+var_190]; void *
0x140017917  lea     r8d, [rdx+40h]; Size
0x14001791b  call    memset
0x140017920  xorps   xmm0, xmm0
0x140017923  movdqa  xmmword ptr [rbp+1E0h+var_150], xmm0
0x14001792b  test    r13, r13
0x14001792e  jz      loc_140017B91
0x140017934  mov     cl, [rbp+1E0h+var_70]
0x14001793a  xor     r14d, r14d
0x14001793d  test    cl, cl
0x14001793f  jz      loc_140017B25
0x140017945  mov     rax, [rbp+1E0h+var_B0]
0x14001794c  mov     rbx, [rax+1BF8h]
0x140017953  mov     rax, gs:188h
0x14001795c  cmp     [rbx+20h], rax
0x140017960  jz      loc_140017B1F
0x140017966  xor     r9d, r9d; Alertable
0x140017969  mov     [rsp+2E0h+Timeout], r14; Timeout
0x14001796e  xor     r8d, r8d; WaitMode
0x140017971  xor     edx, edx; WaitReason
0x140017973  mov     rcx, rbx; Object
0x140017976  call    cs:__imp_KeWaitForSingleObject
0x14001797d  nop     dword ptr [rax+rax+00h]
0x140017982  mov     ecx, eax
0x140017984  cmp     eax, 102h
0x140017989  jz      loc_140017B1F
0x14001798f  mov     rax, gs:188h
0x140017998  mov     [rbx+20h], rax
0x14001799c  test    ecx, ecx
0x14001799e  jns     loc_140017B1F
0x1400179a4  lea     ecx, [r14+2]
0x1400179a8  call    cs:__imp_WdLogSingleEntry0
0x1400179af  nop     dword ptr [rax+rax+00h]
0x1400179b4  mov     ebx, 26Ah
0x1400179b9  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400179bf  call    cs:__imp_WdLogNewEntry5_WdError
0x1400179c6  nop     dword ptr [rax+rax+00h]
0x1400179cb  mov     rcx, rax
0x1400179ce  lea     r15d, [r14+1]
0x1400179d2  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400179d9  mov     [rcx+18h], rax
0x1400179dd  mov     eax, cs:dword_14003E570
0x1400179e3  mov     [rcx+20h], rax
0x1400179e7  mov     [rcx+28h], rsi
0x1400179eb  mov     cs:WdLogGlobalForLineNumber, ebx
0x1400179f1  mov     ecx, 4
0x1400179f6  call    cs:__imp_WdLogSingleEntry0
0x1400179fd  nop     dword ptr [rax+rax+00h]
0x140017a02  mov     ebx, 0F1Fh
0x140017a07  mov     cs:WdLogGlobalForLineNumber, ebx
  ... truncated ...
```
