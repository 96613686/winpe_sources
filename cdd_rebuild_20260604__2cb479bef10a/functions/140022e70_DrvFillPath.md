# DrvFillPath

- ea: `0x140022e70`
- end: `0x1400235ae`
- name: `DrvFillPath`
- size: `1854`
- prototype: `FN_DrvFillPath`
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update`

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
- `0x140022e70`
- `0x1400248f8`
- `0x140033db0`
- `0x140033e60`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x140023034`
- `watchdog!WdLogSingleEntry0` at `0x1400232dd`
- `watchdog!WdLogSingleEntry0` at `0x140023034`
- `watchdog!WdLogSingleEntry0` at `0x1400232dd`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002304b`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400232f4`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002304b`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x1400232f4`
- `WIN32K!EngFillPath` at `0x140023132`
- `WIN32K!EngFillPath` at `0x1400233b7`
- `WIN32K!EngFillPath` at `0x14002354b`
- `WIN32K!EngFillPath` at `0x140023132`
- `WIN32K!EngFillPath` at `0x1400233b7`
- `WIN32K!EngFillPath` at `0x14002354b`
- `WIN32K!PATHOBJ_vGetBounds` at `0x140022edb`
- `WIN32K!PATHOBJ_vGetBounds` at `0x140022edb`

## pseudocode

```c
BOOL __stdcall DrvFillPath(
        SURFOBJ *pso,
        PATHOBJ *ppo,
        CLIPOBJ *pco,
        BRUSHOBJ *pbo,
        POINTL *pptlBrushOrg,
        MIX mix,
        FLONG flOptions)
{
  DHPDEV dhpdev; // rdi
  BOOL v11; // ebx
  int v12; // r8d
  DHSURF dhsurf; // rdi
  __int64 v14; // rax
  CddBitmap *v15; // rax
  _QWORD *v16; // rax
  BOOL v17; // esi
  LONG lDelta; // edx
  int v19; // eax
  CDDPDEV *v20; // r14
  CLIPOBJ *v21; // r15
  int v22; // r8d
  _QWORD *v23; // rax
  DHSURF v24; // rdi
  int v25; // eax
  DHSURF v26; // rbx
  _BOOL8 v27; // r14
  int v29; // [rsp+50h] [rbp-B0h] BYREF
  CLIPOBJ *pcoa; // [rsp+58h] [rbp-A8h] BYREF
  SURFOBJ *v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  POINTL *v32; // [rsp+70h] [rbp-90h]
  __int128 v33; // [rsp+78h] [rbp-88h] BYREF
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int128 v35; // [rsp+98h] [rbp-68h]
  _BYTE v36[16]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v37; // [rsp+B8h] [rbp-48h]
  int v38; // [rsp+C0h] [rbp-40h]
  _BYTE v39[24]; // [rsp+C8h] [rbp-38h] BYREF
  SURFOBJ *psoa[8]; // [rsp+E0h] [rbp-20h] BYREF
  CddBitmap *v41; // [rsp+120h] [rbp+20h]
  struct _RECTL *v42; // [rsp+128h] [rbp+28h]
  struct _RECTL v43; // [rsp+130h] [rbp+30h] BYREF
  SURFOBJ *v44[8]; // [rsp+140h] [rbp+40h] BYREF
  CLIPOBJ *v45; // [rsp+180h] [rbp+80h]
  DHSURF v46; // [rsp+188h] [rbp+88h]
  SURFOBJ *pvScan0; // [rsp+190h] [rbp+90h]
  DHSURF v48; // [rsp+198h] [rbp+98h]
  DHPDEV v49; // [rsp+1A0h] [rbp+A0h]
  int v50; // [rsp+1A8h] [rbp+A8h]
  int v51; // [rsp+1ACh] [rbp+ACh]
  LONG v52; // [rsp+1B0h] [rbp+B0h]
  struct _RECTFX prectfx; // [rsp+1C0h] [rbp+C0h] BYREF

  pcoa = pco;
  dhpdev = pso->dhpdev;
  v31[0] = pso;
  v32 = pptlBrushOrg;
  prectfx = 0;
  PATHOBJ_vGetBounds(ppo, &prectfx);
  v11 = 1;
  v43.left = prectfx.xLeft >> 4;
  v43.top = prectfx.yTop >> 4;
  v38 = 1;
  v43.right = (prectfx.xRight + 15) >> 4;
  v37 = 0;
  v43.bottom = (prectfx.yBottom + 15) >> 4;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  if ( (*((unsigned int (**)(void))dhpdev + 10))() )
  {
    v34 = 0;
    v33 = 0;
    v35 = 0;
    DWORD1(v33) = pso->iType;
    LODWORD(v34) = v43.right - v43.left;
    DWORD1(v34) = v43.bottom - v43.top;
    CDDETWPROFILER::Init((CDDETWPROFILER *)v36, (struct CDDPDEV *)dhpdev, 0xBD2u, (struct _DXGKETW_PARAMS *)&v33, 0);
  }
  if ( pso->iType == 1 )
  {
    v17 = 0;
    CDDDEVLOCK::CDDDEVLOCK((CDDDEVLOCK *)v39, *((HSEMAPHORE *)dhpdev + 365), v12);
    if ( *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) )
    {
      LODWORD(v27) = 1;
    }
    else
    {
      CddAllocShadowSysMem((struct CDDPDEV *const)dhpdev);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) = *((_QWORD *)dhpdev + 319);
      *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 56LL) = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL);
      v27 = *(_QWORD *)(*((_QWORD *)dhpdev + 349) + 48LL) != 0;
    }
    CDDDEVLOCK::vUnlock((CDDDEVLOCK *)v39);
    if ( v27 )
    {
      ReadFromFrameBuffer((struct CDDPDEV *)dhpdev, v43.left, v43.top, v43.right, v43.bottom);
      v29 = 0;
      CDDSURFLOCK::vInit((CDDSURFLOCK *)v44, (struct CDDPDEV *)dhpdev, v31, &v43, &v29, pcoa);
      if ( (unsigned int)bIgnoreDeviceSurfaceUpdates(pso, &pcoa) )
      {
        CDDSURFLOCK::vDone((CDDSURFLOCK *)v44);
        goto LABEL_44;
      }
      v17 = EngFillPath(v31[0], ppo, pcoa, pbo, v32, mix, flOptions);
      if ( v17 && v29 == 1 )
        vGDIDirtyUpdate((struct CDDPDEV *)dhpdev, &v43, pcoa);
      CDDSURFLOCK::vDone((CDDSURFLOCK *)v44);
    }
LABEL_43:
    v11 = v17;
    goto LABEL_44;
  }
  dhsurf = pso->dhsurf;
  CDDBITMAPLOCK::CDDBITMAPLOCK((CDDBITMAPLOCK *)v31, (struct CddBitmap *)pso->dhsurf);
  if ( *((_DWORD *)&ROP2_NEED_DEST + (((_BYTE)mix - 1) & 0xF)) | *((_DWORD *)&ROP2_NEED_DEST + ((BYTE1(mix) - 1) & 0xF))
    || ((_DWORD)dhsurf[32] & 1) == 0 )
  {
    v20 = (CDDPDEV *)*((_QWORD *)dhsurf + 1);
    v21 = pcoa;
    memset(v44, 0, sizeof(v44));
    v49 = 0;
    v45 = 0;
    pvScan0 = 0;
    v46 = 0;
    LODWORD(v48) = 0;
    v29 = 0;
    if ( (*(int (__fastcall **)(DHSURF, struct _RECTL *, struct _RECTL *, CLIPOBJ *, int, int, int *, SURFOBJ **, char))(*(_QWORD *)dhsurf + 56LL))(
           dhsurf,
           &v43,
           &v43,
           pcoa,
           1,
           1,
           &v29,
           v44,
           1) >= 0 )
    {
      v45 = v21;
      v46 = dhsurf;
      pvScan0 = (SURFOBJ *)&v43;
      v49 = v44[0]->dhpdev;
      v44[0]->dhpdev = 0;
      v22 = v29;
      if ( v29 )
      {
        CDDPDEV::Flush(v20);
        v22 = v29;
      }
      WaitForStartGdiAccessToFinish(v20, (struct CDDBITMAP_GDIDESC *)v44, v22);
    }
    if ( !v46 )
    {
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 6321;
      v23 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v23[3] = gCddImageInfo;
      v23[4] = (unsigned int)dword_14003E570;
      v23[5] = 215857758;
      WdLogGlobalForLineNumber = 6321;
      if ( v46 )
      {
        v44[0]->dhpdev = v49;
        v24 = v46;
        if ( !(_DWORD)v48 )
          (*(void (__fastcall **)(DHSURF, SURFOBJ **, SURFOBJ *, CLIPOBJ *, _QWORD))(*(_QWORD *)v46 + 64LL))(
            v46,
            v44,
            pvScan0,
            v45,
            0);
        (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v24 + 128LL))(v24, v44);
      }
      goto LABEL_12;
    }
    v17 = EngFillPath(v44[0], ppo, pcoa, pbo, v32, mix, flOptions);
    v25 = (int)v48;
    if ( !v17 )
      v25 = 1;
    LODWORD(v48) = v25;
    if ( v46 )
    {
      v44[0]->dhpdev = v49;
      v26 = v46;
      if ( !(_DWORD)v48 )
        (*(void (__fastcall **)(DHSURF, SURFOBJ **, SURFOBJ *, CLIPOBJ *, _QWORD))(*(_QWORD *)v46 + 64LL))(
          v46,
          v44,
          pvScan0,
          v45,
          0);
      (*(void (__fastcall **)(DHSURF, SURFOBJ **))(*(_QWORD *)v26 + 128LL))(v26, v44);
    }
    goto LABEL_32;
  }
  memset(psoa, 0, sizeof(psoa));
  v14 = *(_QWORD *)dhsurf;
  v41 = 0;
  if ( (*(int (__fastcall **)(DHSURF, struct _RECTL *, __int64, SURFOBJ **))(v14 + 96))(dhsurf, &v43, 1, psoa) < 0 )
  {
    v15 = v41;
  }
  else
  {
    v15 = (CddBitmap *)dhsurf;
    v41 = (CddBitmap *)dhsurf;
    v42 = &v43;
  }
  if ( v15 )
  {
    v44[0] = (SURFOBJ *)pcoa;
    v44[1] = (SURFOBJ *)&v43;
    v44[2] = (SURFOBJ *)&v43;
    v44[3] = (SURFOBJ *)&v43;
    LOBYTE(v44[6]) = 0;
    v46 = 0;
    pvScan0 = (SURFOBJ *)psoa[0]->pvScan0;
    LODWORD(v48) = psoa[0]->lDelta;
    HIDWORD(v48) = -251592189;
    v44[5] = 0;
    ClipDstRects(
      (struct CLIP_RECTS_DATA *)v44,
      (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))FillColorKeyCallback);
    v17 = EngFillPath(psoa[0], ppo, pcoa, pbo, pptlBrushOrg, mix, flOptions);
    if ( v17 )
    {
      v44[0] = (SURFOBJ *)pcoa;
      LOBYTE(v44[6]) = 0;
      v46 = 0;
      lDelta = psoa[0]->lDelta;
      v44[1] = (SURFOBJ *)((char *)&psoa[4] + 4);
      v44[2] = (SURFOBJ *)&v43;
      v44[3] = (SURFOBJ *)&v43;
      pvScan0 = psoa[3];
      LODWORD(v49) = psoa[2];
      v19 = *((_DWORD *)dhsurf + 10);
      v52 = lDelta;
      HIDWORD(v49) = v19;
      v50 = -251592189;
      v48 = dhsurf;
      v51 = 1;
      v44[5] = 0;
      ClipDstRects(
        (struct CLIP_RECTS_DATA *)v44,
        (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::TransparentBltCallback);
    }
    if ( v41 )
    {
      (*(void (__fastcall **)(CddBitmap *, SURFOBJ **))(*(_QWORD *)v41 + 128LL))(v41, psoa);
      CddBitmap::VidMemDirtyUpdate(v41);
    }
LABEL_32:
    CDDBITMAPLOCK::~CDDBITMAPLOCK((CDDBITMAPLOCK *)v31);
    goto LABEL_43;
  }
  WdLogSingleEntry0(4);
  WdLogGlobalForLineNumber = 6276;
  v16 = (_QWORD *)WdLogNewEntry5_WdEvent();
  v16[3] = gCddImageInfo;
  v16[4] = (unsigned int)dword_14003E570;
  v16[5] = 215857758;
  WdLogGlobalForLineNumber = 6276;
  if ( v41 )
  {
    (*(void (__fastcall **)(CddBitmap *, SURFOBJ **))(*(_QWORD *)v41 + 128LL))(v41, psoa);
    CddBitmap::VidMemDirtyUpdate(v41);
  }
LABEL_12:
  CDDBITMAPLOCK::~CDDBITMAPLOCK((CDDBITMAPLOCK *)v31);
LABEL_44:
  CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)v36);
  return v11;
}

```

## disassembly

```asm
0x140022e70  push    rbp
0x140022e72  push    rbx
0x140022e73  push    rsi
0x140022e74  push    rdi
0x140022e75  push    r12
0x140022e77  push    r13
0x140022e79  push    r14
0x140022e7b  push    r15
0x140022e7d  lea     rbp, [rsp-0E8h]
0x140022e85  sub     rsp, 1E8h
0x140022e8c  mov     rax, cs:__security_cookie
0x140022e93  xor     rax, rsp
0x140022e96  mov     [rbp+120h+var_50], rax
0x140022e9d  mov     r14, [rbp+120h+pptlBrushOrg]
0x140022ea4  mov     r12, rdx
0x140022ea7  mov     [rsp+220h+pco], r8
0x140022eac  lea     rdx, [rbp+120h+prectfx]; prectfx
0x140022eb3  mov     rdi, [rcx+10h]
0x140022eb7  mov     r15, rcx
0x140022eba  mov     [rsp+220h+var_1C0], rcx
0x140022ebf  xorps   xmm0, xmm0
0x140022ec2  xorps   xmm1, xmm1
0x140022ec5  mov     [rsp+220h+var_1B0], r14
0x140022eca  mov     rcx, r12; ppo
0x140022ecd  mov     r13, r9
0x140022ed0  movups  xmmword ptr [rbp+120h+prectfx.xLeft], xmm0
0x140022ed7  movups  xmmword ptr [rbp+120h+var_F0.left], xmm1
0x140022edb  call    cs:__imp_PATHOBJ_vGetBounds
0x140022ee2  nop     dword ptr [rax+rax+00h]
0x140022ee7  mov     eax, [rbp+120h+prectfx.xLeft]
0x140022eed  xorps   xmm0, xmm0
0x140022ef0  sar     eax, 4
0x140022ef3  mov     ebx, 1
0x140022ef8  mov     [rbp+120h+var_F0.left], eax
0x140022efb  mov     eax, [rbp+120h+prectfx.yTop]
0x140022f01  sar     eax, 4
0x140022f04  mov     [rbp+120h+var_F0.top], eax
0x140022f07  mov     eax, [rbp+120h+prectfx.xRight]
0x140022f0d  add     eax, 0Fh
0x140022f10  mov     [rbp+120h+var_160], ebx
0x140022f13  sar     eax, 4
0x140022f16  mov     [rbp+120h+var_F0.right], eax
0x140022f19  mov     eax, [rbp+120h+prectfx.yBottom]
0x140022f1f  add     eax, 0Fh
0x140022f22  mov     [rbp+120h+var_168], 0
0x140022f2a  sar     eax, 4
0x140022f2d  mov     [rbp+120h+var_F0.bottom], eax
0x140022f30  movups  [rsp+220h+var_1A8], xmm0
0x140022f35  movups  [rbp+120h+var_198], xmm0
0x140022f39  movups  [rbp+120h+var_188], xmm0
0x140022f3d  mov     rax, [rdi+50h]
0x140022f41  call    _guard_dispatch_icall
0x140022f46  test    eax, eax
0x140022f48  jz      short loc_140022F91
0x140022f4a  xorps   xmm0, xmm0
0x140022f4d  mov     byte ptr [rsp+220h+var_200], 0; bool
0x140022f52  movups  [rbp+120h+var_198], xmm0
0x140022f56  lea     r9, [rsp+220h+var_1A8]; struct _DXGKETW_PARAMS *
0x140022f5b  mov     r8d, 0BD2h; unsigned int
0x140022f61  movups  [rsp+220h+var_1A8], xmm0
0x140022f66  mov     rdx, rdi; struct CDDPDEV *
0x140022f69  lea     rcx, [rbp+120h+var_178]; this
0x140022f6d  movups  [rbp+120h+var_188], xmm0
0x140022f71  movzx   eax, word ptr [r15+4Ch]
0x140022f76  mov     dword ptr [rsp+220h+var_1A8+4], eax
0x140022f7a  mov     eax, [rbp+120h+var_F0.right]
0x140022f7d  sub     eax, [rbp+120h+var_F0.left]
0x140022f80  mov     dword ptr [rbp+120h+var_198], eax
0x140022f83  mov     eax, [rbp+120h+var_F0.bottom]
0x140022f86  sub     eax, [rbp+120h+var_F0.top]
0x140022f89  mov     dword ptr [rbp+120h+var_198+4], eax
0x140022f8c  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x140022f91  cmp     [r15+4Ch], bx
0x140022f96  jz      loc_140023449
0x140022f9c  mov     rdi, [r15]
0x140022f9f  lea     rcx, [rsp+220h+var_1C0]; this
0x140022fa4  mov     rdx, rdi; struct CddBitmap *
0x140022fa7  call    ??0CDDBITMAPLOCK@@QEAA@PEAVCddBitmap@@@Z; CDDBITMAPLOCK::CDDBITMAPLOCK(CddBitmap *)
0x140022fac  mov     esi, [rbp+120h+mix]
0x140022fb2  lea     rdx, ?ROP2_NEED_DEST@@3PAHA; int near * ROP2_NEED_DEST
0x140022fb9  mov     eax, esi
0x140022fbb  shr     eax, 8
0x140022fbe  sub     eax, ebx
0x140022fc0  and     eax, 0Fh
0x140022fc3  lea     ecx, [rsi-1]
0x140022fc6  and     ecx, 0Fh
0x140022fc9  mov     eax, [rdx+rax*4]
0x140022fcc  or      eax, [rdx+rcx*4]
0x140022fcf  jnz     loc_1400231F7
0x140022fd5  mov     eax, [rdi+80h]
0x140022fdb  test    bl, al
0x140022fdd  jz      loc_1400231F7
0x140022fe3  xor     edx, edx; Val
0x140022fe5  lea     rcx, [rbp+120h+pso]; void *
0x140022fe9  lea     r8d, [rdx+40h]; Size
0x140022fed  call    memset
0x140022ff2  mov     rax, [rdi]
0x140022ff5  lea     r9, [rbp+120h+pso]
0x140022ff9  xor     r15d, r15d
0x140022ffc  lea     rdx, [rbp+120h+var_F0]
0x140023000  mov     r8d, ebx
0x140023003  mov     [rbp+120h+var_100], r15
0x140023007  mov     rcx, rdi
0x14002300a  mov     rax, [rax+60h]
0x14002300e  call    _guard_dispatch_icall
0x140023013  test    eax, eax
0x140023015  js      short loc_140023028
0x140023017  mov     rax, rdi
0x14002301a  lea     rcx, [rbp+120h+var_F0]
0x14002301e  mov     [rbp+120h+var_100], rax
0x140023022  mov     [rbp+120h+var_F8], rcx
0x140023026  jmp     short loc_14002302C
0x140023028  mov     rax, [rbp+120h+var_100]
0x14002302c  test    rax, rax
0x14002302f  jnz     short loc_1400230AE
0x140023031  lea     ecx, [rax+4]
0x140023034  call    cs:__imp_WdLogSingleEntry0
0x14002303b  nop     dword ptr [rax+rax+00h]
0x140023040  mov     edi, 1884h
0x140023045  mov     cs:WdLogGlobalForLineNumber, edi
0x14002304b  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140023052  nop     dword ptr [rax+rax+00h]
0x140023057  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002305e  mov     [rax+18h], rcx
0x140023062  mov     ecx, cs:dword_14003E570
0x140023068  mov     [rax+20h], rcx
0x14002306c  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140023074  mov     rcx, [rbp+120h+var_100]
0x140023078  mov     cs:WdLogGlobalForLineNumber, edi
0x14002307e  test    rcx, rcx
0x140023081  jz      short loc_14002309F
0x140023083  mov     rax, [rcx]
0x140023086  lea     rdx, [rbp+120h+pso]
0x14002308a  mov     rax, [rax+80h]
0x140023091  call    _guard_dispatch_icall
0x140023096  mov     rcx, [rbp+120h+var_100]; this
0x14002309a  call    ?VidMemDirtyUpdate@CddBitmap@@QEAAXXZ; CddBitmap::VidMemDirtyUpdate(void)
0x14002309f  lea     rcx, [rsp+220h+var_1C0]; this
0x1400230a4  call    ??1CDDBITMAPLOCK@@QEAA@XZ; CDDBITMAPLOCK::~CDDBITMAPLOCK(void)
0x1400230a9  jmp     loc_14002357F
0x1400230ae  mov     rcx, [rbp+120h+pso]
0x1400230b2  lea     rdx, ?FillColorKeyCallback@@YAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z; int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)
0x1400230b9  mov     rax, [rsp+220h+pco]
0x1400230be  mov     [rbp+120h+var_E0], rax
0x1400230c2  lea     rax, [rbp+120h+var_F0]
0x1400230c6  mov     [rbp+120h+var_D8], rax
0x1400230ca  lea     rax, [rbp+120h+var_F0]
0x1400230ce  mov     [rbp+120h+var_D0], rax
0x1400230d2  lea     rax, [rbp+120h+var_F0]
0x1400230d6  mov     [rbp+120h+var_C8], rax
0x1400230da  mov     [rbp+120h+var_B0], r15b
0x1400230de  mov     [rbp+120h+var_98], r15
0x1400230e5  mov     rax, [rcx+38h]
0x1400230e9  mov     [rbp+120h+var_90], rax
0x1400230f0  mov     eax, [rcx+40h]
0x1400230f3  lea     rcx, [rbp+120h+var_E0]; struct CLIP_RECTS_DATA *
0x1400230f7  mov     dword ptr [rbp+120h+var_88], eax
0x1400230fd  mov     dword ptr [rbp+120h+var_88+4], 0F1010203h
0x140023107  mov     [rbp+120h+var_B8], r15
0x14002310b  call    ?ClipDstRects@@YAJPEAUCLIP_RECTS_DATA@@P6AJ0IPEBUtagRECT@@@Z@Z; ClipDstRects(CLIP_RECTS_DATA *,long (*)(CLIP_RECTS_DATA *,uint,tagRECT const *))
0x140023110  mov     eax, [rbp+120h+flOptions]
0x140023116  mov     r9, r13; pbo
0x140023119  mov     r8, [rsp+220h+pco]; pco
0x14002311e  mov     rdx, r12; ppo
0x140023121  mov     rcx, [rbp+120h+pso]; pso
0x140023125  mov     [rsp+220h+var_1F0], eax; flOptions
0x140023129  mov     [rsp+220h+var_1F8], esi; mix
0x14002312d  mov     [rsp+220h+var_200], r14; pptlBrushOrg
0x140023132  call    cs:__imp_EngFillPath
0x140023139  nop     dword ptr [rax+rax+00h]
0x14002313e  mov     esi, eax
0x140023140  test    eax, eax
0x140023142  jz      loc_1400231C9
0x140023148  mov     rcx, [rsp+220h+pco]
0x14002314d  lea     rax, [rbp+120h+var_11C]
0x140023151  mov     [rbp+120h+var_E0], rcx
0x140023155  mov     rcx, [rbp+120h+pso]
0x140023159  mov     [rbp+120h+var_B0], r15b
0x14002315d  mov     [rbp+120h+var_98], r15
0x140023164  mov     edx, [rcx+40h]
0x140023167  lea     rcx, [rbp+120h+var_E0]; struct CLIP_RECTS_DATA *
0x14002316b  mov     [rbp+120h+var_D8], rax
0x14002316f  lea     rax, [rbp+120h+var_F0]
0x140023173  mov     [rbp+120h+var_D0], rax
0x140023177  lea     rax, [rbp+120h+var_F0]
0x14002317b  mov     [rbp+120h+var_C8], rax
0x14002317f  mov     rax, [rbp+120h+var_128]
0x140023183  mov     [rbp+120h+var_90], rax
0x14002318a  mov     eax, [rbp+120h+var_130]
0x14002318d  mov     dword ptr [rbp+120h+var_80], eax
0x140023193  mov     eax, [rdi+28h]
0x140023196  mov     [rbp+120h+var_70], edx
0x14002319c  lea     rdx, ?TransparentBltCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z; int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)
0x1400231a3  mov     dword ptr [rbp+120h+var_80+4], eax
0x1400231a9  mov     [rbp+120h+var_78], 0F1010203h
0x1400231b3  mov     [rbp+120h+var_88], rdi
0x1400231ba  mov     [rbp+120h+var_74], ebx
0x1400231c0  mov     [rbp+120h+var_B8], r15
0x1400231c4  call    ?ClipDstRects@@YAJPEAUCLIP_RECTS_DATA@@P6AJ0IPEBUtagRECT@@@Z@Z; ClipDstRects(CLIP_RECTS_DATA *,long (*)(CLIP_RECTS_DATA *,uint,tagRECT const *))
0x1400231c9  mov     rcx, [rbp+120h+var_100]
0x1400231cd  test    rcx, rcx
0x1400231d0  jz      loc_14002343A
0x1400231d6  mov     rax, [rcx]
0x1400231d9  lea     rdx, [rbp+120h+pso]
0x1400231dd  mov     rax, [rax+80h]
0x1400231e4  call    _guard_dispatch_icall
0x1400231e9  mov     rcx, [rbp+120h+var_100]; this
0x1400231ed  call    ?VidMemDirtyUpdate@CddBitmap@@QEAAXXZ; CddBitmap::VidMemDirtyUpdate(void)
0x1400231f2  jmp     loc_14002343A
0x1400231f7  mov     r14, [rdi+8]
0x1400231fb  lea     rcx, [rbp+120h+var_E0]; void *
0x1400231ff  mov     r15, [rsp+220h+pco]
0x140023204  xor     edx, edx; Val
0x140023206  lea     r8d, [rdx+40h]; Size
0x14002320a  call    memset
0x14002320f  xor     eax, eax
0x140023211  mov     [rsp+220h+var_1E0], bl
0x140023215  mov     [rbp+120h+var_80], rax
0x14002321c  lea     rcx, [rbp+120h+var_E0]
0x140023220  mov     [rsp+220h+var_1E8], rcx
0x140023225  lea     r8, [rbp+120h+var_F0]
0x140023229  mov     [rbp+120h+var_A0], rax
0x140023230  lea     rcx, [rsp+220h+var_1D0]
0x140023235  mov     qword ptr [rsp+220h+var_1F0], rcx
0x14002323a  lea     rdx, [rbp+120h+var_F0]
0x14002323e  mov     [rbp+120h+var_90], rax
0x140023245  mov     r9, r15
0x140023248  mov     [rbp+120h+var_98], rax
0x14002324f  mov     rcx, rdi
0x140023252  mov     dword ptr [rbp+120h+var_88], eax
0x140023258  mov     [rsp+220h+var_1D0], eax
0x14002325c  mov     rax, [rdi]
0x14002325f  mov     [rsp+220h+var_1F8], ebx
0x140023263  mov     dword ptr [rsp+220h+var_200], ebx
0x140023267  mov     rax, [rax+38h]
0x14002326b  call    _guard_dispatch_icall
0x140023270  test    eax, eax
0x140023272  js      short loc_1400232C8
0x140023274  mov     rdx, [rbp+120h+var_E0]
0x140023278  lea     rax, [rbp+120h+var_F0]
0x14002327c  mov     [rbp+120h+var_A0], r15
0x140023283  xor     r15d, r15d
0x140023286  mov     [rbp+120h+var_98], rdi
0x14002328d  mov     [rbp+120h+var_90], rax
0x140023294  mov     rax, [rdx+10h]
0x140023298  mov     [rbp+120h+var_80], rax
0x14002329f  mov     [rdx+10h], r15
0x1400232a3  mov     r8d, [rsp+220h+var_1D0]
0x1400232a8  test    r8d, r8d
0x1400232ab  jz      short loc_1400232BA
0x1400232ad  mov     rcx, r14; this
0x1400232b0  call    ?Flush@CDDPDEV@@QEAAJXZ; CDDPDEV::Flush(void)
0x1400232b5  mov     r8d, [rsp+220h+var_1D0]; int
0x1400232ba  lea     rdx, [rbp+120h+var_E0]; struct CDDBITMAP_GDIDESC *
0x1400232be  mov     rcx, r14; struct CDDPDEV *
0x1400232c1  call    ?WaitForStartGdiAccessToFinish@@YAXPEAUCDDPDEV@@PEAUCDDBITMAP_GDIDESC@@H@Z; WaitForStartGdiAccessToFinish(CDDPDEV *,CDDBITMAP_GDIDESC *,int)
0x1400232c6  jmp     short loc_1400232CB
0x1400232c8  xor     r15d, r15d
0x1400232cb  cmp     [rbp+120h+var_98], r15
0x1400232d2  jnz     loc_140023390
0x1400232d8  mov     ecx, 4
0x1400232dd  call    cs:__imp_WdLogSingleEntry0
0x1400232e4  nop     dword ptr [rax+rax+00h]
0x1400232e9  mov     edi, 18B1h
0x1400232ee  mov     cs:WdLogGlobalForLineNumber, edi
0x1400232f4  call    cs:__imp_WdLogNewEntry5_WdEvent
0x1400232fb  nop     dword ptr [rax+rax+00h]
0x140023300  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140023307  mov     [rax+18h], rcx
0x14002330b  mov     ecx, cs:dword_14003E570
0x140023311  mov     [rax+20h], rcx
0x140023315  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002331d  mov     cs:WdLogGlobalForLineNumber, edi
0x140023323  cmp     [rbp+120h+var_98], r15
0x14002332a  jz      loc_14002309F
0x140023330  mov     rcx, [rbp+120h+var_E0]
0x140023334  mov     rax, [rbp+120h+var_80]
0x14002333b  mov     [rcx+10h], rax
0x14002333f  mov     rdi, [rbp+120h+var_98]
0x140023346  cmp     dword ptr [rbp+120h+var_88], r15d
0x14002334d  jnz     short loc_140023375
0x14002334f  mov     rax, [rdi]
0x140023352  lea     rdx, [rbp+120h+var_E0]
0x140023356  mov     r9, [rbp+120h+var_A0]
0x14002335d  mov     rcx, rdi
0x140023360  mov     r8, [rbp+120h+var_90]
0x140023367  mov     [rsp+220h+var_200], r15
0x14002336c  mov     rax, [rax+40h]
0x140023370  call    _guard_dispatch_icall
0x140023375  mov     rax, [rdi]
0x140023378  lea     rdx, [rbp+120h+var_E0]
0x14002337c  mov     rcx, rdi
0x14002337f  mov     rax, [rax+80h]
0x140023386  call    _guard_dispatch_icall
0x14002338b  jmp     loc_14002309F
0x140023390  mov     eax, [rbp+120h+flOptions]
0x140023396  mov     r9, r13; pbo
0x140023399  mov     r8, [rsp+220h+pco]; pco
0x14002339e  mov     rdx, r12; ppo
0x1400233a1  mov     rcx, [rbp+120h+var_E0]; pso
  ... truncated ...
```
