# DrvAlphaBlendInternal(_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_RECTL *,_BLENDOBJ *,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))

- ea: `0x140004904`
- end: `0x140005cb2`
- name: `?DrvAlphaBlendInternal@@YAHPEAU_SURFOBJ@@0PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@3PEAU_BLENDOBJ@@P6AH000123PEAU_POINTL@@5PEAU_BRUSHOBJ@@5K@Z@Z`
- size: `5038`
- prototype: `int(struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _RECTL *, struct _BLENDOBJ *, int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))`
- caller_count: `2`
- callee_count: `25`
- tags: `installer_update`

## callers

- `0x1400048c0`
- `0x140025090`

## callees

- `0x140001008`
- `0x140002470`
- `0x140004600`
- `0x140004904`
- `0x140008714`
- `0x14000874c`
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

- `ntoskrnl!KeWaitForSingleObject` at `0x140005314`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400057e7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140005314`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400057e7`
- `ntoskrnl!KeReleaseSemaphore` at `0x140005517`
- `ntoskrnl!KeReleaseSemaphore` at `0x140005763`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000597b`
- `ntoskrnl!KeReleaseSemaphore` at `0x140005ad1`
- `ntoskrnl!KeReleaseSemaphore` at `0x140005c50`
- `ntoskrnl!KeReleaseSemaphore` at `0x140005517`
- `ntoskrnl!KeReleaseSemaphore` at `0x140005763`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000597b`
- `ntoskrnl!KeReleaseSemaphore` at `0x140005ad1`
- `ntoskrnl!KeReleaseSemaphore` at `0x140005c50`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000509d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400051c6`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000509d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400051c6`
- `ntoskrnl!DbgPrint` at `0x140005a18`
- `ntoskrnl!DbgPrint` at `0x140005a18`
- `ntoskrnl!KdDebuggerEnabled` at `0x140005a05`
- `watchdog!WdLogSingleEntry2` at `0x140004b8f`
- `watchdog!WdLogSingleEntry2` at `0x140004b8f`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140004ba6`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140004ba6`
- `watchdog!WdLogNewEntry5_WdError` at `0x140004e58`
- `watchdog!WdLogNewEntry5_WdError` at `0x140005354`
- `watchdog!WdLogNewEntry5_WdError` at `0x140005652`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000582f`
- `watchdog!WdLogNewEntry5_WdError` at `0x140005a3f`
- `watchdog!WdLogNewEntry5_WdError` at `0x140004e58`
- `watchdog!WdLogNewEntry5_WdError` at `0x140005354`
- `watchdog!WdLogNewEntry5_WdError` at `0x140005652`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000582f`
- `watchdog!WdLogNewEntry5_WdError` at `0x140005a3f`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140004c0a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140004c0a`
- `watchdog!WdLogSingleEntry0` at `0x140004bf1`
- `watchdog!WdLogSingleEntry0` at `0x140004cf3`
- `watchdog!WdLogSingleEntry0` at `0x140004e41`
- `watchdog!WdLogSingleEntry0` at `0x140004eec`
- `watchdog!WdLogSingleEntry0` at `0x140004f0f`
- `watchdog!WdLogSingleEntry0` at `0x140005051`
- `watchdog!WdLogSingleEntry0` at `0x14000533d`
- `watchdog!WdLogSingleEntry0` at `0x1400053f7`
- `watchdog!WdLogSingleEntry0` at `0x14000563b`
- `watchdog!WdLogSingleEntry0` at `0x140005779`
- `watchdog!WdLogSingleEntry0` at `0x140005818`
- `watchdog!WdLogSingleEntry0` at `0x14000585f`
- `watchdog!WdLogSingleEntry0` at `0x140005a29`
- `watchdog!WdLogSingleEntry0` at `0x140004bf1`
- `watchdog!WdLogSingleEntry0` at `0x140004cf3`
- `watchdog!WdLogSingleEntry0` at `0x140004e41`
- `watchdog!WdLogSingleEntry0` at `0x140004eec`
- `watchdog!WdLogSingleEntry0` at `0x140004f0f`
- `watchdog!WdLogSingleEntry0` at `0x140005051`
- `watchdog!WdLogSingleEntry0` at `0x14000533d`
- `watchdog!WdLogSingleEntry0` at `0x1400053f7`
- `watchdog!WdLogSingleEntry0` at `0x14000563b`
- `watchdog!WdLogSingleEntry0` at `0x140005779`
- `watchdog!WdLogSingleEntry0` at `0x140005818`
- `watchdog!WdLogSingleEntry0` at `0x14000585f`
- `watchdog!WdLogSingleEntry0` at `0x140005a29`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140004d0a`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140004f26`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140005068`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000540e`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140005876`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140004d0a`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140004f26`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140005068`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000540e`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140005876`
- `WIN32K!EngAlphaBlend` at `0x140004b4d`
- `WIN32K!EngAlphaBlend` at `0x140005b51`
- `WIN32K!EngAlphaBlend` at `0x140004b4d`
- `WIN32K!EngAlphaBlend` at `0x140005b51`
- `WIN32K!EngBitBlt` at `0x140004c42`
- `WIN32K!EngBitBlt` at `0x140005564`

## string_xrefs

- `0x140005a11`: `Ivalid pco in GDIBITMAPACCESS2::StartAccessDst`

## pseudocode

```c
__int64 __fastcall DrvAlphaBlendInternal(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XLATEOBJ *a4,
        struct _RECTL *prclDest,
        struct _RECTL *prclSrc,
        struct _BLENDOBJ *a7,
        int (*a8)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))
{
  unsigned int v8; // r12d
  char *dhpdev; // rsi
  unsigned int v12; // ebx
  unsigned int (*v13)(void); // rax
  int v14; // r8d
  int v15; // ecx
  unsigned int iType; // eax
  USHORT v17; // cx
  USHORT v18; // dx
  BOOL v19; // edi
  __int64 v20; // rdx
  struct _SURFOBJ *v21; // r12
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  DHSURF dhsurf; // r12
  SURFOBJ *v25; // rax
  int v26; // edx
  int v27; // ecx
  _QWORD *v28; // rax
  __int64 v29; // r10
  _QWORD *v30; // rax
  ULONG cjBits; // ecx
  SURFOBJ *v32; // r11
  int v33; // esi
  _QWORD *v34; // rax
  bool v35; // zf
  LONG right; // r10d
  LONG left; // r9d
  int bottom; // r8d
  LONG top; // edx
  int v40; // eax
  _QWORD *v41; // rax
  void *v42; // rax
  SURFOBJ *v43; // r10
  char v44; // cl
  _QWORD *v45; // rsi
  NTSTATUS v46; // eax
  _QWORD *v47; // rax
  _QWORD *v48; // rax
  DHSURF v49; // rdi
  __int64 v50; // rcx
  struct _KTHREAD *v51; // rdx
  __int64 v52; // rdx
  SURFOBJ *v53; // rsi
  CStagingPool *v54; // rsi
  _QWORD *v55; // rax
  DHSURF v56; // rdi
  __int64 v57; // rcx
  struct _KTHREAD *v58; // rdx
  int v59; // esi
  char v60; // cl
  CLIPOBJ *v61; // r13
  _QWORD *v62; // r13
  NTSTATUS v63; // eax
  _QWORD *v64; // rax
  _QWORD *v65; // rax
  DHSURF v66; // rdi
  __int64 v67; // rcx
  struct _KTHREAD *v68; // rdx
  _QWORD *v70; // rax
  SURFOBJ *v71; // rdi
  __int64 v72; // rcx
  struct _KTHREAD *v73; // rdx
  int v74; // r8d
  int v75; // eax
  DHSURF v76; // rdi
  __int64 v77; // rcx
  struct _KTHREAD *v78; // rdx
  int v79; // [rsp+40h] [rbp-C0h]
  int v80; // [rsp+60h] [rbp-A0h] BYREF
  SURFOBJ *psoDest; // [rsp+68h] [rbp-98h] BYREF
  int v82; // [rsp+70h] [rbp-90h]
  CLIPOBJ *pco; // [rsp+78h] [rbp-88h] BYREF
  int v84; // [rsp+80h] [rbp-80h]
  SURFOBJ *psoSrc; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v86; // [rsp+90h] [rbp-70h]
  BLENDOBJ *pBlendObj; // [rsp+98h] [rbp-68h]
  BOOL (__stdcall *v88)(SURFOBJ *, SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *, POINTL *, BRUSHOBJ *, POINTL *, ROP4); // [rsp+A0h] [rbp-60h]
  XLATEOBJ *pxlo; // [rsp+A8h] [rbp-58h]
  CLIPOBJ *v90; // [rsp+B0h] [rbp-50h]
  unsigned int StagingVidMemAllocation; // [rsp+B8h] [rbp-48h]
  struct _SURFOBJ *v92; // [rsp+C0h] [rbp-40h]
  __int64 v93; // [rsp+C8h] [rbp-38h] BYREF
  int v94; // [rsp+D0h] [rbp-30h]
  __int64 v95; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v96; // [rsp+E0h] [rbp-20h]
  __int64 v97; // [rsp+E8h] [rbp-18h]
  int v98; // [rsp+F0h] [rbp-10h]
  _OWORD v99[3]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v100[24]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v101[8]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v102; // [rsp+180h] [rbp+80h]
  void *v103; // [rsp+190h] [rbp+90h]
  DHSURF v104; // [rsp+198h] [rbp+98h]
  unsigned int v105; // [rsp+1A0h] [rbp+A0h]
  unsigned int v106; // [rsp+1A4h] [rbp+A4h]
  int v107; // [rsp+1A8h] [rbp+A8h]
  int v108; // [rsp+1ACh] [rbp+ACh]
  int v109; // [rsp+1B0h] [rbp+B0h]
  char v110; // [rsp+1B4h] [rbp+B4h]
  _QWORD v111[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  CStagingPool *v112[2]; // [rsp+200h] [rbp+100h]
  SURFOBJ *v113[8]; // [rsp+210h] [rbp+110h] BYREF
  SURFOBJ *v114[8]; // [rsp+250h] [rbp+150h] BYREF
  struct CDDPDEV *v115; // [rsp+290h] [rbp+190h]
  CLIPOBJ *v116; // [rsp+298h] [rbp+198h]
  SURFOBJ *v117; // [rsp+2A0h] [rbp+1A0h]
  DHSURF v118; // [rsp+2A8h] [rbp+1A8h]
  struct _RECTL *v119; // [rsp+2B0h] [rbp+1B0h]
  __int64 v120; // [rsp+2B8h] [rbp+1B8h] BYREF
  int v121; // [rsp+2C0h] [rbp+1C0h]
  __int64 v122; // [rsp+2C8h] [rbp+1C8h]
  char v123; // [rsp+2D0h] [rbp+1D0h]
  __int64 v124; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v125; // [rsp+2F8h] [rbp+1F8h]
  int v126; // [rsp+2FCh] [rbp+1FCh]

  v8 = 0;
  pco = a3;
  dhpdev = (char *)a1->dhpdev;
  pBlendObj = a7;
  v12 = 1;
  v88 = a8;
  memset(v99, 0, sizeof(v99));
  v98 = 1;
  pxlo = a4;
  v13 = (unsigned int (*)(void))*((_QWORD *)dhpdev + 10);
  v92 = a1;
  psoDest = a1;
  psoSrc = a2;
  v82 = 0;
  v97 = 0;
  if ( v13() )
  {
    v15 = prclSrc->right - prclSrc->left;
    memset((char *)&v99[1] + 8, 0, 24);
    LODWORD(v99[0]) = a2->iType;
    iType = a1->iType;
    HIDWORD(v99[0]) = prclSrc->bottom - prclSrc->top;
    LODWORD(v99[1]) = prclDest->right - prclDest->left;
    DWORD1(v99[1]) = prclDest->bottom - prclDest->top;
    *(_QWORD *)((char *)v99 + 4) = __PAIR64__(v15, iType);
    CDDETWPROFILER::Init((CDDETWPROFILER *)&v95, (struct CDDPDEV *)dhpdev, 0xBD0u, (struct _DXGKETW_PARAMS *)v99, 0);
  }
  v17 = a2->iType;
  if ( v17 != 1 )
  {
    v18 = a1->iType;
    if ( v18 != 1 )
    {
      if ( v17 != 3 && v18 != 3 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 561;
        v23 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v23[3] = gCddImageInfo;
        v23[4] = (unsigned int)dword_14003E570;
        v23[5] = 215857758;
        WdLogGlobalForLineNumber = 561;
      }
      dhsurf = v92->dhsurf;
      if ( v88 == EngBitBlt )
        v25 = (SURFOBJ *)a2->dhsurf;
      else
        v25 = 0;
      psoDest = v25;
      CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(
        (CDDMULTIBITMAPLOCK *)v100,
        (struct CddBitmap *)dhsurf,
        (struct CddBitmap *)v25);
      if ( dhsurf && ((_DWORD)dhsurf[32] & 1) != 0 )
      {
        v26 = 1;
      }
      else
      {
        v26 = 0;
        if ( !dhsurf )
        {
          if ( psoDest )
            dhpdev = (char *)psoDest->hsurf;
LABEL_32:
          v27 = prclSrc->bottom - prclSrc->top;
          v80 = 0;
          if ( v27 > *((_DWORD *)dhpdev + 619) || prclSrc->right - prclSrc->left > *((_DWORD *)dhpdev + 618) || !v26 )
          {
LABEL_79:
            GDIBITMAPACCESS2::GDIBITMAPACCESS2(
              (GDIBITMAPACCESS2 *)v113,
              (struct CDDPDEV *)dhpdev,
              (struct CddBitmap *)psoDest,
              (struct CddBitmap *)dhsurf);
            memset(v101, 0, sizeof(v101));
            v43 = psoDest;
            v102 = 0;
            if ( psoDest )
            {
              v44 = v123;
              if ( v123 )
              {
                v45 = (_QWORD *)*((_QWORD *)v115 + 895);
                if ( (struct _KTHREAD *)v45[4] != KeGetCurrentThread() )
                {
                  v46 = KeWaitForSingleObject(v45, Executive, 0, 0, 0);
                  if ( v46 != 258 )
                  {
                    v45[4] = KeGetCurrentThread();
                    if ( v46 < 0 )
                    {
                      WdLogSingleEntry0(2);
                      WdLogGlobalForLineNumber = 618;
                      v47 = (_QWORD *)WdLogNewEntry5_WdError();
                      v47[3] = gCddImageInfo;
                      v47[4] = (unsigned int)dword_14003E570;
                      v47[5] = 215857758;
                      WdLogGlobalForLineNumber = 618;
LABEL_89:
                      WdLogSingleEntry0(4);
                      WdLogGlobalForLineNumber = 3125;
                      v48 = (_QWORD *)WdLogNewEntry5_WdEvent();
                      v48[3] = gCddImageInfo;
                      v48[4] = (unsigned int)dword_14003E570;
                      v48[5] = 215857758;
                      WdLogGlobalForLineNumber = 3125;
                      if ( (_QWORD)v102 )
                      {
                        *(_QWORD *)(v101[0] + 16LL) = *((_QWORD *)&v102 + 1);
                        CStagingPool::ReleaseGdiSurface((CStagingPool *)v102, (struct CDDBITMAP_GDIDESC *)v101);
                      }
                      if ( v117 )
                        (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v117->dhsurf + 16))(v117, v113);
                      v49 = v118;
                      if ( v118 )
                      {
                        if ( !v121 )
                          (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))(*(_QWORD *)v118 + 64LL))(
                            v118,
                            v114,
                            v119,
                            v116,
                            v122);
                        (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v49 + 128LL))(v49, v114);
                      }
                      v50 = *((_QWORD *)v115 + 895);
                      v51 = *(struct _KTHREAD **)(v50 + 32);
                      if ( v51 == KeGetCurrentThread() && v51 )
                      {
                        *(_QWORD *)(v50 + 32) = 0;
                        KeReleaseSemaphore((PRKSEMAPHORE)v50, 0, 1, 0);
                      }
                      CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v100);
                      if ( !v98 )
                      {
                        LOBYTE(v52) = 2;
                        (*(void (__fastcall **)(_QWORD, __int64, __int64))(v95 + 264))(v96, v52, v97);
                      }
                      return v12;
                    }
                  }
                  v43 = psoDest;
                }
                v44 = v123;
              }
              LOBYTE(v79) = v44 == 0;
              if ( (*((int (__fastcall **)(SURFOBJ *, struct _RECTL *, struct _RECTL *, _QWORD, int, int, __int64 *, SURFOBJ **, int))v43->dhsurf
                    + 7))(
                     v43,
                     prclSrc,
                     prclSrc,
                     0,
                     1,
                     1,
                     &v120,
                     v113,
                     v79) < 0 )
                goto LABEL_89;
              v117 = psoDest;
              v116 = 0;
              v53 = v113[0];
LABEL_120:
              if ( dhsurf )
              {
                v60 = v123;
                v61 = pco;
                v90 = pco;
                if ( v123 )
                {
                  v62 = (_QWORD *)*((_QWORD *)v115 + 895);
                  if ( (struct _KTHREAD *)v62[4] != KeGetCurrentThread() )
                  {
                    v63 = KeWaitForSingleObject(v62, Executive, 0, 0, 0);
                    if ( v63 != 258 )
                    {
                      v62[4] = KeGetCurrentThread();
                      if ( v63 < 0 )
                      {
                        WdLogSingleEntry0(2);
                        WdLogGlobalForLineNumber = 659;
                        v64 = (_QWORD *)WdLogNewEntry5_WdError();
                        v64[3] = gCddImageInfo;
                        v64[4] = (unsigned int)dword_14003E570;
                        v64[5] = 215857758;
                        WdLogGlobalForLineNumber = 659;
LABEL_126:
                        WdLogSingleEntry0(4);
                        v59 = 3168;
                        goto LABEL_127;
                      }
                    }
                  }
                  v60 = v123;
                  v61 = v90;
                }
                LOBYTE(v79) = v60 == 0;
                if ( (*(int (__fastcall **)(DHSURF, struct _RECTL *, struct _RECTL *, CLIPOBJ *, int, int, char *, SURFOBJ **, int))(*(_QWORD *)dhsurf + 56LL))(
                       dhsurf,
                       prclDest,
                       prclDest,
                       v61,
                       1,
                       1,
                       (char *)&v120 + 4,
                       v114,
                       v79) < 0 )
                  goto LABEL_126;
                if ( v116 && v61 != v116 && (_BYTE)KdDebuggerEnabled )
                {
                  DbgPrint("Ivalid pco in GDIBITMAPACCESS2::StartAccessDst");
                  WdLogSingleEntry0(2);
                  WdLogGlobalForLineNumber = 670;
                  v70 = (_QWORD *)WdLogNewEntry5_WdError();
                  v70[3] = gCddImageInfo;
                  v70[4] = (unsigned int)dword_14003E570;
                  v70[5] = 215857758;
                  WdLogGlobalForLineNumber = 670;
                  __debugbreak();
                }
                v71 = v114[0];
                v118 = dhsurf;
                v119 = prclDest;
                v116 = v61;
                v122 = 0;
              }
              else
              {
                v71 = v92;
              }
              v72 = *((_QWORD *)v115 + 895);
              v73 = *(struct _KTHREAD **)(v72 + 32);
              if ( v73 == KeGetCurrentThread() && v73 )
              {
                *(_QWORD *)(v72 + 32) = 0;
                KeReleaseSemaphore((PRKSEMAPHORE)v72, 0, 1, 0);
              }
              v74 = HIDWORD(v120);
              if ( v120 )
              {
                CDDPDEV::Flush(v115);
                v74 = HIDWORD(v120);
              }
              WaitForStartGdiAccessToFinish(v115, (struct CDDBITMAP_GDIDESC *)v114, v74);
              WaitForStartGdiAccessToFinish(v115, (struct CDDBITMAP_GDIDESC *)v113, v120);
              v8 = EngAlphaBlend(v71, v53, pco, pxlo, prclDest, prclSrc, pBlendObj);
              v75 = v121;
              if ( !v8 )
                v75 = 1;
              v121 = v75;
              if ( (_QWORD)v102 )
              {
                *(_QWORD *)(v101[0] + 16LL) = *((_QWORD *)&v102 + 1);
                CStagingPool::ReleaseGdiSurface((CStagingPool *)v102, (struct CDDBITMAP_GDIDESC *)v101);
              }
              if ( v117 )
                (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v117->dhsurf + 16))(v117, v113);
              v76 = v118;
              if ( v118 )
              {
                if ( !v121 )
                  (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))(*(_QWORD *)v118
                                                                                                  + 64LL))(
                    v118,
                    v114,
                    v119,
                    v116,
                    v122);
                (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v76 + 128LL))(v76, v114);
              }
              v77 = *((_QWORD *)v115 + 895);
              v78 = *(struct _KTHREAD **)(v77 + 32);
              if ( v78 == KeGetCurrentThread() && v78 )
              {
                *(_QWORD *)(v77 + 32) = 0;
                KeReleaseSemaphore((PRKSEMAPHORE)v77, 0, 1, 0);
              }
              goto LABEL_168;
            }
            if ( v88 == EngBitBlt )
              goto LABEL_119;
            v54 = (CStagingPool *)(dhpdev + 5504);
            if ( (int)CStagingPool::GetGdiSurface(
                        v54,
                        a2->sizlBitmap.cx,
                        a2->sizlBitmap.cy,
                        (const struct tagRECT *)prclSrc,
                        (struct CDDBITMAP_GDIDESC *)v101,
                        1u) < 0 )
            {
              WdLogSingleEntry0(4);
              v59 = 3134;
LABEL_127:
              WdLogGlobalForLineNumber = v59;
              v65 = (_QWORD *)WdLogNewEntry5_WdEvent();
              v65[3] = gCddImageInfo;
              v65[4] = (unsigned int)dword_14003E570;
              v65[5] = 215857758;
              WdLogGlobalForLineNumber = v59;
              if ( (_QWORD)v102 )
              {
                *(_QWORD *)(v101[0] + 16LL) = *((_QWORD *)&v102 + 1);
                CStagingPool::ReleaseGdiSurface((CStagingPool *)v102, (struct CDDBITMAP_GDIDESC *)v101);
              }
              if ( v117 )
                (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v117->dhsurf + 16))(v117, v113);
              v66 = v118;
              if ( v118 )
              {
                if ( !v121 )
                  (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))(*(_QWORD *)v118
                                                                                                  + 64LL))(
                    v118,
                    v114,
                    v119,
                    v116,
                    v122);
                (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v66 + 128LL))(v66, v114);
              }
              v67 = *((_QWORD *)v115 + 895);
              v68 = *(struct _KTHREAD **)(v67 + 32);
              if ( v68 == KeGetCurrentThread() && v68 )
              {
                *(_QWORD *)(v67 + 32) = 0;
                KeReleaseSemaphore((PRKSEMAPHORE)v67, 0, 1, 0);
              }
              goto LABEL_138;
            }
            *(_QWORD *)&v102 = v54;
            *((_QWORD *)&v102 + 1) = *(_QWORD *)(v101[0] + 16LL);
            *(_QWORD *)(v101[0] + 16LL) = 0;
            v53 = (SURFOBJ *)v101[0];
            if ( (unsigned __int64)(*(int *)(v101[0] + 64LL) * (__int64)(prclSrc->top + 1) + 0x80000000LL) > 0xFFFFFFFF
              || v80 )
            {
LABEL_119:
              v53 = a2;
              goto LABEL_120;
            }
            if ( ((unsigned int (__fastcall *)(_QWORD, struct _SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, struct _RECTL *, struct _RECTL *, _QWORD, _QWORD, _QWORD, int))v88)(
                   v101[0],
                   a2,
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
              goto LABEL_120;
            }
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 3152;
            v55 = (_QWORD *)WdLogNewEntry5_WdError();
            v55[3] = gCddImageInfo;
            v55[4] = (unsigned int)dword_14003E570;
            v55[5] = 215857758;
            WdLogGlobalForLineNumber = 3152;
            if ( (_QWORD)v102 )
            {
              *(_QWORD *)(v101[0] + 16LL) = *((_QWORD *)&v102 + 1);
              CStagingPool::ReleaseGdiSurface((CStagingPool *)v102, (struct CDDBITMAP_GDIDESC *)v101);
            }
            if ( v117 )
              (*((void (__fastcall **)(SURFOBJ *, SURFOBJ **))v117->dhsurf + 16))(v117, v113);
            v56 = v118;
            if ( v118 )
            {
              if ( !v121 )
                (*(void (__fastcall **)(DHSURF, SURFOBJ **, struct _RECTL *, CLIPOBJ *, __int64))(*(_QWORD *)v118 + 64LL))(
                  v118,
                  v114,
                  v119,
                  v116,
                  v122);
              (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v56 + 128LL))(v56, v114);
            }
            v57 = *((_QWORD *)v115 + 895);
            v58 = *(struct _KTHREAD **)(v57 + 32);
            if ( v58 == KeGetCurrentThread() && v58 )
            {
              *(_QWORD *)(v57 + 32) = 0;
              KeReleaseSemaphore((PRKSEMAPHORE)v57, 0, 1, 0);
            }
LABEL_46:
            v12 = 0;
            goto LABEL_138;
          }
          if ( !pBlendObj->BlendFunction.SourceConstantAlpha )
          {
            v8 = 1;
LABEL_168:
            CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v100);
            goto LABEL_169;
          }
          DWORD2(v99[1]) = 1;
          v86 = *((_DWORD *)dhsurf + 10);
          if ( !v86 )
          {
            WdLogSingleEntry0(4);
            WdLogGlobalForLineNumber = 2982;
            v28 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v28[3] = gCddImageInfo;
            v28[4] = (unsigned int)dword_14003E570;
            v28[5] = 215857758;
            WdLogGlobalForLineNumber = 2982;
LABEL_138:
            CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v100);
            goto LABEL_139;
          }
          memset(v111, 0, sizeof(v111));
          *(_OWORD *)v112 = 0;
          if ( psoDest )
          {
            cjBits = psoDest->cjBits;
            v82 = cjBits;
            if ( cjBits )
            {
              psoSrc = (SURFOBJ *)prclSrc;
              v32 = psoDest;
              v84 = 0;
              goto LABEL_55;
            }
            WdLogSingleEntry0(4);
            v33 = 3033;
          }
          else
          {
            if ( (int)CStagingPool::GetGdiSurface(
                        (CStagingPool *)(dhpdev + 5504),
                        a2->sizlBitmap.cx,
                        a2->sizlBitmap.cy,
                        (const struct tagRECT *)prclSrc,
                        (struct CDDBITMAP_GDIDESC *)v111,
                        1u) >= 0 )
            {
              v112[0] = (CStagingPool *)(dhpdev + 5504);
              v112[1] = *(CStagingPool **)(v111[0] + 16LL);
              *(_QWORD *)(v111[0] + 16LL) = 0;
              v29 = v111[0];
              if ( (unsigned __int64)(*(int *)(v111[0] + 64LL) * (__int64)(prclSrc->top + 1) + 0x80000000LL) > 0xFFFFFFFF )
              {
                v80 = 1;
                goto LABEL_76;
              }
              if ( !((unsigned int (__fastcall *)(_QWORD, struct _SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, struct _RECTL *, struct _RECTL *, _QWORD, _QWORD, _QWORD, int))v88)(
                      v111[0],
                      a2,
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
                WdLogGlobalForLineNumber = 3017;
                v30 = (_QWORD *)WdLogNewEntry5_WdError();
                v30[3] = gCddImageInfo;
                v30[4] = (unsigned int)dword_14003E570;
                v30[5] = 215857758;
                WdLogGlobalForLineNumber = 3017;
                if ( v112[0] )
                {
                  *(CStagingPool **)(v111[0] + 16LL) = v112[1];
                  CStagingPool::ReleaseGdiSurface(v112[0], (struct CDDBITMAP_GDIDESC *)v111);
                }
                goto LABEL_46;
              }
              cjBits = v111[2];
              v32 = (SURFOBJ *)v111[3];
              psoSrc = (SURFOBJ *)((char *)&v111[4] + 4);
              v82 = v111[2];
              v84 = *(_DWORD *)(v111[0] + 64LL);
LABEL_55:
              right = prclDest->right;
              left = prclDest->left;
              bottom = prclDest->bottom;
              top = prclDest->top;
              v125 = right - prclDest->left;
              v90 = (CLIPOBJ *)v32;
              v124 = 0;
              v126 = bottom - top;
              if ( psoDest != (SURFOBJ *)dhsurf )
                goto LABEL_74;
              v40 = *((_DWORD *)dhpdev + 475);
              if ( (v40 & 8) != 0 )
                goto LABEL_68;
              if ( (v40 & 0x40) == 0 )
                goto LABEL_74;
              if ( prclSrc->left > left )
                left = prclSrc->left;
              if ( prclSrc->right < right )
                right = prclSrc->right;
              if ( left >= right )
                goto LABEL_74;
              if ( prclSrc->top > top )
                top = prclSrc->top;
              if ( prclSrc->bottom < bottom )
                bottom = prclSrc->bottom;
              if ( top < bottom )
              {
LABEL_68:
                CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v93, *((struct CDDMUTEX **)dhpdev + 364), bottom);
                StagingVidMemAllocation = CddBitmapStagingVidMem::GetStagingVidMemAllocation(
                                            *((CddBitmapStagingVidMem **)dhpdev + 687),
                                            (const struct tagRECT *)prclDest);
                if ( !StagingVidMemAllocation )
                {
                  WdLogSingleEntry0(4);
                  WdLogGlobalForLineNumber = 3055;
                  v41 = (_QWORD *)WdLogNewEntry5_WdEvent();
                  v35 = v94 == 0;
                  v41[3] = gCddImageInfo;
                  v41[4] = (unsigned int)dword_14003E570;
                  v41[5] = 215857758;
                  WdLogGlobalForLineNumber = 3055;
                  if ( !v35 )
                    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v93);
                  v35 = v112[0] == 0;
                  goto LABEL_52;
                }
                v101[0] = pco;
                v101[1] = psoSrc;
                v101[3] = &v124;
                v103 = v90;
                v104 = (DHSURF)*((_QWORD *)dhpdev + 687);
                v105 = v82;
                LOBYTE(v101[6]) = 0;
                v110 = 0;
                v106 = StagingVidMemAllocation;
                v109 = 0;
                v101[5] = 0;
                v108 = v84;
                v101[2] = prclDest;
                *((_QWORD *)&v102 + 1) = dhpdev;
                v107 = 1;
                ClipDstRects(
                  (struct CLIP_RECTS_DATA *)v101,
                  (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::BitBltCallback);
                v101[0] = pco;
                v101[1] = &v124;
                LOBYTE(v101[6]) = 0;
                v35 = pBlendObj->BlendFunction.AlphaFormat == 1;
                BYTE1(v107) = pBlendObj->BlendFunction.SourceConstantAlpha;
                v42 = (void *)*((_QWORD *)dhpdev + 687);
                LOBYTE(v107) = v35;
                v103 = v42;
                v105 = StagingVidMemAllocation;
                *((_QWORD *)&v102 + 1) = 0;
                v108 = 0;
                v101[5] = 0;
                v106 = v86;
                v101[2] = prclDest;
                v101[3] = prclDest;
                v104 = dhsurf;
                ClipDstRects(
                  (struct CLIP_RECTS_DATA *)v101,
                  (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::AlphaBlendCallback);
                if ( v94 )
                  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v93);
              }
              else
              {
LABEL_74:
                v101[0] = pco;
                v101[1] = psoSrc;
                v35 = pBlendObj->BlendFunction.AlphaFormat == 1;
                BYTE1(v107) = pBlendObj->BlendFunction.SourceConstantAlpha;
                LOBYTE(v107) = v35;
                v106 = v86;
                v105 = cjBits;
                v108 = v84;
                LOBYTE(v101[6]) = 0;
                *((_QWORD *)&v102 + 1) = 0;
                v101[2] = prclDest;
                v101[3] = prclDest;
                v103 = v32;
                v104 = dhsurf;
                v101[5] = 0;
                ClipDstRects(
                  (struct CLIP_RECTS_DATA *)v101,
                  (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::AlphaBlendCallback);
              }
              CddBitmap::VidMemDirtyUpdate((CddBitmap *)dhsurf);
              v29 = v111[0];
              v82 = 1;
LABEL_76:
              if ( v112[0] )
              {
                *(CStagingPool **)(v29 + 16) = v112[1];
                CStagingPool::ReleaseGdiSurface(v112[0], (struct CDDBITMAP_GDIDESC *)v111);
              }
              if ( !v80 )
              {
                v8 = v82;
                goto LABEL_168;
              }
              goto LABEL_79;
            }
            WdLogSingleEntry0(4);
            v33 = 2999;
          }
          WdLogGlobalForLineNumber = v33;
          v34 = (_QWORD *)WdLogNewEntry5_WdEvent();
          v34[3] = gCddImageInfo;
          v34[4] = (unsigned int)dword_14003E570;
          v34[5] = 215857758;
          v35 = v112[0] == 0;
          WdLogGlobalForLineNumber = v33;
LABEL_52:
          if ( !v35 )
          {
            *(CStagingPool **)(v111[0] + 16LL) = v112[1];
            CStagingPool::ReleaseGdiSurface(v112[0], (struct CDDBITMAP_GDIDESC *)v111);
          }
          goto LABEL_138;
        }
      }
      dhpdev = (char *)*((_QWORD *)dhsurf + 1);
      goto LABEL_32;
    }
  }
  CDDDEVLOCK::CDDDEVLOCK((CDDDEVLOCK *)&v93, *((HSEMAPHORE *)dhpdev + 365), v14);
  if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
  {
    v19 = 1;
  }
  else
  {
    CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
    *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
    *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 56LL) = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
    v19 = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) != 0;
  }
  CDDDEVLOCK::vUnlock((CDDDEVLOCK *)&v93);
  if ( v19 )
  {
    v21 = v92;
    if ( v92->iType == 3 || a2 && a2->iType == 3 )
    {
      WdLogSingleEntry2(3, a2, v92);
      WdLogGlobalForLineNumber = 581;
      v22 = (_QWORD *)WdLogNewEntry5_WdWarning();
      v22[3] = gCddImageInfo;
      v22[4] = (unsigned int)dword_14003E570;
      v22[5] = 215857758;
      WdLogGlobalForLineNumber = 581;
      goto LABEL_139;
    }
    ReadFromFrameBuffer((struct CDDPDEV *)dhpdev, prclDest->left, prclDest->top, prclDest->right, prclDest->bottom);
    v80 = 0;
    CDDMULTISURFLOCK::vInit(
      (CDDMULTISURFLOCK *)v113,
      (struct CDDPDEV *)dhpdev,
      &psoDest,
      &psoSrc,
      prclDest,
      prclSrc,
      &v80,
      pco);
    if ( bIgnoreDeviceSurfaceUpdates(v21, &pco) )
    {
      CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)v113);
LABEL_139:
      CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v95);
      return v12;
    }
    v8 = EngAlphaBlend(psoDest, psoSrc, pco, pxlo, prclDest, prclSrc, pBlendObj);
    if ( v8 && v80 == 1 )
      vGDIDirtyUpdate((struct CDDPDEV *)dhpdev, (struct tagRECT *)prclDest, pco);
    CDDMULTISURFLOCK::vDone((CDDMULTISURFLOCK *)v113);
  }
LABEL_169:
  if ( !v98 )
  {
    LOBYTE(v20) = 2;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(v95 + 264))(v96, v20, v97);
  }
  return v8;
}

```

## disassembly

```asm
0x140004904  push    rbp
0x140004906  push    rbx
0x140004907  push    rsi
0x140004908  push    rdi
0x140004909  push    r12
0x14000490b  push    r13
0x14000490d  push    r14
0x14000490f  push    r15
0x140004911  lea     rbp, [rsp-218h]
0x140004919  sub     rsp, 318h
0x140004920  mov     rax, cs:__security_cookie
0x140004927  xor     rax, rsp
0x14000492a  mov     [rbp+250h+var_50], rax
0x140004931  mov     rax, [rbp+250h+arg_30]
0x140004938  xorps   xmm0, xmm0
0x14000493b  mov     r14, [rbp+250h+arg_20]
0x140004942  xor     r12d, r12d
0x140004945  mov     r15, [rbp+250h+arg_28]
0x14000494c  mov     r13, rdx
0x14000494f  mov     [rsp+350h+pco], r8
0x140004954  mov     rdi, rcx
0x140004957  mov     rsi, [rcx+10h]
0x14000495b  mov     [rbp+250h+var_2B8], rax
0x14000495f  lea     ebx, [r12+1]
0x140004964  mov     rax, [rbp+250h+arg_38]
0x14000496b  mov     [rbp+250h+var_2B0], rax
0x14000496f  movups  [rbp+250h+var_258], xmm0
0x140004973  mov     [rbp+250h+var_260], ebx
0x140004976  movups  [rbp+250h+var_248], xmm0
0x14000497a  mov     [rbp+250h+pxlo], r9
0x14000497e  movups  [rbp+250h+var_238], xmm0
0x140004982  mov     rax, [rsi+50h]
0x140004986  mov     [rbp+250h+var_290], rcx
0x14000498a  mov     [rsp+350h+psoDest], rcx
0x14000498f  mov     [rbp+250h+psoSrc], rdx
0x140004993  mov     [rsp+350h+var_2E0], r12d
0x140004998  mov     [rbp+250h+var_268], r12
0x14000499c  call    _guard_dispatch_icall
0x1400049a1  test    eax, eax
0x1400049a3  jz      short loc_140004A05
0x1400049a5  mov     ecx, [r15+8]
0x1400049a9  lea     r9, [rbp+250h+var_258]; struct _DXGKETW_PARAMS *
0x1400049ad  sub     ecx, [r15]
0x1400049b0  xorps   xmm0, xmm0
0x1400049b3  movdqu  [rbp+250h+var_248+8], xmm0
0x1400049b8  mov     qword ptr [rbp+250h+var_238+8], r12
0x1400049bc  mov     r8d, 0BD0h; unsigned int
0x1400049c2  movzx   eax, word ptr [r13+4Ch]
0x1400049c7  mov     rdx, rsi; struct CDDPDEV *
0x1400049ca  mov     dword ptr [rbp+250h+var_258], eax
0x1400049cd  movzx   eax, word ptr [rdi+4Ch]
0x1400049d1  mov     dword ptr [rbp+250h+var_258+8], ecx
0x1400049d4  mov     ecx, [r15+0Ch]
0x1400049d8  sub     ecx, [r15+4]
0x1400049dc  mov     dword ptr [rbp+250h+var_258+0Ch], ecx
0x1400049df  mov     ecx, [r14+8]
0x1400049e3  sub     ecx, [r14]
0x1400049e6  mov     dword ptr [rbp+250h+var_248], ecx
0x1400049e9  mov     ecx, [r14+0Ch]
0x1400049ed  sub     ecx, [r14+4]
0x1400049f1  mov     dword ptr [rbp+250h+var_248+4], ecx
0x1400049f4  lea     rcx, [rbp+250h+var_278]; this
0x1400049f8  mov     dword ptr [rbp+250h+var_258+4], eax
0x1400049fb  mov     byte ptr [rsp+350h+prclDest], r12b; bool
0x140004a00  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x140004a05  movzx   ecx, word ptr [r13+4Ch]
0x140004a0a  cmp     cx, bx
0x140004a0d  jz      short loc_140004A1C
0x140004a0f  movzx   edx, word ptr [rdi+4Ch]
0x140004a13  cmp     dx, bx
0x140004a16  jnz     loc_140004BDB
0x140004a1c  mov     rdx, [rsi+0B68h]; HSEMAPHORE
0x140004a23  lea     rcx, [rbp+250h+var_288]; this
0x140004a27  call    ??0CDDDEVLOCK@@QEAA@PEAUHSEMAPHORE__@@H@Z; CDDDEVLOCK::CDDDEVLOCK(HSEMAPHORE__ *,int)
0x140004a2c  mov     rax, [rsi+0AE8h]
0x140004a33  cmp     [rax+30h], r12
0x140004a37  jnz     short loc_140004A75
0x140004a39  mov     rcx, rsi; struct CDDPDEV *
0x140004a3c  call    ?CddAllocShadowSysMem@@YAXQEAUCDDPDEV@@@Z; CddAllocShadowSysMem(CDDPDEV * const)
0x140004a41  mov     rcx, [rsi+0AE8h]
0x140004a48  xor     edi, edi
0x140004a4a  mov     rax, [rsi+9F8h]
0x140004a51  mov     [rcx+30h], rax
0x140004a55  mov     rcx, [rsi+0AE8h]
0x140004a5c  mov     rax, [rcx+30h]
0x140004a60  mov     [rcx+38h], rax
0x140004a64  mov     rax, [rsi+0AE8h]
0x140004a6b  cmp     [rax+30h], rdi
0x140004a6f  setnz   dil
0x140004a73  jmp     short loc_140004A77
0x140004a75  mov     edi, ebx
0x140004a77  lea     rcx, [rbp+250h+var_288]; this
0x140004a7b  call    ?vUnlock@CDDDEVLOCK@@QEAAXXZ; CDDDEVLOCK::vUnlock(void)
0x140004a80  test    edi, edi
0x140004a82  jz      loc_140005C6C
0x140004a88  mov     r12, [rbp+250h+var_290]
0x140004a8c  mov     eax, 3
0x140004a91  cmp     [r12+4Ch], ax
0x140004a97  jz      loc_140004B87
0x140004a9d  test    r13, r13
0x140004aa0  jz      short loc_140004AAD
0x140004aa2  cmp     [r13+4Ch], ax
0x140004aa7  jz      loc_140004B87
0x140004aad  mov     eax, [r14+0Ch]
0x140004ab1  mov     rcx, rsi; struct CDDPDEV *
0x140004ab4  mov     r9d, [r14+8]; int
0x140004ab8  mov     r8d, [r14+4]; int
0x140004abc  mov     edx, [r14]; int
0x140004abf  mov     dword ptr [rsp+350h+prclDest], eax; int
0x140004ac3  call    ?ReadFromFrameBuffer@@YAXPEAUCDDPDEV@@HHHH@Z; ReadFromFrameBuffer(CDDPDEV *,int,int,int,int)
0x140004ac8  mov     rax, [rsp+350h+pco]
0x140004acd  lea     r9, [rbp+250h+psoSrc]; struct _SURFOBJ **
0x140004ad1  mov     [rsp+350h+var_318], rax; struct _CLIPOBJ *
0x140004ad6  lea     r8, [rsp+350h+psoDest]; struct _SURFOBJ **
0x140004adb  lea     rax, [rsp+350h+var_2F0]
0x140004ae0  mov     [rsp+350h+var_2F0], 0
0x140004ae8  mov     [rsp+350h+pBlendObj], rax; int *
0x140004aed  lea     rcx, [rbp+250h+var_140]; this
0x140004af4  mov     [rsp+350h+prclSrc], r15; struct _RECTL *
0x140004af9  mov     rdx, rsi; struct CDDPDEV *
0x140004afc  mov     [rsp+350h+prclDest], r14; struct _RECTL *
0x140004b01  call    ?vInit@CDDMULTISURFLOCK@@QEAAXPEAUCDDPDEV@@PEAPEAU_SURFOBJ@@1PEAU_RECTL@@2PEAHPEAU_CLIPOBJ@@@Z; CDDMULTISURFLOCK::vInit(CDDPDEV *,_SURFOBJ * *,_SURFOBJ * *,_RECTL *,_RECTL *,int *,_CLIPOBJ *)
0x140004b06  lea     rdx, [rsp+350h+pco]; struct _CLIPOBJ **
0x140004b0b  mov     rcx, r12; struct _SURFOBJ *
0x140004b0e  call    ?bIgnoreDeviceSurfaceUpdates@@YAHPEAU_SURFOBJ@@PEAPEAU_CLIPOBJ@@@Z; bIgnoreDeviceSurfaceUpdates(_SURFOBJ *,_CLIPOBJ * *)
0x140004b13  test    eax, eax
0x140004b15  jz      short loc_140004B28
0x140004b17  lea     rcx, [rbp+250h+var_140]; this
0x140004b1e  call    ?vDone@CDDMULTISURFLOCK@@QEAAXXZ; CDDMULTISURFLOCK::vDone(void)
0x140004b23  jmp     loc_140005990
0x140004b28  mov     rax, [rbp+250h+var_2B8]
0x140004b2c  mov     r9, [rbp+250h+pxlo]; pxlo
0x140004b30  mov     r8, [rsp+350h+pco]; pco
0x140004b35  mov     rdx, [rbp+250h+psoSrc]; psoSrc
0x140004b39  mov     rcx, [rsp+350h+psoDest]; psoDest
0x140004b3e  mov     [rsp+350h+pBlendObj], rax; pBlendObj
0x140004b43  mov     [rsp+350h+prclSrc], r15; prclSrc
0x140004b48  mov     [rsp+350h+prclDest], r14; prclDest
0x140004b4d  call    cs:__imp_EngAlphaBlend
0x140004b54  nop     dword ptr [rax+rax+00h]
0x140004b59  mov     r12d, eax
0x140004b5c  test    eax, eax
0x140004b5e  jz      short loc_140004B76
0x140004b60  cmp     [rsp+350h+var_2F0], ebx
0x140004b64  jnz     short loc_140004B76
0x140004b66  mov     r8, [rsp+350h+pco]; struct _CLIPOBJ *
0x140004b6b  mov     rdx, r14; struct _RECTL *
0x140004b6e  mov     rcx, rsi; struct CDDPDEV *
0x140004b71  call    ?vGDIDirtyUpdate@@YAXPEAUCDDPDEV@@PEAU_RECTL@@PEAU_CLIPOBJ@@@Z; vGDIDirtyUpdate(CDDPDEV *,_RECTL *,_CLIPOBJ *)
0x140004b76  lea     rcx, [rbp+250h+var_140]; this
0x140004b7d  call    ?vDone@CDDMULTISURFLOCK@@QEAAXXZ; CDDMULTISURFLOCK::vDone(void)
0x140004b82  jmp     loc_140005C6C
0x140004b87  mov     r8, r12
0x140004b8a  mov     rdx, r13
0x140004b8d  mov     ecx, eax
0x140004b8f  call    cs:__imp_WdLogSingleEntry2
0x140004b96  nop     dword ptr [rax+rax+00h]
0x140004b9b  mov     esi, 245h
0x140004ba0  mov     cs:WdLogGlobalForLineNumber, esi
0x140004ba6  call    cs:__imp_WdLogNewEntry5_WdWarning
0x140004bad  nop     dword ptr [rax+rax+00h]
0x140004bb2  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140004bb9  mov     edi, 0CDDBA5Eh
0x140004bbe  mov     [rax+18h], rcx
0x140004bc2  mov     ecx, cs:dword_14003E570
0x140004bc8  mov     [rax+20h], rcx
0x140004bcc  mov     [rax+28h], rdi
0x140004bd0  mov     cs:WdLogGlobalForLineNumber, esi
0x140004bd6  jmp     loc_140005990
0x140004bdb  mov     eax, 3
0x140004be0  mov     edi, 0CDDBA5Eh
0x140004be5  cmp     cx, ax
0x140004be8  jz      short loc_140004C36
0x140004bea  cmp     dx, ax
0x140004bed  jz      short loc_140004C36
0x140004bef  mov     ecx, ebx
0x140004bf1  call    cs:__imp_WdLogSingleEntry0
0x140004bf8  nop     dword ptr [rax+rax+00h]
0x140004bfd  mov     r12d, 231h
0x140004c03  mov     cs:WdLogGlobalForLineNumber, r12d
0x140004c0a  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140004c11  nop     dword ptr [rax+rax+00h]
0x140004c16  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140004c1d  mov     [rax+18h], rcx
0x140004c21  mov     ecx, cs:dword_14003E570
0x140004c27  mov     [rax+20h], rcx
0x140004c2b  mov     [rax+28h], rdi
0x140004c2f  mov     cs:WdLogGlobalForLineNumber, r12d
0x140004c36  mov     r12, [rbp+250h+var_290]
0x140004c3a  mov     rax, [rbp+250h+var_2B0]
0x140004c3e  mov     r12, [r12]
0x140004c42  cmp     rax, cs:__imp_EngBitBlt
0x140004c49  jnz     short loc_140004C51
0x140004c4b  mov     rax, [r13+0]
0x140004c4f  jmp     short loc_140004C53
0x140004c51  xor     eax, eax
0x140004c53  mov     r8, rax; struct CddBitmap *
0x140004c56  mov     [rsp+350h+psoDest], rax
0x140004c5b  mov     rdx, r12; struct CddBitmap *
0x140004c5e  lea     rcx, [rbp+250h+var_228]; this
0x140004c62  call    ??0CDDMULTIBITMAPLOCK@@QEAA@PEAVCddBitmap@@0@Z; CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(CddBitmap *,CddBitmap *)
0x140004c67  test    r12, r12
0x140004c6a  jz      short loc_140004C7C
0x140004c6c  mov     eax, [r12+80h]
0x140004c74  test    bl, al
0x140004c76  jz      short loc_140004C7C
0x140004c78  mov     edx, ebx
0x140004c7a  jmp     short loc_140004C83
0x140004c7c  xor     edx, edx
0x140004c7e  test    r12, r12
0x140004c81  jz      short loc_140004C8A
0x140004c83  mov     rsi, [r12+8]
0x140004c88  jmp     short loc_140004C98
0x140004c8a  mov     rax, [rsp+350h+psoDest]
0x140004c8f  test    rax, rax
0x140004c92  jz      short loc_140004C98
0x140004c94  mov     rsi, [rax+8]
0x140004c98  mov     ecx, [r15+0Ch]
0x140004c9c  sub     ecx, [r15+4]
0x140004ca0  mov     [rsp+350h+var_2F0], 0
0x140004ca8  cmp     ecx, [rsi+9ACh]
0x140004cae  jg      loc_140005292
0x140004cb4  mov     ecx, [r15+8]
0x140004cb8  sub     ecx, [r15]
0x140004cbb  cmp     ecx, [rsi+9A8h]
0x140004cc1  jg      loc_140005292
0x140004cc7  test    edx, edx
0x140004cc9  jz      loc_140005292
0x140004ccf  mov     rax, [rbp+250h+var_2B8]
0x140004cd3  cmp     byte ptr [rax+2], 0
0x140004cd7  jnz     short loc_140004CE1
0x140004cd9  mov     r12d, ebx
0x140004cdc  jmp     loc_140005C63
0x140004ce1  mov     dword ptr [rbp+250h+var_248+8], ebx
0x140004ce4  mov     eax, [r12+28h]
0x140004ce9  mov     [rbp+250h+var_2C0], eax
0x140004cec  test    eax, eax
0x140004cee  jnz     short loc_140004D3A
0x140004cf0  lea     ecx, [rax+4]
0x140004cf3  call    cs:__imp_WdLogSingleEntry0
0x140004cfa  nop     dword ptr [rax+rax+00h]
0x140004cff  mov     esi, 0BA6h
0x140004d04  mov     cs:WdLogGlobalForLineNumber, esi
0x140004d0a  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140004d11  nop     dword ptr [rax+rax+00h]
0x140004d16  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140004d1d  mov     [rax+18h], rcx
0x140004d21  mov     ecx, cs:dword_14003E570
0x140004d27  mov     [rax+20h], rcx
0x140004d2b  mov     [rax+28h], rdi
0x140004d2f  mov     cs:WdLogGlobalForLineNumber, esi
0x140004d35  jmp     loc_140005987
0x140004d3a  xor     edx, edx; Val
0x140004d3c  lea     rcx, [rbp+250h+var_190]; void *
0x140004d43  lea     r8d, [rdx+40h]; Size
0x140004d47  call    memset
0x140004d4c  mov     rax, [rsp+350h+psoDest]
0x140004d51  xorps   xmm0, xmm0
0x140004d54  movdqa  xmmword ptr [rbp+250h+var_150], xmm0
0x140004d5c  test    rax, rax
0x140004d5f  jnz     loc_140004EFF
0x140004d65  mov     r8d, [r13+24h]; int
0x140004d69  lea     rcx, [rbp+250h+var_190]
0x140004d70  mov     edx, [r13+20h]; int
0x140004d74  mov     r9, r15; struct tagRECT *
0x140004d77  mov     byte ptr [rsp+350h+prclSrc], bl; unsigned __int8
0x140004d7b  mov     [rsp+350h+prclDest], rcx; struct CDDBITMAP_GDIDESC *
0x140004d80  lea     rcx, [rsi+1580h]; this
0x140004d87  call    ?GetGdiSurface@CStagingPool@@QEAAJHHPEBUtagRECT@@PEAUCDDBITMAP_GDIDESC@@E@Z; CStagingPool::GetGdiSurface(int,int,tagRECT const *,CDDBITMAP_GDIDESC *,uchar)
0x140004d8c  test    eax, eax
0x140004d8e  js      loc_140004EE7
0x140004d94  mov     rcx, [rbp+250h+var_190]
0x140004d9b  lea     rax, [rsi+1580h]
0x140004da2  mov     [rbp+250h+var_150], rax
0x140004da9  mov     rax, [rcx+10h]
0x140004dad  mov     [rbp+250h+var_150+8], rax
0x140004db4  mov     qword ptr [rcx+10h], 0
0x140004dbc  mov     eax, [r15+4]
0x140004dc0  mov     r10, [rbp+250h+var_190]
0x140004dc7  add     eax, ebx
0x140004dc9  movsxd  rcx, eax
0x140004dcc  movsxd  rax, dword ptr [r10+40h]
0x140004dd0  imul    rcx, rax
0x140004dd4  mov     eax, 80000000h
0x140004dd9  add     rax, rcx
0x140004ddc  mov     ecx, 0FFFFFFFFh
0x140004de1  cmp     rax, rcx
0x140004de4  jbe     short loc_140004DEF
0x140004de6  mov     [rsp+350h+var_2F0], ebx
0x140004dea  jmp     loc_14000525F
0x140004def  mov     rax, [rbp+250h+pxlo]
0x140004df3  xor     r9d, r9d
0x140004df6  mov     [rsp+350h+var_300], 0CCCCh
0x140004dfe  xor     r8d, r8d
0x140004e01  mov     [rsp+350h+var_308], 0
0x140004e0a  mov     rdx, r13
0x140004e0d  mov     [rsp+350h+var_310], 0
0x140004e16  mov     rcx, r10
0x140004e19  mov     [rsp+350h+var_318], 0
0x140004e22  mov     [rsp+350h+pBlendObj], r15
  ... truncated ...
```
