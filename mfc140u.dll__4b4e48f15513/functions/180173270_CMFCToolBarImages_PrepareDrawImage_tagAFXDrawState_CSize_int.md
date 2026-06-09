# CMFCToolBarImages::PrepareDrawImage(tagAFXDrawState &,CSize,int)

- ea: `0x180173270`
- end: `0x180173496`
- name: `?PrepareDrawImage@CMFCToolBarImages@@QEAAHAEAUtagAFXDrawState@@VCSize@@H@Z`
- size: `550`
- prototype: `int __fastcall(CMFCToolBarImages *this, tagAFXDrawState *ds, CSize sizeImageDest, int bFadeInactive)`
- caller_count: `23`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001d920`
- `0x180021980`
- `0x1800603b0`
- `0x180092000`
- `0x18009c0d0`
- `0x18009c9c0`
- `0x1800ebd20`
- `0x1800ef160`
- `0x1800f33b0`
- `0x180118380`
- `0x18011c550`
- `0x18012dd80`
- `0x180135e00`
- `0x180155bf0`
- `0x1801647c0`
- `0x1801660c0`
- `0x180166f70`
- `0x180167360`
- `0x180173740`
- `0x1801742d0`
- `0x180176330`
- `0x18017b650`
- `0x1801891d0`

## callees

- `0x180173270`
- `0x180231d70`
- `0x1802aee60`
- `0x1802b0720`
- `0x1802b07d0`
- `0x1802b09a0`
- `0x1802b09d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180173323`
- `KERNEL32!LeaveCriticalSection` at `0x180173323`
- `KERNEL32!EnterCriticalSection` at `0x1801732af`
- `KERNEL32!EnterCriticalSection` at `0x1801732af`
- `GDI32!CreateBitmap` at `0x180173360`
- `GDI32!CreateBitmap` at `0x180173360`
- `GDI32!CreateCompatibleBitmap` at `0x18017342e`
- `GDI32!CreateCompatibleBitmap` at `0x18017342e`
- `GDI32!DeleteObject` at `0x18017338a`
- `GDI32!DeleteObject` at `0x18017338a`
- `GDI32!SelectObject` at `0x180173305`
- `GDI32!SelectObject` at `0x180173373`
- `GDI32!SelectObject` at `0x18017345c`
- `GDI32!SelectObject` at `0x180173305`
- `GDI32!SelectObject` at `0x180173373`
- `GDI32!SelectObject` at `0x18017345c`
- `GDI32!CreateCompatibleDC` at `0x180173409`
- `GDI32!CreateCompatibleDC` at `0x180173409`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMFCToolBarImages::PrepareDrawImage(
        CMFCToolBarImages *this,
        tagAFXDrawState *ds,
        CSize sizeImageDest,
        int bFadeInactive)
{
  HBITMAP__ *m_hbmImageWell; // rdx
  HBITMAP__ *v8; // rax
  HBITMAP__ *Bitmap; // rax
  HBITMAP__ *v11; // rax
  unsigned int m_clrTransparent; // ecx
  CSize m_sizeImage; // rax
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  void *m_hObject; // rdx
  HGDIOBJ v17; // rax
  CBitmap *v18; // rax
  CWindowDC dc; // [rsp+30h] [rbp-38h] BYREF
  int cy; // [rsp+84h] [rbp+1Ch]

  cy = sizeImageDest.cy;
  if ( !this->m_hbmImageWell )
    return 0;
  if ( CMFCToolBarImages::m_bMultiThreaded )
    EnterCriticalSection(&CMFCToolBarImages::m_CriticalSection.m_sect);
  this->m_bStretch = 0;
  m_hbmImageWell = this->m_hbmImageWell;
  if ( !m_hbmImageWell
    || this != (CMFCToolBarImages *)-72LL && this->m_dcMem.m_hDC
    || this != (CMFCToolBarImages *)-192LL && this->m_bmpMem.m_hObject
    || this->m_pBmpOriginal )
  {
    AfxThrowInvalidArgException();
  }
  v8 = (HBITMAP__ *)SelectObject(hDCGlyphs, m_hbmImageWell);
  ds->hbmOldGlyphs = v8;
  if ( !v8 )
  {
LABEL_11:
    if ( CMFCToolBarImages::m_bMultiThreaded )
      LeaveCriticalSection(&CMFCToolBarImages::m_CriticalSection.m_sect);
    return 0;
  }
  if ( this->m_bCreateMonoDC )
  {
    Bitmap = CreateBitmap(this->m_sizeImage.cx + 2, this->m_sizeImage.cy + 2, 1u, 1u, 0);
    ds->hbmMono = Bitmap;
    v11 = (HBITMAP__ *)SelectObject(hDCMono, Bitmap);
    ds->hbmMonoOld = v11;
    if ( !ds->hbmMono )
      goto LABEL_11;
    if ( !v11 )
    {
      DeleteObject(ds->hbmMono);
      ds->hbmMono = 0;
      goto LABEL_11;
    }
  }
  if ( sizeImageDest.cx <= 0 || cy <= 0 )
    this->m_sizeImageDest = this->m_sizeImage;
  else
    this->m_sizeImageDest = sizeImageDest;
  m_clrTransparent = -1;
  if ( this->m_nBitsPerPixel != 32 )
    m_clrTransparent = this->m_clrTransparent;
  if ( *(_QWORD *)&this->m_sizeImageDest != *(_QWORD *)&this->m_sizeImage || m_clrTransparent != -1 )
  {
    CWindowDC::CWindowDC(&dc, 0);
    m_sizeImage = this->m_sizeImage;
    if ( this->m_sizeImageDest.cx != m_sizeImage.cx || (m_sizeImage.cx = 0, this->m_sizeImageDest.cy != m_sizeImage.cy) )
      m_sizeImage.cx = 1;
    this->m_bStretch = m_sizeImage.cx;
    CompatibleDC = CreateCompatibleDC(0);
    CDC::Attach(&this->m_dcMem, CompatibleDC);
    CompatibleBitmap = CreateCompatibleBitmap(dc.m_hDC, this->m_sizeImage.cx + 2, this->m_sizeImage.cy + 2);
    CGdiObject::Attach(&this->m_bmpMem, CompatibleBitmap);
    if ( this == (CMFCToolBarImages *)-192LL )
      m_hObject = 0;
    else
      m_hObject = this->m_bmpMem.m_hObject;
    v17 = SelectObject(this->m_dcMem.m_hDC, m_hObject);
    v18 = (CBitmap *)CGdiObject::FromHandle(v17);
    this->m_pBmpOriginal = v18;
    if ( !v18 )
      AfxThrowInvalidArgException();
    CWindowDC::~CWindowDC(&dc);
  }
  return 1;
}

```

## disassembly

```asm
0x180173270  mov     rax, rsp
0x180173273  mov     [rax+8], rbx
0x180173277  mov     [rax+10h], rbp
0x18017327b  mov     [rax+20h], rsi
0x18017327f  mov     [rax+18h], sizeImageDest
0x180173283  push    rdi
0x180173284  sub     rsp, 60h
0x180173288  mov     rbx, sizeImageDest
0x18017328b  mov     rsi, rdx
0x18017328e  mov     rdi, this
0x180173291  xor     ebp, ebp
0x180173293  cmp     [this+0A0h], rbp
0x18017329a  jz      loc_180173329
0x1801732a0  cmp     cs:?m_bMultiThreaded@CMFCToolBarImages@@2HA, ebp; int CMFCToolBarImages::m_bMultiThreaded
0x1801732a6  jz      short loc_1801732B5
0x1801732a8  lea     this, ?m_CriticalSection@CMFCToolBarImages@@1VCCriticalSection@@A.m_sect; lpCriticalSection
0x1801732af  call    cs:__imp_EnterCriticalSection
0x1801732b5  mov     [rdi+24h], ebp
0x1801732b8  mov     rdx, [rdi+0A0h]; h
0x1801732bf  test    rdx, rdx
0x1801732c2  jz      loc_180173490
0x1801732c8  lea     rax, [rdi+48h]
0x1801732cc  test    rax, rax
0x1801732cf  jz      short loc_1801732DB
0x1801732d1  cmp     [rax+8], rbp
0x1801732d5  jnz     loc_180173490
0x1801732db  lea     rax, [rdi+0C0h]
0x1801732e2  test    rax, rax
0x1801732e5  jz      short loc_1801732F1
0x1801732e7  cmp     [rax+8], rbp
0x1801732eb  jnz     loc_180173490
0x1801732f1  cmp     [rdi+0D0h], rbp
0x1801732f8  jnz     loc_180173490
0x1801732fe  mov     this, cs:hDCGlyphs; hdc
0x180173305  call    cs:__imp_SelectObject
0x18017330b  mov     [rsi+10h], rax
0x18017330f  test    rax, rax
0x180173312  jnz     short loc_180173341
0x180173314  cmp     cs:?m_bMultiThreaded@CMFCToolBarImages@@2HA, ebp; int CMFCToolBarImages::m_bMultiThreaded
0x18017331a  jz      short loc_180173329
0x18017331c  lea     this, ?m_CriticalSection@CMFCToolBarImages@@1VCCriticalSection@@A.m_sect; lpCriticalSection
0x180173323  call    cs:__imp_LeaveCriticalSection
0x180173329  xor     eax, eax
0x18017332b  lea     r11, [rsp+68h+var_8]
0x180173330  mov     rbx, [r11+10h]
0x180173334  mov     rbp, [r11+18h]
0x180173338  mov     rsi, [r11+28h]
0x18017333c  mov     rsp, r11
0x18017333f  pop     rdi
0x180173340  retn
0x180173341  cmp     [rdi+44h], ebp
0x180173344  jz      short loc_180173398
0x180173346  mov     edx, [rdi+6Ch]
0x180173349  add     edx, 2; nHeight
0x18017334c  mov     ecx, [rdi+68h]
0x18017334f  add     ecx, 2; nWidth
0x180173352  mov     [rsp+68h+lpBits], rbp; lpBits
0x180173357  mov     bFadeInactive, 1; nBitCount
0x18017335d  mov     r8d, bFadeInactive; nPlanes
0x180173360  call    cs:__imp_CreateBitmap
0x180173366  mov     [rsi], rax
0x180173369  mov     rdx, rax; h
0x18017336c  mov     this, cs:hDCMono; hdc
0x180173373  call    cs:__imp_SelectObject
0x180173379  mov     [rsi+8], rax
0x18017337d  mov     this, [rsi]; ho
0x180173380  test    this, this
0x180173383  jz      short loc_180173314
0x180173385  test    rax, rax
0x180173388  jnz     short loc_180173398
0x18017338a  call    cs:__imp_DeleteObject
0x180173390  mov     [rsi], rbp
0x180173393  jmp     loc_180173314
0x180173398  test    ebx, ebx
0x18017339a  jle     short loc_1801733AB
0x18017339c  cmp     [rsp+68h+arg_14], ebp
0x1801733a3  jle     short loc_1801733AB
0x1801733a5  mov     [rdi+78h], rbx
0x1801733a9  jmp     short loc_1801733B3
0x1801733ab  mov     rax, [rdi+68h]
0x1801733af  mov     [rdi+78h], rax
0x1801733b3  or      edx, 0FFFFFFFFh
0x1801733b6  cmp     dword ptr [rdi+0Ch], 20h ; ' '
0x1801733ba  mov     ecx, edx
0x1801733bc  jz      short loc_1801733C4
0x1801733be  mov     ecx, [rdi+0D8h]
0x1801733c4  mov     rax, [rdi+68h]
0x1801733c8  cmp     [rdi+78h], eax
0x1801733cb  jnz     short loc_1801733DE
0x1801733cd  shr     rax, 20h
0x1801733d1  cmp     [rdi+7Ch], eax
0x1801733d4  jnz     short loc_1801733DE
0x1801733d6  cmp     ecx, edx
0x1801733d8  jz      loc_180173480
0x1801733de  xor     edx, edx; pWnd
0x1801733e0  lea     this, [rsp+68h+dc]; this
0x1801733e5  call    ??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x1801733ea  nop
0x1801733eb  mov     rax, [rdi+68h]
0x1801733ef  cmp     [rdi+78h], eax
0x1801733f2  jnz     short loc_1801733FF
0x1801733f4  shr     rax, 20h
0x1801733f8  cmp     [rdi+7Ch], eax
0x1801733fb  mov     eax, ebp
0x1801733fd  jz      short loc_180173404
0x1801733ff  mov     eax, 1
0x180173404  mov     [rdi+24h], eax
0x180173407  xor     ecx, ecx; hdc
0x180173409  call    cs:__imp_CreateCompatibleDC
0x18017340f  mov     rdx, rax; hDC
0x180173412  lea     this, [rdi+48h]; this
0x180173416  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18017341b  mov     r8d, [rdi+6Ch]
0x18017341f  add     r8d, 2; cy
0x180173423  mov     edx, [rdi+68h]
0x180173426  add     edx, 2; cx
0x180173429  mov     this, [rsp+68h+dc.m_hDC]; hdc
0x18017342e  call    cs:__imp_CreateCompatibleBitmap
0x180173434  mov     rdx, rax; hObject
0x180173437  lea     this, [rdi+0C0h]; this
0x18017343e  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x180173443  lea     rdx, [rdi+0C0h]
0x18017344a  test    rdx, rdx
0x18017344d  jnz     short loc_180173454
0x18017344f  mov     rdx, rbp
0x180173452  jmp     short loc_180173458
0x180173454  mov     rdx, [rdx+8]; h
0x180173458  mov     this, [rdi+50h]; hdc
0x18017345c  call    cs:__imp_SelectObject
0x180173462  mov     this, rax; h
0x180173465  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18017346a  mov     [rdi+0D0h], rax
0x180173471  test    rax, rax
0x180173474  jz      short loc_18017348A
0x180173476  lea     this, [rsp+68h+dc]; this
0x18017347b  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x180173480  mov     eax, 1
0x180173485  jmp     loc_18017332B
0x18017348a  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180173490  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
