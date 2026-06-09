# CTxtEdit::TxDraw(ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,tagRECT *,int (*)(ulong),ulong,long)

- ea: `0x180082420`
- end: `0x180082857`
- name: `?TxDraw@CTxtEdit@@UEAAJKJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@2PEBU_RECTL@@3PEAUtagRECT@@P6AHK@ZKJ@Z`
- size: `1079`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, int@<r8d>, void *@<r9>, struct tagDVTARGETDEVICE *, HDC hdc, HDC, const struct _RECTL *, const struct _RECTL *, struct tagRECT *, int (*)(unsigned int), unsigned int, int)`
- caller_count: `0`
- callee_count: `18`
- tags: ``

## callees

- `0x18000b920`
- `0x18002fb90`
- `0x18002fc30`
- `0x18003aeb0`
- `0x18003b054`
- `0x18003d61c`
- `0x180040904`
- `0x1800420a4`
- `0x18004af5c`
- `0x1800541b4`
- `0x18005519c`
- `0x18005bb98`
- `0x18005cc48`
- `0x18008209c`
- `0x1800820e8`
- `0x180082420`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `GDI32!LPtoDP` at `0x1800825ad`
- `GDI32!LPtoDP` at `0x1800825db`
- `GDI32!LPtoDP` at `0x180082609`
- `GDI32!LPtoDP` at `0x1800825ad`
- `GDI32!LPtoDP` at `0x1800825db`
- `GDI32!LPtoDP` at `0x180082609`
- `GDI32!GetDeviceCaps` at `0x18008257a`
- `GDI32!GetDeviceCaps` at `0x18008257a`
- `GDI32!DeleteDC` at `0x1800826d2`
- `GDI32!DeleteDC` at `0x1800826d2`
- `GDI32!RestoreDC` at `0x1800826c4`
- `GDI32!RestoreDC` at `0x1800826c4`
- `GDI32!GetMapMode` at `0x180082564`
- `GDI32!GetMapMode` at `0x180082564`

## pseudocode

```c
__int64 __fastcall CTxtEdit::TxDraw(
        CDisplay **this,
        unsigned int a2,
        int a3,
        void *a4,
        struct tagDVTARGETDEVICE *a5,
        HDC hdc,
        HDC a7,
        struct tagRECT *a8,
        struct tagRECT *a9,
        struct tagRECT *a10,
        int (*a11)(unsigned int),
        unsigned int a12,
        int a13)
{
  HDC v15; // rdi
  struct tagRECT *v16; // r12
  __int64 v17; // rcx
  unsigned int v18; // edi
  HDC v19; // r15
  HDC IC; // rax
  int v21; // r13d
  CDisplay *v22; // rcx
  HDC v23; // r8
  struct tagDVTARGETDEVICE *v24; // r9
  COleObject *v25; // rbx
  CDisplay *v27; // rax
  HDC v28; // r8
  CDisplay *v29; // rbx
  int (*v30)(unsigned int); // [rsp+30h] [rbp-D0h]
  unsigned int v31; // [rsp+38h] [rbp-C8h]
  struct tagRECT *v32; // [rsp+40h] [rbp-C0h]
  struct tagRECT *v33; // [rsp+48h] [rbp-B8h]
  struct tagRECT v36; // [rsp+58h] [rbp-A8h] BYREF
  int v37; // [rsp+68h] [rbp-98h] BYREF
  HDC v38; // [rsp+70h] [rbp-90h]
  __int64 v39; // [rsp+78h] [rbp-88h]
  _QWORD v40[7]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v41[32]; // [rsp+B8h] [rbp-48h] BYREF
  struct tagPOINT pt[2]; // [rsp+D8h] [rbp-28h] BYREF
  struct tagPOINT v43[2]; // [rsp+E8h] [rbp-18h] BYREF
  struct tagPOINT v44[2]; // [rsp+F8h] [rbp-8h] BYREF

  v15 = a7;
  v16 = a8;
  v32 = a9;
  v33 = a10;
  *(_QWORD *)&v36.left = a4;
  CMagellanBMPStateWrap::CMagellanBMPStateWrap((CMagellanBMPStateWrap *)&v37, (struct CTxtEdit *)this, hdc);
  *(_OWORD *)&pt[0].x = 0;
  *(_OWORD *)&v43[0].x = 0;
  *(_OWORD *)&v44[0].x = 0;
  CCallMgr::CCallMgr((CCallMgr *)v41, (struct CTxtEdit *)this);
  if ( !a13 )
  {
    v17 = *((_QWORD *)this[8] + 6);
    if ( v17 )
    {
      *(_DWORD *)(v17 + 16) |= 4u;
      v18 = -2147418113;
      goto LABEL_39;
    }
  }
  if ( a2 != 1 && a2 != 8 )
  {
    v18 = -2147221397;
    goto LABEL_39;
  }
  if ( !a8 && (*((_BYTE *)this + 180) & 8) == 0 || a7 && !a5 )
  {
    v18 = -2147024809;
    goto LABEL_39;
  }
  v19 = 0;
  if ( !a7 && a5 )
  {
    IC = CW32System::CreateIC(
           (unsigned __int16 *)((char *)a5 + a5->tdDriverNameOffset),
           (unsigned __int16 *)((char *)a5 + a5->tdDeviceNameOffset),
           (unsigned __int16 *)((char *)a5 + a5->tdPortNameOffset),
           (const struct _devicemodeW *)((char *)a5 + a5->tdExtDevmodeOffset));
    v19 = IC;
    if ( !IC )
    {
      v18 = -2147467259;
      goto LABEL_39;
    }
    v15 = IC;
  }
  v21 = 0;
  if ( GetMapMode(hdc) != 1 && GetDeviceCaps(hdc, 2) != 5 )
  {
    v21 = 1;
    if ( a8 )
    {
      *(struct tagRECT *)&pt[0].x = *a8;
      v16 = (struct tagRECT *)pt;
      LPtoDP(hdc, pt, 2);
    }
    if ( a9 )
    {
      v32 = (struct tagRECT *)v43;
      *(struct tagRECT *)&v43[0].x = *a9;
      LPtoDP(hdc, v43, 2);
    }
    if ( a10 )
    {
      v33 = (struct tagRECT *)v44;
      *(struct tagRECT *)&v44[0].x = *a10;
      LPtoDP(hdc, v44, 2);
    }
    ConvertDrawDCMapping(hdc);
  }
  v40[0] = 0;
  v40[3] = 0;
  v40[2] = 0;
  v22 = this[8];
  v40[1] = this;
  CDisplay::SetDrawInfo(v22, (struct CDrawInfo *)v40, a2, a3, *(void **)&v36.left, a5, v15);
  if ( !a13 || !a5 )
  {
    v18 = 1;
    if ( v32 )
      goto LABEL_46;
    if ( (*((_BYTE *)this + 180) & 8) != 0 )
    {
      if ( a13 )
        goto LABEL_46;
    }
    else if ( a13 != -1 )
    {
      goto LABEL_46;
    }
    v18 = CDisplay::Draw(this[8], hdc, v23, v16, 0, v33, v30, v31);
    if ( v18 != 1 )
      goto LABEL_29;
LABEL_46:
    v27 = (CDisplay *)(*(__int64 (__fastcall **)(CDisplay *))(*(_QWORD *)this[8] + 376LL))(this[8]);
    v29 = v27;
    if ( v27 )
    {
      *((_DWORD *)v27 + 14) |= 0x80u;
      v18 = CDisplay::Draw(v27, hdc, v28, v16, v32, v33, v30, v31);
      (*(void (__fastcall **)(CDisplay *, __int64))(*(_QWORD *)v29 + 72LL))(v29, 1);
    }
    goto LABEL_29;
  }
  v36 = *v16;
  v18 = CTxtEdit::FormatAndPrint((CTxtEdit *)this, hdc, v15, v24, &v36, v32);
  CTxtEdit::OnFormatRange(this, 0, 0, 0);
LABEL_29:
  CDisplay::ReleaseDrawInfo(this[8]);
  if ( v21 )
    RestoreDC(hdc, -1);
  if ( v19 )
    DeleteDC(v19);
  if ( this[17] )
  {
    if ( ((_BYTE)this[23] & 0xC0) != 0 )
    {
      v25 = (COleObject *)*((_QWORD *)CTxtEdit::GetObjectMgr((CTxtEdit *)this) + 5);
      if ( v25 )
      {
        *((_WORD *)this + 92) ^= (*((_WORD *)this + 92) ^ (((*((_WORD *)this + 92) >> 6) - 1) << 6)) & 0xC0;
        if ( (*((_DWORD *)v25 + 40) & 0x400) != 0 )
        {
          COleObject::FetchObjectExtents(v25);
          *((_DWORD *)v25 + 40) &= ~0x400u;
        }
        COleObject::ResetPosRect(v25, 0);
        COleObject::OnReposition(v25, 0, 0);
      }
    }
  }
LABEL_39:
  CCallMgr::~CCallMgr((CCallMgr *)v41);
  CMagellan::InvertMagellanDownBMP((HGDIOBJ *)(v39 + 24), *(struct CDisplay **)(v39 + 64), v37, v38);
  return v18;
}

```

## disassembly

```asm
0x180082420  push    rbp
0x180082422  push    rbx
0x180082423  push    rsi
0x180082424  push    rdi
0x180082425  push    r12
0x180082427  push    r13
0x180082429  push    r14
0x18008242b  push    r15
0x18008242d  lea     rbp, [rsp-18h]
0x180082432  sub     rsp, 118h
0x180082439  mov     rax, cs:__security_cookie
0x180082440  xor     rax, rsp
0x180082443  mov     [rbp+50h+var_48], rax
0x180082447  mov     rax, [rbp+50h+arg_40]
0x18008244e  mov     r15d, edx
0x180082451  mov     r14, [rbp+50h+hdc]
0x180082458  mov     rsi, rcx
0x18008245b  mov     rbx, [rbp+50h+arg_20]
0x180082462  mov     rdi, [rbp+50h+arg_30]
0x180082469  mov     r12, [rbp+50h+arg_38]
0x180082470  mov     [rsp+150h+var_110], rax
0x180082475  mov     rax, [rbp+50h+arg_48]
0x18008247c  mov     [rsp+150h+var_FC], edx
0x180082480  mov     rdx, rcx; struct CTxtEdit *
0x180082483  mov     [rsp+150h+var_100], r8d
0x180082488  lea     rcx, [rsp+150h+var_E8]; this
0x18008248d  mov     r8, r14; HDC
0x180082490  mov     [rsp+150h+var_108], rax
0x180082495  mov     qword ptr [rsp+150h+var_F8.left], r9
0x18008249a  call    ??0CMagellanBMPStateWrap@@QEAA@AEAVCTxtEdit@@PEAUHDC__@@@Z; CMagellanBMPStateWrap::CMagellanBMPStateWrap(CTxtEdit &,HDC__ *)
0x18008249f  xorps   xmm0, xmm0
0x1800824a2  lea     rcx, [rbp+50h+var_98]; this
0x1800824a6  xorps   xmm1, xmm1
0x1800824a9  mov     rdx, rsi; struct CTxtEdit *
0x1800824ac  movups  xmmword ptr [rbp+50h+pt.x], xmm0
0x1800824b0  movups  xmmword ptr [rbp+50h+var_68.x], xmm1
0x1800824b4  movups  xmmword ptr [rbp+50h+var_58.x], xmm0
0x1800824b8  call    ??0CCallMgr@@QEAA@PEAVCTxtEdit@@@Z; CCallMgr::CCallMgr(CTxtEdit *)
0x1800824bd  cmp     [rbp+50h+arg_60], 0
0x1800824c4  jnz     short loc_1800824E1
0x1800824c6  mov     rax, [rsi+40h]
0x1800824ca  mov     rcx, [rax+30h]
0x1800824ce  test    rcx, rcx
0x1800824d1  jz      short loc_1800824E1
0x1800824d3  or      dword ptr [rcx+10h], 4
0x1800824d7  mov     edi, 8000FFFFh
0x1800824dc  jmp     loc_18008275C
0x1800824e1  cmp     r15d, 1
0x1800824e5  jz      short loc_1800824F7
0x1800824e7  cmp     r15d, 8
0x1800824eb  jz      short loc_1800824F7
0x1800824ed  mov     edi, 8004006Bh
0x1800824f2  jmp     loc_18008275C
0x1800824f7  test    r12, r12
0x1800824fa  jnz     short loc_180082505
0x1800824fc  test    byte ptr [rsi+0B4h], 8
0x180082503  jz      short loc_18008250F
0x180082505  test    rdi, rdi
0x180082508  jz      short loc_180082519
0x18008250a  test    rbx, rbx
0x18008250d  jnz     short loc_180082519
0x18008250f  mov     edi, 80070057h
0x180082514  jmp     loc_18008275C
0x180082519  xor     r15d, r15d
0x18008251c  test    rdi, rdi
0x18008251f  jnz     short loc_18008255E
0x180082521  test    rbx, rbx
0x180082524  jz      short loc_18008255E
0x180082526  movzx   r9d, word ptr [rbx+0Ah]
0x18008252b  movzx   r8d, word ptr [rbx+8]
0x180082530  add     r9, rbx; struct _devicemodeW *
0x180082533  movzx   edx, word ptr [rbx+6]
0x180082537  add     r8, rbx; unsigned __int16 *
0x18008253a  movzx   ecx, word ptr [rbx+4]
0x18008253e  add     rdx, rbx; unsigned __int16 *
0x180082541  add     rcx, rbx; unsigned __int16 *
0x180082544  call    ?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z; CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)
0x180082549  mov     r15, rax
0x18008254c  test    rax, rax
0x18008254f  jnz     short loc_18008255B
0x180082551  mov     edi, 80004005h
0x180082556  jmp     loc_18008275C
0x18008255b  mov     rdi, rax
0x18008255e  mov     rcx, r14; hdc
0x180082561  xor     r13d, r13d
0x180082564  call    cs:__imp_GetMapMode
0x18008256a  cmp     eax, 1
0x18008256d  jz      loc_180082617
0x180082573  lea     edx, [r13+2]; index
0x180082577  mov     rcx, r14; hdc
0x18008257a  call    cs:__imp_GetDeviceCaps
0x180082580  cmp     eax, 5
0x180082583  jz      loc_180082617
0x180082589  mov     r13d, 1
0x18008258f  test    r12, r12
0x180082592  jz      short loc_1800825B3
0x180082594  movups  xmm0, xmmword ptr [r12]
0x180082599  lea     r8d, [r13+1]; c
0x18008259d  mov     rcx, r14; hdc
0x1800825a0  lea     rdx, [rbp+50h+pt]; lppt
0x1800825a4  movdqu  xmmword ptr [rbp+50h+pt.x], xmm0
0x1800825a9  lea     r12, [rbp+50h+pt]
0x1800825ad  call    cs:__imp_LPtoDP
0x1800825b3  mov     rax, [rsp+150h+var_110]
0x1800825b8  test    rax, rax
0x1800825bb  jz      short loc_1800825E1
0x1800825bd  movups  xmm0, xmmword ptr [rax]
0x1800825c0  lea     rax, [rbp+50h+var_68]
0x1800825c4  mov     r8d, 2; c
0x1800825ca  lea     rdx, [rbp+50h+var_68]; lppt
0x1800825ce  mov     [rsp+150h+var_110], rax
0x1800825d3  mov     rcx, r14; hdc
0x1800825d6  movdqu  xmmword ptr [rbp+50h+var_68.x], xmm0
0x1800825db  call    cs:__imp_LPtoDP
0x1800825e1  mov     rax, [rsp+150h+var_108]
0x1800825e6  test    rax, rax
0x1800825e9  jz      short loc_18008260F
0x1800825eb  movups  xmm0, xmmword ptr [rax]
0x1800825ee  lea     rax, [rbp+50h+var_58]
0x1800825f2  mov     r8d, 2; c
0x1800825f8  lea     rdx, [rbp+50h+var_58]; lppt
0x1800825fc  mov     [rsp+150h+var_108], rax
0x180082601  mov     rcx, r14; hdc
0x180082604  movdqu  xmmword ptr [rbp+50h+var_58.x], xmm0
0x180082609  call    cs:__imp_LPtoDP
0x18008260f  mov     rcx, r14; hdc
0x180082612  call    ?ConvertDrawDCMapping@@YAXPEAUHDC__@@@Z; ConvertDrawDCMapping(HDC__ *)
0x180082617  mov     rax, qword ptr [rsp+150h+var_F8.left]
0x18008261c  lea     rdx, [rbp+50h+var_D0]; struct CDrawInfo *
0x180082620  mov     r9d, [rsp+150h+var_100]; int
0x180082625  xor     ecx, ecx
0x180082627  mov     r8d, [rsp+150h+var_FC]; unsigned int
0x18008262c  mov     [rbp+50h+var_D0], rcx
0x180082630  mov     [rbp+50h+var_B8], rcx
0x180082634  mov     [rbp+50h+var_C0], rcx
0x180082638  mov     rcx, [rsi+40h]; this
0x18008263c  mov     [rsp+150h+var_120], rdi; int (*)(unsigned int)
0x180082641  mov     [rsp+150h+var_128], rbx; struct tagDVTARGETDEVICE *
0x180082646  mov     [rbp+50h+var_C8], rsi
0x18008264a  mov     [rsp+150h+var_130], rax; void *
0x18008264f  call    ?SetDrawInfo@CDisplay@@QEAAXPEAVCDrawInfo@@KJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@@Z; CDisplay::SetDrawInfo(CDrawInfo *,ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *)
0x180082654  mov     ecx, [rbp+50h+arg_60]
0x18008265a  test    ecx, ecx
0x18008265c  jz      loc_1800827A3
0x180082662  test    rbx, rbx
0x180082665  jz      loc_1800827A3
0x18008266b  mov     rax, [rsp+150h+var_110]
0x180082670  mov     r8, rdi; HDC
0x180082673  movups  xmm0, xmmword ptr [r12]
0x180082678  mov     [rsp+150h+var_128], rax; struct tagRECT *
0x18008267d  mov     rdx, r14; HDC
0x180082680  lea     rax, [rsp+150h+var_F8]
0x180082685  mov     rcx, rsi; this
0x180082688  mov     [rsp+150h+var_130], rax; struct tagRECT *
0x18008268d  movdqu  xmmword ptr [rsp+150h+var_F8.left], xmm0
0x180082693  call    ?FormatAndPrint@CTxtEdit@@QEAAJPEAUHDC__@@0PEAUtagDVTARGETDEVICE@@PEAUtagRECT@@2@Z; CTxtEdit::FormatAndPrint(HDC__ *,HDC__ *,tagDVTARGETDEVICE *,tagRECT *,tagRECT *)
0x180082698  xor     r8d, r8d
0x18008269b  xor     r9d, r9d
0x18008269e  xor     edx, edx
0x1800826a0  mov     rcx, rsi
0x1800826a3  mov     edi, eax
0x1800826a5  call    ?OnFormatRange@CTxtEdit@@AEAA_JPEAU_formatrange@@USPrintControl@@H@Z; CTxtEdit::OnFormatRange(_formatrange *,SPrintControl,int)
0x1800826aa  mov     r12d, 1
0x1800826b0  mov     rcx, [rsi+40h]; this
0x1800826b4  call    ?ReleaseDrawInfo@CDisplay@@QEAAXXZ; CDisplay::ReleaseDrawInfo(void)
0x1800826b9  test    r13d, r13d
0x1800826bc  jz      short loc_1800826CA
0x1800826be  or      edx, 0FFFFFFFFh; nSavedDC
0x1800826c1  mov     rcx, r14; hdc
0x1800826c4  call    cs:__imp_RestoreDC
0x1800826ca  test    r15, r15
0x1800826cd  jz      short loc_1800826D8
0x1800826cf  mov     rcx, r15; hdc
0x1800826d2  call    cs:__imp_DeleteDC
0x1800826d8  cmp     qword ptr [rsi+88h], 0
0x1800826e0  jz      short loc_18008275C
0x1800826e2  mov     r14d, 0C0h
0x1800826e8  test    [rsi+0B8h], r14b
0x1800826ef  jz      short loc_18008275C
0x1800826f1  mov     rcx, rsi; this
0x1800826f4  call    ?GetObjectMgr@CTxtEdit@@QEAAPEAVCObjectMgr@@XZ; CTxtEdit::GetObjectMgr(void)
0x1800826f9  mov     rbx, [rax+28h]
0x1800826fd  test    rbx, rbx
0x180082700  jz      short loc_18008275C
0x180082702  movzx   eax, word ptr [rsi+0B8h]
0x180082709  movzx   ecx, ax
0x18008270c  shr     cx, 6
0x180082710  sub     cx, r12w
0x180082714  shl     cx, 6
0x180082718  xor     cx, ax
0x18008271b  and     cx, r14w
0x18008271f  xor     cx, ax
0x180082722  mov     [rsi+0B8h], cx
0x180082729  test    dword ptr [rbx+0A0h], 400h
0x180082733  jz      short loc_180082745
0x180082735  mov     rcx, rbx; this
0x180082738  call    ?FetchObjectExtents@COleObject@@QEAAXXZ; COleObject::FetchObjectExtents(void)
0x18008273d  btr     dword ptr [rbx+0A0h], 0Ah
0x180082745  xor     edx, edx; int *
0x180082747  mov     rcx, rbx; this
0x18008274a  call    ?ResetPosRect@COleObject@@QEAAXPEAJ@Z; COleObject::ResetPosRect(long *)
0x18008274f  xor     r8d, r8d; int
0x180082752  xor     edx, edx; int
0x180082754  mov     rcx, rbx; this
0x180082757  call    ?OnReposition@COleObject@@QEAAXJJ@Z; COleObject::OnReposition(long,long)
0x18008275c  lea     rcx, [rbp+50h+var_98]; this
0x180082760  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x180082765  mov     rdx, [rsp+150h+var_D8]
0x18008276a  mov     r9, [rsp+150h+var_E0]; HDC
0x18008276f  mov     r8d, [rsp+150h+var_E8]; int
0x180082774  lea     rcx, [rdx+18h]; this
0x180082778  mov     rdx, [rdx+40h]; struct CDisplay *
0x18008277c  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x180082781  mov     eax, edi
0x180082783  mov     rcx, [rbp+50h+var_48]
0x180082787  xor     rcx, rsp; StackCookie
0x18008278a  call    __security_check_cookie
0x18008278f  add     rsp, 118h
0x180082796  pop     r15
0x180082798  pop     r14
0x18008279a  pop     r13
0x18008279c  pop     r12
0x18008279e  pop     rdi
0x18008279f  pop     rsi
0x1800827a0  pop     rbx
0x1800827a1  pop     rbp
0x1800827a2  retn
0x1800827a3  cmp     [rsp+150h+var_110], 0
0x1800827a9  mov     ebx, 1
0x1800827ae  mov     edi, ebx
0x1800827b0  jnz     short loc_1800827F2
0x1800827b2  test    byte ptr [rsi+0B4h], 8
0x1800827b9  jz      short loc_1800827C1
0x1800827bb  test    ecx, ecx
0x1800827bd  jz      short loc_1800827C6
0x1800827bf  jmp     short loc_1800827F2
0x1800827c1  cmp     ecx, 0FFFFFFFFh
0x1800827c4  jnz     short loc_1800827F2
0x1800827c6  mov     rax, [rsp+150h+var_108]
0x1800827cb  mov     r9, r12; struct tagRECT *
0x1800827ce  mov     rcx, [rsi+40h]; this
0x1800827d2  mov     rdx, r14; hdc
0x1800827d5  mov     [rsp+150h+var_128], rax; struct tagRECT *
0x1800827da  mov     [rsp+150h+var_130], 0; struct tagRECT *
0x1800827e3  call    ?Draw@CDisplay@@QEAAJPEAUHDC__@@0PEBUtagRECT@@11P6AHK@ZK@Z; CDisplay::Draw(HDC__ *,HDC__ *,tagRECT const *,tagRECT const *,tagRECT const *,int (*)(ulong),ulong)
0x1800827e8  mov     edi, eax
0x1800827ea  cmp     eax, ebx
0x1800827ec  jnz     loc_1800826AA
0x1800827f2  mov     rcx, [rsi+40h]
0x1800827f6  mov     rax, [rcx]
0x1800827f9  mov     rax, [rax+178h]
0x180082800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082805  mov     rbx, rax
0x180082808  test    rax, rax
0x18008280b  jz      loc_1800826AA
0x180082811  bts     dword ptr [rax+38h], 7
0x180082816  mov     r9, r12; struct tagRECT *
0x180082819  mov     rax, [rsp+150h+var_108]
0x18008281e  mov     rdx, r14; hdc
0x180082821  mov     [rsp+150h+var_128], rax; struct tagRECT *
0x180082826  mov     rcx, rbx; this
0x180082829  mov     rax, [rsp+150h+var_110]
0x18008282e  mov     [rsp+150h+var_130], rax; struct tagRECT *
0x180082833  call    ?Draw@CDisplay@@QEAAJPEAUHDC__@@0PEBUtagRECT@@11P6AHK@ZK@Z; CDisplay::Draw(HDC__ *,HDC__ *,tagRECT const *,tagRECT const *,tagRECT const *,int (*)(ulong),ulong)
0x180082838  mov     r8, [rbx]
0x18008283b  mov     edi, eax
0x18008283d  mov     r12d, 1
0x180082843  mov     rcx, rbx
0x180082846  mov     edx, r12d
0x180082849  mov     rax, [r8+48h]
0x18008284d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082852  jmp     loc_1800826B0
```
