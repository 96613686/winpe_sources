# AfxGetGrayBitmap(CBitmap const &,CBitmap *,ulong)

- ea: `0x1802b0e30`
- end: `0x1802b11ff`
- name: `?AfxGetGrayBitmap@@YAXAEBVCBitmap@@PEAV1@K@Z`
- size: `975`
- prototype: `void __fastcall(const CBitmap *rSrc, CBitmap *pDest, unsigned int crBackground)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1802b5000`

## callees

- `0x18001d090`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802af110`
- `0x1802af220`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b0a60`
- `0x1802b0b50`
- `0x1802b0e30`
- `0x1802b25f0`

## import_xrefs

- `USER32!GetSysColor` at `0x1802b0e97`
- `USER32!GetSysColor` at `0x1802b0eae`
- `USER32!GetSysColor` at `0x1802b0e97`
- `USER32!GetSysColor` at `0x1802b0eae`
- `GDI32!CreateBitmap` at `0x1802b0f28`
- `GDI32!CreateBitmap` at `0x1802b0f57`
- `GDI32!CreateBitmap` at `0x1802b0f28`
- `GDI32!CreateBitmap` at `0x1802b0f57`
- `GDI32!DeleteDC` at `0x1802b11ba`
- `GDI32!DeleteDC` at `0x1802b11d7`
- `GDI32!DeleteDC` at `0x1802b11ba`
- `GDI32!DeleteDC` at `0x1802b11d7`
- `GDI32!BitBlt` at `0x1802b1001`
- `GDI32!BitBlt` at `0x1802b1044`
- `GDI32!BitBlt` at `0x1802b10e2`
- `GDI32!BitBlt` at `0x1802b1121`
- `GDI32!BitBlt` at `0x1802b1001`
- `GDI32!BitBlt` at `0x1802b1044`
- `GDI32!BitBlt` at `0x1802b10e2`
- `GDI32!BitBlt` at `0x1802b1121`
- `GDI32!GetPixel` at `0x1802b0fbe`
- `GDI32!GetPixel` at `0x1802b0fbe`
- `GDI32!SelectObject` at `0x1802b0f79`
- `GDI32!SelectObject` at `0x1802b0f92`
- `GDI32!SelectObject` at `0x1802b105a`
- `GDI32!SelectObject` at `0x1802b1147`
- `GDI32!SelectObject` at `0x1802b115d`
- `GDI32!SelectObject` at `0x1802b0f79`
- `GDI32!SelectObject` at `0x1802b0f92`
- `GDI32!SelectObject` at `0x1802b105a`
- `GDI32!SelectObject` at `0x1802b1147`
- `GDI32!SelectObject` at `0x1802b115d`
- `GDI32!CreateCompatibleDC` at `0x1802b0ec2`
- `GDI32!CreateCompatibleDC` at `0x1802b0ede`
- `GDI32!CreateCompatibleDC` at `0x1802b0ec2`
- `GDI32!CreateCompatibleDC` at `0x1802b0ede`
- `GDI32!GetObjectW` at `0x1802b0f05`
- `GDI32!GetObjectW` at `0x1802b0f05`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall AfxGetGrayBitmap(const CBitmap *rSrc, CBitmap *pDest, unsigned int crBackground)
{
  DWORD SysColor; // eax
  DWORD v7; // eax
  HDC CompatibleDC; // rax
  HDC v9; // rax
  HBITMAP Bitmap; // rax
  HBITMAP v11; // rax
  HGDIOBJ v12; // rax
  CGdiObject *v13; // rsi
  HGDIOBJ v14; // rax
  CGdiObject *v15; // rax
  CGdiObject *v16; // rdi
  COLORREF Pixel; // eax
  unsigned int v18; // r14d
  void *m_hObject; // rdx
  HGDIOBJ v20; // rax
  CFont *v21; // rbx
  HGDIOBJ v22; // rax
  HGDIOBJ v23; // rax
  HDC v24; // rax
  HDC v25; // rax
  CDC dcMem; // [rsp+50h] [rbp-61h] BYREF
  tagBITMAP bm; // [rsp+70h] [rbp-41h] BYREF
  CDC dcMask; // [rsp+90h] [rbp-21h] BYREF
  CBitmap bmpMask; // [rsp+B0h] [rbp-1h] BYREF
  CBrush brShadow; // [rsp+C0h] [rbp+Fh] BYREF
  CBrush brHighLight; // [rsp+D0h] [rbp+1Fh] BYREF

  dcMem.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&dcMem.m_hAttribDC = 0;
  bm.bmType = 0;
  dcMask.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&dcMask.m_hAttribDC = 0;
  LODWORD(bmpMask.__vftable) = 0;
  brShadow.__vftable = 0;
  bmpMask.m_hObject = (void *)CBitmap::`vftable';
  SysColor = GetSysColor(20);
  CBrush::CBrush((CBrush *)&brHighLight.m_hObject, SysColor);
  v7 = GetSysColor(16);
  CBrush::CBrush((CBrush *)&brShadow.m_hObject, v7);
  CompatibleDC = CreateCompatibleDC(0);
  if ( CDC::Attach((CDC *)&dcMem.m_hDC, CompatibleDC) )
  {
    v9 = CreateCompatibleDC(0);
    if ( CDC::Attach((CDC *)&dcMask.m_hDC, v9) )
    {
      GetObjectW(rSrc->m_hObject, 32, &bm.bmHeight);
      CGdiObject::DeleteObject(pDest);
      Bitmap = CreateBitmap(bm.bmWidthBytes, *(int *)&bm.bmPlanes, LOWORD(bm.bmBits), WORD1(bm.bmBits), 0);
      if ( CGdiObject::Attach(pDest, Bitmap) )
      {
        v11 = CreateBitmap(bm.bmWidthBytes, *(int *)&bm.bmPlanes, 1u, 1u, 0);
        if ( CGdiObject::Attach((CGdiObject *)&bmpMask.m_hObject, v11) )
        {
          v12 = SelectObject(dcMem.m_hAttribDC, rSrc->m_hObject);
          v13 = CGdiObject::FromHandle(v12);
          v14 = SelectObject(dcMask.m_hAttribDC, brShadow.__vftable);
          v15 = CGdiObject::FromHandle(v14);
          v16 = v15;
          if ( v13 )
          {
            if ( v15 )
            {
              Pixel = GetPixel(dcMem.m_hAttribDC, 0, 0);
              v18 = CDC::SetBkColor((CDC *)&dcMem.m_hDC, Pixel);
              BitBlt(
                dcMask.m_hAttribDC,
                0,
                0,
                bm.bmWidthBytes,
                *(int *)&bm.bmPlanes,
                dcMem.m_hAttribDC,
                0,
                0,
                0xCC0020u);
              CDC::SetBkColor((CDC *)&dcMem.m_hDC, 0xFFFFFFu);
              BitBlt(
                dcMask.m_hAttribDC,
                0,
                0,
                bm.bmWidthBytes,
                *(int *)&bm.bmPlanes,
                dcMem.m_hAttribDC,
                0,
                0,
                0x1100A6u);
              m_hObject = 0;
              if ( pDest )
                m_hObject = pDest->m_hObject;
              v20 = SelectObject(dcMem.m_hAttribDC, m_hObject);
              if ( CGdiObject::FromHandle(v20) )
              {
                CDC::FillSolidRect((CDC *)&dcMem.m_hDC, 0, 0, bm.bmWidthBytes, *(int *)&bm.bmPlanes, crBackground);
                CDC::SetBkColor((CDC *)&dcMem.m_hDC, 0xFFFFFFu);
                v21 = CDC::SelectObject((CDC *)&dcMem.m_hDC, (CFont *)&brHighLight.m_hObject);
                BitBlt(
                  dcMem.m_hAttribDC,
                  1,
                  1,
                  bm.bmWidthBytes,
                  *(int *)&bm.bmPlanes,
                  dcMask.m_hAttribDC,
                  0,
                  0,
                  0xE20746u);
                CDC::SelectObject((CDC *)&dcMem.m_hDC, (CFont *)&brShadow.m_hObject);
                BitBlt(
                  dcMem.m_hAttribDC,
                  0,
                  0,
                  bm.bmWidthBytes,
                  *(int *)&bm.bmPlanes,
                  dcMask.m_hAttribDC,
                  0,
                  0,
                  0xE20746u);
                CDC::SelectObject((CDC *)&dcMem.m_hDC, v21);
                CDC::SetBkColor((CDC *)&dcMem.m_hDC, v18);
              }
              v22 = SelectObject(dcMask.m_hAttribDC, v16->m_hObject);
              CGdiObject::FromHandle(v22);
              v23 = SelectObject(dcMem.m_hAttribDC, v13->m_hObject);
              CGdiObject::FromHandle(v23);
            }
          }
        }
      }
    }
  }
  brShadow.m_hObject = (void *)CBrush::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&brShadow.m_hObject);
  brHighLight.m_hObject = (void *)CBrush::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&brHighLight.m_hObject);
  bmpMask.m_hObject = (void *)CBitmap::`vftable';
  CGdiObject::~CGdiObject((CGdiObject *)&bmpMask.m_hObject);
  dcMask.m_hDC = (HDC__ *)CDC::`vftable';
  if ( dcMask.m_hAttribDC )
  {
    v24 = CDC::Detach((CDC *)&dcMask.m_hDC);
    DeleteDC(v24);
  }
  dcMem.m_hDC = (HDC__ *)CDC::`vftable';
  if ( dcMem.m_hAttribDC )
  {
    v25 = CDC::Detach((CDC *)&dcMem.m_hDC);
    DeleteDC(v25);
  }
}

```

## disassembly

```asm
0x1802b0e30  mov     rax, rsp
0x1802b0e33  mov     [rax+8], rbx
0x1802b0e37  mov     [rax+10h], rsi
0x1802b0e3b  mov     [rax+18h], rdi
0x1802b0e3f  push    rbp
0x1802b0e40  push    r12
0x1802b0e42  push    r13
0x1802b0e44  push    r14
0x1802b0e46  push    r15
0x1802b0e48  lea     rbp, [rax-5Fh]
0x1802b0e4c  sub     rsp, 0E0h
0x1802b0e53  mov     r15d, crBackground
0x1802b0e56  mov     rbx, pDest
0x1802b0e59  mov     rdi, rSrc
0x1802b0e5c  lea     r13, ??_7CDC@@6B@; const CDC::`vftable'
0x1802b0e63  mov     [rbp+57h+dcMem.m_hDC], r13
0x1802b0e67  xorps   xmm0, xmm0
0x1802b0e6a  movdqu  xmmword ptr [rbp+57h+dcMem.m_hAttribDC], xmm0
0x1802b0e6f  xor     r12d, r12d
0x1802b0e72  mov     [rbp+57h+bm.bmType], r12d
0x1802b0e76  mov     [rbp+57h+dcMask.m_hDC], r13
0x1802b0e7a  movdqu  xmmword ptr [rbp+57h+dcMask.m_hAttribDC], xmm0
0x1802b0e7f  mov     dword ptr [rbp+57h+bmpMask.__vftable], r12d
0x1802b0e83  mov     [rbp+57h+brShadow.__vftable], r12
0x1802b0e87  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1802b0e8e  mov     [rbp+57h+bmpMask.m_hObject], rax
0x1802b0e92  lea     ecx, [r12+14h]; nIndex
0x1802b0e97  call    cs:__imp_GetSysColor
0x1802b0e9d  mov     edx, eax; crColor
0x1802b0e9f  lea     rSrc, [rbp+57h+brHighLight.m_hObject]; this
0x1802b0ea3  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x1802b0ea8  nop
0x1802b0ea9  lea     ecx, [r12+10h]; nIndex
0x1802b0eae  call    cs:__imp_GetSysColor
0x1802b0eb4  mov     edx, eax; crColor
0x1802b0eb6  lea     rSrc, [rbp+57h+brShadow.m_hObject]; this
0x1802b0eba  call    ??0CBrush@@QEAA@K@Z; CBrush::CBrush(ulong)
0x1802b0ebf  nop
0x1802b0ec0  xor     ecx, ecx; hdc
0x1802b0ec2  call    cs:__imp_CreateCompatibleDC
0x1802b0ec8  mov     pDest, rax; hDC
0x1802b0ecb  lea     rSrc, [rbp+57h+dcMem.m_hDC]; this
0x1802b0ecf  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802b0ed4  test    eax, eax
0x1802b0ed6  jz      loc_1802B116C
0x1802b0edc  xor     ecx, ecx; hdc
0x1802b0ede  call    cs:__imp_CreateCompatibleDC
0x1802b0ee4  mov     pDest, rax; hDC
0x1802b0ee7  lea     rSrc, [rbp+57h+dcMask.m_hDC]; this
0x1802b0eeb  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802b0ef0  test    eax, eax
0x1802b0ef2  jz      loc_1802B116C
0x1802b0ef8  lea     r8, [rbp+57h+bm.bmHeight]; pv
0x1802b0efc  lea     edx, [r12+20h]; c
0x1802b0f01  mov     rSrc, [rdi+8]; h
0x1802b0f05  call    cs:__imp_GetObjectW
0x1802b0f0b  mov     rSrc, rbx; this
0x1802b0f0e  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1802b0f13  movzx   r9d, word ptr [rbp+57h+bm.bmBits+2]; nBitCount
0x1802b0f18  movzx   crBackground, word ptr [rbp+57h+bm.bmBits]; nPlanes
0x1802b0f1d  mov     [rsp+100h+lpBits], r12; lpBits
0x1802b0f22  mov     edx, dword ptr [rbp+57h+bm.bmPlanes]; nHeight
0x1802b0f25  mov     ecx, [rbp+57h+bm.bmWidthBytes]; nWidth
0x1802b0f28  call    cs:__imp_CreateBitmap
0x1802b0f2e  mov     pDest, rax; hObject
0x1802b0f31  mov     rSrc, rbx; this
0x1802b0f34  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b0f39  test    eax, eax
0x1802b0f3b  jz      loc_1802B116C
0x1802b0f41  mov     [rsp+100h+lpBits], r12; lpBits
0x1802b0f46  lea     eax, [r12+1]
0x1802b0f4b  mov     r9d, eax; nBitCount
0x1802b0f4e  mov     crBackground, eax; nPlanes
0x1802b0f51  mov     edx, dword ptr [rbp+57h+bm.bmPlanes]; nHeight
0x1802b0f54  mov     ecx, [rbp+57h+bm.bmWidthBytes]; nWidth
0x1802b0f57  call    cs:__imp_CreateBitmap
0x1802b0f5d  mov     pDest, rax; hObject
0x1802b0f60  lea     rSrc, [rbp+57h+bmpMask.m_hObject]; this
0x1802b0f64  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b0f69  test    eax, eax
0x1802b0f6b  jz      loc_1802B116C
0x1802b0f71  mov     pDest, [rdi+8]; h
0x1802b0f75  mov     rSrc, [rbp+57h+dcMem.m_hAttribDC]; hdc
0x1802b0f79  call    cs:__imp_SelectObject
0x1802b0f7f  mov     rSrc, rax; h
0x1802b0f82  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b0f87  mov     rsi, rax
0x1802b0f8a  mov     pDest, [rbp+57h+brShadow.__vftable]; h
0x1802b0f8e  mov     rSrc, [rbp+57h+dcMask.m_hAttribDC]; hdc
0x1802b0f92  call    cs:__imp_SelectObject
0x1802b0f98  mov     rSrc, rax; h
0x1802b0f9b  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b0fa0  mov     rdi, rax
0x1802b0fa3  test    rsi, rsi
0x1802b0fa6  jz      loc_1802B116C
0x1802b0fac  test    rax, rax
0x1802b0faf  jz      loc_1802B116C
0x1802b0fb5  xor     crBackground, crBackground; y
0x1802b0fb8  xor     edx, edx; x
0x1802b0fba  mov     rSrc, [rbp+57h+dcMem.m_hAttribDC]; hdc
0x1802b0fbe  call    cs:__imp_GetPixel
0x1802b0fc4  mov     edx, eax; crColor
0x1802b0fc6  lea     rSrc, [rbp+57h+dcMem.m_hDC]; this
0x1802b0fca  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b0fcf  mov     r14d, eax
0x1802b0fd2  mov     [rsp+100h+rop], 0CC0020h; rop
0x1802b0fda  mov     [rsp+100h+y1], r12d; y1
0x1802b0fdf  mov     [rsp+100h+x1], r12d; x1
0x1802b0fe4  mov     rSrc, [rbp+57h+dcMem.m_hAttribDC]
0x1802b0fe8  mov     [rsp+100h+hdcSrc], rSrc; hdcSrc
0x1802b0fed  mov     ecx, dword ptr [rbp+57h+bm.bmPlanes]
0x1802b0ff0  mov     dword ptr [rsp+100h+lpBits], ecx; cy
0x1802b0ff4  mov     r9d, [rbp+57h+bm.bmWidthBytes]; cx
0x1802b0ff8  xor     crBackground, crBackground; y
0x1802b0ffb  xor     edx, edx; x
0x1802b0ffd  mov     rSrc, [rbp+57h+dcMask.m_hAttribDC]; hdc
0x1802b1001  call    cs:__imp_BitBlt
0x1802b1007  mov     edx, 0FFFFFFh; crColor
0x1802b100c  lea     rSrc, [rbp+57h+dcMem.m_hDC]; this
0x1802b1010  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b1015  mov     [rsp+100h+rop], 1100A6h; rop
0x1802b101d  mov     [rsp+100h+y1], r12d; y1
0x1802b1022  mov     [rsp+100h+x1], r12d; x1
0x1802b1027  mov     rax, [rbp+57h+dcMem.m_hAttribDC]
0x1802b102b  mov     [rsp+100h+hdcSrc], rax; hdcSrc
0x1802b1030  mov     eax, dword ptr [rbp+57h+bm.bmPlanes]
0x1802b1033  mov     dword ptr [rsp+100h+lpBits], eax; cy
0x1802b1037  mov     r9d, [rbp+57h+bm.bmWidthBytes]; cx
0x1802b103b  xor     crBackground, crBackground; y
0x1802b103e  xor     edx, edx; x
0x1802b1040  mov     rSrc, [rbp+57h+dcMask.m_hAttribDC]; hdc
0x1802b1044  call    cs:__imp_BitBlt
0x1802b104a  test    rbx, rbx
0x1802b104d  mov     edx, r12d
0x1802b1050  jz      short loc_1802B1056
0x1802b1052  mov     pDest, [rbx+8]; h
0x1802b1056  mov     rSrc, [rbp+57h+dcMem.m_hAttribDC]; hdc
0x1802b105a  call    cs:__imp_SelectObject
0x1802b1060  mov     rSrc, rax; h
0x1802b1063  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b1068  test    rax, rax
0x1802b106b  jz      loc_1802B113F
0x1802b1071  mov     dword ptr [rsp+100h+hdcSrc], r15d; clr
0x1802b1076  mov     eax, dword ptr [rbp+57h+bm.bmPlanes]
0x1802b1079  mov     dword ptr [rsp+100h+lpBits], eax; cy
0x1802b107d  mov     r9d, [rbp+57h+bm.bmWidthBytes]; cx
0x1802b1081  xor     crBackground, crBackground; y
0x1802b1084  xor     edx, edx; x
0x1802b1086  lea     rSrc, [rbp+57h+dcMem.m_hDC]; this
0x1802b108a  call    ?FillSolidRect@CDC@@QEAAXHHHHK@Z; CDC::FillSolidRect(int,int,int,int,ulong)
0x1802b108f  mov     edx, 0FFFFFFh; crColor
0x1802b1094  lea     rSrc, [rbp+57h+dcMem.m_hDC]; this
0x1802b1098  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b109d  lea     pDest, [rbp+57h+brHighLight.m_hObject]; pFont
0x1802b10a1  lea     rSrc, [rbp+57h+dcMem.m_hDC]; this
0x1802b10a5  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1802b10aa  mov     rbx, rax
0x1802b10ad  mov     r15d, 0E20746h
0x1802b10b3  mov     [rsp+100h+rop], r15d; rop
0x1802b10b8  mov     [rsp+100h+y1], r12d; y1
0x1802b10bd  mov     [rsp+100h+x1], r12d; x1
0x1802b10c2  mov     rSrc, [rbp+57h+dcMask.m_hAttribDC]
0x1802b10c6  mov     [rsp+100h+hdcSrc], rSrc; hdcSrc
0x1802b10cb  mov     ecx, dword ptr [rbp+57h+bm.bmPlanes]
0x1802b10ce  mov     dword ptr [rsp+100h+lpBits], ecx; cy
0x1802b10d2  mov     r9d, [rbp+57h+bm.bmWidthBytes]; cx
0x1802b10d6  mov     edx, 1; x
0x1802b10db  mov     crBackground, edx; y
0x1802b10de  mov     rSrc, [rbp+57h+dcMem.m_hAttribDC]; hdc
0x1802b10e2  call    cs:__imp_BitBlt
0x1802b10e8  lea     pDest, [rbp+57h+brShadow.m_hObject]; pFont
0x1802b10ec  lea     rSrc, [rbp+57h+dcMem.m_hDC]; this
0x1802b10f0  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1802b10f5  mov     [rsp+100h+rop], r15d; rop
0x1802b10fa  mov     [rsp+100h+y1], r12d; y1
0x1802b10ff  mov     [rsp+100h+x1], r12d; x1
0x1802b1104  mov     rax, [rbp+57h+dcMask.m_hAttribDC]
0x1802b1108  mov     [rsp+100h+hdcSrc], rax; hdcSrc
0x1802b110d  mov     eax, dword ptr [rbp+57h+bm.bmPlanes]
0x1802b1110  mov     dword ptr [rsp+100h+lpBits], eax; cy
0x1802b1114  mov     r9d, [rbp+57h+bm.bmWidthBytes]; cx
0x1802b1118  xor     crBackground, crBackground; y
0x1802b111b  xor     edx, edx; x
0x1802b111d  mov     rSrc, [rbp+57h+dcMem.m_hAttribDC]; hdc
0x1802b1121  call    cs:__imp_BitBlt
0x1802b1127  mov     pDest, rbx; pFont
0x1802b112a  lea     rSrc, [rbp+57h+dcMem.m_hDC]; this
0x1802b112e  call    ?SelectObject@CDC@@QEAAPEAVCPen@@PEAV2@@Z; CDC::SelectObject(CPen *)
0x1802b1133  mov     edx, r14d; crColor
0x1802b1136  lea     rSrc, [rbp+57h+dcMem.m_hDC]; this
0x1802b113a  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b113f  mov     pDest, [rdi+8]; h
0x1802b1143  mov     rSrc, [rbp+57h+dcMask.m_hAttribDC]; hdc
0x1802b1147  call    cs:__imp_SelectObject
0x1802b114d  mov     rSrc, rax; h
0x1802b1150  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b1155  mov     pDest, [rsi+8]; h
0x1802b1159  mov     rSrc, [rbp+57h+dcMem.m_hAttribDC]; hdc
0x1802b115d  call    cs:__imp_SelectObject
0x1802b1163  mov     rSrc, rax; h
0x1802b1166  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b116b  nop
0x1802b116c  lea     rbx, ??_7CBrush@@6B@; const CBrush::`vftable'
0x1802b1173  mov     [rbp+57h+brShadow.m_hObject], rbx
0x1802b1177  lea     rSrc, [rbp+57h+brShadow.m_hObject]; this
0x1802b117b  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b1180  nop
0x1802b1181  mov     [rbp+57h+brHighLight.m_hObject], rbx
0x1802b1185  lea     rSrc, [rbp+57h+brHighLight.m_hObject]; this
0x1802b1189  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b118e  nop
0x1802b118f  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1802b1196  mov     [rbp+57h+bmpMask.m_hObject], rax
0x1802b119a  lea     rSrc, [rbp+57h+bmpMask.m_hObject]; this
0x1802b119e  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b11a3  nop
0x1802b11a4  mov     [rbp+57h+dcMask.m_hDC], r13
0x1802b11a8  cmp     [rbp+57h+dcMask.m_hAttribDC], r12
0x1802b11ac  jz      short loc_1802B11C1
0x1802b11ae  lea     rSrc, [rbp+57h+dcMask.m_hDC]; this
0x1802b11b2  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1802b11b7  mov     rSrc, rax; hdc
0x1802b11ba  call    cs:__imp_DeleteDC
0x1802b11c0  nop
0x1802b11c1  mov     [rbp+57h+dcMem.m_hDC], r13
0x1802b11c5  cmp     [rbp+57h+dcMem.m_hAttribDC], r12
0x1802b11c9  jz      short loc_1802B11DE
0x1802b11cb  lea     rSrc, [rbp+57h+dcMem.m_hDC]; this
0x1802b11cf  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1802b11d4  mov     rSrc, rax; hdc
0x1802b11d7  call    cs:__imp_DeleteDC
0x1802b11dd  nop
0x1802b11de  lea     r11, [rsp+100h+var_20]
0x1802b11e6  mov     rbx, [r11+30h]
0x1802b11ea  mov     rsi, [r11+38h]
0x1802b11ee  mov     rdi, [r11+40h]
0x1802b11f2  mov     rsp, r11
0x1802b11f5  pop     r15
0x1802b11f7  pop     r14
0x1802b11f9  pop     r13
0x1802b11fb  pop     r12
0x1802b11fd  pop     rbp
0x1802b11fe  retn
```
