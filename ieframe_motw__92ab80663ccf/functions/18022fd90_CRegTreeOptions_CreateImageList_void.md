# CRegTreeOptions::_CreateImageList(void)

- ea: `0x18022fd90`
- end: `0x1802300fb`
- name: `?_CreateImageList@CRegTreeOptions@@IEAAXXZ`
- size: `875`
- prototype: `void __fastcall(CRegTreeOptions *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18022f430`

## callees

- `0x18009d3a4`
- `0x1800c87dc`
- `0x18022f3b4`
- `0x18022fd90`
- `0x180435084`
- `0x18047c998`
- `0x18047cdb8`
- `0x18047ce28`
- `0x18047ce98`
- `0x180523498`
- `0x180591f80`

## import_xrefs

- `GDI32!DeleteObject` at `0x18022ff93`
- `GDI32!DeleteObject` at `0x18022fff9`
- `GDI32!DeleteObject` at `0x180230008`
- `GDI32!DeleteObject` at `0x180230087`
- `GDI32!DeleteObject` at `0x180230096`
- `GDI32!DeleteObject` at `0x18022ff93`
- `GDI32!DeleteObject` at `0x18022fff9`
- `GDI32!DeleteObject` at `0x180230008`
- `GDI32!DeleteObject` at `0x180230087`
- `GDI32!DeleteObject` at `0x180230096`
- `GDI32!SelectObject` at `0x18022ff0f`
- `GDI32!SelectObject` at `0x18022ff6a`
- `GDI32!SelectObject` at `0x18022ff0f`
- `GDI32!SelectObject` at `0x18022ff6a`
- `GDI32!DeleteDC` at `0x1802300a5`
- `GDI32!DeleteDC` at `0x1802300a5`
- `GDI32!CreateCompatibleDC` at `0x18022fe28`
- `GDI32!CreateCompatibleDC` at `0x18022fe28`
- `USER32!GetWindowLongW` at `0x18022fdc3`
- `USER32!GetWindowLongW` at `0x18022fdc3`
- `USER32!SendMessageW` at `0x1802300c1`
- `USER32!SendMessageW` at `0x1802300c1`
- `UxTheme!GetThemePartSize` at `0x18022fe8d`
- `UxTheme!GetThemePartSize` at `0x18022fe8d`
- `UxTheme!OpenThemeData` at `0x18022fe49`
- `UxTheme!OpenThemeData` at `0x18022fe49`
- `UxTheme!DrawThemeBackground` at `0x18022ff58`
- `UxTheme!DrawThemeBackground` at `0x18022ff58`
- `UxTheme!CloseThemeData` at `0x180230017`
- `UxTheme!CloseThemeData` at `0x180230017`

## pseudocode

```c
void __fastcall CRegTreeOptions::_CreateImageList(CRegTreeOptions *this)
{
  int v2; // ebx
  int cx; // edi
  int cy; // esi
  HIMAGELIST v5; // rax
  HDC CompatibleDC; // r15
  HTHEME v7; // r12
  struct tagRGBQUAD **v8; // r9
  HBITMAP DIB; // r13
  unsigned int i; // edi
  HGDIOBJ v11; // rbx
  HBITMAP MappedBitmap; // rax
  HBITMAP v13; // rbx
  HBITMAP v14; // rax
  HBITMAP v15; // rbx
  struct _IMAGELIST *v16; // rax
  SIZE v17; // [rsp+40h] [rbp-29h] BYREF
  SIZE psz; // [rsp+48h] [rbp-21h] BYREF
  RECT pRect; // [rsp+50h] [rbp-19h] BYREF
  __int64 v20; // [rsp+60h] [rbp-9h] BYREF
  int v21; // [rsp+68h] [rbp-1h]
  int v22; // [rsp+6Ch] [rbp+3h]

  v2 = (GetWindowLongW(*((HWND *)this + 4), -20) & 0x400000) != 0 ? 0xA000 : 0;
  v17.cx = IEGetIconSize(8);
  cx = v17.cx;
  v17.cy = IEGetIconSize(8);
  cy = v17.cy;
  v5 = ImageList_Create(v17.cx, v17.cy, v2 + 33, 5, 4);
  *((_QWORD *)this + 6) = v5;
  if ( v5 )
  {
    CompatibleDC = CreateCompatibleDC(0);
    if ( CompatibleDC )
    {
      v7 = OpenThemeData(0, L"Button");
      if ( v7 )
      {
        psz = v17;
        GetThemePartSize(v7, CompatibleDC, 3, 1, 0, TS_DRAW, &psz);
        DIB = CreateDIB(CompatibleDC, cx, cy, v8);
        if ( DIB )
        {
          v20 = 0;
          v21 = cx;
          v22 = cy;
          *(_QWORD *)&pRect.left = 0;
          pRect.right = cx;
          pRect.bottom = cy;
          if ( cx > psz.cx && cy > psz.cy )
          {
            pRect.left = (cx - psz.cx) / 2;
            pRect.top = (cy - psz.cy) / 2;
            pRect.bottom = psz.cy + pRect.top;
            pRect.right = pRect.left + psz.cx;
          }
          for ( i = 0; i < 4; ++i )
          {
            v11 = SelectObject(CompatibleDC, DIB);
            SHFillRectClr(CompatibleDC, &v20, 0);
            DrawThemeBackground(v7, CompatibleDC, dword_180624470[i], dword_180624480[i], &pRect, 0);
            SelectObject(CompatibleDC, v11);
            ImageList_Add(*((HIMAGELIST *)this + 6), DIB, 0);
          }
          DeleteObject(DIB);
        }
        MappedBitmap = CreateMappedBitmap(g_hinst, 529, 0, 0, 0);
        v13 = MappedBitmap;
        if ( MappedBitmap )
        {
          *(_QWORD *)&pRect.left = 0;
          if ( (int)CenterBitmapForImageList(&v17, MappedBitmap, 1, &pRect) >= 0 )
          {
            ImageList_AddMasked(*((HIMAGELIST *)this + 6), *(HBITMAP *)&pRect.left, 0xFF000000);
            DeleteObject(*(HGDIOBJ *)&pRect.left);
          }
          DeleteObject(v13);
        }
        CloseThemeData(v7);
      }
      else
      {
        v17.cx = 5 * cx;
        v17.cy = cy;
        v14 = CreateMappedBitmap(g_hinst, 528, 0, 0, 0);
        v15 = v14;
        if ( v14 )
        {
          *(_QWORD *)&pRect.left = 0;
          if ( (int)CenterBitmapForImageList(&v17, v14, 5, &pRect) >= 0 )
          {
            ImageList_AddMasked(*((HIMAGELIST *)this + 6), *(HBITMAP *)&pRect.left, 0xFF000000);
            DeleteObject(*(HGDIOBJ *)&pRect.left);
          }
          DeleteObject(v15);
        }
      }
      DeleteDC(CompatibleDC);
    }
    v16 = (struct _IMAGELIST *)SendMessageW(*((HWND *)this + 4), 0x1109u, 0, *((_QWORD *)this + 6));
    if ( v16 )
      ImageList_Destroy(v16);
  }
}

```

## disassembly

```asm
0x18022fd90  push    rbp
0x18022fd92  push    rbx
0x18022fd93  push    rsi
0x18022fd94  push    rdi
0x18022fd95  push    r12
0x18022fd97  push    r13
0x18022fd99  push    r14
0x18022fd9b  push    r15
0x18022fd9d  lea     rbp, [rsp-1Fh]
0x18022fda2  sub     rsp, 88h
0x18022fda9  mov     rax, cs:__security_cookie
0x18022fdb0  xor     rax, rsp
0x18022fdb3  mov     [rbp+57h+var_50], rax
0x18022fdb7  mov     r14, rcx
0x18022fdba  mov     edx, 0FFFFFFECh; nIndex
0x18022fdbf  mov     rcx, [rcx+20h]; hWnd
0x18022fdc3  call    cs:__imp_GetWindowLongW
0x18022fdca  nop     dword ptr [rax+rax+00h]
0x18022fdcf  and     eax, 400000h
0x18022fdd4  mov     esi, 8
0x18022fdd9  neg     eax
0x18022fddb  mov     ecx, esi
0x18022fddd  sbb     ebx, ebx
0x18022fddf  and     ebx, 0A000h
0x18022fde5  call    ?IEGetIconSize@@YAHW4FEATURE_ICON_TYPE@@@Z; IEGetIconSize(FEATURE_ICON_TYPE)
0x18022fdea  mov     ecx, esi
0x18022fdec  mov     dword ptr [rbp+57h+var_80], eax
0x18022fdef  mov     edi, eax
0x18022fdf1  call    ?IEGetIconSize@@YAHW4FEATURE_ICON_TYPE@@@Z; IEGetIconSize(FEATURE_ICON_TYPE)
0x18022fdf6  mov     r9d, 5; cInitial
0x18022fdfc  mov     dword ptr [rbp+57h+var_80+4], eax
0x18022fdff  lea     r8d, [rbx+21h]; flags
0x18022fe03  mov     [rsp+0C0h+cGrow], 4; cGrow
0x18022fe0b  mov     edx, eax; cy
0x18022fe0d  mov     ecx, edi; cx
0x18022fe0f  mov     esi, eax
0x18022fe11  call    ImageList_Create
0x18022fe16  xor     r13d, r13d
0x18022fe19  mov     [r14+30h], rax
0x18022fe1d  test    rax, rax
0x18022fe20  jz      loc_1802300DA
0x18022fe26  xor     ecx, ecx; hdc
0x18022fe28  call    cs:__imp_CreateCompatibleDC
0x18022fe2f  nop     dword ptr [rax+rax+00h]
0x18022fe34  mov     r15, rax
0x18022fe37  test    rax, rax
0x18022fe3a  jz      loc_1802300B1
0x18022fe40  lea     rdx, aButton_1; "Button"
0x18022fe47  xor     ecx, ecx; hwnd
0x18022fe49  call    cs:__imp_OpenThemeData
0x18022fe50  nop     dword ptr [rax+rax+00h]
0x18022fe55  mov     r12, rax
0x18022fe58  test    rax, rax
0x18022fe5b  jz      loc_180230025
0x18022fe61  mov     rcx, [rbp+57h+var_80]
0x18022fe65  lea     rax, [rbp+57h+var_78]
0x18022fe69  mov     [rsp+0C0h+psz], rax; psz
0x18022fe6e  lea     ebx, [r13+2]
0x18022fe72  mov     qword ptr [rbp+57h+var_78.cx], rcx
0x18022fe76  lea     r9d, [r13+1]; iStateId
0x18022fe7a  mov     [rsp+0C0h+eSize], ebx; eSize
0x18022fe7e  lea     r8d, [r13+3]; iPartId
0x18022fe82  mov     rcx, r12; hTheme
0x18022fe85  mov     qword ptr [rsp+0C0h+cGrow], r13; prc
0x18022fe8a  mov     rdx, r15; hdc
0x18022fe8d  call    cs:__imp_GetThemePartSize
0x18022fe94  nop     dword ptr [rax+rax+00h]
0x18022fe99  mov     r8d, esi; int
0x18022fe9c  mov     edx, edi; int
0x18022fe9e  mov     rcx, r15; HDC
0x18022fea1  call    ?CreateDIB@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAPEAUtagRGBQUAD@@@Z; CreateDIB(HDC__ *,int,int,tagRGBQUAD * *)
0x18022fea6  xor     r10d, r10d
0x18022fea9  mov     r13, rax
0x18022feac  test    rax, rax
0x18022feaf  jz      loc_18022FF9F
0x18022feb5  mov     rcx, qword ptr [rbp+57h+var_78.cx]
0x18022feb9  mov     [rbp+57h+var_60], r10
0x18022febd  mov     [rbp+57h+var_58], edi
0x18022fec0  mov     [rbp+57h+var_54], esi
0x18022fec3  mov     qword ptr [rbp+57h+pRect.left], r10
0x18022fec7  mov     [rbp+57h+pRect.right], edi
0x18022feca  mov     [rbp+57h+pRect.bottom], esi
0x18022fecd  cmp     edi, ecx
0x18022fecf  jle     short loc_18022FEFF
0x18022fed1  mov     r9d, [rbp+57h+var_78.cy]
0x18022fed5  cmp     esi, r9d
0x18022fed8  jle     short loc_18022FEFF
0x18022feda  sub     edi, ecx
0x18022fedc  sub     esi, r9d
0x18022fedf  mov     eax, edi
0x18022fee1  cdq
0x18022fee2  idiv    ebx
0x18022fee4  mov     r8d, eax
0x18022fee7  mov     [rbp+57h+pRect.left], eax
0x18022feea  mov     eax, esi
0x18022feec  cdq
0x18022feed  idiv    ebx
0x18022feef  lea     edx, [r8+rcx]
0x18022fef3  mov     [rbp+57h+pRect.top], eax
0x18022fef6  add     eax, r9d
0x18022fef9  mov     [rbp+57h+pRect.bottom], eax
0x18022fefc  mov     [rbp+57h+pRect.right], edx
0x18022feff  mov     edi, r10d
0x18022ff02  lea     rsi, __ImageBase
0x18022ff09  mov     rdx, r13; h
0x18022ff0c  mov     rcx, r15; hdc
0x18022ff0f  call    cs:__imp_SelectObject
0x18022ff16  nop     dword ptr [rax+rax+00h]
0x18022ff1b  xor     r8d, r8d
0x18022ff1e  lea     rdx, [rbp+57h+var_60]
0x18022ff22  mov     rcx, r15
0x18022ff25  mov     rbx, rax
0x18022ff28  call    SHFillRectClr
0x18022ff2d  movsxd  r8, edi
0x18022ff30  lea     rax, [rbp+57h+pRect]
0x18022ff34  mov     qword ptr [rsp+0C0h+eSize], 0; pClipRect
0x18022ff3d  mov     rdx, r15; hdc
0x18022ff40  mov     rcx, r12; hTheme
0x18022ff43  mov     qword ptr [rsp+0C0h+cGrow], rax; pRect
0x18022ff48  mov     r9d, ds:rva dword_180624480[rsi+r8*4]; iStateId
0x18022ff50  mov     r8d, ds:rva dword_180624470[rsi+r8*4]; iPartId
0x18022ff58  call    cs:__imp_DrawThemeBackground
0x18022ff5f  nop     dword ptr [rax+rax+00h]
0x18022ff64  mov     rdx, rbx; h
0x18022ff67  mov     rcx, r15; hdc
0x18022ff6a  call    cs:__imp_SelectObject
0x18022ff71  nop     dword ptr [rax+rax+00h]
0x18022ff76  mov     rcx, [r14+30h]; himl
0x18022ff7a  xor     r8d, r8d; hbmMask
0x18022ff7d  mov     rdx, r13; hbmImage
0x18022ff80  call    ImageList_Add
0x18022ff85  inc     edi
0x18022ff87  cmp     edi, 4
0x18022ff8a  jb      loc_18022FF09
0x18022ff90  mov     rcx, r13; ho
0x18022ff93  call    cs:__imp_DeleteObject
0x18022ff9a  nop     dword ptr [rax+rax+00h]
0x18022ff9f  mov     rcx, cs:g_hinst; hInstance
0x18022ffa6  xor     r13d, r13d
0x18022ffa9  xor     r9d, r9d; lpColorMap
0x18022ffac  mov     [rsp+0C0h+cGrow], r13d; iNumMaps
0x18022ffb1  xor     r8d, r8d; wFlags
0x18022ffb4  mov     edx, 211h; idBitmap
0x18022ffb9  call    CreateMappedBitmap
0x18022ffbe  mov     rbx, rax
0x18022ffc1  test    rax, rax
0x18022ffc4  jz      short loc_180230014
0x18022ffc6  lea     r9, [rbp+57h+pRect]
0x18022ffca  mov     qword ptr [rbp+57h+pRect.left], r13
0x18022ffce  lea     r8d, [r13+1]
0x18022ffd2  mov     rdx, rax
0x18022ffd5  lea     rcx, [rbp+57h+var_80]
0x18022ffd9  call    CenterBitmapForImageList
0x18022ffde  test    eax, eax
0x18022ffe0  js      short loc_180230005
0x18022ffe2  mov     rdx, qword ptr [rbp+57h+pRect.left]; hbmImage
0x18022ffe6  mov     r8d, 0FF000000h; crMask
0x18022ffec  mov     rcx, [r14+30h]; himl
0x18022fff0  call    ImageList_AddMasked
0x18022fff5  mov     rcx, qword ptr [rbp+57h+pRect.left]; ho
0x18022fff9  call    cs:__imp_DeleteObject
0x180230000  nop     dword ptr [rax+rax+00h]
0x180230005  mov     rcx, rbx; ho
0x180230008  call    cs:__imp_DeleteObject
0x18023000f  nop     dword ptr [rax+rax+00h]
0x180230014  mov     rcx, r12; hTheme
0x180230017  call    cs:__imp_CloseThemeData
0x18023001e  nop     dword ptr [rax+rax+00h]
0x180230023  jmp     short loc_1802300A2
0x180230025  mov     rcx, cs:g_hinst; hInstance
0x18023002c  lea     eax, [rdi+rdi*4]
0x18023002f  xor     r9d, r9d; lpColorMap
0x180230032  mov     dword ptr [rbp+57h+var_80], eax
0x180230035  xor     r8d, r8d; wFlags
0x180230038  mov     dword ptr [rbp+57h+var_80+4], esi
0x18023003b  mov     edx, 210h; idBitmap
0x180230040  mov     [rsp+0C0h+cGrow], r13d; iNumMaps
0x180230045  call    CreateMappedBitmap
0x18023004a  mov     rbx, rax
0x18023004d  test    rax, rax
0x180230050  jz      short loc_1802300A2
0x180230052  lea     r9, [rbp+57h+pRect]
0x180230056  mov     qword ptr [rbp+57h+pRect.left], r13
0x18023005a  mov     r8d, 5
0x180230060  lea     rcx, [rbp+57h+var_80]
0x180230064  mov     rdx, rax
0x180230067  call    CenterBitmapForImageList
0x18023006c  test    eax, eax
0x18023006e  js      short loc_180230093
0x180230070  mov     rdx, qword ptr [rbp+57h+pRect.left]; hbmImage
0x180230074  mov     r8d, 0FF000000h; crMask
0x18023007a  mov     rcx, [r14+30h]; himl
0x18023007e  call    ImageList_AddMasked
0x180230083  mov     rcx, qword ptr [rbp+57h+pRect.left]; ho
0x180230087  call    cs:__imp_DeleteObject
0x18023008e  nop     dword ptr [rax+rax+00h]
0x180230093  mov     rcx, rbx; ho
0x180230096  call    cs:__imp_DeleteObject
0x18023009d  nop     dword ptr [rax+rax+00h]
0x1802300a2  mov     rcx, r15; hdc
0x1802300a5  call    cs:__imp_DeleteDC
0x1802300ac  nop     dword ptr [rax+rax+00h]
0x1802300b1  mov     r9, [r14+30h]; lParam
0x1802300b5  xor     r8d, r8d; wParam
0x1802300b8  mov     rcx, [r14+20h]; hWnd
0x1802300bc  mov     edx, 1109h; Msg
0x1802300c1  call    cs:__imp_SendMessageW
0x1802300c8  nop     dword ptr [rax+rax+00h]
0x1802300cd  test    rax, rax
0x1802300d0  jz      short loc_1802300DA
0x1802300d2  mov     rcx, rax; himl
0x1802300d5  call    ImageList_Destroy
0x1802300da  mov     rcx, [rbp+57h+var_50]
0x1802300de  xor     rcx, rsp; StackCookie
0x1802300e1  call    __security_check_cookie
0x1802300e6  add     rsp, 88h
0x1802300ed  pop     r15
0x1802300ef  pop     r14
0x1802300f1  pop     r13
0x1802300f3  pop     r12
0x1802300f5  pop     rdi
0x1802300f6  pop     rsi
0x1802300f7  pop     rbx
0x1802300f8  pop     rbp
0x1802300f9  retn
```
