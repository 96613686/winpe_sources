# CToolbar::_CopyBitmap(HBITMAP__ *,tagBITMAP *)

- ea: `0x1800df1e8`
- end: `0x1800df433`
- name: `?_CopyBitmap@CToolbar@@AEAAPEAUHBITMAP__@@PEAU2@PEAUtagBITMAP@@@Z`
- size: `587`
- prototype: `HBITMAP(CToolbar *__hidden this, HBITMAP, struct tagBITMAP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180045cd4`

## callees

- `0x1800df1e8`
- `0x180114520`
- `0x180114ebc`
- `0x180126814`

## import_xrefs

- `GDI32!SelectObject` at `0x1800df26f`
- `GDI32!SelectObject` at `0x1800df373`
- `GDI32!SelectObject` at `0x1800df26f`
- `GDI32!SelectObject` at `0x1800df373`
- `GDI32!DeleteDC` at `0x1800df3f2`
- `GDI32!DeleteDC` at `0x1800df400`
- `GDI32!DeleteDC` at `0x1800df3f2`
- `GDI32!DeleteDC` at `0x1800df400`
- `GDI32!CreateCompatibleDC` at `0x1800df239`
- `GDI32!CreateCompatibleDC` at `0x1800df245`
- `GDI32!CreateCompatibleDC` at `0x1800df239`
- `GDI32!CreateCompatibleDC` at `0x1800df245`
- `GDI32!BitBlt` at `0x1800df3d2`
- `GDI32!BitBlt` at `0x1800df3d2`
- `GDI32!CreateDIBSection` at `0x1800df33a`
- `GDI32!CreateDIBSection` at `0x1800df33a`
- `GDI32!GetDIBColorTable` at `0x1800df317`
- `GDI32!GetDIBColorTable` at `0x1800df317`
- `GDI32!CreateBitmapIndirect` at `0x1800df364`
- `GDI32!CreateBitmapIndirect` at `0x1800df364`
- `USER32!GetDC` at `0x1800df22d`
- `USER32!GetDC` at `0x1800df22d`
- `USER32!GetSysColor` at `0x1800df37e`
- `USER32!GetSysColor` at `0x1800df37e`
- `USER32!ReleaseDC` at `0x1800df3e4`
- `USER32!ReleaseDC` at `0x1800df3e4`

## pseudocode

```c
HBITMAP __fastcall CToolbar::_CopyBitmap(HWND *this, HBITMAP a2, struct tagBITMAP *a3)
{
  HBITMAP v3; // r12
  HDC DC; // r13
  HDC CompatibleDC; // rdi
  HDC v8; // rax
  HDC v9; // r14
  int bmBitsPixel; // ecx
  int *p_bmWidth; // rsi
  int *p_bmHeight; // r15
  unsigned int v13; // ecx
  UINT v14; // r8d
  WORD v15; // ax
  HBITMAP BitmapIndirect; // rax
  int v17; // eax
  DWORD SysColor; // eax
  CToolbar *v19; // rcx
  void *ppvBits; // [rsp+58h] [rbp-A8h] BYREF
  BITMAPINFO pbmi; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 0;
  DC = GetDC(this[7]);
  CompatibleDC = CreateCompatibleDC(DC);
  v8 = CreateCompatibleDC(DC);
  v9 = v8;
  if ( DC )
  {
    if ( !CompatibleDC || !v8 )
      goto LABEL_16;
    SelectObject(CompatibleDC, a2);
    if ( a3->bmBits )
    {
      memset_0(pbmi.bmiColors, 0, 0x400u);
      bmBitsPixel = a3->bmBitsPixel;
      p_bmWidth = &a3->bmWidth;
      ppvBits = 0;
      pbmi.bmiHeader.biWidth = a3->bmWidth;
      memset(&pbmi.bmiHeader.biBitCount, 0, 26);
      p_bmHeight = &a3->bmHeight;
      pbmi.bmiHeader.biHeight = a3->bmHeight;
      v13 = a3->bmPlanes * bmBitsPixel;
      pbmi.bmiHeader.biSize = 40;
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 1;
      if ( v13 <= 1 )
      {
        pbmi.bmiHeader.biBitCount = 1;
        v14 = 2;
LABEL_12:
        pbmi.bmiHeader.biClrUsed = GetDIBColorTable(CompatibleDC, 0, v14, pbmi.bmiColors);
        BitmapIndirect = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
LABEL_15:
        v3 = BitmapIndirect;
        SelectObject(v9, BitmapIndirect);
        SysColor = GetSysColor(15);
        CToolbar::PatB(v19, v9, 0, 0, *p_bmWidth, *p_bmHeight, SysColor);
        BitBlt(v9, 0, 0, *p_bmWidth, *p_bmHeight, CompatibleDC, 0, 0, 0xCC0020u);
LABEL_16:
        ReleaseDC(this[7], DC);
        goto LABEL_17;
      }
      v15 = 4;
      if ( v13 <= 4 )
      {
        v14 = 16;
LABEL_11:
        pbmi.bmiHeader.biBitCount = v15;
        goto LABEL_12;
      }
      v15 = 8;
      if ( v13 <= 8 )
      {
        v14 = 256;
        goto LABEL_11;
      }
    }
    else
    {
      p_bmWidth = &a3->bmWidth;
      p_bmHeight = &a3->bmHeight;
    }
    v17 = *p_bmWidth * a3->bmBitsPixel;
    a3->bmBits = 0;
    a3->bmWidthBytes = ((v17 + 15) >> 3) & 0xFFFFFFFE;
    BitmapIndirect = CreateBitmapIndirect(a3);
    goto LABEL_15;
  }
LABEL_17:
  if ( CompatibleDC )
    DeleteDC(CompatibleDC);
  if ( v9 )
    DeleteDC(v9);
  return v3;
}

```

## disassembly

```asm
0x1800df1e8  mov     [rsp-8+arg_18], rbx
0x1800df1ed  push    rbp
0x1800df1ee  push    rsi
0x1800df1ef  push    rdi
0x1800df1f0  push    r12
0x1800df1f2  push    r13
0x1800df1f4  push    r14
0x1800df1f6  push    r15
0x1800df1f8  lea     rbp, [rsp-3A0h]
0x1800df200  sub     rsp, 4A0h
0x1800df207  mov     rax, cs:__security_cookie
0x1800df20e  xor     rax, rsp
0x1800df211  mov     [rbp+3D0h+var_40], rax
0x1800df218  mov     [rsp+4D0h+var_480], rcx
0x1800df21d  xor     r15d, r15d
0x1800df220  mov     rcx, [rcx+38h]; hWnd
0x1800df224  mov     r12d, r15d
0x1800df227  mov     rbx, r8
0x1800df22a  mov     rsi, rdx
0x1800df22d  call    cs:__imp_GetDC
0x1800df233  mov     rcx, rax; hdc
0x1800df236  mov     r13, rax
0x1800df239  call    cs:__imp_CreateCompatibleDC
0x1800df23f  mov     rcx, r13; hdc
0x1800df242  mov     rdi, rax
0x1800df245  call    cs:__imp_CreateCompatibleDC
0x1800df24b  mov     r14, rax
0x1800df24e  test    r13, r13
0x1800df251  jz      loc_1800DF3EA
0x1800df257  test    rdi, rdi
0x1800df25a  jz      loc_1800DF3D8
0x1800df260  test    rax, rax
0x1800df263  jz      loc_1800DF3D8
0x1800df269  mov     rdx, rsi; h
0x1800df26c  mov     rcx, rdi; hdc
0x1800df26f  call    cs:__imp_SelectObject
0x1800df275  cmp     [rbx+18h], r15
0x1800df279  jz      loc_1800DF342
0x1800df27f  xor     edx, edx; Val
0x1800df281  lea     rcx, [rbp+3D0h+pbmi.bmiColors]; void *
0x1800df285  mov     r8d, 400h; Size
0x1800df28b  call    memset_0
0x1800df290  movzx   ecx, word ptr [rbx+12h]
0x1800df294  lea     edx, [r12+1]
0x1800df299  lea     rsi, [rbx+4]
0x1800df29d  mov     [rsp+4D0h+ppvBits], r15
0x1800df2a2  mov     eax, [rsi]
0x1800df2a4  mov     [rsp+4D0h+pbmi.bmiHeader.biWidth], eax
0x1800df2a8  mov     qword ptr [rsp+4D0h+pbmi.bmiHeader.biBitCount], r15
0x1800df2ad  mov     qword ptr [rsp+4D0h+pbmi.bmiHeader.biSizeImage+2], r15
0x1800df2b2  mov     qword ptr [rsp+4D0h+pbmi.bmiHeader.biYPelsPerMeter+2], r15
0x1800df2b7  mov     word ptr [rbp+3D0h+pbmi.bmiHeader.biClrImportant+2], r15w
0x1800df2bc  lea     r15, [rbx+8]
0x1800df2c0  mov     eax, [r15]
0x1800df2c3  mov     [rsp+4D0h+pbmi.bmiHeader.biHeight], eax
0x1800df2c7  movzx   eax, word ptr [rbx+10h]
0x1800df2cb  imul    ecx, eax
0x1800df2ce  mov     [rsp+4D0h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800df2d6  mov     [rsp+4D0h+pbmi.bmiHeader.biPlanes], dx
0x1800df2db  cmp     ecx, edx
0x1800df2dd  ja      short loc_1800DF2EB
0x1800df2df  mov     [rsp+4D0h+pbmi.bmiHeader.biBitCount], dx
0x1800df2e4  lea     r8d, [r12+2]
0x1800df2e9  jmp     short loc_1800DF30E
0x1800df2eb  mov     eax, 4
0x1800df2f0  cmp     ecx, eax
0x1800df2f2  ja      short loc_1800DF2FA
0x1800df2f4  lea     r8d, [rax+0Ch]
0x1800df2f8  jmp     short loc_1800DF309
0x1800df2fa  mov     eax, 8
0x1800df2ff  cmp     ecx, eax
0x1800df301  ja      short loc_1800DF34A
0x1800df303  mov     r8d, 100h; cEntries
0x1800df309  mov     [rsp+4D0h+pbmi.bmiHeader.biBitCount], ax
0x1800df30e  lea     r9, [rbp+3D0h+pbmi.bmiColors]; prgbq
0x1800df312  xor     edx, edx; iStart
0x1800df314  mov     rcx, rdi; hdc
0x1800df317  call    cs:__imp_GetDIBColorTable
0x1800df31d  lea     r9, [rsp+4D0h+ppvBits]; ppvBits
0x1800df322  mov     [rsp+4D0h+offset], r12d; offset
0x1800df327  xor     r8d, r8d; usage
0x1800df32a  mov     [rbp+3D0h+pbmi.bmiHeader.biClrUsed], eax
0x1800df32d  lea     rdx, [rsp+4D0h+pbmi]; pbmi
0x1800df332  mov     [rsp+4D0h+hSection], r12; hSection
0x1800df337  mov     rcx, r13; hdc
0x1800df33a  call    cs:__imp_CreateDIBSection
0x1800df340  jmp     short loc_1800DF36A
0x1800df342  lea     rsi, [rbx+4]
0x1800df346  lea     r15, [rbx+8]
0x1800df34a  movzx   eax, word ptr [rbx+12h]
0x1800df34e  mov     rcx, rbx; pbm
0x1800df351  imul    eax, [rsi]
0x1800df354  mov     [rbx+18h], r12
0x1800df358  add     eax, 0Fh
0x1800df35b  sar     eax, 3
0x1800df35e  and     eax, 0FFFFFFFEh
0x1800df361  mov     [rbx+0Ch], eax
0x1800df364  call    cs:__imp_CreateBitmapIndirect
0x1800df36a  mov     rdx, rax; h
0x1800df36d  mov     rcx, r14; hdc
0x1800df370  mov     r12, rax
0x1800df373  call    cs:__imp_SelectObject
0x1800df379  mov     ecx, 0Fh; nIndex
0x1800df37e  call    cs:__imp_GetSysColor
0x1800df384  mov     [rsp+4D0h+x1], eax; unsigned int
0x1800df388  xor     r9d, r9d; int
0x1800df38b  mov     eax, [r15]
0x1800df38e  xor     r8d, r8d; int
0x1800df391  mov     [rsp+4D0h+offset], eax; int
0x1800df395  mov     rdx, r14; HDC
0x1800df398  mov     eax, [rsi]
0x1800df39a  mov     dword ptr [rsp+4D0h+hSection], eax; int
0x1800df39e  call    ?PatB@CToolbar@@AEBAXPEAUHDC__@@HHHHK@Z; CToolbar::PatB(HDC__ *,int,int,int,int,ulong)
0x1800df3a3  mov     eax, [r15]
0x1800df3a6  xor     r8d, r8d; y
0x1800df3a9  mov     r9d, [rsi]; cx
0x1800df3ac  xor     edx, edx; x
0x1800df3ae  mov     [rsp+4D0h+rop], 0CC0020h; rop
0x1800df3b6  mov     rcx, r14; hdc
0x1800df3b9  mov     [rsp+4D0h+y1], 0; y1
0x1800df3c1  mov     [rsp+4D0h+x1], 0; x1
0x1800df3c9  mov     qword ptr [rsp+4D0h+offset], rdi; hdcSrc
0x1800df3ce  mov     dword ptr [rsp+4D0h+hSection], eax; cy
0x1800df3d2  call    cs:__imp_BitBlt
0x1800df3d8  mov     rcx, [rsp+4D0h+var_480]
0x1800df3dd  mov     rdx, r13; hDC
0x1800df3e0  mov     rcx, [rcx+38h]; hWnd
0x1800df3e4  call    cs:__imp_ReleaseDC
0x1800df3ea  test    rdi, rdi
0x1800df3ed  jz      short loc_1800DF3F8
0x1800df3ef  mov     rcx, rdi; hdc
0x1800df3f2  call    cs:__imp_DeleteDC
0x1800df3f8  test    r14, r14
0x1800df3fb  jz      short loc_1800DF406
0x1800df3fd  mov     rcx, r14; hdc
0x1800df400  call    cs:__imp_DeleteDC
0x1800df406  mov     rax, r12
0x1800df409  mov     rcx, [rbp+3D0h+var_40]
0x1800df410  xor     rcx, rsp; StackCookie
0x1800df413  call    __security_check_cookie
0x1800df418  mov     rbx, [rsp+4D0h+arg_18]
0x1800df420  add     rsp, 4A0h
0x1800df427  pop     r15
0x1800df429  pop     r14
0x1800df42b  pop     r13
0x1800df42d  pop     r12
0x1800df42f  pop     rdi
0x1800df430  pop     rsi
0x1800df431  pop     rbp
0x1800df432  retn
```
