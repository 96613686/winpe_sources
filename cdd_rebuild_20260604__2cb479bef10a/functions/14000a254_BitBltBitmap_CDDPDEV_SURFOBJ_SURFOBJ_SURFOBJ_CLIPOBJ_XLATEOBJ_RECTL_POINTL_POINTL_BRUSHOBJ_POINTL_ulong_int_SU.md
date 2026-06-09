# BitBltBitmap(CDDPDEV *,_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))

- ea: `0x14000a254`
- end: `0x14000be2b`
- name: `?BitBltBitmap@@YAHPEAUCDDPDEV@@PEAU_SURFOBJ@@11PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@5PEAU_BRUSHOBJ@@5KP6AH1112345565K@Z@Z`
- size: `7127`
- prototype: `__int64 __usercall@<rax>(struct CDDPDEV *@<rcx>, struct _SURFOBJ *@<rdx>, struct _SURFOBJ *@<r8>, struct _SURFOBJ *@<r9>, struct _CLIPOBJ *, struct _XLATEOBJ *, RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int, int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))`
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
  __int64 v54; // rdx
  __int64 v55; // rcx
  SURFOBJ *v56; // r15
  struct CddBitmap **v57; // r13
  CLIPOBJ *v58; // rsi
  SURFOBJ *v59; // r13
  __int64 v60; // rcx
  struct _KTHREAD *v61; // rdx
  int v62; // r8d
  BOOL v63; // eax
  int v64; // ecx
  DHSURF v65; // rdi
  __int64 v66; // rcx
  struct _KTHREAD *v67; // rdx
  __int64 v68; // rdx
  char v69; // cl
  CLIPOBJ *v70; // r14
  _QWORD *v71; // rax
  DHSURF v72; // rdi
  __int64 v73; // rcx
  struct _KTHREAD *v74; // rdx
  unsigned __int8 v75; // r8
  char v76; // cl
  unsigned __int8 v77; // dl
  _QWORD *v78; // rax
  DHSURF v79; // rdi
  __int64 v80; // rcx
  struct _KTHREAD *v81; // rdx
  ULONG iBitmapFormat; // eax
  tagRECT *v83; // r13
  LONG v84; // r8d
  LONG v85; // r9d
  LONG v86; // r11d
  LONG v87; // r10d
  LONG v88; // edx
  LONG v89; // ecx
  struct CddBitmap **v90; // rax
  _QWORD *v91; // rax
  bool v92; // zf
  __int64 v93; // rcx
  _QWORD *v94; // r14
  NTSTATUS v95; // eax
  _QWORD *v96; // rax
  DHSURF v97; // rdi
  __int64 v98; // rcx
  struct _KTHREAD *v99; // rdx
  _QWORD *v100; // rax
  DHSURF v101; // rdi
  struct _KTHREAD *v102; // rdx
  _QWORD *v103; // r14
  NTSTATUS v104; // eax
  int v105; // edx
  int v106; // ecx
  _QWORD *v107; // rax
  _QWORD *v108; // rax
  int v109; // ebx
  _QWORD *v110; // rax
  _QWORD *v111; // rax
  int v112; // eax
  __int64 v113; // rcx
  _QWORD *v114; // rax
  int v115; // eax
  _QWORD *v116; // rax
  _QWORD *v117; // rax
  unsigned int pxlo; // [rsp+20h] [rbp-E0h]
  int pbo; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v120; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v121; // [rsp+61h] [rbp-9Fh]
  unsigned int v122; // [rsp+68h] [rbp-98h]
  LONG v123; // [rsp+68h] [rbp-98h]
  signed int v124; // [rsp+68h] [rbp-98h]
  unsigned int StagingVidMemAllocation; // [rsp+68h] [rbp-98h]
  unsigned int v126; // [rsp+6Ch] [rbp-94h]
  struct CDDPDEV *v127; // [rsp+70h] [rbp-90h]
  BOOL v128; // [rsp+78h] [rbp-88h]
  unsigned int v129; // [rsp+78h] [rbp-88h]
  struct CddBitmap *v130; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v131; // [rsp+88h] [rbp-78h]
  struct tagRECT *v132; // [rsp+90h] [rbp-70h] BYREF
  CLIPOBJ *pco; // [rsp+98h] [rbp-68h]
  struct CddBitmap *v134; // [rsp+A0h] [rbp-60h]
  POINTL *pptlSrc; // [rsp+A8h] [rbp-58h]
  unsigned int v136; // [rsp+B0h] [rbp-50h]
  int v137; // [rsp+B4h] [rbp-4Ch]
  int v138; // [rsp+B8h] [rbp-48h]
  BOOL (__stdcall *v139)(SURFOBJ *, SURFOBJ *, SURFOBJ *, CLIPOBJ *, XLATEOBJ *, RECTL *, POINTL *, POINTL *, BRUSHOBJ *, POINTL *, ROP4); // [rsp+C0h] [rbp-40h]
  XLATEOBJ *v140; // [rsp+C8h] [rbp-38h]
  _QWORD v141[16]; // [rsp+D0h] [rbp-30h] BYREF
  SURFOBJ *psoSrc; // [rsp+150h] [rbp+50h]
  unsigned __int64 v143; // [rsp+158h] [rbp+58h] BYREF
  LONG v144; // [rsp+160h] [rbp+60h]
  SURFOBJ *psoTrg; // [rsp+168h] [rbp+68h]
  __int64 v146; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v147; // [rsp+178h] [rbp+78h]
  __int64 v148; // [rsp+180h] [rbp+80h]
  int v149; // [rsp+188h] [rbp+88h]
  __int64 v150; // [rsp+190h] [rbp+90h] BYREF
  POINTL *pptlMask; // [rsp+198h] [rbp+98h]
  __int128 v152; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v153; // [rsp+1B0h] [rbp+B0h]
  __int128 v154; // [rsp+1C0h] [rbp+C0h]
  BRUSHOBJ *v155; // [rsp+1D0h] [rbp+D0h]
  SURFOBJ *psoMask; // [rsp+1D8h] [rbp+D8h]
  POINTL *pptlBrush; // [rsp+1E0h] [rbp+E0h]
  _BYTE v158[24]; // [rsp+1E8h] [rbp+E8h] BYREF
  tagRECT v159; // [rsp+200h] [rbp+100h] BYREF
  unsigned int v160[16]; // [rsp+210h] [rbp+110h] BYREF
  CStagingPool *v161[2]; // [rsp+250h] [rbp+150h]
  _QWORD v162[8]; // [rsp+260h] [rbp+160h] BYREF
  CStagingPool *v163[2]; // [rsp+2A0h] [rbp+1A0h]
  struct tagRECT v164; // [rsp+2B0h] [rbp+1B0h] BYREF
  _QWORD v165[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _QWORD v166[8]; // [rsp+300h] [rbp+200h] BYREF
  struct CDDPDEV *v167; // [rsp+340h] [rbp+240h]
  CLIPOBJ *v168; // [rsp+348h] [rbp+248h]
  struct CddBitmap *v169; // [rsp+350h] [rbp+250h]
  DHSURF v170; // [rsp+358h] [rbp+258h]
  struct tagRECT *v171; // [rsp+360h] [rbp+260h]
  __int64 v172; // [rsp+368h] [rbp+268h] BYREF
  int v173; // [rsp+370h] [rbp+270h]
  struct CddBitmap **v174; // [rsp+378h] [rbp+278h]
  char v175; // [rsp+380h] [rbp+280h]
  __int128 v176; // [rsp+390h] [rbp+290h] BYREF
  __int64 v177; // [rsp+3A0h] [rbp+2A0h] BYREF
  int v178; // [rsp+3A8h] [rbp+2A8h]
  int v179; // [rsp+3ACh] [rbp+2ACh]

  v13 = a3;
  v14 = (unsigned __int64 *)a8;
  prclTrg = (struct tagRECT *)a7;
  v140 = a6;
  v155 = a10;
  pptlBrush = a11;
  psoSrc = a3;
  v139 = a13;
  psoMask = a4;
  v17 = 1;
  psoTrg = a2;
  v127 = (struct CDDPDEV *)a1;
  pptlSrc = a8;
  pptlMask = a9;
  pco = a5;
  v143 = 0;
  v150 = 0;
  v176 = 0;
  if ( a5 && a5->iDComplexity )
  {
    left = a5->rclBounds.left;
    v27 = a7->left;
    right = a5->rclBounds.right;
    v29 = a7->right;
    if ( a7->left > left )
      left = a7->left;
    LODWORD(v176) = left;
    if ( v29 < right )
      right = v29;
    DWORD2(v176) = right;
    if ( left >= right )
      return v17;
    top = a5->rclBounds.top;
    v31 = a7->top;
    bottom = a5->rclBounds.bottom;
    v33 = a7->bottom;
    if ( v31 > top )
      top = a7->top;
    DWORD1(v176) = top;
    if ( v33 < bottom )
      bottom = v33;
    HIDWORD(v176) = bottom;
    if ( top >= bottom )
      return v17;
    v34 = left - v27;
    v35 = top - v31;
    x = v34 + a8->x;
    v143 = __PAIR64__(v35 + a8->y, x);
    if ( a9 )
    {
      v36 = v34 + a9->x;
      pptlMask = (POINTL *)&v150;
      LODWORD(v150) = v36;
      HIDWORD(v150) = v35 + a9->y;
    }
    v14 = &v143;
    pptlSrc = (POINTL *)&v143;
    prclTrg = (struct tagRECT *)&v176;
  }
  else
  {
    x = a8->x;
  }
  v19 = *((_DWORD *)v14 + 1);
  v20 = 0;
  v21 = prclTrg->right - prclTrg->left;
  v131 = v19 + prclTrg->bottom - prclTrg->top;
  v22 = x + v21;
  v23 = a1[10];
  v122 = v19;
  v134 = 0;
  v152 = 0;
  v149 = 1;
  v153 = 0;
  v148 = 0;
  v154 = 0;
  if ( v23() )
  {
    v105 = prclTrg->right - prclTrg->left;
    v106 = prclTrg->bottom - prclTrg->top;
    LODWORD(v152) = v13->iType;
    *(_QWORD *)((char *)&v154 + 4) = 0;
    HIDWORD(v154) = 0;
    DWORD1(v152) = psoTrg->iType;
    *((_QWORD *)&v152 + 1) = __PAIR64__(v106, v105);
    v153 = __PAIR64__(v106, v105);
    *(_QWORD *)&v154 = (unsigned __int16)rop4;
    CDDETWPROFILER::Init((CDDETWPROFILER *)&v146, (struct CDDPDEV *)a1, 0xBCDu, (struct _DXGKETW_PARAMS *)&v152, 0);
  }
  if ( v13->iType && v139 == EngBitBlt )
  {
    dhsurf = (struct CddBitmap *)v13->dhsurf;
    v134 = (struct CddBitmap *)v13->dhsurf;
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
    v127 = v25;
  }
  CDDMULTIBITMAPLOCK::CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v158, (struct CddBitmap *)v20, dhsurf);
  v126 = 0;
  v128 = v13->iBitmapFormat - 7 <= 1;
  if ( !v20 || (v37 = 1, ((_DWORD)v20[32] & 1) == 0) )
    v37 = 0;
  if ( (signed int)(v131 - v122) > *((_DWORD *)v127 + 619) || v22 - x > *((_DWORD *)v127 + 618) )
  {
    v37 = 0;
  }
  else if ( v37 )
  {
    v38 = rop4;
    switch ( rop4 )
    {
      case 0x6666u:
        v126 = 2;
        goto LABEL_33;
      case 0x8888u:
        v126 = 3;
        goto LABEL_33;
      case 0xCCCCu:
        v126 = 1;
        goto LABEL_33;
      case 0xEEEEu:
        v126 = 4;
        goto LABEL_33;
    }
    if ( (*((_DWORD *)v127 + 475) & 0x100000) == 0
      || (unsigned __int8)rop4 != BYTE1(rop4)
      || ((*((_BYTE *)qword_140039D10 + (unsigned __int8)rop4) | *((_BYTE *)qword_140039D10 + BYTE1(rop4))) & 0xE8) != 0 )
    {
      v37 = 0;
      goto LABEL_33;
    }
    v126 = (rop4 << 16) | 5;
  }
  v38 = rop4;
LABEL_33:
  if ( v13->iBitmapFormat - 7 <= 1 && v38 != 52428 )
    v37 = 0;
  if ( v140 && (v140->flXlate & 1) == 0 || (v138 = 1, v139 != EngBitBlt) )
    v138 = 0;
  v137 = 0;
  y = pptlSrc->y;
  if ( y < 0 || pptlSrc->x < 0 )
    v37 = 0;
  DWORD2(v153) = v37;
  if ( !v37 )
    goto LABEL_61;
  v40 = pptlSrc->x;
  v41 = *((_DWORD *)v20 + 10);
  LODWORD(v132) = pptlSrc->x + prclTrg->right - prclTrg->left;
  v159.right = (int)v132;
  v42 = y + prclTrg->bottom - prclTrg->top;
  v123 = v40;
  v159.left = v40;
  v144 = v42;
  v159.bottom = v42;
  v131 = v41;
  v159.top = y;
  memset(v160, 0, sizeof(v160));
  *(_OWORD *)v161 = 0;
  if ( !v134 )
  {
    if ( (int)CStagingPool::GetGdiSurface(
                (struct CDDPDEV *)((char *)v127 + 5504),
                v13->sizlBitmap.cx,
                v13->sizlBitmap.cy,
                &v159,
                (struct CDDBITMAP_GDIDESC *)v160,
                1u) < 0 )
    {
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 4451;
      v43 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v43[3] = gCddImageInfo;
      v43[4] = (unsigned int)dword_14003E570;
      v43[5] = 215857758;
      WdLogGlobalForLineNumber = 4451;
      if ( v161[0] )
      {
        *(CStagingPool **)(*(_QWORD *)v160 + 16LL) = v161[1];
        CStagingPool::ReleaseGdiSurface(v161[0], (struct CDDBITMAP_GDIDESC *)v160);
      }
      CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v158);
      v45 = v149 == 0;
LABEL_45:
      if ( v45 )
      {
        LOBYTE(v44) = 2;
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(v146 + 264))(v147, v44, v148);
      }
      return v17;
    }
    v161[0] = (struct CDDPDEV *)((char *)v127 + 5504);
    v161[1] = *(CStagingPool **)(*(_QWORD *)v160 + 16LL);
    *(_QWORD *)(*(_QWORD *)v160 + 16LL) = 0;
    v47 = *(_QWORD *)v160;
    if ( !*(_QWORD *)(*(_QWORD *)v160 + 56LL) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4457;
      v107 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v107[3] = gCddImageInfo;
      v107[4] = (unsigned int)dword_14003E570;
      v107[5] = 215857758;
      WdLogGlobalForLineNumber = 4457;
    }
    if ( *(_DWORD *)(v47 + 72) != 6 )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 4458;
      v108 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v108[3] = gCddImageInfo;
      v108[4] = (unsigned int)dword_14003E570;
      v108[5] = 215857758;
      WdLogGlobalForLineNumber = 4458;
    }
    v124 = *(_DWORD *)(v47 + 64);
    if ( (unsigned __int64)(v124 * (__int64)(v159.top + 1) + 0x80000000LL) > 0xFFFFFFFF )
    {
      v137 = 1;
      goto LABEL_54;
    }
    if ( v138 )
    {
      iBitmapFormat = v13->iBitmapFormat;
      if ( iBitmapFormat == 6 )
      {
        CopySurfBits(*(char **)(v47 + 56), v124, (char *)v13->pvScan0, v13->lDelta, pxlo, &v159);
LABEL_130:
        v83 = (tagRECT *)&v160[9];
        v84 = v159.bottom;
        v85 = v159.right;
        y = v159.top;
        v136 = v160[4];
        v130 = *(struct CddBitmap **)&v160[6];
        v129 = *(_DWORD *)(*(_QWORD *)v160 + 64LL);
        v123 = v159.left;
        goto LABEL_131;
      }
      if ( iBitmapFormat == 5 )
      {
        CopyBitsNonTemporal24_32(
          (unsigned int *)(*(_QWORD *)(v47 + 56) + (unsigned int)(4 * v159.left) + (__int64)(v159.top * v124)),
          v124,
          (const unsigned int *)((char *)v13->pvScan0 + 3 * v159.left + (__int64)(v159.top * v13->lDelta)),
          v13->lDelta,
          v159.bottom - v159.top,
          v159.right - v159.left);
        goto LABEL_130;
      }
    }
    if ( v128 )
    {
      memset(&v141[4], 0, 0x58u);
      v141[3] = &v159;
      v141[0] = pco;
      v141[1] = prclTrg;
      v141[2] = prclTrg;
      v141[10] = *(_QWORD *)(v47 + 56);
      LODWORD(v141[11]) = *(_DWORD *)(v47 + 64);
      HIDWORD(v141[11]) = -251592189;
      v141[5] = 0;
      ClipDstRects(
        (struct CLIP_RECTS_DATA *)v141,
        (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))FillColorKeyCallback);
      if ( ((unsigned int (__fastcall *)(__int64, SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, tagRECT *, POINTL *, _QWORD, _QWORD, _QWORD, int))v139)(
             v47,
             v13,
             0,
             0,
             v140,
             &v159,
             pptlSrc,
             0,
             0,
             0,
             52428) )
      {
        memset(v141, 0, 0x78u);
        v141[0] = pco;
        v141[1] = &v160[9];
        v141[10] = *(_QWORD *)&v160[6];
        LODWORD(v141[12]) = v160[4];
        v141[2] = prclTrg;
        v141[3] = prclTrg;
        v141[13] = 0x1F1010203LL;
        v141[11] = v20;
        HIDWORD(v141[12]) = v20[10];
        LODWORD(v141[14]) = *(_DWORD *)(*(_QWORD *)v160 + 64LL);
        v141[5] = 0;
        ClipDstRects(
          (struct CLIP_RECTS_DATA *)v141,
          (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::TransparentBltCallback);
        CddBitmap::VidMemDirtyUpdate((CddBitmap *)v20);
        v92 = v161[0] == 0;
        goto LABEL_138;
      }
      WdLogSingleEntry0(2);
      v109 = 4507;
      WdLogGlobalForLineNumber = 4507;
      v110 = (_QWORD *)WdLogNewEntry5_WdError();
    }
    else
    {
      if ( ((unsigned int (__fastcall *)(__int64, SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, tagRECT *, POINTL *, _QWORD, _QWORD, _QWORD, int))v139)(
             v47,
             v13,
             0,
             0,
             v140,
             &v159,
             pptlSrc,
             0,
             0,
             0,
             52428) )
      {
        goto LABEL_130;
      }
      WdLogSingleEntry0(2);
      v109 = 4536;
      WdLogGlobalForLineNumber = 4536;
      v110 = (_QWORD *)WdLogNewEntry5_WdError();
    }
    v110[3] = gCddImageInfo;
    v110[4] = (unsigned int)dword_14003E570;
    v110[5] = 215857758;
    WdLogGlobalForLineNumber = v109;
    if ( v161[0] )
    {
      *(CStagingPool **)(*(_QWORD *)v160 + 16LL) = v161[1];
      CStagingPool::ReleaseGdiSurface(v161[0], (struct CDDBITMAP_GDIDESC *)v160);
    }
    goto LABEL_119;
  }
  v136 = *((_DWORD *)v134 + 10);
  if ( !v136 )
  {
    WdLogSingleEntry0(4);
    WdLogGlobalForLineNumber = 4553;
    v111 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v111[3] = gCddImageInfo;
    v111[4] = (unsigned int)dword_14003E570;
    v111[5] = 215857758;
    v92 = v161[0] == 0;
    WdLogGlobalForLineNumber = 4553;
    goto LABEL_138;
  }
  v84 = v144;
  v83 = &v159;
  v85 = (int)v132;
  v129 = 0;
  v130 = v134;
LABEL_131:
  v86 = prclTrg->right;
  v87 = prclTrg->left;
  v88 = prclTrg->bottom;
  v89 = prclTrg->top;
  v178 = v86 - prclTrg->left;
  v177 = 0;
  v179 = v88 - v89;
  if ( v134 == (struct CddBitmap *)v20 )
  {
    v112 = *((_DWORD *)v127 + 475);
    if ( (v112 & 0x1000000) != 0 )
      goto LABEL_152;
    if ( (v112 & 0x2000000) != 0 )
    {
      if ( v123 > v87 )
        v87 = v123;
      if ( v85 < v86 )
        v86 = v85;
      if ( v87 < v86 )
      {
        if ( y > v89 )
          v89 = y;
        if ( v84 < v88 )
          v88 = v84;
        if ( v89 < v88 )
        {
LABEL_152:
          CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v164, *((struct CDDMUTEX **)v127 + 364), v84);
          StagingVidMemAllocation = CddBitmapStagingVidMem::GetStagingVidMemAllocation(
                                      *((CddBitmapStagingVidMem **)v127 + 687),
                                      prclTrg);
          if ( StagingVidMemAllocation )
          {
            memset(v141, 0, 0x78u);
            v141[0] = pco;
            v141[3] = &v177;
            v141[10] = v130;
            v141[9] = v127;
            v141[1] = v83;
            v141[2] = prclTrg;
            v141[11] = *((_QWORD *)v127 + 687);
            *(_QWORD *)((char *)&v141[13] + 4) = v129;
            v141[12] = __PAIR64__(StagingVidMemAllocation, v136);
            v141[5] = 0;
            LODWORD(v141[13]) = 1;
            ClipDstRects(
              (struct CLIP_RECTS_DATA *)v141,
              (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::BitBltCallback);
            memset(v141, 0, 0x78u);
            v141[0] = pco;
            v141[1] = &v177;
            v141[2] = prclTrg;
            v141[3] = prclTrg;
            v141[9] = v127;
            v141[10] = *((_QWORD *)v127 + 687);
            v141[12] = __PAIR64__(v131, StagingVidMemAllocation);
            LODWORD(v141[13]) = v126;
            *(_QWORD *)((char *)&v141[13] + 4) = 0;
            v132 = 0;
            v141[11] = v20;
            if ( *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v93, v131) + 72) + 3412LL)
              && (*((unsigned int (**)(void))v127 + 80))() )
            {
              LODWORD(v132) = v83->left - prclTrg->left;
              HIDWORD(v132) = v83->top - prclTrg->top;
              v141[5] = &v132;
            }
            else
            {
              v141[5] = 0;
            }
            ClipDstRects(
              (struct CLIP_RECTS_DATA *)v141,
              (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::BitBltCallback);
            if ( v164.right )
              ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*(_QWORD *)&v164.left);
            goto LABEL_134;
          }
          WdLogSingleEntry0(4);
          WdLogGlobalForLineNumber = 4692;
          v91 = (_QWORD *)WdLogNewEntry5_WdEvent();
          v91[3] = gCddImageInfo;
          v91[4] = (unsigned int)dword_14003E570;
          v91[5] = 215857758;
          WdLogGlobalForLineNumber = 4692;
          if ( v164.right )
            ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*(_QWORD *)&v164.left);
          v92 = v161[0] == 0;
LABEL_138:
          if ( !v92 )
          {
            *(CStagingPool **)(*(_QWORD *)v160 + 16LL) = v161[1];
            CStagingPool::ReleaseGdiSurface(v161[0], (struct CDDBITMAP_GDIDESC *)v160);
          }
          goto LABEL_120;
        }
      }
    }
  }
  memset(v141, 0, 0x78u);
  v141[0] = pco;
  v141[10] = v130;
  LODWORD(v141[13]) = v126;
  *(_QWORD *)((char *)&v141[13] + 4) = v129;
  v90 = 0;
  v141[1] = v83;
  v141[2] = prclTrg;
  v141[3] = prclTrg;
  v141[9] = v127;
  v141[11] = v20;
  v141[12] = __PAIR64__(v131, v136);
  v130 = 0;
  if ( v136 == v131 )
  {
    v113 = *(_QWORD *)(W32GetSessionState(v136, v131) + 72);
    v90 = 0;
    if ( *(_DWORD *)(v113 + 3412) )
    {
      if ( (*((unsigned int (**)(void))v127 + 80))() )
      {
        v90 = &v130;
        LODWORD(v130) = v83->left - prclTrg->left;
        HIDWORD(v130) = v83->top - prclTrg->top;
      }
      else
      {
        v90 = 0;
      }
    }
  }
  v141[5] = v90;
  ClipDstRects(
    (struct CLIP_RECTS_DATA *)v141,
    (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::BitBltCallback);
LABEL_134:
  CddBitmap::VidMemDirtyUpdate((CddBitmap *)v20);
  v13 = psoSrc;
LABEL_54:
  if ( v161[0] )
  {
    *(CStagingPool **)(*(_QWORD *)v160 + 16LL) = v161[1];
    CStagingPool::ReleaseGdiSurface(v161[0], (struct CDDBITMAP_GDIDESC *)v160);
  }
  v48 = 1;
  if ( !v137 )
    goto LABEL_82;
LABEL_61:
  v49 = v134;
  v50 = pptlSrc->x;
  v51 = pptlSrc->y;
  v52 = v127;
  v164.right = pptlSrc->x + prclTrg->right - prclTrg->left;
  v53 = prclTrg->bottom - prclTrg->top;
  v164.left = v50;
  v164.bottom = v51 + v53;
  v164.top = v51;
  GDIBITMAPACCESS2::GDIBITMAPACCESS2((GDIBITMAPACCESS2 *)v165, v127, v134, (struct CddBitmap *)v20);
  v132 = &v164;
  memset(v162, 0, sizeof(v162));
  *(_OWORD *)v163 = 0;
  if ( v49 )
  {
    v69 = v175;
    v57 = 0;
    if ( v175 )
    {
      v94 = (_QWORD *)*((_QWORD *)v167 + 895);
      if ( (struct _KTHREAD *)v94[4] != KeGetCurrentThread() )
      {
        v95 = KeWaitForSingleObject(v94, Executive, 0, 0, 0);
        if ( v95 != 258 )
        {
          v94[4] = KeGetCurrentThread();
          if ( v95 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 618;
            v114 = (_QWORD *)WdLogNewEntry5_WdError();
            v114[3] = gCddImageInfo;
            v114[4] = (unsigned int)dword_14003E570;
            v114[5] = 215857758;
            WdLogGlobalForLineNumber = 618;
            goto LABEL_96;
          }
        }
      }
      v69 = v175;
    }
    v70 = pco;
    LOBYTE(pbo) = v69 == 0;
    if ( (*(int (__fastcall **)(struct CddBitmap *, struct tagRECT *, struct tagRECT *, CLIPOBJ *, _DWORD, int, __int64 *, _QWORD *, int))(*(_QWORD *)v49 + 56LL))(
           v49,
           prclTrg,
           &v164,
           pco,
           0,
           1,
           &v172,
           v165,
           pbo) >= 0 )
    {
      v45 = *((_DWORD *)v49 + 8) == 2;
      v169 = v49;
      v168 = v70;
      if ( v45 )
      {
        pptlSrc = (POINTL *)prclTrg;
        v132 = prclTrg;
      }
      v56 = (SURFOBJ *)v165[0];
      goto LABEL_189;
    }
LABEL_96:
    WdLogSingleEntry0(4);
    WdLogGlobalForLineNumber = 4797;
    v71 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v71[3] = gCddImageInfo;
    v71[4] = (unsigned int)dword_14003E570;
    v71[5] = 215857758;
    WdLogGlobalForLineNumber = 4797;
    if ( v163[0] )
    {
      *(CStagingPool **)(v162[0] + 16LL) = v163[1];
      CStagingPool::ReleaseGdiSurface(v163[0], (struct CDDBITMAP_GDIDESC *)v162);
    }
    if ( v169 )
      (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v169 + 128LL))(v169, v165);
    v72 = v170;
    if ( v170 )
    {
      if ( !v173 )
        (*(void (__fastcall **)(DHSURF, _QWORD *, struct tagRECT *, CLIPOBJ *, struct CddBitmap **))(*(_QWORD *)v170 + 64LL))(
          v170,
          v166,
          v171,
          v168,
          v174);
      (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v72 + 128LL))(v72, v166);
    }
    v73 = *((_QWORD *)v167 + 895);
    v74 = *(struct _KTHREAD **)(v73 + 32);
    if ( v74 == KeGetCurrentThread() && v74 )
    {
      *(_QWORD *)(v73 + 32) = 0;
      KeReleaseSemaphore((PRKSEMAPHORE)v73, 0, 1, 0);
    }
    CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v158);
    v45 = v149 == 0;
    goto LABEL_45;
  }
  if ( v139 == EngBitBlt )
  {
    v56 = psoSrc;
    v57 = 0;
    goto LABEL_64;
  }
  if ( (int)CStagingPool::GetGdiSurface(
              (struct CDDPDEV *)((char *)v127 + 5504),
              v13->sizlBitmap.cx,
              v13->sizlBitmap.cy,
              &v164,
              (struct CDDBITMAP_GDIDESC *)v162,
              1u) < 0 )
  {
    WdLogSingleEntry0(4);
    WdLogGlobalForLineNumber = 4816;
    v100 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v100[3] = gCddImageInfo;
    v100[4] = (unsigned int)dword_14003E570;
    v100[5] = 215857758;
    WdLogGlobalForLineNumber = 4816;
    if ( v163[0] )
    {
      *(CStagingPool **)(v162[0] + 16LL) = v163[1];
      CStagingPool::ReleaseGdiSurface(v163[0], (struct CDDBITMAP_GDIDESC *)v162);
    }
    if ( v169 )
      (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v169 + 128LL))(v169, v165);
    v101 = v170;
    if ( v170 )
    {
      if ( !v173 )
        (*(void (__fastcall **)(DHSURF, _QWORD *, struct tagRECT *, CLIPOBJ *, struct CddBitmap **))(*(_QWORD *)v170 + 64LL))(
          v170,
          v166,
          v171,
          v168,
          v174);
      (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v101 + 128LL))(v101, v166);
    }
    v80 = *((_QWORD *)v167 + 895);
    v102 = *(struct _KTHREAD **)(v80 + 32);
    if ( v102 != KeGetCurrentThread() || !v102 )
      goto LABEL_120;
    *(_QWORD *)(v80 + 32) = 0;
LABEL_126:
    KeReleaseSemaphore((PRKSEMAPHORE)v80, 0, 1, 0);
    goto LABEL_120;
  }
  v163[0] = (struct CDDPDEV *)((char *)v127 + 5504);
  v163[1] = *(CStagingPool **)(v162[0] + 16LL);
  *(_QWORD *)(v162[0] + 16LL) = 0;
  v56 = (SURFOBJ *)v162[0];
  v54 = (v164.top + 1) * (__int64)*(int *)(v162[0] + 64LL);
  v55 = 0xFFFFFFFFLL;
  if ( (unsigned __int64)(v54 + 0x80000000LL) > 0xFFFFFFFF || v137 )
  {
    v56 = psoSrc;
    v57 = 0;
  }
  else
  {
    v115 = ((__int64 (__fastcall *)(_QWORD, SURFOBJ *, _QWORD, _QWORD, XLATEOBJ *, struct tagRECT *, POINTL *, _QWORD, _QWORD, _QWORD, int))v139)(
             v162[0],
             v13,
             0,
             0,
             v140,
             &v164,
             pptlSrc,
             0,
             0,
             0,
             52428);
    v57 = 0;
    if ( !v115 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 4834;
      v96 = (_QWORD *)WdLogNewEntry5_WdError();
      v96[3] = gCddImageInfo;
      v96[4] = (unsigned int)dword_14003E570;
      v96[5] = 215857758;
      WdLogGlobalForLineNumber = 4834;
      if ( v163[0] )
      {
        *(CStagingPool **)(v162[0] + 16LL) = v163[1];
        CStagingPool::ReleaseGdiSurface(v163[0], (struct CDDBITMAP_GDIDESC *)v162);
      }
      if ( v169 )
        (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v169 + 128LL))(v169, v165);
      v97 = v170;
      if ( v170 )
      {
        if ( !v173 )
          (*(void (__fastcall **)(DHSURF, _QWORD *, struct tagRECT *, CLIPOBJ *, struct CddBitmap **))(*(_QWORD *)v170 + 64LL))(
            v170,
            v166,
            v171,
            v168,
            v174);
        (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v97 + 128LL))(v97, v166);
      }
      v98 = *((_QWORD *)v167 + 895);
      v99 = *(struct _KTHREAD **)(v98 + 32);
      if ( v99 == KeGetCurrentThread() && v99 )
      {
        *(_QWORD *)(v98 + 32) = 0;
        KeReleaseSemaphore((PRKSEMAPHORE)v98, 0, 1, 0);
      }
LABEL_119:
      v17 = 0;
LABEL_120:
      CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v158);
      CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)&v146);
      return v17;
    }
  }
LABEL_189:
  v52 = v127;
LABEL_64:
  if ( v20 )
  {
    v130 = 0;
    if ( v20 == (DHSURF)v134
      && *(_DWORD *)(*(_QWORD *)(W32GetSessionState(v55, v54) + 72) + 3412LL)
      && (*((unsigned int (**)(void))v52 + 80))() )
    {
      v57 = &v130;
      LODWORD(v130) = v132->left - prclTrg->left;
      HIDWORD(v130) = v132->top - prclTrg->top;
    }
    v75 = *((_BYTE *)qword_140039D10 + BYTE1(rop4));
    v76 = v175;
    v77 = *((_BYTE *)qword_140039D10 + (unsigned __int8)rop4);
    v120 = v75;
    v121 = v77;
    if ( v175 )
    {
      v103 = (_QWORD *)*((_QWORD *)v167 + 895);
      if ( (struct _KTHREAD *)v103[4] != KeGetCurrentThread() )
      {
        v104 = KeWaitForSingleObject(v103, Executive, 0, 0, 0);
        if ( v104 == 258 )
        {
          v75 = v120;
          v77 = v121;
        }
        else
        {
          v103[4] = KeGetCurrentThread();
          if ( v104 < 0 )
          {
            WdLogSingleEntry0(2);
            WdLogGlobalForLineNumber = 659;
            v116 = (_QWORD *)WdLogNewEntry5_WdError();
            v116[3] = gCddImageInfo;
            v116[4] = (unsigned int)dword_14003E570;
            v116[5] = 215857758;
            WdLogGlobalForLineNumber = 659;
LABEL_108:
            WdLogSingleEntry0(4);
            WdLogGlobalForLineNumber = 4864;
            v78 = (_QWORD *)WdLogNewEntry5_WdEvent();
            v78[3] = gCddImageInfo;
            v78[4] = (unsigned int)dword_14003E570;
            v78[5] = 215857758;
            WdLogGlobalForLineNumber = 4864;
            if ( v163[0] )
            {
              *(CStagingPool **)(v162[0] + 16LL) = v163[1];
              CStagingPool::ReleaseGdiSurface(v163[0], (struct CDDBITMAP_GDIDESC *)v162);
            }
            if ( v169 )
              (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v169 + 128LL))(v169, v165);
            v79 = v170;
            if ( v170 )
            {
              if ( !v173 )
                (*(void (__fastcall **)(DHSURF, _QWORD *, struct tagRECT *, CLIPOBJ *, struct CddBitmap **))(*(_QWORD *)v170 + 64LL))(
                  v170,
                  v166,
                  v171,
                  v168,
                  v174);
              (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v79 + 128LL))(v79, v166);
            }
            v80 = *((_QWORD *)v167 + 895);
            v81 = *(struct _KTHREAD **)(v80 + 32);
            if ( v81 != KeGetCurrentThread() || !v81 )
              goto LABEL_120;
            *(_QWORD *)(v80 + 32) = 0;
            goto LABEL_126;
          }
          v75 = v120;
          v77 = v121;
        }
      }
      v76 = v175;
    }
    LOBYTE(pbo) = v76 == 0;
    if ( (*(int (__fastcall **)(DHSURF, struct tagRECT *, struct tagRECT *, CLIPOBJ *, int, int, char *, _QWORD *, int))(*(_QWORD *)v20 + 56LL))(
           v20,
           prclTrg,
           prclTrg,
           pco,
           1,
           (v75 | v77) & 0xB2,
           (char *)&v172 + 4,
           v166,
           pbo) >= 0 )
    {
      v48 = 1;
      if ( v168 && pco != v168 && (_BYTE)KdDebuggerEnabled )
      {
        DbgPrint("Ivalid pco in GDIBITMAPACCESS2::StartAccessDst");
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 670;
        v117 = (_QWORD *)WdLogNewEntry5_WdError();
        v117[3] = gCddImageInfo;
        v117[4] = (unsigned int)dword_14003E570;
        v117[5] = 215857758;
        WdLogGlobalForLineNumber = 670;
        __debugbreak();
      }
      v58 = pco;
      v174 = v57;
      v59 = (SURFOBJ *)v166[0];
      v168 = pco;
      v170 = v20;
      v171 = prclTrg;
      goto LABEL_66;
    }
    goto LABEL_108;
  }
  v58 = pco;
  v48 = 1;
  v59 = psoTrg;
LABEL_66:
  v60 = *((_QWORD *)v167 + 895);
  v61 = *(struct _KTHREAD **)(v60 + 32);
  if ( v61 == KeGetCurrentThread() && v61 )
  {
    *(_QWORD *)(v60 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v60, 0, 1, 0);
  }
  v62 = HIDWORD(v172);
  if ( v172 )
  {
    CDDPDEV::Flush(v167);
    v62 = HIDWORD(v172);
  }
  WaitForStartGdiAccessToFinish(v167, (struct CDDBITMAP_GDIDESC *)v166, v62);
  WaitForStartGdiAccessToFinish(v167, (struct CDDBITMAP_GDIDESC *)v165, v172);
  if ( v56->iBitmapFormat == 6 && v59->iBitmapFormat == 6 && rop4 == 52428 && v138 && v134 != (struct CddBitmap *)v20 )
  {
    memset(&v141[1], 0, 0x70u);
    v141[0] = v58;
    v141[10] = v56->pvScan0;
    v141[11] = v59->pvScan0;
    v141[1] = v132;
    v141[2] = prclTrg;
    v141[3] = prclTrg;
    LODWORD(v141[12]) = v56->lDelta;
    HIDWORD(v141[12]) = v59->lDelta;
    v141[5] = 0;
    ClipDstRects((struct CLIP_RECTS_DATA *)v141, CopyMemoryCallback);
  }
  else
  {
    v63 = EngBitBlt(v59, v56, psoMask, v58, v140, (RECTL *)prclTrg, pptlSrc, pptlMask, v155, pptlBrush, rop4);
    v64 = v173;
    v48 = v63;
    if ( !v63 )
      v64 = 1;
    v173 = v64;
  }
  if ( v163[0] )
  {
    *(CStagingPool **)(v162[0] + 16LL) = v163[1];
    CStagingPool::ReleaseGdiSurface(v163[0], (struct CDDBITMAP_GDIDESC *)v162);
  }
  if ( v169 )
    (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v169 + 128LL))(v169, v165);
  v65 = v170;
  if ( v170 )
  {
    if ( !v173 )
      (*(void (__fastcall **)(DHSURF, _QWORD *, struct tagRECT *, CLIPOBJ *, struct CddBitmap **))(*(_QWORD *)v170 + 64LL))(
        v170,
        v166,
        v171,
        v168,
        v174);
    (*(void (__fastcall **)(DHSURF, _QWORD *))(*(_QWORD *)v65 + 128LL))(v65, v166);
  }
  v66 = *((_QWORD *)v167 + 895);
  v67 = *(struct _KTHREAD **)(v66 + 32);
  if ( v67 == KeGetCurrentThread() && v67 )
  {
    *(_QWORD *)(v66 + 32) = 0;
    KeReleaseSemaphore((PRKSEMAPHORE)v66, 0, 1, 0);
  }
LABEL_82:
  CDDMULTIBITMAPLOCK::~CDDMULTIBITMAPLOCK((CDDMULTIBITMAPLOCK *)v158);
  if ( !v149 )
  {
    LOBYTE(v68) = 2;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(v146 + 264))(v147, v68, v148);
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
