# CRegTreeOptions::_CreateImageList(void)

- ea: `0x180214868`
- end: `0x180214b74`
- name: `?_CreateImageList@CRegTreeOptions@@IEAAXXZ`
- size: `780`
- prototype: `void __fastcall(CRegTreeOptions *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180213fa0`

## callees

- `0x180096010`
- `0x1800c16d8`
- `0x180213f28`
- `0x180214868`
- `0x1803fe1f0`
- `0x180441d98`
- `0x1804421a8`
- `0x180442218`
- `0x180442288`
- `0x1804e50bc`
- `0x18054e310`

## import_xrefs

- `GDI32!DeleteObject` at `0x180214a3d`
- `GDI32!DeleteObject` at `0x180214a9d`
- `GDI32!DeleteObject` at `0x180214aa6`
- `GDI32!DeleteObject` at `0x180214b19`
- `GDI32!DeleteObject` at `0x180214b22`
- `GDI32!DeleteObject` at `0x180214a3d`
- `GDI32!DeleteObject` at `0x180214a9d`
- `GDI32!DeleteObject` at `0x180214aa6`
- `GDI32!DeleteObject` at `0x180214b19`
- `GDI32!DeleteObject` at `0x180214b22`
- `GDI32!SelectObject` at `0x1802149cf`
- `GDI32!SelectObject` at `0x180214a1e`
- `GDI32!SelectObject` at `0x1802149cf`
- `GDI32!SelectObject` at `0x180214a1e`
- `GDI32!DeleteDC` at `0x180214b2b`
- `GDI32!DeleteDC` at `0x180214b2b`
- `GDI32!CreateCompatibleDC` at `0x1802148fa`
- `GDI32!CreateCompatibleDC` at `0x1802148fa`
- `USER32!GetWindowLongW` at `0x18021489b`
- `USER32!GetWindowLongW` at `0x18021489b`
- `USER32!SendMessageW` at `0x180214b41`
- `USER32!SendMessageW` at `0x180214b41`
- `UxTheme!GetThemePartSize` at `0x180214953`
- `UxTheme!GetThemePartSize` at `0x180214953`
- `UxTheme!OpenThemeData` at `0x180214915`
- `UxTheme!OpenThemeData` at `0x180214915`
- `UxTheme!DrawThemeBackground` at `0x180214a12`
- `UxTheme!DrawThemeBackground` at `0x180214a12`
- `UxTheme!CloseThemeData` at `0x180214aaf`
- `UxTheme!CloseThemeData` at `0x180214aaf`

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
            DrawThemeBackground(v7, CompatibleDC, dword_1805E05B0[i], dword_1805E05C0[i], &pRect, 0);
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
0x180214868  push    rbp
0x18021486a  push    rbx
0x18021486b  push    rsi
0x18021486c  push    rdi
0x18021486d  push    r12
0x18021486f  push    r13
0x180214871  push    r14
0x180214873  push    r15
0x180214875  lea     rbp, [rsp-1Fh]
0x18021487a  sub     rsp, 88h
0x180214881  mov     rax, cs:__security_cookie
0x180214888  xor     rax, rsp
0x18021488b  mov     [rbp+57h+var_50], rax
0x18021488f  mov     r14, rcx
0x180214892  mov     edx, 0FFFFFFECh; nIndex
0x180214897  mov     rcx, [rcx+20h]; hWnd
0x18021489b  call    cs:__imp_GetWindowLongW
0x1802148a1  and     eax, 400000h
0x1802148a6  mov     esi, 8
0x1802148ab  neg     eax
0x1802148ad  mov     ecx, esi
0x1802148af  sbb     ebx, ebx
0x1802148b1  and     ebx, 0A000h
0x1802148b7  call    ?IEGetIconSize@@YAHW4FEATURE_ICON_TYPE@@@Z; IEGetIconSize(FEATURE_ICON_TYPE)
0x1802148bc  mov     ecx, esi
0x1802148be  mov     dword ptr [rbp+57h+var_80], eax
0x1802148c1  mov     edi, eax
0x1802148c3  call    ?IEGetIconSize@@YAHW4FEATURE_ICON_TYPE@@@Z; IEGetIconSize(FEATURE_ICON_TYPE)
0x1802148c8  mov     r9d, 5; cInitial
0x1802148ce  mov     dword ptr [rbp+57h+var_80+4], eax
0x1802148d1  lea     r8d, [rbx+21h]; flags
0x1802148d5  mov     [rsp+0C0h+cGrow], 4; cGrow
0x1802148dd  mov     edx, eax; cy
0x1802148df  mov     ecx, edi; cx
0x1802148e1  mov     esi, eax
0x1802148e3  call    ImageList_Create
0x1802148e8  xor     r13d, r13d
0x1802148eb  mov     [r14+30h], rax
0x1802148ef  test    rax, rax
0x1802148f2  jz      loc_180214B54
0x1802148f8  xor     ecx, ecx; hdc
0x1802148fa  call    cs:__imp_CreateCompatibleDC
0x180214900  mov     r15, rax
0x180214903  test    rax, rax
0x180214906  jz      loc_180214B31
0x18021490c  lea     rdx, aButton_1; "Button"
0x180214913  xor     ecx, ecx; hwnd
0x180214915  call    cs:__imp_OpenThemeData
0x18021491b  mov     r12, rax
0x18021491e  test    rax, rax
0x180214921  jz      loc_180214AB7
0x180214927  mov     rcx, [rbp+57h+var_80]
0x18021492b  lea     rax, [rbp+57h+var_78]
0x18021492f  mov     [rsp+0C0h+psz], rax; psz
0x180214934  lea     ebx, [r13+2]
0x180214938  mov     qword ptr [rbp+57h+var_78.cx], rcx
0x18021493c  lea     r9d, [r13+1]; iStateId
0x180214940  mov     [rsp+0C0h+eSize], ebx; eSize
0x180214944  lea     r8d, [r13+3]; iPartId
0x180214948  mov     rcx, r12; hTheme
0x18021494b  mov     qword ptr [rsp+0C0h+cGrow], r13; prc
0x180214950  mov     rdx, r15; hdc
0x180214953  call    cs:__imp_GetThemePartSize
0x180214959  mov     r8d, esi; int
0x18021495c  mov     edx, edi; int
0x18021495e  mov     rcx, r15; HDC
0x180214961  call    ?CreateDIB@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAPEAUtagRGBQUAD@@@Z; CreateDIB(HDC__ *,int,int,tagRGBQUAD * *)
0x180214966  xor     r10d, r10d
0x180214969  mov     r13, rax
0x18021496c  test    rax, rax
0x18021496f  jz      loc_180214A43
0x180214975  mov     rcx, qword ptr [rbp+57h+var_78.cx]
0x180214979  mov     [rbp+57h+var_60], r10
0x18021497d  mov     [rbp+57h+var_58], edi
0x180214980  mov     [rbp+57h+var_54], esi
0x180214983  mov     qword ptr [rbp+57h+pRect.left], r10
0x180214987  mov     [rbp+57h+pRect.right], edi
0x18021498a  mov     [rbp+57h+pRect.bottom], esi
0x18021498d  cmp     edi, ecx
0x18021498f  jle     short loc_1802149BF
0x180214991  mov     r9d, [rbp+57h+var_78.cy]
0x180214995  cmp     esi, r9d
0x180214998  jle     short loc_1802149BF
0x18021499a  sub     edi, ecx
0x18021499c  sub     esi, r9d
0x18021499f  mov     eax, edi
0x1802149a1  cdq
0x1802149a2  idiv    ebx
0x1802149a4  mov     r8d, eax
0x1802149a7  mov     [rbp+57h+pRect.left], eax
0x1802149aa  mov     eax, esi
0x1802149ac  cdq
0x1802149ad  idiv    ebx
0x1802149af  lea     edx, [r8+rcx]
0x1802149b3  mov     [rbp+57h+pRect.top], eax
0x1802149b6  add     eax, r9d
0x1802149b9  mov     [rbp+57h+pRect.bottom], eax
0x1802149bc  mov     [rbp+57h+pRect.right], edx
0x1802149bf  mov     edi, r10d
0x1802149c2  lea     rsi, __ImageBase
0x1802149c9  mov     rdx, r13; h
0x1802149cc  mov     rcx, r15; hdc
0x1802149cf  call    cs:__imp_SelectObject
0x1802149d5  xor     r8d, r8d
0x1802149d8  lea     rdx, [rbp+57h+var_60]
0x1802149dc  mov     rcx, r15
0x1802149df  mov     rbx, rax
0x1802149e2  call    SHFillRectClr
0x1802149e7  movsxd  r8, edi
0x1802149ea  lea     rax, [rbp+57h+pRect]
0x1802149ee  mov     qword ptr [rsp+0C0h+eSize], 0; pClipRect
0x1802149f7  mov     rdx, r15; hdc
0x1802149fa  mov     rcx, r12; hTheme
0x1802149fd  mov     qword ptr [rsp+0C0h+cGrow], rax; pRect
0x180214a02  mov     r9d, ds:rva dword_1805E05C0[rsi+r8*4]; iStateId
0x180214a0a  mov     r8d, ds:rva dword_1805E05B0[rsi+r8*4]; iPartId
0x180214a12  call    cs:__imp_DrawThemeBackground
0x180214a18  mov     rdx, rbx; h
0x180214a1b  mov     rcx, r15; hdc
0x180214a1e  call    cs:__imp_SelectObject
0x180214a24  mov     rcx, [r14+30h]; himl
0x180214a28  xor     r8d, r8d; hbmMask
0x180214a2b  mov     rdx, r13; hbmImage
0x180214a2e  call    ImageList_Add
0x180214a33  inc     edi
0x180214a35  cmp     edi, 4
0x180214a38  jb      short loc_1802149C9
0x180214a3a  mov     rcx, r13; ho
0x180214a3d  call    cs:__imp_DeleteObject
0x180214a43  mov     rcx, cs:g_hinst; hInstance
0x180214a4a  xor     r13d, r13d
0x180214a4d  xor     r9d, r9d; lpColorMap
0x180214a50  mov     [rsp+0C0h+cGrow], r13d; iNumMaps
0x180214a55  xor     r8d, r8d; wFlags
0x180214a58  mov     edx, 211h; idBitmap
0x180214a5d  call    CreateMappedBitmap
0x180214a62  mov     rbx, rax
0x180214a65  test    rax, rax
0x180214a68  jz      short loc_180214AAC
0x180214a6a  lea     r9, [rbp+57h+pRect]
0x180214a6e  mov     qword ptr [rbp+57h+pRect.left], r13
0x180214a72  lea     r8d, [r13+1]
0x180214a76  mov     rdx, rax
0x180214a79  lea     rcx, [rbp+57h+var_80]
0x180214a7d  call    CenterBitmapForImageList
0x180214a82  test    eax, eax
0x180214a84  js      short loc_180214AA3
0x180214a86  mov     rdx, qword ptr [rbp+57h+pRect.left]; hbmImage
0x180214a8a  mov     r8d, 0FF000000h; crMask
0x180214a90  mov     rcx, [r14+30h]; himl
0x180214a94  call    ImageList_AddMasked
0x180214a99  mov     rcx, qword ptr [rbp+57h+pRect.left]; ho
0x180214a9d  call    cs:__imp_DeleteObject
0x180214aa3  mov     rcx, rbx; ho
0x180214aa6  call    cs:__imp_DeleteObject
0x180214aac  mov     rcx, r12; hTheme
0x180214aaf  call    cs:__imp_CloseThemeData
0x180214ab5  jmp     short loc_180214B28
0x180214ab7  mov     rcx, cs:g_hinst; hInstance
0x180214abe  lea     eax, [rdi+rdi*4]
0x180214ac1  xor     r9d, r9d; lpColorMap
0x180214ac4  mov     dword ptr [rbp+57h+var_80], eax
0x180214ac7  xor     r8d, r8d; wFlags
0x180214aca  mov     dword ptr [rbp+57h+var_80+4], esi
0x180214acd  mov     edx, 210h; idBitmap
0x180214ad2  mov     [rsp+0C0h+cGrow], r13d; iNumMaps
0x180214ad7  call    CreateMappedBitmap
0x180214adc  mov     rbx, rax
0x180214adf  test    rax, rax
0x180214ae2  jz      short loc_180214B28
0x180214ae4  lea     r9, [rbp+57h+pRect]
0x180214ae8  mov     qword ptr [rbp+57h+pRect.left], r13
0x180214aec  mov     r8d, 5
0x180214af2  lea     rcx, [rbp+57h+var_80]
0x180214af6  mov     rdx, rax
0x180214af9  call    CenterBitmapForImageList
0x180214afe  test    eax, eax
0x180214b00  js      short loc_180214B1F
0x180214b02  mov     rdx, qword ptr [rbp+57h+pRect.left]; hbmImage
0x180214b06  mov     r8d, 0FF000000h; crMask
0x180214b0c  mov     rcx, [r14+30h]; himl
0x180214b10  call    ImageList_AddMasked
0x180214b15  mov     rcx, qword ptr [rbp+57h+pRect.left]; ho
0x180214b19  call    cs:__imp_DeleteObject
0x180214b1f  mov     rcx, rbx; ho
0x180214b22  call    cs:__imp_DeleteObject
0x180214b28  mov     rcx, r15; hdc
0x180214b2b  call    cs:__imp_DeleteDC
0x180214b31  mov     r9, [r14+30h]; lParam
0x180214b35  xor     r8d, r8d; wParam
0x180214b38  mov     rcx, [r14+20h]; hWnd
0x180214b3c  mov     edx, 1109h; Msg
0x180214b41  call    cs:__imp_SendMessageW
0x180214b47  test    rax, rax
0x180214b4a  jz      short loc_180214B54
0x180214b4c  mov     rcx, rax; himl
0x180214b4f  call    ImageList_Destroy
0x180214b54  mov     rcx, [rbp+57h+var_50]
0x180214b58  xor     rcx, rsp; StackCookie
0x180214b5b  call    __security_check_cookie
0x180214b60  add     rsp, 88h
0x180214b67  pop     r15
0x180214b69  pop     r14
0x180214b6b  pop     r13
0x180214b6d  pop     r12
0x180214b6f  pop     rdi
0x180214b70  pop     rsi
0x180214b71  pop     rbx
0x180214b72  pop     rbp
0x180214b73  retn
```
