# CMFCColorPickerCtrl::DrawItem(tagDRAWITEMSTRUCT *)

- ea: `0x18002ef00`
- end: `0x18002f3f4`
- name: `?DrawItem@CMFCColorPickerCtrl@@MEAAXPEAUtagDRAWITEMSTRUCT@@@Z`
- size: `1268`
- prototype: `void __fastcall(CMFCColorPickerCtrl *this, tagDRAWITEMSTRUCT *lpDIS)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x18001d090`
- `0x18002d5e0`
- `0x18002daa0`
- `0x18002dd90`
- `0x18002df40`
- `0x18002e220`
- `0x18002ef00`
- `0x18002f680`
- `0x18006cab0`
- `0x18006df10`
- `0x180231d70`
- `0x1802aee30`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b25f0`
- `0x1802b2690`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!CopyRect` at `0x18002efb3`
- `USER32!CopyRect` at `0x18002efb3`
- `GDI32!SelectPalette` at `0x18002ef6d`
- `GDI32!SelectPalette` at `0x18002f076`
- `GDI32!SelectPalette` at `0x18002f341`
- `GDI32!SelectPalette` at `0x18002f37e`
- `GDI32!SelectPalette` at `0x18002ef6d`
- `GDI32!SelectPalette` at `0x18002f076`
- `GDI32!SelectPalette` at `0x18002f341`
- `GDI32!SelectPalette` at `0x18002f37e`
- `GDI32!DeleteDC` at `0x18002f3c0`
- `GDI32!DeleteDC` at `0x18002f3c0`
- `GDI32!BitBlt` at `0x18002f32b`
- `GDI32!BitBlt` at `0x18002f32b`
- `GDI32!CreateCompatibleBitmap` at `0x18002f021`
- `GDI32!CreateCompatibleBitmap` at `0x18002f021`
- `GDI32!RealizePalette` at `0x18002ef86`
- `GDI32!RealizePalette` at `0x18002f08b`
- `GDI32!RealizePalette` at `0x18002ef86`
- `GDI32!RealizePalette` at `0x18002f08b`
- `GDI32!GetTextColor` at `0x18002f223`
- `GDI32!GetTextColor` at `0x18002f223`
- `GDI32!SelectObject` at `0x18002f04a`
- `GDI32!SelectObject` at `0x18002f360`
- `GDI32!SelectObject` at `0x18002f04a`
- `GDI32!SelectObject` at `0x18002f360`
- `GDI32!CreateCompatibleDC` at `0x18002efee`
- `GDI32!CreateCompatibleDC` at `0x18002efee`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CMFCColorPickerCtrl::DrawItem(CMFCColorPickerCtrl *this, tagDRAWITEMSTRUCT *lpDIS)
{
  CDC *p_dcMem; // r14
  CPalette *m_pPalette; // rax
  HPALETTE m_hObject; // rdx
  HDC *p_m_hDC; // r12
  HPALETTE v8; // rax
  CGdiObject *v9; // rdi
  CGdiObject *v10; // r15
  CGdiObject *v11; // r13
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v14; // rax
  CPalette *v15; // rdx
  HPALETTE v16; // rax
  CMFCColorPickerCtrl::COLORTYPE m_COLORTYPE; // ecx
  __int32 v18; // ecx
  __int32 v19; // ecx
  __int32 v20; // ecx
  void (__fastcall *DrawCursor)(CMFCColorPickerCtrl *, CDC *, const CRect *); // rbx
  CRect *CursorRect; // rax
  int m_bInitialized; // eax
  unsigned int clrBtnHilite; // ebx
  void (__fastcall *v25)(CMFCColorPickerCtrl *, CDC *, const CRect *); // rbx
  CRect *v26; // rax
  COLORREF TextColor; // edi
  int cy; // ebx
  int v29; // eax
  unsigned int clrBtnDkShadow; // r8d
  unsigned int v31; // ebx
  HPALETTE v32; // rax
  void *v33; // rdx
  HGDIOBJ v34; // rax
  HPALETTE v35; // rax
  HDC v36; // rax
  int v37; // [rsp+50h] [rbp-49h]
  CDC dcMem; // [rsp+58h] [rbp-41h] BYREF
  CBitmap bmp; // [rsp+78h] [rbp-21h] BYREF
  CRect rectClient; // [rsp+88h] [rbp-11h] BYREF
  CRect result; // [rsp+98h] [rbp-1h] BYREF
  CRect rectClip; // [rsp+A8h] [rbp+Fh] BYREF

  if ( !lpDIS || lpDIS->CtlType != 4 )
    AfxThrowInvalidArgException();
  p_dcMem = CDC::FromHandle(lpDIS->hDC);
  m_pPalette = this->m_pPalette;
  if ( m_pPalette )
    m_hObject = (HPALETTE)m_pPalette->m_hObject;
  else
    m_hObject = 0;
  p_m_hDC = &p_dcMem->m_hDC;
  v8 = SelectPalette(p_dcMem->m_hDC, m_hObject, 0);
  v9 = CGdiObject::FromHandle(v8);
  *(_QWORD *)&result.left = v9;
  RealizePalette(p_dcMem->m_hDC);
  rectClip = 0;
  p_dcMem->GetClipBox(p_dcMem, &rectClip);
  CopyRect(&rectClient, &lpDIS->rcItem);
  v37 = 0;
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcMem.m_hDC, 0, 20);
  bmp.m_hObject = 0;
  bmp.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  v10 = 0;
  v11 = 0;
  CompatibleDC = CreateCompatibleDC(p_dcMem->m_hDC);
  if ( CDC::Attach(&dcMem, CompatibleDC) )
  {
    CompatibleBitmap = CreateCompatibleBitmap(
                         *p_m_hDC,
                         rectClient.right - rectClient.left,
                         rectClient.bottom - rectClient.top);
    if ( CGdiObject::Attach(&bmp, CompatibleBitmap) )
    {
      v37 = 1;
      v14 = SelectObject(dcMem.m_hDC, bmp.m_hObject);
      v10 = CGdiObject::FromHandle(v14);
      p_dcMem = &dcMem;
      v15 = this->m_pPalette;
      if ( v15 )
        v15 = (CPalette *)v15->m_hObject;
      v16 = SelectPalette(dcMem.m_hDC, (HPALETTE)v15, 0);
      v11 = CGdiObject::FromHandle(v16);
      RealizePalette(dcMem.m_hDC);
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      AFX_GLOBAL_DATA::DrawParentBackground(&afxGlobalData, this, &dcMem, 0);
    }
  }
  m_COLORTYPE = this->m_COLORTYPE;
  if ( m_COLORTYPE )
  {
    v18 = m_COLORTYPE - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
        {
          if ( v20 != 1 )
            goto LABEL_34;
          CMFCColorPickerCtrl::CreateHexGreyScaleBar(this);
        }
        else
        {
          CMFCColorPickerCtrl::CreateHexagon(this);
        }
        CMFCColorPickerCtrl::DrawHex(this, p_dcMem);
      }
      else
      {
        CMFCColorPickerCtrl::DrawPicker(this, p_dcMem);
        DrawCursor = this->DrawCursor;
        CursorRect = CMFCColorPickerCtrl::GetCursorRect(this, &result);
        DrawCursor(this, p_dcMem, CursorRect);
        m_bInitialized = afxGlobalData.m_bInitialized;
        if ( !afxGlobalData.m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          m_bInitialized = 1;
          afxGlobalData.m_bInitialized = 1;
        }
        clrBtnHilite = afxGlobalData.clrBtnHilite;
        if ( !m_bInitialized )
        {
          AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
          afxGlobalData.m_bInitialized = 1;
        }
        CDC::Draw3dRect(p_dcMem, &rectClient, afxGlobalData.clrBtnDkShadow, clrBtnHilite);
      }
    }
    else
    {
      CMFCColorPickerCtrl::DrawLuminanceBar(this, p_dcMem);
      if ( !afxGlobalData.m_bInitialized )
      {
        AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
        afxGlobalData.m_bInitialized = 1;
      }
      result.left = this->m_nLumBarWidth;
      result.top = 0;
      result.right = rectClient.right - result.left - rectClient.left;
      result.bottom = rectClient.bottom - rectClient.top;
      AFX_GLOBAL_DATA::DrawParentBackground(&afxGlobalData, this, p_dcMem, &result);
      v25 = this->DrawCursor;
      v26 = CMFCColorPickerCtrl::GetCursorRect(this, &result);
      v25(this, p_dcMem, v26);
    }
  }
  else
  {
    TextColor = GetTextColor(p_dcMem->m_hAttribDC);
    cy = (rectClient.bottom - rectClient.top) / 2;
    CDC::FillSolidRect(p_dcMem, 0, 0, rectClient.right - rectClient.left, cy, this->m_colorNew);
    CDC::FillSolidRect(p_dcMem, 0, cy, rectClient.right - rectClient.left, cy, this->m_colorOriginal);
    p_dcMem->SetTextColor(p_dcMem, TextColor);
    v29 = afxGlobalData.m_bInitialized;
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      v29 = 1;
      afxGlobalData.m_bInitialized = 1;
    }
    clrBtnDkShadow = afxGlobalData.clrBtnDkShadow;
    v31 = afxGlobalData.clrBtnDkShadow;
    if ( !v29 )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
      clrBtnDkShadow = afxGlobalData.clrBtnDkShadow;
    }
    CDC::Draw3dRect(p_dcMem, &rectClient, clrBtnDkShadow, v31);
    v9 = *(CGdiObject **)&result.left;
  }
LABEL_34:
  if ( v37 )
  {
    BitBlt(
      *p_m_hDC,
      rectClip.left,
      rectClip.top,
      rectClip.right - rectClip.left,
      rectClip.bottom - rectClip.top,
      dcMem.m_hDC,
      rectClip.left,
      rectClip.top,
      0xCC0020u);
    if ( v11 )
    {
      v32 = SelectPalette(dcMem.m_hDC, (HPALETTE)v11->m_hObject, 0);
      CGdiObject::FromHandle(v32);
    }
    if ( v10 )
      v33 = v10->m_hObject;
    else
      v33 = 0;
    v34 = SelectObject(dcMem.m_hDC, v33);
    CGdiObject::FromHandle(v34);
  }
  if ( v9 )
  {
    v35 = SelectPalette(*p_m_hDC, (HPALETTE)v9->m_hObject, 0);
    CGdiObject::FromHandle(v35);
  }
  bmp.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&bmp);
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( dcMem.m_hDC )
  {
    v36 = CDC::Detach(&dcMem);
    DeleteDC(v36);
  }
}

```

## disassembly

```asm
0x18002ef00  mov     [rsp-8+arg_10], rbx
0x18002ef05  push    rbp
0x18002ef06  push    rsi
0x18002ef07  push    rdi
0x18002ef08  push    r12
0x18002ef0a  push    r13
0x18002ef0c  push    r14
0x18002ef0e  push    r15
0x18002ef10  lea     rbp, [rsp-27h]
0x18002ef15  sub     rsp, 0C0h
0x18002ef1c  mov     rax, cs:__security_cookie
0x18002ef23  xor     rax, rsp
0x18002ef26  mov     [rbp+57h+var_38], rax
0x18002ef2a  mov     rbx, lpDIS
0x18002ef2d  mov     rsi, this
0x18002ef30  test    lpDIS, lpDIS
0x18002ef33  jz      loc_18002F3EE
0x18002ef39  cmp     dword ptr [lpDIS], 4
0x18002ef3c  jnz     loc_18002F3EE
0x18002ef42  mov     this, [lpDIS+20h]; hDC
0x18002ef46  call    ?FromHandle@CDC@@SAPEAV1@PEAUHDC__@@@Z; CDC::FromHandle(HDC__ *)
0x18002ef4b  mov     r14, rax
0x18002ef4e  mov     rax, [rsi+118h]
0x18002ef55  test    rax, rax
0x18002ef58  jnz     short loc_18002EF5E
0x18002ef5a  xor     edx, edx
0x18002ef5c  jmp     short loc_18002EF62
0x18002ef5e  mov     lpDIS, [rax+8]; hPal
0x18002ef62  lea     r12, [r14+8]
0x18002ef66  xor     r8d, r8d; bForceBkgd
0x18002ef69  mov     this, [r12]; hdc
0x18002ef6d  call    cs:__imp_SelectPalette
0x18002ef73  mov     this, rax; h
0x18002ef76  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18002ef7b  mov     rdi, rax
0x18002ef7e  mov     qword ptr [rbp+57h+result.left], rax
0x18002ef82  mov     this, [r12]; hdc
0x18002ef86  call    cs:__imp_RealizePalette
0x18002ef8c  xorps   xmm0, xmm0
0x18002ef8f  movdqu  xmmword ptr [rbp+57h+rectClip.left], xmm0
0x18002ef94  mov     this, [r14]
0x18002ef97  mov     rax, [this+0B0h]
0x18002ef9e  lea     lpDIS, [rbp+57h+rectClip]
0x18002efa2  mov     this, r14
0x18002efa5  call    cs:__guard_dispatch_icall_fptr
0x18002efab  lea     lpDIS, [rbx+28h]; lprcSrc
0x18002efaf  lea     this, [rbp+57h+rectClient]; lprcDst
0x18002efb3  call    cs:__imp_CopyRect
0x18002efb9  and     [rbp+57h+var_A0], 0
0x18002efbd  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18002efc4  mov     [rbp+57h+dcMem.__vftable], rax
0x18002efc8  xorps   xmm0, xmm0
0x18002efcb  movdqu  xmmword ptr [rbp+57h+dcMem.m_hDC], xmm0
0x18002efd0  and     [rbp+57h+dcMem.m_bPrinting], 0
0x18002efd4  and     [rbp+57h+bmp.m_hObject], 0
0x18002efd9  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18002efe0  mov     [rbp+57h+bmp.__vftable], rax
0x18002efe4  xor     r15d, r15d
0x18002efe7  xor     r13d, r13d
0x18002efea  mov     this, [r12]; hdc
0x18002efee  call    cs:__imp_CreateCompatibleDC
0x18002eff4  mov     lpDIS, rax; hDC
0x18002eff7  lea     this, [rbp+57h+dcMem]; this
0x18002effb  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18002f000  lea     rbx, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; AFX_GLOBAL_DATA afxGlobalData
0x18002f007  test    eax, eax
0x18002f009  jz      loc_18002F0BE
0x18002f00f  mov     r8d, [rbp+57h+rectClient.bottom]
0x18002f013  sub     r8d, [rbp+57h+rectClient.top]; cy
0x18002f017  mov     edx, [rbp+57h+rectClient.right]
0x18002f01a  sub     edx, [rbp+57h+rectClient.left]; cx
0x18002f01d  mov     this, [r12]; hdc
0x18002f021  call    cs:__imp_CreateCompatibleBitmap
0x18002f027  mov     lpDIS, rax; hObject
0x18002f02a  lea     this, [rbp+57h+bmp]; this
0x18002f02e  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18002f033  test    eax, eax
0x18002f035  jz      loc_18002F0BE
0x18002f03b  mov     [rbp+57h+var_A0], 1
0x18002f042  mov     lpDIS, [rbp+57h+bmp.m_hObject]; h
0x18002f046  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18002f04a  call    cs:__imp_SelectObject
0x18002f050  mov     this, rax; h
0x18002f053  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18002f058  mov     r15, rax
0x18002f05b  lea     r14, [rbp+57h+dcMem]
0x18002f05f  mov     lpDIS, [rsi+118h]
0x18002f066  test    lpDIS, lpDIS
0x18002f069  jz      short loc_18002F06F
0x18002f06b  mov     lpDIS, [lpDIS+8]; hPal
0x18002f06f  xor     r8d, r8d; bForceBkgd
0x18002f072  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18002f076  call    cs:__imp_SelectPalette
0x18002f07c  mov     this, rax; h
0x18002f07f  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18002f084  mov     r13, rax
0x18002f087  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18002f08b  call    cs:__imp_RealizePalette
0x18002f091  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f098  jnz     short loc_18002F0AC
0x18002f09a  mov     this, rbx; this
0x18002f09d  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18002f0a2  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f0ac  xor     r9d, r9d; rectClip
0x18002f0af  lea     r8, [rbp+57h+dcMem]; pDC
0x18002f0b3  mov     lpDIS, rsi; pWnd
0x18002f0b6  mov     this, rbx; this
0x18002f0b9  call    ?DrawParentBackground@AFX_GLOBAL_DATA@@QEAAHPEAVCWnd@@PEAVCDC@@PEAUtagRECT@@@Z; AFX_GLOBAL_DATA::DrawParentBackground(CWnd *,CDC *,tagRECT *)
0x18002f0be  mov     ecx, [rsi+0E8h]
0x18002f0c4  test    ecx, ecx
0x18002f0c6  jz      loc_18002F21F
0x18002f0cc  sub     ecx, 1
0x18002f0cf  jz      loc_18002F199
0x18002f0d5  sub     ecx, 1
0x18002f0d8  jz      short loc_18002F10A
0x18002f0da  sub     ecx, 1
0x18002f0dd  jz      short loc_18002F0F2
0x18002f0df  cmp     ecx, 1
0x18002f0e2  jnz     loc_18002F2EF
0x18002f0e8  mov     this, rsi; this
0x18002f0eb  call    ?CreateHexGreyScaleBar@CMFCColorPickerCtrl@@IEAAXXZ; CMFCColorPickerCtrl::CreateHexGreyScaleBar(void)
0x18002f0f0  jmp     short loc_18002F0FA
0x18002f0f2  mov     this, rsi; this
0x18002f0f5  call    ?CreateHexagon@CMFCColorPickerCtrl@@IEAAXXZ; CMFCColorPickerCtrl::CreateHexagon(void)
0x18002f0fa  mov     lpDIS, r14; pDC
0x18002f0fd  mov     this, rsi; this
0x18002f100  call    ?DrawHex@CMFCColorPickerCtrl@@IEAAXPEAVCDC@@@Z; CMFCColorPickerCtrl::DrawHex(CDC *)
0x18002f105  jmp     loc_18002F2EF
0x18002f10a  mov     lpDIS, r14; pDC
0x18002f10d  mov     this, rsi; this
0x18002f110  call    ?DrawPicker@CMFCColorPickerCtrl@@IEAAXPEAVCDC@@@Z; CMFCColorPickerCtrl::DrawPicker(CDC *)
0x18002f115  mov     rax, [rsi]
0x18002f118  mov     rbx, [rax+2E8h]
0x18002f11f  lea     lpDIS, [rbp+57h+result]; result
0x18002f123  mov     this, rsi; this
0x18002f126  call    ?GetCursorRect@CMFCColorPickerCtrl@@IEAA?AVCRect@@XZ; CMFCColorPickerCtrl::GetCursorRect(void)
0x18002f12b  mov     r8, rax
0x18002f12e  mov     lpDIS, r14
0x18002f131  mov     this, rsi
0x18002f134  mov     rax, rbx
0x18002f137  call    cs:__guard_dispatch_icall_fptr
0x18002f13d  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f143  test    eax, eax
0x18002f145  jnz     short loc_18002F15E
0x18002f147  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18002f14e  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18002f153  mov     eax, 1
0x18002f158  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f15e  mov     ebx, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnHilite; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f164  test    eax, eax
0x18002f166  jnz     short loc_18002F17E
0x18002f168  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18002f16f  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18002f174  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f17e  mov     r9d, ebx; clrBottomRight
0x18002f181  mov     r8d, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnDkShadow; clrTopLeft
0x18002f188  lea     lpDIS, [rbp+57h+rectClient]; lpRect
0x18002f18c  mov     this, r14; this
0x18002f18f  call    ?Draw3dRect@CDC@@QEAAXPEBUtagRECT@@KK@Z; CDC::Draw3dRect(tagRECT const *,ulong,ulong)
0x18002f194  jmp     loc_18002F2EF
0x18002f199  mov     lpDIS, r14; pDC
0x18002f19c  mov     this, rsi; this
0x18002f19f  call    ?DrawLuminanceBar@CMFCColorPickerCtrl@@IEAAXPEAVCDC@@@Z; CMFCColorPickerCtrl::DrawLuminanceBar(CDC *)
0x18002f1a4  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 0; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f1ab  jnz     short loc_18002F1BF
0x18002f1ad  mov     this, rbx; this
0x18002f1b0  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18002f1b5  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f1bf  mov     edx, [rbp+57h+rectClient.bottom]
0x18002f1c2  sub     edx, [rbp+57h+rectClient.top]
0x18002f1c5  mov     eax, [rsi+110h]
0x18002f1cb  mov     ecx, [rbp+57h+rectClient.right]
0x18002f1ce  sub     ecx, eax
0x18002f1d0  sub     ecx, [rbp+57h+rectClient.left]
0x18002f1d3  mov     [rbp+57h+result.left], eax
0x18002f1d6  and     [rbp+57h+result.top], 0
0x18002f1da  mov     [rbp+57h+result.right], ecx
0x18002f1dd  mov     [rbp+57h+result.bottom], edx
0x18002f1e0  lea     r9, [rbp+57h+result]; rectClip
0x18002f1e4  mov     r8, r14; pDC
0x18002f1e7  mov     lpDIS, rsi; pWnd
0x18002f1ea  mov     this, rbx; this
0x18002f1ed  call    ?DrawParentBackground@AFX_GLOBAL_DATA@@QEAAHPEAVCWnd@@PEAVCDC@@PEAUtagRECT@@@Z; AFX_GLOBAL_DATA::DrawParentBackground(CWnd *,CDC *,tagRECT *)
0x18002f1f2  mov     rax, [rsi]
0x18002f1f5  mov     rbx, [rax+2E8h]
0x18002f1fc  lea     lpDIS, [rbp+57h+result]; result
0x18002f200  mov     this, rsi; this
0x18002f203  call    ?GetCursorRect@CMFCColorPickerCtrl@@IEAA?AVCRect@@XZ; CMFCColorPickerCtrl::GetCursorRect(void)
0x18002f208  mov     r8, rax
0x18002f20b  mov     lpDIS, r14
0x18002f20e  mov     this, rsi
0x18002f211  mov     rax, rbx
0x18002f214  call    cs:__guard_dispatch_icall_fptr
0x18002f21a  jmp     loc_18002F2EF
0x18002f21f  mov     this, [r14+10h]; hdc
0x18002f223  call    cs:__imp_GetTextColor
0x18002f229  mov     edi, eax
0x18002f22b  mov     eax, [rbp+57h+rectClient.bottom]
0x18002f22e  sub     eax, [rbp+57h+rectClient.top]
0x18002f231  cdq
0x18002f232  sub     eax, edx
0x18002f234  sar     eax, 1
0x18002f236  mov     ebx, eax
0x18002f238  mov     ecx, [rsi+108h]
0x18002f23e  mov     r9d, [rbp+57h+rectClient.right]
0x18002f242  sub     r9d, [rbp+57h+rectClient.left]; cx
0x18002f246  mov     [rsp+0F0h+clr], ecx; clr
0x18002f24a  mov     [rsp+0F0h+cy], eax; cy
0x18002f24e  xor     r8d, r8d; y
0x18002f251  xor     edx, edx; x
0x18002f253  mov     this, r14; this
0x18002f256  call    ?FillSolidRect@CDC@@QEAAXHHHHK@Z; CDC::FillSolidRect(int,int,int,int,ulong)
0x18002f25b  mov     ecx, [rsi+10Ch]
0x18002f261  mov     r9d, [rbp+57h+rectClient.right]
0x18002f265  sub     r9d, [rbp+57h+rectClient.left]; cx
0x18002f269  mov     [rsp+0F0h+clr], ecx; clr
0x18002f26d  mov     [rsp+0F0h+cy], ebx; cy
0x18002f271  mov     r8d, ebx; y
0x18002f274  xor     edx, edx; x
0x18002f276  mov     this, r14; this
0x18002f279  call    ?FillSolidRect@CDC@@QEAAXHHHHK@Z; CDC::FillSolidRect(int,int,int,int,ulong)
0x18002f27e  mov     rax, [r14]
0x18002f281  mov     edx, edi
0x18002f283  mov     this, r14
0x18002f286  mov     rax, [rax+70h]
0x18002f28a  call    cs:__guard_dispatch_icall_fptr
0x18002f290  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f296  test    eax, eax
0x18002f298  jnz     short loc_18002F2B1
0x18002f29a  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18002f2a1  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18002f2a6  mov     eax, 1
0x18002f2ab  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, eax; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f2b1  mov     r8d, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnDkShadow; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f2b8  mov     ebx, r8d
0x18002f2bb  test    eax, eax
0x18002f2bd  jnz     short loc_18002F2DC
0x18002f2bf  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x18002f2c6  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18002f2cb  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18002f2d5  mov     r8d, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnDkShadow; clrTopLeft
0x18002f2dc  mov     r9d, ebx; clrBottomRight
0x18002f2df  lea     lpDIS, [rbp+57h+rectClient]; lpRect
0x18002f2e3  mov     this, r14; this
0x18002f2e6  call    ?Draw3dRect@CDC@@QEAAXPEBUtagRECT@@KK@Z; CDC::Draw3dRect(tagRECT const *,ulong,ulong)
0x18002f2eb  mov     rdi, qword ptr [rbp+57h+result.left]
0x18002f2ef  cmp     [rbp+57h+var_A0], 0
0x18002f2f3  jz      short loc_18002F36E
0x18002f2f5  mov     ecx, [rbp+57h+rectClip.bottom]
0x18002f2f8  mov     r8d, [rbp+57h+rectClip.top]; y
0x18002f2fc  sub     ecx, r8d
0x18002f2ff  mov     r9d, [rbp+57h+rectClip.right]
0x18002f303  mov     edx, [rbp+57h+rectClip.left]; x
0x18002f306  sub     r9d, edx; cx
0x18002f309  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x18002f311  mov     [rsp+0F0h+y1], r8d; y1
0x18002f316  mov     [rsp+0F0h+x1], edx; x1
0x18002f31a  mov     rax, [rbp+57h+dcMem.m_hDC]
0x18002f31e  mov     qword ptr [rsp+0F0h+clr], rax; hdcSrc
0x18002f323  mov     [rsp+0F0h+cy], ecx; cy
0x18002f327  mov     this, [r12]; hdc
0x18002f32b  call    cs:__imp_BitBlt
0x18002f331  test    r13, r13
0x18002f334  jz      short loc_18002F34F
0x18002f336  xor     r8d, r8d; bForceBkgd
0x18002f339  mov     lpDIS, [r13+8]; hPal
0x18002f33d  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18002f341  call    cs:__imp_SelectPalette
0x18002f347  mov     this, rax; h
0x18002f34a  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18002f34f  test    r15, r15
0x18002f352  jnz     short loc_18002F358
0x18002f354  xor     edx, edx
0x18002f356  jmp     short loc_18002F35C
0x18002f358  mov     lpDIS, [r15+8]; h
0x18002f35c  mov     this, [rbp+57h+dcMem.m_hDC]; hdc
0x18002f360  call    cs:__imp_SelectObject
0x18002f366  mov     this, rax; h
0x18002f369  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18002f36e  test    rdi, rdi
0x18002f371  jz      short loc_18002F38D
0x18002f373  xor     r8d, r8d; bForceBkgd
0x18002f376  mov     lpDIS, [rdi+8]; hPal
0x18002f37a  mov     this, [r12]; hdc
0x18002f37e  call    cs:__imp_SelectPalette
0x18002f384  mov     this, rax; h
0x18002f387  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18002f38c  nop
0x18002f38d  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18002f394  mov     [rbp+57h+bmp.__vftable], rax
0x18002f398  lea     this, [rbp+57h+bmp]; this
0x18002f39c  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18002f3a1  nop
0x18002f3a2  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18002f3a9  mov     [rbp+57h+dcMem.__vftable], rax
0x18002f3ad  cmp     [rbp+57h+dcMem.m_hDC], 0
0x18002f3b2  jz      short loc_18002F3C7
0x18002f3b4  lea     this, [rbp+57h+dcMem]; this
0x18002f3b8  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18002f3bd  mov     this, rax; hdc
  ... truncated ...
```
