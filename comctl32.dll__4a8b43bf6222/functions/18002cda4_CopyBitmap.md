# _CopyBitmap

- ea: `0x18002cda4`
- end: `0x18002cfe4`
- name: `_CopyBitmap`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800264a0`

## callees

- `0x1800115f0`
- `0x1800262c4`
- `0x18002cda4`
- `0x18008ea60`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18002cdf4`
- `GDI32!CreateCompatibleDC` at `0x18002ce00`
- `GDI32!CreateCompatibleDC` at `0x18002cdf4`
- `GDI32!CreateCompatibleDC` at `0x18002ce00`
- `GDI32!CreateDIBSection` at `0x18002cef5`
- `GDI32!CreateDIBSection` at `0x18002cef5`
- `GDI32!SelectObject` at `0x18002ce2a`
- `GDI32!SelectObject` at `0x18002cf2e`
- `GDI32!SelectObject` at `0x18002ce2a`
- `GDI32!SelectObject` at `0x18002cf2e`
- `GDI32!BitBlt` at `0x18002cf84`
- `GDI32!BitBlt` at `0x18002cf84`
- `GDI32!DeleteDC` at `0x18002cfa3`
- `GDI32!DeleteDC` at `0x18002cfb1`
- `GDI32!DeleteDC` at `0x18002cfa3`
- `GDI32!DeleteDC` at `0x18002cfb1`
- `GDI32!GetDIBColorTable` at `0x18002ced2`
- `GDI32!GetDIBColorTable` at `0x18002ced2`
- `GDI32!CreateBitmapIndirect` at `0x18002cf1f`
- `GDI32!CreateBitmapIndirect` at `0x18002cf1f`
- `USER32!GetDC` at `0x18002cde8`
- `USER32!GetDC` at `0x18002cde8`
- `USER32!ReleaseDC` at `0x18002cf95`
- `USER32!ReleaseDC` at `0x18002cf95`

## pseudocode

```c
HBITMAP __fastcall CopyBitmap(HWND *a1, void *a2, const BITMAP *a3)
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
  __int16 v15; // ax
  HBITMAP BitmapIndirect; // rax
  int v17; // eax
  void *ppvBits; // [rsp+50h] [rbp-B0h] BYREF
  HWND *v20; // [rsp+58h] [rbp-A8h]
  BITMAPINFO pbmi; // [rsp+60h] [rbp-A0h] BYREF

  v20 = a1;
  v3 = 0;
  DC = GetDC(*a1);
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
      memset(pbmi.bmiColors, 0, 0x400u);
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
        PatB(v9, *p_bmHeight, g_clrBtnFace);
        BitBlt(v9, 0, 0, *p_bmWidth, *p_bmHeight, CompatibleDC, 0, 0, 0xCC0020u);
LABEL_16:
        ReleaseDC(*v20, DC);
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
0x18002cda4  mov     [rsp-8+arg_18], rbx
0x18002cda9  push    rbp
0x18002cdaa  push    rsi
0x18002cdab  push    rdi
0x18002cdac  push    r12
0x18002cdae  push    r13
0x18002cdb0  push    r14
0x18002cdb2  push    r15
0x18002cdb4  lea     rbp, [rsp-3A0h]
0x18002cdbc  sub     rsp, 4A0h
0x18002cdc3  mov     rax, cs:__security_cookie
0x18002cdca  xor     rax, rsp
0x18002cdcd  mov     [rbp+3D0h+var_40], rax
0x18002cdd4  mov     [rsp+4D0h+var_478], rcx
0x18002cdd9  xor     r15d, r15d
0x18002cddc  mov     rcx, [rcx]; hWnd
0x18002cddf  mov     r12d, r15d
0x18002cde2  mov     rbx, r8
0x18002cde5  mov     rsi, rdx
0x18002cde8  call    cs:__imp_GetDC
0x18002cdee  mov     rcx, rax; hdc
0x18002cdf1  mov     r13, rax
0x18002cdf4  call    cs:__imp_CreateCompatibleDC
0x18002cdfa  mov     rcx, r13; hdc
0x18002cdfd  mov     rdi, rax
0x18002ce00  call    cs:__imp_CreateCompatibleDC
0x18002ce06  mov     r14, rax
0x18002ce09  test    r13, r13
0x18002ce0c  jz      loc_18002CF9B
0x18002ce12  test    rdi, rdi
0x18002ce15  jz      loc_18002CF8A
0x18002ce1b  test    rax, rax
0x18002ce1e  jz      loc_18002CF8A
0x18002ce24  mov     rdx, rsi; h
0x18002ce27  mov     rcx, rdi; hdc
0x18002ce2a  call    cs:__imp_SelectObject
0x18002ce30  cmp     [rbx+18h], r15
0x18002ce34  jz      loc_18002CEFD
0x18002ce3a  xor     edx, edx; Val
0x18002ce3c  lea     rcx, [rbp+3D0h+pbmi.bmiColors]; void *
0x18002ce40  mov     r8d, 400h; Size
0x18002ce46  call    memset
0x18002ce4b  movzx   ecx, word ptr [rbx+12h]
0x18002ce4f  lea     edx, [r12+1]
0x18002ce54  lea     rsi, [rbx+4]
0x18002ce58  mov     [rsp+4D0h+ppvBits], r15
0x18002ce5d  mov     eax, [rsi]
0x18002ce5f  mov     [rsp+4D0h+pbmi.bmiHeader.biWidth], eax
0x18002ce63  mov     qword ptr [rsp+4D0h+pbmi.bmiHeader.biBitCount], r15
0x18002ce68  mov     qword ptr [rsp+4D0h+pbmi.bmiHeader.biSizeImage+2], r15
0x18002ce6d  mov     qword ptr [rsp+4D0h+pbmi.bmiHeader.biYPelsPerMeter+2], r15
0x18002ce72  mov     word ptr [rbp+3D0h+pbmi.bmiHeader.biClrImportant+2], r15w
0x18002ce77  lea     r15, [rbx+8]
0x18002ce7b  mov     eax, [r15]
0x18002ce7e  mov     [rsp+4D0h+pbmi.bmiHeader.biHeight], eax
0x18002ce82  movzx   eax, word ptr [rbx+10h]
0x18002ce86  imul    ecx, eax
0x18002ce89  mov     [rsp+4D0h+pbmi.bmiHeader.biSize], 28h ; '('
0x18002ce91  mov     [rsp+4D0h+pbmi.bmiHeader.biPlanes], dx
0x18002ce96  cmp     ecx, edx
0x18002ce98  ja      short loc_18002CEA6
0x18002ce9a  mov     [rsp+4D0h+pbmi.bmiHeader.biBitCount], dx
0x18002ce9f  lea     r8d, [r12+2]
0x18002cea4  jmp     short loc_18002CEC9
0x18002cea6  mov     eax, 4
0x18002ceab  cmp     ecx, eax
0x18002cead  ja      short loc_18002CEB5
0x18002ceaf  lea     r8d, [rax+0Ch]
0x18002ceb3  jmp     short loc_18002CEC4
0x18002ceb5  mov     eax, 8
0x18002ceba  cmp     ecx, eax
0x18002cebc  ja      short loc_18002CF05
0x18002cebe  mov     r8d, 100h; cEntries
0x18002cec4  mov     [rsp+4D0h+pbmi.bmiHeader.biBitCount], ax
0x18002cec9  lea     r9, [rbp+3D0h+pbmi.bmiColors]; prgbq
0x18002cecd  xor     edx, edx; iStart
0x18002cecf  mov     rcx, rdi; hdc
0x18002ced2  call    cs:__imp_GetDIBColorTable
0x18002ced8  lea     r9, [rsp+4D0h+ppvBits]; ppvBits
0x18002cedd  mov     [rsp+4D0h+offset], r12d; offset
0x18002cee2  xor     r8d, r8d; usage
0x18002cee5  mov     [rbp+3D0h+pbmi.bmiHeader.biClrUsed], eax
0x18002cee8  lea     rdx, [rsp+4D0h+pbmi]; pbmi
0x18002ceed  mov     [rsp+4D0h+hSection], r12; hSection
0x18002cef2  mov     rcx, r13; hdc
0x18002cef5  call    cs:__imp_CreateDIBSection
0x18002cefb  jmp     short loc_18002CF25
0x18002cefd  lea     rsi, [rbx+4]
0x18002cf01  lea     r15, [rbx+8]
0x18002cf05  movzx   eax, word ptr [rbx+12h]
0x18002cf09  mov     rcx, rbx; pbm
0x18002cf0c  imul    eax, [rsi]
0x18002cf0f  mov     [rbx+18h], r12
0x18002cf13  add     eax, 0Fh
0x18002cf16  sar     eax, 3
0x18002cf19  and     eax, 0FFFFFFFEh
0x18002cf1c  mov     [rbx+0Ch], eax
0x18002cf1f  call    cs:__imp_CreateBitmapIndirect
0x18002cf25  mov     rdx, rax; h
0x18002cf28  mov     rcx, r14; hdc
0x18002cf2b  mov     r12, rax
0x18002cf2e  call    cs:__imp_SelectObject
0x18002cf34  mov     eax, cs:g_clrBtnFace
0x18002cf3a  xor     r8d, r8d
0x18002cf3d  mov     r9d, [rsi]
0x18002cf40  xor     edx, edx
0x18002cf42  mov     [rsp+4D0h+offset], eax; color
0x18002cf46  mov     rcx, r14; hdc
0x18002cf49  mov     eax, [r15]
0x18002cf4c  mov     dword ptr [rsp+4D0h+hSection], eax; int
0x18002cf50  call    PatB
0x18002cf55  mov     eax, [r15]
0x18002cf58  xor     r8d, r8d; y
0x18002cf5b  mov     r9d, [rsi]; cx
0x18002cf5e  xor     edx, edx; x
0x18002cf60  mov     [rsp+4D0h+rop], 0CC0020h; rop
0x18002cf68  mov     rcx, r14; hdc
0x18002cf6b  mov     [rsp+4D0h+y1], 0; y1
0x18002cf73  mov     [rsp+4D0h+x1], 0; x1
0x18002cf7b  mov     qword ptr [rsp+4D0h+offset], rdi; hdcSrc
0x18002cf80  mov     dword ptr [rsp+4D0h+hSection], eax; cy
0x18002cf84  call    cs:__imp_BitBlt
0x18002cf8a  mov     rcx, [rsp+4D0h+var_478]
0x18002cf8f  mov     rdx, r13; hDC
0x18002cf92  mov     rcx, [rcx]; hWnd
0x18002cf95  call    cs:__imp_ReleaseDC
0x18002cf9b  test    rdi, rdi
0x18002cf9e  jz      short loc_18002CFA9
0x18002cfa0  mov     rcx, rdi; hdc
0x18002cfa3  call    cs:__imp_DeleteDC
0x18002cfa9  test    r14, r14
0x18002cfac  jz      short loc_18002CFB7
0x18002cfae  mov     rcx, r14; hdc
0x18002cfb1  call    cs:__imp_DeleteDC
0x18002cfb7  mov     rax, r12
0x18002cfba  mov     rcx, [rbp+3D0h+var_40]
0x18002cfc1  xor     rcx, rsp; StackCookie
0x18002cfc4  call    __security_check_cookie
0x18002cfc9  mov     rbx, [rsp+4D0h+arg_18]
0x18002cfd1  add     rsp, 4A0h
0x18002cfd8  pop     r15
0x18002cfda  pop     r14
0x18002cfdc  pop     r13
0x18002cfde  pop     r12
0x18002cfe0  pop     rdi
0x18002cfe1  pop     rsi
0x18002cfe2  pop     rbp
0x18002cfe3  retn
```
