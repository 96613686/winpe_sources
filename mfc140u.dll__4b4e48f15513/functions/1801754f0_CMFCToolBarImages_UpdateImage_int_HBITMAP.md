# CMFCToolBarImages::UpdateImage(int,HBITMAP__ *)

- ea: `0x1801754f0`
- end: `0x1801756f5`
- name: `?UpdateImage@CMFCToolBarImages@@QEAAHHPEAUHBITMAP__@@@Z`
- size: `517`
- prototype: `int __fastcall(CMFCToolBarImages *this, int iImage, HBITMAP__ *hbmp)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801660c0`

## callees

- `0x18001d090`
- `0x1801754f0`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b0720`
- `0x1802b07d0`

## import_xrefs

- `GDI32!DeleteDC` at `0x18017568c`
- `GDI32!DeleteDC` at `0x1801756aa`
- `GDI32!DeleteDC` at `0x18017568c`
- `GDI32!DeleteDC` at `0x1801756aa`
- `GDI32!BitBlt` at `0x180175602`
- `GDI32!BitBlt` at `0x180175602`
- `GDI32!DeleteObject` at `0x18017564c`
- `GDI32!DeleteObject` at `0x18017566b`
- `GDI32!DeleteObject` at `0x18017564c`
- `GDI32!DeleteObject` at `0x18017566b`
- `GDI32!SelectObject` at `0x1801755ac`
- `GDI32!SelectObject` at `0x1801755c5`
- `GDI32!SelectObject` at `0x180175614`
- `GDI32!SelectObject` at `0x180175626`
- `GDI32!SelectObject` at `0x1801755ac`
- `GDI32!SelectObject` at `0x1801755c5`
- `GDI32!SelectObject` at `0x180175614`
- `GDI32!SelectObject` at `0x180175626`
- `GDI32!CreateCompatibleDC` at `0x180175574`
- `GDI32!CreateCompatibleDC` at `0x18017558a`
- `GDI32!CreateCompatibleDC` at `0x180175574`
- `GDI32!CreateCompatibleDC` at `0x18017558a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMFCToolBarImages::UpdateImage(CMFCToolBarImages *this, int iImage, HBITMAP__ *hbmp)
{
  HDC CompatibleDC; // rax
  HDC v7; // rax
  HBITMAP__ *m_hbmImageWell; // rdx
  HGDIOBJ v9; // rsi
  HBITMAP__ **p_m_hbmImageLight; // rdi
  HBITMAP__ **p_m_hbmImageShadow; // rbx
  HDC v12; // rax
  HDC v13; // rax
  CBitmap bitmap; // [rsp+50h] [rbp-41h] BYREF
  CDC memDCDst; // [rsp+60h] [rbp-31h] BYREF
  CDC memDCSrc; // [rsp+80h] [rbp-11h] BYREF
  CWindowDC dc; // [rsp+A0h] [rbp+Fh] BYREF

  if ( this->m_bIsTemporary || !this->m_bUserImagesList )
    return 0;
  CWindowDC::CWindowDC((CWindowDC *)&dc.m_hDC, 0);
  memDCDst.__vftable = 0;
  bitmap.m_hObject = (void *)CBitmap::`vftable';
  memDCSrc.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&memDCSrc.m_hAttribDC = 0;
  LODWORD(dc.__vftable) = 0;
  memDCDst.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&memDCDst.m_hAttribDC = 0;
  LODWORD(memDCSrc.__vftable) = 0;
  CompatibleDC = CreateCompatibleDC(dc.m_hAttribDC);
  CDC::Attach((CDC *)&memDCSrc.m_hDC, CompatibleDC);
  v7 = CreateCompatibleDC(dc.m_hAttribDC);
  CDC::Attach((CDC *)&memDCDst.m_hDC, v7);
  m_hbmImageWell = this->m_hbmImageWell;
  if ( m_hbmImageWell )
    v9 = SelectObject(memDCDst.m_hAttribDC, m_hbmImageWell);
  else
    v9 = 0;
  if ( hbmp )
    hbmp = (HBITMAP__ *)SelectObject(memDCSrc.m_hAttribDC, hbmp);
  BitBlt(
    memDCDst.m_hAttribDC,
    iImage * this->m_sizeImage.cx,
    0,
    this->m_sizeImage.cx,
    this->m_sizeImage.cy,
    memDCSrc.m_hAttribDC,
    0,
    0,
    0xCC0020u);
  if ( v9 )
    SelectObject(memDCDst.m_hAttribDC, v9);
  if ( hbmp )
    SelectObject(memDCSrc.m_hAttribDC, hbmp);
  this->m_bModified = 1;
  p_m_hbmImageLight = &this->m_hbmImageLight;
  if ( this == (CMFCToolBarImages *)-168LL )
    goto LABEL_24;
  if ( *p_m_hbmImageLight )
    DeleteObject(*p_m_hbmImageLight);
  *p_m_hbmImageLight = 0;
  p_m_hbmImageShadow = &this->m_hbmImageShadow;
  if ( !p_m_hbmImageShadow )
LABEL_24:
    AfxThrowInvalidArgException();
  if ( *p_m_hbmImageShadow )
    DeleteObject(*p_m_hbmImageShadow);
  *p_m_hbmImageShadow = 0;
  memDCDst.m_hDC = (HDC__ *)CDC::`vftable';
  if ( memDCDst.m_hAttribDC )
  {
    v12 = CDC::Detach((CDC *)&memDCDst.m_hDC);
    DeleteDC(v12);
  }
  memDCSrc.m_hDC = (HDC__ *)CDC::`vftable';
  if ( memDCSrc.m_hAttribDC )
  {
    v13 = CDC::Detach((CDC *)&memDCSrc.m_hDC);
    DeleteDC(v13);
  }
  bitmap.m_hObject = (void *)CBitmap::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&bitmap.m_hObject);
  CWindowDC::~CWindowDC((CWindowDC *)&dc.m_hDC);
  return 1;
}

```

## disassembly

```asm
0x1801754f0  mov     rax, rsp
0x1801754f3  mov     [rax+8], rbx
0x1801754f7  mov     [rax+10h], rsi
0x1801754fb  mov     [rax+18h], rdi
0x1801754ff  mov     [rax+20h], r12
0x180175503  push    rbp
0x180175504  push    r13
0x180175506  push    r14
0x180175508  lea     rbp, [rax-5Fh]
0x18017550c  sub     rsp, 0D0h
0x180175513  mov     rdi, hbmp
0x180175516  mov     r14d, iImage
0x180175519  mov     rbx, this
0x18017551c  cmp     dword ptr [this+2Ch], 0
0x180175520  jnz     loc_1801756CC
0x180175526  cmp     dword ptr [this+1Ch], 0
0x18017552a  jz      loc_1801756CC
0x180175530  xor     iImage, iImage; pWnd
0x180175532  lea     this, [rbp+57h+dc.m_hDC]; this
0x180175536  call    ??0CWindowDC@@QEAA@PEAVCWnd@@@Z; CWindowDC::CWindowDC(CWnd *)
0x18017553b  nop
0x18017553c  and     [rbp+57h+memDCDst.__vftable], 0
0x180175541  lea     r13, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x180175548  mov     [rbp+57h+bitmap.m_hObject], r13
0x18017554c  lea     r12, ??_7CDC@@6B@; const CDC::`vftable'
0x180175553  mov     [rbp+57h+memDCSrc.m_hDC], r12
0x180175557  xorps   xmm0, xmm0
0x18017555a  movdqu  xmmword ptr [rbp+57h+memDCSrc.m_hAttribDC], xmm0
0x18017555f  and     dword ptr [rbp+57h+dc.__vftable], 0
0x180175563  mov     [rbp+57h+memDCDst.m_hDC], r12
0x180175567  movdqu  xmmword ptr [rbp+57h+memDCDst.m_hAttribDC], xmm0
0x18017556c  and     dword ptr [rbp+57h+memDCSrc.__vftable], 0
0x180175570  mov     this, [rbp+57h+dc.m_hAttribDC]; hdc
0x180175574  call    cs:__imp_CreateCompatibleDC
0x18017557a  mov     rdx, rax; hDC
0x18017557d  lea     this, [rbp+57h+memDCSrc.m_hDC]; this
0x180175581  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180175586  mov     this, [rbp+57h+dc.m_hAttribDC]; hdc
0x18017558a  call    cs:__imp_CreateCompatibleDC
0x180175590  mov     rdx, rax; hDC
0x180175593  lea     this, [rbp+57h+memDCDst.m_hDC]; this
0x180175597  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18017559c  mov     rdx, [rbx+0A0h]; h
0x1801755a3  test    rdx, rdx
0x1801755a6  jz      short loc_1801755B7
0x1801755a8  mov     this, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x1801755ac  call    cs:__imp_SelectObject
0x1801755b2  mov     rsi, rax
0x1801755b5  jmp     short loc_1801755B9
0x1801755b7  xor     esi, esi
0x1801755b9  test    rdi, rdi
0x1801755bc  jz      short loc_1801755CE
0x1801755be  mov     rdx, rdi; h
0x1801755c1  mov     this, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x1801755c5  call    cs:__imp_SelectObject
0x1801755cb  mov     rdi, rax
0x1801755ce  mov     ecx, [rbx+6Ch]
0x1801755d1  mov     r9d, [rbx+68h]; cx
0x1801755d5  mov     iImage, r9d
0x1801755d8  imul    iImage, r14d; x
0x1801755dc  mov     [rsp+0E0h+rop], 0CC0020h; rop
0x1801755e4  and     [rsp+0E0h+var_A8], 0
0x1801755e9  and     [rsp+0E0h+var_B0], 0
0x1801755ee  mov     rax, [rbp+57h+memDCSrc.m_hAttribDC]
0x1801755f2  mov     [rsp+0E0h+hdcSrc], rax; hdcSrc
0x1801755f7  mov     [rsp+0E0h+cy], ecx; cy
0x1801755fb  xor     r8d, r8d; y
0x1801755fe  mov     this, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x180175602  call    cs:__imp_BitBlt
0x180175608  test    rsi, rsi
0x18017560b  jz      short loc_18017561A
0x18017560d  mov     rdx, rsi; h
0x180175610  mov     this, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x180175614  call    cs:__imp_SelectObject
0x18017561a  test    rdi, rdi
0x18017561d  jz      short loc_18017562C
0x18017561f  mov     rdx, rdi; h
0x180175622  mov     this, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x180175626  call    cs:__imp_SelectObject
0x18017562c  mov     esi, 1
0x180175631  mov     [rbx+20h], esi
0x180175634  lea     rdi, [rbx+0A8h]
0x18017563b  test    rdi, rdi
0x18017563e  jz      loc_1801756EF
0x180175644  mov     this, [rdi]; ho
0x180175647  test    this, this
0x18017564a  jz      short loc_180175652
0x18017564c  call    cs:__imp_DeleteObject
0x180175652  and     qword ptr [rdi], 0
0x180175656  add     rbx, 0B0h
0x18017565d  jz      loc_1801756EF
0x180175663  mov     this, [rbx]; ho
0x180175666  test    this, this
0x180175669  jz      short loc_180175671
0x18017566b  call    cs:__imp_DeleteObject
0x180175671  and     qword ptr [rbx], 0
0x180175675  mov     [rbp+57h+memDCDst.m_hDC], r12
0x180175679  cmp     [rbp+57h+memDCDst.m_hAttribDC], 0
0x18017567e  jz      short loc_180175693
0x180175680  lea     this, [rbp+57h+memDCDst.m_hDC]; this
0x180175684  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180175689  mov     this, rax; hdc
0x18017568c  call    cs:__imp_DeleteDC
0x180175692  nop
0x180175693  mov     [rbp+57h+memDCSrc.m_hDC], r12
0x180175697  cmp     [rbp+57h+memDCSrc.m_hAttribDC], 0
0x18017569c  jz      short loc_1801756B1
0x18017569e  lea     this, [rbp+57h+memDCSrc.m_hDC]; this
0x1801756a2  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1801756a7  mov     this, rax; hdc
0x1801756aa  call    cs:__imp_DeleteDC
0x1801756b0  nop
0x1801756b1  mov     [rbp+57h+bitmap.m_hObject], r13
0x1801756b5  lea     this, [rbp+57h+bitmap.m_hObject]; this
0x1801756b9  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1801756be  nop
0x1801756bf  lea     this, [rbp+57h+dc.m_hDC]; this
0x1801756c3  call    ??1CWindowDC@@UEAA@XZ; CWindowDC::~CWindowDC(void)
0x1801756c8  mov     eax, esi
0x1801756ca  jmp     short loc_1801756CE
0x1801756cc  xor     eax, eax
0x1801756ce  lea     r11, [rsp+0E0h+var_10]
0x1801756d6  mov     rbx, [r11+20h]
0x1801756da  mov     rsi, [r11+28h]
0x1801756de  mov     rdi, [r11+30h]
0x1801756e2  mov     r12, [r11+38h]
0x1801756e6  mov     rsp, r11
0x1801756e9  pop     r14
0x1801756eb  pop     r13
0x1801756ed  pop     rbp
0x1801756ee  retn
0x1801756ef  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
