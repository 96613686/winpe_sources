# CMapiPreviewer::DrawItemOnHeader(ulong,ulong,wchar_t const *,ulong,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int)

- ea: `0x1800239c8`
- end: `0x18002430c`
- name: `?DrawItemOnHeader@CMapiPreviewer@@AEAAJKKPEB_WKHKKKKKKKH@Z`
- size: `2372`
- prototype: `__int64 __fastcall(CMapiPreviewer *this, unsigned int, unsigned int, const wchar_t *, unsigned int, int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops`

## callers

- `0x180023304`

## callees

- `0x1800031c0`
- `0x180004080`
- `0x18000419c`
- `0x180004850`
- `0x1800048c0`
- `0x180004d40`
- `0x18000557c`
- `0x180006270`
- `0x180006640`
- `0x180019084`
- `0x18001cc24`
- `0x180021ed8`
- `0x180022654`
- `0x1800239c8`
- `0x1800247b0`
- `0x180024ea0`
- `0x180025728`
- `0x180025948`
- `0x1800259f0`
- `0x180026570`
- `0x1800265dc`
- `0x180027178`
- `0x180034094`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1800242a2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1800242a2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023da7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023dc8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023ddb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023e2b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023ee1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023da7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023dc8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023ddb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023e2b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180023ee1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x180023c18`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x180023c18`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180023f5f`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180023f5f`
- `USER32!ReleaseDC` at `0x1800242b7`
- `USER32!ReleaseDC` at `0x1800242b7`
- `USER32!GetDC` at `0x180023c3b`
- `USER32!GetDC` at `0x180023c3b`
- `GDI32!CreateFontIndirectW` at `0x180023d79`
- `GDI32!CreateFontIndirectW` at `0x180024065`
- `GDI32!CreateFontIndirectW` at `0x180023d79`
- `GDI32!CreateFontIndirectW` at `0x180024065`
- `GDI32!GetTextExtentPoint32W` at `0x1800240d2`
- `GDI32!GetTextExtentPoint32W` at `0x1800240d2`
- `GDI32!GetTextMetricsW` at `0x180023f36`
- `GDI32!GetTextMetricsW` at `0x180024115`
- `GDI32!GetTextMetricsW` at `0x180023f36`
- `GDI32!GetTextMetricsW` at `0x180024115`
- `GDI32!GetDeviceCaps` at `0x180023cc9`
- `GDI32!GetDeviceCaps` at `0x180023fd9`
- `GDI32!GetDeviceCaps` at `0x180023cc9`
- `GDI32!GetDeviceCaps` at `0x180023fd9`
- `GDI32!SelectObject` at `0x180023efb`
- `GDI32!SelectObject` at `0x18002408f`
- `GDI32!SelectObject` at `0x180024149`
- `GDI32!SelectObject` at `0x180023efb`
- `GDI32!SelectObject` at `0x18002408f`
- `GDI32!SelectObject` at `0x180024149`
- `GDI32!DeleteObject` at `0x180024281`
- `GDI32!DeleteObject` at `0x180024294`
- `GDI32!DeleteObject` at `0x180024281`
- `GDI32!DeleteObject` at `0x180024294`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMapiPreviewer::DrawItemOnHeader(
        CMapiPreviewer *this,
        unsigned int a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11,
        unsigned int a12,
        unsigned int a13,
        int a14)
{
  unsigned int v18; // r12d
  __int64 v19; // rcx
  int AttachmentList; // eax
  int Error; // edi
  __int64 v22; // rcx
  __int64 v23; // rcx
  HWND Window; // r14
  HDC DC; // r15
  unsigned int v26; // ebx
  HFONT v27; // r12
  LPCWSTR *v28; // rbx
  __int64 v29; // rax
  unsigned int v30; // r13d
  const WCHAR *v31; // rbx
  unsigned int SystemMetrics; // eax
  int DeviceCaps; // eax
  bool v34; // cf
  void *v35; // rax
  __int64 v36; // r12
  int *v37; // r14
  __int64 v38; // rbx
  int Y; // [rsp+28h] [rbp-D8h]
  unsigned int v41; // [rsp+60h] [rbp-A0h] BYREF
  int v42; // [rsp+64h] [rbp-9Ch]
  LPARAM v43; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpString; // [rsp+70h] [rbp-90h] BYREF
  WPARAM wParam; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v46; // [rsp+80h] [rbp-80h] BYREF
  tagSIZE psizl; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *v48; // [rsp+90h] [rbp-70h] BYREF
  HGDIOBJ h; // [rsp+98h] [rbp-68h]
  unsigned int v50; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v51; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v52; // [rsp+B8h] [rbp-48h]
  __int128 v53; // [rsp+C0h] [rbp-40h]
  int v54; // [rsp+D0h] [rbp-30h]
  LOGFONTW lParam; // [rsp+E0h] [rbp-20h] BYREF
  tagTEXTMETRICW tm; // [rsp+140h] [rbp+40h] BYREF
  LOGFONTW lf; // [rsp+180h] [rbp+80h] BYREF

  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v43);
  v51 = 0;
  v18 = 0;
  v19 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 10;
  if ( a14 )
  {
    AttachmentList = CMapiPreviewer::GetAttachmentList((__int64)this, (__int64 *)&v51);
LABEL_3:
    Error = AttachmentList;
    goto LABEL_16;
  }
  Error = 0;
  if ( !a3 )
  {
    h = &CMapiNamedProp::`vftable';
    v50 = 0;
    if ( CMapiNamedProp::GetNamedPropId(0, *((struct IMAPIProp **)this + 27), a4, HIWORD(a5), &v50, Y) >= 0 )
    {
      if ( (unsigned int)(unsigned __int16)a5 - 30 <= 1 )
      {
        CMapiPreviewer::GetStringProp(
          (unsigned __int16)a5,
          *((_QWORD *)this + 27),
          (unsigned __int16)a5 | (v50 << 16),
          &v43);
        ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Trim(&v43);
      }
      else if ( (unsigned __int16)a5 == 64 )
      {
        lpString = 0;
        if ( CMapiPreviewer::GetFileTimeProp(
               (CMapiPreviewer *)(unsigned __int16)a5,
               *((struct IMessage **)this + 27),
               (v50 << 16) | 0x40,
               (struct _FILETIME *)&lpString) >= 0 )
          Error = CMapiPreviewer::ConvertFileTimeToString(v23, lpString, &v43);
      }
    }
LABEL_16:
    if ( Error < 0 )
      goto LABEL_104;
    goto LABEL_17;
  }
  if ( (unsigned int)(unsigned __int16)a3 - 30 <= 1 )
  {
    CMapiPreviewer::GetStringProp(0, *((_QWORD *)this + 27), a3, &v43);
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Trim(&v43);
    goto LABEL_16;
  }
  if ( (unsigned __int16)a3 == 64 )
  {
    lpString = 0;
    if ( CMapiPreviewer::GetFileTimeProp(0, *((struct IMessage **)this + 27), a3, (struct _FILETIME *)&lpString) < 0 )
    {
LABEL_17:
      v19 = v52;
      goto LABEL_18;
    }
    AttachmentList = CMapiPreviewer::ConvertFileTimeToString(v22, lpString, &v43);
    goto LABEL_3;
  }
LABEL_18:
  if ( *(int *)(v43 - 16) <= 0 && !v19 && a6 )
    goto LABEL_104;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&lpString);
  if ( !a2
    || (unsigned int)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
                       &lpString,
                       hInstance,
                       a2) )
  {
    Window = CreateWindowExW(
               0,
               L"RICHEDIT50W",
               0,
               0x50200804u,
               0,
               0,
               0,
               0,
               *((HWND *)this + 21),
               (HMENU)*((unsigned int *)this + 298),
               off_180053498,
               0);
    if ( !Window )
      Error = ResultFromLastError();
    DC = 0;
    if ( Error >= 0 )
    {
      DC = GetDC(*((HWND *)this + 21));
      if ( !DC )
        Error = ResultFromLastError();
    }
  }
  else
  {
    Error = -2147418113;
    Window = 0;
    DC = 0;
  }
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v48);
  if ( Error < 0
    || (unsigned int)ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
                       &v48,
                       hInstance,
                       250) )
  {
    v41 = 0;
    if ( Error >= 0 )
    {
      Error = GetULONGFromResource(a8, &v41);
      v18 = v41;
    }
    v26 = 0;
    v41 = 0;
    if ( Error >= 0 )
    {
      Error = GetULONGFromResource(a10, &v41);
      v26 = v41;
    }
  }
  else
  {
    Error = -2147467259;
    v26 = 0;
  }
  lf.lfHeight = -(v18 * GetDeviceCaps(DC, 90) / 0x48);
  *(_QWORD *)&lf.lfWidth = 0;
  lf.lfOrientation = 0;
  lf.lfWeight = v26 != 0 ? 700 : 400;
  memset(&lf.lfItalic, 0, 72);
  if ( Error >= 0 )
    Error = StringCchCopyW(lf.lfFaceName, 0x20u, v48);
  v27 = 0;
  if ( Error < 0 )
    goto LABEL_54;
  v27 = CreateFontIndirectW(&lf);
  if ( !v27 )
    Error = ResultFromLastError();
  if ( Error < 0 )
  {
LABEL_54:
    h = 0;
    if ( Error < 0 )
      goto LABEL_57;
    goto LABEL_55;
  }
  SendMessageW(Window, 0x445u, 0, 0x40000);
  SendMessageW(Window, 0x446u, 0, ((unsigned __int64)this + 32) & -(__int64)(this != 0));
  SendMessageW(Window, 0x30u, (WPARAM)v27, 0);
  lParam.lfHeight = 92;
  *(_QWORD *)&lParam.lfWidth = 0x40000000;
  *(_QWORD *)&lParam.lfOrientation = 0;
  *(_DWORD *)&lParam.lfItalic = a9;
  memset(&lParam.lfOutPrecision, 0, 68);
  SendMessageW(Window, 0x444u, 4u, (LPARAM)&lParam);
  if ( a14 )
  {
    while ( v52 )
    {
      if ( !(_QWORD)v51 )
        ATL::AtlThrowImpl(-2147467259);
      v28 = *(LPCWSTR **)(v51 + 16);
      v29 = *(_QWORD *)v51;
      *(_QWORD *)&v51 = v29;
      if ( v29 )
        *(_QWORD *)(v29 + 8) = 0;
      else
        v51 = 0u;
      ATL::CAtlList<CMapiPreviewer::AttachmentData *,ATL::CElementTraits<CMapiPreviewer::AttachmentData *>>::FreeNode(&v51);
      if ( Error >= 0 )
        Error = CMapiPreviewer::SetAttachmentDataOnRichEdit((HWND *)this, Window, v28, v52 != 0);
      if ( v28 )
      {
        CMapiPreviewer::AttachmentData::~AttachmentData((CMapiPreviewer::AttachmentData *)v28);
        operator delete(v28, (const struct std::nothrow_t *)0x10);
      }
    }
    goto LABEL_54;
  }
  wParam = 0x4B000000000LL;
  SendMessageW(Window, 0x461u, (WPARAM)&wParam, v43);
LABEL_55:
  h = SelectObject(DC, v27);
  if ( !h )
    Error = -2147467259;
LABEL_57:
  v30 = 0;
  v31 = lpString;
  if ( Error >= 0 )
  {
    memset(&tm, 0, sizeof(tm));
    if ( GetTextMetricsW(DC, &tm) )
      v30 = tm.tmHeight + tm.tmExternalLeading;
    else
      Error = ResultFromLastError();
    if ( a14 )
    {
      SystemMetrics = GetSystemMetrics(50);
      if ( SystemMetrics <= v30 )
      {
        if ( !SystemMetrics )
        {
          Error = -2147467259;
          wParam = 0;
          goto LABEL_85;
        }
      }
      else
      {
        v30 = SystemMetrics;
      }
    }
  }
  wParam = 0;
  v42 = 0;
  if ( Error < 0 || *((int *)v31 - 4) <= 0 )
    goto LABEL_86;
  psizl.cx = 0;
  Error = GetULONGFromResource(a11, (unsigned int *)&psizl);
  v41 = 0;
  v46 = 0;
  if ( Error >= 0 )
  {
    Error = GetULONGFromResource(a13, &v46);
    v41 = v46;
  }
  DeviceCaps = GetDeviceCaps(DC, 90);
  lParam.lfHeight = -(psizl.cx * DeviceCaps / 0x48u);
  *(_QWORD *)&lParam.lfWidth = 0;
  lParam.lfOrientation = 0;
  v34 = v41 != 0;
  v41 = -v41;
  lParam.lfWeight = v34 ? 700 : 400;
  memset(&lParam.lfItalic, 0, 72);
  if ( Error < 0 )
    goto LABEL_86;
  Error = StringCchCopyW(lParam.lfFaceName, 0x20u, v48);
  if ( Error < 0 )
    goto LABEL_86;
  v35 = CreateFontIndirectW(&lParam);
  wParam = (WPARAM)v35;
  if ( v35 )
  {
LABEL_73:
    if ( !SelectObject(DC, v35) )
    {
      Error = -2147467259;
      goto LABEL_86;
    }
    psizl = 0;
    if ( GetTextExtentPoint32W(DC, v31, *((_DWORD *)v31 - 4), &psizl) )
    {
      if ( psizl.cx > *((_DWORD *)this + 299) )
        *((_DWORD *)this + 299) = psizl.cx;
    }
    else
    {
      Error = ResultFromLastError();
    }
    if ( Error >= 0 )
    {
      memset(&tm, 0, sizeof(tm));
      if ( GetTextMetricsW(DC, &tm) )
      {
        v42 = tm.tmHeight + tm.tmExternalLeading;
        goto LABEL_86;
      }
      Error = ResultFromLastError();
    }
LABEL_85:
    v42 = 0;
    goto LABEL_86;
  }
  Error = ResultFromLastError();
  if ( Error >= 0 )
  {
    v35 = (void *)wParam;
    goto LABEL_73;
  }
LABEL_86:
  if ( h )
    SelectObject(DC, h);
  if ( Error < 0 )
  {
    if ( v27 )
      DeleteObject(v27);
    if ( wParam )
      DeleteObject((HGDIOBJ)wParam);
    if ( Window )
      DestroyWindow(Window);
  }
  else
  {
    *((_QWORD *)this + 7 * *((unsigned int *)this + 298) + 37) = Window;
    *((_QWORD *)this + 7 * *((unsigned int *)this + 298) + 38) = v27;
    v36 = 56LL * *((unsigned int *)this + 298);
    v37 = (int *)(*(_QWORD *)((char *)this + v36 + 312) - 24LL);
    if ( v31 - 12 != (const WCHAR *)v37 )
    {
      if ( v37[4] >= 0 && *((_QWORD *)v31 - 3) == *(_QWORD *)v37 )
      {
        v38 = ATL::CSimpleStringT<wchar_t,0>::CloneData();
        ATL::CStringData::Release((ATL::CStringData *)v37);
        *(_QWORD *)((char *)this + v36 + 312) = v38 + 24;
      }
      else
      {
        ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + v36 + 312, v31, *((unsigned int *)v31 - 4));
      }
    }
    *((_QWORD *)this + 7 * *((unsigned int *)this + 298) + 40) = wParam;
    *((_DWORD *)this + 14 * *((unsigned int *)this + 298) + 82) = v42;
    *((_DWORD *)this + 14 * *((unsigned int *)this + 298) + 83) = a12;
    *((_DWORD *)this + 14 * *((unsigned int *)this + 298) + 84) = 0;
    *((_DWORD *)this + 14 * *((unsigned int *)this + 298) + 85) = 0;
    *((_DWORD *)this + 14 * *((unsigned int *)this + 298) + 86) = v30;
    *((_DWORD *)this + 14 * (unsigned int)(*((_DWORD *)this + 298))++ + 87) = 0;
  }
  if ( DC )
    ReleaseDC(*((HWND *)this + 21), DC);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v48);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&lpString);
LABEL_104:
  ATL::CAtlList<CMapiPreviewer::AttachmentData *,ATL::CElementTraits<CMapiPreviewer::AttachmentData *>>::RemoveAll(&v51);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v43);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800239c8  push    rbp
0x1800239ca  push    rbx
0x1800239cb  push    rsi
0x1800239cc  push    rdi
0x1800239cd  push    r12
0x1800239cf  push    r13
0x1800239d1  push    r14
0x1800239d3  push    r15
0x1800239d5  lea     rbp, [rsp-0F8h]
0x1800239dd  sub     rsp, 1F8h
0x1800239e4  mov     rax, cs:__security_cookie
0x1800239eb  xor     rax, rsp
0x1800239ee  mov     [rbp+130h+var_50], rax
0x1800239f5  mov     r15, r9
0x1800239f8  mov     ebx, r8d
0x1800239fb  mov     r14d, edx
0x1800239fe  mov     rsi, rcx
0x180023a01  lea     rcx, [rsp+230h+var_1C8]
0x180023a06  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180023a0b  nop
0x180023a0c  xorps   xmm0, xmm0
0x180023a0f  movdqu  [rbp+130h+var_188], xmm0
0x180023a14  xor     r12d, r12d
0x180023a17  mov     ecx, r12d; this
0x180023a1a  mov     [rbp+130h+var_178], rcx
0x180023a1e  movdqu  [rbp+130h+var_170], xmm0
0x180023a23  mov     [rbp+130h+var_160], 0Ah
0x180023a2a  mov     r13d, [rbp+130h+arg_68]
0x180023a31  test    r13d, r13d
0x180023a34  jz      short loc_180023A49
0x180023a36  lea     rdx, [rbp+130h+var_188]
0x180023a3a  mov     rcx, rsi
0x180023a3d  call    ?GetAttachmentList@CMapiPreviewer@@AEAAJAEAV?$CAtlList@PEAUAttachmentData@CMapiPreviewer@@V?$CElementTraits@PEAUAttachmentData@CMapiPreviewer@@@ATL@@@ATL@@@Z; CMapiPreviewer::GetAttachmentList(ATL::CAtlList<CMapiPreviewer::AttachmentData *,ATL::CElementTraits<CMapiPreviewer::AttachmentData *>> &)
0x180023a42  mov     edi, eax
0x180023a44  jmp     loc_180023B62
0x180023a49  mov     edi, r12d
0x180023a4c  test    ebx, ebx
0x180023a4e  jz      short loc_180023AB9
0x180023a50  movzx   edx, bx
0x180023a53  lea     eax, [rdx-1Eh]
0x180023a56  cmp     eax, 1
0x180023a59  jbe     short loc_180023A96
0x180023a5b  cmp     edx, 40h ; '@'
0x180023a5e  jnz     loc_180023B6E
0x180023a64  mov     [rsp+230h+lpString], r12
0x180023a69  lea     r9, [rsp+230h+lpString]; struct _FILETIME *
0x180023a6e  mov     r8d, ebx; unsigned int
0x180023a71  mov     rdx, [rsi+0D8h]; struct IMessage *
0x180023a78  call    ?GetFileTimeProp@CMapiPreviewer@@AEAAJPEAUIMessage@@KPEAU_FILETIME@@@Z; CMapiPreviewer::GetFileTimeProp(IMessage *,ulong,_FILETIME *)
0x180023a7d  test    eax, eax
0x180023a7f  js      loc_180023B6A
0x180023a85  lea     r8, [rsp+230h+var_1C8]
0x180023a8a  mov     rdx, [rsp+230h+lpString]
0x180023a8f  call    ?ConvertFileTimeToString@CMapiPreviewer@@AEAAJU_FILETIME@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiPreviewer::ConvertFileTimeToString(_FILETIME,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180023a94  jmp     short loc_180023A42
0x180023a96  lea     r9, [rsp+230h+var_1C8]
0x180023a9b  mov     r8d, ebx
0x180023a9e  mov     rdx, [rsi+0D8h]
0x180023aa5  call    ?GetStringProp@CMapiPreviewer@@AEAAJPEAUIMessage@@KAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiPreviewer::GetStringProp(IMessage *,ulong,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180023aaa  lea     rcx, [rsp+230h+var_1C8]
0x180023aaf  call    ?Trim@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Trim(void)
0x180023ab4  jmp     loc_180023B62
0x180023ab9  lea     rax, ??_7CMapiNamedProp@@6B@; const CMapiNamedProp::`vftable'
0x180023ac0  mov     [rbp+130h+h], rax
0x180023ac4  mov     [rbp+130h+var_190], r12d
0x180023ac8  mov     r9d, [rbp+130h+arg_20]
0x180023acf  shr     r9d, 10h; unsigned int
0x180023ad3  lea     rax, [rbp+130h+var_190]
0x180023ad7  mov     qword ptr [rsp+230h+X], rax; unsigned int *
0x180023adc  mov     r8, r15; wchar_t *
0x180023adf  mov     rdx, [rsi+0D8h]; struct IMAPIProp *
0x180023ae6  call    ?GetNamedPropId@CMapiNamedProp@@AEAAJPEAUIMAPIProp@@PEB_WKPEAKH@Z; CMapiNamedProp::GetNamedPropId(IMAPIProp *,wchar_t const *,ulong,ulong *,int)
0x180023aeb  test    eax, eax
0x180023aed  js      short loc_180023B62
0x180023aef  movzx   ecx, word ptr [rbp+130h+arg_20]; this
0x180023af6  lea     eax, [rcx-1Eh]
0x180023af9  cmp     eax, 1
0x180023afc  jbe     short loc_180023B3B
0x180023afe  cmp     ecx, 40h ; '@'
0x180023b01  jnz     short loc_180023B62
0x180023b03  mov     [rsp+230h+lpString], r12
0x180023b08  mov     r8d, [rbp+130h+var_190]
0x180023b0c  shl     r8d, 10h
0x180023b10  or      r8d, ecx; unsigned int
0x180023b13  lea     r9, [rsp+230h+lpString]; struct _FILETIME *
0x180023b18  mov     rdx, [rsi+0D8h]; struct IMessage *
0x180023b1f  call    ?GetFileTimeProp@CMapiPreviewer@@AEAAJPEAUIMessage@@KPEAU_FILETIME@@@Z; CMapiPreviewer::GetFileTimeProp(IMessage *,ulong,_FILETIME *)
0x180023b24  test    eax, eax
0x180023b26  js      short loc_180023B62
0x180023b28  lea     r8, [rsp+230h+var_1C8]
0x180023b2d  mov     rdx, [rsp+230h+lpString]
0x180023b32  call    ?ConvertFileTimeToString@CMapiPreviewer@@AEAAJU_FILETIME@@AEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiPreviewer::ConvertFileTimeToString(_FILETIME,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180023b37  mov     edi, eax
0x180023b39  jmp     short loc_180023B62
0x180023b3b  mov     r8d, [rbp+130h+var_190]
0x180023b3f  shl     r8d, 10h
0x180023b43  or      r8d, ecx
0x180023b46  lea     r9, [rsp+230h+var_1C8]
0x180023b4b  mov     rdx, [rsi+0D8h]
0x180023b52  call    ?GetStringProp@CMapiPreviewer@@AEAAJPEAUIMessage@@KAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiPreviewer::GetStringProp(IMessage *,ulong,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180023b57  lea     rcx, [rsp+230h+var_1C8]
0x180023b5c  call    ?Trim@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Trim(void)
0x180023b61  nop
0x180023b62  test    edi, edi
0x180023b64  js      loc_1800242D3
0x180023b6a  mov     rcx, [rbp+130h+var_178]
0x180023b6e  mov     rax, [rsp+230h+var_1C8]
0x180023b73  cmp     [rax-10h], r12d
0x180023b77  jg      short loc_180023B8B
0x180023b79  test    rcx, rcx
0x180023b7c  jnz     short loc_180023B8B
0x180023b7e  cmp     [rbp+130h+arg_28], r12d
0x180023b85  jnz     loc_1800242D3
0x180023b8b  lea     rcx, [rsp+230h+lpString]
0x180023b90  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180023b95  nop
0x180023b96  test    r14d, r14d
0x180023b99  jz      short loc_180023BC3
0x180023b9b  mov     r8d, r14d
0x180023b9e  mov     rdx, cs:hInstance
0x180023ba5  lea     rcx, [rsp+230h+lpString]
0x180023baa  call    ?LoadStringW@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(HINSTANCE__ *,uint)
0x180023baf  test    eax, eax
0x180023bb1  jnz     short loc_180023BC3
0x180023bb3  mov     edi, 8000FFFFh
0x180023bb8  mov     r14, r12
0x180023bbb  mov     r15, r12
0x180023bbe  jmp     loc_180023C50
0x180023bc3  mov     r14, r12
0x180023bc6  test    edi, edi
0x180023bc8  js      short loc_180023C2D
0x180023bca  mov     rax, cs:off_180053498
0x180023bd1  mov     ecx, [rsi+4A8h]
0x180023bd7  mov     [rsp+230h+lpParam], r12; lpParam
0x180023bdc  mov     [rsp+230h+hInstance], rax; hInstance
0x180023be1  mov     [rsp+230h+hMenu], rcx; hMenu
0x180023be6  mov     rax, [rsi+0A8h]
0x180023bed  mov     [rsp+230h+hWndParent], rax; hWndParent
0x180023bf2  mov     [rsp+230h+nHeight], r12d; nHeight
0x180023bf7  mov     [rsp+230h+nWidth], r12d; nWidth
0x180023bfc  mov     [rsp+230h+Y], r12d; Y
0x180023c01  mov     [rsp+230h+X], r12d; X
0x180023c06  mov     r9d, 50200804h; dwStyle
0x180023c0c  xor     r8d, r8d; lpWindowName
0x180023c0f  lea     rdx, aRichedit50w; "RICHEDIT50W"
0x180023c16  xor     ecx, ecx; dwExStyle
0x180023c18  call    cs:__imp_CreateWindowExW
0x180023c1e  mov     r14, rax
0x180023c21  test    rax, rax
0x180023c24  jnz     short loc_180023C2D
0x180023c26  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180023c2b  mov     edi, eax
0x180023c2d  mov     r15, r12
0x180023c30  test    edi, edi
0x180023c32  js      short loc_180023C50
0x180023c34  mov     rcx, [rsi+0A8h]; hWnd
0x180023c3b  call    cs:__imp_GetDC
0x180023c41  mov     r15, rax
0x180023c44  test    rax, rax
0x180023c47  jnz     short loc_180023C50
0x180023c49  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180023c4e  mov     edi, eax
0x180023c50  lea     rcx, [rbp+130h+var_1A0]
0x180023c54  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180023c59  nop
0x180023c5a  test    edi, edi
0x180023c5c  js      short loc_180023C81
0x180023c5e  mov     r8d, 0FAh
0x180023c64  mov     rdx, cs:hInstance
0x180023c6b  lea     rcx, [rbp+130h+var_1A0]
0x180023c6f  call    ?LoadStringW@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(HINSTANCE__ *,uint)
0x180023c74  test    eax, eax
0x180023c76  jnz     short loc_180023C81
0x180023c78  mov     edi, 80004005h
0x180023c7d  xor     ebx, ebx
0x180023c7f  jmp     short loc_180023CC1
0x180023c81  mov     [rsp+230h+var_1D0], r12d
0x180023c86  test    edi, edi
0x180023c88  js      short loc_180023CA1
0x180023c8a  lea     rdx, [rsp+230h+var_1D0]; unsigned int *
0x180023c8f  mov     ecx, [rbp+130h+arg_38]; unsigned int
0x180023c95  call    ?GetULONGFromResource@@YAJKPEAK@Z; GetULONGFromResource(ulong,ulong *)
0x180023c9a  mov     edi, eax
0x180023c9c  mov     r12d, [rsp+230h+var_1D0]
0x180023ca1  xor     ebx, ebx
0x180023ca3  mov     [rsp+230h+var_1D0], ebx
0x180023ca7  test    edi, edi
0x180023ca9  js      short loc_180023CC1
0x180023cab  lea     rdx, [rsp+230h+var_1D0]; unsigned int *
0x180023cb0  mov     ecx, [rbp+130h+arg_48]; unsigned int
0x180023cb6  call    ?GetULONGFromResource@@YAJKPEAK@Z; GetULONGFromResource(ulong,ulong *)
0x180023cbb  mov     edi, eax
0x180023cbd  mov     ebx, [rsp+230h+var_1D0]
0x180023cc1  mov     edx, 5Ah ; 'Z'; index
0x180023cc6  mov     rcx, r15; hdc
0x180023cc9  call    cs:__imp_GetDeviceCaps
0x180023ccf  mov     ecx, eax
0x180023cd1  imul    ecx, r12d
0x180023cd5  mov     eax, 38E38E39h
0x180023cda  mul     ecx
0x180023cdc  shr     edx, 4
0x180023cdf  neg     edx
0x180023ce1  mov     [rbp+130h+lf.lfHeight], edx
0x180023ce7  mov     qword ptr [rbp+130h+lf.lfWidth], 0
0x180023cf2  mov     [rbp+130h+lf.lfOrientation], 0
0x180023cfc  neg     ebx
0x180023cfe  sbb     eax, eax
0x180023d00  and     eax, 12Ch
0x180023d05  add     eax, 190h
0x180023d0a  mov     [rbp+130h+lf.lfWeight], eax
0x180023d10  mov     dword ptr [rbp+130h+lf.lfItalic], 0
0x180023d1a  mov     word ptr [rbp+130h+lf.lfOutPrecision], 0
0x180023d23  mov     dword ptr [rbp+130h+lf.lfQuality], 0
0x180023d2d  xorps   xmm0, xmm0
0x180023d30  movups  xmmword ptr [rbp+130h+lf.lfFaceName+2], xmm0
0x180023d37  movups  xmmword ptr [rbp+130h+lf.lfFaceName+12h], xmm0
0x180023d3e  movups  xmmword ptr [rbp+130h+lf.lfFaceName+22h], xmm0
0x180023d45  movups  xmmword ptr [rbp+130h+lf.lfFaceName+30h], xmm0
0x180023d4c  test    edi, edi
0x180023d4e  js      short loc_180023D67
0x180023d50  mov     r8, [rbp+130h+var_1A0]; wchar_t *
0x180023d54  mov     edx, 20h ; ' '; unsigned __int64
0x180023d59  lea     rcx, [rbp+130h+lf.lfFaceName]; wchar_t *
0x180023d60  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180023d65  mov     edi, eax
0x180023d67  xor     r12d, r12d
0x180023d6a  test    edi, edi
0x180023d6c  js      loc_180023EE9
0x180023d72  lea     rcx, [rbp+130h+lf]; lplf
0x180023d79  call    cs:__imp_CreateFontIndirectW
0x180023d7f  mov     r12, rax
0x180023d82  test    rax, rax
0x180023d85  jnz     short loc_180023D8E
0x180023d87  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180023d8c  mov     edi, eax
0x180023d8e  test    edi, edi
0x180023d90  js      loc_180023EE9
0x180023d96  mov     r9d, 40000h; lParam
0x180023d9c  xor     r8d, r8d; wParam
0x180023d9f  mov     edx, 445h; Msg
0x180023da4  mov     rcx, r14; hWnd
0x180023da7  call    cs:__imp_SendMessageW
0x180023dad  mov     rax, rsi
0x180023db0  lea     rcx, [rsi+20h]
0x180023db4  neg     rax
0x180023db7  sbb     r9, r9
0x180023dba  and     r9, rcx; lParam
0x180023dbd  xor     r8d, r8d; wParam
0x180023dc0  mov     edx, 446h; Msg
0x180023dc5  mov     rcx, r14; hWnd
0x180023dc8  call    cs:__imp_SendMessageW
0x180023dce  xor     r9d, r9d; lParam
0x180023dd1  mov     r8, r12; wParam
0x180023dd4  lea     edx, [r9+30h]; Msg
0x180023dd8  mov     rcx, r14; hWnd
0x180023ddb  call    cs:__imp_SendMessageW
0x180023de1  mov     dword ptr [rbp+130h+lParam], 5Ch ; '\'
0x180023de8  mov     [rbp+130h+lParam+4], 40000000h
0x180023df0  xor     ecx, ecx
0x180023df2  mov     [rbp+130h+var_144], rcx
0x180023df6  mov     eax, [rbp+130h+arg_40]
0x180023dfc  mov     [rbp+130h+var_13C], eax
0x180023dff  mov     [rbp+130h+var_138], ecx
0x180023e02  xorps   xmm0, xmm0
0x180023e05  xor     eax, eax
0x180023e07  movups  xmmword ptr [rbp+130h+var_134], xmm0
0x180023e0b  movups  [rbp+130h+var_124], xmm0
0x180023e0f  movups  [rbp+130h+var_114], xmm0
0x180023e13  movups  [rbp+130h+var_114+0Eh], xmm0
0x180023e17  mov     [rbp+130h+var_F6], ax
0x180023e1b  lea     r9, [rbp+130h+lParam]; lParam
0x180023e1f  mov     edx, 444h; Msg
0x180023e24  lea     r8d, [rcx+4]; wParam
0x180023e28  mov     rcx, r14; hWnd
0x180023e2b  call    cs:__imp_SendMessageW
0x180023e31  test    r13d, r13d
0x180023e34  jz      loc_180023EBF
0x180023e3a  cmp     [rbp+130h+var_178], 0
0x180023e3f  jz      loc_180023EE9
0x180023e45  mov     rdx, qword ptr [rbp+130h+var_188]
0x180023e49  test    rdx, rdx
0x180023e4c  jz      short loc_180023EB4
0x180023e4e  mov     rbx, [rdx+10h]
0x180023e52  mov     rax, [rdx]
0x180023e55  mov     qword ptr [rbp+130h+var_188], rax
0x180023e59  test    rax, rax
0x180023e5c  jz      short loc_180023E68
0x180023e5e  mov     qword ptr [rax+8], 0
0x180023e66  jmp     short loc_180023E70
0x180023e68  mov     qword ptr [rbp+130h+var_188+8], 0
0x180023e70  lea     rcx, [rbp+130h+var_188]
0x180023e74  call    ?FreeNode@?$CAtlList@PEAUAttachmentData@CMapiPreviewer@@V?$CElementTraits@PEAUAttachmentData@CMapiPreviewer@@@ATL@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<CMapiPreviewer::AttachmentData *,ATL::CElementTraits<CMapiPreviewer::AttachmentData *>>::FreeNode(ATL::CAtlList<CMapiPreviewer::AttachmentData *,ATL::CElementTraits<CMapiPreviewer::AttachmentData *>>::CNode *)
0x180023e79  test    edi, edi
0x180023e7b  js      short loc_180023E98
0x180023e7d  xor     r9d, r9d
0x180023e80  cmp     [rbp+130h+var_178], r9
0x180023e84  setnz   r9b; int
0x180023e88  mov     r8, rbx; struct CMapiPreviewer::AttachmentData *
0x180023e8b  mov     rdx, r14; HWND
0x180023e8e  mov     rcx, rsi; this
  ... truncated ...
```
