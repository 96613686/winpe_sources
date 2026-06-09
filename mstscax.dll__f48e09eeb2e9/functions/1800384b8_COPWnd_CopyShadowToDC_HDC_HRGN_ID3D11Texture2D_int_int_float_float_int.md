# COPWnd::CopyShadowToDC(HDC__ *,HRGN__ *,ID3D11Texture2D *,int,int,float,float,int)

- ea: `0x1800384b8`
- end: `0x18003979d`
- name: `?CopyShadowToDC@COPWnd@@QEAAHPEAUHDC__@@PEAUHRGN__@@PEAUID3D11Texture2D@@HHMMH@Z`
- size: `4837`
- prototype: `__int64 __usercall@<rax>(COPWnd *__hidden this@<rcx>, HDC@<rdx>, HRGN hrgn@<r8>, struct ID3D11Texture2D *@<r9>, int, int, float, float, int)`
- caller_count: `3`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001b4ec`
- `0x18001c170`
- `0x180514ba0`

## callees

- `0x18001cdc0`
- `0x1800204e8`
- `0x18002a334`
- `0x180037fe8`
- `0x180038364`
- `0x1800384b8`
- `0x1800397a4`
- `0x180039820`
- `0x180039c98`
- `0x180039ce4`
- `0x18007fd60`
- `0x1800e9b1c`
- `0x1800f47c8`
- `0x1800f7748`
- `0x18010215c`
- `0x180512bd4`
- `0x1805149ac`
- `0x180688eae`
- `0x180688ede`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180038840`
- `KERNEL32!GetLastError` at `0x180038876`
- `KERNEL32!GetLastError` at `0x180038a05`
- `KERNEL32!GetLastError` at `0x180038ca2`
- `KERNEL32!GetLastError` at `0x180038d66`
- `KERNEL32!GetLastError` at `0x18003904c`
- `KERNEL32!GetLastError` at `0x18003916f`
- `KERNEL32!GetLastError` at `0x18003968d`
- `KERNEL32!GetLastError` at `0x1800396c7`
- `KERNEL32!GetLastError` at `0x180039735`
- `KERNEL32!GetLastError` at `0x180038840`
- `KERNEL32!GetLastError` at `0x180038876`
- `KERNEL32!GetLastError` at `0x180038a05`
- `KERNEL32!GetLastError` at `0x180038ca2`
- `KERNEL32!GetLastError` at `0x180038d66`
- `KERNEL32!GetLastError` at `0x18003904c`
- `KERNEL32!GetLastError` at `0x18003916f`
- `KERNEL32!GetLastError` at `0x18003968d`
- `KERNEL32!GetLastError` at `0x1800396c7`
- `KERNEL32!GetLastError` at `0x180039735`
- `GDI32!SetStretchBltMode` at `0x18003861b`
- `GDI32!SetStretchBltMode` at `0x18003861b`
- `GDI32!StretchBlt` at `0x180038c92`
- `GDI32!StretchBlt` at `0x18003967d`
- `GDI32!StretchBlt` at `0x180038c92`
- `GDI32!StretchBlt` at `0x18003967d`
- `GDI32!CreateRectRgn` at `0x180038a90`
- `GDI32!CreateRectRgn` at `0x1800393a0`
- `GDI32!CreateRectRgn` at `0x1800393b8`
- `GDI32!CreateRectRgn` at `0x180038a90`
- `GDI32!CreateRectRgn` at `0x1800393a0`
- `GDI32!CreateRectRgn` at `0x1800393b8`
- `GDI32!SetRectRgn` at `0x180038a4a`
- `GDI32!SetRectRgn` at `0x180039165`
- `GDI32!SetRectRgn` at `0x180038a4a`
- `GDI32!SetRectRgn` at `0x180039165`
- `GDI32!CombineRgn` at `0x1800393db`
- `GDI32!CombineRgn` at `0x1800393db`
- `GDI32!DeleteObject` at `0x180039437`
- `GDI32!DeleteObject` at `0x180039445`
- `GDI32!DeleteObject` at `0x180039568`
- `GDI32!DeleteObject` at `0x180039437`
- `GDI32!DeleteObject` at `0x180039445`
- `GDI32!DeleteObject` at `0x180039568`
- `GDI32!SelectClipRgn` at `0x180038654`
- `GDI32!SelectClipRgn` at `0x180038772`
- `GDI32!SelectClipRgn` at `0x180038aa8`
- `GDI32!SelectClipRgn` at `0x180038e40`
- `GDI32!SelectClipRgn` at `0x1800393ec`
- `GDI32!SelectClipRgn` at `0x18003942e`
- `GDI32!SelectClipRgn` at `0x180039552`
- `GDI32!SelectClipRgn` at `0x180038654`
- `GDI32!SelectClipRgn` at `0x180038772`
- `GDI32!SelectClipRgn` at `0x180038aa8`
- `GDI32!SelectClipRgn` at `0x180038e40`
- `GDI32!SelectClipRgn` at `0x1800393ec`
- `GDI32!SelectClipRgn` at `0x18003942e`
- `GDI32!SelectClipRgn` at `0x180039552`
- `GDI32!SetBrushOrgEx` at `0x18003862c`
- `GDI32!SetBrushOrgEx` at `0x18003862c`
- `GDI32!BitBlt` at `0x180038830`
- `GDI32!BitBlt` at `0x180038d1e`
- `GDI32!BitBlt` at `0x180038d56`
- `GDI32!BitBlt` at `0x180039423`
- `GDI32!BitBlt` at `0x180038830`
- `GDI32!BitBlt` at `0x180038d1e`
- `GDI32!BitBlt` at `0x180038d56`
- `GDI32!BitBlt` at `0x180039423`
- `GDI32!GetClipBox` at `0x180038661`
- `GDI32!GetClipBox` at `0x180038e4d`
- `GDI32!GetClipBox` at `0x18003955f`
- `GDI32!GetClipBox` at `0x180038661`
- `GDI32!GetClipBox` at `0x180038e4d`
- `GDI32!GetClipBox` at `0x18003955f`
- `GDI32!GetRgnBox` at `0x180038995`
- `GDI32!GetRgnBox` at `0x180038995`
- `GDI32!OffsetRgn` at `0x18003873f`
- `GDI32!OffsetRgn` at `0x180038767`
- `GDI32!OffsetRgn` at `0x18003873f`
- `GDI32!OffsetRgn` at `0x180038767`
- `USER32!SetTimer` at `0x180039792`
- `USER32!SetTimer` at `0x180039792`
- `USER32!IsRectEmpty` at `0x18003866b`
- `USER32!IsRectEmpty` at `0x18003866b`
- `USER32!ReleaseDC` at `0x180038789`
- `USER32!ReleaseDC` at `0x180038789`
- `USER32!GetDC` at `0x180038513`
- `USER32!GetDC` at `0x180038513`

## pseudocode

```c
__int64 __fastcall COPWnd::CopyShadowToDC(
        COPWnd *this,
        HDC a2,
        HRGN hrgn,
        struct ID3D11Texture2D *a4,
        int a5,
        int a6,
        float a7,
        float a8,
        int a9)
{
  HWND v11; // rcx
  HRGN v12; // r15
  HDC v13; // rsi
  HDC DC; // rdi
  __int64 v15; // rbx
  int v16; // esi
  int v17; // r15d
  int updated; // ebx
  HKEY v19; // rcx
  LONG bottom; // r12d
  LONG right; // r15d
  LONG x1; // r13d
  LONG y1; // ebx
  __int64 v24; // rcx
  HDC v25; // rsi
  __int64 v26; // rcx
  HRGN v27; // r15
  int v28; // edi
  int v29; // ebx
  unsigned int v30; // ebx
  DWORD v32; // edi
  unsigned int v33; // eax
  __int64 v34; // rdx
  int *v35; // rbx
  int v36; // r12d
  _DWORD *v37; // rbx
  int v38; // r13d
  int v39; // eax
  int v40; // ebx
  HKEY v41; // rax
  int v42; // r13d
  int RgnBox; // edx
  DWORD v44; // ebx
  HRGN v45; // rsi
  LONG left; // r15d
  LONG top; // r13d
  HRGN v48; // rax
  HRGN v49; // rbx
  int v50; // ebx
  int v51; // ecx
  int v52; // r12d
  HDC v53; // r12
  int (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v55; // rcx
  int v56; // r12d
  int v57; // r15d
  int v58; // esi
  int v59; // edi
  int v60; // ebx
  float v61; // xmm0_4
  DWORD v62; // edi
  unsigned int v63; // eax
  __int64 v64; // rdx
  unsigned int v65; // eax
  HKEY v66; // rbx
  int v67; // ecx
  int v68; // r12d
  int *v69; // rsi
  float v70; // xmm0_4
  float v71; // xmm0_4
  LONG v72; // ecx
  int v73; // ebx
  int v74; // edi
  unsigned int v75; // eax
  DWORD v76; // ebx
  unsigned int v77; // eax
  __int64 v78; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v80; // rdx
  HRGN v81; // rcx
  DWORD LastError; // ebx
  unsigned int v83; // eax
  unsigned int v84; // eax
  unsigned int v85; // eax
  HRGN RectRgn; // rbx
  HRGN v87; // rax
  HRGN v88; // rsi
  unsigned int v89; // eax
  unsigned int v90; // eax
  unsigned int v91; // eax
  int v92; // esi
  int v93; // edi
  int v94; // ebx
  float v95; // xmm0_4
  DWORD v96; // edi
  unsigned int v97; // eax
  __int64 v98; // rdx
  HWND v99; // rcx
  HDC hdcSrc; // [rsp+30h] [rbp-D8h]
  int hSrc; // [rsp+50h] [rbp-B8h]
  int hSrca; // [rsp+50h] [rbp-B8h]
  HDC hdcDest; // [rsp+68h] [rbp-A0h]
  __int64 v104; // [rsp+70h] [rbp-98h] BYREF
  int v105; // [rsp+78h] [rbp-90h] BYREF
  int v106; // [rsp+7Ch] [rbp-8Ch]
  int v107; // [rsp+80h] [rbp-88h] BYREF
  int v108; // [rsp+84h] [rbp-84h]
  int x2; // [rsp+88h] [rbp-80h]
  int v110; // [rsp+8Ch] [rbp-7Ch]
  int y2; // [rsp+90h] [rbp-78h]
  int v112; // [rsp+94h] [rbp-74h]
  HRGN hrgna[2]; // [rsp+98h] [rbp-70h] BYREF
  int v114; // [rsp+A8h] [rbp-60h] BYREF
  int v115; // [rsp+ACh] [rbp-5Ch]
  int v116; // [rsp+B0h] [rbp-58h]
  int v117; // [rsp+B4h] [rbp-54h]
  HDC DisconnectedBitmapDC; // [rsp+B8h] [rbp-50h]
  int v119; // [rsp+C0h] [rbp-48h]
  struct ID3D11Texture2D *v120; // [rsp+C8h] [rbp-40h]
  struct tagRECT rect; // [rsp+D0h] [rbp-38h] BYREF
  float y[6]; // [rsp+E0h] [rbp-28h] BYREF
  struct tagRECT rc; // [rsp+F8h] [rbp-10h] BYREF

  hrgna[0] = hrgn;
  v120 = a4;
  v11 = (HWND)*((_QWORD *)this + 6);
  v12 = hrgn;
  v13 = a2;
  DisconnectedBitmapDC = a2;
  v114 = 0;
  v105 = 0;
  DC = GetDC(v11);
  hdcDest = DC;
  (*(void (__fastcall **)(_QWORD, const char *, int *))(**((_QWORD **)this + 20) + 120LL))(
    *((_QWORD *)this + 20),
    "EnableSmartSizing",
    &v114);
  (*(void (__fastcall **)(_QWORD, const char *, int *))(**((_QWORD **)this + 20) + 96LL))(
    *((_QWORD *)this + 20),
    "ZoomLevel",
    &v105);
  if ( *((_DWORD *)this + 61) )
  {
    DisconnectedBitmapDC = COPWnd::GetDisconnectedBitmapDC(this);
    v13 = DisconnectedBitmapDC;
    if ( !DisconnectedBitmapDC && !a4 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_121;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v80 = 49;
      goto LABEL_135;
    }
    if ( v105 == 100 )
      CDesktopToWndTransform::SetSourceViewport(
        (CDesktopToWndTransform *)(*((_QWORD *)this + 28) + 56LL),
        0,
        0,
        *((_DWORD *)this + 50),
        *((_DWORD *)this + 51));
    goto LABEL_12;
  }
  if ( !v13 )
  {
    if ( !a4 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_121;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v80 = 46;
      goto LABEL_135;
    }
    goto LABEL_12;
  }
  if ( v114 && *((_DWORD *)this + 32) )
  {
    updated = COPWnd::UpdateSourceViewport(this, v13);
    goto LABEL_11;
  }
  if ( v105 == 100 )
  {
    v15 = *((_QWORD *)this + 28);
    v16 = *((_DWORD *)this + 51);
    v17 = *((_DWORD *)this + 50);
    v104 = v15 + 64;
    CTSCriticalSection::Lock((CTSCriticalSection *)(v15 + 64));
    if ( *(_DWORD *)(v15 + 80) || *(_DWORD *)(v15 + 88) != v17 || *(_DWORD *)(v15 + 84) || *(_DWORD *)(v15 + 92) != v16 )
    {
      *(_QWORD *)(v15 + 80) = 0;
      *(_DWORD *)(v15 + 88) = v17;
      *(_DWORD *)(v15 + 92) = v16;
      updated = 1;
    }
    else
    {
      updated = 0;
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v104);
    v13 = DisconnectedBitmapDC;
    v12 = hrgna[0];
LABEL_11:
    if ( !updated )
      goto LABEL_12;
    v81 = (HRGN)*((_QWORD *)this + 29);
    if ( !v81 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_121;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v80 = 48;
      goto LABEL_135;
    }
    if ( !SetRectRgn(v81, 0, 0, 32766, 32766) )
    {
      LastError = GetLastError();
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_143;
      }
      v83 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids,
        v83,
        LastError);
    }
    v19 = WPP_GLOBAL_Control;
LABEL_143:
    v12 = (HRGN)*((_QWORD *)this + 29);
    hrgna[0] = v12;
    goto LABEL_13;
  }
LABEL_12:
  v19 = WPP_GLOBAL_Control;
LABEL_13:
  if ( !v13 && !*((_QWORD *)this + 23) )
  {
    if ( v19 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v19[7] & 1) != 0 && *((_BYTE *)v19 + 25) )
      WPP_SF_(*((_QWORD *)v19 + 2), 50, WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids);
    goto LABEL_121;
  }
  SetStretchBltMode(DC, 4);
  SetBrushOrgEx(DC, 0, 0, 0);
  if ( v105 != 100
    || v114
    && !(unsigned int)CDesktopToWndTransform::IsIdentity(
                        *((CDesktopToWndTransform **)this + 28),
                        *((_DWORD *)this + 50),
                        *((_DWORD *)this + 51)) )
  {
    v35 = (int *)*((_QWORD *)this + 28);
    rc = 0;
    hrgna[0] = (HRGN)(v35 + 16);
    rect = 0;
    CTSCriticalSection::Lock((CTSCriticalSection *)(v35 + 16));
    v36 = v35[22];
    v106 = v35[20];
    v112 = v35[21];
    y2 = v35[23];
    v117 = v36;
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)hrgna);
    CDesktopToWndTransform::GetScaledTargetRect(*((_QWORD *)this + 28), &v107);
    v37 = (_DWORD *)*((_QWORD *)this + 28);
    hrgna[0] = (HRGN)(v37 + 16);
    CTSCriticalSection::Lock((CTSCriticalSection *)(v37 + 16));
    v38 = v37[26];
    v115 = v37[24];
    v39 = v37[25];
    v40 = v37[27];
    LODWORD(v104) = v40;
    v116 = v39;
    v119 = v38;
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)hrgna);
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control )
    {
      if ( ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v84 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ddddd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids,
          v84,
          v106,
          v112,
          v36,
          y2);
        v41 = WPP_GLOBAL_Control;
      }
      if ( v41 != (HKEY)&WPP_GLOBAL_Control )
      {
        if ( ((_BYTE)v41[7] & 1) != 0 && *((_BYTE *)v41 + 25) >= 5u )
        {
          v85 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids,
            v85,
            v107,
            v108,
            x2,
            v110);
          v41 = WPP_GLOBAL_Control;
        }
        if ( v41 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v41[7] & 1) != 0 && *((_BYTE *)v41 + 25) >= 5u )
        {
          v65 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids,
            v65,
            v115,
            v116,
            v38,
            v40);
          v41 = WPP_GLOBAL_Control;
        }
      }
    }
    if ( *((_QWORD *)this + 29) )
    {
      v42 = v107;
      if ( v107 || v108 )
      {
        RectRgn = CreateRectRgn(v106, v112, v36, y2);
        v87 = CreateRectRgn(v42, v108, x2, v110);
        v88 = v87;
        if ( RectRgn )
        {
          if ( v87 && (unsigned int)CombineRgn(RectRgn, RectRgn, v87, 4) > 1 )
          {
            SelectClipRgn(DC, RectRgn);
            BitBlt(DC, 0, 0, *((_DWORD *)this + 50), *((_DWORD *)this + 51), 0, 0, 0, 0x42u);
            SelectClipRgn(DC, 0);
          }
          DeleteObject(RectRgn);
        }
        if ( v88 )
          DeleteObject(v88);
        v13 = DisconnectedBitmapDC;
      }
      RgnBox = GetRgnBox(v12, &rc);
      *(struct tagRECT *)hrgna = rc;
      y[0] = (float)_mm_cvtsi128_si32((__m128i)rc);
      y[2] = (float)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)rc, 8));
      y[1] = (float)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)rc, 4));
      y[3] = (float)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)rc, 12));
      if ( RgnBox )
      {
        if ( v13 || *((_DWORD *)this + 31) )
          COPWnd::ScaleRect(this, (int *)hrgna, (int *)hrgna + 1, (int *)&hrgna[1], (int *)&hrgna[1] + 1);
        else
          DXScaleRect(&rc, *((_QWORD *)this + 28), hrgna, y);
      }
      else
      {
        v44 = GetLastError();
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v89 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(hdcSrc) = v44;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            (unsigned int)WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids,
            v89,
            (__int64)"GetRgnBox failed!",
            hdcSrc);
        }
        *(__m128i *)hrgna = _mm_load_si128((const __m128i *)&_xmm);
      }
      if ( SetRectRgn(*((HRGN *)this + 29), (int)hrgna[0], SHIDWORD(hrgna[0]), (int)hrgna[1], SHIDWORD(hrgna[1])) )
      {
        v45 = (HRGN)*((_QWORD *)this + 29);
        left = 0;
        top = 0;
        hrgna[0] = v45;
        if ( v105 == 100 )
        {
          SelectClipRgn(DC, v45);
          GetClipBox(DC, &rect);
          v66 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v90 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Ddddd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              62,
              WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids,
              v90,
              rect.left,
              rect.top,
              rect.right,
              rect.bottom);
            v66 = WPP_GLOBAL_Control;
          }
          if ( !v115 && !v116 && rect.right - rect.left == v119 && rect.bottom - rect.top == (_DWORD)v104 )
          {
            if ( *((_DWORD *)this + 69) )
            {
              v67 = v36 - v106;
              if ( v36 == v106
                || (v68 = y2 - v112, y2 == v112)
                || (v69 = (int *)((char *)this + 260),
                    v70 = ceilf_0((float)((float)(x2 - v107) * (float)*((int *)this + 65)) / (float)v67),
                    left = rect.left - (int)v70,
                    v71 = ceilf_0((float)((float)(v110 - v108) * (float)*((int *)this + 66)) / (float)v68),
                    top = rect.top - (int)v71,
                    left >= -1)
                && left <= 1 )
              {
                left = 0;
                v69 = (int *)((char *)this + 260);
              }
              v72 = 0;
              if ( (unsigned int)(top + 1) > 2 )
                v72 = top;
              top = v72;
              if ( v66 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v66[7] & 1) != 0 && *((_BYTE *)v66 + 25) >= 4u )
              {
                v73 = *((_DWORD *)this + 67);
                v74 = *v69;
                v75 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Ddddd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  63,
                  WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids,
                  v75,
                  v74,
                  v73,
                  left,
                  top);
                DC = hdcDest;
              }
              v36 = v117;
            }
            else
            {
              left = rect.left;
              top = rect.top;
              if ( v66 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v66[7] & 1) != 0 && *((_BYTE *)v66 + 25) >= 4u )
              {
                v91 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DLD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  64,
                  WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids,
                  v91,
                  left,
                  top);
              }
            }
          }
        }
        else
        {
          v48 = CreateRectRgn(0, 0, 32766 * v105 / 0x64u, 32766 * v105 / 0x64u);
          v49 = v48;
          if ( v48 )
          {
            SelectClipRgn(DC, v48);
            GetClipBox(DC, &rect);
            DeleteObject(v49);
            if ( rect.right - rect.left == v119 - v115 && rect.bottom - rect.top == (_DWORD)v104 - v116 )
            {
              left = rect.left;
              top = rect.top;
            }
          }
          SelectClipRgn(DC, v45);
        }
        v50 = v112;
        v51 = y2 - v112;
        v52 = v36 - v106;
        if ( *((_DWORD *)this + 64) )
        {
          v51 = v52;
          v52 = y2 - v112;
        }
        v117 = v52;
        if ( *((_DWORD *)this + 31) )
        {
          BitBlt(DC, v107 + left, v108 + top, x2 - v107, v110 - v108, 0, v106, v112, 0x42u);
LABEL_64:
          v25 = hdcDest;
          goto LABEL_24;
        }
        v53 = DisconnectedBitmapDC;
        if ( !DisconnectedBitmapDC )
        {
          v54 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 23);
          v104 = 0;
          if ( (**v54)(v54, &IID_IRDPSurfacePresenterTransforms, &v104) < 0 )
          {
            v30 = 0;
            v96 = GetLastError();
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
LABEL_130:
              v78 = v104;
              if ( v104 )
              {
                v104 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
              }
              goto LABEL_43;
            }
            v97 = RdpWppGetCurrentThreadActivityIdPrefix();
            v98 = 68;
          }
          else
          {
            if ( (*(int (__fastcall **)(__int64, struct ID3D11Texture2D *, _QWORD))(*(_QWORD *)v104 + 24LL))(
                   v104,
                   v120,
                   *((unsigned int *)this + 77)) >= 0 )
            {
              v55 = v104;
              if ( v104 )
              {
                v104 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
              }
              goto LABEL_64;
            }
            v30 = 0;
            v96 = GetLastError();
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
              || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_130;
            }
            v97 = RdpWppGetCurrentThreadActivityIdPrefix();
            v98 = 69;
          }
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v98, WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids, v97, v96);
          goto LABEL_130;
        }
        v92 = (int)floorf_0((float)v51 / a8);
        v93 = (int)floorf_0((float)v117 / a7);
        v94 = a6 + (int)ceilf_0((float)((float)v50 - (float)a6) / a8);
        v95 = ceilf_0((float)((float)v106 - (float)a5) / a7);
        hSrca = v92;
        v25 = hdcDest;
        v30 = StretchBlt(
                hdcDest,
                v107 + left,
                v108 + top,
                x2 - v107,
                v110 - v108,
                v53,
                a5 + (int)v95,
                v94,
                v93,
                hSrca,
                0xCC0020u);
        if ( v30 )
          goto LABEL_24;
        v62 = GetLastError();
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_30;
        }
        v63 = RdpWppGetCurrentThreadActivityIdPrefix();
        v64 = 67;
LABEL_157:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v64, WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids, v63, v62);
        goto LABEL_30;
      }
      v76 = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v77 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(hdcSrc) = v76;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          (unsigned int)WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids,
          v77,
          (__int64)"SetRectRgn failed!",
          hdcSrc);
      }
LABEL_121:
      v30 = 0;
      v25 = DC;
      goto LABEL_30;
    }
    if ( v41 == (HKEY)&WPP_GLOBAL_Control || ((_BYTE)v41[7] & 1) == 0 || *((_BYTE *)v41 + 25) < 2u )
      goto LABEL_121;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v80 = 58;
LABEL_135:
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v80,
      WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids,
      CurrentThreadActivityIdPrefix);
    goto LABEL_121;
  }
  rect = 0;
  SelectClipRgn(DC, v12);
  GetClipBox(DC, &rect);
  if ( IsRectEmpty(&rect) )
  {
    right = *((_DWORD *)this + 50);
    x1 = 0;
    bottom = *((_DWORD *)this + 51);
    y1 = 0;
    *(_QWORD *)&rect.left = 0;
    rect.right = right;
    rect.bottom = bottom;
  }
  else
  {
    bottom = rect.bottom;
    right = rect.right;
    x1 = rect.left;
    y1 = rect.top;
  }
  if ( !a9 )
  {
    if ( *((_DWORD *)this + 31) )
    {
      v30 = BitBlt(DC, x1, y1, right - x1, bottom - y1, 0, x1, y1, 0x42u);
      if ( v30 )
        goto LABEL_23;
      v32 = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v33 = RdpWppGetCurrentThreadActivityIdPrefix();
        v34 = v30 + 51;
        goto LABEL_71;
      }
LABEL_43:
      v25 = hdcDest;
      goto LABEL_30;
    }
    if ( !v13 )
    {
      v24 = *((_QWORD *)this + 23);
      LODWORD(v104) = 0;
      if ( (*(int (__fastcall **)(__int64, struct ID3D11Texture2D *, struct tagRECT *, __int64, int, int, __int64 *))(*(_QWORD *)v24 + 64LL))(
             v24,
             v120,
             &rect,
             1,
             a5,
             a6,
             &v104) >= 0 )
        goto LABEL_23;
      v30 = 0;
      v32 = GetLastError();
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v33 = RdpWppGetCurrentThreadActivityIdPrefix();
        v34 = 54;
LABEL_71:
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids, v33, v32);
        goto LABEL_43;
      }
      goto LABEL_43;
    }
    if ( a7 != 1.0 || a8 != 1.0 )
    {
      v56 = bottom - y1;
      v57 = right - x1;
      v58 = (int)floorf_0((float)v56 / a8);
      v59 = (int)floorf_0((float)v57 / a7);
      v60 = a6 + (int)ceilf_0((float)((float)y1 - (float)a6) / a8);
      v61 = ceilf_0((float)((float)x1 - (float)a5) / a7);
      hSrc = v58;
      v25 = hdcDest;
      v30 = StretchBlt(hdcDest, x1, rect.top, v57, v56, DisconnectedBitmapDC, a5 + (int)v61, v60, v59, hSrc, 0xCC0020u);
      if ( v30 )
        goto LABEL_24;
      v62 = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v63 = RdpWppGetCurrentThreadActivityIdPrefix();
      v64 = v30 + 53;
      goto LABEL_157;
    }
    v30 = BitBlt(DC, x1, y1, right - x1, bottom - y1, v13, x1, y1, 0xCC0020u);
    if ( !v30 )
    {
      v32 = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      v34 = v30 + 52;
      goto LABEL_71;
    }
  }
LABEL_23:
  v25 = DC;
LABEL_24:
  if ( *((_QWORD *)this + 35) )
  {
    v26 = *((_QWORD *)this + 22);
    *(_OWORD *)y = 0;
    if ( v26 && (*(int (__fastcall **)(__int64, float *))(*(_QWORD *)v26 + 136LL))(v26, y) < 0 )
      *(_OWORD *)y = 0;
    v27 = hrgna[0];
    v28 = LODWORD(y[0]);
    v29 = LODWORD(y[1]);
    OffsetRgn(hrgna[0], SLODWORD(y[0]), SLODWORD(y[1]));
    (*(void (__fastcall **)(_QWORD, HRGN))(**((_QWORD **)this + 35) + 16LL))(*((_QWORD *)this + 35), v27);
    OffsetRgn(v27, -v28, -v29);
  }
  SelectClipRgn(v25, 0);
  v30 = 1;
LABEL_30:
  if ( v25 )
    ReleaseDC(*((HWND *)this + 6), v25);
  if ( *((_DWORD *)this + 60) )
  {
    v99 = (HWND)*((_QWORD *)this + 6);
    *((_DWORD *)this + 60) = 0;
    SetTimer(v99, 2u, 0xC8u, 0);
  }
  return v30;
}

```

## disassembly

```asm
0x1800384b8  mov     rax, rsp
0x1800384bb  push    rbp
0x1800384bc  push    rbx
0x1800384bd  push    rsi
0x1800384be  push    rdi
0x1800384bf  push    r12
0x1800384c1  push    r13
0x1800384c3  push    r14
0x1800384c5  push    r15
0x1800384c7  lea     rbp, [rax-78h]
0x1800384cb  sub     rsp, 138h
0x1800384d2  movaps  xmmword ptr [rax-58h], xmm6
0x1800384d6  movaps  xmmword ptr [rax-68h], xmm7
0x1800384da  mov     rax, cs:__security_cookie
0x1800384e1  xor     rax, rsp
0x1800384e4  mov     [rbp+70h+var_70], rax
0x1800384e8  mov     rbx, r9
0x1800384eb  mov     [rbp+70h+hrgn], r8
0x1800384ef  mov     r14, rcx
0x1800384f2  mov     [rbp+70h+var_B0], rbx
0x1800384f6  mov     rcx, [rcx+30h]; hWnd
0x1800384fa  mov     r15, r8
0x1800384fd  mov     rsi, rdx
0x180038500  mov     [rbp+70h+var_C0], rdx
0x180038504  mov     [rbp+70h+var_D0], 0
0x18003850b  mov     [rsp+170h+var_100], 0
0x180038513  call    cs:__imp_GetDC
0x180038519  mov     rcx, [r14+0A0h]
0x180038520  lea     r8, [rbp+70h+var_D0]
0x180038524  mov     rdi, rax
0x180038527  mov     [rsp+170h+hdcDest], rax
0x18003852c  mov     rdx, [rcx]
0x18003852f  mov     rax, [rdx+78h]
0x180038533  lea     rdx, aEnablesmartsiz; "EnableSmartSizing"
0x18003853a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003853f  mov     rcx, [r14+0A0h]
0x180038546  lea     r8, [rsp+170h+var_100]
0x18003854b  mov     rdx, [rcx]
0x18003854e  mov     rax, [rdx+60h]
0x180038552  lea     rdx, aZoomlevel_0; "ZoomLevel"
0x180038559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003855e  xor     eax, eax
0x180038560  lea     r12, WPP_GLOBAL_Control
0x180038567  lea     r13, WPP_fc291b1b0d8d3d5f98a46bce47f6e9ec_Traceguids
0x18003856e  cmp     [r14+0F4h], eax
0x180038575  jnz     loc_1800391FD
0x18003857b  test    rsi, rsi
0x18003857e  jz      loc_180038FF7
0x180038584  cmp     [rbp+70h+var_D0], eax
0x180038587  jnz     loc_180038B77
0x18003858d  cmp     [rsp+170h+var_100], 64h ; 'd'
0x180038592  jnz     short loc_1800385FA
0x180038594  mov     rbx, [r14+0E0h]
0x18003859b  mov     esi, [r14+0CCh]
0x1800385a2  mov     r15d, [r14+0C8h]
0x1800385a9  lea     rcx, [rbx+40h]; this
0x1800385ad  mov     [rsp+170h+var_108], rcx
0x1800385b2  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800385b7  xor     eax, eax
0x1800385b9  cmp     [rbx+50h], eax
0x1800385bc  jnz     loc_180038B62
0x1800385c2  cmp     [rbx+58h], r15d
0x1800385c6  jnz     loc_180038B62
0x1800385cc  cmp     [rbx+54h], eax
0x1800385cf  jnz     loc_180038B62
0x1800385d5  cmp     [rbx+5Ch], esi
0x1800385d8  jnz     loc_180038B62
0x1800385de  mov     ebx, eax
0x1800385e0  lea     rcx, [rsp+170h+var_108]; this
0x1800385e5  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800385ea  mov     rsi, [rbp+70h+var_C0]
0x1800385ee  mov     r15, [rbp+70h+hrgn]
0x1800385f2  test    ebx, ebx
0x1800385f4  jnz     loc_180039149
0x1800385fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180038601  test    rsi, rsi
0x180038604  jnz     short loc_180038613
0x180038606  cmp     [r14+0B8h], rsi
0x18003860d  jz      loc_180038FD3
0x180038613  mov     edx, 4; mode
0x180038618  mov     rcx, rdi; hdc
0x18003861b  call    cs:__imp_SetStretchBltMode
0x180038621  xor     r9d, r9d; lppt
0x180038624  xor     r8d, r8d; y
0x180038627  xor     edx, edx; x
0x180038629  mov     rcx, rdi; hdc
0x18003862c  call    cs:__imp_SetBrushOrgEx
0x180038632  cmp     [rsp+170h+var_100], 64h ; 'd'
0x180038637  jnz     loc_1800388C1
0x18003863d  cmp     [rbp+70h+var_D0], 0
0x180038641  jnz     loc_18003889F
0x180038647  xorps   xmm0, xmm0
0x18003864a  mov     rdx, r15; hrgn
0x18003864d  mov     rcx, rdi; hdc
0x180038650  movups  xmmword ptr [rbp+70h+rect.left], xmm0
0x180038654  call    cs:__imp_SelectClipRgn
0x18003865a  lea     rdx, [rbp+70h+rect]; lprect
0x18003865e  mov     rcx, rdi; hdc
0x180038661  call    cs:__imp_GetClipBox
0x180038667  lea     rcx, [rbp+70h+rect]; lprc
0x18003866b  call    cs:__imp_IsRectEmpty
0x180038671  test    eax, eax
0x180038673  jnz     loc_180039276
0x180038679  mov     r12d, [rbp+70h+rect.bottom]
0x18003867d  mov     r15d, [rbp+70h+rect.right]
0x180038681  mov     r13d, [rbp+70h+rect.left]
0x180038685  mov     ebx, [rbp+70h+rect.top]
0x180038688  xor     eax, eax
0x18003868a  cmp     [rbp+70h+arg_40], eax
0x180038690  jnz     short loc_1800386F2
0x180038692  cmp     [r14+7Ch], eax
0x180038696  jnz     loc_180038D29
0x18003869c  test    rsi, rsi
0x18003869f  jnz     loc_1800387CD
0x1800386a5  mov     r8d, [rbp+70h+arg_28]
0x1800386ac  lea     rdx, [rsp+170h+var_108]
0x1800386b1  mov     rcx, [r14+0B8h]
0x1800386b8  lea     r9d, [rsi+1]
0x1800386bc  mov     qword ptr [rsp+170h+x1], rdx
0x1800386c1  mov     rdx, [rbp+70h+var_B0]
0x1800386c5  mov     dword ptr [rsp+170h+hdcSrc], r8d
0x1800386ca  mov     r8d, [rbp+70h+arg_20]
0x1800386d1  mov     dword ptr [rsp+170h+var_108], eax
0x1800386d5  mov     rax, [rcx]
0x1800386d8  mov     [rsp+170h+cy], r8d
0x1800386dd  lea     r8, [rbp+70h+rect]
0x1800386e1  mov     rax, [rax+40h]
0x1800386e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386ea  test    eax, eax
0x1800386ec  js      loc_180038874
0x1800386f2  mov     rsi, rdi
0x1800386f5  cmp     qword ptr [r14+118h], 0
0x1800386fd  jz      short loc_18003876D
0x1800386ff  mov     rcx, [r14+0B0h]
0x180038706  xorps   xmm0, xmm0
0x180038709  movups  xmmword ptr [rbp+70h+y], xmm0
0x18003870d  test    rcx, rcx
0x180038710  jz      short loc_18003872D
0x180038712  mov     rax, [rcx]
0x180038715  lea     rdx, [rbp+70h+y]
0x180038719  mov     rax, [rax+88h]
0x180038720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038725  test    eax, eax
0x180038727  js      loc_18003976A
0x18003872d  mov     r15, [rbp+70h+hrgn]
0x180038731  mov     edi, [rbp+70h+y]
0x180038734  mov     rcx, r15; hrgn
0x180038737  mov     ebx, [rbp+70h+y+4]
0x18003873a  mov     edx, edi; x
0x18003873c  mov     r8d, ebx; y
0x18003873f  call    cs:__imp_OffsetRgn
0x180038745  mov     rcx, [r14+118h]
0x18003874c  mov     rdx, r15
0x18003874f  mov     rax, [rcx]
0x180038752  mov     rax, [rax+10h]
0x180038756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003875b  neg     ebx
0x18003875d  neg     edi
0x18003875f  mov     r8d, ebx; y
0x180038762  mov     edx, edi; x
0x180038764  mov     rcx, r15; hrgn
0x180038767  call    cs:__imp_OffsetRgn
0x18003876d  xor     edx, edx; hrgn
0x18003876f  mov     rcx, rsi; hdc
0x180038772  call    cs:__imp_SelectClipRgn
0x180038778  mov     ebx, 1
0x18003877d  test    rsi, rsi
0x180038780  jz      short loc_18003878F
0x180038782  mov     rcx, [r14+30h]; hWnd
0x180038786  mov     rdx, rsi; hDC
0x180038789  call    cs:__imp_ReleaseDC
0x18003878f  cmp     dword ptr [r14+0F0h], 0
0x180038797  jnz     loc_180039776
0x18003879d  mov     eax, ebx
0x18003879f  mov     rcx, [rbp+70h+var_70]
0x1800387a3  xor     rcx, rsp; StackCookie
0x1800387a6  call    __security_check_cookie
0x1800387ab  lea     r11, [rsp+170h+var_38]
0x1800387b3  movaps  xmm6, xmmword ptr [r11-18h]
0x1800387b8  movaps  xmm7, xmmword ptr [r11-28h]
0x1800387bd  mov     rsp, r11
0x1800387c0  pop     r15
0x1800387c2  pop     r14
0x1800387c4  pop     r13
0x1800387c6  pop     r12
0x1800387c8  pop     rdi
0x1800387c9  pop     rsi
0x1800387ca  pop     rbx
0x1800387cb  pop     rbp
0x1800387cc  retn
0x1800387cd  movss   xmm7, [rbp+70h+arg_30]
0x1800387d5  movss   xmm0, cs:__real@3f800000
0x1800387dd  ucomiss xmm7, xmm0
0x1800387e0  movss   xmm6, [rbp+70h+arg_38]
0x1800387e8  jp      loc_180038BD7
0x1800387ee  jnz     loc_180038BD7
0x1800387f4  ucomiss xmm6, xmm0
0x1800387f7  jp      loc_180038BD7
0x1800387fd  jnz     loc_180038BD7
0x180038803  mov     [rsp+170h+rop], 0CC0020h; rop
0x18003880b  sub     r15d, r13d
0x18003880e  mov     [rsp+170h+y1], ebx; y1
0x180038812  sub     r12d, ebx
0x180038815  mov     [rsp+170h+x1], r13d; x1
0x18003881a  mov     r9d, r15d; cx
0x18003881d  mov     [rsp+170h+hdcSrc], rsi; hdcSrc
0x180038822  mov     r8d, ebx; y
0x180038825  mov     edx, r13d; x
0x180038828  mov     [rsp+170h+cy], r12d; cy
0x18003882d  mov     rcx, rdi; hdc
0x180038830  call    cs:__imp_BitBlt
0x180038836  mov     ebx, eax
0x180038838  test    eax, eax
0x18003883a  jnz     loc_1800386F2
0x180038840  call    cs:__imp_GetLastError
0x180038846  mov     edi, eax
0x180038848  mov     rcx, cs:WPP_GLOBAL_Control
0x18003884f  lea     rax, WPP_GLOBAL_Control
0x180038856  cmp     rcx, rax
0x180038859  jz      short loc_180038895
0x18003885b  test    byte ptr [rcx+1Ch], 8
0x18003885f  jz      short loc_180038895
0x180038861  cmp     byte ptr [rcx+19h], 2
0x180038865  jb      short loc_180038895
0x180038867  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003886c  lea     edx, [rbx+34h]
0x18003886f  jmp     loc_180038BB4
0x180038874  xor     ebx, ebx
0x180038876  call    cs:__imp_GetLastError
0x18003887c  mov     edi, eax
0x18003887e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038885  lea     rax, WPP_GLOBAL_Control
0x18003888c  cmp     rcx, rax
0x18003888f  jnz     loc_180038B96
0x180038895  mov     rsi, [rsp+170h+hdcDest]
0x18003889a  jmp     loc_18003877D
0x18003889f  mov     r8d, [r14+0CCh]; unsigned int
0x1800388a6  mov     edx, [r14+0C8h]; unsigned int
0x1800388ad  mov     rcx, [r14+0E0h]; this
0x1800388b4  call    ?IsIdentity@CDesktopToWndTransform@@QEBAHII@Z; CDesktopToWndTransform::IsIdentity(uint,uint)
0x1800388b9  test    eax, eax
0x1800388bb  jnz     loc_180038647
0x1800388c1  mov     rbx, [r14+0E0h]
0x1800388c8  xorps   xmm0, xmm0
0x1800388cb  xorps   xmm1, xmm1
0x1800388ce  movups  xmmword ptr [rbp+70h+rc.left], xmm0
0x1800388d2  lea     rcx, [rbx+40h]; this
0x1800388d6  mov     [rbp+70h+hrgn], rcx
0x1800388da  movups  xmmword ptr [rbp+70h+rect.left], xmm1
0x1800388de  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800388e3  mov     eax, [rbx+50h]
0x1800388e6  lea     rcx, [rbp+70h+hrgn]; this
0x1800388ea  mov     r12d, [rbx+58h]
0x1800388ee  mov     [rsp+170h+var_FC], eax
0x1800388f2  mov     eax, [rbx+54h]
0x1800388f5  mov     [rbp+70h+var_E4], eax
0x1800388f8  mov     eax, [rbx+5Ch]
0x1800388fb  mov     [rbp+70h+y2], eax
0x1800388fe  mov     [rbp+70h+var_C4], r12d
0x180038902  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180038907  mov     rcx, [r14+0E0h]
0x18003890e  lea     rdx, [rsp+170h+var_F8]
0x180038913  call    ?GetScaledTargetRect@CDesktopToWndTransform@@QEBA?BUtagTS_GFX_RECT@@XZ; CDesktopToWndTransform::GetScaledTargetRect(void)
0x180038918  mov     rbx, [r14+0E0h]
0x18003891f  lea     rcx, [rbx+40h]; this
0x180038923  mov     [rbp+70h+hrgn], rcx
0x180038927  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18003892c  mov     eax, [rbx+60h]
0x18003892f  lea     rcx, [rbp+70h+hrgn]; this
0x180038933  mov     r13d, [rbx+68h]
0x180038937  mov     [rbp+70h+var_CC], eax
0x18003893a  mov     eax, [rbx+64h]
0x18003893d  mov     ebx, [rbx+6Ch]
0x180038940  mov     dword ptr [rsp+170h+var_108], ebx
0x180038944  mov     [rbp+70h+var_C8], eax
0x180038947  mov     [rbp+70h+var_B8], r13d
0x18003894b  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180038950  mov     rax, cs:WPP_GLOBAL_Control
0x180038957  lea     rcx, WPP_GLOBAL_Control
0x18003895e  cmp     rax, rcx
0x180038961  jnz     loc_180038DA6
0x180038967  cmp     qword ptr [r14+0E8h], 0
0x18003896f  jz      loc_180039370
0x180038975  mov     r13d, [rsp+170h+var_F8]
0x18003897a  test    r13d, r13d
0x18003897d  jnz     loc_180039392
0x180038983  cmp     [rsp+170h+var_F4], r13d
0x180038988  jnz     loc_180039392
0x18003898e  lea     rdx, [rbp+70h+rc]; lprc
0x180038992  mov     rcx, r15; hrgn
0x180038995  call    cs:__imp_GetRgnBox
0x18003899b  movaps  xmm2, xmmword ptr [rbp+70h+rc.left]
0x18003899f  mov     edx, eax
0x1800389a1  movd    ecx, xmm2
0x1800389a5  movdqa  xmm1, xmm2
0x1800389a9  psrldq  xmm1, 8
0x1800389ae  movdqa  xmmword ptr [rbp+70h+hrgn], xmm2
0x1800389b3  movd    xmm0, ecx
0x1800389b7  movd    ecx, xmm1
0x1800389bb  movdqa  xmm1, xmm2
  ... truncated ...
```
