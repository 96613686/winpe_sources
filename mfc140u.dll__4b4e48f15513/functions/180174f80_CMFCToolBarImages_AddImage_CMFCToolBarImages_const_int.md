# CMFCToolBarImages::AddImage(CMFCToolBarImages const &,int)

- ea: `0x180174f80`
- end: `0x180175266`
- name: `?AddImage@CMFCToolBarImages@@QEAAHAEBV1@H@Z`
- size: `742`
- prototype: `int __fastcall(CMFCToolBarImages *this, const CMFCToolBarImages *imageList, int nIndex)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800f74a0`

## callees

- `0x18001d090`
- `0x180174b20`
- `0x180174f80`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b0720`
- `0x1802b07d0`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802c4640`
- `0x1802c56e6`

## import_xrefs

- `GDI32!DeleteDC` at `0x180175213`
- `GDI32!DeleteDC` at `0x180175231`
- `GDI32!DeleteDC` at `0x180175213`
- `GDI32!DeleteDC` at `0x180175231`
- `GDI32!CreateDIBSection` at `0x180175121`
- `GDI32!CreateDIBSection` at `0x180175121`
- `GDI32!BitBlt` at `0x180175198`
- `GDI32!BitBlt` at `0x180175198`
- `GDI32!CreateCompatibleBitmap` at `0x180175134`
- `GDI32!CreateCompatibleBitmap` at `0x180175134`
- `GDI32!SelectObject` at `0x180175050`
- `GDI32!SelectObject` at `0x180175151`
- `GDI32!SelectObject` at `0x1801751b0`
- `GDI32!SelectObject` at `0x1801751ca`
- `GDI32!SelectObject` at `0x180175050`
- `GDI32!SelectObject` at `0x180175151`
- `GDI32!SelectObject` at `0x1801751b0`
- `GDI32!SelectObject` at `0x1801751ca`
- `GDI32!CreateCompatibleDC` at `0x18017502e`
- `GDI32!CreateCompatibleDC` at `0x180175072`
- `GDI32!CreateCompatibleDC` at `0x18017502e`
- `GDI32!CreateCompatibleDC` at `0x180175072`
- `GDI32!GetObjectW` at `0x1801750c0`
- `GDI32!GetObjectW` at `0x1801750c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMFCToolBarImages::AddImage(CMFCToolBarImages *this, const CMFCToolBarImages *imageList, int nIndex)
{
  HDC CompatibleDC; // rax
  HBITMAP__ *m_hbmImageWell; // rdx
  HGDIOBJ v8; // rsi
  HDC v9; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v11; // rax
  CGdiObject *v12; // r15
  void *m_hObject; // rdx
  HGDIOBJ v14; // rax
  unsigned int v15; // ebx
  HDC v16; // rax
  HDC v17; // rax
  CBitmap bitmap; // [rsp+50h] [rbp-B0h] BYREF
  CDC memDCDest; // [rsp+60h] [rbp-A0h] BYREF
  CDC memDCSrc; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *pBits; // [rsp+A0h] [rbp-60h] BYREF
  CWindowDC dc; // [rsp+A8h] [rbp-58h] BYREF
  tagBITMAPINFO bi; // [rsp+D0h] [rbp-30h] BYREF
  tagDIBSECTION pv; // [rsp+100h] [rbp+0h] BYREF

  if ( nIndex < 0 || nIndex >= imageList->m_iCount )
    return 0xFFFFFFFFLL;
  CWindowDC::CWindowDC(&dc, 0);
  if ( this->m_dblScale == 1.0 )
  {
    this->m_sizeImage = imageList->m_sizeImage;
    this->m_sizeImageDest = imageList->m_sizeImageDest;
    this->m_clrTransparent = imageList->m_clrTransparent;
    this->m_clrImageShadow = imageList->m_clrImageShadow;
    this->m_bFadeInactive = imageList->m_bFadeInactive;
    this->m_nBitsPerPixel = imageList->m_nBitsPerPixel;
  }
  memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&memDCSrc.m_hDC, 0, 20);
  CompatibleDC = CreateCompatibleDC(0);
  CDC::Attach(&memDCSrc, CompatibleDC);
  m_hbmImageWell = imageList->m_hbmImageWell;
  if ( m_hbmImageWell )
    v8 = SelectObject(memDCSrc.m_hDC, m_hbmImageWell);
  else
    v8 = 0;
  memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&memDCDest.m_hDC, 0, 20);
  v9 = CreateCompatibleDC(0);
  CDC::Attach(&memDCDest, v9);
  bitmap.m_hObject = 0;
  bitmap.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  pv.dsBm.bmType = 0;
  memset_0(&pv.dsBm.bmWidth, 0, 0x64u);
  if ( imageList->m_nBitsPerPixel >= 24 && GetObjectW(this->m_hbmImageWell, 104, &pv) )
  {
    memset(&bi.bmiHeader.biWidth, 0, 40);
    bi.bmiHeader.biSize = 40;
    bi.bmiHeader.biWidth = imageList->m_sizeImage.cx;
    bi.bmiHeader.biHeight = imageList->m_sizeImage.cy;
    bi.bmiHeader.biPlanes = pv.dsBm.bmPlanes;
    bi.bmiHeader.biBitCount = pv.dsBm.bmBitsPixel;
    bi.bmiHeader.biCompression = 0;
    pBits = 0;
    CompatibleBitmap = CreateDIBSection(dc.m_hDC, &bi, 0, (void **)&pBits, 0, 0);
  }
  else
  {
    CompatibleBitmap = CreateCompatibleBitmap(dc.m_hDC, imageList->m_sizeImage.cx, imageList->m_sizeImage.cy);
  }
  CGdiObject::Attach(&bitmap, CompatibleBitmap);
  v11 = SelectObject(memDCDest.m_hDC, bitmap.m_hObject);
  v12 = CGdiObject::FromHandle(v11);
  BitBlt(
    memDCDest.m_hDC,
    0,
    0,
    imageList->m_sizeImage.cx,
    imageList->m_sizeImage.cy,
    memDCSrc.m_hDC,
    nIndex * imageList->m_sizeImage.cx,
    0,
    0xCC0020u);
  if ( v12 )
    m_hObject = v12->m_hObject;
  else
    m_hObject = 0;
  v14 = SelectObject(memDCDest.m_hDC, m_hObject);
  CGdiObject::FromHandle(v14);
  if ( v8 )
    SelectObject(memDCSrc.m_hDC, v8);
  v15 = CMFCToolBarImages::AddImage(this, (HBITMAP__ *)bitmap.m_hObject, 0);
  bitmap.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&bitmap);
  memDCDest.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( memDCDest.m_hDC )
  {
    v16 = CDC::Detach(&memDCDest);
    DeleteDC(v16);
  }
  memDCSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( memDCSrc.m_hDC )
  {
    v17 = CDC::Detach(&memDCSrc);
    DeleteDC(v17);
  }
  CWindowDC::~CWindowDC(&dc);
  return v15;
}

```

## disassembly

```asm
0x180174f80  push    rbp
0x180174f82  push    rbx
0x180174f83  push    rsi
0x180174f84  push    rdi
0x180174f85  push    r13
0x180174f87  push    r14
0x180174f89  push    r15
0x180174f8b  lea     rbp, [rsp-80h]
0x180174f90  sub     rsp, 180h
0x180174f97  mov     rax, cs:__security_cookie
0x180174f9e  xor     rax, rsp
0x180174fa1  mov     [rbp+0B0h+var_40], rax
0x180174fa5  mov     r14d, nIndex
0x180174fa8  mov     rbx, imageList
0x180174fab  mov     rdi, this
0x180174fae  test    nIndex, nIndex
0x180174fb1  js      loc_180175245
0x180174fb7  cmp     nIndex, [imageList+8]
0x180174fbb  jge     loc_180175245
0x180174fc1  xor     edx, edx; pWnd
0x180174fc3  lea     this, [rbp+0B0h+dc]; this
0x180174fc7  call    ??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x180174fcc  nop
0x180174fcd  movsd   xmm0, qword ptr [rdi+0E8h]
0x180174fd5  ucomisd xmm0, cs:__real@3ff0000000000000
0x180174fdd  jp      short loc_180175015
0x180174fdf  jnz     short loc_180175015
0x180174fe1  mov     rax, [rbx+68h]
0x180174fe5  mov     [rdi+68h], rax
0x180174fe9  mov     rax, [rbx+78h]
0x180174fed  mov     [rdi+78h], rax
0x180174ff1  mov     eax, [rbx+0D8h]
0x180174ff7  mov     [rdi+0D8h], eax
0x180174ffd  mov     eax, [rbx+0E0h]
0x180175003  mov     [rdi+0E0h], eax
0x180175009  mov     eax, [rbx+30h]
0x18017500c  mov     [rdi+30h], eax
0x18017500f  mov     eax, [rbx+0Ch]
0x180175012  mov     [rdi+0Ch], eax
0x180175015  lea     r13, ??_7CDC@@6B@; const CDC::`vftable'
0x18017501c  mov     [rbp+0B0h+memDCSrc.__vftable], r13
0x180175020  xorps   xmm0, xmm0
0x180175023  movdqu  xmmword ptr [rbp+0B0h+memDCSrc.m_hDC], xmm0
0x180175028  and     [rbp+0B0h+memDCSrc.m_bPrinting], 0
0x18017502c  xor     ecx, ecx; hdc
0x18017502e  call    cs:__imp_CreateCompatibleDC
0x180175034  mov     imageList, rax; hDC
0x180175037  lea     this, [rbp+0B0h+memDCSrc]; this
0x18017503b  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180175040  mov     imageList, [rbx+0A0h]; h
0x180175047  test    imageList, imageList
0x18017504a  jz      short loc_18017505B
0x18017504c  mov     this, [rbp+0B0h+memDCSrc.m_hDC]; hdc
0x180175050  call    cs:__imp_SelectObject
0x180175056  mov     rsi, rax
0x180175059  jmp     short loc_18017505D
0x18017505b  xor     esi, esi
0x18017505d  mov     [rsp+1B0h+memDCDest.__vftable], r13
0x180175062  xorps   xmm0, xmm0
0x180175065  movdqu  xmmword ptr [rsp+1B0h+memDCDest.m_hDC], xmm0
0x18017506b  and     [rsp+1B0h+memDCDest.m_bPrinting], 0
0x180175070  xor     ecx, ecx; hdc
0x180175072  call    cs:__imp_CreateCompatibleDC
0x180175078  mov     imageList, rax; hDC
0x18017507b  lea     this, [rsp+1B0h+memDCDest]; this
0x180175080  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180175085  and     [rsp+1B0h+bitmap.m_hObject], 0
0x18017508b  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180175092  mov     [rsp+1B0h+bitmap.__vftable], rax
0x180175097  and     [rbp+0B0h+pv.dsBm.bmType], 0
0x18017509b  xor     edx, edx; Val
0x18017509d  lea     nIndex, [imageList+64h]; Size
0x1801750a1  lea     this, [rbp+0B0h+pv.dsBm.bmWidth]; void *
0x1801750a5  call    memset_0
0x1801750aa  cmp     dword ptr [rbx+0Ch], 18h
0x1801750ae  jl      short loc_180175129
0x1801750b0  lea     r8, [rbp+0B0h+pv]; pv
0x1801750b4  mov     edx, 68h ; 'h'; c
0x1801750b9  mov     this, [rdi+0A0h]; h
0x1801750c0  call    cs:__imp_GetObjectW
0x1801750c6  test    eax, eax
0x1801750c8  jz      short loc_180175129
0x1801750ca  xorps   xmm0, xmm0
0x1801750cd  xor     eax, eax
0x1801750cf  movups  xmmword ptr [rbp+0B0h+bi.bmiHeader.biWidth], xmm0
0x1801750d3  movups  xmmword ptr [rbp+0B0h+bi.bmiHeader.biSizeImage], xmm0
0x1801750d7  mov     qword ptr [rbp+0B0h+bi.bmiHeader.biClrImportant], rax
0x1801750db  mov     [rbp+0B0h+bi.bmiHeader.biSize], 28h ; '('
0x1801750e2  mov     eax, [rbx+68h]
0x1801750e5  mov     [rbp+0B0h+bi.bmiHeader.biWidth], eax
0x1801750e8  mov     eax, [rbx+6Ch]
0x1801750eb  mov     [rbp+0B0h+bi.bmiHeader.biHeight], eax
0x1801750ee  movzx   eax, [rbp+0B0h+pv.dsBm.bmPlanes]
0x1801750f2  mov     [rbp+0B0h+bi.bmiHeader.biPlanes], ax
0x1801750f6  movzx   eax, [rbp+0B0h+pv.dsBm.bmBitsPixel]
0x1801750fa  mov     [rbp+0B0h+bi.bmiHeader.biBitCount], ax
0x1801750fe  and     [rbp+0B0h+bi.bmiHeader.biCompression], 0
0x180175102  and     [rbp+0B0h+pBits], 0
0x180175107  and     dword ptr [rsp+1B0h+hdcSrc], 0
0x18017510c  and     qword ptr [rsp+1B0h+cy], 0
0x180175112  lea     r9, [rbp+0B0h+pBits]; ppvBits
0x180175116  xor     nIndex, nIndex; usage
0x180175119  lea     imageList, [rbp+0B0h+bi]; pbmi
0x18017511d  mov     this, [rbp+0B0h+dc.m_hDC]; hdc
0x180175121  call    cs:__imp_CreateDIBSection
0x180175127  jmp     short loc_18017513A
0x180175129  mov     nIndex, [rbx+6Ch]; cy
0x18017512d  mov     edx, [rbx+68h]; cx
0x180175130  mov     this, [rbp+0B0h+dc.m_hDC]; hdc
0x180175134  call    cs:__imp_CreateCompatibleBitmap
0x18017513a  mov     imageList, rax; hObject
0x18017513d  lea     this, [rsp+1B0h+bitmap]; this
0x180175142  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180175147  mov     imageList, [rsp+1B0h+bitmap.m_hObject]; h
0x18017514c  mov     this, [rsp+1B0h+memDCDest.m_hDC]; hdc
0x180175151  call    cs:__imp_SelectObject
0x180175157  mov     this, rax; h
0x18017515a  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18017515f  mov     r15, rax
0x180175162  mov     r9d, [rbx+68h]; cx
0x180175166  mov     ecx, r9d
0x180175169  imul    ecx, r14d
0x18017516d  mov     edx, [rbx+6Ch]
0x180175170  mov     [rsp+1B0h+rop], 0CC0020h; rop
0x180175178  and     [rsp+1B0h+var_178], 0
0x18017517d  mov     [rsp+1B0h+x1], ecx; x1
0x180175181  mov     this, [rbp+0B0h+memDCSrc.m_hDC]
0x180175185  mov     [rsp+1B0h+hdcSrc], this; hdcSrc
0x18017518a  mov     [rsp+1B0h+cy], edx; cy
0x18017518e  xor     nIndex, nIndex; y
0x180175191  xor     edx, edx; x
0x180175193  mov     this, [rsp+1B0h+memDCDest.m_hDC]; hdc
0x180175198  call    cs:__imp_BitBlt
0x18017519e  test    r15, r15
0x1801751a1  jnz     short loc_1801751A7
0x1801751a3  xor     edx, edx
0x1801751a5  jmp     short loc_1801751AB
0x1801751a7  mov     imageList, [r15+8]; h
0x1801751ab  mov     this, [rsp+1B0h+memDCDest.m_hDC]; hdc
0x1801751b0  call    cs:__imp_SelectObject
0x1801751b6  mov     this, rax; h
0x1801751b9  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1801751be  test    rsi, rsi
0x1801751c1  jz      short loc_1801751D0
0x1801751c3  mov     imageList, rsi; h
0x1801751c6  mov     this, [rbp+0B0h+memDCSrc.m_hDC]; hdc
0x1801751ca  call    cs:__imp_SelectObject
0x1801751d0  xor     nIndex, nIndex; bSetBitPerPixel
0x1801751d3  mov     imageList, [rsp+1B0h+bitmap.m_hObject]; hbmp
0x1801751d8  mov     this, rdi; this
0x1801751db  call    ?AddImage@CMFCToolBarImages@@QEAAHPEAUHBITMAP__@@H@Z; CMFCToolBarImages::AddImage(HBITMAP__ *,int)
0x1801751e0  mov     ebx, eax
0x1801751e2  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1801751e9  mov     [rsp+1B0h+bitmap.__vftable], rax
0x1801751ee  lea     this, [rsp+1B0h+bitmap]; this
0x1801751f3  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1801751f8  nop
0x1801751f9  mov     [rsp+1B0h+memDCDest.__vftable], r13
0x1801751fe  cmp     [rsp+1B0h+memDCDest.m_hDC], 0
0x180175204  jz      short loc_18017521A
0x180175206  lea     this, [rsp+1B0h+memDCDest]; this
0x18017520b  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180175210  mov     this, rax; hdc
0x180175213  call    cs:__imp_DeleteDC
0x180175219  nop
0x18017521a  mov     [rbp+0B0h+memDCSrc.__vftable], r13
0x18017521e  cmp     [rbp+0B0h+memDCSrc.m_hDC], 0
0x180175223  jz      short loc_180175238
0x180175225  lea     this, [rbp+0B0h+memDCSrc]; this
0x180175229  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18017522e  mov     this, rax; hdc
0x180175231  call    cs:__imp_DeleteDC
0x180175237  nop
0x180175238  lea     this, [rbp+0B0h+dc]; this
0x18017523c  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x180175241  mov     eax, ebx
0x180175243  jmp     short loc_180175248
0x180175245  or      eax, 0FFFFFFFFh
0x180175248  mov     this, [rbp+0B0h+var_40]
0x18017524c  xor     this, rsp; StackCookie
0x18017524f  call    __security_check_cookie
0x180175254  add     rsp, 180h
0x18017525b  pop     r15
0x18017525d  pop     r14
0x18017525f  pop     r13
0x180175261  pop     rdi
0x180175262  pop     rsi
0x180175263  pop     rbx
0x180175264  pop     rbp
0x180175265  retn
```
