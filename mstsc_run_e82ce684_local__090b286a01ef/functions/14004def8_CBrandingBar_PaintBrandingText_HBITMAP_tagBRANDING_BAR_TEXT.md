# CBrandingBar::PaintBrandingText(HBITMAP__ *,tagBRANDING_BAR_TEXT *)

- ea: `0x14004def8`
- end: `0x14004e411`
- name: `?PaintBrandingText@CBrandingBar@@IEAAHPEAUHBITMAP__@@PEAUtagBRANDING_BAR_TEXT@@@Z`
- size: `1305`
- prototype: `__int64 __fastcall(CBrandingBar *__hidden this, HBITMAP h, struct tagBRANDING_BAR_TEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14004d40c`

## callees

- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14001e2f4`
- `0x14004dbf0`
- `0x14004def8`
- `0x14004e418`
- `0x1400fcad0`
- `0x140113390`

## import_xrefs

- `USER32!DrawTextW` at `0x14004e240`
- `USER32!DrawTextW` at `0x14004e240`
- `USER32!GetClientRect` at `0x14004e081`
- `USER32!GetClientRect` at `0x14004e081`
- `USER32!GetWindowLongPtrW` at `0x14004df51`
- `USER32!GetWindowLongPtrW` at `0x14004e0b4`
- `USER32!GetWindowLongPtrW` at `0x14004df51`
- `USER32!GetWindowLongPtrW` at `0x14004e0b4`
- `msvcrt!_wtol` at `0x14004dfd3`
- `msvcrt!_wtol` at `0x14004dfd3`
- `KERNEL32!GetLastError` at `0x14004e26c`
- `KERNEL32!GetLastError` at `0x14004e26c`
- `GDI32!SetMapMode` at `0x14004e072`
- `GDI32!SetMapMode` at `0x14004e072`
- `GDI32!DeleteDC` at `0x14004e38d`
- `GDI32!DeleteDC` at `0x14004e38d`
- `GDI32!CreateCompatibleDC` at `0x14004e021`
- `GDI32!CreateCompatibleDC` at `0x14004e021`
- `GDI32!SetTextColor` at `0x14004e054`
- `GDI32!SetTextColor` at `0x14004e054`
- `GDI32!SetBkMode` at `0x14004e066`
- `GDI32!SetBkMode` at `0x14004e066`
- `GDI32!SelectObject` at `0x14004e041`
- `GDI32!SelectObject` at `0x14004e207`
- `GDI32!SelectObject` at `0x14004e214`
- `GDI32!SelectObject` at `0x14004e36e`
- `GDI32!SelectObject` at `0x14004e384`
- `GDI32!SelectObject` at `0x14004e041`
- `GDI32!SelectObject` at `0x14004e207`
- `GDI32!SelectObject` at `0x14004e214`
- `GDI32!SelectObject` at `0x14004e36e`
- `GDI32!SelectObject` at `0x14004e384`
- `GDI32!DeleteObject` at `0x14004e1d4`
- `GDI32!DeleteObject` at `0x14004e3a3`
- `GDI32!DeleteObject` at `0x14004e1d4`
- `GDI32!DeleteObject` at `0x14004e3a3`

## pseudocode

```c
__int64 __fastcall CBrandingBar::PaintBrandingText(CBrandingBar *this, HBITMAP h, struct tagBRANDING_BAR_TEXT *a3)
{
  unsigned int v3; // r15d
  HWND v6; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v9; // eax
  HDC CompatibleDC; // rax
  HDC v11; // rsi
  HFONT v12; // r14
  LONG right; // ebx
  LONG v14; // eax
  HWND v15; // rcx
  LONG v16; // eax
  LONG v17; // ebx
  unsigned int v18; // eax
  const unsigned __int16 *v19; // r8
  PVOID v20; // r11
  unsigned int v21; // eax
  HFONT FontFromResourceInfo; // rax
  __int64 v23; // r8
  int v24; // r12d
  DWORD LastError; // ebx
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 format; // [rsp+40h] [rbp-C0h]
  unsigned int v32; // [rsp+48h] [rbp-B8h]
  HGDIOBJ ha; // [rsp+50h] [rbp-B0h]
  HGDIOBJ v34; // [rsp+58h] [rbp-A8h]
  struct tagRECT rc; // [rsp+60h] [rbp-A0h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-90h] BYREF
  wchar_t String[24]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR chText[264]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = 0;
  v32 = 0;
  v6 = (HWND)*((_QWORD *)this + 1);
  Rect = 0;
  rc = 0;
  if ( (GetWindowLongPtrW(v6, -20) & 0x400000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_1af8da3092413da1a7897833402d1c53_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    LODWORD(format) = 32770;
  }
  else
  {
    LODWORD(format) = 0x8000;
  }
  if ( TSLoadString(*((HINSTANCE *)this + 2), *((_DWORD *)a3 + 3), String, 20) )
  {
    HIDWORD(format) = _wtol(String);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1af8da3092413da1a7897833402d1c53_Traceguids, v9);
    }
    HIDWORD(format) = 5;
  }
  CompatibleDC = CreateCompatibleDC(0);
  v11 = CompatibleDC;
  if ( CompatibleDC )
  {
    ha = 0;
    v12 = 0;
    v34 = SelectObject(CompatibleDC, h);
    SetTextColor(v11, 0x993300u);
    SetBkMode(v11, 1);
    SetMapMode(v11, 1);
    GetClientRect(*((HWND *)this + 1), &Rect);
    right = Rect.right;
    if ( *((_DWORD *)this + 8) < Rect.right )
      right = *((_DWORD *)this + 8);
    v14 = CBrandingBar::ScaleForCurrentDpi(this, *((_DWORD *)a3 + 1));
    v15 = (HWND)*((_QWORD *)this + 1);
    rc.top = v14;
    rc.bottom = 100;
    if ( (GetWindowLongPtrW(v15, -20) & 0x400000) != 0 )
    {
      v16 = *((_DWORD *)a3 + 2);
      v17 = right - *(_DWORD *)a3;
    }
    else
    {
      v16 = *(_DWORD *)a3;
      v17 = right - *((_DWORD *)a3 + 2);
    }
    rc.right = v17;
    rc.left = v16;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v18 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_1af8da3092413da1a7897833402d1c53_Traceguids,
        v18,
        rc.left,
        rc.top,
        rc.right,
        rc.bottom,
        format);
    }
    while ( v3 < *((_DWORD *)a3 + 4) )
    {
      v19 = (const unsigned __int16 *)*((_QWORD *)a3 + 3 * v3 + 3);
      if ( v19 )
      {
        if ( StringCchCopyW(chText, 0x104u, v19) < 0
          && WPP_GLOBAL_Control != v20
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1af8da3092413da1a7897833402d1c53_Traceguids, v21);
        }
      }
      else if ( !TSLoadString(*((HINSTANCE *)this + 2), *((_DWORD *)a3 + 6 * v3 + 8), chText, 260) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v28 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_1af8da3092413da1a7897833402d1c53_Traceguids, v28);
        }
        goto LABEL_60;
      }
      if ( v12 )
        DeleteObject(v12);
      FontFromResourceInfo = CBrandingBar::LoadFontFromResourceInfo(
                               this,
                               *((_DWORD *)a3 + 6 * v3 + 9),
                               *((_DWORD *)a3 + 6 * v3 + 10),
                               *((_DWORD *)a3 + 6 * v3 + 11));
      v12 = FontFromResourceInfo;
      if ( !FontFromResourceInfo )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1af8da3092413da1a7897833402d1c53_Traceguids, v27, v3);
        }
        return v32;
      }
      if ( v3 )
        SelectObject(v11, FontFromResourceInfo);
      else
        ha = SelectObject(v11, FontFromResourceInfo);
      v23 = -1;
      do
        ++v23;
      while ( chText[v23] );
      v24 = DrawTextW(v11, chText, v23, &rc, format);
      if ( !v24
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_1af8da3092413da1a7897833402d1c53_Traceguids,
          v26,
          LastError);
      }
      rc.top += v24 - HIDWORD(format);
      rc.bottom += v24 - HIDWORD(format);
      ++v3;
    }
    if ( ha )
      SelectObject(v11, ha);
    if ( v34 )
      SelectObject(v11, v34);
    DeleteDC(v11);
    v32 = 1;
LABEL_60:
    if ( v12 )
      DeleteObject(v12);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_1af8da3092413da1a7897833402d1c53_Traceguids, v29);
  }
  return v32;
}

```

## disassembly

```asm
0x14004def8  mov     [rsp-8+arg_18], rbx
0x14004defd  push    rbp
0x14004defe  push    rsi
0x14004deff  push    rdi
0x14004df00  push    r12
0x14004df02  push    r13
0x14004df04  push    r14
0x14004df06  push    r15
0x14004df08  lea     rbp, [rsp-1D0h]
0x14004df10  sub     rsp, 2D0h
0x14004df17  mov     rax, cs:__security_cookie
0x14004df1e  xor     rax, rsp
0x14004df21  mov     [rbp+200h+var_40], rax
0x14004df28  xor     r15d, r15d
0x14004df2b  mov     rbx, rdx
0x14004df2e  mov     r13, rcx
0x14004df31  mov     [rsp+300h+var_2B8], r15d
0x14004df36  mov     rcx, [rcx+8]; hWnd
0x14004df3a  xorps   xmm0, xmm0
0x14004df3d  xorps   xmm1, xmm1
0x14004df40  mov     rdi, r8
0x14004df43  lea     edx, [r15-14h]; nIndex
0x14004df47  movups  xmmword ptr [rsp+300h+Rect.left], xmm0
0x14004df4c  movups  xmmword ptr [rsp+300h+rc.left], xmm1
0x14004df51  call    cs:__imp_GetWindowLongPtrW
0x14004df57  lea     r14, WPP_GLOBAL_Control
0x14004df5e  lea     r12, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004df65  bt      rax, 16h
0x14004df6a  jnb     short loc_14004DFAD
0x14004df6c  mov     rax, cs:WPP_GLOBAL_Control
0x14004df73  cmp     rax, r14
0x14004df76  jz      short loc_14004DFA3
0x14004df78  test    byte ptr [rax+1Ch], 1
0x14004df7c  jz      short loc_14004DFA3
0x14004df7e  cmp     byte ptr [rax+19h], 4
0x14004df82  jb      short loc_14004DFA3
0x14004df84  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004df89  mov     rcx, cs:WPP_GLOBAL_Control
0x14004df90  lea     edx, [r15+10h]
0x14004df94  mov     r9d, eax
0x14004df97  mov     r8, r12
0x14004df9a  mov     rcx, [rcx+10h]
0x14004df9e  call    WPP_SF_d
0x14004dfa3  mov     [rsp+300h+var_2C0], 8002h
0x14004dfab  jmp     short loc_14004DFB5
0x14004dfad  mov     [rsp+300h+var_2C0], 8000h
0x14004dfb5  mov     edx, [rdi+0Ch]; unsigned int
0x14004dfb8  lea     r8, [rbp+200h+String]; unsigned __int16 *
0x14004dfbc  mov     rcx, [r13+10h]; HINSTANCE
0x14004dfc0  mov     r9d, 14h; int
0x14004dfc6  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14004dfcb  test    eax, eax
0x14004dfcd  jz      short loc_14004DFDF
0x14004dfcf  lea     rcx, [rbp+200h+String]; String
0x14004dfd3  call    cs:__imp__wtol
0x14004dfd9  mov     [rsp+300h+var_2BC], eax
0x14004dfdd  jmp     short loc_14004E01F
0x14004dfdf  mov     rax, cs:WPP_GLOBAL_Control
0x14004dfe6  cmp     rax, r14
0x14004dfe9  jz      short loc_14004E017
0x14004dfeb  test    byte ptr [rax+1Ch], 1
0x14004dfef  jz      short loc_14004E017
0x14004dff1  cmp     byte ptr [rax+19h], 2
0x14004dff5  jb      short loc_14004E017
0x14004dff7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004dffc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e003  mov     edx, 11h
0x14004e008  mov     r9d, eax
0x14004e00b  mov     r8, r12
0x14004e00e  mov     rcx, [rcx+10h]
0x14004e012  call    WPP_SF_d
0x14004e017  mov     [rsp+300h+var_2BC], 5
0x14004e01f  xor     ecx, ecx; hdc
0x14004e021  call    cs:__imp_CreateCompatibleDC
0x14004e027  mov     rsi, rax
0x14004e02a  test    rax, rax
0x14004e02d  jz      loc_14004E3AB
0x14004e033  mov     rdx, rbx; h
0x14004e036  mov     [rsp+300h+h], r15
0x14004e03b  mov     rcx, rax; hdc
0x14004e03e  mov     r14, r15
0x14004e041  call    cs:__imp_SelectObject
0x14004e047  mov     edx, 993300h; color
0x14004e04c  mov     rcx, rsi; hdc
0x14004e04f  mov     [rsp+300h+var_2A8], rax
0x14004e054  call    cs:__imp_SetTextColor
0x14004e05a  mov     r12d, 1
0x14004e060  mov     rcx, rsi; hdc
0x14004e063  mov     edx, r12d; mode
0x14004e066  call    cs:__imp_SetBkMode
0x14004e06c  mov     edx, r12d; iMode
0x14004e06f  mov     rcx, rsi; hdc
0x14004e072  call    cs:__imp_SetMapMode
0x14004e078  mov     rcx, [r13+8]; hWnd
0x14004e07c  lea     rdx, [rsp+300h+Rect]; lpRect
0x14004e081  call    cs:__imp_GetClientRect
0x14004e087  mov     ebx, [rsp+300h+Rect.right]
0x14004e08b  mov     rcx, r13; this
0x14004e08e  cmp     [r13+20h], ebx
0x14004e092  mov     edx, [rdi+4]; int
0x14004e095  cmovl   ebx, [r13+20h]
0x14004e09a  call    ?ScaleForCurrentDpi@CBrandingBar@@IEAAHH@Z; CBrandingBar::ScaleForCurrentDpi(int)
0x14004e09f  mov     rcx, [r13+8]; hWnd
0x14004e0a3  lea     edx, [r12-15h]; nIndex
0x14004e0a8  mov     [rsp+300h+rc.top], eax
0x14004e0ac  mov     [rsp+300h+rc.bottom], 64h ; 'd'
0x14004e0b4  call    cs:__imp_GetWindowLongPtrW
0x14004e0ba  bt      rax, 16h
0x14004e0bf  jnb     short loc_14004E0C8
0x14004e0c1  mov     eax, [rdi+8]
0x14004e0c4  sub     ebx, [rdi]
0x14004e0c6  jmp     short loc_14004E0CD
0x14004e0c8  mov     eax, [rdi]
0x14004e0ca  sub     ebx, [rdi+8]
0x14004e0cd  mov     [rsp+300h+rc.right], ebx
0x14004e0d1  mov     [rsp+300h+rc.left], eax
0x14004e0d5  mov     rax, cs:WPP_GLOBAL_Control
0x14004e0dc  lea     r11, WPP_GLOBAL_Control
0x14004e0e3  cmp     rax, r11
0x14004e0e6  jz      short loc_14004E13F
0x14004e0e8  test    [rax+1Ch], r12b
0x14004e0ec  jz      short loc_14004E13F
0x14004e0ee  cmp     byte ptr [rax+19h], 4
0x14004e0f2  jb      short loc_14004E13F
0x14004e0f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004e0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e100  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004e107  mov     r9d, eax
0x14004e10a  mov     edx, 12h
0x14004e10f  mov     eax, [rsp+300h+rc.bottom]
0x14004e113  mov     [rsp+300h+var_2C8], eax
0x14004e117  mov     eax, [rsp+300h+rc.right]
0x14004e11b  mov     rcx, [rcx+10h]
0x14004e11f  mov     [rsp+300h+var_2D0], eax
0x14004e123  mov     eax, [rsp+300h+rc.top]
0x14004e127  mov     [rsp+300h+var_2D8], eax
0x14004e12b  mov     eax, [rsp+300h+rc.left]
0x14004e12f  mov     [rsp+300h+format], eax
0x14004e133  call    WPP_SF_Ddddd
0x14004e138  lea     r11, WPP_GLOBAL_Control
0x14004e13f  cmp     r15d, [rdi+10h]
0x14004e143  jnb     loc_14004E35E
0x14004e149  mov     eax, r15d
0x14004e14c  xor     r12d, r12d
0x14004e14f  lea     rbx, [rax+rax*2]
0x14004e153  mov     r8, [rdi+rbx*8+18h]; unsigned __int16 *
0x14004e158  test    r8, r8
0x14004e15b  jz      short loc_14004E1AD
0x14004e15d  mov     edx, 104h; unsigned __int64
0x14004e162  lea     rcx, [rbp+200h+chText]; unsigned __int16 *
0x14004e166  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14004e16b  test    eax, eax
0x14004e16d  jns     short loc_14004E1CC
0x14004e16f  mov     rax, cs:WPP_GLOBAL_Control
0x14004e176  cmp     rax, r11
0x14004e179  jz      short loc_14004E1CC
0x14004e17b  test    byte ptr [rax+1Ch], 1
0x14004e17f  jz      short loc_14004E1CC
0x14004e181  cmp     byte ptr [rax+19h], 2
0x14004e185  jb      short loc_14004E1CC
0x14004e187  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004e18c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e193  lea     edx, [r12+13h]
0x14004e198  mov     r9d, eax
0x14004e19b  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004e1a2  mov     rcx, [rcx+10h]
0x14004e1a6  call    WPP_SF_d
0x14004e1ab  jmp     short loc_14004E1CC
0x14004e1ad  mov     edx, [rdi+rbx*8+20h]; unsigned int
0x14004e1b1  lea     r8, [rbp+200h+chText]; unsigned __int16 *
0x14004e1b5  mov     rcx, [r13+10h]; HINSTANCE
0x14004e1b9  mov     r9d, 104h; int
0x14004e1bf  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14004e1c4  test    eax, eax
0x14004e1c6  jz      loc_14004E319
0x14004e1cc  test    r14, r14
0x14004e1cf  jz      short loc_14004E1DA
0x14004e1d1  mov     rcx, r14; ho
0x14004e1d4  call    cs:__imp_DeleteObject
0x14004e1da  mov     r9d, [rdi+rbx*8+2Ch]; int
0x14004e1df  mov     rcx, r13; this
0x14004e1e2  mov     r8d, [rdi+rbx*8+28h]; unsigned int
0x14004e1e7  mov     edx, [rdi+rbx*8+24h]; unsigned int
0x14004e1eb  call    ?LoadFontFromResourceInfo@CBrandingBar@@IEAAPEAUHFONT__@@IIH@Z; CBrandingBar::LoadFontFromResourceInfo(uint,uint,int)
0x14004e1f0  mov     r14, rax
0x14004e1f3  test    rax, rax
0x14004e1f6  jz      loc_14004E2C0
0x14004e1fc  mov     rdx, rax; h
0x14004e1ff  mov     rcx, rsi; hdc
0x14004e202  test    r15d, r15d
0x14004e205  jnz     short loc_14004E214
0x14004e207  call    cs:__imp_SelectObject
0x14004e20d  mov     [rsp+300h+h], rax
0x14004e212  jmp     short loc_14004E21A
0x14004e214  call    cs:__imp_SelectObject
0x14004e21a  lea     rax, [rbp+200h+chText]
0x14004e21e  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004e222  inc     r8; cchText
0x14004e225  cmp     [rax+r8*2], r12w
0x14004e22a  jnz     short loc_14004E222
0x14004e22c  mov     eax, [rsp+300h+var_2C0]
0x14004e230  lea     r9, [rsp+300h+rc]; lprc
0x14004e235  lea     rdx, [rbp+200h+chText]; lpchText
0x14004e239  mov     [rsp+300h+format], eax; format
0x14004e23d  mov     rcx, rsi; hdc
0x14004e240  call    cs:__imp_DrawTextW
0x14004e246  mov     r12d, eax
0x14004e249  test    eax, eax
0x14004e24b  jnz     short loc_14004E29C
0x14004e24d  mov     rax, cs:WPP_GLOBAL_Control
0x14004e254  lea     r11, WPP_GLOBAL_Control
0x14004e25b  cmp     rax, r11
0x14004e25e  jz      short loc_14004E2A3
0x14004e260  test    byte ptr [rax+1Ch], 1
0x14004e264  jz      short loc_14004E2A3
0x14004e266  cmp     byte ptr [rax+19h], 2
0x14004e26a  jb      short loc_14004E2A3
0x14004e26c  call    cs:__imp_GetLastError
0x14004e272  mov     ebx, eax
0x14004e274  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004e279  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e280  lea     edx, [r12+16h]
0x14004e285  mov     r9d, eax
0x14004e288  mov     [rsp+300h+format], ebx
0x14004e28c  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004e293  mov     rcx, [rcx+10h]
0x14004e297  call    WPP_SF_Dd
0x14004e29c  lea     r11, WPP_GLOBAL_Control
0x14004e2a3  mov     eax, r12d
0x14004e2a6  sub     r12d, [rsp+300h+var_2BC]
0x14004e2ab  sub     eax, [rsp+300h+var_2BC]
0x14004e2af  add     [rsp+300h+rc.top], eax
0x14004e2b3  add     [rsp+300h+rc.bottom], r12d
0x14004e2b8  inc     r15d
0x14004e2bb  jmp     loc_14004E13F
0x14004e2c0  mov     rax, cs:WPP_GLOBAL_Control
0x14004e2c7  lea     rcx, WPP_GLOBAL_Control
0x14004e2ce  cmp     rax, rcx
0x14004e2d1  jz      loc_14004E3E3
0x14004e2d7  test    byte ptr [rax+1Ch], 1
0x14004e2db  jz      loc_14004E3E3
0x14004e2e1  cmp     byte ptr [rax+19h], 2
0x14004e2e5  jb      loc_14004E3E3
0x14004e2eb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004e2f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e2f7  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004e2fe  mov     edx, 15h
0x14004e303  mov     [rsp+300h+format], r15d
0x14004e308  mov     r9d, eax
0x14004e30b  mov     rcx, [rcx+10h]
0x14004e30f  call    WPP_SF_Dd
0x14004e314  jmp     loc_14004E3E3
0x14004e319  mov     rax, cs:WPP_GLOBAL_Control
0x14004e320  lea     rcx, WPP_GLOBAL_Control
0x14004e327  cmp     rax, rcx
0x14004e32a  jz      short loc_14004E39B
0x14004e32c  test    byte ptr [rax+1Ch], 1
0x14004e330  jz      short loc_14004E39B
0x14004e332  cmp     byte ptr [rax+19h], 2
0x14004e336  jb      short loc_14004E39B
0x14004e338  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004e33d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e344  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004e34b  mov     edx, 14h
0x14004e350  mov     r9d, eax
0x14004e353  mov     rcx, [rcx+10h]
0x14004e357  call    WPP_SF_d
0x14004e35c  jmp     short loc_14004E39B
0x14004e35e  mov     r12, [rsp+300h+h]
0x14004e363  test    r12, r12
0x14004e366  jz      short loc_14004E374
0x14004e368  mov     rdx, r12; h
0x14004e36b  mov     rcx, rsi; hdc
0x14004e36e  call    cs:__imp_SelectObject
0x14004e374  mov     rax, [rsp+300h+var_2A8]
0x14004e379  test    rax, rax
0x14004e37c  jz      short loc_14004E38A
0x14004e37e  mov     rdx, rax; h
0x14004e381  mov     rcx, rsi; hdc
0x14004e384  call    cs:__imp_SelectObject
0x14004e38a  mov     rcx, rsi; hdc
0x14004e38d  call    cs:__imp_DeleteDC
0x14004e393  mov     [rsp+300h+var_2B8], 1
0x14004e39b  test    r14, r14
0x14004e39e  jz      short loc_14004E3E3
0x14004e3a0  mov     rcx, r14; ho
0x14004e3a3  call    cs:__imp_DeleteObject
0x14004e3a9  jmp     short loc_14004E3E3
0x14004e3ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e3b2  cmp     rcx, r14
0x14004e3b5  jz      short loc_14004E3E3
0x14004e3b7  test    byte ptr [rcx+1Ch], 1
0x14004e3bb  jz      short loc_14004E3E3
0x14004e3bd  cmp     byte ptr [rcx+19h], 2
0x14004e3c1  jb      short loc_14004E3E3
0x14004e3c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004e3c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e3cf  mov     edx, 17h
0x14004e3d4  mov     r9d, eax
0x14004e3d7  mov     r8, r12
  ... truncated ...
```
