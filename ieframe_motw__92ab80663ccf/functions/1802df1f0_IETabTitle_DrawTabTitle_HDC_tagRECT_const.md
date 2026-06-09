# IETabTitle::_DrawTabTitle(HDC__ *,tagRECT const *)

- ea: `0x1802df1f0`
- end: `0x1802df687`
- name: `?_DrawTabTitle@IETabTitle@@AEAAJPEAUHDC__@@PEBUtagRECT@@@Z`
- size: `1175`
- prototype: `__int64 __fastcall(IETabTitle *__hidden this, HDC hdc, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1802dba70`

## callees

- `0x180012490`
- `0x1800204e8`
- `0x1800207d0`
- `0x18008cfe0`
- `0x1800975f0`
- `0x18009b248`
- `0x1800b7864`
- `0x1802d92e8`
- `0x1802d9320`
- `0x1802d9354`
- `0x1802d93c4`
- `0x1802d93f8`
- `0x1802df1f0`
- `0x180449070`
- `0x180484b60`
- `0x180591ef6`
- `0x180591f4a`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1802df387`
- `KERNEL32!TlsGetValue` at `0x1802df387`
- `GDI32!CreateDIBSection` at `0x1802df2f2`
- `GDI32!CreateDIBSection` at `0x1802df2f2`
- `GDI32!DeleteObject` at `0x1802df639`
- `GDI32!DeleteObject` at `0x1802df639`
- `GDI32!SelectObject` at `0x1802df368`
- `GDI32!SelectObject` at `0x1802df425`
- `GDI32!SelectObject` at `0x1802df600`
- `GDI32!SelectObject` at `0x1802df62a`
- `GDI32!SelectObject` at `0x1802df368`
- `GDI32!SelectObject` at `0x1802df425`
- `GDI32!SelectObject` at `0x1802df600`
- `GDI32!SelectObject` at `0x1802df62a`
- `GDI32!DeleteDC` at `0x1802df651`
- `GDI32!DeleteDC` at `0x1802df651`
- `GDI32!CreateCompatibleDC` at `0x1802df291`
- `GDI32!CreateCompatibleDC` at `0x1802df291`
- `USER32!GetClientRect` at `0x1802df282`
- `USER32!GetClientRect` at `0x1802df282`
- `USER32!GetSysColor` at `0x1802df487`
- `USER32!GetSysColor` at `0x1802df487`
- `MSIMG32!AlphaBlend` at `0x1802df5e4`
- `MSIMG32!AlphaBlend` at `0x1802df5e4`
- `UxTheme!DrawThemeTextEx` at `0x1802df4e2`
- `UxTheme!DrawThemeTextEx` at `0x1802df4e2`
- `UxTheme!OpenThemeData` at `0x1802df49f`
- `UxTheme!OpenThemeData` at `0x1802df49f`

## pseudocode

```c
__int64 __fastcall IETabTitle::_DrawTabTitle(IETabTitle *this, HDC hdc, const struct tagRECT *a3)
{
  unsigned int v6; // esi
  HWND v7; // rax
  HDC CompatibleDC; // r12
  HBITMAP v9; // rbx
  BYTE v10; // r13
  LPVOID Value; // rax
  __int64 (__fastcall **v12)(LPVOID, const unsigned __int16 *, __int64, _QWORD, int, int, _DWORD); // rcx
  __int64 (__fastcall *v13)(LPVOID, const unsigned __int16 *, __int64, _QWORD, int, int, _DWORD); // r14
  int FontQuality; // esi
  int FontStyle; // edi
  unsigned int FontWeight; // ebx
  const unsigned __int16 *FontFace; // rax
  LPVOID v18; // rdi
  __int64 v19; // r8
  void *v20; // rbx
  HGDIOBJ v21; // rsi
  struct DirectUI::Value *v22; // rax
  char v23; // bl
  HTHEME v24; // rax
  bool v25; // bl
  const wchar_t *Class; // rax
  struct DirectUI::Value *v27; // rax
  char v28; // bl
  struct DirectUI::Value *v29; // rax
  char v30; // bl
  int hSection; // [rsp+20h] [rbp-E0h]
  int dwTextFlags; // [rsp+60h] [rbp-A0h]
  BLENDFUNCTION ftn; // [rsp+60h] [rbp-A0h]
  int cchText[2]; // [rsp+68h] [rbp-98h] BYREF
  struct DirectUI::HWNDElement *v36; // [rsp+70h] [rbp-90h] BYREF
  struct DirectUI::Value *v37; // [rsp+78h] [rbp-88h] BYREF
  struct DirectUI::Value *v38; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v39; // [rsp+88h] [rbp-78h]
  LPCWSTR pszText; // [rsp+90h] [rbp-70h]
  const struct tagRECT *v41; // [rsp+98h] [rbp-68h]
  HDC hdcDest; // [rsp+A0h] [rbp-60h]
  HBITMAP v43; // [rsp+A8h] [rbp-58h]
  HGDIOBJ h; // [rsp+B0h] [rbp-50h]
  DTTOPTS pOptions; // [rsp+C0h] [rbp-40h] BYREF
  struct tagRECT Rect; // [rsp+110h] [rbp+10h] BYREF
  BITMAPINFO pbmi; // [rsp+120h] [rbp+20h] BYREF
  struct tagRECT pRect; // [rsp+150h] [rbp+50h] BYREF

  v41 = a3;
  hdcDest = hdc;
  v36 = 0;
  v6 = -2147467259;
  if ( hdc )
  {
    if ( (*((_BYTE *)this + 149) & 0x40) != 0 && (int)DUI_GetElementRootHWNDElement(this, &v36) >= 0 )
    {
      Rect = 0;
      v7 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::HWNDElement *))(*(_QWORD *)v36 + 360LL))(v36);
      GetClientRect(v7, &Rect);
      CompatibleDC = CreateCompatibleDC(hdc);
      if ( CompatibleDC )
      {
        pbmi.bmiHeader.biWidth = Rect.right - Rect.left;
        pbmi.bmiHeader.biHeight = Rect.top - Rect.bottom;
        memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
        pbmi.bmiHeader.biSize = 40;
        *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
        v43 = CreateDIBSection(hdc, &pbmi, 0, 0, 0, 0);
        v9 = v43;
        if ( v43 )
        {
          v38 = 0;
          v10 = 0x80;
          pszText = DirectUI::Element::GetContentString(this, &v38);
          *(_QWORD *)cchText = 0;
          v6 = StringCchLengthW(pszText, 0x80u, (unsigned __int64 *)cchText);
          LODWORD(v36) = v6;
          dwTextFlags = (unsigned int)IsBiDiLocalizedSystemEx() != 0 ? 165926 : 34852;
          pRect = *a3;
          h = SelectObject(CompatibleDC, v9);
          if ( h )
          {
            Value = TlsGetValue(DirectUI::g_dwFontCacheSlot);
            v39 = Value;
            if ( Value )
            {
              v12 = *(__int64 (__fastcall ***)(LPVOID, const unsigned __int16 *, __int64, _QWORD, int, int, _DWORD))Value;
              v37 = 0;
              v13 = *v12;
              FontQuality = DirectUI::Element::GetFontQuality(this);
              FontStyle = DirectUI::Element::GetFontStyle(this);
              FontWeight = DirectUI::Element::GetFontWeight(this);
              DirectUI::Element::GetFontSize(this);
              FontFace = DirectUI::Element::GetFontFace(this, &v37);
              hSection = FontStyle;
              v18 = v39;
              v20 = (void *)v13(v39, FontFace, v19, FontWeight, hSection, FontQuality, 0);
              DirectUI::Value::Release(v37);
              if ( v20 )
              {
                v21 = SelectObject(CompatibleDC, v20);
                if ( v21 )
                {
                  pOptions.dwSize = 72;
                  memset_0(&pOptions.dwFlags, 0, 0x44u);
                  pOptions.dwFlags = 0x2000;
                  v22 = DirectUI::Element::GetValue(this, (const struct DirectUI::PropertyInfo *)&off_1805B3D90, 2, 0);
                  v23 = *((_BYTE *)v22 + 8);
                  DirectUI::Value::Release(v22);
                  if ( v23 )
                  {
                    pOptions.dwFlags |= 1u;
                    pOptions.crText = GetSysColor(9);
                  }
                  v24 = OpenThemeData(0, L"SearchBox");
                  if ( DrawThemeTextEx(v24, CompatibleDC, 0, 0, pszText, cchText[0], dwTextFlags, &pRect, &pOptions) >= 0 )
                  {
                    v25 = 0;
                    *(_QWORD *)cchText = 0;
                    Class = DirectUI::Element::GetClass(this, (struct DirectUI::Value **)cchText);
                    if ( Class )
                      v25 = wcscmp_0(Class, L"hung") == 0;
                    if ( IsHighContrast()
                      || !v25
                      && ((*((_BYTE *)this + 148) & 0x10) != 0
                       || (v27 = DirectUI::Element::GetValue(
                                   this,
                                   (const struct DirectUI::PropertyInfo *)&off_1805B3DC0,
                                   2,
                                   0),
                           v28 = *((_BYTE *)v27 + 8),
                           DirectUI::Value::Release(v27),
                           v28)
                       || (v29 = DirectUI::Element::GetValue(
                                   this,
                                   (const struct DirectUI::PropertyInfo *)&off_1805B3F58,
                                   2,
                                   0),
                           v30 = *((_BYTE *)v29 + 8),
                           DirectUI::Value::Release(v29),
                           v10 = -52,
                           v30)) )
                    {
                      v10 = -1;
                    }
                    ftn.AlphaFormat = 1;
                    *(_WORD *)&ftn.BlendOp = 0;
                    ftn.SourceConstantAlpha = v10;
                    AlphaBlend(
                      hdcDest,
                      v41->left,
                      v41->top,
                      v41->right - v41->left,
                      v41->bottom - v41->top,
                      CompatibleDC,
                      v41->left,
                      v41->top,
                      v41->right - v41->left,
                      v41->bottom - v41->top,
                      ftn);
                    ValueRef::~ValueRef((ValueRef *)cchText);
                  }
                  SelectObject(CompatibleDC, v21);
                }
              }
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 8LL))(v18);
              v9 = v43;
              v6 = (unsigned int)v36;
            }
            SelectObject(CompatibleDC, h);
          }
          DeleteObject(v9);
          ValueRef::~ValueRef((ValueRef *)&v38);
        }
        DeleteDC(CompatibleDC);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1802df1f0  mov     [rsp-8+arg_18], rbx
0x1802df1f5  push    rbp
0x1802df1f6  push    rsi
0x1802df1f7  push    rdi
0x1802df1f8  push    r12
0x1802df1fa  push    r13
0x1802df1fc  push    r14
0x1802df1fe  push    r15
0x1802df200  lea     rbp, [rsp-70h]
0x1802df205  sub     rsp, 170h
0x1802df20c  mov     rax, cs:__security_cookie
0x1802df213  xor     rax, rsp
0x1802df216  mov     [rbp+0A0h+var_40], rax
0x1802df21a  xor     r14d, r14d
0x1802df21d  mov     [rbp+0A0h+var_108], r8
0x1802df221  mov     [rbp+0A0h+hdcDest], rdx
0x1802df225  mov     rdi, r8
0x1802df228  mov     [rsp+1A0h+var_130], r14
0x1802df22d  mov     rbx, rdx
0x1802df230  mov     r15, rcx
0x1802df233  mov     esi, 80004005h
0x1802df238  test    rdx, rdx
0x1802df23b  jz      loc_1802DF65D
0x1802df241  test    byte ptr [rcx+95h], 40h
0x1802df248  jz      loc_1802DF65D
0x1802df24e  lea     rdx, [rsp+1A0h+var_130]; struct DirectUI::HWNDElement **
0x1802df253  call    ?DUI_GetElementRootHWNDElement@@YAJPEAVElement@DirectUI@@PEAPEAVHWNDElement@2@@Z; DUI_GetElementRootHWNDElement(DirectUI::Element *,DirectUI::HWNDElement * *)
0x1802df258  test    eax, eax
0x1802df25a  js      loc_1802DF65D
0x1802df260  mov     rcx, [rsp+1A0h+var_130]
0x1802df265  xorps   xmm0, xmm0
0x1802df268  movups  xmmword ptr [rbp+0A0h+Rect.left], xmm0
0x1802df26c  mov     rax, [rcx]
0x1802df26f  mov     rax, [rax+168h]
0x1802df276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802df27b  mov     rcx, rax; hWnd
0x1802df27e  lea     rdx, [rbp+0A0h+Rect]; lpRect
0x1802df282  call    cs:__imp_GetClientRect
0x1802df289  nop     dword ptr [rax+rax+00h]
0x1802df28e  mov     rcx, rbx; hdc
0x1802df291  call    cs:__imp_CreateCompatibleDC
0x1802df298  nop     dword ptr [rax+rax+00h]
0x1802df29d  mov     r12, rax
0x1802df2a0  test    rax, rax
0x1802df2a3  jz      loc_1802DF65D
0x1802df2a9  mov     ecx, [rbp+0A0h+Rect.right]
0x1802df2ac  lea     rdx, [rbp+0A0h+pbmi]; pbmi
0x1802df2b0  sub     ecx, [rbp+0A0h+Rect.left]
0x1802df2b3  xorps   xmm0, xmm0
0x1802df2b6  movups  xmmword ptr [rbp+0A0h+pbmi.bmiHeader.biWidth], xmm0
0x1802df2ba  mov     [rbp+0A0h+pbmi.bmiHeader.biWidth], ecx
0x1802df2bd  xor     eax, eax
0x1802df2bf  mov     ecx, [rbp+0A0h+Rect.top]
0x1802df2c2  xor     r9d, r9d; ppvBits
0x1802df2c5  sub     ecx, [rbp+0A0h+Rect.bottom]
0x1802df2c8  xor     r8d, r8d; usage
0x1802df2cb  mov     [rbp+0A0h+pbmi.bmiHeader.biHeight], ecx
0x1802df2ce  mov     rcx, rbx; hdc
0x1802df2d1  mov     [rsp+1A0h+offset], r14d; offset
0x1802df2d6  movups  xmmword ptr [rbp+0A0h+pbmi.bmiHeader.biSizeImage], xmm0
0x1802df2da  mov     qword ptr [rbp+0A0h+pbmi.bmiHeader.biClrImportant], rax
0x1802df2de  mov     [rbp+0A0h+pbmi.bmiHeader.biSize], 28h ; '('
0x1802df2e5  mov     qword ptr [rbp+0A0h+pbmi.bmiHeader.biPlanes], 200001h
0x1802df2ed  mov     [rsp+1A0h+hSection], r14; hSection
0x1802df2f2  call    cs:__imp_CreateDIBSection
0x1802df2f9  nop     dword ptr [rax+rax+00h]
0x1802df2fe  mov     [rbp+0A0h+var_F8], rax
0x1802df302  mov     rbx, rax
0x1802df305  test    rax, rax
0x1802df308  jz      loc_1802DF64E
0x1802df30e  lea     rdx, [rbp+0A0h+var_120]; struct DirectUI::Value **
0x1802df312  mov     [rbp+0A0h+var_120], r14
0x1802df316  mov     rcx, r15; this
0x1802df319  call    ?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x1802df31e  mov     r13d, 80h
0x1802df324  mov     [rbp+0A0h+pszText], rax
0x1802df328  mov     edx, r13d; unsigned __int64
0x1802df32b  mov     qword ptr [rsp+1A0h+cchText], r14
0x1802df330  lea     r8, [rsp+1A0h+cchText]; unsigned __int64 *
0x1802df335  mov     rcx, rax; unsigned __int16 *
0x1802df338  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1802df33d  mov     esi, eax
0x1802df33f  mov     dword ptr [rsp+1A0h+var_130], eax
0x1802df343  call    IsBiDiLocalizedSystemEx
0x1802df348  movups  xmm0, xmmword ptr [rdi]
0x1802df34b  neg     eax
0x1802df34d  mov     rdx, rbx; h
0x1802df350  mov     rcx, r12; hdc
0x1802df353  sbb     eax, eax
0x1802df355  and     eax, 20002h
0x1802df35a  add     eax, 8824h
0x1802df35f  mov     dword ptr [rsp+1A0h+var_140.BlendOp], eax
0x1802df363  movdqu  xmmword ptr [rbp+0A0h+var_50.left], xmm0
0x1802df368  call    cs:__imp_SelectObject
0x1802df36f  nop     dword ptr [rax+rax+00h]
0x1802df374  mov     [rbp+0A0h+h], rax
0x1802df378  test    rax, rax
0x1802df37b  jz      loc_1802DF636
0x1802df381  mov     ecx, cs:?g_dwFontCacheSlot@DirectUI@@3KA; dwTlsIndex
0x1802df387  call    cs:__imp_TlsGetValue
0x1802df38e  nop     dword ptr [rax+rax+00h]
0x1802df393  mov     [rbp+0A0h+var_118], rax
0x1802df397  test    rax, rax
0x1802df39a  jz      loc_1802DF623
0x1802df3a0  mov     rcx, [rax]
0x1802df3a3  mov     [rsp+1A0h+var_128], r14
0x1802df3a8  mov     r14, [rcx]
0x1802df3ab  mov     rcx, r15; this
0x1802df3ae  call    ?GetFontQuality@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontQuality(void)
0x1802df3b3  mov     rcx, r15; this
0x1802df3b6  mov     esi, eax
0x1802df3b8  call    ?GetFontStyle@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontStyle(void)
0x1802df3bd  mov     rcx, r15; this
0x1802df3c0  mov     edi, eax
0x1802df3c2  call    ?GetFontWeight@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontWeight(void)
0x1802df3c7  mov     rcx, r15; this
0x1802df3ca  mov     ebx, eax
0x1802df3cc  call    ?GetFontSize@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontSize(void)
0x1802df3d1  lea     rdx, [rsp+1A0h+var_128]; struct DirectUI::Value **
0x1802df3d6  mov     rcx, r15; this
0x1802df3d9  mov     r8d, eax
0x1802df3dc  call    ?GetFontFace@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetFontFace(DirectUI::Value * *)
0x1802df3e1  mov     [rsp+1A0h+dwTextFlags], 0
0x1802df3e9  mov     rdx, rax
0x1802df3ec  mov     [rsp+1A0h+offset], esi
0x1802df3f0  mov     r9d, ebx
0x1802df3f3  mov     dword ptr [rsp+1A0h+hSection], edi
0x1802df3f7  mov     rax, r14
0x1802df3fa  mov     rdi, [rbp+0A0h+var_118]
0x1802df3fe  mov     rcx, rdi
0x1802df401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802df406  mov     rcx, [rsp+1A0h+var_128]; this
0x1802df40b  mov     rbx, rax
0x1802df40e  call    ?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1802df413  xor     r14d, r14d
0x1802df416  test    rbx, rbx
0x1802df419  jz      loc_1802DF60C
0x1802df41f  mov     rdx, rbx; h
0x1802df422  mov     rcx, r12; hdc
0x1802df425  call    cs:__imp_SelectObject
0x1802df42c  nop     dword ptr [rax+rax+00h]
0x1802df431  mov     rsi, rax
0x1802df434  test    rax, rax
0x1802df437  jz      loc_1802DF60C
0x1802df43d  xor     edx, edx; Val
0x1802df43f  mov     [rbp+0A0h+var_E0.dwSize], 48h ; 'H'
0x1802df446  lea     r8d, [r13-3Ch]; Size
0x1802df44a  lea     rcx, [rbp+0A0h+var_E0.dwFlags]; void *
0x1802df44e  call    memset_0
0x1802df453  xor     r9d, r9d; struct DirectUI::UpdateCache *
0x1802df456  mov     [rbp+0A0h+var_E0.dwFlags], 2000h
0x1802df45d  lea     r8d, [r13-7Eh]; int
0x1802df461  mov     rcx, r15; this
0x1802df464  lea     rdx, off_1805B3D90; struct DirectUI::PropertyInfo *
0x1802df46b  call    ?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1802df470  mov     rcx, rax; this
0x1802df473  mov     bl, [rax+8]
0x1802df476  call    ?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1802df47b  test    bl, bl
0x1802df47d  jz      short loc_1802DF496
0x1802df47f  or      [rbp+0A0h+var_E0.dwFlags], 1
0x1802df483  lea     ecx, [r13-77h]; nIndex
0x1802df487  call    cs:__imp_GetSysColor
0x1802df48e  nop     dword ptr [rax+rax+00h]
0x1802df493  mov     [rbp+0A0h+var_E0.crText], eax
0x1802df496  lea     rdx, aSearchbox; "SearchBox"
0x1802df49d  xor     ecx, ecx; hwnd
0x1802df49f  call    cs:__imp_OpenThemeData
0x1802df4a6  nop     dword ptr [rax+rax+00h]
0x1802df4ab  xor     r9d, r9d; iStateId
0x1802df4ae  xor     r8d, r8d; iPartId
0x1802df4b1  mov     rcx, rax; hTheme
0x1802df4b4  mov     rdx, r12; hdc
0x1802df4b7  lea     rax, [rbp+0A0h+var_E0]
0x1802df4bb  mov     [rsp+1A0h+pOptions], rax; pOptions
0x1802df4c0  lea     rax, [rbp+0A0h+var_50]
0x1802df4c4  mov     [rsp+1A0h+pRect], rax; pRect
0x1802df4c9  mov     eax, dword ptr [rsp+1A0h+var_140.BlendOp]
0x1802df4cd  mov     [rsp+1A0h+dwTextFlags], eax; dwTextFlags
0x1802df4d1  mov     eax, [rsp+1A0h+cchText]
0x1802df4d5  mov     [rsp+1A0h+offset], eax; cchText
0x1802df4d9  mov     rax, [rbp+0A0h+pszText]
0x1802df4dd  mov     [rsp+1A0h+hSection], rax; pszText
0x1802df4e2  call    cs:__imp_DrawThemeTextEx
0x1802df4e9  nop     dword ptr [rax+rax+00h]
0x1802df4ee  test    eax, eax
0x1802df4f0  js      loc_1802DF5FA
0x1802df4f6  lea     rdx, [rsp+1A0h+cchText]; struct DirectUI::Value **
0x1802df4fb  movzx   ebx, r14b
0x1802df4ff  mov     rcx, r15; this
0x1802df502  mov     qword ptr [rsp+1A0h+cchText], r14
0x1802df507  call    ?GetClass@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetClass(DirectUI::Value * *)
0x1802df50c  test    rax, rax
0x1802df50f  jz      short loc_1802DF52A
0x1802df511  lea     rdx, aHung; "hung"
0x1802df518  mov     rcx, rax; String1
0x1802df51b  call    wcscmp_0
0x1802df520  test    eax, eax
0x1802df522  mov     eax, 1
0x1802df527  cmovz   ebx, eax
0x1802df52a  call    ?IsHighContrast@@YA_NXZ; IsHighContrast(void)
0x1802df52f  test    al, al
0x1802df531  jnz     short loc_1802DF590
0x1802df533  test    bl, bl
0x1802df535  jnz     short loc_1802DF593
0x1802df537  test    byte ptr [r15+94h], 10h
0x1802df53f  jnz     short loc_1802DF590
0x1802df541  xor     r9d, r9d; struct DirectUI::UpdateCache *
0x1802df544  lea     rdx, off_1805B3DC0; struct DirectUI::PropertyInfo *
0x1802df54b  mov     rcx, r15; this
0x1802df54e  lea     r13d, [r9+2]
0x1802df552  mov     r8d, r13d; int
0x1802df555  call    ?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1802df55a  mov     rcx, rax; this
0x1802df55d  mov     bl, [rax+8]
0x1802df560  call    ?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1802df565  test    bl, bl
0x1802df567  jnz     short loc_1802DF590
0x1802df569  xor     r9d, r9d; struct DirectUI::UpdateCache *
0x1802df56c  lea     rdx, off_1805B3F58; struct DirectUI::PropertyInfo *
0x1802df573  mov     r8d, r13d; int
0x1802df576  mov     rcx, r15; this
0x1802df579  call    ?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1802df57e  mov     rcx, rax; this
0x1802df581  mov     bl, [rax+8]
0x1802df584  call    ?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1802df589  mov     r13b, 0CCh
0x1802df58c  test    bl, bl
0x1802df58e  jz      short loc_1802DF593
0x1802df590  mov     r13b, 0FFh
0x1802df593  mov     rax, [rbp+0A0h+var_108]
0x1802df597  mov     rcx, [rbp+0A0h+hdcDest]; hdcDest
0x1802df59b  mov     [rsp+1A0h+var_140.AlphaFormat], 1
0x1802df5a0  mov     word ptr [rsp+1A0h+var_140.BlendOp], r14w
0x1802df5a6  mov     r8d, [rax+4]; yoriginDest
0x1802df5aa  mov     edx, [rax]; xoriginDest
0x1802df5ac  mov     r10d, [rax+0Ch]
0x1802df5b0  mov     r9d, [rax+8]
0x1802df5b4  sub     r10d, r8d
0x1802df5b7  sub     r9d, edx; wDest
0x1802df5ba  mov     [rsp+1A0h+var_140.SourceConstantAlpha], r13b
0x1802df5bf  mov     eax, dword ptr [rsp+1A0h+var_140.BlendOp]
0x1802df5c3  mov     dword ptr [rsp+1A0h+ftn.BlendOp], eax; ftn
0x1802df5c7  mov     [rsp+1A0h+hSrc], r10d; hSrc
0x1802df5cc  mov     dword ptr [rsp+1A0h+pOptions], r9d; wSrc
0x1802df5d1  mov     dword ptr [rsp+1A0h+pRect], r8d; yoriginSrc
0x1802df5d6  mov     [rsp+1A0h+dwTextFlags], edx; xoriginSrc
0x1802df5da  mov     qword ptr [rsp+1A0h+offset], r12; hdcSrc
0x1802df5df  mov     dword ptr [rsp+1A0h+hSection], r10d; hDest
0x1802df5e4  call    cs:__imp_AlphaBlend
0x1802df5eb  nop     dword ptr [rax+rax+00h]
0x1802df5f0  lea     rcx, [rsp+1A0h+cchText]; this
0x1802df5f5  call    ??1ValueRef@@QEAA@XZ; ValueRef::~ValueRef(void)
0x1802df5fa  mov     rdx, rsi; h
0x1802df5fd  mov     rcx, r12; hdc
0x1802df600  call    cs:__imp_SelectObject
0x1802df607  nop     dword ptr [rax+rax+00h]
0x1802df60c  mov     rax, [rdi]
0x1802df60f  mov     rcx, rdi
0x1802df612  mov     rax, [rax+8]
0x1802df616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802df61b  mov     rbx, [rbp+0A0h+var_F8]
0x1802df61f  mov     esi, dword ptr [rsp+1A0h+var_130]
0x1802df623  mov     rdx, [rbp+0A0h+h]; h
0x1802df627  mov     rcx, r12; hdc
0x1802df62a  call    cs:__imp_SelectObject
0x1802df631  nop     dword ptr [rax+rax+00h]
0x1802df636  mov     rcx, rbx; ho
0x1802df639  call    cs:__imp_DeleteObject
0x1802df640  nop     dword ptr [rax+rax+00h]
0x1802df645  lea     rcx, [rbp+0A0h+var_120]; this
0x1802df649  call    ??1ValueRef@@QEAA@XZ; ValueRef::~ValueRef(void)
0x1802df64e  mov     rcx, r12; hdc
0x1802df651  call    cs:__imp_DeleteDC
0x1802df658  nop     dword ptr [rax+rax+00h]
0x1802df65d  mov     eax, esi
0x1802df65f  mov     rcx, [rbp+0A0h+var_40]
0x1802df663  xor     rcx, rsp; StackCookie
0x1802df666  call    __security_check_cookie
0x1802df66b  mov     rbx, [rsp+1A0h+arg_18]
0x1802df673  add     rsp, 170h
0x1802df67a  pop     r15
0x1802df67c  pop     r14
0x1802df67e  pop     r13
0x1802df680  pop     r12
0x1802df682  pop     rdi
0x1802df683  pop     rsi
0x1802df684  pop     rbp
0x1802df685  retn
```
