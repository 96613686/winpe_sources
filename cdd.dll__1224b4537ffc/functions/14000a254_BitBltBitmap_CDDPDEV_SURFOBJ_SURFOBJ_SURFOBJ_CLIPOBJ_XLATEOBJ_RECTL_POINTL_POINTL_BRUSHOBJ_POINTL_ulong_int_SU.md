# BitBltBitmap(CDDPDEV *,_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))

- ea: `0x14000a254`
- end: `0x14000be2b`
- name: `?BitBltBitmap@@YAHPEAUCDDPDEV@@PEAU_SURFOBJ@@11PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@5PEAU_BRUSHOBJ@@5KP6AH1112345565K@Z@Z`
- size: `7127`
- prototype: `__int64 __fastcall(unsigned int (**)(void), struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, ROP4 rop4, int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000919c`

## callees

- `0x140002470`
- `0x140004600`
- `0x14000a254`
- `0x14000be40`
- `0x14000bf90`
- `0x14000c0b0`
- `0x14000c33c`
- `0x14000c730`
- `0x14000c810`
- `0x14000c890`
- `0x14000cb44`
- `0x14000cec4`
- `0x14000ef80`
- `0x1400160c8`
- `0x140018f44`
- `0x14001f778`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000b2cb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b5b3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b2cb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b5b3`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000a9b9`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000aa14`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000ac31`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000ae9b`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000b41b`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000a9b9`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000aa14`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000ac31`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000ae9b`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000b41b`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000b040`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000b28d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000b040`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14000b28d`
- `ntoskrnl!DbgPrint` at `0x14000bd85`
- `ntoskrnl!DbgPrint` at `0x14000bd85`
- `ntoskrnl!KdDebuggerEnabled` at `0x14000bd73`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000b309`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000b9a1`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000baa3`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000bbe3`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000bd1e`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000bdac`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000b309`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000b9a1`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000baa3`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000bbe3`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000bd1e`
- `watchdog!WdLogNewEntry5_WdError` at `0x14000bdac`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000b7db`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000b82a`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000b7db`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14000b82a`
- `watchdog!WdLogSingleEntry0` at `0x14000a606`
- `watchdog!WdLogSingleEntry0` at `0x14000ab5e`
- `watchdog!WdLogSingleEntry0` at `0x14000acfb`
- `watchdog!WdLogSingleEntry0` at `0x14000afee`
- `watchdog!WdLogSingleEntry0` at `0x14000b2f2`
- `watchdog!WdLogSingleEntry0` at `0x14000b469`
- `watchdog!WdLogSingleEntry0` at `0x14000b7c5`
- `watchdog!WdLogSingleEntry0` at `0x14000b814`
- `watchdog!WdLogSingleEntry0` at `0x14000b98a`
- `watchdog!WdLogSingleEntry0` at `0x14000ba8c`
- `watchdog!WdLogSingleEntry0` at `0x14000bac6`
- `watchdog!WdLogSingleEntry0` at `0x14000bbcc`
- `watchdog!WdLogSingleEntry0` at `0x14000bd07`
- `watchdog!WdLogSingleEntry0` at `0x14000bd96`
- `watchdog!WdLogSingleEntry0` at `0x14000a606`
- `watchdog!WdLogSingleEntry0` at `0x14000ab5e`
- `watchdog!WdLogSingleEntry0` at `0x14000acfb`
- `watchdog!WdLogSingleEntry0` at `0x14000afee`
- `watchdog!WdLogSingleEntry0` at `0x14000b2f2`
- `watchdog!WdLogSingleEntry0` at `0x14000b469`
- `watchdog!WdLogSingleEntry0` at `0x14000b7c5`
- `watchdog!WdLogSingleEntry0` at `0x14000b814`
- `watchdog!WdLogSingleEntry0` at `0x14000b98a`
- `watchdog!WdLogSingleEntry0` at `0x14000ba8c`
- `watchdog!WdLogSingleEntry0` at `0x14000bac6`
- `watchdog!WdLogSingleEntry0` at `0x14000bbcc`
- `watchdog!WdLogSingleEntry0` at `0x14000bd07`
- `watchdog!WdLogSingleEntry0` at `0x14000bd96`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000a61d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000ab75`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000ad12`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000b005`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000b480`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000badd`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000a61d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000ab75`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000ad12`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000b005`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000b480`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000badd`
- `WIN32K!EngBitBlt` at `0x14000a906`
- `WIN32K!EngBitBlt` at `0x14000a803`
- `WIN32K!EngBitBlt` at `0x14000a906`
- `WIN32K!EngBitBlt` at `0x14000b6c7`
- `WIN32K!EngBitBlt` at `0x14000b7a9`
- `WIN32K!W32GetSessionState` at `0x14000b21a`
- `WIN32K!W32GetSessionState` at `0x14000bb61`
- `WIN32K!W32GetSessionState` at `0x14000bca1`
- `WIN32K!W32GetSessionState` at `0x14000b21a`
- `WIN32K!W32GetSessionState` at `0x14000bb61`
- `WIN32K!W32GetSessionState` at `0x14000bca1`

## string_xrefs

- `0x14000bd7e`: `Ivalid pco in GDIBITMAPACCESS2::StartAccessDst`

## pseudocode

```c
__int64 __fastcall BitBltBitmap(
        unsigned int (**a1)(void),
        struct _SURFOBJ *a2,
        struct _SURFOBJ *a3,
        struct _SURFOBJ *a4,
        struct _CLIPOBJ *a5,
        struct _XLATEOBJ *a6,
        RECTL *a7,
        struct _POINTL *a8,
        struct _POINTL *a9,
        struct _BRUSHOBJ *a10,
        struct _POINTL *a11,
        ROP4 rop4,
        int (*a13)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))
{
  SURFOBJ *v13; // r13
  unsigned __int64 *v14; // r15
  struct tagRECT *prclTrg; // rdi
  unsigned int v17; // ebx
  LONG x; // esi
  unsigned int v19; // edx
  DHSURF v20; // r12
  int v21; // r15d
  int v22; // r15d
  unsigned int (*v23)(void); // rax
  struct CddBitmap *dhsurf; // rcx
  struct CDDPDEV *v25; // rax
  LONG left; // edx
  LONG v27; // r10d
  LONG right; // ecx
  LONG v29; // eax
  LONG top; // r8d
  LONG v31; // r9d
  LONG bottom; // ecx
  LONG v33; // eax
  int v34; // edx
  int v35; // r8d
  int v36; // ecx
  int v37; // r14d
  ROP4 v38; // r8d
  int y; // r15d
  LONG v40; // edx
  unsigned int v41; // eax
  LONG v42; // ecx
  _QWORD *v43; // rax
  __int64 v44; // rdx
  bool v45; // zf
  __int64 v47; // r15
  unsigned int v48; // r14d
  struct CddBitmap *v49; // r15
  LONG v50; // edx
  LONG v51; // r8d
  struct CDDPDEV *v52; // r14
  int v53; // ecx
  SURFOBJ *v54; // r15
  struct CddBitmap **v55; // r13
  CLIPOBJ *v56; // rsi
  SURFOBJ *v57; // r13
  __int64 v58; // rcx
  struct _KTHREAD *v59; // rdx
  int v60; // r8d
  BOOL v61; // eax
  int v62; // ecx
  DHSURF v63; // rdi
  __int64 v64; // rcx
  struct _KTHREAD *v65; // rdx
  __int64 v66; // rdx
  char v67; // cl
  CLIPOBJ *v68; // r14
  _QWORD *v69; // rax
  DHSURF v70; // rdi
  __int64 v71; // rcx
  struct _KTHREAD *v72; // rdx
  unsigned __int8 v73; // r8
  char v74; // cl
  unsigned __int8 v75; // dl
  _QWORD *v76; // rax
  DHSURF v77; // rdi
  __int64 v78; // rcx
  struct _KTHREAD *v79; // rdx
  ULONG iBitmapFormat; // eax
  tagRECT *v81; // r13
  LONG v82; // r8d
  LONG v83; // r9d
  LONG v84; // r11d
  LONG v85; // r10d
  LONG v86; // edx
  LONG v87; // ecx
  struct CddBitmap **v88; // rax
  _QWORD *v89; // rax
  bool v90; // zf
  _QWORD *v91; // r14
  NTSTATUS v92; // eax
  _QWORD *v93; // rax
  DHSURF v94; // rdi
  __int64 v95; // rcx
  struct _KTHREAD *v96; // rdx
  _QWORD *v97; // rax
  DHSURF v98; // rdi
  struct _KTHREAD *v99; // rdx
  _QWORD *v100; // r14
  NTSTATUS v101; // eax
  int v102; // edx
  int v103; // ecx
  _QWORD *v104; // rax
  _QWORD *v105; // rax
  int v106; // ebx
  _QWORD *v107; // rax
  _QWORD *v108; // rax
  int v109; // eax
  __int64 v110; // rcx
  _QWORD *v111; // rax
  int v112; // eax
  _QWORD *v113; // rax
  _QWORD *v114; // rax
  unsigned int pxlo; // [rsp+20h] [rbp-E0h]
  int pbo; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v117; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v118; // [rsp+61h] [rbp-9Fh]
  unsigned int v119; // [rsp+68h] [rbp-98h]
  LONG v120; // [rsp+68h] [rbp-98h]
  signed int v121; // [rsp+68h] [rbp-98h]
  unsigned int StagingVidMemAllocation; // [rsp+68h] [rbp-98h]
  unsigned int v123; // [rsp+6Ch] [rbp-94h]
  struct CDDPDEV *v124; // [rsp+70h] [rbp-90h]
  BOOL v125; // [rsp+78h] [rbp-88h]
  unsigned int v126; // [rsp+78h] [rbp-88h]
  struct CddBitmap *v127; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v128; // [rsp+88h] [rbp-78h]
  struct tagRECT *v129; // [rsp+90h] [rbp-70h] BYREF
  CLIPOBJ *pco; // [rsp+98h] [rbp-68h]
  struct CddBitmap *v131; // [rsp+A0h] [rbp-60h]
  POINTL *pptlSrc; // [rsp+A8h] [rbp-58h]
  unsigned int v133; // [rsp+B0h] [rbp-50h]
  int v134; // [rsp+B4h] [rbp-4Ch]
  int v135; // [rsp+B8h] [rbp-48h]
  BOOL (__stdcall *v136)(SURFOBJ *, SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *, POINTL *, BRUSHOBJ *, POINTL *, ROP4); // [rsp+C0h] [rbp-40h]
  XLATEOBJ *v137; // [rsp+C8h] [rbp-38h]
  _QWORD v138[16]; // [rsp+D0h] [rbp-30h] BYREF
  SURFOBJ *psoSrc; // [rsp+150h] [rbp+50h]
  unsigned __int64 v140; // [rsp+158h] [rbp+58h] BYREF
  LONG v141; // [rsp+160h] [rbp+60h]
  SURFOBJ *psoTrg; // [rsp+168h] [rbp+68h]
  __int64 v143; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v144; // [rsp+178h] [rbp+78h]
  __int64 v145; // [rsp+180h] [rbp+80h]
  int v146; // [rsp+188h] [rbp+88h]
  __int64 v147; // [rsp+190h] [rbp+90h] BYREF
  POINTL *pptlMask; // [rsp+198h] [rbp+98h]
  __int128 v149; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v150; // [rsp+1B0h] [rbp+B0h]
  __int128 v151; // [rsp+1C0h] [rbp+C0h]
  BRUSHOBJ *v152; // [rsp+1D0h] [rbp+D0h]
  SURFOBJ *psoMask; // [rsp+1D8h] [rbp+D8h]
  POINTL *pptlBrush; // [rsp+1E0h] [rbp+E0h]
  _BYTE v155[24]; // [rsp+1E8h] [rbp+E8h] BYREF
  tagRECT v156; // [rsp+200h] [rbp+100h] BYREF
  unsigned int v157[16]; // [rsp+210h] [rbp+110h] BYREF
  CStagingPool *v158[2]; // [rsp+250h] [rbp+150h]
  _QWORD v159[8]; // [rsp+260h] [rbp+160h] BYREF
  CStagingPool *v160[2]; // [rsp+2A0h] [rbp+1A0h]
  struct tagRECT v161; // [rsp+2B0h] [rbp+1B0h] BYREF
  _QWORD v162[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _QWORD v163[8]; // [rsp+300h] [rbp+200h] BYREF
  struct CDDPDEV *v164; // [rsp+340h] [rbp+240h]
  CLIPOBJ *v165; // [rsp+348h] [rbp+248h]
  struct CddBitmap *v166; // [rsp+350h] [rbp+250h]
  DHSURF v167; // [rsp+358h] [rbp+258h]
  struct tagRECT *v168; // [rsp+360h] [rbp+260h]
  __int64 v169; // [rsp+368h] [rbp+268h] BYREF
  int v170; // [rsp+370h] [rbp+270h]
  struct CddBitmap **v171; // [rsp+378h] [rbp+278h]
  char v172; // [rsp+380h] [rbp+280h]
  __int128 v173; // [rsp+390h] [rbp+290h] BYREF
  __int64 v174; // [rsp+3A0h] [rbp+2A0h] BYREF
  int v175; // [rsp+3A8h] [rbp+2A8h]
  int v176; // [rsp+3ACh] [rbp+2ACh]

  v13 = a3;
  v14 = (unsigned __int64 *)a8;
  prclTrg = (struct tagRECT *)a7;
  v137 = a6;
  v152 = a10;
  pptlBrush = a11;
  psoSrc = a3;
  v136 = a13;
  psoMask = a4;
  v17 = 1;
  psoTrg = a2;
  v124 = (struct CDDPDEV *)a1;
  pptlSrc = a8;
  pptlMask = a9;
  pco = a5;
  v140 = 0;
  v147 = 0;
  v173 = 0;
  if ( a5 && a5->iDComplexity )
  {
    left = a5->rclBounds.left;
    v27 = a7->left;
    right = a5->rclBounds.right;
    v29 = a7->right;
    if ( a7->left > left )
      left = a7->left;
    LODWORD(v173) = left;
    if ( v29 < right )
      right = v29;
    DWORD2(v173) = right;
    if ( left >= right )
      return v17;
    top = a5->rclBounds.top;
    v31 = a7->top;
    bottom = a5->rclBounds.bottom;
    v33 = a7->bottom;
    if ( v31 > top )
      top = a7->top;
    DWORD1(v173) = top;
    if ( v33 < bottom )
      bottom = v33;
    HIDWORD(v173) = bottom;
    if ( top >= bottom )
      return v17;
    v34 = left - v27;
    v35 = top - v31;
    x = v34 + a8->x;
    v140 = __PAIR64__(v35 + a8->y, x);
    if ( a9 )
    {
      v36 = v34 + a9->x;
      pptlMask = (POINTL *)&v147;
      LODWORD(v147) = v36;
      HIDWORD(v147) = v35 + a9->y;
    }
    v14 = &v140;
    pptlSrc = (POINTL *)&v140;
    prclTrg = (struct tagRECT *)&v173;
  }
  else
  {
    x = a8->x;
  }
  v19 = *((_DWORD *)v14 + 1);
  v20 = 0;
  v21 = prclTrg->right - prclTrg->left;
  v128 = v19 + prclTrg->bottom - prclTrg->top;
  v22 = x + v21;
  v23 = a1[10];
  v119 = v19;
  v131 = 0;
  v149 = 0;
  v146 = 1;
  v150 = 0;
  v145 = 0;
  v151 = 0;
  if ( v23() )
  {
    v102 = prclTrg->right - prclTrg->left;
    v103 = prclTrg->bottom - prclTrg->top;
    LODWORD(v149) = v13->iType;
    *(_QWORD *)((char *)&v151 + 4) = 0;
    HIDWORD(v151) = 0;
    DWORD1(v149) = psoTrg->iType;
    *((_QWORD *)&v149 + 1) = __PAIR64__(v103, v102);
    v150 = __PAIR64__(v103, v102);
    *(_QWORD *)&v151 = (unsigned __int16)rop4;
    CDDETWPROFILER::Init((CDDETWPROFILER *)&v143, (struct CDDPDEV *)a1, 0xBCDu, (struct _DXGKETW_PARAMS *)&v149, 0);
  }
  if ( v13->iType && v136 == EngBitBlt )
  {
    dhsurf = (struct CddBitmap *)v13->dhsurf;
    v131 = (struct CddBitmap *)v13->dhsurf;
  }
  else
  {
    dhsurf = 0;
  }
  if ( psoTrg->iType )
  {
    v20 = psoTrg->dhsurf;
    if ( psoTrg->dhsurf )
    {
      v25 = (struct CDDPDEV *)*((_QWORD *)v20 + 1);
      goto LABEL_26;
    }
  }
  if ( dhsurf )
  {
    v25 = (struct CDDPDEV *)*((_QWORD *)dhsurf + 1);
LABEL_26:
    v124 = v25;
  }
  CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v155, (struct CddBitmap *)v20, dhsurf);
  v123 = 0;
  v125 = v13->iBitmapFormat - 7 <= 1;
  if ( !v20 || (v37 = 1, ((_DWORD)v20[32] & 1) == 0) )
    v37 = 0;
  if ( (signed int)(v128 - v119) > *((_DWORD *)v124 + 619) || v22 - x > *((_DWORD *)v124 + 618) )
  {
    v37 = 0;
  }
  else if ( v37 )
  {
    v38 = rop4;
    switch ( rop4 )
    {
      case 0x6666u:
        v123 = 2;
        goto LABEL_33;
      case 0x8888u:
        v123 = 3;
        goto LABEL_33;
      case 0xCCCCu:
        v123 = 1;
        goto LABEL_33;
      case 0xEEEEu:
        v123 = 4;
        goto LABEL_33;
    }
    if ( (*((_DWORD *)v124 + 475) & 0x100000) == 0
      || (unsigned __int8)rop4 != BYTE1(rop4)
      || ((*((_BYTE *)qword_140039D10 + (unsigned __int8)rop4) | *((_BYTE *)qword_140039D10 + BYTE1(rop4))) & 0xE8) != 0 )
    {
      v37 = 0;
      goto LABEL_33;
    }
    v123 = (rop4 << 16) | 5;
  }
  v38 = rop4;
LABEL_33:
  if ( v13->iBitmapFormat - 7 <= 1 && v38 != 52428 )
    v37 = 0;
  if ( v137 && (v137->flXlate & 1) == 0 || (v135 = 1, v136 != EngBitBlt) )
    v135 = 0;
  v134 = 0;
  y = pptlSrc->y;
  if ( y < 0 || pptlSrc->x < 0 )
    v37 = 0;
  DWORD2(v150) = v37;
  if ( !v37 )
    goto LABEL_61;
  v40 = pptlSrc->x;
  v41 = *((_DWORD *)v20 + 10);
  LODWORD(v129) = pptlSrc->x + prclTrg->right - prclTrg->left;
  v156.right = (int)v129;
  v42 = y + prclTrg->bottom - prclTrg->top;
  v120 = v40;
  v156.left = v40;
  v141 = v42;
  v156.bottom = v42;
  v128 = v41;
  v156.top = y;
  memset(v157, 0, sizeof(v157));
  *(_OWORD *)v158 = 0;
  if ( !v131 )
  {
    if ( (int)CStagingPool::GetGdiSurface(
                (struct CDDPDEV *)((char *)v124 + 5504),
                v13->sizlBitmap.cx,
                v13->sizlBitmap.cy,
                &v156,
                (struct CDDBITMAP_GDIDESC *)v157,
                1u) < 0 )
    {
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 4451;
      v43 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v43[3] = gCddImageInfo;
      v43[4] = (unsigned int)dword_14003E570;
      v43[5] = 215857758;
      WdLogGlobalForLineNumber = 4451;
      if ( v158[0] )
      {
        *(CStagingPool **)(*(_QWORD *)v157 + 16LL) = v158[1];
        CStagingPool::ReleaseGdiSurface(v158[0], (struct CDDBITMAP_GDIDESC *)v157);
      }
      CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v155);
      v45 = v146 == 0;
LABEL_45:
      if ( v45 )
      {
        LOBYTE(v44) = 2;
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(v143 + 264))(v144, v44, v145);
      }
      return v17;
    }
    v158[0] = (struct CDDPDEV *)((char *)v124 + 5504);
    v158[1] = *(CStagingPool **)(*(_QWORD *)v157 + 16LL);
    *(_QWORD *)(*(_QWORD *)v157 + 16LL) = 0;
    v47 = *(_QWORD *)v157;
    if ( !*(_QWORD *)(*(_QWORD *)v157 + 56LL) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4457;
      v104 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v104[3] = gCddImageInfo;
      v104[4] = (unsigned int)dword_14003E570;
      v104[5] = 215857758;
      WdLogGlobalForLineNumber = 4457;
    }
    if ( *(_DWORD *)(v47 + 72) != 6 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4458;
      v105 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v105[3] = gCddImageInfo;
      v105[4] = (unsigned int)dword_14003E570;
      v105[5] = 215857758;
      WdLogGlobalForLineNumber = 4458;
    }
    v121 = *(_DWORD *)(v47 + 64);
    if ( (unsigned __int64)(v121 * (__int64)(v156.top + 1) + 0x80000000LL) > 0xFFFFFFFF )
    {
      v134 = 1;
      goto LABEL_54;
    }
    if ( v135 )
    {
      iBitmapFormat = v13->iBitmapFormat;
      if ( iBitmapFormat == 6 )
      {
        CopySurfBits(*(char **)(v47 + 56), v121, (char *)v13->pvScan0, v13->lDelta, pxlo, &v156);
LABEL_130:
        v81 = (tagRECT *)&v157[9];
        v82 = v156.bottom;
        v83 = v156.right;
        y = v156.top;
        v133 = v157[4];
        v127 = *(struct CddBitmap **)&v157[6];
        v126 = *(_DWORD *)(*(_QWORD *)v157 + 64LL);
        v120 = v156.left;
        goto LABEL_131;
      }
      if ( iBitmapFormat == 5 )
      {
        CopyBitsNonTemporal24_32(
          (unsigned int *)(*(_QWORD *)(v47 + 56) + (unsigned int)(4 * v156.left) + (__int64)(v156.top * v121)),
          v121,
          (const unsigned int *)((char *)v13->pvScan0 + 3 * v156.left + (__int64)(v156.top * v13->lDelta)),
          v13->lDelta,
          v156.bottom - v156.top,
          v156.right - v156.left);
        goto LABEL_130;
      }
    }
    if ( v125 )
    {
      memset(&v138[4], 0, 0x58u);
      v138[3] = &v156;
      v138[0] = pco;
      v138[1] = prclTrg;
      v138[2] = prclTrg;
      v138[10] = *(_QWORD *)(v47 + 56);
      LODWORD(v138[11]) = *(_DWORD *)(v47 + 64);
      HIDWORD(v138[11]) = -251592189;
      v138[5] = 0;
      ClipDstRects(
        (struct CLIP_RECTS_DATA *)v138,
        (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))FillColorKeyCallback);
      if ( ((unsigned int (__fastcall *)(__int64, SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, tagRECT *, POINTL *, _QWORD, _QWORD, _QWORD, int))v136)(
             v47,
             v13,
             0,
             0,
             v137,
             &v156,
             pptlSrc,
             0,
             0,
             0,
             52428) )
      {
        memset(v138, 0, 0x78u);
        v138[0] = pco;
        v138[1] = &v157[9];
        v138[10] = *(_QWORD *)&v157[6];
        LODWORD(v138[12]) = v157[4];
        v138[2] = prclTrg;
        v138[3] = prclTrg;
        v138[13] = 0x1F1010203LL;
        v138[11] = v20;
        HIDWORD(v138[12]) = v20[10];
        LODWORD(v138[14]) = *(_DWORD *)(*(_QWORD *)v157 + 64LL);
        v138[5] = 0;
        ClipDstRects(
          (struct CLIP_RECTS_DATA *)v138,
          (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::TransparentBltCallback);
        CddBitmap::VidMemDirtyUpdate((CddBitmap *)v20);
        v90 = v158[0] == 0;
        goto LABEL_138;
      }
      WdLogSingleEntry0(2);
      v106 = 4507;
      WdLogGlobalForLineNumber = 4507;
      v107 = (_QWORD *)WdLogNewEntry5_WdError();
    }
    else
    {
      if ( ((unsigned int (__fastcall *)(__int64, SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, tagRECT *, POINTL *, _QWORD, _QWORD, _QWORD, int))v136)(
             v47,
             v13,
             0,
             0,
             v137,
             &v156,
             pptlSrc,
             0,
             0,
             0,
             52428) )
      {
        goto LABEL_130;
      }
      WdLogSingleEntry0(2);
      v106 = 4536;
      WdLogGlobalForLineNumber = 4536;
      v107 = (_QWORD *)WdLogNewEntry5_WdError();
    }
    v107[3] = gCddImageInfo;
    v107[4] = (unsigned int)dword_14003E570;
    v107[5] = 215857758;
    WdLogGlobalForLineNumber = v106;
    if ( v158[0] )
    {
      *(CStagingPool **)(*(_QWORD *)v157 + 16LL) = v158[1];
      CStagingPool::ReleaseGdiSurface(v158[0], (struct CDDBITMAP_GDIDESC *)v157);
    }
    goto LABEL_119;
  }
  v133 = *((_DWORD *)v131 + 10);
  if ( !v133 )
  {
    WdLogSingleEntry0(4);
    WdLogGlobalForLineNumber = 4553;
    v108 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v108[3] = gCddImageInfo;
    v108[4] = (unsigned int)dword_14003E570;
    v108[5] = 215857758;
    v90 = v158[0] == 0;
    WdLogGlobalForLineNumber = 4553;
    goto LABEL_138;
  }
  v82 = v141;
  v81 = &v156;
  v83 = (int)v129;
  v126 = 0;
  v127 = v131;
LABEL_131:
  v84 = prclTrg->right;
  v85 = prclTrg->left;
  v86 = prclTrg->bottom;
  v87 = prclTrg->top;
  v175 = v84 - prclTrg->left;
  v174 = 0;
  v176 = v86 - v87;
  if ( v131 == (struct CddBitmap *)v20 )
  {
    v109 = *((_DWORD *)v124 + 475);
    if ( (v109 & 0x1000000) != 0 )
      goto LABEL_152;
    if ( (v109 & 0x2000000) != 0 )
    {
      if ( v120 > v85 )
        v85 = v120;
      if ( v83 < v84 )
        v84 = v83;
      if ( v85 < v84 )
      {
        if ( y > v87 )
          v87 = y;
        if ( v82 < v86 )
          v86 = v82;
        if ( v87 < v86 )
        {
LABEL_152:
          CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v161, *((struct CDDMUTEX **)v124 + 364), v82);
          StagingVidMemAllocation = CddBitmapStagingVidMem::GetStagingVidMemAllocation(
                                      *((CddBitmapStagingVidMem **)v124 + 687),
                                      prclTrg);
          if ( StagingVidMemAllocation )
          {
            memset(v138, 0, 0x78u);
            v138[0] = pco;
            v138[3] = &v174;
            v138[10] = v127;
            v138[9] = v124;
            v138[1] = v81;
            v138[2] = prclTrg;
            v138[11] = *((_QWORD *)v124 + 687);
            *(_QWORD *)((char *)&v138[13] + 4) = v126;
            v138[12] = __PAIR64__(StagingVidMemAllocation, v133);
            v138[5] = 0;
            LODWORD(v138[13]) = 1;
            ClipDstRects(
              (struct CLIP_RECTS_DATA *)v138,
              (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::BitBltCallback);
            memset(v138, 0, 0x78u);
            v138[0] = pco;
            v138[1] = &v174;
            v138[2] = prclTrg;
            v138[3] = prclTrg;
            v138[9] = v124;
            v138[10] = *((_QWORD *)v124 + 687);
            v138[12] = __PAIR64__(v128, StagingVidMemAllocation);
            LODWORD(v138[13]) = v123;
            *(_QWORD *)((char *)&v138[13] + 4) = 0;
            v129 = 0;
            v138[11] = v20;
            if ( *(_DWORD *)(*(_QWORD *)(W32GetSessionState() + 72) + 3412LL)
              && (*((unsigned int (**)(void))v124 + 80))() )
            {
              LODWORD(v129) = v81->left - prclTrg->left;
              HIDWORD(v129) = v81->top - prclTrg->top;
              v138[5] = &v129;
            }
            else
            {
              v138[5] = 0;
            }
            ClipDstRects(
              (struct CLIP_RECTS_DATA *)v138,
              (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::BitBltCallback);
            if ( v161.right )
              ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*(_QWORD *)&v161.left);
            goto LABEL_134;
          }
          WdLogSingleEntry0(4);
          WdLogGlobalForLineNumber = 4692;
          v89 = (_QWORD *)WdLogNewEntry5_WdEvent();
          v89[3] = gCddImageInfo;
          v89[4] = (unsigned int)dword_14003E570;
          v89[5] = 215857758;
          WdLogGlobalForLineNumber = 4692;
          if ( v161.right )
            ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*(_QWORD *)&v161.left);
          v90 = v158[0] == 0;
LABEL_138:
          if ( !v90 )
          {
            *(CStagingPool **)(*(_QWORD *)v157 + 16LL) = v158[1];
            CStagingPool::ReleaseGdiSurface(v158[0], (struct CDDBITMAP_GDIDESC *)v157);
          }
          goto LABEL_120;
        }
      }
    }
  }
  memset(v138, 0, 0x78u);
  v138[0] = pco;
  v138[10] = v127;
  LODWORD(v138[13]) = v123;
  *(_QWORD *)((char *)&v138[13] + 4) = v126;
  v88 = 0;
  v138[1] = v81;
  v138[2] = prclTrg;
  v138[3] = prclTrg;
  v138[9] = v124;
  v138[11] = v20;
  v138[12] = __PAIR64__(v128, v133);
  v127 = 0;
  if ( v133 == v128 )
  {
    v110 = *(_QWORD *)(W32GetSessionState() + 72);
    v88 = 0;
    if ( *(_DWORD *)(v110 + 3412) )
    {
      if ( (*((unsigned int (**)(void))v124 + 80))() )
      {
        v88 = &v127;
        LODWORD(v127) = v81->left - prclTrg->left;
        HIDWORD(v127) = v81->top - prclTrg->top;
      }
      else
      {
        v88 = 0;
      }
    }
  }
  v138[5] = v88;
  ClipDstRects(
    (struct CLIP_RECTS_DATA *)v138,
    (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::BitBltCallback);
LABEL_134:
  CddBitmap::VidMemDirtyUpdate((CddBitmap *)v20);
  v13 = psoSrc;
LABEL_54:
  if ( v158[0] )
  {
    *(CStagingPool **)(*(_QWORD *)v157 + 16LL) = v158[1];
    CStagingPool::ReleaseGdiSurface(v158[0], (struct CDDBITMAP_GDIDESC *)v157);
  }
  v48 = 1;
  if ( !v134 )
    goto LABEL_82;
LABEL_61:
  v49 = v131;
  v50 = pptlSrc->x;
  v51 = pptlSrc->y;
  v52 = v124;
  v161.right = pptlSrc->x + prclTrg->right - prclTrg->left;
  v53 = prclTrg->bottom - prclTrg->top;
  v161.left = v50;
  v161.bottom = v51 + v53;
  v161.top = v51;
  GDIBITMAPACCESS2::GDIBITMAPACCESS2((GDIBITMAPACCESS2 *)v162, v124, v131, (struct CddBitmap *)v20);
  v129 = &v161;
  memset(v159, 0, sizeof(v159));
  *(_OWORD *)v160 = 0;
  if ( v49 )
  {
    v67 = v172;
    v55 = 0;
    if ( v172 )
    {
      v91 = (_QWORD *)*((_QWORD *)v164 + 895);
      if ( (struct _KTHREAD *)v91[4] != KeGetCurrentThread() )
      {
        v92 = KeWaitForSingleObject(v91, Executive, 0, 0, 0);
        if ( v92 != 258 )
        {
          v91[4] = KeGetCurrentThread();
          if ( v92 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 618;
            v111 = (_QWORD *)WdLogNewEntry5_WdError();
            v111[3] = gCddImageInfo;
            v111[4] = (unsigned int)dword_14003E570;
            v111[5] = 215857758;
            WdLogGlobalForLineNumber = 618;
            goto LABEL_96;
          }
        }
      }
      v67 = v172;
    }
    v68 = pco;
    LOBYTE(pbo) = v67 == 0;
    if ( (*(int (__fastcall **)(struct CddBitmap *, struct tagRECT *, struct tagRECT *, CLIPOBJ *, _DWORD, int, __int64 *, _QWORD *, int))(*(_QWORD *)v49 + 56LL))(
           v49,
           prclTrg,
           &v161,
           pco,
           0,
           1,
           &v169,
           v162,
           pbo) >= 0 )
    {
      v45 = *((_DWORD *)v49 + 8) == 2;
      v166 = v49;
      v165 = v68;
      if ( v45 )
      {
        pptlSrc = (POINTL *)prclTrg;
        v129 = prclTrg;
      }
      v54 = (SURFOBJ *)v162[0];
      goto LABEL_189;
    }
LABEL_96:
    WdLogSingleEntry0(4);
    WdLogGlobalForLineNumber = 4797;
    v69 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v69[3] = gCddImageInfo;
    v69[4] = (unsigned int)dword_14003E570;
    v69[5] = 215857758;
    WdLogGlobalForLineNumber = 4797;
    if ( v160[0] )
    {
      *(CStagingPool **)(v159[0] + 16LL) = v160[1];
      CStagingPool::ReleaseGdiSurface(v160[0], (struct CDDBITMAP_GDIDESC *)v159);
    }
    if ( v166 )
      (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v166 + 128LL))(v166, v162);
    v70 = v167;
    if ( v167 )
    {
      if ( !v170 )
        (*(void (__fastcall **)(DHSURF, _QWORD *, struct tagRECT *, CLIPOBJ *, struct CddBitmap **))(*(_QWORD *)v167 + 64LL))(
          v167,
          v163,
          v168,
          v165,
          v171);
      (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v70 + 128LL))(v70, v163);
    }
    v71 = *((_QWORD *)v164 + 895);
    v72 = *(struct _KTHREAD **)(v71 + 32);
    if ( v72 == KeGetCurrentThread() && v72 )
    {
      *(_QWORD *)(v71 + 32) = 0;
      KeReleaseSemaphore((PRKSEMAPHORE)v71, 0, 1, 0);
    }
    CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v155);
    v45 = v146 == 0;
    goto LABEL_45;
  }
  if ( v136 == EngBitBlt )
  {
    v54 = psoSrc;
    v55 = 0;
    goto LABEL_64;
  }
  if ( (int)CStagingPool::GetGdiSurface(
              (struct CDDPDEV *)((char *)v124 + 5504),
              v13->sizlBitmap.cx,
              v13->sizlBitmap.cy,
              &v161,
              (struct CDDBITMAP_GDIDESC *)v159,
              1u) < 0 )
  {
    WdLogSingleEntry0(4);
    WdLogGlobalForLineNumber = 4816;
    v97 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v97[3] = gCddImageInfo;
    v97[4] = (unsigned int)dword_14003E570;
    v97[5] = 215857758;
    WdLogGlobalForLineNumber = 4816;
    if ( v160[0] )
    {
      *(CStagingPool **)(v159[0] + 16LL) = v160[1];
      CStagingPool::ReleaseGdiSurface(v160[0], (struct CDDBITMAP_GDIDESC *)v159);
    }
    if ( v166 )
      (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v166 + 128LL))(v166, v162);
    v98 = v167;
    if ( v167 )
    {
      if ( !v170 )
        (*(void (__fastcall **)(DHSURF, _QWORD *, struct tagRECT *, CLIPOBJ *, struct CddBitmap **))(*(_QWORD *)v167 + 64LL))(
          v167,
          v163,
          v168,
          v165,
          v171);
      (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v98 + 128LL))(v98, v163);
    }
    v78 = *((_QWORD *)v164 + 895);
    v99 = *(struct _KTHREAD **)(v78 + 32);
    if ( v99 != KeGetCurrentThread() || !v99 )
      goto LABEL_120;
    *(_QWORD *)(v78 + 32) = 0;
LABEL_126:
    KeReleaseSemaphore((PRKSEMAPHORE)v78, 0, 1, 0);
    goto LABEL_120;
  }
  v160[0] = (struct CDDPDEV *)((char *)v124 + 5504);
  v160[1] = *(CStagingPool **)(v159[0] + 16LL);
  *(_QWORD *)(v159[0] + 16LL) = 0;
  v54 = (SURFOBJ *)v159[0];
  if ( (unsigned __int64)((v161.top + 1) * (__int64)*(int *)(v159[0] + 64LL) + 0x80000000LL) > 0xFFFFFFFF || v134 )
  {
    v54 = psoSrc;
    v55 = 0;
  }
  else
  {
    v112 = ((__int64 (__fastcall *)(_QWORD, SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, struct tagRECT *, POINTL *, _QWORD, _QWORD, _QWORD, int))v136)(
             v159[0],
             v13,
             0,
             0,
             v137,
             &v161,
             pptlSrc,
             0,
             0,
             0,
             52428);
    v55 = 0;
    if ( !v112 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 4834;
      v93 = (_QWORD *)WdLogNewEntry5_WdError();
      v93[3] = gCddImageInfo;
      v93[4] = (unsigned int)dword_14003E570;
      v93[5] = 215857758;
      WdLogGlobalForLineNumber = 4834;
      if ( v160[0] )
      {
        *(CStagingPool **)(v159[0] + 16LL) = v160[1];
        CStagingPool::ReleaseGdiSurface(v160[0], (struct CDDBITMAP_GDIDESC *)v159);
      }
      if ( v166 )
        (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v166 + 128LL))(v166, v162);
      v94 = v167;
      if ( v167 )
      {
        if ( !v170 )
          (*(void (__fastcall **)(DHSURF, _QWORD *, struct tagRECT *, CLIPOBJ *, struct CddBitmap **))(*(_QWORD *)v167 + 64LL))(
            v167,
            v163,
            v168,
            v165,
            v171);
        (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v94 + 128LL))(v94, v163);
      }
      v95 = *((_QWORD *)v164 + 895);
      v96 = *(struct _KTHREAD **)(v95 + 32);
      if ( v96 == KeGetCurrentThread() && v96 )
      {
        *(_QWORD *)(v95 + 32) = 0;
        KeReleaseSemaphore((PRKSEMAPHORE)v95, 0, 1, 0);
      }
LABEL_119:
      v17 = 0;
LABEL_120:
      CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v155);
      CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v143);
      return v17;
    }
  }
LABEL_189:
  v52 = v124;
LABEL_64:
  if ( v20 )
  {
    v127 = 0;
    if ( v20 == (DHSURF)v131
      && *(_DWORD *)(*(_QWORD *)(W32GetSessionState() + 72) + 3412LL)
      && (*((unsigned int (**)(void))v52 + 80))() )
    {
      v55 = &v127;
      LODWORD(v127) = v129->left - prclTrg->left;
      HIDWORD(v127) = v129->top - prclTrg->top;
    }
    v73 = *((_BYTE *)qword_140039D10 + BYTE1(rop4));
    v74 = v172;
    v75 = *((_BYTE *)qword_140039D10 + (unsigned __int8)rop4);
    v117 = v73;
    v118 = v75;
    if ( v172 )
    {
      v100 = (_QWORD *)*((_QWORD *)v164 + 895);
      if ( (struct _KTHREAD *)v100[4] != KeGetCurrentThread() )
      {
        v101 = KeWaitForSingleObject(v100, Executive, 0, 0, 0);
        if ( v101 == 258 )
        {
          v73 = v117;
          v75 = v118;
        }
        else
        {
          v100[4] = KeGetCurrentThread();
          if ( v101 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 659;
            v113 = (_QWORD *)WdLogNewEntry5_WdError();
            v113[3] = gCddImageInfo;
            v113[4] = (unsigned int)dword_14003E570;
            v113[5] = 215857758;
            WdLogGlobalForLineNumber = 659;
LABEL_108:
            WdLogSingleEntry0(4);
            WdLogGlobalForLineNumber = 4864;
            v76 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v76[3] = gCddImageInfo;
            v76[4] = (unsigned int)dword_14003E570;
            v76[5] = 215857758;
            WdLogGlobalForLineNumber = 4864;
            if ( v160[0] )
            {
              *(CStagingPool **)(v159[0] + 16LL) = v160[1];
              CStagingPool::ReleaseGdiSurface(v160[0], (struct CDDBITMAP_GDIDESC *)v159);
            }
            if ( v166 )
              (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v166 + 128LL))(v166, v162);
            v77 = v167;
            if ( v167 )
            {
              if ( !v170 )
                (*(void (__fastcall **)(DHSURF, _QWORD *, struct tagRECT *, CLIPOBJ *, struct CddBitmap **))(*(_QWORD *)v167 + 64LL))(
                  v167,
                  v163,
                  v168,
                  v165,
                  v171);
              (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v77 + 128LL))(v77, v163);
            }
            v78 = *((_QWORD *)v164 + 895);
            v79 = *(struct _KTHREAD **)(v78 + 32);
            if ( v79 != KeGetCurrentThread() || !v79 )
              goto LABEL_120;
            *(_QWORD *)(v78 + 32) = 0;
            goto LABEL_126;
          }
          v73 = v117;
          v75 = v118;
        }
      }
      v74 = v172;
    }
    LOBYTE(pbo) = v74 == 0;
    if ( (*(int (__fastcall **)(DHSURF, struct tagRECT *, struct tagRECT *, CLIPOBJ *, int, int, char *, _QWORD *, int))(*(_QWORD *)v20 + 56LL))(
           v20,
           prclTrg,
           prclTrg,
           pco,
           1,
           (v73 | v75) & 0xB2,
           (char *)&v169 + 4,
           v163,
           pbo) >= 0 )
    {
      v48 = 1;
      if ( v165 && pco != v165 && (_BYTE)KdDebuggerEnabled )
      {
        DbgPrint("Ivalid pco in GDIBITMAPACCESS2::StartAccessDst");
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 670;
        v114 = (_QWORD *)WdLogNewEntry5_WdError();
        v114[3] = gCddImageInfo;
        v114[4] = (unsigned int)dword_14003E570;
        v114[5] = 215857758;
        WdLogGlobalForLineNumber = 670;
        __debugbreak();
      }
      v56 = pco;
      v171 = v55;
      v57 = (SURFOBJ *)v163[0];
      v165 = pco;
      v167 = v20;
      v168 = prclTrg;
      goto LABEL_66;
    }
    goto LABEL_108;
  }
  v56 = pco;
  v48 = 1;
  v57 = psoTrg;
LABEL_66:
  v58 = *((_QWORD *)v164 + 895);
  v59 = *(struct _KTHREAD **)(v58 + 32);
  if ( v59 == KeGetCurrentThread() && v59 )
  {
    *(_QWORD *)(v58 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v58, 0, 1, 0);
  }
  v60 = HIDWORD(v169);
  if ( v169 )
  {
    CDDPDEV::Flush(v164);
    v60 = HIDWORD(v169);
  }
  WaitForStartGdiAccessToFinish(v164, (struct CDDBITMAP_GDIDESC *)v163, v60);
  WaitForStartGdiAccessToFinish(v164, (struct CDDBITMAP_GDIDESC *)v162, v169);
  if ( v54->iBitmapFormat == 6 && v57->iBitmapFormat == 6 && rop4 == 52428 && v135 && v131 != (struct CddBitmap *)v20 )
  {
    memset(&v138[1], 0, 0x70u);
    v138[0] = v56;
    v138[10] = v54->pvScan0;
    v138[11] = v57->pvScan0;
    v138[1] = v129;
    v138[2] = prclTrg;
    v138[3] = prclTrg;
    LODWORD(v138[12]) = v54->lDelta;
    HIDWORD(v138[12]) = v57->lDelta;
    v138[5] = 0;
    ClipDstRects(
      (struct CLIP_RECTS_DATA *)v138,
      (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CopyMemoryCallback);
  }
  else
  {
    v61 = EngBitBlt(v57, v54, psoMask, v56, v137, (RECTL *)prclTrg, pptlSrc, pptlMask, v152, pptlBrush, rop4);
    v62 = v170;
    v48 = v61;
    if ( !v61 )
      v62 = 1;
    v170 = v62;
  }
  if ( v160[0] )
  {
    *(CStagingPool **)(v159[0] + 16LL) = v160[1];
    CStagingPool::ReleaseGdiSurface(v160[0], (struct CDDBITMAP_GDIDESC *)v159);
  }
  if ( v166 )
    (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v166 + 128LL))(v166, v162);
  v63 = v167;
  if ( v167 )
  {
    if ( !v170 )
      (*(void (__fastcall **)(DHSURF, _QWORD *, struct tagRECT *, CLIPOBJ *, struct CddBitmap **))(*(_QWORD *)v167 + 64LL))(
        v167,
        v163,
        v168,
        v165,
        v171);
    (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v63 + 128LL))(v63, v163);
  }
  v64 = *((_QWORD *)v164 + 895);
  v65 = *(struct _KTHREAD **)(v64 + 32);
  if ( v65 == KeGetCurrentThread() && v65 )
  {
    *(_QWORD *)(v64 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v64, 0, 1, 0);
  }
LABEL_82:
  CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v155);
  if ( !v146 )
  {
    LOBYTE(v66) = 2;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(v143 + 264))(v144, v66, v145);
  }
  return v48;
}

```

## disassembly

```asm
0x14000a254  push    rbp
0x14000a256  push    rbx
0x14000a257  push    rsi
0x14000a258  push    rdi
0x14000a259  push    r12
0x14000a25b  push    r13
0x14000a25d  push    r14
0x14000a25f  push    r15
0x14000a261  lea     rbp, [rsp-2C8h]
0x14000a269  sub     rsp, 3C8h
0x14000a270  mov     rax, cs:__security_cookie
0x14000a277  xor     rax, rsp
0x14000a27a  mov     [rbp+300h+var_50], rax
0x14000a281  mov     rax, [rbp+300h+arg_28]
0x14000a288  mov     r13, r8
0x14000a28b  mov     r11, [rbp+300h+arg_20]
0x14000a292  xorps   xmm0, xmm0
0x14000a295  mov     r15, [rbp+300h+arg_38]
0x14000a29c  mov     r14, rcx
0x14000a29f  mov     r12, [rbp+300h+arg_40]
0x14000a2a6  mov     rdi, [rbp+300h+arg_30]
0x14000a2ad  mov     [rbp+300h+var_338], rax
0x14000a2b1  mov     rax, [rbp+300h+arg_48]
0x14000a2b8  mov     [rbp+300h+var_230], rax
0x14000a2bf  mov     rax, [rbp+300h+arg_50]
0x14000a2c6  mov     [rbp+300h+var_220], rax
0x14000a2cd  mov     eax, [rbp+300h+arg_58]
0x14000a2d3  mov     [rbp+300h+psoSrc], r8
0x14000a2d7  xor     r8d, r8d
0x14000a2da  mov     [rsp+400h+var_39C], eax
0x14000a2de  mov     rax, [rbp+300h+arg_60]
0x14000a2e5  mov     [rbp+300h+var_340], rax
0x14000a2e9  mov     [rbp+300h+psoMask], r9
0x14000a2f0  lea     ebx, [r8+1]
0x14000a2f4  mov     [rbp+300h+psoTrg], rdx
0x14000a2f8  mov     [rsp+400h+var_390], rcx
0x14000a2fd  mov     [rbp+300h+var_358], r15
0x14000a301  mov     [rbp+300h+var_268], r12
0x14000a308  mov     [rbp+300h+pco], r11
0x14000a30c  mov     [rbp+300h+var_2A8], r8
0x14000a310  mov     [rbp+300h+var_270], r8
0x14000a317  movups  [rbp+300h+var_70], xmm0
0x14000a31e  test    r11, r11
0x14000a321  jnz     loc_14000A3B3
0x14000a327  mov     esi, [r15]
0x14000a32a  mov     edx, [r15+4]
0x14000a32e  mov     r12, r8
0x14000a331  mov     eax, [rdi+0Ch]
0x14000a334  sub     eax, [rdi+4]
0x14000a337  mov     r15d, [rdi+8]
0x14000a33b  add     eax, edx
0x14000a33d  sub     r15d, [rdi]
0x14000a340  mov     [rbp+300h+var_378], eax
0x14000a343  add     r15d, esi
0x14000a346  mov     rax, [r14+50h]
0x14000a34a  mov     [rsp+400h+var_398], edx
0x14000a34e  mov     [rbp+300h+var_360], r8
0x14000a352  movups  [rbp+300h+var_260], xmm0
0x14000a359  mov     [rbp+300h+var_278], ebx
0x14000a35f  movups  [rbp+300h+var_250], xmm0
0x14000a366  mov     [rbp+300h+var_280], r8
0x14000a36d  movups  [rbp+300h+var_240], xmm0
0x14000a374  call    _guard_dispatch_icall
0x14000a379  xor     r8d, r8d
0x14000a37c  test    eax, eax
0x14000a37e  jnz     loc_14000B63F
0x14000a384  cmp     [r13+4Ch], r8w
0x14000a389  jnz     loc_14000B6C3
0x14000a38f  mov     rcx, r12
0x14000a392  mov     rax, [rbp+300h+psoTrg]
0x14000a396  cmp     [rax+4Ch], r8w
0x14000a39b  jnz     loc_14000A478
0x14000a3a1  test    rcx, rcx
0x14000a3a4  jz      loc_14000A48E
0x14000a3aa  mov     rax, [rcx+8]
0x14000a3ae  jmp     loc_14000A489
0x14000a3b3  cmp     [r11+14h], r8b
0x14000a3b7  jz      loc_14000A327
0x14000a3bd  mov     edx, [r11+4]
0x14000a3c1  mov     r10d, [rdi]
0x14000a3c4  cmp     r10d, edx
0x14000a3c7  mov     ecx, [r11+0Ch]
0x14000a3cb  mov     eax, [rdi+8]
0x14000a3ce  cmovg   edx, r10d
0x14000a3d2  cmp     eax, ecx
0x14000a3d4  mov     dword ptr [rbp+300h+var_70], edx
0x14000a3da  cmovl   ecx, eax
0x14000a3dd  mov     dword ptr [rbp+300h+var_70+8], ecx
0x14000a3e3  cmp     edx, ecx
0x14000a3e5  jge     loc_14000A6A8
0x14000a3eb  mov     r8d, [r11+8]
0x14000a3ef  mov     r9d, [rdi+4]
0x14000a3f3  cmp     r9d, r8d
0x14000a3f6  mov     ecx, [r11+10h]
0x14000a3fa  mov     eax, [rdi+0Ch]
0x14000a3fd  cmovg   r8d, r9d
0x14000a401  cmp     eax, ecx
0x14000a403  mov     dword ptr [rbp+300h+var_70+4], r8d
0x14000a40a  cmovl   ecx, eax
0x14000a40d  mov     dword ptr [rbp+300h+var_70+0Ch], ecx
0x14000a413  cmp     r8d, ecx
0x14000a416  jge     loc_14000A6A8
0x14000a41c  mov     esi, [r15]
0x14000a41f  sub     edx, r10d
0x14000a422  mov     ecx, [r15+4]
0x14000a426  sub     r8d, r9d
0x14000a429  add     esi, edx
0x14000a42b  add     ecx, r8d
0x14000a42e  mov     dword ptr [rbp+300h+var_2A8], esi
0x14000a431  mov     dword ptr [rbp+300h+var_2A8+4], ecx
0x14000a434  test    r12, r12
0x14000a437  jz      short loc_14000A461
0x14000a439  mov     ecx, [r12]
0x14000a43d  lea     rax, [rbp+300h+var_270]
0x14000a444  add     ecx, edx
0x14000a446  mov     [rbp+300h+var_268], rax
0x14000a44d  mov     dword ptr [rbp+300h+var_270], ecx
0x14000a453  mov     ecx, [r12+4]
0x14000a458  add     ecx, r8d
0x14000a45b  mov     dword ptr [rbp+300h+var_270+4], ecx
0x14000a461  lea     r15, [rbp+300h+var_2A8]
0x14000a465  xor     r8d, r8d
0x14000a468  mov     [rbp+300h+var_358], r15
0x14000a46c  lea     rdi, [rbp+300h+var_70]
0x14000a473  jmp     loc_14000A32A
0x14000a478  mov     r12, [rax]
0x14000a47b  test    r12, r12
0x14000a47e  jz      loc_14000A3A1
0x14000a484  mov     rax, [r12+8]
0x14000a489  mov     [rsp+400h+var_390], rax
0x14000a48e  mov     r8, rcx; struct CddBitmap *
0x14000a491  mov     rdx, r12; struct CddBitmap *
0x14000a494  lea     rcx, [rbp+300h+var_218]; this
0x14000a49b  call    ??0CDDMULTIBITMAPLOCK@@QEAA@PEAVCddBitmap@@0@Z; CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK(CddBitmap *,CddBitmap *)
0x14000a4a0  mov     eax, [r13+48h]
0x14000a4a4  xor     r10d, r10d
0x14000a4a7  sub     eax, 7
0x14000a4aa  mov     [rsp+400h+var_394], r10d
0x14000a4af  cmp     eax, ebx
0x14000a4b1  mov     r9d, r10d
0x14000a4b4  setbe   r9b
0x14000a4b8  mov     [rsp+400h+var_388], r9d
0x14000a4bd  test    r12, r12
0x14000a4c0  jnz     loc_14000A760
0x14000a4c6  mov     r14d, r10d
0x14000a4c9  mov     rcx, [rsp+400h+var_390]
0x14000a4ce  mov     r11d, 0CCCCh
0x14000a4d4  mov     eax, [rbp+300h+var_378]
0x14000a4d7  sub     eax, [rsp+400h+var_398]
0x14000a4db  cmp     eax, [rcx+9ACh]
0x14000a4e1  jg      loc_14000B78E
0x14000a4e7  sub     r15d, esi
0x14000a4ea  cmp     r15d, [rcx+9A8h]
0x14000a4f1  jg      loc_14000B78E
0x14000a4f7  test    r14d, r14d
0x14000a4fa  jnz     loc_14000B6E1
0x14000a500  mov     r8d, [rsp+400h+var_39C]
0x14000a505  test    r9d, r9d
0x14000a508  jnz     loc_14000B796
0x14000a50e  mov     rax, [rbp+300h+var_338]
0x14000a512  test    rax, rax
0x14000a515  jz      loc_14000B7A2
0x14000a51b  mov     eax, [rax+4]
0x14000a51e  test    bl, al
0x14000a520  jnz     loc_14000B7A2
0x14000a526  mov     [rbp+300h+var_348], r10d
0x14000a52a  mov     rcx, [rbp+300h+var_358]
0x14000a52e  mov     [rbp+300h+var_34C], r10d
0x14000a532  mov     r15d, [rcx+4]
0x14000a536  test    r15d, r15d
0x14000a539  js      loc_14000B7BB
0x14000a53f  cmp     [rcx], r10d
0x14000a542  jl      loc_14000B7BB
0x14000a548  mov     dword ptr [rbp+300h+var_250+8], r14d
0x14000a54f  mov     esi, 0CDDBA5Eh
0x14000a554  test    r14d, r14d
0x14000a557  jz      loc_14000A77D
0x14000a55d  mov     edx, [rcx]
0x14000a55f  mov     ecx, [rdi+8]
0x14000a562  sub     ecx, [rdi]
0x14000a564  mov     eax, [r12+28h]
0x14000a569  add     ecx, edx
0x14000a56b  mov     dword ptr [rbp+300h+var_370], ecx
0x14000a56e  mov     [rbp+300h+var_200.right], ecx
0x14000a574  mov     ecx, [rdi+0Ch]
0x14000a577  sub     ecx, [rdi+4]
0x14000a57a  add     ecx, r15d
0x14000a57d  mov     [rsp+400h+var_398], edx
0x14000a581  mov     [rbp+300h+var_200.left], edx
0x14000a587  xor     edx, edx; Val
0x14000a589  mov     [rbp+300h+var_2A0], ecx
0x14000a58c  mov     [rbp+300h+var_200.bottom], ecx
0x14000a592  lea     rcx, [rbp+300h+var_1F0]; void *
0x14000a599  mov     [rbp+300h+var_378], eax
0x14000a59c  lea     r8d, [rdx+40h]; Size
0x14000a5a0  mov     [rbp+300h+var_200.top], r15d
0x14000a5a7  call    memset
0x14000a5ac  mov     rax, [rbp+300h+var_360]
0x14000a5b0  xor     edx, edx
0x14000a5b2  xorps   xmm0, xmm0
0x14000a5b5  movdqa  xmmword ptr [rbp+300h+var_1B0], xmm0
0x14000a5bd  test    rax, rax
0x14000a5c0  jnz     loc_14000BAB7
0x14000a5c6  mov     r15, [rsp+400h+var_390]
0x14000a5cb  lea     rax, [rbp+300h+var_1F0]
0x14000a5d2  mov     r8d, [r13+24h]; int
0x14000a5d6  lea     r9, [rbp+300h+var_200]; struct tagRECT *
0x14000a5dd  mov     edx, [r13+20h]; int
0x14000a5e1  add     r15, 1580h
0x14000a5e8  mov     rcx, r15; this
0x14000a5eb  mov     byte ptr [rsp+400h+prclTrg], bl; unsigned __int8
0x14000a5ef  mov     [rsp+400h+pxlo], rax; unsigned int
0x14000a5f4  call    ?GetGdiSurface@CStagingPool@@QEAAJHHPEBUtagRECT@@PEAUCDDBITMAP_GDIDESC@@E@Z; CStagingPool::GetGdiSurface(int,int,tagRECT const *,CDDBITMAP_GDIDESC *,uchar)
0x14000a5f9  xor     edx, edx
0x14000a5fb  test    eax, eax
0x14000a5fd  jns     loc_14000A6B0
0x14000a603  lea     ecx, [rdx+4]
0x14000a606  call    cs:__imp_WdLogSingleEntry0
0x14000a60d  nop     dword ptr [rax+rax+00h]
0x14000a612  mov     edi, 1163h
0x14000a617  mov     cs:WdLogGlobalForLineNumber, edi
0x14000a61d  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14000a624  nop     dword ptr [rax+rax+00h]
0x14000a629  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000a630  mov     [rax+18h], rcx
0x14000a634  mov     ecx, cs:dword_14003E570
0x14000a63a  mov     [rax+20h], rcx
0x14000a63e  mov     [rax+28h], rsi
0x14000a642  mov     cs:WdLogGlobalForLineNumber, edi
0x14000a648  xor     edi, edi
0x14000a64a  cmp     [rbp+300h+var_1B0], rdi
0x14000a651  jz      short loc_14000A678
0x14000a653  mov     rcx, qword ptr [rbp+300h+var_1F0]
0x14000a65a  lea     rdx, [rbp+300h+var_1F0]; struct CDDBITMAP_GDIDESC *
0x14000a661  mov     rax, [rbp+300h+var_1B0+8]
0x14000a668  mov     [rcx+10h], rax
0x14000a66c  mov     rcx, [rbp+300h+var_1B0]; this
0x14000a673  call    ?ReleaseGdiSurface@CStagingPool@@QEAAXPEAUCDDBITMAP_GDIDESC@@@Z; CStagingPool::ReleaseGdiSurface(CDDBITMAP_GDIDESC *)
0x14000a678  lea     rcx, [rbp+300h+var_218]; this
0x14000a67f  call    ??1CDDMULTIBITMAPLOCK@@QEAA@XZ; CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK(void)
0x14000a684  cmp     [rbp+300h+var_278], edi
0x14000a68a  jnz     short loc_14000A6A8
0x14000a68c  mov     rax, [rbp+300h+var_290]
0x14000a690  mov     dl, 2
0x14000a692  mov     r8, [rbp+300h+var_280]
0x14000a699  mov     ecx, [rbp+300h+var_288]
0x14000a69c  mov     rax, [rax+108h]
0x14000a6a3  call    _guard_dispatch_icall
0x14000a6a8  mov     eax, ebx
0x14000a6aa  jmp     loc_14000BE08
0x14000a6b0  mov     rcx, qword ptr [rbp+300h+var_1F0]
0x14000a6b7  mov     [rbp+300h+var_1B0], r15
0x14000a6be  mov     rax, [rcx+10h]
0x14000a6c2  mov     [rbp+300h+var_1B0+8], rax
0x14000a6c9  mov     [rcx+10h], rdx
0x14000a6cd  mov     r15, qword ptr [rbp+300h+var_1F0]
0x14000a6d4  cmp     [r15+38h], rdx
0x14000a6d8  jz      loc_14000B7C3
0x14000a6de  cmp     dword ptr [r15+48h], 6
0x14000a6e3  jnz     loc_14000B812
0x14000a6e9  movsxd  rdx, dword ptr [r15+40h]; unsigned int
0x14000a6ed  mov     r8d, [rbp+300h+var_200.top]
0x14000a6f4  mov     [rsp+400h+var_398], edx
0x14000a6f8  lea     eax, [r8+1]
0x14000a6fc  movsxd  rcx, eax
0x14000a6ff  mov     eax, 80000000h
0x14000a704  imul    rcx, rdx
0x14000a708  add     rax, rcx
0x14000a70b  mov     ecx, 0FFFFFFFFh
0x14000a710  cmp     rax, rcx
0x14000a713  jbe     loc_14000AEAC
0x14000a719  mov     [rbp+300h+var_34C], ebx
0x14000a71c  xor     r10d, r10d
0x14000a71f  cmp     [rbp+300h+var_1B0], r10
0x14000a726  jz      short loc_14000A778
0x14000a728  mov     rcx, qword ptr [rbp+300h+var_1F0]
0x14000a72f  lea     rdx, [rbp+300h+var_1F0]; struct CDDBITMAP_GDIDESC *
0x14000a736  mov     rax, [rbp+300h+var_1B0+8]
0x14000a73d  mov     [rcx+10h], rax
0x14000a741  mov     rcx, [rbp+300h+var_1B0]; this
0x14000a748  call    ?ReleaseGdiSurface@CStagingPool@@QEAAXPEAUCDDBITMAP_GDIDESC@@@Z; CStagingPool::ReleaseGdiSurface(CDDBITMAP_GDIDESC *)
0x14000a74d  xor     r10d, r10d
0x14000a750  mov     r14d, ebx
0x14000a753  cmp     [rbp+300h+var_34C], r10d
0x14000a757  jnz     short loc_14000A77D
0x14000a759  xor     esi, esi
0x14000a75b  jmp     loc_14000A9C5
0x14000a760  mov     eax, [r12+80h]
0x14000a768  mov     r14d, ebx
0x14000a76b  test    bl, al
0x14000a76d  jnz     loc_14000A4C9
0x14000a773  jmp     loc_14000A4C6
0x14000a778  test    r14d, r14d
0x14000a77b  jnz     short loc_14000A750
0x14000a77d  mov     rax, [rbp+300h+var_358]
0x14000a781  mov     r9, r12; struct CddBitmap *
0x14000a784  mov     ecx, [rdi+8]
0x14000a787  sub     ecx, [rdi]
0x14000a789  mov     r15, [rbp+300h+var_360]
0x14000a78d  mov     edx, [rax]
  ... truncated ...
```
