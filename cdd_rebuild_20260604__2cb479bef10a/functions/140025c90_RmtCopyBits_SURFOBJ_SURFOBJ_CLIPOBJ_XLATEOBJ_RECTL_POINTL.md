# RmtCopyBits(_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *)

- ea: `0x140025c90`
- end: `0x140026190`
- name: `?RmtCopyBits@@YAHPEAU_SURFOBJ@@0PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@@Z`
- size: `1280`
- prototype: `__int64 __usercall@<rax>(struct _SURFOBJ *@<rcx>, struct _SURFOBJ *@<rdx>, struct _CLIPOBJ *@<r8>, struct _XLATEOBJ *@<r9>, RECTL *, struct _POINTL *)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x14000919c`
- `0x14000c730`
- `0x14000ef80`
- `0x140024f20`
- `0x140025030`
- `0x140025c90`
- `0x14002733c`
- `0x14002793c`
- `0x140027c48`
- `0x1400347d0`
- `0x1400371f0`
- `0x1400372d0`
- `0x140037640`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x140026033`
- `watchdog!WdLogSingleEntry0` at `0x140026033`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002604a`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14002604a`
- `WIN32K!W32GetSessionState` at `0x140025d6f`
- `WIN32K!W32GetSessionState` at `0x140025e9d`
- `WIN32K!W32GetSessionState` at `0x1400260c2`
- `WIN32K!W32GetSessionState` at `0x140025d6f`
- `WIN32K!W32GetSessionState` at `0x140025e9d`
- `WIN32K!W32GetSessionState` at `0x1400260c2`

## pseudocode

```c
__int64 __fastcall RmtCopyBits(
        struct _SURFOBJ *a1,
        struct _SURFOBJ *a2,
        struct _CLIPOBJ *a3,
        struct _XLATEOBJ *a4,
        RECTL *a5,
        struct _POINTL *a6)
{
  __int64 v10; // rdx
  SURFACCESS *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  struct CddBitmap *v14; // r14
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // r8d
  __int64 v21; // rax
  int v22; // edi
  struct CddBitmap *v23; // rbx
  _QWORD *v24; // rdx
  unsigned int v25; // ebx
  LONG x; // edx
  LONG y; // r8d
  struct CddBitmap *v28; // r15
  int v29; // ecx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // r8d
  _QWORD *v34; // rax
  __int64 SessionState; // rax
  struct _DDI_DISPATCH_TABLE *v36; // rax
  struct CDDPDEV *v38; // [rsp+50h] [rbp-B0h]
  struct CddBitmap *v39; // [rsp+60h] [rbp-A0h] BYREF
  struct CDDPDEV *v40[2]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v41[16]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+88h] [rbp-78h]
  _BYTE v43[16]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v44; // [rsp+A8h] [rbp-58h]
  struct _XLATEOBJ *v45; // [rsp+B8h] [rbp-48h] BYREF
  int v46; // [rsp+C0h] [rbp-40h]
  int v47; // [rsp+C4h] [rbp-3Ch]
  _QWORD v48[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+110h] [rbp+10h]
  struct CddBitmap *v50; // [rsp+118h] [rbp+18h]
  struct _XLATEOBJ **v51; // [rsp+120h] [rbp+20h]
  int v52; // [rsp+128h] [rbp+28h]
  __int64 v53; // [rsp+130h] [rbp+30h]
  _QWORD v54[8]; // [rsp+140h] [rbp+40h] BYREF
  struct _CLIPOBJ *v55; // [rsp+180h] [rbp+80h]
  struct CddBitmap *v56; // [rsp+188h] [rbp+88h]
  RECTL *v57; // [rsp+190h] [rbp+90h]
  int v58; // [rsp+198h] [rbp+98h]
  __int64 v59; // [rsp+1A0h] [rbp+A0h]

  v45 = a4;
  SURFSWITCHLOCK::SURFSWITCHLOCK((SURFSWITCHLOCK *)v40, a1, a2);
  SURFACCESS::SURFACCESS((SURFACCESS *)v43, a1);
  SURFACCESS::SURFACCESS((SURFACCESS *)v41, a2);
  if ( !v44 )
  {
    v11 = (SURFACCESS *)v41;
LABEL_31:
    v36 = SURFACCESS::Dispatch(v11, v10);
    v16 = (*((__int64 (__fastcall **)(struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, RECTL *, struct _POINTL *))v36
           + 19))(
            a1,
            a2,
            a3,
            a4,
            a5,
            a6);
    goto LABEL_32;
  }
  if ( !v42 || v44 == v42 )
  {
    v11 = (SURFACCESS *)v43;
    goto LABEL_31;
  }
  v40[0] = 0;
  v39 = 0;
  if ( !SURFACCESS::GetCddBitmap((SURFACCESS *)v43, (struct SURFACCESS *)v41, &v39, v40) )
  {
    x = a6->x;
    y = a6->y;
    v28 = v39;
    v46 = a6->x + a5->right - a5->left;
    v29 = y + a5->bottom - a5->top;
    v45 = (struct _XLATEOBJ *)__PAIR64__(y, x);
    v47 = v29;
    memset(v48, 0, sizeof(v48));
    v53 = 0;
    v49 = 0;
    v51 = 0;
    v50 = 0;
    v52 = 0;
    v30 = *(_QWORD *)v39;
    LODWORD(v39) = 0;
    v22 = 1;
    if ( (*(int (__fastcall **)(struct CddBitmap *, struct _XLATEOBJ **, struct _XLATEOBJ **, _QWORD, int, int, struct CddBitmap **, _QWORD *, char))(v30 + 56))(
           v28,
           &v45,
           &v45,
           0,
           1,
           1,
           &v39,
           v48,
           1) >= 0 )
    {
      v50 = v28;
      v49 = 0;
      v51 = &v45;
      v53 = *(_QWORD *)(v48[0] + 16LL);
      *(_QWORD *)(v48[0] + 16LL) = 0;
      v33 = (int)v39;
      if ( (_DWORD)v39 )
      {
        CDDPDEV::Flush(v40[0]);
        v33 = (int)v39;
      }
      WaitForStartGdiAccessToFinish(v40[0], (struct CDDBITMAP_GDIDESC *)v48, v33);
    }
    v52 = 1;
    if ( v50 )
    {
      SessionState = W32GetSessionState(v32, v31);
      v22 = (*(__int64 (__fastcall **)(struct _SURFOBJ *, _QWORD, struct _CLIPOBJ *, struct _XLATEOBJ *, RECTL *, struct _POINTL *))(*(_QWORD *)(SessionState + 72) + 992LL))(
              a1,
              v48[0],
              a3,
              a4,
              a5,
              a6);
      if ( !v50 )
        goto LABEL_17;
      *(_QWORD *)(v48[0] + 16LL) = v53;
      v23 = v50;
      if ( v52 )
        goto LABEL_26;
    }
    else
    {
      WdLogSingleEntry0(4);
      WdLogGlobalForLineNumber = 1431;
      v34 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v34[3] = gCddImageInfo;
      v34[4] = (unsigned int)dword_14003E570;
      v34[5] = 215857758;
      WdLogGlobalForLineNumber = 1431;
      if ( !v50 )
        goto LABEL_17;
      *(_QWORD *)(v48[0] + 16LL) = v53;
      v23 = v50;
      if ( v52 )
        goto LABEL_26;
    }
    (*(void (__fastcall **)(struct CddBitmap *, _QWORD *, struct _XLATEOBJ **, __int64, _QWORD))(*(_QWORD *)v50 + 64LL))(
      v50,
      v48,
      v51,
      v49,
      0);
LABEL_26:
    v24 = v48;
LABEL_16:
    (*(void (__fastcall **)(struct CddBitmap *, _QWORD *))(*(_QWORD *)v23 + 128LL))(v23, v24);
    goto LABEL_17;
  }
  v14 = v39;
  if ( (*((_DWORD *)v39 + 32) & 1) != 0 )
  {
    v15 = W32GetSessionState(v13, v12);
    LODWORD(v38) = 52428;
    v16 = DrvBitBltInternal(
            a1,
            a2,
            0,
            a3,
            v45,
            a5,
            a6,
            0,
            0,
            0,
            v38,
            *(int (**)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int))(*(_QWORD *)(v15 + 72) + 984LL));
LABEL_32:
    v25 = v16;
    goto LABEL_33;
  }
  memset(v54, 0, sizeof(v54));
  v59 = 0;
  v55 = 0;
  v57 = 0;
  v56 = 0;
  v58 = 0;
  v17 = *(_QWORD *)v39;
  LODWORD(v39) = 0;
  if ( (*(int (__fastcall **)(struct CddBitmap *, RECTL *, RECTL *, struct _CLIPOBJ *, int, _DWORD, struct CddBitmap **, _QWORD *, char))(v17 + 56))(
         v14,
         a5,
         a5,
         a3,
         1,
         0,
         &v39,
         v54,
         1) >= 0 )
  {
    v56 = v14;
    v55 = a3;
    v57 = a5;
    v59 = *(_QWORD *)(v54[0] + 16LL);
    *(_QWORD *)(v54[0] + 16LL) = 0;
    v20 = (int)v39;
    if ( (_DWORD)v39 )
    {
      CDDPDEV::Flush(v40[0]);
      v20 = (int)v39;
    }
    WaitForStartGdiAccessToFinish(v40[0], (struct CDDBITMAP_GDIDESC *)v54, v20);
  }
  v21 = W32GetSessionState(v19, v18);
  v22 = (*(__int64 (__fastcall **)(_QWORD, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, RECTL *, struct _POINTL *))(*(_QWORD *)(v21 + 72) + 992LL))(
          v54[0],
          a2,
          a3,
          v45,
          a5,
          a6);
  if ( v56 )
  {
    *(_QWORD *)(v54[0] + 16LL) = v59;
    v23 = v56;
    if ( !v58 )
      (*(void (__fastcall **)(struct CddBitmap *, _QWORD *, RECTL *, struct _CLIPOBJ *, _QWORD))(*(_QWORD *)v56 + 64LL))(
        v56,
        v54,
        v57,
        v55,
        0);
    v24 = v54;
    goto LABEL_16;
  }
LABEL_17:
  v25 = v22;
LABEL_33:
  SURFACCESS::~SURFACCESS((SURFACCESS *)v41);
  SURFACCESS::~SURFACCESS((SURFACCESS *)v43);
  SURFSWITCHLOCK::~SURFSWITCHLOCK((SURFSWITCHLOCK *)v40);
  return v25;
}

```

## disassembly

```asm
0x140025c90  push    rbp
0x140025c92  push    rbx
0x140025c93  push    rsi
0x140025c94  push    rdi
0x140025c95  push    r12
0x140025c97  push    r13
0x140025c99  push    r14
0x140025c9b  push    r15
0x140025c9d  lea     rbp, [rsp-0C8h]
0x140025ca5  sub     rsp, 1C8h
0x140025cac  mov     rax, cs:__security_cookie
0x140025cb3  xor     rax, rsp
0x140025cb6  mov     [rbp+100h+var_50], rax
0x140025cbd  mov     rbx, [rbp+100h+arg_20]
0x140025cc4  mov     rsi, r8
0x140025cc7  mov     r12, [rbp+100h+arg_28]
0x140025cce  mov     r8, rdx; struct _SURFOBJ *
0x140025cd1  mov     r15, rdx
0x140025cd4  mov     [rbp+100h+var_148], r9
0x140025cd8  mov     rdx, rcx; struct _SURFOBJ *
0x140025cdb  mov     r13, rcx
0x140025cde  lea     rcx, [rsp+200h+var_198]; this
0x140025ce3  mov     r14, r9
0x140025ce6  call    ??0SURFSWITCHLOCK@@QEAA@PEAU_SURFOBJ@@0@Z; SURFSWITCHLOCK::SURFSWITCHLOCK(_SURFOBJ *,_SURFOBJ *)
0x140025ceb  mov     rdx, r13; struct _SURFOBJ *
0x140025cee  lea     rcx, [rbp+100h+var_168]; this
0x140025cf2  call    ??0SURFACCESS@@QEAA@PEAU_SURFOBJ@@@Z; SURFACCESS::SURFACCESS(_SURFOBJ *)
0x140025cf7  mov     rdx, r15; struct _SURFOBJ *
0x140025cfa  lea     rcx, [rsp+200h+var_188]; this
0x140025cff  call    ??0SURFACCESS@@QEAA@PEAU_SURFOBJ@@@Z; SURFACCESS::SURFACCESS(_SURFOBJ *)
0x140025d04  mov     rcx, [rbp+100h+var_158]
0x140025d08  xor     edi, edi
0x140025d0a  test    rcx, rcx
0x140025d0d  jnz     short loc_140025D19
0x140025d0f  lea     rcx, [rsp+200h+var_188]
0x140025d14  jmp     loc_140026124
0x140025d19  mov     rax, [rbp+100h+var_178]
0x140025d1d  test    rax, rax
0x140025d20  jz      loc_140026120
0x140025d26  cmp     rcx, rax
0x140025d29  jz      loc_140026120
0x140025d2f  lea     r9, [rsp+200h+var_198]; struct CDDPDEV **
0x140025d34  mov     [rsp+200h+var_198], rdi
0x140025d39  lea     r8, [rsp+200h+var_1A0]; struct CddBitmap **
0x140025d3e  mov     [rsp+200h+var_1A0], rdi
0x140025d43  lea     rdx, [rsp+200h+var_188]; struct SURFACCESS *
0x140025d48  lea     rcx, [rbp+100h+var_168]; this
0x140025d4c  call    ?GetCddBitmap@SURFACCESS@@QEAAEAEAV1@PEAPEAVCddBitmap@@PEAPEAUCDDPDEV@@@Z; SURFACCESS::GetCddBitmap(SURFACCESS &,CddBitmap * *,CDDPDEV * *)
0x140025d51  test    al, al
0x140025d53  jz      loc_140025F3E
0x140025d59  mov     r14, [rsp+200h+var_1A0]
0x140025d5e  mov     edi, 1
0x140025d63  mov     eax, [r14+80h]
0x140025d6a  test    dil, al
0x140025d6d  jz      short loc_140025DD7
0x140025d6f  call    cs:__imp_W32GetSessionState
0x140025d76  nop     dword ptr [rax+rax+00h]
0x140025d7b  mov     r9, [rbp+100h+var_148]
0x140025d7f  xor     r8d, r8d; struct _SURFOBJ *
0x140025d82  mov     rdx, r15; struct _SURFOBJ *
0x140025d85  mov     rcx, [rax+48h]
0x140025d89  mov     rax, [rcx+3D8h]
0x140025d90  mov     rcx, r13; struct _SURFOBJ *
0x140025d93  mov     [rsp+200h+var_1A8], rax; int (*)(struct _SURFOBJ *, struct _SURFOBJ *, struct _SURFOBJ *, struct _CLIPOBJ *, struct _XLATEOBJ *, struct _RECTL *, struct _POINTL *, struct _POINTL *, struct _BRUSHOBJ *, struct _POINTL *, unsigned int)
0x140025d98  mov     dword ptr [rsp+200h+var_1B0], 0CCCCh; struct CDDPDEV *
0x140025da0  mov     [rsp+200h+var_1B8], 0; struct _POINTL *
0x140025da9  mov     [rsp+200h+var_1C0], 0; struct _BRUSHOBJ *
0x140025db2  mov     [rsp+200h+var_1C8], 0; struct _POINTL *
0x140025dbb  mov     [rsp+200h+var_1D0], r12; POINTL *
0x140025dc0  mov     [rsp+200h+var_1D8], rbx; RECTL *
0x140025dc5  mov     [rsp+200h+var_1E0], r9; struct _XLATEOBJ *
0x140025dca  mov     r9, rsi; struct _CLIPOBJ *
0x140025dcd  call    ?DrvBitBltInternal@@YAHPEAU_SURFOBJ@@00PEAU_CLIPOBJ@@PEAU_XLATEOBJ@@PEAU_RECTL@@PEAU_POINTL@@4PEAU_BRUSHOBJ@@4KP6AH0001234454K@Z@Z; DrvBitBltInternal(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong,int (*)(_SURFOBJ *,_SURFOBJ *,_SURFOBJ *,_CLIPOBJ *,_XLATEOBJ *,_RECTL *,_POINTL *,_POINTL *,_BRUSHOBJ *,_POINTL *,ulong))
0x140025dd2  jmp     loc_14002614B
0x140025dd7  xor     edx, edx; Val
0x140025dd9  lea     rcx, [rbp+100h+var_C0]; void *
0x140025ddd  lea     r8d, [rdx+40h]; Size
0x140025de1  call    memset
0x140025de6  xor     r13d, r13d
0x140025de9  mov     byte ptr [rsp+200h+var_1C0], dil
0x140025dee  mov     [rbp+100h+var_60], r13
0x140025df5  lea     rcx, [rbp+100h+var_C0]
0x140025df9  mov     [rsp+200h+var_1C8], rcx
0x140025dfe  mov     r9, rsi
0x140025e01  mov     [rbp+100h+var_80], r13
0x140025e08  lea     rcx, [rsp+200h+var_1A0]
0x140025e0d  mov     [rsp+200h+var_1D0], rcx
0x140025e12  mov     r8, rbx
0x140025e15  mov     [rbp+100h+var_70], r13
0x140025e1c  mov     rdx, rbx
0x140025e1f  mov     [rbp+100h+var_78], r13
0x140025e26  mov     rcx, r14
0x140025e29  mov     [rbp+100h+var_68], r13d
0x140025e30  mov     rax, [r14]
0x140025e33  mov     dword ptr [rsp+200h+var_1D8], r13d
0x140025e38  mov     dword ptr [rsp+200h+var_1A0], r13d
0x140025e3d  mov     dword ptr [rsp+200h+var_1E0], edi
0x140025e41  mov     rax, [rax+38h]
0x140025e45  call    _guard_dispatch_icall
0x140025e4a  test    eax, eax
0x140025e4c  js      short loc_140025E9D
0x140025e4e  mov     rdx, [rbp+100h+var_C0]
0x140025e52  mov     [rbp+100h+var_78], r14
0x140025e59  mov     [rbp+100h+var_80], rsi
0x140025e60  mov     [rbp+100h+var_70], rbx
0x140025e67  mov     rax, [rdx+10h]
0x140025e6b  mov     [rbp+100h+var_60], rax
0x140025e72  mov     [rdx+10h], r13
0x140025e76  mov     r8d, dword ptr [rsp+200h+var_1A0]
0x140025e7b  test    r8d, r8d
0x140025e7e  jz      short loc_140025E8F
0x140025e80  mov     rcx, [rsp+200h+var_198]; this
0x140025e85  call    ?Flush@CDDPDEV@@QEAAJXZ; CDDPDEV::Flush(void)
0x140025e8a  mov     r8d, dword ptr [rsp+200h+var_1A0]; int
0x140025e8f  mov     rcx, [rsp+200h+var_198]; struct CDDPDEV *
0x140025e94  lea     rdx, [rbp+100h+var_C0]; struct CDDBITMAP_GDIDESC *
0x140025e98  call    ?WaitForStartGdiAccessToFinish@@YAXPEAUCDDPDEV@@PEAUCDDBITMAP_GDIDESC@@H@Z; WaitForStartGdiAccessToFinish(CDDPDEV *,CDDBITMAP_GDIDESC *,int)
0x140025e9d  call    cs:__imp_W32GetSessionState
0x140025ea4  nop     dword ptr [rax+rax+00h]
0x140025ea9  mov     r9, [rbp+100h+var_148]
0x140025ead  mov     r8, rsi
0x140025eb0  mov     [rsp+200h+var_1D8], r12
0x140025eb5  mov     rdx, r15
0x140025eb8  mov     [rsp+200h+var_1E0], rbx
0x140025ebd  mov     rcx, [rax+48h]
0x140025ec1  mov     rax, [rcx+3E0h]
0x140025ec8  mov     rcx, [rbp+100h+var_C0]
0x140025ecc  call    _guard_dispatch_icall
0x140025ed1  mov     edi, eax
0x140025ed3  cmp     [rbp+100h+var_78], r13
0x140025eda  jz      short loc_140025F37
0x140025edc  mov     rdx, [rbp+100h+var_C0]
0x140025ee0  mov     rcx, [rbp+100h+var_60]
0x140025ee7  mov     [rdx+10h], rcx
0x140025eeb  mov     rbx, [rbp+100h+var_78]
0x140025ef2  cmp     [rbp+100h+var_68], r13d
0x140025ef9  jnz     short loc_140025F21
0x140025efb  mov     rcx, [rbx]
0x140025efe  lea     rdx, [rbp+100h+var_C0]
0x140025f02  mov     r9, [rbp+100h+var_80]
0x140025f09  mov     r8, [rbp+100h+var_70]
0x140025f10  mov     [rsp+200h+var_1E0], r13
0x140025f15  mov     rax, [rcx+40h]
0x140025f19  mov     rcx, rbx
0x140025f1c  call    _guard_dispatch_icall
0x140025f21  lea     rdx, [rbp+100h+var_C0]
0x140025f25  mov     rax, [rbx]
0x140025f28  mov     rcx, rbx
0x140025f2b  mov     rax, [rax+80h]
0x140025f32  call    _guard_dispatch_icall
0x140025f37  mov     ebx, edi
0x140025f39  jmp     loc_14002614D
0x140025f3e  mov     edx, [r12]
0x140025f42  mov     r8d, [r12+4]
0x140025f47  mov     ecx, [rbx+8]
0x140025f4a  sub     ecx, [rbx]
0x140025f4c  mov     r15, [rsp+200h+var_1A0]
0x140025f51  add     ecx, edx
0x140025f53  mov     [rbp+100h+var_140], ecx
0x140025f56  mov     ecx, [rbx+0Ch]
0x140025f59  sub     ecx, [rbx+4]
0x140025f5c  add     ecx, r8d
0x140025f5f  mov     dword ptr [rbp+100h+var_148], edx
0x140025f62  xor     edx, edx; Val
0x140025f64  mov     [rbp+100h+var_13C], ecx
0x140025f67  mov     dword ptr [rbp+100h+var_148+4], r8d
0x140025f6b  lea     rcx, [rbp+100h+var_130]; void *
0x140025f6f  lea     r8d, [rdx+40h]; Size
0x140025f73  call    memset
0x140025f78  mov     [rbp+100h+var_D0], rdi
0x140025f7c  lea     rcx, [rbp+100h+var_130]
0x140025f80  mov     [rbp+100h+var_F0], rdi
0x140025f84  lea     r8, [rbp+100h+var_148]
0x140025f88  mov     [rbp+100h+var_E0], rdi
0x140025f8c  lea     rdx, [rbp+100h+var_148]
0x140025f90  mov     [rbp+100h+var_E8], rdi
0x140025f94  xor     r9d, r9d
0x140025f97  mov     [rbp+100h+var_D8], edi
0x140025f9a  mov     rax, [r15]
0x140025f9d  mov     dword ptr [rsp+200h+var_1A0], edi
0x140025fa1  mov     edi, 1
0x140025fa6  mov     byte ptr [rsp+200h+var_1C0], dil
0x140025fab  mov     [rsp+200h+var_1C8], rcx
0x140025fb0  lea     rcx, [rsp+200h+var_1A0]
0x140025fb5  mov     rax, [rax+38h]
0x140025fb9  mov     [rsp+200h+var_1D0], rcx
0x140025fbe  mov     rcx, r15
0x140025fc1  mov     dword ptr [rsp+200h+var_1D8], edi
0x140025fc5  mov     dword ptr [rsp+200h+var_1E0], edi
0x140025fc9  call    _guard_dispatch_icall
0x140025fce  test    eax, eax
0x140025fd0  js      short loc_14002601E
0x140025fd2  mov     rdx, [rbp+100h+var_130]
0x140025fd6  lea     rax, [rbp+100h+var_148]
0x140025fda  mov     [rbp+100h+var_E8], r15
0x140025fde  xor     r15d, r15d
0x140025fe1  mov     [rbp+100h+var_F0], r15
0x140025fe5  mov     [rbp+100h+var_E0], rax
0x140025fe9  mov     rax, [rdx+10h]
0x140025fed  mov     [rbp+100h+var_D0], rax
0x140025ff1  mov     [rdx+10h], r15
0x140025ff5  mov     r8d, dword ptr [rsp+200h+var_1A0]
0x140025ffa  test    r8d, r8d
0x140025ffd  jz      short loc_14002600E
0x140025fff  mov     rcx, [rsp+200h+var_198]; this
0x140026004  call    ?Flush@CDDPDEV@@QEAAJXZ; CDDPDEV::Flush(void)
0x140026009  mov     r8d, dword ptr [rsp+200h+var_1A0]; int
0x14002600e  mov     rcx, [rsp+200h+var_198]; struct CDDPDEV *
0x140026013  lea     rdx, [rbp+100h+var_130]; struct CDDBITMAP_GDIDESC *
0x140026017  call    ?WaitForStartGdiAccessToFinish@@YAXPEAUCDDPDEV@@PEAUCDDBITMAP_GDIDESC@@H@Z; WaitForStartGdiAccessToFinish(CDDPDEV *,CDDBITMAP_GDIDESC *,int)
0x14002601c  jmp     short loc_140026021
0x14002601e  xor     r15d, r15d
0x140026021  mov     [rbp+100h+var_D8], edi
0x140026024  cmp     [rbp+100h+var_E8], r15
0x140026028  jnz     loc_1400260C2
0x14002602e  mov     ecx, 4
0x140026033  call    cs:__imp_WdLogSingleEntry0
0x14002603a  nop     dword ptr [rax+rax+00h]
0x14002603f  mov     ebx, 597h
0x140026044  mov     cs:WdLogGlobalForLineNumber, ebx
0x14002604a  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140026051  nop     dword ptr [rax+rax+00h]
0x140026056  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002605d  mov     [rax+18h], rcx
0x140026061  mov     ecx, cs:dword_14003E570
0x140026067  mov     [rax+20h], rcx
0x14002606b  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140026073  mov     cs:WdLogGlobalForLineNumber, ebx
0x140026079  cmp     [rbp+100h+var_E8], r15
0x14002607d  jz      loc_140025F37
0x140026083  mov     rcx, [rbp+100h+var_130]
0x140026087  mov     rax, [rbp+100h+var_D0]
0x14002608b  mov     [rcx+10h], rax
0x14002608f  mov     rbx, [rbp+100h+var_E8]
0x140026093  cmp     [rbp+100h+var_D8], r15d
0x140026097  jnz     short loc_1400260B9
0x140026099  mov     rax, [rbx]
0x14002609c  mov     rax, [rax+40h]
0x1400260a0  mov     r9, [rbp+100h+var_F0]
0x1400260a4  lea     rdx, [rbp+100h+var_130]
0x1400260a8  mov     r8, [rbp+100h+var_E0]
0x1400260ac  mov     rcx, rbx
0x1400260af  mov     [rsp+200h+var_1E0], r15
0x1400260b4  call    _guard_dispatch_icall
0x1400260b9  lea     rdx, [rbp+100h+var_130]
0x1400260bd  jmp     loc_140025F25
0x1400260c2  call    cs:__imp_W32GetSessionState
0x1400260c9  nop     dword ptr [rax+rax+00h]
0x1400260ce  mov     rdx, [rbp+100h+var_130]
0x1400260d2  mov     r9, r14
0x1400260d5  mov     [rsp+200h+var_1D8], r12
0x1400260da  mov     r8, rsi
0x1400260dd  mov     [rsp+200h+var_1E0], rbx
0x1400260e2  mov     rcx, [rax+48h]
0x1400260e6  mov     rax, [rcx+3E0h]
0x1400260ed  mov     rcx, r13
0x1400260f0  call    _guard_dispatch_icall
0x1400260f5  mov     edi, eax
0x1400260f7  cmp     [rbp+100h+var_E8], r15
0x1400260fb  jz      loc_140025F37
0x140026101  mov     rdx, [rbp+100h+var_130]
0x140026105  mov     rcx, [rbp+100h+var_D0]
0x140026109  mov     [rdx+10h], rcx
0x14002610d  mov     rbx, [rbp+100h+var_E8]
0x140026111  cmp     [rbp+100h+var_D8], r15d
0x140026115  jnz     short loc_1400260B9
0x140026117  mov     rcx, [rbx]
0x14002611a  mov     rax, [rcx+40h]
0x14002611e  jmp     short loc_1400260A0
0x140026120  lea     rcx, [rbp+100h+var_168]; this
0x140026124  call    ?Dispatch@SURFACCESS@@QEAAPEAU_DDI_DISPATCH_TABLE@@XZ; SURFACCESS::Dispatch(void)
0x140026129  mov     [rsp+200h+var_1D8], r12
0x14002612e  mov     r9, r14
0x140026131  mov     r8, rsi
0x140026134  mov     [rsp+200h+var_1E0], rbx
0x140026139  mov     rdx, r15
0x14002613c  mov     rcx, r13
0x14002613f  mov     rax, [rax+98h]
0x140026146  call    _guard_dispatch_icall
0x14002614b  mov     ebx, eax
0x14002614d  lea     rcx, [rsp+200h+var_188]; this
0x140026152  call    ??1SURFACCESS@@QEAA@XZ; SURFACCESS::~SURFACCESS(void)
0x140026157  lea     rcx, [rbp+100h+var_168]; this
0x14002615b  call    ??1SURFACCESS@@QEAA@XZ; SURFACCESS::~SURFACCESS(void)
0x140026160  lea     rcx, [rsp+200h+var_198]; this
0x140026165  call    ??1SURFSWITCHLOCK@@QEAA@XZ; SURFSWITCHLOCK::~SURFSWITCHLOCK(void)
0x14002616a  mov     eax, ebx
0x14002616c  mov     rcx, [rbp+100h+var_50]
0x140026173  xor     rcx, rsp; StackCookie
0x140026176  call    __security_check_cookie
0x14002617b  add     rsp, 1C8h
0x140026182  pop     r15
0x140026184  pop     r14
0x140026186  pop     r13
0x140026188  pop     r12
0x14002618a  pop     rdi
0x14002618b  pop     rsi
0x14002618c  pop     rbx
0x14002618d  pop     rbp
0x14002618e  retn
  ... truncated ...
```
