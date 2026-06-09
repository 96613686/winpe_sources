# CMFCToolBarImages::Copy(HBITMAP__ *)

- ea: `0x180178ac0`
- end: `0x180178c6f`
- name: `?Copy@CMFCToolBarImages@@SAPEAUHBITMAP__@@PEAU2@@Z`
- size: `431`
- prototype: `HBITMAP__ *__fastcall(HBITMAP__ *hbmpSrc)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180178ac0`
- `0x1802aee60`
- `0x1802aeeb0`

## import_xrefs

- `GDI32!DeleteDC` at `0x180178b7f`
- `GDI32!DeleteDC` at `0x180178c62`
- `GDI32!DeleteDC` at `0x180178b7f`
- `GDI32!DeleteDC` at `0x180178c62`
- `GDI32!BitBlt` at `0x180178c2a`
- `GDI32!BitBlt` at `0x180178c2a`
- `GDI32!CreateCompatibleBitmap` at `0x180178b4b`
- `GDI32!CreateCompatibleBitmap` at `0x180178b4b`
- `GDI32!DeleteObject` at `0x180178bf1`
- `GDI32!DeleteObject` at `0x180178bf1`
- `GDI32!SelectObject` at `0x180178b20`
- `GDI32!SelectObject` at `0x180178b60`
- `GDI32!SelectObject` at `0x180178bd3`
- `GDI32!SelectObject` at `0x180178be8`
- `GDI32!SelectObject` at `0x180178c37`
- `GDI32!SelectObject` at `0x180178c44`
- `GDI32!SelectObject` at `0x180178b20`
- `GDI32!SelectObject` at `0x180178b60`
- `GDI32!SelectObject` at `0x180178bd3`
- `GDI32!SelectObject` at `0x180178be8`
- `GDI32!SelectObject` at `0x180178c37`
- `GDI32!SelectObject` at `0x180178c44`
- `GDI32!CreateCompatibleDC` at `0x180178b07`
- `GDI32!CreateCompatibleDC` at `0x180178bba`
- `GDI32!CreateCompatibleDC` at `0x180178b07`
- `GDI32!CreateCompatibleDC` at `0x180178bba`
- `GDI32!GetObjectW` at `0x180178b3a`
- `GDI32!GetObjectW` at `0x180178b3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
HBITMAP __fastcall CMFCToolBarImages::Copy(HBITMAP__ *hbmpSrc)
{
  HDC CompatibleDC; // rax
  HGDIOBJ v4; // rdi
  HBITMAP CompatibleBitmap; // rbx
  HDC v6; // rax
  HDC v7; // rax
  HGDIOBJ v8; // rsi
  HDC v9; // rax
  CDC memDCSrc; // [rsp+50h] [rbp-11h] BYREF
  CDC memDCDst; // [rsp+70h] [rbp+Fh] BYREF
  tagBITMAP bmp; // [rsp+90h] [rbp+2Fh] BYREF

  if ( !hbmpSrc )
    return 0;
  memDCSrc.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&memDCSrc.m_hAttribDC = 0;
  LODWORD(memDCDst.__vftable) = 0;
  CompatibleDC = CreateCompatibleDC(0);
  CDC::Attach((CDC *)&memDCSrc.m_hDC, CompatibleDC);
  v4 = SelectObject(memDCSrc.m_hAttribDC, hbmpSrc);
  if ( v4 )
  {
    GetObjectW(hbmpSrc, 32, &bmp.bmHeight);
    CompatibleBitmap = CreateCompatibleBitmap(memDCSrc.m_hAttribDC, bmp.bmWidthBytes, *(int *)&bmp.bmPlanes);
    if ( CompatibleBitmap )
    {
      memDCDst.m_hDC = (HDC__ *)CDC::`vftable';
      *(_OWORD *)&memDCDst.m_hAttribDC = 0;
      bmp.bmType = 0;
      v7 = CreateCompatibleDC(memDCSrc.m_hAttribDC);
      CDC::Attach((CDC *)&memDCDst.m_hDC, v7);
      v8 = SelectObject(memDCDst.m_hAttribDC, CompatibleBitmap);
      if ( v8 )
      {
        BitBlt(
          memDCDst.m_hAttribDC,
          0,
          0,
          bmp.bmWidthBytes,
          *(int *)&bmp.bmPlanes,
          memDCSrc.m_hAttribDC,
          0,
          0,
          0xCC0020u);
        SelectObject(memDCDst.m_hAttribDC, v8);
        SelectObject(memDCSrc.m_hAttribDC, v4);
      }
      else
      {
        SelectObject(memDCSrc.m_hAttribDC, v4);
        DeleteObject(CompatibleBitmap);
        CompatibleBitmap = 0;
      }
      memDCDst.m_hDC = (HDC__ *)CDC::`vftable';
      if ( memDCDst.m_hAttribDC )
      {
        v9 = CDC::Detach((CDC *)&memDCDst.m_hDC);
        DeleteDC(v9);
      }
      goto LABEL_7;
    }
    SelectObject(memDCSrc.m_hAttribDC, v4);
  }
  CompatibleBitmap = 0;
LABEL_7:
  memDCSrc.m_hDC = (HDC__ *)CDC::`vftable';
  if ( memDCSrc.m_hAttribDC )
  {
    v6 = CDC::Detach((CDC *)&memDCSrc.m_hDC);
    DeleteDC(v6);
  }
  return CompatibleBitmap;
}

```

## disassembly

```asm
0x180178ac0  mov     rax, rsp
0x180178ac3  mov     [rax+8], rbx
0x180178ac7  mov     [rax+10h], rsi
0x180178acb  mov     [rax+18h], rdi
0x180178acf  mov     [rax+20h], r15
0x180178ad3  push    rbp
0x180178ad4  lea     rbp, [rax-5Fh]
0x180178ad8  sub     rsp, 0B0h
0x180178adf  mov     rbx, hbmpSrc
0x180178ae2  test    hbmpSrc, hbmpSrc
0x180178ae5  jnz     short loc_180178AEE
0x180178ae7  xor     eax, eax
0x180178ae9  jmp     loc_180178B89
0x180178aee  lea     r15, ??_7CDC@@6B@; const CDC::`vftable'
0x180178af5  mov     [rbp+57h+memDCSrc.m_hDC], r15
0x180178af9  xorps   xmm0, xmm0
0x180178afc  movdqu  xmmword ptr [rbp+57h+memDCSrc.m_hAttribDC], xmm0
0x180178b01  and     dword ptr [rbp+57h+memDCDst.__vftable], 0
0x180178b05  xor     ecx, ecx; hdc
0x180178b07  call    cs:__imp_CreateCompatibleDC
0x180178b0d  mov     rdx, rax; hDC
0x180178b10  lea     hbmpSrc, [rbp+57h+memDCSrc.m_hDC]; this
0x180178b14  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180178b19  mov     rdx, rbx; h
0x180178b1c  mov     hbmpSrc, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x180178b20  call    cs:__imp_SelectObject
0x180178b26  mov     rdi, rax
0x180178b29  test    rax, rax
0x180178b2c  jz      short loc_180178B66
0x180178b2e  lea     r8, [rbp+57h+bmp.bmHeight]; pv
0x180178b32  mov     edx, 20h ; ' '; c
0x180178b37  mov     hbmpSrc, rbx; h
0x180178b3a  call    cs:__imp_GetObjectW
0x180178b40  mov     r8d, dword ptr [rbp+57h+bmp.bmPlanes]; cy
0x180178b44  mov     edx, [rbp+57h+bmp.bmWidthBytes]; cx
0x180178b47  mov     hbmpSrc, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x180178b4b  call    cs:__imp_CreateCompatibleBitmap
0x180178b51  mov     rbx, rax
0x180178b54  test    rax, rax
0x180178b57  jnz     short loc_180178BA6
0x180178b59  mov     rdx, rdi; h
0x180178b5c  mov     hbmpSrc, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x180178b60  call    cs:__imp_SelectObject
0x180178b66  xor     ebx, ebx
0x180178b68  mov     [rbp+57h+memDCSrc.m_hDC], r15
0x180178b6c  cmp     [rbp+57h+memDCSrc.m_hAttribDC], 0
0x180178b71  jz      short loc_180178B86
0x180178b73  lea     hbmpSrc, [rbp+57h+memDCSrc.m_hDC]; this
0x180178b77  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180178b7c  mov     hbmpSrc, rax; hdc
0x180178b7f  call    cs:__imp_DeleteDC
0x180178b85  nop
0x180178b86  mov     rax, rbx
0x180178b89  lea     r11, [rsp+0B0h+var_s0]
0x180178b91  mov     rbx, [r11+10h]
0x180178b95  mov     rsi, [r11+18h]
0x180178b99  mov     rdi, [r11+20h]
0x180178b9d  mov     r15, [r11+28h]
0x180178ba1  mov     rsp, r11
0x180178ba4  pop     rbp
0x180178ba5  retn
0x180178ba6  mov     [rbp+57h+memDCDst.m_hDC], r15
0x180178baa  xorps   xmm0, xmm0
0x180178bad  movdqu  xmmword ptr [rbp+57h+memDCDst.m_hAttribDC], xmm0
0x180178bb2  and     [rbp+57h+bmp.bmType], 0
0x180178bb6  mov     hbmpSrc, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x180178bba  call    cs:__imp_CreateCompatibleDC
0x180178bc0  mov     rdx, rax; hDC
0x180178bc3  lea     hbmpSrc, [rbp+57h+memDCDst.m_hDC]; this
0x180178bc7  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180178bcc  mov     rdx, rbx; h
0x180178bcf  mov     hbmpSrc, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x180178bd3  call    cs:__imp_SelectObject
0x180178bd9  mov     rsi, rax
0x180178bdc  test    rax, rax
0x180178bdf  jnz     short loc_180178BFB
0x180178be1  mov     rdx, rdi; h
0x180178be4  mov     hbmpSrc, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x180178be8  call    cs:__imp_SelectObject
0x180178bee  mov     hbmpSrc, rbx; ho
0x180178bf1  call    cs:__imp_DeleteObject
0x180178bf7  xor     ebx, ebx
0x180178bf9  jmp     short loc_180178C4B
0x180178bfb  mov     [rsp+0B0h+rop], 0CC0020h; rop
0x180178c03  and     [rsp+0B0h+var_78], 0
0x180178c08  and     [rsp+0B0h+var_80], 0
0x180178c0d  mov     rax, [rbp+57h+memDCSrc.m_hAttribDC]
0x180178c11  mov     [rsp+0B0h+hdcSrc], rax; hdcSrc
0x180178c16  mov     eax, dword ptr [rbp+57h+bmp.bmPlanes]
0x180178c19  mov     [rsp+0B0h+cy], eax; cy
0x180178c1d  mov     r9d, [rbp+57h+bmp.bmWidthBytes]; cx
0x180178c21  xor     r8d, r8d; y
0x180178c24  xor     edx, edx; x
0x180178c26  mov     hbmpSrc, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x180178c2a  call    cs:__imp_BitBlt
0x180178c30  mov     rdx, rsi; h
0x180178c33  mov     hbmpSrc, [rbp+57h+memDCDst.m_hAttribDC]; hdc
0x180178c37  call    cs:__imp_SelectObject
0x180178c3d  mov     rdx, rdi; h
0x180178c40  mov     hbmpSrc, [rbp+57h+memDCSrc.m_hAttribDC]; hdc
0x180178c44  call    cs:__imp_SelectObject
0x180178c4a  nop
0x180178c4b  mov     [rbp+57h+memDCDst.m_hDC], r15
0x180178c4f  cmp     [rbp+57h+memDCDst.m_hAttribDC], 0
0x180178c54  jz      short loc_180178C69
0x180178c56  lea     hbmpSrc, [rbp+57h+memDCDst.m_hDC]; this
0x180178c5a  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180178c5f  mov     hbmpSrc, rax; hdc
0x180178c62  call    cs:__imp_DeleteDC
0x180178c68  nop
0x180178c69  jmp     loc_180178B68
```
