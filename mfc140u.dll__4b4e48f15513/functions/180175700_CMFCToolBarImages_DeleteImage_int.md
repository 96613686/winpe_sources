# CMFCToolBarImages::DeleteImage(int)

- ea: `0x180175700`
- end: `0x18017597e`
- name: `?DeleteImage@CMFCToolBarImages@@QEAAHH@Z`
- size: `638`
- prototype: `int __fastcall(CMFCToolBarImages *this, int iImage)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180174ad0`
- `0x180175700`
- `0x1802aee60`
- `0x1802aeeb0`

## import_xrefs

- `GDI32!DeleteDC` at `0x1801757fd`
- `GDI32!DeleteDC` at `0x18017594f`
- `GDI32!DeleteDC` at `0x1801757fd`
- `GDI32!DeleteDC` at `0x18017594f`
- `GDI32!BitBlt` at `0x18017589a`
- `GDI32!BitBlt` at `0x1801758f1`
- `GDI32!BitBlt` at `0x18017589a`
- `GDI32!BitBlt` at `0x1801758f1`
- `GDI32!CreateCompatibleBitmap` at `0x1801757c2`
- `GDI32!CreateCompatibleBitmap` at `0x1801757c2`
- `GDI32!DeleteObject` at `0x180175856`
- `GDI32!DeleteObject` at `0x180175918`
- `GDI32!DeleteObject` at `0x180175856`
- `GDI32!DeleteObject` at `0x180175918`
- `GDI32!SelectObject` at `0x1801757a6`
- `GDI32!SelectObject` at `0x1801757d7`
- `GDI32!SelectObject` at `0x180175838`
- `GDI32!SelectObject` at `0x18017584d`
- `GDI32!SelectObject` at `0x1801758fe`
- `GDI32!SelectObject` at `0x18017590b`
- `GDI32!SelectObject` at `0x1801757a6`
- `GDI32!SelectObject` at `0x1801757d7`
- `GDI32!SelectObject` at `0x180175838`
- `GDI32!SelectObject` at `0x18017584d`
- `GDI32!SelectObject` at `0x1801758fe`
- `GDI32!SelectObject` at `0x18017590b`
- `GDI32!CreateCompatibleDC` at `0x180175784`
- `GDI32!CreateCompatibleDC` at `0x18017581f`
- `GDI32!CreateCompatibleDC` at `0x180175784`
- `GDI32!CreateCompatibleDC` at `0x18017581f`
- `GDI32!GetObjectW` at `0x18017575d`
- `GDI32!GetObjectW` at `0x18017575d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMFCToolBarImages::DeleteImage(CMFCToolBarImages *this, int iImage)
{
  HDC CompatibleDC; // rax
  HBITMAP__ *m_hbmImageWell; // rdx
  HGDIOBJ v6; // r14
  HBITMAP__ *CompatibleBitmap; // r15
  unsigned int v8; // esi
  HDC v9; // rax
  HDC v11; // rax
  HGDIOBJ v12; // r12
  int m_iCount; // ecx
  HDC v14; // rax
  CDC memDCSrc; // [rsp+50h] [rbp-21h] BYREF
  CDC memDCDst; // [rsp+70h] [rbp-1h] BYREF
  tagBITMAP bmp; // [rsp+90h] [rbp+1Fh] BYREF

  if ( this->m_bIsTemporary
    || !this->m_bUserImagesList
    || iImage < 0
    || iImage >= this->m_iCount
    || !GetObjectW(this->m_hbmImageWell, 32, &bmp.bmHeight) )
  {
    return 0;
  }
  memDCSrc.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&memDCSrc.m_hAttribDC = 0;
  LODWORD(memDCDst.__vftable) = 0;
  CompatibleDC = CreateCompatibleDC(0);
  CDC::Attach((CDC *)&memDCSrc.m_hDC, CompatibleDC);
  m_hbmImageWell = this->m_hbmImageWell;
  if ( m_hbmImageWell )
  {
    v6 = SelectObject(memDCSrc.m_hAttribDC, m_hbmImageWell);
    if ( v6 )
    {
      CompatibleBitmap = CreateCompatibleBitmap(
                           memDCSrc.m_hAttribDC,
                           bmp.bmWidthBytes - this->m_sizeImage.cx,
                           *(int *)&bmp.bmPlanes);
      if ( CompatibleBitmap )
      {
        memDCDst.m_hDC = (HDC__ *)CDC::`vftable';
        *(_OWORD *)&memDCDst.m_hAttribDC = 0;
        bmp.bmType = 0;
        v11 = CreateCompatibleDC(memDCSrc.m_hAttribDC);
        CDC::Attach((CDC *)&memDCDst.m_hDC, v11);
        v12 = SelectObject(memDCDst.m_hAttribDC, CompatibleBitmap);
        if ( v12 )
        {
          if ( iImage )
            BitBlt(
              memDCDst.m_hAttribDC,
              0,
              0,
              this->m_sizeImage.cx * iImage,
              *(int *)&bmp.bmPlanes,
              memDCSrc.m_hAttribDC,
              0,
              0,
              0xCC0020u);
          m_iCount = this->m_iCount;
          v8 = 1;
          if ( iImage != m_iCount - 1 )
            BitBlt(
              memDCDst.m_hAttribDC,
              iImage * this->m_sizeImage.cx,
              0,
              bmp.bmWidthBytes - this->m_sizeImage.cx * (m_iCount - iImage - 1),
              *(int *)&bmp.bmPlanes,
              memDCSrc.m_hAttribDC,
              this->m_sizeImage.cx * (iImage + 1),
              0,
              0xCC0020u);
          SelectObject(memDCDst.m_hAttribDC, v12);
          SelectObject(memDCSrc.m_hAttribDC, v6);
          DeleteObject(this->m_hbmImageWell);
          this->m_hbmImageWell = CompatibleBitmap;
          this->m_bModified = 1;
          CMFCToolBarImages::UpdateCount(this);
        }
        else
        {
          SelectObject(memDCSrc.m_hAttribDC, v6);
          DeleteObject(CompatibleBitmap);
          v8 = 0;
        }
        memDCDst.m_hDC = (HDC__ *)CDC::`vftable';
        if ( memDCDst.m_hAttribDC )
        {
          v14 = CDC::Detach((CDC *)&memDCDst.m_hDC);
          DeleteDC(v14);
        }
        goto LABEL_11;
      }
      SelectObject(memDCSrc.m_hAttribDC, v6);
    }
  }
  v8 = 0;
LABEL_11:
  memDCSrc.m_hDC = (HDC__ *)CDC::`vftable';
  if ( memDCSrc.m_hAttribDC )
  {
    v9 = CDC::Detach((CDC *)&memDCSrc.m_hDC);
    DeleteDC(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x180175700  mov     rax, rsp
0x180175703  mov     [rax+8], rbx
0x180175707  mov     [rax+10h], rsi
0x18017570b  mov     [rax+18h], rdi
0x18017570f  mov     [rax+20h], r12
0x180175713  push    rbp
0x180175714  push    r14
0x180175716  push    r15
0x180175718  lea     rbp, [rax-5Fh]
0x18017571c  sub     rsp, 0B0h
0x180175723  mov     edi, iImage
0x180175725  mov     rbx, this
0x180175728  cmp     dword ptr [this+2Ch], 0
0x18017572c  jnz     loc_18017595B
0x180175732  cmp     dword ptr [this+1Ch], 0
0x180175736  jz      loc_18017595B
0x18017573c  test    iImage, iImage
0x18017573e  js      loc_18017595B
0x180175744  cmp     iImage, [this+8]
0x180175747  jge     loc_18017595B
0x18017574d  lea     r8, [rbp+57h+bmp.bmHeight]; pv
0x180175751  mov     iImage, 20h ; ' '; c
0x180175756  mov     this, [this+0A0h]; h
0x18017575d  call    cs:__imp_GetObjectW
0x180175763  test    eax, eax
0x180175765  jz      loc_18017595B
0x18017576b  lea     rsi, ??_7CDC@@6B@; const CDC::`vftable'
0x180175772  mov     [rbp+57h+memDCSrc.m_hDC], rsi
0x180175776  xorps   xmm0, xmm0
0x180175779  movdqu  xmmword ptr [rbp+57h+memDCSrc.m_hAttribDC], xmm0
0x18017577e  and     dword ptr [rbp+57h+memDCDst.__vftable], 0
0x180175782  xor     ecx, ecx; hdc
0x180175784  call    cs:__imp_CreateCompatibleDC
0x18017578a  mov     rdx, rax; hDC
0x18017578d  lea     this, [rbp+57h+memDCSrc.m_hDC]; this
0x180175791  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180175796  mov     rdx, [rbx+0A0h]; h
0x18017579d  test    rdx, rdx
0x1801757a0  jz      short loc_1801757DD
0x1801757a2  mov     this, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x1801757a6  call    cs:__imp_SelectObject
0x1801757ac  mov     r14, rax
0x1801757af  test    rax, rax
0x1801757b2  jz      short loc_1801757DD
0x1801757b4  mov     iImage, [rbp+57h+bmp.bmWidthBytes]
0x1801757b7  sub     iImage, [rbx+68h]; cx
0x1801757ba  mov     r8d, dword ptr [rbp+57h+bmp.bmPlanes]; cy
0x1801757be  mov     this, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x1801757c2  call    cs:__imp_CreateCompatibleBitmap
0x1801757c8  mov     r15, rax
0x1801757cb  test    rax, rax
0x1801757ce  jnz     short loc_18017580B
0x1801757d0  mov     rdx, r14; h
0x1801757d3  mov     this, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x1801757d7  call    cs:__imp_SelectObject
0x1801757dd  xor     esi, esi
0x1801757df  lea     rbx, ??_7CDC@@6B@; const CDC::`vftable'
0x1801757e6  mov     [rbp+57h+memDCSrc.m_hDC], rbx
0x1801757ea  cmp     [rbp+57h+memDCSrc.m_hAttribDC], 0
0x1801757ef  jz      short loc_180175804
0x1801757f1  lea     this, [rbp+57h+memDCSrc.m_hDC]; this
0x1801757f5  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1801757fa  mov     this, rax; hdc
0x1801757fd  call    cs:__imp_DeleteDC
0x180175803  nop
0x180175804  mov     eax, esi
0x180175806  jmp     loc_18017595D
0x18017580b  mov     [rbp+57h+memDCDst.m_hDC], rsi
0x18017580f  xorps   xmm0, xmm0
0x180175812  movdqu  xmmword ptr [rbp+57h+memDCDst.m_hAttribDC], xmm0
0x180175817  and     [rbp+57h+bmp.bmType], 0
0x18017581b  mov     this, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x18017581f  call    cs:__imp_CreateCompatibleDC
0x180175825  mov     rdx, rax; hDC
0x180175828  lea     this, [rbp+57h+memDCDst.m_hDC]; this
0x18017582c  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180175831  mov     rdx, r15; h
0x180175834  mov     this, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x180175838  call    cs:__imp_SelectObject
0x18017583e  mov     r12, rax
0x180175841  test    rax, rax
0x180175844  jnz     short loc_180175863
0x180175846  mov     rdx, r14; h
0x180175849  mov     this, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x18017584d  call    cs:__imp_SelectObject
0x180175853  mov     this, r15; ho
0x180175856  call    cs:__imp_DeleteObject
0x18017585c  xor     esi, esi
0x18017585e  jmp     loc_180175931
0x180175863  test    edi, edi
0x180175865  jz      short loc_1801758A0
0x180175867  mov     r9d, edi
0x18017586a  imul    r9d, [rbx+68h]; cx
0x18017586f  mov     [rsp+0C0h+rop], 0CC0020h; rop
0x180175877  and     [rsp+0C0h+var_88], 0
0x18017587c  and     [rsp+0C0h+x1], 0
0x180175881  mov     rax, [rbp+57h+memDCSrc.m_hAttribDC]
0x180175885  mov     [rsp+0C0h+hdcSrc], rax; hdcSrc
0x18017588a  mov     eax, dword ptr [rbp+57h+bmp.bmPlanes]
0x18017588d  mov     [rsp+0C0h+cy], eax; cy
0x180175891  xor     r8d, r8d; y
0x180175894  xor     iImage, iImage; x
0x180175896  mov     this, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x18017589a  call    cs:__imp_BitBlt
0x1801758a0  mov     ecx, [rbx+8]
0x1801758a3  lea     eax, [this-1]
0x1801758a6  mov     esi, 1
0x1801758ab  cmp     edi, eax
0x1801758ad  jz      short loc_1801758F7
0x1801758af  mov     iImage, [rbx+68h]
0x1801758b2  lea     eax, [rdi+1]
0x1801758b5  imul    eax, iImage
0x1801758b8  sub     ecx, edi
0x1801758ba  sub     ecx, esi
0x1801758bc  imul    ecx, iImage
0x1801758bf  mov     r9d, [rbp+57h+bmp.bmWidthBytes]
0x1801758c3  sub     r9d, ecx; cx
0x1801758c6  imul    iImage, edi; x
0x1801758c9  mov     [rsp+0C0h+rop], 0CC0020h; rop
0x1801758d1  and     [rsp+0C0h+var_88], 0
0x1801758d6  mov     [rsp+0C0h+x1], eax; x1
0x1801758da  mov     rax, [rbp+57h+memDCSrc.m_hAttribDC]
0x1801758de  mov     [rsp+0C0h+hdcSrc], rax; hdcSrc
0x1801758e3  mov     eax, dword ptr [rbp+57h+bmp.bmPlanes]
0x1801758e6  mov     [rsp+0C0h+cy], eax; cy
0x1801758ea  xor     r8d, r8d; y
0x1801758ed  mov     this, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x1801758f1  call    cs:__imp_BitBlt
0x1801758f7  mov     rdx, r12; h
0x1801758fa  mov     this, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x1801758fe  call    cs:__imp_SelectObject
0x180175904  mov     rdx, r14; h
0x180175907  mov     this, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x18017590b  call    cs:__imp_SelectObject
0x180175911  mov     this, [rbx+0A0h]; ho
0x180175918  call    cs:__imp_DeleteObject
0x18017591e  mov     [rbx+0A0h], r15
0x180175925  mov     [rbx+20h], esi
0x180175928  mov     this, rbx; this
0x18017592b  call    ?UpdateCount@CMFCToolBarImages@@IEAAXXZ; CMFCToolBarImages::UpdateCount(void)
0x180175930  nop
0x180175931  lea     rbx, ??_7CDC@@6B@; const CDC::`vftable'
0x180175938  mov     [rbp+57h+memDCDst.m_hDC], rbx
0x18017593c  cmp     [rbp+57h+memDCDst.m_hAttribDC], 0
0x180175941  jz      short loc_180175956
0x180175943  lea     this, [rbp+57h+memDCDst.m_hDC]; this
0x180175947  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x18017594c  mov     this, rax; hdc
0x18017594f  call    cs:__imp_DeleteDC
0x180175955  nop
0x180175956  jmp     loc_1801757E6
0x18017595b  xor     eax, eax
0x18017595d  lea     r11, [rsp+0C0h+var_10]
0x180175965  mov     rbx, [r11+20h]
0x180175969  mov     rsi, [r11+28h]
0x18017596d  mov     rdi, [r11+30h]
0x180175971  mov     r12, [r11+38h]
0x180175975  mov     rsp, r11
0x180175978  pop     r15
0x18017597a  pop     r14
0x18017597c  pop     rbp
0x18017597d  retn
```
