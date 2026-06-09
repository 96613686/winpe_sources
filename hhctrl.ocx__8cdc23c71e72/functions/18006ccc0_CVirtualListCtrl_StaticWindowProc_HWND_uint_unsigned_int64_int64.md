# CVirtualListCtrl::StaticWindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18006ccc0`
- end: `0x18006d321`
- name: `?StaticWindowProc@CVirtualListCtrl@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `1633`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180002968`
- `0x18001d4f8`
- `0x18001d570`
- `0x18006c678`
- `0x18006c85c`
- `0x18006c95c`
- `0x18006caf0`
- `0x18006cb4c`
- `0x18006cc40`
- `0x18006ccc0`
- `0x18006d850`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `USER32!SystemParametersInfoA` at `0x18006d0db`
- `USER32!SystemParametersInfoA` at `0x18006d0db`
- `USER32!FillRect` at `0x18006cf12`
- `USER32!FillRect` at `0x18006cf12`
- `USER32!BeginPaint` at `0x18006cf3a`
- `USER32!BeginPaint` at `0x18006cf3a`
- `USER32!EndPaint` at `0x18006cfcc`
- `USER32!EndPaint` at `0x18006cfcc`
- `USER32!SetScrollInfo` at `0x18006d04f`
- `USER32!SetScrollInfo` at `0x18006d04f`
- `USER32!GetScrollInfo` at `0x18006d21e`
- `USER32!GetScrollInfo` at `0x18006d21e`
- `USER32!ReleaseDC` at `0x18006d067`
- `USER32!ReleaseDC` at `0x18006d067`
- `USER32!GetDC` at `0x18006cda6`
- `USER32!GetDC` at `0x18006cda6`
- `USER32!DefWindowProcA` at `0x18006cf28`
- `USER32!DefWindowProcA` at `0x18006cf28`
- `USER32!SetFocus` at `0x18006d116`
- `USER32!SetFocus` at `0x18006d129`
- `USER32!SetFocus` at `0x18006d13c`
- `USER32!SetFocus` at `0x18006d171`
- `USER32!SetFocus` at `0x18006d116`
- `USER32!SetFocus` at `0x18006d129`
- `USER32!SetFocus` at `0x18006d13c`
- `USER32!SetFocus` at `0x18006d171`
- `USER32!GetClientRect` at `0x18006cd9d`
- `USER32!GetClientRect` at `0x18006ce1a`
- `USER32!GetClientRect` at `0x18006cd9d`
- `USER32!GetClientRect` at `0x18006ce1a`
- `USER32!SetWindowLongPtrA` at `0x18006d07d`
- `USER32!SetWindowLongPtrA` at `0x18006d07d`
- `USER32!GetWindowLongPtrA` at `0x18006cd1b`
- `USER32!GetWindowLongPtrA` at `0x18006cd1b`
- `GDI32!RestoreDC` at `0x18006cfbf`
- `GDI32!RestoreDC` at `0x18006d05b`
- `GDI32!RestoreDC` at `0x18006cfbf`
- `GDI32!RestoreDC` at `0x18006d05b`
- `GDI32!SaveDC` at `0x18006cdb2`
- `GDI32!SaveDC` at `0x18006cf46`
- `GDI32!SaveDC` at `0x18006cdb2`
- `GDI32!SaveDC` at `0x18006cf46`
- `GDI32!SelectObject` at `0x18006cdc4`
- `GDI32!SelectObject` at `0x18006cf58`
- `GDI32!SelectObject` at `0x18006cdc4`
- `GDI32!SelectObject` at `0x18006cf58`
- `GDI32!BitBlt` at `0x18006cea9`
- `GDI32!BitBlt` at `0x18006cea9`
- `GDI32!SelectPalette` at `0x18006ce43`
- `GDI32!SelectPalette` at `0x18006ced3`
- `GDI32!SelectPalette` at `0x18006ce43`
- `GDI32!SelectPalette` at `0x18006ced3`
- `GDI32!RealizePalette` at `0x18006ce4f`
- `GDI32!RealizePalette` at `0x18006ce4f`
- `GDI32!GetClipBox` at `0x18006cf01`
- `GDI32!GetClipBox` at `0x18006cf01`
- `GDI32!GetTextExtentPointA` at `0x18006cddf`
- `GDI32!GetTextExtentPointA` at `0x18006cddf`

## pseudocode

```c
__int64 __fastcall CVirtualListCtrl::StaticWindowProc(HWND a1, unsigned int a2, HDC a3, LONG_PTR *a4)
{
  LONG_PTR WindowLongPtrA; // rbx
  HDC DC; // rdi
  void *v11; // rdx
  LONG v12; // ecx
  UINT v13; // eax
  HPALETTE v14; // rdx
  HPALETTE v15; // r14
  int nMin; // ecx
  int v17; // esi
  HDC hdcSrc; // r12
  int nMax; // edx
  int v20; // r15d
  int cy; // eax
  int v22; // edx
  int v23; // r9d
  int v24; // ecx
  UINT v25; // edx
  HDC v26; // rdi
  void *v27; // rdx
  int v28; // ecx
  int v29; // edx
  int v30; // r8d
  LONG_PTR v31; // rbx
  int v32; // eax
  int v33; // edx
  int nTrackPos; // edx
  char *v35; // rdi
  char *v36; // rdi
  char *v37; // rdi
  char *v38; // rdi
  char *v39; // rdi
  char *v40; // rdi
  char *v41; // rdi
  int v42; // edx
  int v43; // eax
  int pvParam; // [rsp+50h] [rbp-B0h] BYREF
  struct tagSIZE sz; // [rsp+58h] [rbp-A8h] BYREF
  HDC v46[6]; // [rsp+60h] [rbp-A0h] BYREF
  SCROLLINFO rect; // [rsp+90h] [rbp-70h] BYREF
  struct tagRECT Rect; // [rsp+B0h] [rbp-50h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(&Paint, 0, sizeof(Paint));
  sz = 0;
  pvParam = 0;
  Rect = 0;
  WindowLongPtrA = GetWindowLongPtrA(a1, 0);
  if ( a2 > 0x87 )
  {
    if ( a2 != 256 )
    {
      switch ( a2 )
      {
        case 0x115u:
          if ( (_WORD)a3 )
          {
            switch ( (unsigned __int16)a3 )
            {
              case 1u:
                nTrackPos = *(_DWORD *)(WindowLongPtrA + 12) + 1;
                break;
              case 2u:
                nTrackPos = *(_DWORD *)(WindowLongPtrA + 12) - *(_DWORD *)(WindowLongPtrA + 24);
                break;
              case 3u:
                nTrackPos = *(_DWORD *)(WindowLongPtrA + 12) + *(_DWORD *)(WindowLongPtrA + 24);
                break;
              case 4u:
              case 5u:
                if ( *(int *)(WindowLongPtrA + 8) <= 0xFFFF )
                {
                  nTrackPos = WORD1(a3);
                }
                else
                {
                  rect.cbSize = 28;
                  rect.fMask = 16;
                  memset(&rect.nMin, 0, 20);
                  GetScrollInfo(a1, 1, &rect);
                  nTrackPos = rect.nTrackPos;
                }
                break;
              case 6u:
                nTrackPos = 0;
                break;
              case 7u:
                nTrackPos = *(_DWORD *)(WindowLongPtrA + 8);
                break;
              default:
                return 0;
            }
          }
          else
          {
            nTrackPos = *(_DWORD *)(WindowLongPtrA + 12) - 1;
          }
          goto LABEL_62;
        case 0x201u:
          SetFocus(a1);
          if ( *(_DWORD *)(WindowLongPtrA + 20) )
            CVirtualListCtrl::SetSelection(
              (CVirtualListCtrl *)WindowLongPtrA,
              *(_DWORD *)(WindowLongPtrA + 12) + WORD1(a4) / *(int *)(WindowLongPtrA + 20),
              1);
          v29 = -2;
          break;
        case 0x203u:
          SetFocus(a1);
          if ( !*(_DWORD *)(WindowLongPtrA + 20)
            || *(_DWORD *)(WindowLongPtrA + 16) != *(_DWORD *)(WindowLongPtrA + 12)
                                                 + WORD1(a4) / *(int *)(WindowLongPtrA + 20) )
          {
            return 0;
          }
          v29 = -3;
          break;
        case 0x204u:
          SetFocus(a1);
          v29 = -5;
          break;
        case 0x206u:
          SetFocus(a1);
          v29 = -6;
          break;
        case 0x20Au:
          if ( SystemParametersInfoA(0x68u, 0, &pvParam, 0) )
          {
            v32 = pvParam;
          }
          else
          {
            v32 = 3;
            pvParam = 3;
          }
          v33 = *(_DWORD *)(WindowLongPtrA + 12);
          if ( SWORD1(a3) <= 0 )
            nTrackPos = v32 + v33;
          else
            nTrackPos = v33 - v32;
LABEL_62:
          CVirtualListCtrl::SetTopIndex((CVirtualListCtrl *)WindowLongPtrA, nTrackPos);
          return 0;
        default:
LABEL_55:
          v25 = a2;
          return DefWindowProcA(a1, v25, (WPARAM)a3, (LPARAM)a4);
      }
LABEL_110:
      CVirtualListCtrl::Notify((CVirtualListCtrl *)WindowLongPtrA, v29, 0);
      return 0;
    }
    v35 = (char *)a3 - 9;
    if ( !v35 )
    {
      v29 = -102;
      goto LABEL_110;
    }
    v36 = v35 - 4;
    if ( !v36 )
    {
      v29 = -4;
      goto LABEL_110;
    }
    v37 = v36 - 20;
    if ( v37 )
    {
      v38 = v37 - 1;
      if ( v38 )
      {
        v39 = v38 - 1;
        if ( !v39 )
        {
          v42 = *(_DWORD *)(WindowLongPtrA + 8) - 1;
          goto LABEL_107;
        }
        v40 = v39 - 1;
        if ( !v40 )
        {
          v42 = 0;
          goto LABEL_107;
        }
        v41 = v40 - 2;
        if ( v41 )
        {
          if ( v41 != (char *)2 )
            return 0;
          v42 = *(_DWORD *)(WindowLongPtrA + 16) + 1;
        }
        else
        {
          v42 = *(_DWORD *)(WindowLongPtrA + 16) - 1;
        }
      }
      else
      {
        v42 = *(_DWORD *)(WindowLongPtrA + 16) + *(_DWORD *)(WindowLongPtrA + 24);
      }
    }
    else
    {
      v42 = *(_DWORD *)(WindowLongPtrA + 16) - *(_DWORD *)(WindowLongPtrA + 24);
    }
    pvParam = v42;
    if ( v42 < 0 )
    {
      v42 = 0;
LABEL_106:
      pvParam = v42;
      goto LABEL_107;
    }
    v43 = *(_DWORD *)(WindowLongPtrA + 8);
    if ( v42 >= v43 )
    {
      v42 = v43 - 1;
      goto LABEL_106;
    }
LABEL_107:
    CVirtualListCtrl::SetSelection((CVirtualListCtrl *)WindowLongPtrA, v42, 1);
    return 0;
  }
  switch ( a2 )
  {
    case 0x87u:
      return 1;
    case 1u:
      v31 = *a4;
      SetWindowLongPtrA(a1, 0, *a4);
      *(_QWORD *)(v31 + 40) = a1;
      break;
    case 5u:
LABEL_13:
      GetClientRect(a1, &Rect);
      DC = GetDC(a1);
      SaveDC(DC);
      v11 = *(void **)(WindowLongPtrA + 32);
      if ( v11 )
        SelectObject(DC, v11);
      GetTextExtentPointA(DC, "CC", 2, &sz);
      v12 = sz.cy;
      *(_DWORD *)(WindowLongPtrA + 20) = sz.cy;
      if ( v12 )
        v13 = (Rect.bottom - Rect.top) / v12;
      else
        v13 = 0;
      *(_DWORD *)(WindowLongPtrA + 24) = v13;
      *(_QWORD *)&rect.nMin = 0;
      *(_QWORD *)&rect.nPos = 0;
      rect.cbSize = 28;
      rect.fMask = 2;
      rect.nPage = v13;
      SetScrollInfo(a1, 1, &rect, 1);
      RestoreDC(DC, -1);
      ReleaseDC(a1, DC);
      return 0;
    case 7u:
      *(_DWORD *)(WindowLongPtrA + 28) = 1;
      CVirtualListCtrl::RedrawCurrentItem((CVirtualListCtrl *)WindowLongPtrA);
      CVirtualListCtrl::Notify((CVirtualListCtrl *)WindowLongPtrA, -7, 0);
      MSAANotifyWinEvent(0x8005u, a1, v30, 0);
      break;
    case 8u:
      *(_DWORD *)(WindowLongPtrA + 28) = 0;
      CVirtualListCtrl::RedrawCurrentItem((CVirtualListCtrl *)WindowLongPtrA);
      v29 = -8;
      goto LABEL_110;
    case 0xFu:
      v26 = BeginPaint(a1, &Paint);
      SaveDC(v26);
      v27 = *(void **)(WindowLongPtrA + 32);
      if ( v27 )
        SelectObject(v26, v27);
      pvParam = 0;
      if ( *(int *)(WindowLongPtrA + 24) >= 0 )
      {
        v28 = 0;
        do
        {
          CVirtualListCtrl::GetItemRect(
            (CVirtualListCtrl *)WindowLongPtrA,
            v28 + *(_DWORD *)(WindowLongPtrA + 12),
            &Rect);
          CVirtualListCtrl::DrawItem(
            (CVirtualListCtrl *)WindowLongPtrA,
            v26,
            pvParam + *(_DWORD *)(WindowLongPtrA + 12),
            &Rect,
            pvParam + *(_DWORD *)(WindowLongPtrA + 12) == *(_DWORD *)(WindowLongPtrA + 16),
            *(_DWORD *)(WindowLongPtrA + 28));
          v28 = pvParam + 1;
          pvParam = v28;
        }
        while ( v28 <= *(_DWORD *)(WindowLongPtrA + 24) );
      }
      RestoreDC(v26, -1);
      EndPaint(a1, &Paint);
      return 0;
    case 0x14u:
      if ( *(_QWORD *)(WindowLongPtrA + 80) )
      {
        *(_OWORD *)&rect.cbSize = 0;
        GetClientRect(a1, (LPRECT)&rect);
        CPalDC::CPalDC((CPalDC *)v46, *(HBITMAP *)(WindowLongPtrA + 80), 0);
        v14 = *(HPALETTE *)(WindowLongPtrA + 64);
        v15 = 0;
        if ( v14 )
        {
          v15 = SelectPalette(a3, v14, 0);
          RealizePalette(a3);
        }
        nMin = rect.nMin;
        v17 = 0;
        if ( rect.nMin >= 0 )
        {
          hdcSrc = v46[0];
          nMax = rect.nMax;
          do
          {
            v20 = 0;
            if ( nMax >= 0 )
            {
              do
              {
                cy = *(_DWORD *)(WindowLongPtrA + 92);
                v22 = nMax - v20;
                v23 = *(_DWORD *)(WindowLongPtrA + 88);
                v24 = nMin - v17;
                if ( cy >= v22 )
                  cy = v22;
                if ( v23 >= v24 )
                  v23 = v24;
                BitBlt(a3, v17, v20, v23, cy, hdcSrc, 0, 0, 0xCC0020u);
                v20 += *(_DWORD *)(WindowLongPtrA + 92);
                nMax = rect.nMax;
                nMin = rect.nMin;
              }
              while ( v20 <= rect.nMax );
            }
            v17 += *(_DWORD *)(WindowLongPtrA + 88);
          }
          while ( v17 <= nMin );
        }
        if ( v15 )
          SelectPalette(a3, v15, 0);
        CPalDC::~CPalDC((CPalDC *)v46);
      }
      else
      {
        if ( !*(_QWORD *)(WindowLongPtrA + 72) )
        {
          v25 = 20;
          return DefWindowProcA(a1, v25, (WPARAM)a3, (LPARAM)a4);
        }
        *(_OWORD *)&rect.cbSize = 0;
        GetClipBox(a3, (LPRECT)&rect);
        FillRect(a3, (const RECT *)&rect, *(HBRUSH *)(WindowLongPtrA + 72));
      }
      return 1;
    case 0x30u:
      *(_QWORD *)(WindowLongPtrA + 32) = a3;
      goto LABEL_13;
    case 0x3Du:
      return CVirtualListCtrl::HandleGetObjectMsg(
               (CVirtualListCtrl *)WindowLongPtrA,
               *(HWND *)(WindowLongPtrA + 40),
               (unsigned __int64)a3,
               (__int64)a4);
    default:
      goto LABEL_55;
  }
  return 0;
}

```

## disassembly

```asm
0x18006ccc0  push    rbp
0x18006ccc2  push    rbx
0x18006ccc3  push    rsi
0x18006ccc4  push    rdi
0x18006ccc5  push    r12
0x18006ccc7  push    r13
0x18006ccc9  push    r14
0x18006cccb  push    r15
0x18006cccd  lea     rbp, [rsp-28h]
0x18006ccd2  sub     rsp, 128h
0x18006ccd9  mov     rax, cs:__security_cookie
0x18006cce0  xor     rax, rsp
0x18006cce3  mov     [rbp+60h+var_50], rax
0x18006cce7  mov     r15d, edx
0x18006ccea  mov     rdi, r8
0x18006cced  xor     edx, edx; Val
0x18006ccef  mov     rsi, rcx
0x18006ccf2  lea     rcx, [rbp+60h+Paint]; void *
0x18006ccf6  mov     r14, r9
0x18006ccf9  lea     r8d, [rdx+48h]; Size
0x18006ccfd  call    memset_0
0x18006cd02  xorps   xmm0, xmm0
0x18006cd05  xor     r13d, r13d
0x18006cd08  xor     edx, edx; nIndex
0x18006cd0a  mov     qword ptr [rsp+160h+sz.cx], r13
0x18006cd0f  mov     rcx, rsi; hWnd
0x18006cd12  mov     [rsp+160h+pvParam], r13d
0x18006cd17  movups  xmmword ptr [rbp+60h+Rect.left], xmm0
0x18006cd1b  call    cs:__imp_GetWindowLongPtrA
0x18006cd21  mov     rbx, rax
0x18006cd24  mov     eax, 87h
0x18006cd29  cmp     r15d, eax
0x18006cd2c  ja      loc_18006D08C
0x18006cd32  jz      loc_18006CEE3
0x18006cd38  mov     eax, r15d
0x18006cd3b  sub     eax, 1
0x18006cd3e  jz      loc_18006D072
0x18006cd44  sub     eax, 4
0x18006cd47  jz      short loc_18006CD96
0x18006cd49  sub     eax, 2
0x18006cd4c  jz      loc_18006CFED
0x18006cd52  sub     eax, 1
0x18006cd55  jz      loc_18006CFD7
0x18006cd5b  sub     eax, 7
0x18006cd5e  jz      loc_18006CF33
0x18006cd64  sub     eax, 5
0x18006cd67  jz      loc_18006CE02
0x18006cd6d  sub     eax, 1Ch
0x18006cd70  jz      short loc_18006CD92
0x18006cd72  cmp     eax, 0Dh
0x18006cd75  jnz     loc_18006D0C6
0x18006cd7b  mov     rdx, [rbx+28h]; HWND
0x18006cd7f  mov     r9, r14; __int64
0x18006cd82  mov     r8, rdi; unsigned __int64
0x18006cd85  mov     rcx, rbx; this
0x18006cd88  call    ?HandleGetObjectMsg@CVirtualListCtrl@@QEAA_JPEAUHWND__@@_K_J@Z; CVirtualListCtrl::HandleGetObjectMsg(HWND__ *,unsigned __int64,__int64)
0x18006cd8d  jmp     loc_18006D301
0x18006cd92  mov     [rbx+20h], rdi
0x18006cd96  lea     rdx, [rbp+60h+Rect]; lpRect
0x18006cd9a  mov     rcx, rsi; hWnd
0x18006cd9d  call    cs:__imp_GetClientRect
0x18006cda3  mov     rcx, rsi; hWnd
0x18006cda6  call    cs:__imp_GetDC
0x18006cdac  mov     rcx, rax; hdc
0x18006cdaf  mov     rdi, rax
0x18006cdb2  call    cs:__imp_SaveDC
0x18006cdb8  mov     rdx, [rbx+20h]; h
0x18006cdbc  test    rdx, rdx
0x18006cdbf  jz      short loc_18006CDCA
0x18006cdc1  mov     rcx, rdi; hdc
0x18006cdc4  call    cs:__imp_SelectObject
0x18006cdca  lea     r9, [rsp+160h+sz]; lpsz
0x18006cdcf  mov     r8d, 2; c
0x18006cdd5  lea     rdx, aCc; "CC"
0x18006cddc  mov     rcx, rdi; hdc
0x18006cddf  call    cs:__imp_GetTextExtentPointA
0x18006cde5  mov     ecx, [rsp+160h+sz.cy]
0x18006cde9  mov     [rbx+14h], ecx
0x18006cdec  test    ecx, ecx
0x18006cdee  jz      loc_18006D020
0x18006cdf4  mov     eax, [rbp+60h+Rect.bottom]
0x18006cdf7  sub     eax, [rbp+60h+Rect.top]
0x18006cdfa  cdq
0x18006cdfb  idiv    ecx
0x18006cdfd  jmp     loc_18006D023
0x18006ce02  cmp     [rbx+50h], r13
0x18006ce06  jz      loc_18006CEED
0x18006ce0c  xorps   xmm0, xmm0
0x18006ce0f  lea     rdx, [rbp+60h+rect]; lpRect
0x18006ce13  mov     rcx, rsi; hWnd
0x18006ce16  movups  xmmword ptr [rbp+60h+rect.left], xmm0
0x18006ce1a  call    cs:__imp_GetClientRect
0x18006ce20  mov     rdx, [rbx+50h]; h
0x18006ce24  lea     rcx, [rsp+160h+var_100]; this
0x18006ce29  xor     r8d, r8d; HPALETTE
0x18006ce2c  call    ??0CPalDC@@QEAA@PEAUHBITMAP__@@PEAUHPALETTE__@@@Z; CPalDC::CPalDC(HBITMAP__ *,HPALETTE__ *)
0x18006ce31  mov     rdx, [rbx+40h]; hPal
0x18006ce35  mov     r14, r13
0x18006ce38  test    rdx, rdx
0x18006ce3b  jz      short loc_18006CE55
0x18006ce3d  xor     r8d, r8d; bForceBkgd
0x18006ce40  mov     rcx, rdi; hdc
0x18006ce43  call    cs:__imp_SelectPalette
0x18006ce49  mov     rcx, rdi; hdc
0x18006ce4c  mov     r14, rax
0x18006ce4f  call    cs:__imp_RealizePalette
0x18006ce55  mov     ecx, [rbp+60h+rect.right]
0x18006ce58  mov     esi, r13d
0x18006ce5b  test    ecx, ecx
0x18006ce5d  js      short loc_18006CEC5
0x18006ce5f  mov     r12, [rsp+160h+var_100]
0x18006ce64  mov     edx, [rbp+60h+rect.bottom]
0x18006ce67  mov     r15d, r13d
0x18006ce6a  test    edx, edx
0x18006ce6c  js      short loc_18006CEBE
0x18006ce6e  mov     eax, [rbx+5Ch]
0x18006ce71  sub     edx, r15d
0x18006ce74  mov     r9d, [rbx+58h]
0x18006ce78  sub     ecx, esi
0x18006ce7a  cmp     eax, edx
0x18006ce7c  mov     [rsp+160h+rop], 0CC0020h; rop
0x18006ce84  mov     [rsp+160h+y1], r13d; y1
0x18006ce89  mov     r8d, r15d; y
0x18006ce8c  cmovge  eax, edx
0x18006ce8f  mov     [rsp+160h+x1], r13d; x1
0x18006ce94  cmp     r9d, ecx
0x18006ce97  mov     [rsp+160h+hdcSrc], r12; hdcSrc
0x18006ce9c  mov     edx, esi; x
0x18006ce9e  mov     [rsp+160h+cy], eax; cy
0x18006cea2  cmovge  r9d, ecx; cx
0x18006cea6  mov     rcx, rdi; hdc
0x18006cea9  call    cs:__imp_BitBlt
0x18006ceaf  add     r15d, [rbx+5Ch]
0x18006ceb3  mov     edx, [rbp+60h+rect.bottom]
0x18006ceb6  mov     ecx, [rbp+60h+rect.right]
0x18006ceb9  cmp     r15d, edx
0x18006cebc  jle     short loc_18006CE6E
0x18006cebe  add     esi, [rbx+58h]
0x18006cec1  cmp     esi, ecx
0x18006cec3  jle     short loc_18006CE67
0x18006cec5  test    r14, r14
0x18006cec8  jz      short loc_18006CED9
0x18006ceca  xor     r8d, r8d; bForceBkgd
0x18006cecd  mov     rdx, r14; hPal
0x18006ced0  mov     rcx, rdi; hdc
0x18006ced3  call    cs:__imp_SelectPalette
0x18006ced9  lea     rcx, [rsp+160h+var_100]; this
0x18006cede  call    ??1CPalDC@@QEAA@XZ; CPalDC::~CPalDC(void)
0x18006cee3  mov     eax, 1
0x18006cee8  jmp     loc_18006D301
0x18006ceed  cmp     [rbx+48h], r13
0x18006cef1  jz      short loc_18006CF1A
0x18006cef3  xorps   xmm0, xmm0
0x18006cef6  lea     rdx, [rbp+60h+rect]; lprect
0x18006cefa  mov     rcx, rdi; hdc
0x18006cefd  movups  xmmword ptr [rbp+60h+rect.left], xmm0
0x18006cf01  call    cs:__imp_GetClipBox
0x18006cf07  mov     r8, [rbx+48h]; hbr
0x18006cf0b  lea     rdx, [rbp+60h+rect]; lprc
0x18006cf0f  mov     rcx, rdi; hDC
0x18006cf12  call    cs:__imp_FillRect
0x18006cf18  jmp     short loc_18006CEE3
0x18006cf1a  mov     edx, 14h; Msg
0x18006cf1f  mov     r8, rdi; wParam
0x18006cf22  mov     r9, r14; lParam
0x18006cf25  mov     rcx, rsi; hWnd
0x18006cf28  call    cs:__imp_DefWindowProcA
0x18006cf2e  jmp     loc_18006D301
0x18006cf33  lea     rdx, [rbp+60h+Paint]; lpPaint
0x18006cf37  mov     rcx, rsi; hWnd
0x18006cf3a  call    cs:__imp_BeginPaint
0x18006cf40  mov     rcx, rax; hdc
0x18006cf43  mov     rdi, rax
0x18006cf46  call    cs:__imp_SaveDC
0x18006cf4c  mov     rdx, [rbx+20h]; h
0x18006cf50  test    rdx, rdx
0x18006cf53  jz      short loc_18006CF5E
0x18006cf55  mov     rcx, rdi; hdc
0x18006cf58  call    cs:__imp_SelectObject
0x18006cf5e  mov     [rsp+160h+pvParam], r13d
0x18006cf63  cmp     [rbx+18h], r13d
0x18006cf67  jl      short loc_18006CFB9
0x18006cf69  mov     ecx, r13d
0x18006cf6c  mov     edx, [rbx+0Ch]
0x18006cf6f  lea     r8, [rbp+60h+Rect]; struct tagRECT *
0x18006cf73  add     edx, ecx; int
0x18006cf75  mov     rcx, rbx; this
0x18006cf78  call    ?GetItemRect@CVirtualListCtrl@@QEAAHHPEAUtagRECT@@@Z; CVirtualListCtrl::GetItemRect(int,tagRECT *)
0x18006cf7d  mov     r8d, [rbx+0Ch]
0x18006cf81  lea     r9, [rbp+60h+Rect]; RECT *
0x18006cf85  add     r8d, [rsp+160h+pvParam]; int
0x18006cf8a  mov     ecx, r13d
0x18006cf8d  cmp     r8d, [rbx+10h]
0x18006cf91  mov     rdx, rdi; HDC
0x18006cf94  mov     eax, [rbx+1Ch]
0x18006cf97  setz    cl
0x18006cf9a  mov     dword ptr [rsp+160h+hdcSrc], eax; int
0x18006cf9e  mov     [rsp+160h+cy], ecx; int
0x18006cfa2  mov     rcx, rbx; this
0x18006cfa5  call    ?DrawItem@CVirtualListCtrl@@QEAA_JPEAUHDC__@@HPEAUtagRECT@@HH@Z; CVirtualListCtrl::DrawItem(HDC__ *,int,tagRECT *,int,int)
0x18006cfaa  mov     ecx, [rsp+160h+pvParam]
0x18006cfae  inc     ecx
0x18006cfb0  mov     [rsp+160h+pvParam], ecx
0x18006cfb4  cmp     ecx, [rbx+18h]
0x18006cfb7  jle     short loc_18006CF6C
0x18006cfb9  or      edx, 0FFFFFFFFh; nSavedDC
0x18006cfbc  mov     rcx, rdi; hdc
0x18006cfbf  call    cs:__imp_RestoreDC
0x18006cfc5  lea     rdx, [rbp+60h+Paint]; lpPaint
0x18006cfc9  mov     rcx, rsi; hWnd
0x18006cfcc  call    cs:__imp_EndPaint
0x18006cfd2  jmp     loc_18006D2FF
0x18006cfd7  mov     rcx, rbx; this
0x18006cfda  mov     [rbx+1Ch], r13d
0x18006cfde  call    ?RedrawCurrentItem@CVirtualListCtrl@@AEAAXXZ; CVirtualListCtrl::RedrawCurrentItem(void)
0x18006cfe3  mov     edx, 0FFFFFFF8h
0x18006cfe8  jmp     loc_18006D2F4
0x18006cfed  mov     rcx, rbx; this
0x18006cff0  mov     dword ptr [rbx+1Ch], 1
0x18006cff7  call    ?RedrawCurrentItem@CVirtualListCtrl@@AEAAXXZ; CVirtualListCtrl::RedrawCurrentItem(void)
0x18006cffc  xor     r8d, r8d; struct tagNMHDR *
0x18006cfff  mov     rcx, rbx; this
0x18006d002  lea     edx, [r8-7]; int
0x18006d006  call    ?Notify@CVirtualListCtrl@@AEAA_JHPEAUtagNMHDR@@@Z; CVirtualListCtrl::Notify(int,tagNMHDR *)
0x18006d00b  xor     r9d, r9d; int
0x18006d00e  mov     rdx, rsi; HWND
0x18006d011  mov     ecx, 8005h; unsigned int
0x18006d016  call    ?MSAANotifyWinEvent@@YAXKPEAUHWND__@@JJ@Z; MSAANotifyWinEvent(ulong,HWND__ *,long,long)
0x18006d01b  jmp     loc_18006D2FF
0x18006d020  mov     eax, r13d
0x18006d023  mov     [rbx+18h], eax
0x18006d026  lea     r8, [rbp+60h+rect]; lpsi
0x18006d02a  mov     r9d, 1; redraw
0x18006d030  mov     qword ptr [rbp+60h+rect.right], r13
0x18006d034  mov     edx, r9d; nBar
0x18006d037  mov     [rbp+60h+var_BC], r13
0x18006d03b  mov     rcx, rsi; hwnd
0x18006d03e  mov     [rbp+60h+rect.left], 1Ch
0x18006d045  mov     [rbp+60h+rect.top], 2
0x18006d04c  mov     [rbp+60h+var_C0], eax
0x18006d04f  call    cs:__imp_SetScrollInfo
0x18006d055  or      edx, 0FFFFFFFFh; nSavedDC
0x18006d058  mov     rcx, rdi; hdc
0x18006d05b  call    cs:__imp_RestoreDC
0x18006d061  mov     rdx, rdi; hDC
0x18006d064  mov     rcx, rsi; hWnd
0x18006d067  call    cs:__imp_ReleaseDC
0x18006d06d  jmp     loc_18006D2FF
0x18006d072  mov     rbx, [r14]
0x18006d075  xor     edx, edx; nIndex
0x18006d077  mov     r8, rbx; dwNewLong
0x18006d07a  mov     rcx, rsi; hWnd
0x18006d07d  call    cs:__imp_SetWindowLongPtrA
0x18006d083  mov     [rbx+28h], rsi
0x18006d087  jmp     loc_18006D2FF
0x18006d08c  mov     eax, r15d
0x18006d08f  sub     eax, 100h
0x18006d094  jz      loc_18006D262
0x18006d09a  sub     eax, 15h
0x18006d09d  jz      loc_18006D1A6
0x18006d0a3  sub     eax, 0ECh
0x18006d0a8  jz      loc_18006D16E
0x18006d0ae  sub     eax, 2
0x18006d0b1  jz      loc_18006D139
0x18006d0b7  sub     eax, 1
0x18006d0ba  jz      short loc_18006D126
0x18006d0bc  sub     eax, 2
0x18006d0bf  jz      short loc_18006D113
0x18006d0c1  cmp     eax, 4
0x18006d0c4  jz      short loc_18006D0CE
0x18006d0c6  mov     edx, r15d
0x18006d0c9  jmp     loc_18006CF1F
0x18006d0ce  xor     edx, edx; uiParam
0x18006d0d0  lea     r8, [rsp+160h+pvParam]; pvParam
0x18006d0d5  xor     r9d, r9d; fWinIni
0x18006d0d8  lea     ecx, [rdx+68h]; uiAction
0x18006d0db  call    cs:__imp_SystemParametersInfoA
0x18006d0e1  test    eax, eax
0x18006d0e3  jnz     short loc_18006D0F0
0x18006d0e5  mov     eax, 3
0x18006d0ea  mov     [rsp+160h+pvParam], eax
0x18006d0ee  jmp     short loc_18006D0F4
0x18006d0f0  mov     eax, [rsp+160h+pvParam]
0x18006d0f4  mov     edx, [rbx+0Ch]
0x18006d0f7  shr     rdi, 10h
0x18006d0fb  test    di, di
0x18006d0fe  jle     short loc_18006D104
0x18006d100  sub     edx, eax
0x18006d102  jmp     short loc_18006D106
0x18006d104  add     edx, eax; int
0x18006d106  mov     rcx, rbx; this
0x18006d109  call    ?SetTopIndex@CVirtualListCtrl@@QEAAHH@Z; CVirtualListCtrl::SetTopIndex(int)
0x18006d10e  jmp     loc_18006D2FF
0x18006d113  mov     rcx, rsi; hWnd
0x18006d116  call    cs:__imp_SetFocus
0x18006d11c  mov     edx, 0FFFFFFFAh
0x18006d121  jmp     loc_18006D2F4
0x18006d126  mov     rcx, rsi; hWnd
0x18006d129  call    cs:__imp_SetFocus
0x18006d12f  mov     edx, 0FFFFFFFBh
  ... truncated ...
```
