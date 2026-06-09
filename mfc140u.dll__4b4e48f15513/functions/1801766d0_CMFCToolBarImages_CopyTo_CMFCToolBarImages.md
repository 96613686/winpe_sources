# CMFCToolBarImages::CopyTo(CMFCToolBarImages &)

- ea: `0x1801766d0`
- end: `0x180176a64`
- name: `?CopyTo@CMFCToolBarImages@@QEAAHAEAV1@@Z`
- size: `916`
- prototype: `int __fastcall(CMFCToolBarImages *this, CMFCToolBarImages *dest)`
- caller_count: `17`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180092220`
- `0x180092260`
- `0x1800eefc0`
- `0x1800ef300`
- `0x1800f3780`
- `0x1800f78b0`
- `0x1800fcd90`
- `0x1800fcec0`
- `0x1800fd380`
- `0x1800fd790`
- `0x1801173b0`
- `0x180117af0`
- `0x180117df0`
- `0x180119260`
- `0x18012db10`
- `0x180154c10`
- `0x180161ee0`

## callees

- `0x180007de4`
- `0x18000e0e0`
- `0x180012654`
- `0x180023ffc`
- `0x180030880`
- `0x1801766d0`
- `0x180176a70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802c4640`
- `0x1802c56e6`

## import_xrefs

- `api-ms-win-crt-utility-l1-1-0!labs` at `0x180176743`
- `api-ms-win-crt-utility-l1-1-0!labs` at `0x180176743`
- `GDI32!DeleteDC` at `0x180176912`
- `GDI32!DeleteDC` at `0x180176948`
- `GDI32!DeleteDC` at `0x180176912`
- `GDI32!DeleteDC` at `0x180176948`
- `GDI32!CreateDIBSection` at `0x180176833`
- `GDI32!CreateDIBSection` at `0x180176833`
- `GDI32!BitBlt` at `0x1801768ca`
- `GDI32!BitBlt` at `0x1801768ca`
- `GDI32!CreateCompatibleBitmap` at `0x180176846`
- `GDI32!CreateCompatibleBitmap` at `0x180176846`
- `GDI32!DeleteObject` at `0x1801768e9`
- `GDI32!DeleteObject` at `0x1801768e9`
- `GDI32!SelectObject` at `0x180176790`
- `GDI32!SelectObject` at `0x18017688f`
- `GDI32!SelectObject` at `0x1801768d7`
- `GDI32!SelectObject` at `0x180176921`
- `GDI32!SelectObject` at `0x180176790`
- `GDI32!SelectObject` at `0x18017688f`
- `GDI32!SelectObject` at `0x1801768d7`
- `GDI32!SelectObject` at `0x180176921`
- `GDI32!CreateCompatibleDC` at `0x18017676c`
- `GDI32!CreateCompatibleDC` at `0x180176875`
- `GDI32!CreateCompatibleDC` at `0x18017676c`
- `GDI32!CreateCompatibleDC` at `0x180176875`
- `GDI32!GetObjectW` at `0x180176731`
- `GDI32!GetObjectW` at `0x1801767d1`
- `GDI32!GetObjectW` at `0x180176731`
- `GDI32!GetObjectW` at `0x1801767d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMFCToolBarImages::CopyTo(CMFCToolBarImages *this, CMFCToolBarImages *dest)
{
  int v5; // r12d
  int bmWidth; // r13d
  HDC CompatibleDC; // rax
  HBITMAP__ *m_hbmImageWell; // rdx
  HGDIOBJ v9; // r14
  HBITMAP CompatibleBitmap; // rax
  HBITMAP__ *v11; // rsi
  HDC v12; // rax
  HGDIOBJ v13; // r15
  HDC v14; // rax
  HDC v15; // rax
  CList<unsigned int,unsigned int>::CNode *m_pNodeHead; // rsi
  unsigned int data; // r14d
  CList<HINSTANCE__ *,HINSTANCE__ *>::CNode *v18; // rdi
  CMFCButton *v19; // rdx
  void *iOffset; // [rsp+50h] [rbp-B0h] BYREF
  CDC memDCSrc; // [rsp+58h] [rbp-A8h] BYREF
  CDC memDCDst; // [rsp+78h] [rbp-88h] BYREF
  tagBITMAP bmp; // [rsp+98h] [rbp-68h] BYREF
  tagBITMAPINFO bi; // [rsp+B8h] [rbp-48h] BYREF
  tagDIBSECTION pv; // [rsp+F0h] [rbp-10h] BYREF

  if ( dest->m_bIsTemporary )
    return 0;
  if ( dest->m_hbmImageWell )
    CMFCToolBarImages::Clear(dest);
  if ( GetObjectW(this->m_hbmImageWell, 32, &bmp) == 32 )
  {
    v5 = labs(bmp.bmHeight);
    bmWidth = bmp.bmWidth;
    memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
    memset(&memDCSrc.m_hDC, 0, 20);
    CompatibleDC = CreateCompatibleDC(0);
    CDC::Attach(&memDCSrc, CompatibleDC);
    m_hbmImageWell = this->m_hbmImageWell;
    if ( m_hbmImageWell )
      v9 = SelectObject(memDCSrc.m_hDC, m_hbmImageWell);
    else
      v9 = 0;
    if ( v9 )
    {
      pv.dsBm.bmType = 0;
      memset_0(&pv.dsBm.bmWidth, 0, 0x64u);
      if ( bmp.bmBitsPixel >= 0x18u && GetObjectW(this->m_hbmImageWell, 104, &pv) )
      {
        bi.bmiHeader.biSize = 40;
        bi.bmiHeader.biWidth = bmp.bmWidth;
        bi.bmiHeader.biHeight = bmp.bmHeight;
        bi.bmiHeader.biPlanes = bmp.bmPlanes;
        bi.bmiHeader.biBitCount = bmp.bmBitsPixel;
        memset(&bi.bmiHeader.biCompression, 0, 28);
        iOffset = 0;
        CompatibleBitmap = CreateDIBSection(memDCSrc.m_hDC, &bi, 0, &iOffset, 0, 0);
      }
      else
      {
        CompatibleBitmap = CreateCompatibleBitmap(memDCSrc.m_hDC, bmWidth, v5);
      }
      v11 = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        memDCDst.__vftable = (CDC_vtbl *)CDC::`vftable';
        memset(&memDCDst.m_hDC, 0, 20);
        v12 = CreateCompatibleDC(memDCSrc.m_hDC);
        CDC::Attach(&memDCDst, v12);
        v13 = SelectObject(memDCDst.m_hDC, v11);
        if ( v13 )
        {
          BitBlt(memDCDst.m_hDC, 0, 0, bmWidth, v5, memDCSrc.m_hDC, 0, 0, 0xCC0020u);
          SelectObject(memDCDst.m_hDC, v13);
          dest->m_hbmImageWell = v11;
        }
        else
        {
          DeleteObject(v11);
        }
        memDCDst.__vftable = (CDC_vtbl *)CDC::`vftable';
        if ( memDCDst.m_hDC )
        {
          v14 = CDC::Detach(&memDCDst);
          DeleteDC(v14);
        }
      }
      SelectObject(memDCSrc.m_hDC, v9);
    }
    memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
    if ( memDCSrc.m_hDC )
    {
      v15 = CDC::Detach(&memDCSrc);
      DeleteDC(v15);
    }
  }
  dest->m_sizeImage = this->m_sizeImage;
  dest->m_sizeImageDest = this->m_sizeImageDest;
  dest->m_bUserImagesList = this->m_bUserImagesList;
  ATL::CSimpleStringT<wchar_t,1>::operator=(
    &dest->m_strUDLPath,
    (const ATL::CSimpleStringT<wchar_t,0> *)&this->m_strUDLPath);
  dest->m_bModified = this->m_bModified;
  dest->m_iCount = this->m_iCount;
  dest->m_clrTransparent = this->m_clrTransparent;
  dest->m_bReadOnly = this->m_bReadOnly;
  dest->m_clrImageShadow = this->m_clrImageShadow;
  dest->m_bFadeInactive = this->m_bFadeInactive;
  dest->m_nBitsPerPixel = this->m_nBitsPerPixel;
  dest->m_dblScale = this->m_dblScale;
  dest->m_sizeImageOriginal = this->m_sizeImageOriginal;
  m_pNodeHead = this->m_lstOrigResIds.m_pNodeHead;
  while ( m_pNodeHead )
  {
    data = m_pNodeHead->data;
    m_pNodeHead = m_pNodeHead->pNext;
    CList<unsigned int,unsigned int>::AddTail(&dest->m_lstOrigResIds, data);
    LODWORD(iOffset) = -1;
    if ( CMap<unsigned int,unsigned int,int,int>::Lookup(
           (CMap<int,int,int,int> *)&this->m_mapOrigResOffsets,
           data,
           (int *)&iOffset) )
    {
      CMap<int,int,int,int>::SetAt(
        (CMap<int,int,unsigned int,unsigned int> *)&dest->m_mapOrigResOffsets,
        data,
        (unsigned int)iOffset);
    }
  }
  v18 = this->m_lstOrigResInstances.m_pNodeHead;
  while ( v18 )
  {
    v19 = (CMFCButton *)v18->data;
    v18 = v18->pNext;
    CList<CMFCRibbonBaseElement *,CMFCRibbonBaseElement *>::AddTail(
      (CList<CMFCButton *,CMFCButton *> *)&dest->m_lstOrigResInstances,
      v19);
  }
  return 1;
}

```

## disassembly

```asm
0x1801766d0  mov     [rsp-8+arg_10], rbx
0x1801766d5  push    rbp
0x1801766d6  push    rsi
0x1801766d7  push    rdi
0x1801766d8  push    r12
0x1801766da  push    r13
0x1801766dc  push    r14
0x1801766de  push    r15
0x1801766e0  lea     rbp, [rsp-70h]
0x1801766e5  sub     rsp, 170h
0x1801766ec  mov     rax, cs:__security_cookie
0x1801766f3  xor     rax, rsp
0x1801766f6  mov     [rbp+0A0h+var_40], rax
0x1801766fa  mov     rbx, dest
0x1801766fd  mov     rdi, this
0x180176700  xor     r15d, r15d
0x180176703  cmp     [dest+2Ch], r15d
0x180176707  jz      short loc_180176710
0x180176709  xor     eax, eax
0x18017670b  jmp     loc_180176A3D
0x180176710  cmp     [dest+0A0h], r15
0x180176717  jz      short loc_180176721
0x180176719  mov     this, rbx; this
0x18017671c  call    ?Clear@CMFCToolBarImages@@QEAAXXZ; CMFCToolBarImages::Clear(void)
0x180176721  lea     r8, [rbp+0A0h+bmp]; pv
0x180176725  mov     edx, 20h ; ' '; c
0x18017672a  mov     this, [rdi+0A0h]; h
0x180176731  call    cs:__imp_GetObjectW
0x180176737  cmp     eax, 20h ; ' '
0x18017673a  jnz     loc_18017694F
0x180176740  mov     ecx, [rbp+0A0h+bmp.bmHeight]; Number
0x180176743  call    cs:__imp_labs
0x180176749  mov     r12d, eax
0x18017674c  mov     r13d, [rbp+0A0h+bmp.bmWidth]
0x180176750  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180176757  mov     [rsp+1A0h+memDCSrc.__vftable], rax
0x18017675c  xorps   xmm0, xmm0
0x18017675f  movdqu  xmmword ptr [rsp+1A0h+memDCSrc.m_hDC], xmm0
0x180176765  mov     [rsp+1A0h+memDCSrc.m_bPrinting], r15d
0x18017676a  xor     ecx, ecx; hdc
0x18017676c  call    cs:__imp_CreateCompatibleDC
0x180176772  mov     dest, rax; hDC
0x180176775  lea     this, [rsp+1A0h+memDCSrc]; this
0x18017677a  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18017677f  mov     dest, [rdi+0A0h]; h
0x180176786  test    dest, dest
0x180176789  jz      short loc_18017679B
0x18017678b  mov     this, [rsp+1A0h+memDCSrc.m_hDC]; hdc
0x180176790  call    cs:__imp_SelectObject
0x180176796  mov     r14, rax
0x180176799  jmp     short loc_18017679E
0x18017679b  mov     r14, r15
0x18017679e  test    r14, r14
0x1801767a1  jz      loc_180176928
0x1801767a7  mov     [rbp+0A0h+pv.dsBm.bmType], r15d
0x1801767ab  xor     edx, edx; Val
0x1801767ad  lea     r8d, [dest+64h]; Size
0x1801767b1  lea     this, [rbp+0A0h+pv.dsBm.bmWidth]; void *
0x1801767b5  call    memset_0
0x1801767ba  cmp     [rbp+0A0h+bmp.bmBitsPixel], 18h
0x1801767bf  jb      short loc_18017683B
0x1801767c1  lea     r8, [rbp+0A0h+pv]; pv
0x1801767c5  mov     edx, 68h ; 'h'; c
0x1801767ca  mov     this, [rdi+0A0h]; h
0x1801767d1  call    cs:__imp_GetObjectW
0x1801767d7  test    eax, eax
0x1801767d9  jz      short loc_18017683B
0x1801767db  xorps   xmm0, xmm0
0x1801767de  xor     eax, eax
0x1801767e0  movups  xmmword ptr [rbp+0A0h+bi.bmiHeader.biWidth], xmm0
0x1801767e4  movups  xmmword ptr [rbp+0A0h+bi.bmiHeader.biSizeImage], xmm0
0x1801767e8  mov     qword ptr [rbp+0A0h+bi.bmiHeader.biClrImportant], rax
0x1801767ec  mov     [rbp+0A0h+bi.bmiHeader.biSize], 28h ; '('
0x1801767f3  mov     eax, [rbp+0A0h+bmp.bmWidth]
0x1801767f6  mov     [rbp+0A0h+bi.bmiHeader.biWidth], eax
0x1801767f9  mov     eax, [rbp+0A0h+bmp.bmHeight]
0x1801767fc  mov     [rbp+0A0h+bi.bmiHeader.biHeight], eax
0x1801767ff  movzx   eax, [rbp+0A0h+bmp.bmPlanes]
0x180176803  mov     [rbp+0A0h+bi.bmiHeader.biPlanes], ax
0x180176807  movzx   eax, [rbp+0A0h+bmp.bmBitsPixel]
0x18017680b  mov     [rbp+0A0h+bi.bmiHeader.biBitCount], ax
0x18017680f  mov     [rbp+0A0h+bi.bmiHeader.biCompression], r15d
0x180176813  mov     [rsp+1A0h+iOffset], r15
0x180176818  mov     [rsp+1A0h+offset], r15d; offset
0x18017681d  mov     [rsp+1A0h+hSection], r15; hSection
0x180176822  lea     r9, [rsp+1A0h+iOffset]; ppvBits
0x180176827  xor     r8d, r8d; usage
0x18017682a  lea     dest, [rbp+0A0h+bi]; pbmi
0x18017682e  mov     this, [rsp+1A0h+memDCSrc.m_hDC]; hdc
0x180176833  call    cs:__imp_CreateDIBSection
0x180176839  jmp     short loc_18017684C
0x18017683b  mov     r8d, r12d; cy
0x18017683e  mov     edx, r13d; cx
0x180176841  mov     this, [rsp+1A0h+memDCSrc.m_hDC]; hdc
0x180176846  call    cs:__imp_CreateCompatibleBitmap
0x18017684c  mov     rsi, rax
0x18017684f  test    rax, rax
0x180176852  jz      loc_180176919
0x180176858  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18017685f  mov     [rsp+1A0h+memDCDst.__vftable], rax
0x180176864  xorps   xmm0, xmm0
0x180176867  movdqu  xmmword ptr [rbp+0A0h+memDCDst.m_hDC], xmm0
0x18017686c  mov     [rbp+0A0h+memDCDst.m_bPrinting], r15d
0x180176870  mov     this, [rsp+1A0h+memDCSrc.m_hDC]; hdc
0x180176875  call    cs:__imp_CreateCompatibleDC
0x18017687b  mov     dest, rax; hDC
0x18017687e  lea     this, [rsp+1A0h+memDCDst]; this
0x180176883  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180176888  mov     dest, rsi; h
0x18017688b  mov     this, [rbp+0A0h+memDCDst.m_hDC]; hdc
0x18017688f  call    cs:__imp_SelectObject
0x180176895  mov     r15, rax
0x180176898  test    rax, rax
0x18017689b  jz      short loc_1801768E6
0x18017689d  mov     [rsp+1A0h+rop], 0CC0020h; rop
0x1801768a5  and     [rsp+1A0h+var_168], 0
0x1801768aa  and     [rsp+1A0h+var_170], 0
0x1801768af  mov     this, [rsp+1A0h+memDCSrc.m_hDC]
0x1801768b4  mov     qword ptr [rsp+1A0h+offset], this; hdcSrc
0x1801768b9  mov     dword ptr [rsp+1A0h+hSection], r12d; cy
0x1801768be  mov     r9d, r13d; cx
0x1801768c1  xor     r8d, r8d; y
0x1801768c4  xor     edx, edx; x
0x1801768c6  mov     this, [rbp+0A0h+memDCDst.m_hDC]; hdc
0x1801768ca  call    cs:__imp_BitBlt
0x1801768d0  mov     dest, r15; h
0x1801768d3  mov     this, [rbp+0A0h+memDCDst.m_hDC]; hdc
0x1801768d7  call    cs:__imp_SelectObject
0x1801768dd  mov     [rbx+0A0h], rsi
0x1801768e4  jmp     short loc_1801768F0
0x1801768e6  mov     this, rsi; ho
0x1801768e9  call    cs:__imp_DeleteObject
0x1801768ef  nop
0x1801768f0  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1801768f7  mov     [rsp+1A0h+memDCDst.__vftable], rax
0x1801768fc  xor     r15d, r15d
0x1801768ff  cmp     [rbp+0A0h+memDCDst.m_hDC], r15
0x180176903  jz      short loc_180176919
0x180176905  lea     this, [rsp+1A0h+memDCDst]; this
0x18017690a  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18017690f  mov     this, rax; hdc
0x180176912  call    cs:__imp_DeleteDC
0x180176918  nop
0x180176919  mov     dest, r14; h
0x18017691c  mov     this, [rsp+1A0h+memDCSrc.m_hDC]; hdc
0x180176921  call    cs:__imp_SelectObject
0x180176927  nop
0x180176928  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x18017692f  mov     [rsp+1A0h+memDCSrc.__vftable], rax
0x180176934  cmp     [rsp+1A0h+memDCSrc.m_hDC], r15
0x180176939  jz      short loc_18017694F
0x18017693b  lea     this, [rsp+1A0h+memDCSrc]; this
0x180176940  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180176945  mov     this, rax; hdc
0x180176948  call    cs:__imp_DeleteDC
0x18017694e  nop
0x18017694f  mov     rax, [rdi+68h]
0x180176953  mov     [rbx+68h], rax
0x180176957  mov     rax, [rdi+78h]
0x18017695b  mov     [rbx+78h], rax
0x18017695f  mov     eax, [rdi+1Ch]
0x180176962  mov     [rbx+1Ch], eax
0x180176965  lea     dest, [rdi+0B8h]; strSrc
0x18017696c  lea     this, [rbx+0B8h]; this
0x180176973  call    ??4?$CSimpleStringT@_W$00@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<wchar_t,1>::operator=(ATL::CSimpleStringT<wchar_t,1> const &)
0x180176978  mov     eax, [rdi+20h]
0x18017697b  mov     [rbx+20h], eax
0x18017697e  mov     eax, [rdi+8]
0x180176981  mov     [rbx+8], eax
0x180176984  mov     eax, [rdi+0D8h]
0x18017698a  mov     [rbx+0D8h], eax
0x180176990  mov     eax, [rdi+28h]
0x180176993  mov     [rbx+28h], eax
0x180176996  mov     eax, [rdi+0E0h]
0x18017699c  mov     [rbx+0E0h], eax
0x1801769a2  mov     eax, [rdi+30h]
0x1801769a5  mov     [rbx+30h], eax
0x1801769a8  mov     eax, [rdi+0Ch]
0x1801769ab  mov     [rbx+0Ch], eax
0x1801769ae  mov     rax, [rdi+0E8h]
0x1801769b5  mov     [rbx+0E8h], rax
0x1801769bc  mov     rax, [rdi+70h]
0x1801769c0  mov     [rbx+70h], rax
0x1801769c4  mov     rsi, [rdi+0F8h]
0x1801769cb  jmp     short loc_180176A14
0x1801769cd  mov     r14d, [rsi+10h]
0x1801769d1  mov     rsi, [rsi]
0x1801769d4  mov     edx, r14d; newElement
0x1801769d7  lea     this, [rbx+0F0h]; this
0x1801769de  call    ?AddTail@?$CList@II@@QEAAPEAU__POSITION@@I@Z; CList<uint,uint>::AddTail(uint)
0x1801769e3  or      dword ptr [rsp+1A0h+iOffset], 0FFFFFFFFh
0x1801769e8  lea     r8, [rsp+1A0h+iOffset]; rValue
0x1801769ed  mov     edx, r14d; key
0x1801769f0  lea     this, [rdi+160h]; this
0x1801769f7  call    ?Lookup@?$CMap@IIHH@@QEBAHIAEAH@Z; CMap<uint,uint,int,int>::Lookup(uint,int &)
0x1801769fc  test    eax, eax
0x1801769fe  jz      short loc_180176A14
0x180176a00  lea     this, [rbx+160h]; this
0x180176a07  mov     r8d, dword ptr [rsp+1A0h+iOffset]; newValue
0x180176a0c  mov     edx, r14d; key
0x180176a0f  call    ?SetAt@?$CMap@HHHH@@QEAAXHH@Z; CMap<int,int,int,int>::SetAt(int,int)
0x180176a14  test    rsi, rsi
0x180176a17  jnz     short loc_1801769CD
0x180176a19  mov     rdi, [rdi+130h]
0x180176a20  jmp     short loc_180176A35
0x180176a22  mov     dest, [rdi+10h]; newElement
0x180176a26  mov     rdi, [rdi]
0x180176a29  lea     this, [rbx+128h]; this
0x180176a30  call    ?AddTail@?$CList@PEAVCMFCRibbonBaseElement@@PEAV1@@@QEAAPEAU__POSITION@@PEAVCMFCRibbonBaseElement@@@Z; CList<CMFCRibbonBaseElement *,CMFCRibbonBaseElement *>::AddTail(CMFCRibbonBaseElement *)
0x180176a35  test    rdi, rdi
0x180176a38  jnz     short loc_180176A22
0x180176a3a  lea     eax, [rdi+1]
0x180176a3d  mov     this, [rbp+0A0h+var_40]
0x180176a41  xor     this, rsp; StackCookie
0x180176a44  call    __security_check_cookie
0x180176a49  mov     rbx, [rsp+1A0h+arg_10]
0x180176a51  add     rsp, 170h
0x180176a58  pop     r15
0x180176a5a  pop     r14
0x180176a5c  pop     r13
0x180176a5e  pop     r12
0x180176a60  pop     rdi
0x180176a61  pop     rsi
0x180176a62  pop     rbp
0x180176a63  retn
```
