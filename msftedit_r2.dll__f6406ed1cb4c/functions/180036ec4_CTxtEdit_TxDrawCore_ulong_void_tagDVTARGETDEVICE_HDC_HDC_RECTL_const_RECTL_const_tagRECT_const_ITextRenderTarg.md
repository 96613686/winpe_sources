# CTxtEdit::TxDrawCore(ulong,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,tagRECT const *,ITextRenderTarget *,long)

- ea: `0x180036ec4`
- end: `0x180037a4b`
- name: `?TxDrawCore@CTxtEdit@@AEAAJKPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@2PEBU_RECTL@@3PEBUtagRECT@@PEAUITextRenderTarget@@J@Z`
- size: `2951`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, void *@<r8>, struct tagDVTARGETDEVICE *@<r9>, HDC hdc, HDC, const struct _RECTL *, const struct _RECTL *, const struct tagRECT *, struct ITextRenderTarget *, int)`
- caller_count: `2`
- callee_count: `28`
- tags: `installer_update`

## callers

- `0x1800f0610`
- `0x180106220`

## callees

- `0x18000f358`
- `0x18001aaa0`
- `0x1800363e8`
- `0x1800366b0`
- `0x180036ec4`
- `0x1800382e0`
- `0x1800387b0`
- `0x180044e1c`
- `0x180044ea4`
- `0x18004b674`
- `0x18004d594`
- `0x18004d600`
- `0x18004d658`
- `0x1800584cc`
- `0x18005921c`
- `0x180098490`
- `0x18009cccc`
- `0x1800c9354`
- `0x1800e5128`
- `0x1800f8714`
- `0x1800fcce8`
- `0x180106034`
- `0x18013ce80`
- `0x18016b8d4`
- `0x180174b68`
- `0x180175e44`
- `0x18018b690`
- `0x18027f010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800379ac`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800379ac`
- `ext-ms-win-gdi-dc-create-l1-1-1!CreateICW` at `0x180037694`
- `ext-ms-win-gdi-dc-create-l1-1-1!CreateICW` at `0x180037694`
- `ext-ms-win-gdi-draw-l1-1-0!StretchDIBits` at `0x180037593`
- `ext-ms-win-gdi-draw-l1-1-0!StretchDIBits` at `0x180037593`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800375cf`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800375cf`

## pseudocode

```c
__int64 __fastcall CTxtEdit::TxDrawCore(
        CTxtEdit *this,
        unsigned int a2,
        void *a3,
        struct tagDVTARGETDEVICE *a4,
        HDC hdc,
        HDC a6,
        struct tagRECT *a7,
        struct tagRECT *a8,
        struct tagRECT *a9,
        struct ITextRenderTarget *a10,
        int a11)
{
  __int64 v13; // r13
  _BYTE *v14; // r14
  int v15; // ebx
  const struct CDisplay *v16; // rdx
  CMsgCallBack *v17; // rcx
  __int64 v18; // rcx
  const struct IDpiAccessor *v19; // rdx
  bool v20; // cl
  struct IGraphicContext *v21; // rax
  __int64 v22; // rbx
  int v23; // eax
  HDC v24; // rax
  __int64 v25; // rcx
  void (__fastcall ****v26)(_QWORD, _QWORD **, unsigned int *, __int64 *, char *); // rbx
  void (__fastcall ***v27)(_QWORD, _QWORD **, unsigned int *, __int64 *, char *); // rbx
  struct IGraphicContext *v28; // rcx
  const struct IDpiAccessor *v29; // rbx
  char v30; // al
  __int64 v31; // rdx
  _QWORD *v32; // rbx
  struct tagDVTARGETDEVICE *v33; // r9
  unsigned int v34; // ebx
  __int64 v35; // rbx
  LONG v36; // eax
  __int64 v37; // rax
  void (__fastcall ****v38)(_QWORD, unsigned int *, _QWORD **, __int64 *, char *); // rbx
  void (__fastcall ***v39)(_QWORD, unsigned int *, _QWORD **, __int64 *, char *); // rbx
  struct IGraphicContext *v40; // rcx
  struct tagRECT *v41; // r15
  const struct CDisplay *v42; // rdx
  __int64 v43; // rcx
  __int64 result; // rax
  int top; // r8d
  int v46; // r9d
  int DestHeight; // eax
  int left; // edx
  HDC ICW; // rax
  void (__fastcall **v50)(_QWORD, unsigned int *, _QWORD **, __int64 *, char *); // rax
  struct OTx::ILineLayout *ILineLayout; // rax
  int v52; // r8d
  int v53; // r9d
  CDisplay *v54; // rcx
  CDisplay *v55; // rax
  CDisplay *v56; // r15
  unsigned __int16 v57; // cx
  COleObject *v58; // r15
  _BYTE v59[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int Bits; // [rsp+74h] [rbp-8Ch] BYREF
  struct IGraphicContext *v61; // [rsp+78h] [rbp-88h] BYREF
  char v62; // [rsp+80h] [rbp-80h]
  __int64 v63; // [rsp+84h] [rbp-7Ch] BYREF
  char v64; // [rsp+8Ch] [rbp-74h]
  unsigned int v65; // [rsp+90h] [rbp-70h]
  int v66; // [rsp+94h] [rbp-6Ch]
  _QWORD *v67; // [rsp+98h] [rbp-68h] BYREF
  struct tagRECT v68; // [rsp+A0h] [rbp-60h] BYREF
  HDC v69; // [rsp+B0h] [rbp-50h]
  CDevDesc *v70; // [rsp+B8h] [rbp-48h] BYREF
  struct IGraphicContext *GraphicContext; // [rsp+C0h] [rbp-40h] BYREF
  char v72; // [rsp+C8h] [rbp-38h]
  __int64 v73; // [rsp+CCh] [rbp-34h]
  char v74; // [rsp+D4h] [rbp-2Ch]
  void **v75; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v76; // [rsp+E0h] [rbp-20h]
  struct IGraphicContext *v77; // [rsp+E8h] [rbp-18h] BYREF
  char v78; // [rsp+F0h] [rbp-10h]
  __int64 v79; // [rsp+F4h] [rbp-Ch] BYREF
  char v80; // [rsp+FCh] [rbp-4h]
  struct tagRECT *v81; // [rsp+100h] [rbp+0h]
  struct tagRECT *v82; // [rsp+108h] [rbp+8h]
  char v83[8]; // [rsp+110h] [rbp+10h] BYREF
  struct ITextRenderTarget *v84; // [rsp+118h] [rbp+18h]
  struct tagRECT *v85; // [rsp+120h] [rbp+20h]
  HDC v86; // [rsp+128h] [rbp+28h]
  _QWORD v87[2]; // [rsp+130h] [rbp+30h] BYREF
  struct IGraphicContext *v88; // [rsp+140h] [rbp+40h] BYREF
  char v89; // [rsp+148h] [rbp+48h]
  __int64 v90; // [rsp+14Ch] [rbp+4Ch]
  char v91; // [rsp+154h] [rbp+54h]
  __int16 v92; // [rsp+158h] [rbp+58h]
  __int64 v93; // [rsp+15Ch] [rbp+5Ch]
  int v94; // [rsp+168h] [rbp+68h]
  __int128 v95; // [rsp+170h] [rbp+70h]
  BITMAPINFO bmi; // [rsp+180h] [rbp+80h] BYREF

  v13 = *((_QWORD *)this + 17);
  v82 = a7;
  v81 = a8;
  v85 = a9;
  *(_QWORD *)&v68.left = a3;
  v84 = a10;
  v65 = a2;
  v69 = a6;
  _InterlockedAdd((volatile signed __int32 *)(v13 + 96), 1u);
  if ( *(int *)(*((_QWORD *)this + 17) + 96LL) > 2 )
    goto LABEL_70;
  CCallMgr::CCallMgr((CCallMgr *)v83, this);
  v70 = (CDevDesc *)(*((_QWORD *)this + 17) + 16LL);
  GraphicContext = CreateGraphicContext(
                     (*(_BYTE *)(*(_QWORD *)v70 + 276LL) & 0x40) != 0,
                     *(const struct IDpiAccessor **)(*(_QWORD *)v70 + 568LL),
                     0,
                     0);
  v72 = 0;
  v73 = 0;
  v74 = 0;
  (*(void (__fastcall **)(struct IGraphicContext *, _QWORD))(*(_QWORD *)GraphicContext + 8LL))(
    GraphicContext,
    *((_QWORD *)v70 + 1));
  v14 = (char *)this + 64;
  v72 = *((_BYTE *)v70 + 16);
  v73 = *(_QWORD *)((char *)v70 + 20);
  v74 = *((_BYTE *)v70 + 28);
  if ( hdc && (*v14 & 1) != 0
    || (v15 = 0,
        CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), 0, 0)) )
  {
    v15 = 1;
  }
  v66 = v15;
  *(_WORD *)v14 &= ~1u;
  CWriteLock::CWriteLock(&Bits, 0);
  if ( CLSLock::_cOLSBusy )
  {
    CWriteLock::~CWriteLock((CWriteLock *)&Bits);
    CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), v15, hdc);
    CHDCScope::~CHDCScope((CHDCScope *)&v70);
    CCallMgr::~CCallMgr((CCallMgr *)v83);
    goto LABEL_70;
  }
  CWriteLock::~CWriteLock((CWriteLock *)&Bits);
  if ( (*((_BYTE *)this + 176) & 8) != 0 )
  {
    if ( *((_QWORD *)this + 38) )
    {
      v17 = (CMsgCallBack *)*((_QWORD *)this + 39);
      if ( v17 )
        CMsgCallBack::NotifyEvents(v17, 0x80u);
    }
  }
  if ( !a11 )
  {
    v18 = *(_QWORD *)(*((_QWORD *)this + 17) + 80LL);
    if ( v18 )
    {
      *(_DWORD *)(v18 + 16) |= 4u;
      CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), v15, hdc);
      CDevDesc::SetDC(v70, (const struct CHDC *)&GraphicContext, -1, -1);
      CHDC::~CHDC((CHDC *)&GraphicContext);
      CCallMgr::~CCallMgr((CCallMgr *)v83);
LABEL_70:
      result = 2147549183LL;
      goto LABEL_59;
    }
  }
  if ( hdc && (*((_DWORD *)this + 46) & 0x40000000) != 0 )
  {
    v34 = -2147418113;
LABEL_81:
    CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), v66, hdc);
    CHDCScope::~CHDCScope((CHDCScope *)&v70);
    goto LABEL_58;
  }
  if ( v65 != 1 && v65 != 8 )
  {
    v34 = -2147221397;
    goto LABEL_81;
  }
  if ( v69 && !a4 )
  {
    v34 = -2147024809;
    goto LABEL_81;
  }
  v86 = 0;
  if ( v69 || !a4 )
  {
LABEL_16:
    if ( (*((_DWORD *)this + 46) & 0x40000000) != 0 )
      LS::InvalidateLineCache(*((LS **)this + 17), v16);
    v19 = (const struct IDpiAccessor *)*((_QWORD *)this + 71);
    v20 = (*((_BYTE *)this + 276) & 0x40) != 0;
    v87[0] = 0;
    v87[1] = this;
    v21 = CreateGraphicContext(v20, v19, 0, 0);
    v22 = *((_QWORD *)this + 71);
    v88 = v21;
    v75 = &COverrideDpi::`vftable';
    v89 = 0;
    v90 = 0;
    v91 = 0;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v76 = 0;
    if ( v22 )
    {
      LODWORD(v76) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    else
    {
      LODWORD(v76) = CW32System::_xPerInchScreenDC;
      v23 = CW32System::_yPerInchScreenDC;
    }
    HIDWORD(v76) = v23;
    v24 = v69;
    if ( v69 )
    {
      COverrideDpi::UpdateDpi((COverrideDpi *)&v75, v69);
      v24 = v69;
    }
    v25 = *((_QWORD *)this + 32);
    if ( v25 && (v26 = *(void (__fastcall *****)(_QWORD, _QWORD **, unsigned int *, __int64 *, char *))(v25 + 80)) != 0 )
      v27 = *v26;
    else
      v27 = 0;
    v28 = CreateGraphicContext((*((_BYTE *)this + 276) & 0x40) != 0, (const struct IDpiAccessor *)&v75, v24, 0);
    v77 = v28;
    v78 = 0;
    v79 = 0;
    v80 = 0;
    if ( v27 )
    {
      LODWORD(v67) = 0;
      Bits = 0;
      v80 = 1;
      (**v27)(v27, &v67, &Bits, &v79, (char *)&v79 + 4);
      v28 = v77;
    }
    v67 = (_QWORD *)*((_QWORD *)this + 17);
    v29 = *(const struct IDpiAccessor **)(v67[2] + 568LL);
    v30 = (*(__int64 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)v28 + 80LL))(v28);
    v61 = CreateGraphicContext(v30, v29, 0, 0);
    v62 = 0;
    v63 = 0;
    v64 = 0;
    (*(void (__fastcall **)(struct IGraphicContext *, struct IGraphicContext *))(*(_QWORD *)v61 + 8LL))(v61, v77);
    v62 = v78;
    v63 = v79;
    v64 = v80;
    if ( !v80 && !(*(unsigned __int8 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)v61 + 24LL))(v61) )
    {
      v31 = v67[11];
      if ( v31 )
        CHDC::SetDC((CHDC *)&v61, (const struct CHDC *)(v31 + 8));
    }
    v32 = (_QWORD *)v67[8];
    if ( !v32 )
    {
      v67[8] = v87;
      v32 = v87;
    }
    v32[9] = a4;
    ++*(_DWORD *)v32;
    ++*((_DWORD *)v32 + 1);
    *((_DWORD *)v32 + 14) = v65;
    v32[8] = *(_QWORD *)&v68.left;
    if ( v64 || (*(unsigned __int8 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)v61 + 24LL))(v61) )
      CDevDesc::SetDC((CDevDesc *)(v32 + 1), (const struct CHDC *)&v61, -1, -1);
    CHDC::~CHDC((CHDC *)&v61);
    if ( a11 && a4 )
    {
      v68 = *v82;
      v34 = CTxtEdit::FormatAndPrint(this, hdc, v69, v33, &v68, v81);
      CTxtEdit::OnFormatRange(this, 0, 0, 0);
LABEL_50:
      if ( (*((_DWORD *)this + 46) & 0x40000000) != 0 )
        LS::InvalidateLineCache(*((LS **)this + 17), v42);
      CDisplay::ReleaseDrawInfo(*((CDisplay **)this + 17));
      if ( v86 )
        DeleteDC(v86);
      if ( (unsigned int)CTxtStory::GetObjectCount(*(CTxtStory **)(*((_QWORD *)this + 17) + 72LL)) )
      {
        v57 = *((_WORD *)this + 138);
        if ( (v57 & 0x300) != 0 )
        {
          v58 = *(COleObject **)(*((_QWORD *)this + 30) + 40LL);
          if ( v58 )
          {
            *((_WORD *)this + 138) = v57 ^ (v57 ^ ((HIBYTE(v57) - 1) << 8)) & 0x300;
            if ( (*((_WORD *)v58 + 77) & 0x200) != 0 )
            {
              COleObject::FetchObjectExtents(v58, 0);
              *((_WORD *)v58 + 77) &= ~0x200u;
            }
            COleObject::OnReposition(v58);
          }
        }
      }
      v43 = *((_QWORD *)this + 15);
      if ( v43 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 16LL))(v43, v65);
      CHDC::~CHDC((CHDC *)&v77);
      v75 = &IDpiAccessor::`vftable';
      CHDC::~CHDC((CHDC *)&v88);
      CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), v66, hdc);
      CDevDesc::SetDC(v70, (const struct CHDC *)&GraphicContext, -1, -1);
      CHDC::~CHDC((CHDC *)&GraphicContext);
      goto LABEL_58;
    }
    v34 = 1;
    if ( !v81 )
    {
      LOBYTE(v67) = (*((_DWORD *)this + 44) & 8) != 0;
      if ( (_BYTE)v67 )
      {
        if ( !a11 )
          goto LABEL_40;
      }
      else if ( a11 == -1 )
      {
LABEL_40:
        v35 = *((_QWORD *)this + 71);
        *(_QWORD *)&v68.left = &COverrideDpi::`vftable';
        *(_QWORD *)&v68.right = 0;
        if ( v35 )
        {
          v68.right = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
          v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        else
        {
          v68.right = CW32System::_xPerInchScreenDC;
          v36 = CW32System::_yPerInchScreenDC;
        }
        v68.bottom = v36;
        if ( hdc && GetDeviceCaps(hdc, 2) == 2 )
          COverrideDpi::UpdateDpi((COverrideDpi *)&v68, hdc);
        v37 = *((_QWORD *)this + 32);
        if ( v37
          && (v38 = *(void (__fastcall *****)(_QWORD, unsigned int *, _QWORD **, __int64 *, char *))(v37 + 80)) != 0 )
        {
          v39 = *v38;
        }
        else
        {
          v39 = 0;
        }
        v61 = CreateGraphicContext((*((_BYTE *)this + 276) & 0x40) != 0, (const struct IDpiAccessor *)&v68, hdc, v84);
        v40 = v61;
        v62 = 0;
        v63 = 0;
        v64 = 0;
        if ( v39 )
        {
          v64 = 1;
          v50 = *v39;
          Bits = 0;
          LODWORD(v67) = 0;
          (*v50)(v39, &Bits, &v67, &v63, (char *)&v63 + 4);
          v40 = v61;
        }
        v59[0] = (*((_DWORD *)this + 70) & 0x100000) != 0;
        (*(void (__fastcall **)(struct IGraphicContext *, _BYTE *))(*(_QWORD *)v40 + 16LL))(v40, v59);
        v41 = v82;
        v34 = CDisplay::Draw(*((CDisplay **)this + 17), (const struct CHDC *)&v61, v82, 0, v85);
        if ( !v34 && (*((_DWORD *)this + 72) & 0x10000) != 0 && v41 && hdc )
        {
          top = v41->top;
          v46 = v41->right - v41->left;
          Bits = 0;
          DestHeight = v41->bottom - top;
          left = v41->left;
          memset(&bmi.bmiHeader.biSizeImage, 0, 24);
          bmi.bmiHeader.biSize = 40;
          bmi.bmiHeader.biWidth = 1;
          bmi.bmiHeader.biHeight = 1;
          *(_QWORD *)&bmi.bmiHeader.biPlanes = 2097153;
          HIBYTE(Bits) = -1;
          StretchDIBits(hdc, left, top, v46, DestHeight, 0, 0, 1, 1, &Bits, &bmi, 0, 0xEE0086u);
        }
        CHDC::~CHDC((CHDC *)&v61);
        if ( v34 != 1 )
          goto LABEL_50;
      }
    }
    ILineLayout = CTxtEdit::GetILineLayout(this, 0);
    CHDC::CHDC(
      (CHDC *)&v61,
      (*((_BYTE *)this + 276) & 0x40) != 0,
      *((const struct IDpiAccessor **)this + 71),
      ILineLayout,
      hdc,
      v84);
    v59[0] = (*((_DWORD *)this + 70) & 0x100000) != 0;
    (*(void (__fastcall **)(struct IGraphicContext *, _BYTE *))(*(_QWORD *)v61 + 16LL))(v61, v59);
    if ( (unsigned int)CHDC::GetTechnology((CHDC *)&v61) == 5 )
    {
      Bits = 1;
    }
    else
    {
      v54 = (CDisplay *)*((_QWORD *)this + 17);
      Bits = 0;
      CDisplay::SetDC(v54, (const struct CHDC *)&v61, v52, v53);
    }
    v55 = (CDisplay *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 472LL))(*((_QWORD *)this + 17));
    v56 = v55;
    if ( v55 )
    {
      *((_DWORD *)v55 + 29) |= 0x40u;
      v34 = CDisplay::Draw(v55, (const struct CHDC *)&v61, v82, v81, v85);
      (*(void (__fastcall **)(CDisplay *, __int64))(*(_QWORD *)v56 + 80LL))(v56, 1);
    }
    if ( !Bits )
      CDevDesc::ResetDCW((CDevDesc *)(*((_QWORD *)this + 17) + 16LL));
    CHDC::~CHDC((CHDC *)&v61);
    goto LABEL_50;
  }
  ICW = CreateICW(
          (LPCWSTR)((char *)a4 + a4->tdDriverNameOffset),
          (LPCWSTR)((char *)a4 + a4->tdDeviceNameOffset),
          (LPCWSTR)((char *)a4 + a4->tdPortNameOffset),
          (const DEVMODEW *)((char *)a4 + a4->tdExtDevmodeOffset));
  v86 = ICW;
  if ( ICW )
  {
    v69 = ICW;
    goto LABEL_16;
  }
  CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), v15, hdc);
  CDevDesc::SetDC(v70, (const struct CHDC *)&GraphicContext, -1, -1);
  CHDC::~CHDC((CHDC *)&GraphicContext);
  v34 = -2147467259;
LABEL_58:
  CCallMgr::~CCallMgr((CCallMgr *)v83);
  result = v34;
LABEL_59:
  _InterlockedAdd((volatile signed __int32 *)(v13 + 96), 0xFFFFFFFF);
  return result;
}

```

## disassembly

```asm
0x180036ec4  mov     [rsp-8+arg_10], rbx
0x180036ec9  push    rbp
0x180036eca  push    rsi
0x180036ecb  push    rdi
0x180036ecc  push    r12
0x180036ece  push    r13
0x180036ed0  push    r14
0x180036ed2  push    r15
0x180036ed4  lea     rbp, [rsp-0C0h]
0x180036edc  sub     rsp, 1C0h
0x180036ee3  mov     rax, cs:__security_cookie
0x180036eea  xor     rax, rsp
0x180036eed  mov     [rbp+0F0h+var_40], rax
0x180036ef4  mov     rax, [rbp+0F0h+arg_30]
0x180036efb  mov     r15, r9
0x180036efe  mov     r12, [rbp+0F0h+hdc]
0x180036f05  mov     rdi, rcx
0x180036f08  mov     r13, [rcx+88h]
0x180036f0f  mov     esi, 1
0x180036f14  mov     [rbp+0F0h+var_E8], rax
0x180036f18  mov     rax, [rbp+0F0h+arg_38]
0x180036f1f  mov     [rbp+0F0h+var_F0], rax
0x180036f23  mov     rax, [rbp+0F0h+arg_40]
0x180036f2a  mov     [rbp+0F0h+var_D0], rax
0x180036f2e  mov     rax, [rbp+0F0h+arg_48]
0x180036f35  mov     qword ptr [rbp+0F0h+var_150.left], r8
0x180036f39  mov     r8, [rbp+0F0h+arg_28]
0x180036f40  mov     [rbp+0F0h+var_D8], rax
0x180036f44  mov     [rbp+0F0h+var_160], edx
0x180036f47  mov     [rbp+0F0h+var_140], r8
0x180036f4b  lock add [r13+60h], esi
0x180036f50  mov     rax, [rcx+88h]
0x180036f57  cmp     dword ptr [rax+60h], 2
0x180036f5b  jg      loc_180037610
0x180036f61  mov     rdx, rcx; struct CTxtEdit *
0x180036f64  lea     rcx, [rbp+0F0h+var_E0]; this
0x180036f68  call    ??0CCallMgr@@QEAA@PEAVCTxtEdit@@@Z; CCallMgr::CCallMgr(CTxtEdit *)
0x180036f6d  mov     rbx, [rdi+88h]
0x180036f74  xor     r9d, r9d; struct ITextRenderTarget *
0x180036f77  add     rbx, 10h
0x180036f7b  xor     r8d, r8d; HDC
0x180036f7e  mov     [rbp+0F0h+var_138], rbx
0x180036f82  mov     rdx, [rbx]
0x180036f85  mov     cl, [rdx+114h]
0x180036f8b  mov     rdx, [rdx+238h]; struct IDpiAccessor *
0x180036f92  shr     cl, 6
0x180036f95  and     cl, sil; bool
0x180036f98  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x180036f9d  mov     [rbp+0F0h+var_130], rax
0x180036fa1  xor     esi, esi
0x180036fa3  mov     [rbp+0F0h+var_128], sil
0x180036fa7  mov     r8, rax
0x180036faa  mov     [rbp+0F0h+var_124], rsi
0x180036fae  mov     [rbp+0F0h+var_11C], sil
0x180036fb2  mov     rcx, [rax]
0x180036fb5  mov     rdx, [rbx+8]
0x180036fb9  mov     rax, [rcx+8]
0x180036fbd  mov     rcx, r8
0x180036fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fc5  mov     al, [rbx+10h]
0x180036fc8  lea     r14, [rdi+40h]
0x180036fcc  mov     [rbp+0F0h+var_128], al
0x180036fcf  mov     eax, [rbx+14h]
0x180036fd2  mov     dword ptr [rbp+0F0h+var_124], eax
0x180036fd5  mov     eax, [rbx+18h]
0x180036fd8  mov     dword ptr [rbp+0F0h+var_124+4], eax
0x180036fdb  mov     al, [rbx+1Ch]
0x180036fde  mov     [rbp+0F0h+var_11C], al
0x180036fe1  test    r12, r12
0x180036fe4  jnz     loc_1800375A4
0x180036fea  mov     rdx, [rdi+88h]; struct CDisplay *
0x180036ff1  xor     r9d, r9d; HDC
0x180036ff4  xor     r8d, r8d; int
0x180036ff7  mov     rcx, r14; this
0x180036ffa  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x180036fff  mov     ebx, esi
0x180037001  test    eax, eax
0x180037003  jnz     loc_1800375AE
0x180037009  mov     eax, 0FFFEh
0x18003700e  mov     [rbp+0F0h+var_15C], ebx
0x180037011  and     [r14], ax
0x180037015  lea     rcx, [rsp+1F0h+Bits]
0x18003701a  xor     edx, edx
0x18003701c  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x180037021  cmp     cs:?_cOLSBusy@CLSLock@@1HA, esi; int CLSLock::_cOLSBusy
0x180037027  lea     rcx, [rsp+1F0h+Bits]; this
0x18003702c  jnz     loc_1800376FC
0x180037032  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180037037  test    byte ptr [rdi+0B0h], 8
0x18003703e  jz      short loc_180037059
0x180037040  cmp     [rdi+130h], rsi
0x180037047  jz      short loc_180037059
0x180037049  mov     rcx, [rdi+138h]; this
0x180037050  test    rcx, rcx
0x180037053  jnz     loc_1800375B8
0x180037059  cmp     [rbp+0F0h+arg_50], esi
0x18003705f  jnz     short loc_180037075
0x180037061  mov     rax, [rdi+88h]
0x180037068  mov     rcx, [rax+50h]
0x18003706c  test    rcx, rcx
0x18003706f  jnz     loc_18003761D
0x180037075  or      esi, 0FFFFFFFFh
0x180037078  test    r12, r12
0x18003707b  jnz     loc_1800375F5
0x180037081  mov     eax, [rbp+0F0h+var_160]
0x180037084  cmp     eax, 1
0x180037087  jnz     loc_18003772D
0x18003708d  mov     rax, [rbp+0F0h+var_140]
0x180037091  test    rax, rax
0x180037094  jnz     loc_18003773D
0x18003709a  mov     [rbp+0F0h+var_C8], 0
0x1800370a2  test    rax, rax
0x1800370a5  jnz     short loc_1800370B0
0x1800370a7  test    r15, r15
0x1800370aa  jnz     loc_180037674
0x1800370b0  mov     eax, [rdi+0B8h]
0x1800370b6  mov     ebx, 1
0x1800370bb  shr     eax, 1Eh
0x1800370be  test    bl, al
0x1800370c0  jnz     loc_180037778
0x1800370c6  mov     cl, [rdi+114h]
0x1800370cc  xor     r9d, r9d; struct ITextRenderTarget *
0x1800370cf  mov     rdx, [rdi+238h]; struct IDpiAccessor *
0x1800370d6  xor     r8d, r8d; HDC
0x1800370d9  shr     cl, 6
0x1800370dc  and     cl, bl; bool
0x1800370de  mov     [rbp+0F0h+var_C0], 0
0x1800370e6  mov     [rbp+0F0h+var_B8], rdi
0x1800370ea  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x1800370ef  mov     rbx, [rdi+238h]
0x1800370f6  xor     edx, edx
0x1800370f8  mov     [rbp+0F0h+var_B0], rax
0x1800370fc  lea     rax, ??_7COverrideDpi@@6B@; const COverrideDpi::`vftable'
0x180037103  mov     [rbp+0F0h+var_118], rax
0x180037107  xorps   xmm0, xmm0
0x18003710a  mov     [rbp+0F0h+var_A8], dl
0x18003710d  mov     [rbp+0F0h+var_A4], rdx
0x180037111  mov     [rbp+0F0h+var_9C], dl
0x180037114  mov     [rbp+0F0h+var_98], dx
0x180037118  mov     [rbp+0F0h+var_94], rdx
0x18003711c  mov     [rbp+0F0h+var_88], edx
0x18003711f  movdqa  [rbp+0F0h+var_80], xmm0
0x180037124  mov     [rbp+0F0h+var_110], rdx
0x180037128  test    rbx, rbx
0x18003712b  jz      loc_180037660
0x180037131  mov     rax, [rbx]
0x180037134  mov     rcx, rbx
0x180037137  mov     rax, [rax+8]
0x18003713b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037140  mov     dword ptr [rbp+0F0h+var_110], eax
0x180037143  mov     rcx, rbx
0x180037146  mov     rax, [rbx]
0x180037149  mov     rax, [rax+10h]
0x18003714d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037152  xor     edx, edx
0x180037154  mov     dword ptr [rbp+0F0h+var_110+4], eax
0x180037157  mov     rax, [rbp+0F0h+var_140]
0x18003715b  test    rax, rax
0x18003715e  jnz     loc_180037789
0x180037164  mov     rcx, [rdi+100h]
0x18003716b  test    rcx, rcx
0x18003716e  jz      short loc_18003717D
0x180037170  mov     rbx, [rcx+50h]
0x180037174  test    rbx, rbx
0x180037177  jnz     loc_1800377A0
0x18003717d  mov     rbx, rdx
0x180037180  mov     cl, [rdi+114h]
0x180037186  lea     rdx, [rbp+0F0h+var_118]; struct IDpiAccessor *
0x18003718a  shr     cl, 6
0x18003718d  xor     r9d, r9d; struct ITextRenderTarget *
0x180037190  and     cl, 1; bool
0x180037193  mov     r8, rax; HDC
0x180037196  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x18003719b  mov     rcx, rax
0x18003719e  mov     [rbp+0F0h+var_108], rax
0x1800371a2  xor     eax, eax
0x1800371a4  mov     [rbp+0F0h+var_100], al
0x1800371a7  mov     [rbp+0F0h+var_FC], rax
0x1800371ab  mov     [rbp+0F0h+var_F4], al
0x1800371ae  test    rbx, rbx
0x1800371b1  jnz     loc_1800377A8
0x1800371b7  mov     rax, [rdi+88h]
0x1800371be  mov     [rbp+0F0h+var_158], rax
0x1800371c2  mov     rax, [rax+10h]
0x1800371c6  mov     rbx, [rax+238h]
0x1800371cd  mov     rax, [rcx]
0x1800371d0  mov     rax, [rax+50h]
0x1800371d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371d9  xor     r9d, r9d; struct ITextRenderTarget *
0x1800371dc  xor     r8d, r8d; HDC
0x1800371df  mov     rdx, rbx; struct IDpiAccessor *
0x1800371e2  mov     cl, al; bool
0x1800371e4  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x1800371e9  mov     rdx, [rbp+0F0h+var_108]
0x1800371ed  xor     ebx, ebx
0x1800371ef  mov     [rsp+1F0h+var_178], rax
0x1800371f4  mov     r8, rax
0x1800371f7  mov     [rbp+0F0h+var_170], bl
0x1800371fa  mov     [rbp+0F0h+var_16C], rbx
0x1800371fe  mov     [rbp+0F0h+var_164], bl
0x180037201  mov     rcx, [rax]
0x180037204  mov     rax, [rcx+8]
0x180037208  mov     rcx, r8
0x18003720b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037210  mov     al, [rbp+0F0h+var_100]
0x180037213  mov     [rbp+0F0h+var_170], al
0x180037216  mov     eax, dword ptr [rbp+0F0h+var_FC]
0x180037219  mov     dword ptr [rbp+0F0h+var_16C], eax
0x18003721c  mov     eax, dword ptr [rbp+0F0h+var_FC+4]
0x18003721f  mov     dword ptr [rbp+0F0h+var_16C+4], eax
0x180037222  mov     al, [rbp+0F0h+var_F4]
0x180037225  mov     [rbp+0F0h+var_164], al
0x180037228  test    al, al
0x18003722a  jnz     short loc_180037252
0x18003722c  mov     rcx, [rsp+1F0h+var_178]
0x180037231  mov     rax, [rcx]
0x180037234  mov     rax, [rax+18h]
0x180037238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003723d  test    al, al
0x18003723f  jnz     short loc_180037252
0x180037241  mov     rdx, [rbp+0F0h+var_158]
0x180037245  mov     rdx, [rdx+58h]
0x180037249  test    rdx, rdx
0x18003724c  jnz     loc_1800377E0
0x180037252  mov     rdx, [rbp+0F0h+var_158]
0x180037256  mov     rbx, [rdx+40h]
0x18003725a  test    rbx, rbx
0x18003725d  jnz     short loc_18003726B
0x18003725f  lea     rax, [rbp+0F0h+var_C0]
0x180037263  mov     [rdx+40h], rax
0x180037267  lea     rbx, [rbp+0F0h+var_C0]
0x18003726b  mov     eax, 1
0x180037270  mov     [rbx+48h], r15
0x180037274  add     [rbx], eax
0x180037276  add     [rbx+4], eax
0x180037279  mov     eax, [rbp+0F0h+var_160]
0x18003727c  mov     [rbx+38h], eax
0x18003727f  mov     rax, qword ptr [rbp+0F0h+var_150.left]
0x180037283  mov     [rbx+40h], rax
0x180037287  cmp     [rbp+0F0h+var_164], 0
0x18003728b  jnz     short loc_1800372A2
0x18003728d  mov     rcx, [rsp+1F0h+var_178]
0x180037292  mov     rax, [rcx]
0x180037295  mov     rax, [rax+18h]
0x180037299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003729e  test    al, al
0x1800372a0  jz      short loc_1800372B6
0x1800372a2  lea     rcx, [rbx+8]; this
0x1800372a6  mov     r9d, esi; int
0x1800372a9  mov     r8d, esi; int
0x1800372ac  lea     rdx, [rsp+1F0h+var_178]; struct CHDC *
0x1800372b1  call    ?SetDC@CDevDesc@@QEAAHAEBVCHDC@@JJ@Z; CDevDesc::SetDC(CHDC const &,long,long)
0x1800372b6  lea     rcx, [rsp+1F0h+var_178]; this
0x1800372bb  call    ??1CHDC@@QEAA@XZ; CHDC::~CHDC(void)
0x1800372c0  mov     ecx, [rbp+0F0h+arg_50]
0x1800372c6  test    ecx, ecx
0x1800372c8  jnz     loc_1800377F3
0x1800372ce  xor     r15d, r15d
0x1800372d1  mov     edx, 1
0x1800372d6  mov     ebx, edx
0x1800372d8  cmp     [rbp+0F0h+var_F0], r15
0x1800372dc  jnz     loc_180037890
0x1800372e2  mov     eax, [rdi+0B0h]
0x1800372e8  shr     eax, 3
0x1800372eb  and     al, dl
0x1800372ed  mov     byte ptr [rbp+0F0h+var_158], al
0x1800372f0  jz      loc_180037841
0x1800372f6  test    ecx, ecx
0x1800372f8  jnz     loc_180037890
0x1800372fe  mov     rbx, [rdi+238h]
0x180037305  lea     rax, ??_7COverrideDpi@@6B@; const COverrideDpi::`vftable'
0x18003730c  mov     qword ptr [rbp+0F0h+var_150.left], rax
0x180037310  mov     qword ptr [rbp+0F0h+var_150.right], r15
0x180037314  test    rbx, rbx
0x180037317  jz      loc_1800376E8
0x18003731d  mov     rax, [rbx]
0x180037320  mov     rcx, rbx
0x180037323  mov     rax, [rax+8]
0x180037327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003732c  mov     [rbp+0F0h+var_150.right], eax
0x18003732f  mov     rcx, rbx
0x180037332  mov     rax, [rbx]
0x180037335  mov     rax, [rax+10h]
0x180037339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003733e  mov     [rbp+0F0h+var_150.bottom], eax
0x180037341  test    r12, r12
0x180037344  jnz     loc_1800375C7
0x18003734a  mov     rax, [rdi+100h]
0x180037351  test    rax, rax
0x180037354  jz      short loc_180037363
0x180037356  mov     rbx, [rax+50h]
0x18003735a  test    rbx, rbx
0x18003735d  jnz     loc_18003784A
0x180037363  mov     rbx, r15
0x180037366  mov     cl, [rdi+114h]
0x18003736c  lea     rdx, [rbp+0F0h+var_150]; struct IDpiAccessor *
0x180037370  mov     r9, [rbp+0F0h+var_D8]; struct ITextRenderTarget *
0x180037374  mov     r8, r12; HDC
0x180037377  shr     cl, 6
0x18003737a  and     cl, 1; bool
  ... truncated ...
```
