# AFX_GLOBAL_DATA::UpdateFonts(void)

- ea: `0x18006cd00`
- end: `0x18006d335`
- name: `?UpdateFonts@AFX_GLOBAL_DATA@@QEAAXXZ`
- size: `1589`
- prototype: `void __fastcall(AFX_GLOBAL_DATA *this)`
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x18006cab0`
- `0x1800e3b20`
- `0x1801601e0`

## callees

- `0x18001d090`
- `0x18006cd00`
- `0x18006daf0`
- `0x180231d70`
- `0x180296d50`
- `0x1802b0720`
- `0x1802b07d0`
- `0x1802b09d0`
- `0x1802b0a10`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!lstrcpyW` at `0x18006cf9e`
- `KERNEL32!lstrcpyW` at `0x18006cfde`
- `KERNEL32!lstrcpyW` at `0x18006d01d`
- `KERNEL32!lstrcpyW` at `0x18006d16a`
- `KERNEL32!lstrcpyW` at `0x18006d20e`
- `KERNEL32!lstrcpyW` at `0x18006cf9e`
- `KERNEL32!lstrcpyW` at `0x18006cfde`
- `KERNEL32!lstrcpyW` at `0x18006d01d`
- `KERNEL32!lstrcpyW` at `0x18006d16a`
- `KERNEL32!lstrcpyW` at `0x18006d20e`
- `VCRUNTIME140!memset` at `0x18006cf36`
- `VCRUNTIME140!memset` at `0x18006cf36`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x18006d03f`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x18006d03f`
- `USER32!GetSystemMetrics` at `0x18006d152`
- `USER32!GetSystemMetrics` at `0x18006d152`
- `USER32!SystemParametersInfoW` at `0x18006cf25`
- `USER32!SystemParametersInfoW` at `0x18006d0b1`
- `USER32!SystemParametersInfoW` at `0x18006cf25`
- `USER32!SystemParametersInfoW` at `0x18006d0b1`
- `GDI32!EnumFontFamiliesW` at `0x18006cfc8`
- `GDI32!EnumFontFamiliesW` at `0x18006d000`
- `GDI32!EnumFontFamiliesW` at `0x18006cfc8`
- `GDI32!EnumFontFamiliesW` at `0x18006d000`
- `GDI32!GetTextCharsetInfo` at `0x18006cf46`
- `GDI32!GetTextCharsetInfo` at `0x18006cf46`
- `GDI32!GetDeviceCaps` at `0x18006cd55`
- `GDI32!GetDeviceCaps` at `0x18006cd55`
- `GDI32!CreateFontIndirectW` at `0x18006d028`
- `GDI32!CreateFontIndirectW` at `0x18006d074`
- `GDI32!CreateFontIndirectW` at `0x18006d0d0`
- `GDI32!CreateFontIndirectW` at `0x18006d103`
- `GDI32!CreateFontIndirectW` at `0x18006d12a`
- `GDI32!CreateFontIndirectW` at `0x18006d175`
- `GDI32!CreateFontIndirectW` at `0x18006d219`
- `GDI32!CreateFontIndirectW` at `0x18006d234`
- `GDI32!CreateFontIndirectW` at `0x18006d262`
- `GDI32!CreateFontIndirectW` at `0x18006d285`
- `GDI32!CreateFontIndirectW` at `0x18006d028`
- `GDI32!CreateFontIndirectW` at `0x18006d074`
- `GDI32!CreateFontIndirectW` at `0x18006d0d0`
- `GDI32!CreateFontIndirectW` at `0x18006d103`
- `GDI32!CreateFontIndirectW` at `0x18006d12a`
- `GDI32!CreateFontIndirectW` at `0x18006d175`
- `GDI32!CreateFontIndirectW` at `0x18006d219`
- `GDI32!CreateFontIndirectW` at `0x18006d234`
- `GDI32!CreateFontIndirectW` at `0x18006d262`
- `GDI32!CreateFontIndirectW` at `0x18006d285`
- `GDI32!DeleteObject` at `0x18006cdc2`
- `GDI32!DeleteObject` at `0x18006cde5`
- `GDI32!DeleteObject` at `0x18006ce08`
- `GDI32!DeleteObject` at `0x18006ce2b`
- `GDI32!DeleteObject` at `0x18006ce4e`
- `GDI32!DeleteObject` at `0x18006ce72`
- `GDI32!DeleteObject` at `0x18006ce95`
- `GDI32!DeleteObject` at `0x18006ceb8`
- `GDI32!DeleteObject` at `0x18006cedb`
- `GDI32!DeleteObject` at `0x18006ceff`
- `GDI32!DeleteObject` at `0x18006cdc2`
- `GDI32!DeleteObject` at `0x18006cde5`
- `GDI32!DeleteObject` at `0x18006ce08`
- `GDI32!DeleteObject` at `0x18006ce2b`
- `GDI32!DeleteObject` at `0x18006ce4e`
- `GDI32!DeleteObject` at `0x18006ce72`
- `GDI32!DeleteObject` at `0x18006ce95`
- `GDI32!DeleteObject` at `0x18006ceb8`
- `GDI32!DeleteObject` at `0x18006cedb`
- `GDI32!DeleteObject` at `0x18006ceff`
- `GDI32!GetObjectW` at `0x18006d1c3`
- `GDI32!GetObjectW` at `0x18006d252`
- `GDI32!GetObjectW` at `0x18006d1c3`
- `GDI32!GetObjectW` at `0x18006d252`
- `GDI32!GetStockObject` at `0x18006d19f`
- `GDI32!GetStockObject` at `0x18006d19f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AFX_GLOBAL_DATA::UpdateFonts(AFX_GLOBAL_DATA *this)
{
  double v2; // xmm1_8
  void *v3; // rax
  void *v4; // rax
  void *v5; // rax
  void *v6; // rax
  void *v7; // rax
  void *v8; // rax
  void *v9; // rax
  void *v10; // rax
  void *v11; // rax
  void *v12; // rax
  UINT v13; // edx
  int lfEscapement; // ecx
  int v15; // eax
  const wchar_t *v16; // rdx
  HFONT FontIndirectW; // rax
  int v18; // ebx
  int v19; // eax
  int v20; // eax
  HFONT v21; // rax
  UINT v22; // eax
  HFONT v23; // rax
  HFONT v24; // rax
  HFONT v25; // rax
  char v26; // bl
  HFONT v27; // rax
  CWindowDC_vtbl *StockObject; // rax
  CWindowDC_vtbl *v29; // rbx
  HFONT v30; // rax
  HFONT v31; // rax
  HFONT v32; // rax
  HFONT v33; // rax
  CObList::CNode *m_pNodeHead; // rbx
  HWND__ **data; // rdi
  CFont font; // [rsp+20h] [rbp-E8h] BYREF
  CWindowDC dc; // [rsp+30h] [rbp-D8h] BYREF
  tagLOGFONTW lf; // [rsp+60h] [rbp-A8h] BYREF
  tagNONCLIENTMETRICSW info; // [rsp+C0h] [rbp-48h] BYREF
  tagNONCLIENTMETRICSW ncm; // [rsp+2C0h] [rbp+1B8h] BYREF

  CWindowDC::CWindowDC((CWindowDC *)&dc.m_hDC, 0);
  v2 = (float)((float)GetDeviceCaps(*(HDC *)&dc.m_bPrinting, 88) / 96.0);
  this->m_dblRibbonImageScale = v2;
  if ( v2 > 1.0 && v2 < 1.1 )
    this->m_dblRibbonImageScale = 1.0;
  if ( this != (AFX_GLOBAL_DATA *)-424LL && this->fontRegular.m_hObject )
  {
    v3 = CGdiObject::Detach(&this->fontRegular);
    DeleteObject(v3);
  }
  if ( this != (AFX_GLOBAL_DATA *)-440LL && this->fontTooltip.m_hObject )
  {
    v4 = CGdiObject::Detach(&this->fontTooltip);
    DeleteObject(v4);
  }
  if ( this != (AFX_GLOBAL_DATA *)-456LL && this->fontBold.m_hObject )
  {
    v5 = CGdiObject::Detach(&this->fontBold);
    DeleteObject(v5);
  }
  if ( this != (AFX_GLOBAL_DATA *)-472LL && this->fontDefaultGUIBold.m_hObject )
  {
    v6 = CGdiObject::Detach(&this->fontDefaultGUIBold);
    DeleteObject(v6);
  }
  if ( this != (AFX_GLOBAL_DATA *)-488LL && this->fontUnderline.m_hObject )
  {
    v7 = CGdiObject::Detach(&this->fontUnderline);
    DeleteObject(v7);
  }
  if ( this != (AFX_GLOBAL_DATA *)-504LL && this->fontDefaultGUIUnderline.m_hObject )
  {
    v8 = CGdiObject::Detach(&this->fontDefaultGUIUnderline);
    DeleteObject(v8);
  }
  if ( this != (AFX_GLOBAL_DATA *)-520LL && this->fontVert.m_hObject )
  {
    v9 = CGdiObject::Detach(&this->fontVert);
    DeleteObject(v9);
  }
  if ( this != (AFX_GLOBAL_DATA *)-536LL && this->fontVertCaption.m_hObject )
  {
    v10 = CGdiObject::Detach(&this->fontVertCaption);
    DeleteObject(v10);
  }
  if ( this != (AFX_GLOBAL_DATA *)-568LL && this->fontMarlett.m_hObject )
  {
    v11 = CGdiObject::Detach(&this->fontMarlett);
    DeleteObject(v11);
  }
  if ( this != (AFX_GLOBAL_DATA *)-552LL && this->fontSmall.m_hObject )
  {
    v12 = CGdiObject::Detach(&this->fontSmall);
    DeleteObject(v12);
  }
  v13 = 504;
  if ( !this->bIsWindows7 )
    v13 = 500;
  info.iScrollWidth = v13;
  SystemParametersInfoW(0x29u, v13, &info.iScrollWidth, 0);
  memset(&lf.lfEscapement, 0, sizeof(tagLOGFONTW));
  HIBYTE(lf.lfFaceName[1]) = GetTextCharsetInfo(dc.m_hAttribDC, 0, 0);
  *(_DWORD *)&lf.lfOutPrecision = *(_DWORD *)&info.lfMenuFont.lfOutPrecision;
  LOBYTE(lf.lfFaceName[0]) = info.lfMenuFont.lfFaceName[0];
  lfEscapement = -info.lfMenuFont.lfEscapement;
  if ( info.lfMenuFont.lfEscapement > 0 )
    lfEscapement = info.lfMenuFont.lfEscapement;
  if ( lfEscapement > 12 )
  {
    if ( !this->m_bDontReduceFontHeight )
      --lfEscapement;
  }
  else
  {
    lfEscapement = 11;
  }
  if ( info.lfMenuFont.lfEscapement < 0 )
    lfEscapement = -lfEscapement;
  lf.lfEscapement = lfEscapement;
  lstrcpyW(&lf.lfFaceName[4], &info.lfMenuFont.lfFaceName[4]);
  if ( !this->m_bUseSystemFont && HIBYTE(info.lfMenuFont.lfFaceName[1]) <= 2u )
  {
    if ( EnumFontFamiliesW(dc.m_hAttribDC, 0, FontFamilyProcFonts, (LPARAM)L"Segoe UI") )
    {
      v15 = EnumFontFamiliesW(dc.m_hAttribDC, 0, FontFamilyProcFonts, (LPARAM)L"Tahoma");
      v16 = (const wchar_t *)L"Tahoma";
      if ( v15 )
        v16 = L"MS Sans Serif";
      lstrcpyW(&lf.lfFaceName[4], v16);
    }
    else
    {
      lstrcpyW(&lf.lfFaceName[4], (LPCWSTR)L"Segoe UI");
      LOBYTE(lf.lfFaceName[3]) = 5;
    }
  }
  FontIndirectW = CreateFontIndirectW((const LOGFONTW *)&lf.lfEscapement);
  CGdiObject::Attach(&this->fontRegular, FontIndirectW);
  v18 = lf.lfEscapement;
  v19 = labs(lf.lfEscapement);
  v20 = (int)(((double)v19 + 1.0 + (double)v19 + 1.0) / 3.0);
  lf.lfEscapement = v20;
  if ( v18 < 0 )
    lf.lfEscapement = -v20;
  v21 = CreateFontIndirectW((const LOGFONTW *)&lf.lfEscapement);
  CGdiObject::Attach(&this->fontSmall, v21);
  lf.lfEscapement = v18;
  v22 = 504;
  if ( !this->bIsWindows7 )
    v22 = 500;
  ncm.iScrollWidth = v22;
  SystemParametersInfoW(0x29u, v22, &ncm.iScrollWidth, 0);
  LOBYTE(lf.lfFaceName[0]) = ncm.lfStatusFont.lfFaceName[0];
  *(_DWORD *)&lf.lfOutPrecision = *(_DWORD *)&ncm.lfStatusFont.lfOutPrecision;
  v23 = CreateFontIndirectW((const LOGFONTW *)&lf.lfEscapement);
  CGdiObject::Attach(&this->fontTooltip, v23);
  LOBYTE(lf.lfFaceName[0]) = info.lfMenuFont.lfFaceName[0];
  *(_DWORD *)&lf.lfOutPrecision = *(_DWORD *)&info.lfMenuFont.lfOutPrecision;
  HIBYTE(lf.lfFaceName[0]) = 1;
  v24 = CreateFontIndirectW((const LOGFONTW *)&lf.lfEscapement);
  CGdiObject::Attach(&this->fontUnderline, v24);
  HIBYTE(lf.lfFaceName[0]) = 0;
  *(_DWORD *)&lf.lfOutPrecision = 700;
  v25 = CreateFontIndirectW((const LOGFONTW *)&lf.lfEscapement);
  CGdiObject::Attach(&this->fontBold, v25);
  v26 = HIBYTE(lf.lfFaceName[1]);
  HIBYTE(lf.lfFaceName[1]) = 2;
  *(_DWORD *)&lf.lfOutPrecision = 0;
  lf.lfEscapement = GetSystemMetrics(72) - 1;
  lstrcpyW(&lf.lfFaceName[4], L"Marlett");
  v27 = CreateFontIndirectW((const LOGFONTW *)&lf.lfEscapement);
  CGdiObject::Attach(&this->fontMarlett, v27);
  HIBYTE(lf.lfFaceName[1]) = v26;
  font.m_hObject = (void *)CFont::`vftable';
  StockObject = (CWindowDC_vtbl *)GetStockObject(17);
  v29 = StockObject;
  dc.__vftable = StockObject;
  if ( StockObject && GetObjectW(StockObject, 92, &lf.lfEscapement) )
  {
    *(_DWORD *)&lf.lfItalic = 900;
    lf.lfWeight = 2700;
    lf.lfEscapement = info.lfMenuFont.lfEscapement;
    *(_DWORD *)&lf.lfOutPrecision = *(_DWORD *)&info.lfMenuFont.lfOutPrecision;
    LOBYTE(lf.lfFaceName[0]) = info.lfMenuFont.lfFaceName[0];
    lstrcpyW(&lf.lfFaceName[4], L"Arial");
    v30 = CreateFontIndirectW((const LOGFONTW *)&lf.lfEscapement);
    CGdiObject::Attach(&this->fontVert, v30);
    lf.lfWeight = 900;
    v31 = CreateFontIndirectW((const LOGFONTW *)&lf.lfEscapement);
    CGdiObject::Attach(&this->fontVertCaption, v31);
    GetObjectW(v29, 92, &lf.lfEscapement);
    HIBYTE(lf.lfFaceName[0]) = 1;
    v32 = CreateFontIndirectW((const LOGFONTW *)&lf.lfEscapement);
    CGdiObject::Attach(&this->fontDefaultGUIUnderline, v32);
    HIBYTE(lf.lfFaceName[0]) = 0;
    *(_DWORD *)&lf.lfOutPrecision = 700;
    v33 = CreateFontIndirectW((const LOGFONTW *)&lf.lfEscapement);
    CGdiObject::Attach(&this->fontDefaultGUIBold, v33);
  }
  AFX_GLOBAL_DATA::UpdateTextMetrics(this);
  m_pNodeHead = afxAllToolBars.m_pNodeHead;
  while ( m_pNodeHead )
  {
    data = (HWND__ **)m_pNodeHead->data;
    m_pNodeHead = m_pNodeHead->pNext;
    if ( !data )
      AfxThrowInvalidArgException();
    if ( CWnd::FromHandlePermanent(data[8]) )
      (*((void (__fastcall **)(HWND__ **))*data + 236))(data);
  }
  font.m_hObject = (void *)CFont::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&font.m_hObject);
  CWindowDC::~CWindowDC((CWindowDC *)&dc.m_hDC);
}

```

## disassembly

```asm
0x18006cd00  mov     rax, rsp
0x18006cd03  mov     [rax+10h], rbx
0x18006cd07  mov     [rax+18h], rsi
0x18006cd0b  mov     [rax+20h], rdi
0x18006cd0f  push    rbp
0x18006cd10  push    r12
0x18006cd12  push    r13
0x18006cd14  push    r14
0x18006cd16  push    r15
0x18006cd18  lea     rbp, [rax-408h]
0x18006cd1f  sub     rsp, 4E0h
0x18006cd26  movaps  xmmword ptr [rax-38h], xmm6
0x18006cd2a  mov     rax, cs:__security_cookie
0x18006cd31  xor     rax, rsp
0x18006cd34  mov     [rbp+400h+var_40], rax
0x18006cd3b  mov     rdi, this
0x18006cd3e  xor     edx, edx; pWnd
0x18006cd40  lea     this, [rsp+500h+dc.m_hDC]; this
0x18006cd45  call    ??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x18006cd4a  nop
0x18006cd4b  mov     edx, 58h ; 'X'; index
0x18006cd50  mov     this, qword ptr [rsp+500h+dc.m_bPrinting]; hdc
0x18006cd55  call    cs:__imp_GetDeviceCaps
0x18006cd5b  movd    xmm0, eax
0x18006cd5f  cvtdq2ps xmm0, xmm0
0x18006cd62  divss   xmm0, cs:__real@42c00000
0x18006cd6a  cvtps2pd xmm1, xmm0
0x18006cd6d  movsd   qword ptr [rdi+2B8h], xmm1
0x18006cd75  movsd   xmm6, cs:__real@3ff0000000000000
0x18006cd7d  comisd  xmm1, xmm6
0x18006cd81  jbe     short loc_18006CDA2
0x18006cd83  movsd   xmm0, cs:__real@3ff199999999999a
0x18006cd8b  comisd  xmm0, xmm1
0x18006cd8f  jbe     short loc_18006CDA2
0x18006cd91  mov     rax, 3FF0000000000000h
0x18006cd9b  mov     [rdi+2B8h], rax
0x18006cda2  lea     rbx, [rdi+1A8h]
0x18006cda9  xor     r13d, r13d
0x18006cdac  test    rbx, rbx
0x18006cdaf  jz      short loc_18006CDC8
0x18006cdb1  cmp     [rbx+8], r13
0x18006cdb5  jz      short loc_18006CDC8
0x18006cdb7  mov     this, rbx; this
0x18006cdba  call    ?Detach@CGdiObject@@QEAAPEAXXZ; CGdiObject::Detach(void)
0x18006cdbf  mov     this, rax; ho
0x18006cdc2  call    cs:__imp_DeleteObject
0x18006cdc8  lea     rax, [rdi+1B8h]
0x18006cdcf  test    rax, rax
0x18006cdd2  jz      short loc_18006CDEB
0x18006cdd4  cmp     [rax+8], r13
0x18006cdd8  jz      short loc_18006CDEB
0x18006cdda  mov     this, rax; this
0x18006cddd  call    ?Detach@CGdiObject@@QEAAPEAXXZ; CGdiObject::Detach(void)
0x18006cde2  mov     this, rax; ho
0x18006cde5  call    cs:__imp_DeleteObject
0x18006cdeb  lea     rax, [rdi+1C8h]
0x18006cdf2  test    rax, rax
0x18006cdf5  jz      short loc_18006CE0E
0x18006cdf7  cmp     [rax+8], r13
0x18006cdfb  jz      short loc_18006CE0E
0x18006cdfd  mov     this, rax; this
0x18006ce00  call    ?Detach@CGdiObject@@QEAAPEAXXZ; CGdiObject::Detach(void)
0x18006ce05  mov     this, rax; ho
0x18006ce08  call    cs:__imp_DeleteObject
0x18006ce0e  lea     r15, [rdi+1D8h]
0x18006ce15  test    r15, r15
0x18006ce18  jz      short loc_18006CE31
0x18006ce1a  cmp     [r15+8], r13
0x18006ce1e  jz      short loc_18006CE31
0x18006ce20  mov     this, r15; this
0x18006ce23  call    ?Detach@CGdiObject@@QEAAPEAXXZ; CGdiObject::Detach(void)
0x18006ce28  mov     this, rax; ho
0x18006ce2b  call    cs:__imp_DeleteObject
0x18006ce31  lea     rax, [rdi+1E8h]
0x18006ce38  test    rax, rax
0x18006ce3b  jz      short loc_18006CE54
0x18006ce3d  cmp     [rax+8], r13
0x18006ce41  jz      short loc_18006CE54
0x18006ce43  mov     this, rax; this
0x18006ce46  call    ?Detach@CGdiObject@@QEAAPEAXXZ; CGdiObject::Detach(void)
0x18006ce4b  mov     this, rax; ho
0x18006ce4e  call    cs:__imp_DeleteObject
0x18006ce54  lea     r12, [rdi+1F8h]
0x18006ce5b  test    r12, r12
0x18006ce5e  jz      short loc_18006CE78
0x18006ce60  cmp     [r12+8], r13
0x18006ce65  jz      short loc_18006CE78
0x18006ce67  mov     this, r12; this
0x18006ce6a  call    ?Detach@CGdiObject@@QEAAPEAXXZ; CGdiObject::Detach(void)
0x18006ce6f  mov     this, rax; ho
0x18006ce72  call    cs:__imp_DeleteObject
0x18006ce78  lea     r14, [rdi+208h]
0x18006ce7f  test    r14, r14
0x18006ce82  jz      short loc_18006CE9B
0x18006ce84  cmp     [r14+8], r13
0x18006ce88  jz      short loc_18006CE9B
0x18006ce8a  mov     this, r14; this
0x18006ce8d  call    ?Detach@CGdiObject@@QEAAPEAXXZ; CGdiObject::Detach(void)
0x18006ce92  mov     this, rax; ho
0x18006ce95  call    cs:__imp_DeleteObject
0x18006ce9b  lea     rsi, [rdi+218h]
0x18006cea2  test    rsi, rsi
0x18006cea5  jz      short loc_18006CEBE
0x18006cea7  cmp     [rsi+8], r13
0x18006ceab  jz      short loc_18006CEBE
0x18006cead  mov     this, rsi; this
0x18006ceb0  call    ?Detach@CGdiObject@@QEAAPEAXXZ; CGdiObject::Detach(void)
0x18006ceb5  mov     this, rax; ho
0x18006ceb8  call    cs:__imp_DeleteObject
0x18006cebe  lea     rax, [rdi+238h]
0x18006cec5  test    rax, rax
0x18006cec8  jz      short loc_18006CEE1
0x18006ceca  cmp     [rax+8], r13
0x18006cece  jz      short loc_18006CEE1
0x18006ced0  mov     this, rax; this
0x18006ced3  call    ?Detach@CGdiObject@@QEAAPEAXXZ; CGdiObject::Detach(void)
0x18006ced8  mov     this, rax; ho
0x18006cedb  call    cs:__imp_DeleteObject
0x18006cee1  lea     r13, [rdi+228h]
0x18006cee8  test    r13, r13
0x18006ceeb  jz      short loc_18006CF05
0x18006ceed  cmp     qword ptr [r13+8], 0
0x18006cef2  jz      short loc_18006CF05
0x18006cef4  mov     this, r13; this
0x18006cef7  call    ?Detach@CGdiObject@@QEAAPEAXXZ; CGdiObject::Detach(void)
0x18006cefc  mov     this, rax; ho
0x18006ceff  call    cs:__imp_DeleteObject
0x18006cf05  mov     edx, 1F8h
0x18006cf0a  lea     eax, [rdx-4]
0x18006cf0d  cmp     dword ptr [rdi+258h], 0
0x18006cf14  cmovz   edx, eax; uiParam
0x18006cf17  mov     [rbp+400h+info.iScrollWidth], edx
0x18006cf1a  xor     r9d, r9d; fWinIni
0x18006cf1d  lea     r8, [rbp+400h+info.iScrollWidth]; pvParam
0x18006cf21  lea     ecx, [r9+29h]; uiAction
0x18006cf25  call    cs:__imp_SystemParametersInfoW
0x18006cf2b  xor     edx, edx; Val
0x18006cf2d  lea     r8d, [rdx+5Ch]; Size
0x18006cf31  lea     this, [rsp+500h+lf.lfEscapement]; void *
0x18006cf36  call    cs:__imp_memset
0x18006cf3c  xor     r8d, r8d; dwFlags
0x18006cf3f  xor     edx, edx; lpSig
0x18006cf41  mov     this, [rsp+500h+dc.m_hAttribDC]; hdc
0x18006cf46  call    cs:__imp_GetTextCharsetInfo
0x18006cf4c  mov     byte ptr [rsp+500h+lf.lfFaceName+3], al
0x18006cf50  mov     eax, dword ptr [rbp+400h+info.lfMenuFont.lfOutPrecision]
0x18006cf56  mov     dword ptr [rsp+500h+lf.lfOutPrecision], eax
0x18006cf5a  mov     al, byte ptr [rbp+400h+info.lfMenuFont.lfFaceName]
0x18006cf60  mov     byte ptr [rsp+500h+lf.lfFaceName], al
0x18006cf64  mov     edx, [rbp+400h+info.lfMenuFont.lfEscapement]
0x18006cf6a  mov     ecx, edx
0x18006cf6c  neg     ecx
0x18006cf6e  cmovs   ecx, edx
0x18006cf71  cmp     ecx, 0Ch
0x18006cf74  jg      short loc_18006CF7D
0x18006cf76  mov     ecx, 0Bh
0x18006cf7b  jmp     short loc_18006CF85
0x18006cf7d  cmp     dword ptr [rdi+8], 0
0x18006cf81  jnz     short loc_18006CF85
0x18006cf83  dec     ecx
0x18006cf85  mov     eax, ecx
0x18006cf87  neg     eax
0x18006cf89  test    edx, edx
0x18006cf8b  cmovs   ecx, eax
0x18006cf8e  mov     [rsp+500h+lf.lfEscapement], ecx
0x18006cf92  lea     rdx, [rbp+400h+info.lfMenuFont.lfFaceName+8]; lpString2
0x18006cf99  lea     this, [rsp+500h+lf.lfFaceName+8]; lpString1
0x18006cf9e  call    cs:__imp_lstrcpyW
0x18006cfa4  cmp     dword ptr [rdi+4], 0
0x18006cfa8  jnz     short loc_18006D023
0x18006cfaa  cmp     byte ptr [rbp+400h+info.lfMenuFont.lfFaceName+3], 2
0x18006cfb1  ja      short loc_18006D023
0x18006cfb3  lea     r9, lParam; "Segoe UI"
0x18006cfba  lea     r8, FontFamilyProcFonts; lpProc
0x18006cfc1  xor     edx, edx; lpLogfont
0x18006cfc3  mov     this, [rsp+500h+dc.m_hAttribDC]; hdc
0x18006cfc8  call    cs:__imp_EnumFontFamiliesW
0x18006cfce  test    eax, eax
0x18006cfd0  jnz     short loc_18006CFEB
0x18006cfd2  lea     rdx, lParam; "Segoe UI"
0x18006cfd9  lea     this, [rsp+500h+lf.lfFaceName+8]; lpString1
0x18006cfde  call    cs:__imp_lstrcpyW
0x18006cfe4  mov     byte ptr [rsp+500h+lf.lfFaceName+6], 5
0x18006cfe9  jmp     short loc_18006D023
0x18006cfeb  lea     r9, aTahoma; "Tahoma"
0x18006cff2  lea     r8, FontFamilyProcFonts; lpProc
0x18006cff9  xor     edx, edx; lpLogfont
0x18006cffb  mov     this, [rsp+500h+dc.m_hAttribDC]; hdc
0x18006d000  call    cs:__imp_EnumFontFamiliesW
0x18006d006  lea     this, [rsp+500h+lf.lfFaceName+8]; lpString1
0x18006d00b  test    eax, eax
0x18006d00d  lea     rdx, aTahoma; "Tahoma"
0x18006d014  jz      short loc_18006D01D
0x18006d016  lea     rdx, aMsSansSerif; "MS Sans Serif"
0x18006d01d  call    cs:__imp_lstrcpyW
0x18006d023  lea     this, [rsp+500h+lf.lfEscapement]; lplf
0x18006d028  call    cs:__imp_CreateFontIndirectW
0x18006d02e  mov     rdx, rax; hObject
0x18006d031  mov     this, rbx; this
0x18006d034  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18006d039  mov     ebx, [rsp+500h+lf.lfEscapement]
0x18006d03d  mov     ecx, ebx; Number
0x18006d03f  call    cs:__imp_labs
0x18006d045  movd    xmm0, eax
0x18006d049  cvtdq2pd xmm0, xmm0
0x18006d04d  addsd   xmm0, xmm6
0x18006d051  addsd   xmm0, xmm0
0x18006d055  divsd   xmm0, cs:__real@4008000000000000
0x18006d05d  cvttsd2si eax, xmm0
0x18006d061  mov     [rsp+500h+lf.lfEscapement], eax
0x18006d065  test    ebx, ebx
0x18006d067  jns     short loc_18006D06F
0x18006d069  neg     eax
0x18006d06b  mov     [rsp+500h+lf.lfEscapement], eax
0x18006d06f  lea     this, [rsp+500h+lf.lfEscapement]; lplf
0x18006d074  call    cs:__imp_CreateFontIndirectW
0x18006d07a  mov     rdx, rax; hObject
0x18006d07d  mov     this, r13; this
0x18006d080  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18006d085  mov     [rsp+500h+lf.lfEscapement], ebx
0x18006d089  cmp     dword ptr [rdi+258h], 0
0x18006d090  mov     eax, 1F8h
0x18006d095  lea     ecx, [rax-4]
0x18006d098  cmovz   eax, ecx
0x18006d09b  mov     [rbp+400h+ncm.iScrollWidth], eax
0x18006d0a1  xor     r9d, r9d; fWinIni
0x18006d0a4  lea     r8, [rbp+400h+ncm.iScrollWidth]; pvParam
0x18006d0ab  mov     edx, eax; uiParam
0x18006d0ad  lea     ecx, [r9+29h]; uiAction
0x18006d0b1  call    cs:__imp_SystemParametersInfoW
0x18006d0b7  mov     al, byte ptr [rbp+400h+ncm.lfStatusFont.lfFaceName]
0x18006d0bd  mov     byte ptr [rsp+500h+lf.lfFaceName], al
0x18006d0c1  mov     eax, dword ptr [rbp+400h+ncm.lfStatusFont.lfOutPrecision]
0x18006d0c7  mov     dword ptr [rsp+500h+lf.lfOutPrecision], eax
0x18006d0cb  lea     this, [rsp+500h+lf.lfEscapement]; lplf
0x18006d0d0  call    cs:__imp_CreateFontIndirectW
0x18006d0d6  mov     rdx, rax; hObject
0x18006d0d9  lea     this, [rdi+1B8h]; this
0x18006d0e0  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18006d0e5  mov     al, byte ptr [rbp+400h+info.lfMenuFont.lfFaceName]
0x18006d0eb  mov     byte ptr [rsp+500h+lf.lfFaceName], al
0x18006d0ef  mov     eax, dword ptr [rbp+400h+info.lfMenuFont.lfOutPrecision]
0x18006d0f5  mov     dword ptr [rsp+500h+lf.lfOutPrecision], eax
0x18006d0f9  mov     byte ptr [rsp+500h+lf.lfFaceName+1], 1
0x18006d0fe  lea     this, [rsp+500h+lf.lfEscapement]; lplf
0x18006d103  call    cs:__imp_CreateFontIndirectW
0x18006d109  mov     rdx, rax; hObject
0x18006d10c  lea     this, [rdi+1E8h]; this
0x18006d113  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18006d118  mov     byte ptr [rsp+500h+lf.lfFaceName+1], 0
0x18006d11d  mov     dword ptr [rsp+500h+lf.lfOutPrecision], 2BCh
0x18006d125  lea     this, [rsp+500h+lf.lfEscapement]; lplf
0x18006d12a  call    cs:__imp_CreateFontIndirectW
0x18006d130  mov     rdx, rax; hObject
0x18006d133  lea     this, [rdi+1C8h]; this
0x18006d13a  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18006d13f  mov     bl, byte ptr [rsp+500h+lf.lfFaceName+3]
0x18006d143  mov     byte ptr [rsp+500h+lf.lfFaceName+3], 2
0x18006d148  and     dword ptr [rsp+500h+lf.lfOutPrecision], 0
0x18006d14d  mov     ecx, 48h ; 'H'; nIndex
0x18006d152  call    cs:__imp_GetSystemMetrics
0x18006d158  dec     eax
0x18006d15a  mov     [rsp+500h+lf.lfEscapement], eax
0x18006d15e  lea     rdx, aMarlett; "Marlett"
0x18006d165  lea     this, [rsp+500h+lf.lfFaceName+8]; lpString1
0x18006d16a  call    cs:__imp_lstrcpyW
0x18006d170  lea     this, [rsp+500h+lf.lfEscapement]; lplf
0x18006d175  call    cs:__imp_CreateFontIndirectW
0x18006d17b  mov     rdx, rax; hObject
0x18006d17e  lea     this, [rdi+238h]; this
0x18006d185  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18006d18a  mov     byte ptr [rsp+500h+lf.lfFaceName+3], bl
0x18006d18e  lea     r13, ??_7CFont@@6B@; const CFont::`vftable'
0x18006d195  mov     [rsp+500h+font.m_hObject], r13
0x18006d19a  mov     ecx, 11h; i
0x18006d19f  call    cs:__imp_GetStockObject
0x18006d1a5  mov     rbx, rax
0x18006d1a8  mov     [rsp+500h+dc.__vftable], rax
0x18006d1ad  test    rax, rax
0x18006d1b0  jz      loc_18006D29D
0x18006d1b6  lea     r8, [rsp+500h+lf.lfEscapement]; pv
0x18006d1bb  mov     edx, 5Ch ; '\'; c
0x18006d1c0  mov     this, rax; h
0x18006d1c3  call    cs:__imp_GetObjectW
0x18006d1c9  test    eax, eax
0x18006d1cb  jz      loc_18006D29D
0x18006d1d1  mov     r13d, 384h
0x18006d1d7  mov     dword ptr [rsp+500h+lf.lfItalic], r13d
0x18006d1dc  mov     [rsp+500h+lf.lfWeight], 0A8Ch
0x18006d1e4  mov     eax, [rbp+400h+info.lfMenuFont.lfEscapement]
0x18006d1ea  mov     [rsp+500h+lf.lfEscapement], eax
0x18006d1ee  mov     eax, dword ptr [rbp+400h+info.lfMenuFont.lfOutPrecision]
0x18006d1f4  mov     dword ptr [rsp+500h+lf.lfOutPrecision], eax
0x18006d1f8  mov     al, byte ptr [rbp+400h+info.lfMenuFont.lfFaceName]
0x18006d1fe  mov     byte ptr [rsp+500h+lf.lfFaceName], al
0x18006d202  lea     rdx, aArial; "Arial"
0x18006d209  lea     this, [rsp+500h+lf.lfFaceName+8]; lpString1
0x18006d20e  call    cs:__imp_lstrcpyW
0x18006d214  lea     this, [rsp+500h+lf.lfEscapement]; lplf
0x18006d219  call    cs:__imp_CreateFontIndirectW
  ... truncated ...
```
