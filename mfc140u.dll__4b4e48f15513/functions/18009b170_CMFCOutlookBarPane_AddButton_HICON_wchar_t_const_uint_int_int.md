# CMFCOutlookBarPane::AddButton(HICON__ *,wchar_t const *,uint,int,int)

- ea: `0x18009b170`
- end: `0x18009b3a4`
- name: `?AddButton@CMFCOutlookBarPane@@QEAAHPEAUHICON__@@PEB_WIHH@Z`
- size: `564`
- prototype: `int __fastcall(CMFCOutlookBarPane *this, HICON__ *hIcon, const wchar_t *lpszLabel, unsigned int iIdCommand, int iInsertAt, int bAlphaBlend)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800d1eb0`

## callees

- `0x18001d090`
- `0x18009b170`
- `0x18009b520`
- `0x18009b630`
- `0x180175270`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b0630`
- `0x1802b06e0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b25f0`

## import_xrefs

- `USER32!GetIconInfo` at `0x18009b1b2`
- `USER32!GetIconInfo` at `0x18009b1b2`
- `USER32!DrawIconEx` at `0x18009b2dc`
- `USER32!DrawIconEx` at `0x18009b2dc`
- `GDI32!DeleteDC` at `0x18009b356`
- `GDI32!DeleteDC` at `0x18009b356`
- `GDI32!CreateCompatibleBitmap` at `0x18009b265`
- `GDI32!CreateCompatibleBitmap` at `0x18009b265`
- `GDI32!DeleteObject` at `0x18009b305`
- `GDI32!DeleteObject` at `0x18009b30f`
- `GDI32!DeleteObject` at `0x18009b305`
- `GDI32!DeleteObject` at `0x18009b30f`
- `GDI32!SelectObject` at `0x18009b27f`
- `GDI32!SelectObject` at `0x18009b2f3`
- `GDI32!SelectObject` at `0x18009b27f`
- `GDI32!SelectObject` at `0x18009b2f3`
- `GDI32!CreateCompatibleDC` at `0x18009b23b`
- `GDI32!CreateCompatibleDC` at `0x18009b23b`
- `GDI32!GetObjectW` at `0x18009b1c4`
- `GDI32!GetObjectW` at `0x18009b1c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall CMFCOutlookBarPane::AddButton(
        CMFCOutlookBarPane *this,
        HICON hIcon,
        const wchar_t *lpszLabel,
        unsigned int iIdCommand,
        int iInsertAt,
        int bAlphaBlend)
{
  int bmWidthBytes; // ebx
  int cy; // edi
  int v12; // ebx
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v15; // rax
  CGdiObject *v16; // r15
  void *m_hObject; // rdx
  HGDIOBJ v18; // rax
  HDC v19; // rax
  CBitmap bmp; // [rsp+50h] [rbp-81h] BYREF
  CDC dcMem; // [rsp+60h] [rbp-71h] BYREF
  _ICONINFO iconInfo; // [rsp+80h] [rbp-51h] BYREF
  CClientDC dc; // [rsp+A0h] [rbp-31h] BYREF
  tagBITMAP bitmap; // [rsp+C8h] [rbp-9h] BYREF

  if ( !hIcon )
    AfxThrowInvalidArgException();
  GetIconInfo(hIcon, (PICONINFO)&iconInfo.yHotspot);
  GetObjectW(dc.__vftable, 32, &bitmap.bmHeight);
  bmWidthBytes = bitmap.bmWidthBytes;
  cy = *(_DWORD *)&bitmap.bmPlanes;
  if ( bAlphaBlend )
  {
    if ( !CMFCOutlookBarPane::m_Images.m_iCount )
    {
      CMFCOutlookBarPane::m_csImage = *(CSize *)&bitmap.bmWidthBytes;
      CMFCOutlookBarPane::m_Images.m_sizeImage = *(CSize *)&bitmap.bmWidthBytes;
    }
    v12 = CMFCToolBarImages::AddIcon(&CMFCOutlookBarPane::m_Images, hIcon, 1);
  }
  else
  {
    CClientDC::CClientDC((CClientDC *)&dc.m_hDC, this);
    dcMem.m_hDC = (HDC__ *)CDC::`vftable';
    *(_OWORD *)&dcMem.m_hAttribDC = 0;
    iconInfo.fIcon = 0;
    CompatibleDC = CreateCompatibleDC(dc.m_hAttribDC);
    CDC::Attach((CDC *)&dcMem.m_hDC, CompatibleDC);
    dcMem.__vftable = 0;
    bmp.m_hObject = (void *)CBitmap::`vftable';
    CompatibleBitmap = CreateCompatibleBitmap(dc.m_hAttribDC, bmWidthBytes, cy);
    CGdiObject::Attach((CGdiObject *)&bmp.m_hObject, CompatibleBitmap);
    v15 = SelectObject(dcMem.m_hAttribDC, dcMem.__vftable);
    v16 = CGdiObject::FromHandle(v15);
    if ( this->m_clrTransparentColor != -1 )
      CDC::FillSolidRect((CDC *)&dcMem.m_hDC, 0, 0, bmWidthBytes, cy, this->m_clrTransparentColor);
    DrawIconEx(dcMem.m_hAttribDC, 0, 0, hIcon, bmWidthBytes, cy, 0, 0, 3u);
    if ( v16 )
      m_hObject = v16->m_hObject;
    else
      m_hObject = 0;
    v18 = SelectObject(dcMem.m_hAttribDC, m_hObject);
    CGdiObject::FromHandle(v18);
    DeleteObject(dc.__vftable);
    DeleteObject(iconInfo.hbmColor);
    v12 = CMFCOutlookBarPane::AddBitmapImage(this, (HBITMAP__ *)dcMem.__vftable);
    bmp.m_hObject = (void *)CBitmap::`vftable';
    CGdiObject::~CGdiObject((CGdiObject *)&bmp.m_hObject);
    dcMem.m_hDC = (HDC__ *)CDC::`vftable';
    if ( dcMem.m_hAttribDC )
    {
      v19 = CDC::Detach((CDC *)&dcMem.m_hDC);
      DeleteDC(v19);
    }
    CClientDC::~CClientDC((CClientDC *)&dc.m_hDC);
  }
  return CMFCOutlookBarPane::InternalAddButton(this, v12, lpszLabel, iIdCommand, iInsertAt);
}

```

## disassembly

```asm
0x18009b170  mov     rax, rsp
0x18009b173  mov     [rax+8], rbx
0x18009b177  mov     [rax+10h], rsi
0x18009b17b  mov     [rax+18h], rdi
0x18009b17f  push    rbp
0x18009b180  push    r12
0x18009b182  push    r13
0x18009b184  push    r14
0x18009b186  push    r15
0x18009b188  lea     rbp, [rax-4Fh]
0x18009b18c  sub     rsp, 0F0h
0x18009b193  mov     r12d, iIdCommand
0x18009b196  mov     r13, lpszLabel
0x18009b199  mov     rsi, hIcon
0x18009b19c  mov     r14, this
0x18009b19f  xor     r15d, r15d
0x18009b1a2  test    hIcon, hIcon
0x18009b1a5  jz      loc_18009B39E
0x18009b1ab  lea     hIcon, [rbp+47h+iconInfo.yHotspot]; piconinfo
0x18009b1af  mov     this, rsi; hIcon
0x18009b1b2  call    cs:__imp_GetIconInfo
0x18009b1b8  lea     lpszLabel, [rbp+47h+bitmap.bmHeight]; pv
0x18009b1bc  lea     edx, [r15+20h]; c
0x18009b1c0  mov     this, [rbp+47h+dc.__vftable]; h
0x18009b1c4  call    cs:__imp_GetObjectW
0x18009b1ca  mov     ebx, [rbp+47h+bitmap.bmWidthBytes]
0x18009b1cd  mov     edi, dword ptr [rbp+47h+bitmap.bmPlanes]
0x18009b1d0  cmp     [rbp+47h+arg_28], r15d
0x18009b1d4  jz      short loc_18009B213
0x18009b1d6  cmp     cs:?m_Images@CMFCOutlookBarPane@@1VCMFCToolBarImages@@A.m_iCount, r15d; CMFCToolBarImages CMFCOutlookBarPane::m_Images ...
0x18009b1dd  jnz     short loc_18009B1F7
0x18009b1df  mov     cs:?m_csImage@CMFCOutlookBarPane@@1VCSize@@A.cx, ebx; CSize CMFCOutlookBarPane::m_csImage ...
0x18009b1e5  mov     cs:?m_csImage@CMFCOutlookBarPane@@1VCSize@@A.cy, edi; CSize CMFCOutlookBarPane::m_csImage ...
0x18009b1eb  mov     cs:?m_Images@CMFCOutlookBarPane@@1VCMFCToolBarImages@@A.m_sizeImage.cx, ebx; CMFCToolBarImages CMFCOutlookBarPane::m_Images ...
0x18009b1f1  mov     cs:?m_Images@CMFCOutlookBarPane@@1VCMFCToolBarImages@@A.m_sizeImage.cy, edi; CMFCToolBarImages CMFCOutlookBarPane::m_Images ...
0x18009b1f7  mov     r8d, 1; bAlphaBlend
0x18009b1fd  mov     hIcon, rsi; hIcon
0x18009b200  lea     this, ?m_Images@CMFCOutlookBarPane@@1VCMFCToolBarImages@@A; this
0x18009b207  call    ?AddIcon@CMFCToolBarImages@@QEAAHPEAUHICON__@@H@Z; CMFCToolBarImages::AddIcon(HICON__ *,int)
0x18009b20c  mov     ebx, eax
0x18009b20e  jmp     loc_18009B366
0x18009b213  mov     hIcon, r14; pWnd
0x18009b216  lea     this, [rbp+47h+dc.m_hDC]; this
0x18009b21a  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x18009b21f  nop
0x18009b220  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18009b227  mov     [rbp+47h+dcMem.m_hDC], rax
0x18009b22b  xorps   xmm0, xmm0
0x18009b22e  movdqu  xmmword ptr [rbp+47h+dcMem.m_hAttribDC], xmm0
0x18009b233  mov     [rbp+47h+iconInfo.fIcon], r15d
0x18009b237  mov     this, [rbp+47h+dc.m_hAttribDC]; hdc
0x18009b23b  call    cs:__imp_CreateCompatibleDC
0x18009b241  mov     hIcon, rax; hDC
0x18009b244  lea     this, [rbp+47h+dcMem.m_hDC]; this
0x18009b248  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18009b24d  mov     [rbp+47h+dcMem.__vftable], r15
0x18009b251  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18009b258  mov     [rbp+47h+bmp.m_hObject], rax
0x18009b25c  mov     r8d, edi; cy
0x18009b25f  mov     edx, ebx; cx
0x18009b261  mov     this, [rbp+47h+dc.m_hAttribDC]; hdc
0x18009b265  call    cs:__imp_CreateCompatibleBitmap
0x18009b26b  mov     hIcon, rax; hObject
0x18009b26e  lea     this, [rbp+47h+bmp.m_hObject]; this
0x18009b272  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18009b277  mov     hIcon, [rbp+47h+dcMem.__vftable]; h
0x18009b27b  mov     this, [rbp+47h+dcMem.m_hAttribDC]; hdc
0x18009b27f  call    cs:__imp_SelectObject
0x18009b285  mov     this, rax; h
0x18009b288  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18009b28d  mov     r15, rax
0x18009b290  mov     eax, [r14+1354h]
0x18009b297  cmp     eax, 0FFFFFFFFh
0x18009b29a  jz      short loc_18009B2B5
0x18009b29c  mov     [rsp+110h+clr], eax; clr
0x18009b2a0  mov     [rsp+110h+cy], edi; cy
0x18009b2a4  mov     iIdCommand, ebx; cx
0x18009b2a7  xor     r8d, r8d; y
0x18009b2aa  xor     edx, edx; x
0x18009b2ac  lea     this, [rbp+47h+dcMem.m_hDC]; this
0x18009b2b0  call    ?FillSolidRect@CDC@@QEAAXHHHHK@Z; CDC::FillSolidRect(int,int,int,int,ulong)
0x18009b2b5  mov     [rsp+110h+diFlags], 3; diFlags
0x18009b2bd  and     qword ptr [rsp+110h+var_D8], 0
0x18009b2c3  and     dword ptr [rsp+110h+var_E0], 0
0x18009b2c8  mov     [rsp+110h+clr], edi; cyWidth
0x18009b2cc  mov     [rsp+110h+cy], ebx; cxWidth
0x18009b2d0  mov     r9, rsi; hIcon
0x18009b2d3  xor     r8d, r8d; yTop
0x18009b2d6  xor     edx, edx; xLeft
0x18009b2d8  mov     this, [rbp+47h+dcMem.m_hAttribDC]; hdc
0x18009b2dc  call    cs:__imp_DrawIconEx
0x18009b2e2  test    r15, r15
0x18009b2e5  jnz     short loc_18009B2EB
0x18009b2e7  xor     edx, edx
0x18009b2e9  jmp     short loc_18009B2EF
0x18009b2eb  mov     hIcon, [r15+8]; h
0x18009b2ef  mov     this, [rbp+47h+dcMem.m_hAttribDC]; hdc
0x18009b2f3  call    cs:__imp_SelectObject
0x18009b2f9  mov     this, rax; h
0x18009b2fc  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18009b301  mov     this, [rbp+47h+dc.__vftable]; ho
0x18009b305  call    cs:__imp_DeleteObject
0x18009b30b  mov     this, [rbp+47h+iconInfo.hbmColor]; ho
0x18009b30f  call    cs:__imp_DeleteObject
0x18009b315  mov     hIcon, [rbp+47h+dcMem.__vftable]; hBitmap
0x18009b319  mov     this, r14; this
0x18009b31c  call    ?AddBitmapImage@CMFCOutlookBarPane@@IEAAHPEAUHBITMAP__@@@Z; CMFCOutlookBarPane::AddBitmapImage(HBITMAP__ *)
0x18009b321  mov     ebx, eax
0x18009b323  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18009b32a  mov     [rbp+47h+bmp.m_hObject], rax
0x18009b32e  lea     this, [rbp+47h+bmp.m_hObject]; this
0x18009b332  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18009b337  nop
0x18009b338  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18009b33f  mov     [rbp+47h+dcMem.m_hDC], rax
0x18009b343  cmp     [rbp+47h+dcMem.m_hAttribDC], 0
0x18009b348  jz      short loc_18009B35D
0x18009b34a  lea     this, [rbp+47h+dcMem.m_hDC]; this
0x18009b34e  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18009b353  mov     this, rax; hdc
0x18009b356  call    cs:__imp_DeleteDC
0x18009b35c  nop
0x18009b35d  lea     this, [rbp+47h+dc.m_hDC]; this
0x18009b361  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x18009b366  mov     eax, [rbp+47h+arg_20]
0x18009b369  mov     [rsp+110h+cy], eax; iInsertAt
0x18009b36d  mov     iIdCommand, r12d; iIdCommand
0x18009b370  mov     lpszLabel, r13; lpszLabel
0x18009b373  mov     edx, ebx; iImageIndex
0x18009b375  mov     this, r14; this
0x18009b378  call    ?InternalAddButton@CMFCOutlookBarPane@@IEAAHHPEB_WIH@Z; CMFCOutlookBarPane::InternalAddButton(int,wchar_t const *,uint,int)
0x18009b37d  lea     r11, [rsp+110h+var_20]
0x18009b385  mov     rbx, [r11+30h]
0x18009b389  mov     rsi, [r11+38h]
0x18009b38d  mov     rdi, [r11+40h]
0x18009b391  mov     rsp, r11
0x18009b394  pop     r15
0x18009b396  pop     r14
0x18009b398  pop     r13
0x18009b39a  pop     r12
0x18009b39c  pop     rbp
0x18009b39d  retn
0x18009b39e  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
