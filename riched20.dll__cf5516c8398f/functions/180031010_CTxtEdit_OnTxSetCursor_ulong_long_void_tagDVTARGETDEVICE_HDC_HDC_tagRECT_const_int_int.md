# CTxtEdit::OnTxSetCursor(ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,tagRECT const *,int,int)

- ea: `0x180031010`
- end: `0x180031578`
- name: `?OnTxSetCursor@CTxtEdit@@UEAAJKJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@2PEBUtagRECT@@HH@Z`
- size: `1384`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, int@<r8d>, void *@<r9>, struct tagDVTARGETDEVICE *, HDC hdc, HDC, const struct tagRECT *, int, int)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x18002fbe0`
- `0x18002fc30`
- `0x180031010`
- `0x180031974`
- `0x1800319c0`
- `0x180031a38`
- `0x180033060`
- `0x18003a4d0`
- `0x18003d61c`
- `0x1800404ac`
- `0x180040904`
- `0x1800420a4`
- `0x180049cf4`
- `0x180052fe0`
- `0x180056b70`
- `0x180080140`
- `0x18008209c`
- `0x18008e100`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `USER32!GetCursorPos` at `0x1800312f6`
- `USER32!GetCursorPos` at `0x1800312f6`
- `USER32!PtInRect` at `0x180031240`
- `USER32!PtInRect` at `0x180031240`
- `GDI32!LPtoDP` at `0x18003113f`
- `GDI32!LPtoDP` at `0x18003113f`
- `GDI32!GetDeviceCaps` at `0x180031123`
- `GDI32!GetDeviceCaps` at `0x180031123`
- `GDI32!DeleteDC` at `0x1800311bd`
- `GDI32!DeleteDC` at `0x1800311bd`
- `GDI32!RestoreDC` at `0x1800311ac`
- `GDI32!RestoreDC` at `0x1800311ac`
- `GDI32!GetMapMode` at `0x180031110`
- `GDI32!GetMapMode` at `0x180031110`

## pseudocode

```c
__int64 __fastcall CTxtEdit::OnTxSetCursor(
        CTxtEdit *this,
        LONG a2,
        int a3,
        struct tagPOINT a4,
        struct tagDVTARGETDEVICE *a5,
        HDC hdc,
        HDC a7,
        const struct tagRECT *a8,
        unsigned int a9,
        unsigned int a10)
{
  const struct tagRECT *v10; // r14
  int v11; // r13d
  HDC v13; // r12
  HDC v14; // rsi
  HDC IC; // rax
  HDC v16; // rdx
  struct CTxtSelection *Sel; // r12
  HICON v18; // rsi
  int v19; // ecx
  int v20; // eax
  bool v21; // zf
  int v22; // r8d
  int v23; // r8d
  int AcpFromCp; // eax
  __int64 v25; // rcx
  int v26; // ebx
  unsigned int v27; // ebx
  __int64 v28; // rax
  COleObject *v29; // rcx
  unsigned __int16 *v30; // rax
  HICON SizeCursor; // rax
  POINT v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+58h] [rbp-A8h]
  int v35; // [rsp+5Ch] [rbp-A4h] BYREF
  struct tagPOINT Point; // [rsp+60h] [rbp-A0h] BYREF
  int v37; // [rsp+68h] [rbp-98h] BYREF
  int v38; // [rsp+6Ch] [rbp-94h] BYREF
  HWND v39[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v40[2]; // [rsp+80h] [rbp-80h] BYREF
  int v41; // [rsp+A0h] [rbp-60h]
  _OWORD v42[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v43[7]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v44[112]; // [rsp+100h] [rbp+0h] BYREF
  tagPOINT pt[2]; // [rsp+170h] [rbp+70h] BYREF

  v10 = a8;
  v11 = 0;
  v13 = a7;
  Point = a4;
  v34 = a3;
  v33.x = a2;
  memset(v42, 0, sizeof(v42));
  if ( this )
  {
    *((_QWORD *)&v42[0] + 1) = *((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = v42;
    *(_QWORD *)&v42[0] = this;
    CCallMgr::NotifyEnterContext((CCallMgr *)v42);
  }
  v35 = 0;
  v43[0] = 0;
  v43[3] = 0;
  v43[1] = this;
  v43[2] = 0;
  *(_OWORD *)&pt[0].x = 0;
  if ( !a8 )
  {
    if ( (*((_BYTE *)this + 180) & 8) != 0 )
    {
      (*(void (__fastcall **)(_QWORD, tagPOINT *))(**((_QWORD **)this + 6) + 192LL))(*((_QWORD *)this + 6), pt);
      v10 = (const struct tagRECT *)pt;
      goto LABEL_17;
    }
    goto LABEL_44;
  }
  v14 = 0;
  if ( a7 || !a5 )
    goto LABEL_8;
  IC = CW32System::CreateIC(
         (unsigned __int16 *)((char *)a5 + a5->tdDriverNameOffset),
         (unsigned __int16 *)((char *)a5 + a5->tdDeviceNameOffset),
         (unsigned __int16 *)((char *)a5 + a5->tdPortNameOffset),
         (const struct _devicemodeW *)((char *)a5 + a5->tdExtDevmodeOffset));
  v14 = IC;
  if ( !IC )
  {
LABEL_44:
    v27 = -2147024809;
    goto LABEL_45;
  }
  v13 = IC;
LABEL_8:
  *(struct tagRECT *)&pt[0].x = *a8;
  if ( GetMapMode(hdc) != 1 && GetDeviceCaps(hdc, 2) != 5 )
  {
    v11 = 1;
    LPtoDP(hdc, pt, 2);
    v10 = (const struct tagRECT *)pt;
    ConvertDrawDCMapping(hdc);
  }
  CDevDesc::SetDC((CDevDesc *)(*((_QWORD *)this + 8) + 16LL), hdc, -1, -1);
  CDisplay::SetDrawInfo(*((CDisplay **)this + 8), (struct CDrawInfo *)v43, v33.x, v34, *(void **)&Point, a5, v13);
  CDisplay::ReDrawOnRectChange(*((CDisplay **)this + 8), v16, v10);
  if ( v11 )
    RestoreDC(hdc, -1);
  if ( v14 )
    DeleteDC(v14);
LABEL_17:
  v34 = 0;
  Sel = CTxtEdit::GetSel(this);
  v18 = CTxtEdit::_hcurArrow;
  v33 = (POINT)__PAIR64__(a10, a9);
  if ( !PtInRect((const RECT *)pt, (POINT)__PAIR64__(a10, a9)) )
    goto LABEL_41;
  (*(void (__fastcall **)(_QWORD, unsigned __int64, const struct tagRECT *, _QWORD, _QWORD, _DWORD, int *, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 232LL))(
    *((_QWORD *)this + 8),
    __PAIR64__(a10, a9),
    v10,
    0,
    0,
    0,
    &v35,
    0,
    0);
  v19 = v35;
  if ( v35 == 3 )
  {
    v18 = CTxtEdit::_hcurSelBar;
    goto LABEL_41;
  }
  if ( v35 != 7 )
  {
    if ( ((v35 - 1) & 0xFFFFFFFC) == 0 )
      goto LABEL_41;
    if ( Sel )
    {
      if ( (unsigned int)CTxtSelection::PointInSel(Sel, __PAIR64__(a10, a9), v10, 0)
        && (*((_DWORD *)this + 45) & 0x1000) == 0 )
      {
LABEL_37:
        v28 = *((_QWORD *)this + 17);
        if ( v28 )
        {
          v29 = *(COleObject **)(v28 + 48);
          if ( v29 )
          {
            v30 = COleObject::CheckForHandleHit(v29, &v33);
            SizeCursor = CW32System::GetSizeCursor(v30);
            if ( SizeCursor )
              v18 = SizeCursor;
          }
        }
        goto LABEL_41;
      }
      v19 = v35;
    }
    v18 = CTxtEdit::_hcurIBeam;
    v34 = 1;
    if ( v19 == 8 )
      v18 = CTxtEdit::_hcurItalic;
    goto LABEL_37;
  }
  if ( (*((_DWORD *)this + 44) & 0x4000000) != 0 && (*((_BYTE *)this + 180) & 8) != 0 )
  {
    v37 = 0;
    Point.x = (unsigned __int16)a9;
    Point.y = ((unsigned __int16)a9 | (unsigned __int64)((unsigned __int16)a10 << 16)) >> 16;
    GetCursorPos(&Point);
    if ( (*(unsigned int (__fastcall **)(_QWORD, struct tagPOINT *))(**((_QWORD **)this + 6) + 160LL))(
           *((_QWORD *)this + 6),
           &Point) )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD, struct tagPOINT, _QWORD, _QWORD, _QWORD, _DWORD, int *, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 232LL))(
              *((_QWORD *)this + 8),
              Point,
              0,
              0,
              0,
              0,
              &v37,
              0,
              0);
      if ( v37 == 7 )
      {
        v38 = 0;
        v33.x = 0;
        v41 = 0;
        *(_OWORD *)v39 = 0;
        memset(v40, 0, sizeof(v40));
        CTxtRange::CTxtRange((CTxtRange *)v44, this, v20, 0);
        v21 = (*((_DWORD *)this + 45) & 0x8000000) == 0;
        *(_OWORD *)v39 = 0;
        v41 = 0;
        memset(v40, 0, sizeof(v40));
        if ( !v21 )
        {
          (*(void (__fastcall **)(char *, HWND *))(*((_QWORD *)this + 2) + 304LL))((char *)this + 16, v39);
          v39[1] = (HWND)(int)CW32System::GetWindowLong(v39[0], -12);
        }
        LODWORD(v40[0]) = 1803;
        CTxtRange::Expander((CTxtRange *)v44, -2147483616, 1, 0, &v38, (int *)&v33);
        DWORD2(v40[0]) = 32;
        *(_QWORD *)((char *)v40 + 12) = 0;
        *(_QWORD *)((char *)&v40[1] + 4) = (unsigned __int16)a9 | (unsigned __int64)((unsigned __int16)a10 << 16);
        HIDWORD(v40[1]) = CTxtEdit::GetAcpFromCp(this, v38, v22);
        AcpFromCp = CTxtEdit::GetAcpFromCp(this, v33.x, v23);
        v25 = *((_QWORD *)this + 6);
        v41 = AcpFromCp;
        v26 = (*(__int64 (__fastcall **)(__int64, __int64, HWND *))(*(_QWORD *)v25 + 304LL))(v25, 1803, v39);
        CTxtRange::~CTxtRange((CTxtRange *)v44);
        if ( v26 == 1 )
        {
          v27 = 0;
          goto LABEL_45;
        }
      }
    }
  }
  v18 = CTxtEdit::_hcurHand;
LABEL_41:
  (*(void (__fastcall **)(_QWORD, HICON, _QWORD))(**((_QWORD **)this + 6) + 152LL))(
    *((_QWORD *)this + 6),
    v18,
    (unsigned int)v34);
  if ( hdc )
    CDevDesc::SetDC((CDevDesc *)(*((_QWORD *)this + 8) + 16LL), 0, -1, -1);
  CDisplay::ReleaseDrawInfo(*((CDisplay **)this + 8));
  v27 = 0;
LABEL_45:
  CCallMgr::~CCallMgr((CCallMgr *)v42);
  return v27;
}

```

## disassembly

```asm
0x180031010  push    rbp
0x180031012  push    rbx
0x180031013  push    rsi
0x180031014  push    rdi
0x180031015  push    r12
0x180031017  push    r13
0x180031019  push    r14
0x18003101b  push    r15
0x18003101d  lea     rbp, [rsp-98h]
0x180031025  sub     rsp, 198h
0x18003102c  mov     rax, cs:__security_cookie
0x180031033  xor     rax, rsp
0x180031036  mov     [rbp+0D0h+var_50], rax
0x18003103d  mov     r14, [rbp+0D0h+arg_38]
0x180031044  xorps   xmm0, xmm0
0x180031047  mov     rbx, [rbp+0D0h+arg_20]
0x18003104e  xor     r13d, r13d
0x180031051  mov     r15, [rbp+0D0h+hdc]
0x180031058  mov     rdi, rcx
0x18003105b  mov     r12, [rbp+0D0h+arg_30]
0x180031062  mov     qword ptr [rsp+1D0h+Point.x], r9
0x180031067  mov     [rsp+1D0h+var_178], r8d
0x18003106c  mov     [rsp+1D0h+var_180.x], edx
0x180031070  movups  [rbp+0D0h+var_128], xmm0
0x180031074  movups  [rbp+0D0h+var_118], xmm0
0x180031078  test    rcx, rcx
0x18003107b  jz      short loc_1800310A0
0x18003107d  mov     rax, [rcx+90h]
0x180031084  mov     qword ptr [rbp+0D0h+var_128+8], rax
0x180031088  lea     rax, [rbp+0D0h+var_128]
0x18003108c  mov     [rcx+90h], rax
0x180031093  mov     qword ptr [rbp+0D0h+var_128], rcx
0x180031097  lea     rcx, [rbp+0D0h+var_128]; this
0x18003109b  call    ?NotifyEnterContext@CCallMgr@@AEAAXXZ; CCallMgr::NotifyEnterContext(void)
0x1800310a0  mov     [rsp+1D0h+var_174], r13d
0x1800310a5  xorps   xmm0, xmm0
0x1800310a8  mov     [rbp+0D0h+var_108], r13
0x1800310ac  mov     [rbp+0D0h+var_F0], r13
0x1800310b0  mov     [rbp+0D0h+var_100], rdi
0x1800310b4  mov     [rbp+0D0h+var_F8], r13
0x1800310b8  movups  xmmword ptr [rbp+0D0h+pt.x], xmm0
0x1800310bc  test    r14, r14
0x1800310bf  jz      loc_1800311C5
0x1800310c5  mov     rsi, r13
0x1800310c8  test    r12, r12
0x1800310cb  jnz     short loc_180031104
0x1800310cd  test    rbx, rbx
0x1800310d0  jz      short loc_180031104
0x1800310d2  movzx   r9d, word ptr [rbx+0Ah]
0x1800310d7  movzx   r8d, word ptr [rbx+8]
0x1800310dc  add     r9, rbx; struct _devicemodeW *
0x1800310df  movzx   edx, word ptr [rbx+6]
0x1800310e3  add     r8, rbx; unsigned __int16 *
0x1800310e6  movzx   ecx, word ptr [rbx+4]
0x1800310ea  add     rdx, rbx; unsigned __int16 *
0x1800310ed  add     rcx, rbx; unsigned __int16 *
0x1800310f0  call    ?CreateIC@CW32System@@SAPEAUHDC__@@PEBG00PEBU_devicemodeW@@@Z; CW32System::CreateIC(ushort const *,ushort const *,ushort const *,_devicemodeW const *)
0x1800310f5  mov     rsi, rax
0x1800310f8  test    rax, rax
0x1800310fb  jz      loc_180031545
0x180031101  mov     r12, rax
0x180031104  movups  xmm0, xmmword ptr [r14]
0x180031108  mov     rcx, r15; hdc
0x18003110b  movdqu  xmmword ptr [rbp+0D0h+pt.x], xmm0
0x180031110  call    cs:__imp_GetMapMode
0x180031116  cmp     eax, 1
0x180031119  jz      short loc_180031151
0x18003111b  mov     edx, 2; index
0x180031120  mov     rcx, r15; hdc
0x180031123  call    cs:__imp_GetDeviceCaps
0x180031129  cmp     eax, 5
0x18003112c  jz      short loc_180031151
0x18003112e  mov     r13d, 1
0x180031134  lea     rdx, [rbp+0D0h+pt]; lppt
0x180031138  mov     rcx, r15; hdc
0x18003113b  lea     r8d, [r13+1]; c
0x18003113f  call    cs:__imp_LPtoDP
0x180031145  mov     rcx, r15; hdc
0x180031148  lea     r14, [rbp+0D0h+pt]
0x18003114c  call    ?ConvertDrawDCMapping@@YAXPEAUHDC__@@@Z; ConvertDrawDCMapping(HDC__ *)
0x180031151  mov     rcx, [rdi+40h]
0x180031155  or      eax, 0FFFFFFFFh
0x180031158  add     rcx, 10h; this
0x18003115c  mov     r9d, eax; int
0x18003115f  mov     r8d, eax; int
0x180031162  mov     rdx, r15; HDC
0x180031165  call    ?SetDC@CDevDesc@@QEAAHPEAUHDC__@@JJ@Z; CDevDesc::SetDC(HDC__ *,long,long)
0x18003116a  mov     rax, qword ptr [rsp+1D0h+Point.x]
0x18003116f  lea     rdx, [rbp+0D0h+var_108]; struct CDrawInfo *
0x180031173  mov     r9d, [rsp+1D0h+var_178]; int
0x180031178  mov     r8d, [rsp+1D0h+var_180.x]; unsigned int
0x18003117d  mov     rcx, [rdi+40h]; this
0x180031181  mov     [rsp+1D0h+var_1A0], r12; HDC
0x180031186  mov     [rsp+1D0h+var_1A8], rbx; struct tagDVTARGETDEVICE *
0x18003118b  mov     [rsp+1D0h+var_1B0], rax; void *
0x180031190  call    ?SetDrawInfo@CDisplay@@QEAAXPEAVCDrawInfo@@KJPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@@Z; CDisplay::SetDrawInfo(CDrawInfo *,ulong,long,void *,tagDVTARGETDEVICE *,HDC__ *)
0x180031195  mov     rcx, [rdi+40h]; this
0x180031199  mov     r8, r14; struct tagRECT *
0x18003119c  call    ?ReDrawOnRectChange@CDisplay@@QEAAXPEAUHDC__@@PEBUtagRECT@@@Z; CDisplay::ReDrawOnRectChange(HDC__ *,tagRECT const *)
0x1800311a1  test    r13d, r13d
0x1800311a4  jz      short loc_1800311B2
0x1800311a6  or      edx, 0FFFFFFFFh; nSavedDC
0x1800311a9  mov     rcx, r15; hdc
0x1800311ac  call    cs:__imp_RestoreDC
0x1800311b2  xor     r13d, r13d
0x1800311b5  test    rsi, rsi
0x1800311b8  jz      short loc_1800311ED
0x1800311ba  mov     rcx, rsi; hdc
0x1800311bd  call    cs:__imp_DeleteDC
0x1800311c3  jmp     short loc_1800311ED
0x1800311c5  test    byte ptr [rdi+0B4h], 8
0x1800311cc  jz      loc_180031545
0x1800311d2  mov     rcx, [rdi+30h]
0x1800311d6  lea     rdx, [rbp+0D0h+pt]
0x1800311da  mov     rax, [rcx]
0x1800311dd  mov     rax, [rax+0C0h]
0x1800311e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311e9  lea     r14, [rbp+0D0h+pt]
0x1800311ed  mov     rcx, rdi; this
0x1800311f0  mov     [rsp+1D0h+var_178], r13d
0x1800311f5  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x1800311fa  movzx   ecx, word ptr [rbp+0D0h+arg_40+2]
0x180031201  mov     r12, rax
0x180031204  mov     eax, [rbp+0D0h+arg_48]
0x18003120a  mov     r13d, [rbp+120h]
0x180031211  mov     rsi, cs:?_hcurArrow@CTxtEdit@@2PEAUHICON__@@EA; HICON__ * CTxtEdit::_hcurArrow
0x180031218  mov     word ptr [rsp+1D0h+var_180.x+2], cx
0x18003121d  movzx   ecx, word ptr [rbp+0D0h+arg_48+2]
0x180031224  mov     word ptr [rsp+1D0h+var_180.y+2], cx
0x180031229  lea     rcx, [rbp+0D0h+pt]; lprc
0x18003122d  mov     word ptr [rsp+1D0h+var_180.y], ax
0x180031232  mov     word ptr [rsp+1D0h+var_180.x], r13w
0x180031238  mov     rbx, qword ptr [rsp+1D0h+var_180.x]
0x18003123d  mov     rdx, rbx; pt
0x180031240  call    cs:__imp_PtInRect
0x180031246  xor     r8d, r8d
0x180031249  test    eax, eax
0x18003124b  jz      loc_180031500
0x180031251  mov     rcx, [rdi+40h]
0x180031255  lea     rdx, [rsp+1D0h+var_174]
0x18003125a  mov     [rsp+1D0h+var_190], r8
0x18003125f  xor     r9d, r9d
0x180031262  mov     [rsp+1D0h+var_198], r8
0x180031267  mov     [rsp+1D0h+var_1A0], rdx
0x18003126c  mov     rdx, rbx
0x18003126f  mov     rax, [rcx]
0x180031272  mov     dword ptr [rsp+1D0h+var_1A8], r8d
0x180031277  mov     [rsp+1D0h+var_1B0], r8
0x18003127c  mov     r8, r14
0x18003127f  mov     rax, [rax+0E8h]
0x180031286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003128b  mov     ecx, [rsp+1D0h+var_174]
0x18003128f  cmp     ecx, 3
0x180031292  jnz     short loc_1800312A0
0x180031294  mov     rsi, cs:?_hcurSelBar@CTxtEdit@@2PEAUHICON__@@EA; HICON__ * CTxtEdit::_hcurSelBar
0x18003129b  jmp     loc_180031500
0x1800312a0  cmp     ecx, 7
0x1800312a3  jnz     loc_18003147F
0x1800312a9  test    dword ptr [rdi+0B0h], 4000000h
0x1800312b3  jz      loc_180031473
0x1800312b9  test    byte ptr [rdi+0B4h], 8
0x1800312c0  jz      loc_180031473
0x1800312c6  movzx   ebx, word ptr [rbp+0D0h+arg_48]
0x1800312cd  lea     rcx, [rsp+1D0h+Point]; lpPoint
0x1800312d2  movzx   eax, r13w
0x1800312d6  xor     r14d, r14d
0x1800312d9  shl     ebx, 10h
0x1800312dc  or      rbx, rax
0x1800312df  mov     [rsp+1D0h+var_168], r14d
0x1800312e4  movzx   eax, bx
0x1800312e7  mov     [rsp+1D0h+Point.x], eax
0x1800312eb  mov     rax, rbx
0x1800312ee  shr     rax, 10h
0x1800312f2  mov     [rsp+1D0h+Point.y], eax
0x1800312f6  call    cs:__imp_GetCursorPos
0x1800312fc  mov     rcx, [rdi+30h]
0x180031300  lea     rdx, [rsp+1D0h+Point]
0x180031305  mov     rax, [rcx]
0x180031308  mov     rax, [rax+0A0h]
0x18003130f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031314  test    eax, eax
0x180031316  jz      loc_180031473
0x18003131c  mov     rcx, [rdi+40h]
0x180031320  lea     rdx, [rsp+1D0h+var_168]
0x180031325  mov     [rsp+1D0h+var_190], r14
0x18003132a  xor     r9d, r9d
0x18003132d  mov     [rsp+1D0h+var_198], r14
0x180031332  xor     r8d, r8d
0x180031335  mov     [rsp+1D0h+var_1A0], rdx
0x18003133a  mov     rax, [rcx]
0x18003133d  mov     rdx, qword ptr [rsp+1D0h+Point.x]
0x180031342  mov     dword ptr [rsp+1D0h+var_1A8], r14d
0x180031347  mov     [rsp+1D0h+var_1B0], r14
0x18003134c  mov     rax, [rax+0E8h]
0x180031353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031358  cmp     [rsp+1D0h+var_168], 7
0x18003135d  jnz     loc_180031473
0x180031363  xorps   xmm0, xmm0
0x180031366  mov     [rsp+1D0h+var_164], r14d
0x18003136b  xor     ecx, ecx
0x18003136d  mov     [rsp+1D0h+var_180.x], r14d
0x180031372  mov     [rbp+0D0h+var_130], ecx
0x180031375  xor     r9d, r9d; int
0x180031378  lea     rcx, [rbp+0D0h+var_D0]; this
0x18003137c  mov     r8d, eax; int
0x18003137f  mov     rdx, rdi; struct CTxtEdit *
0x180031382  movups  xmmword ptr [rsp+1D0h+var_160], xmm0
0x180031387  movups  [rbp+0D0h+var_150], xmm0
0x18003138b  movups  [rbp+0D0h+var_140], xmm0
0x18003138f  call    ??0CTxtRange@@QEAA@PEAVCTxtEdit@@JJ@Z; CTxtRange::CTxtRange(CTxtEdit *,long,long)
0x180031394  xorps   xmm0, xmm0
0x180031397  xor     eax, eax
0x180031399  test    dword ptr [rdi+0B4h], 8000000h
0x1800313a3  movups  xmmword ptr [rsp+1D0h+var_160], xmm0
0x1800313a8  mov     [rbp+0D0h+var_130], eax
0x1800313ab  movups  [rbp+0D0h+var_150], xmm0
0x1800313af  movups  [rbp+0D0h+var_140], xmm0
0x1800313b3  jz      short loc_1800313E3
0x1800313b5  lea     rcx, [rdi+10h]
0x1800313b9  mov     rax, [rcx]
0x1800313bc  lea     rdx, [rsp+1D0h+var_160]
0x1800313c1  mov     rax, [rax+130h]
0x1800313c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313cd  mov     rcx, [rsp+1D0h+var_160]; HWND
0x1800313d2  lea     edx, [r14-0Ch]; int
0x1800313d6  call    ?GetWindowLong@CW32System@@SAJPEAUHWND__@@H@Z; CW32System::GetWindowLong(HWND__ *,int)
0x1800313db  movsxd  rcx, eax
0x1800313de  mov     [rsp+1D0h+var_160+8], rcx
0x1800313e3  xor     r9d, r9d; int *
0x1800313e6  lea     rax, [rsp+1D0h+var_180]
0x1800313eb  mov     [rsp+1D0h+var_1A8], rax; int *
0x1800313f0  lea     rcx, [rbp+0D0h+var_D0]; this
0x1800313f4  lea     rax, [rsp+1D0h+var_164]
0x1800313f9  mov     esi, 70Bh
0x1800313fe  mov     edx, 80000020h; int
0x180031403  mov     dword ptr [rbp+0D0h+var_150], esi
0x180031406  lea     r8d, [r9+1]; int
0x18003140a  mov     [rsp+1D0h+var_1B0], rax; int *
0x18003140f  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x180031414  mov     edx, [rsp+1D0h+var_164]; int
0x180031418  mov     rcx, rdi; this
0x18003141b  mov     dword ptr [rbp+0D0h+var_150+8], 20h ; ' '
0x180031422  mov     qword ptr [rbp+0D0h+var_150+0Ch], r14
0x180031426  mov     qword ptr [rbp+0D0h+var_140+4], rbx
0x18003142a  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x18003142f  mov     edx, [rsp+1D0h+var_180.x]; int
0x180031433  mov     rcx, rdi; this
0x180031436  mov     dword ptr [rbp+0D0h+var_140+0Ch], eax
0x180031439  call    ?GetAcpFromCp@CTxtEdit@@QEAAJJH@Z; CTxtEdit::GetAcpFromCp(long,int)
0x18003143e  mov     rcx, [rdi+30h]
0x180031442  lea     r8, [rsp+1D0h+var_160]
0x180031447  mov     [rbp+0D0h+var_130], eax
0x18003144a  mov     edx, esi
0x18003144c  mov     rax, [rcx]
0x18003144f  mov     rax, [rax+130h]
0x180031456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003145b  lea     rcx, [rbp+0D0h+var_D0]; this
0x18003145f  mov     ebx, eax
0x180031461  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x180031466  cmp     ebx, 1
0x180031469  jnz     short loc_180031473
0x18003146b  mov     ebx, r14d
0x18003146e  jmp     loc_18003154A
0x180031473  mov     rsi, cs:?_hcurHand@CTxtEdit@@2PEAUHICON__@@EA; HICON__ * CTxtEdit::_hcurHand
0x18003147a  jmp     loc_180031500
0x18003147f  lea     eax, [rcx-1]
0x180031482  test    eax, 0FFFFFFFCh
0x180031487  jnz     short loc_18003148E
0x180031489  cmp     ecx, 3
0x18003148c  jnz     short loc_180031500
0x18003148e  test    r12, r12
0x180031491  jz      short loc_1800314B8
0x180031493  xor     r9d, r9d
0x180031496  mov     r8, r14
0x180031499  mov     rdx, rbx
0x18003149c  mov     rcx, r12
0x18003149f  call    ?PointInSel@CTxtSelection@@QEBAHUtagPOINT@@PEBUtagRECT@@W4HITTEST@@@Z; CTxtSelection::PointInSel(tagPOINT,tagRECT const *,HITTEST)
0x1800314a4  test    eax, eax
0x1800314a6  jz      short loc_1800314B4
0x1800314a8  test    dword ptr [rdi+0B4h], 1000h
0x1800314b2  jz      short loc_1800314D2
0x1800314b4  mov     ecx, [rsp+1D0h+var_174]
0x1800314b8  mov     rsi, cs:?_hcurIBeam@CTxtEdit@@2PEAUHICON__@@EA; HICON__ * CTxtEdit::_hcurIBeam
0x1800314bf  cmp     ecx, 8
0x1800314c2  mov     [rsp+1D0h+var_178], 1
0x1800314ca  cmovz   rsi, cs:?_hcurItalic@CTxtEdit@@2PEAUHICON__@@EA; HICON__ * CTxtEdit::_hcurItalic
0x1800314d2  mov     rax, [rdi+88h]
0x1800314d9  test    rax, rax
0x1800314dc  jz      short loc_180031500
0x1800314de  mov     rcx, [rax+30h]; this
0x1800314e2  test    rcx, rcx
0x1800314e5  jz      short loc_180031500
0x1800314e7  lea     rdx, [rsp+1D0h+var_180]; struct tagPOINT *
0x1800314ec  call    ?CheckForHandleHit@COleObject@@QEAAPEAGAEBUtagPOINT@@@Z; COleObject::CheckForHandleHit(tagPOINT const &)
0x1800314f1  mov     rcx, rax; unsigned __int16 *
0x1800314f4  call    ?GetSizeCursor@CW32System@@SAPEAUHICON__@@PEAG@Z; CW32System::GetSizeCursor(ushort *)
0x1800314f9  test    rax, rax
0x1800314fc  cmovnz  rsi, rax
0x180031500  mov     rcx, [rdi+30h]
0x180031504  mov     rdx, rsi
  ... truncated ...
```
