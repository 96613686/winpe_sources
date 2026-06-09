# CBrandingBar::PaintBrandingText(HBITMAP__ *,tagBRANDING_BAR_TEXT *)

- ea: `0x14004bd88`
- end: `0x14004c2a1`
- name: `?PaintBrandingText@CBrandingBar@@IEAAHPEAUHBITMAP__@@PEAUtagBRANDING_BAR_TEXT@@@Z`
- size: `1305`
- prototype: `__int64 __fastcall(CBrandingBar *__hidden this, HBITMAP h, struct tagBRANDING_BAR_TEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14004b29c`

## callees

- `0x140008a34`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14001e2f4`
- `0x14004ba80`
- `0x14004bd88`
- `0x14004c2a8`
- `0x1400fa960`
- `0x140111220`

## import_xrefs

- `USER32!DrawTextW` at `0x14004c0d0`
- `USER32!DrawTextW` at `0x14004c0d0`
- `USER32!GetClientRect` at `0x14004bf11`
- `USER32!GetClientRect` at `0x14004bf11`
- `USER32!GetWindowLongPtrW` at `0x14004bde1`
- `USER32!GetWindowLongPtrW` at `0x14004bf44`
- `USER32!GetWindowLongPtrW` at `0x14004bde1`
- `USER32!GetWindowLongPtrW` at `0x14004bf44`
- `msvcrt!_wtol` at `0x14004be63`
- `msvcrt!_wtol` at `0x14004be63`
- `KERNEL32!GetLastError` at `0x14004c0fc`
- `KERNEL32!GetLastError` at `0x14004c0fc`
- `GDI32!SetMapMode` at `0x14004bf02`
- `GDI32!SetMapMode` at `0x14004bf02`
- `GDI32!DeleteDC` at `0x14004c21d`
- `GDI32!DeleteDC` at `0x14004c21d`
- `GDI32!CreateCompatibleDC` at `0x14004beb1`
- `GDI32!CreateCompatibleDC` at `0x14004beb1`
- `GDI32!SetTextColor` at `0x14004bee4`
- `GDI32!SetTextColor` at `0x14004bee4`
- `GDI32!SetBkMode` at `0x14004bef6`
- `GDI32!SetBkMode` at `0x14004bef6`
- `GDI32!SelectObject` at `0x14004bed1`
- `GDI32!SelectObject` at `0x14004c097`
- `GDI32!SelectObject` at `0x14004c0a4`
- `GDI32!SelectObject` at `0x14004c1fe`
- `GDI32!SelectObject` at `0x14004c214`
- `GDI32!SelectObject` at `0x14004bed1`
- `GDI32!SelectObject` at `0x14004c097`
- `GDI32!SelectObject` at `0x14004c0a4`
- `GDI32!SelectObject` at `0x14004c1fe`
- `GDI32!SelectObject` at `0x14004c214`
- `GDI32!DeleteObject` at `0x14004c064`
- `GDI32!DeleteObject` at `0x14004c233`
- `GDI32!DeleteObject` at `0x14004c064`
- `GDI32!DeleteObject` at `0x14004c233`

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
0x14004bd88  mov     [rsp-8+arg_18], rbx
0x14004bd8d  push    rbp
0x14004bd8e  push    rsi
0x14004bd8f  push    rdi
0x14004bd90  push    r12
0x14004bd92  push    r13
0x14004bd94  push    r14
0x14004bd96  push    r15
0x14004bd98  lea     rbp, [rsp-1D0h]
0x14004bda0  sub     rsp, 2D0h
0x14004bda7  mov     rax, cs:__security_cookie
0x14004bdae  xor     rax, rsp
0x14004bdb1  mov     [rbp+200h+var_40], rax
0x14004bdb8  xor     r15d, r15d
0x14004bdbb  mov     rbx, rdx
0x14004bdbe  mov     r13, rcx
0x14004bdc1  mov     [rsp+300h+var_2B8], r15d
0x14004bdc6  mov     rcx, [rcx+8]; hWnd
0x14004bdca  xorps   xmm0, xmm0
0x14004bdcd  xorps   xmm1, xmm1
0x14004bdd0  mov     rdi, r8
0x14004bdd3  lea     edx, [r15-14h]; nIndex
0x14004bdd7  movups  xmmword ptr [rsp+300h+Rect.left], xmm0
0x14004bddc  movups  xmmword ptr [rsp+300h+rc.left], xmm1
0x14004bde1  call    cs:__imp_GetWindowLongPtrW
0x14004bde7  lea     r14, WPP_GLOBAL_Control
0x14004bdee  lea     r12, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004bdf5  bt      rax, 16h
0x14004bdfa  jnb     short loc_14004BE3D
0x14004bdfc  mov     rax, cs:WPP_GLOBAL_Control
0x14004be03  cmp     rax, r14
0x14004be06  jz      short loc_14004BE33
0x14004be08  test    byte ptr [rax+1Ch], 1
0x14004be0c  jz      short loc_14004BE33
0x14004be0e  cmp     byte ptr [rax+19h], 4
0x14004be12  jb      short loc_14004BE33
0x14004be14  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004be19  mov     rcx, cs:WPP_GLOBAL_Control
0x14004be20  lea     edx, [r15+10h]
0x14004be24  mov     r9d, eax
0x14004be27  mov     r8, r12
0x14004be2a  mov     rcx, [rcx+10h]
0x14004be2e  call    WPP_SF_d
0x14004be33  mov     [rsp+300h+var_2C0], 8002h
0x14004be3b  jmp     short loc_14004BE45
0x14004be3d  mov     [rsp+300h+var_2C0], 8000h
0x14004be45  mov     edx, [rdi+0Ch]; unsigned int
0x14004be48  lea     r8, [rbp+200h+String]; unsigned __int16 *
0x14004be4c  mov     rcx, [r13+10h]; HINSTANCE
0x14004be50  mov     r9d, 14h; int
0x14004be56  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14004be5b  test    eax, eax
0x14004be5d  jz      short loc_14004BE6F
0x14004be5f  lea     rcx, [rbp+200h+String]; String
0x14004be63  call    cs:__imp__wtol
0x14004be69  mov     [rsp+300h+var_2BC], eax
0x14004be6d  jmp     short loc_14004BEAF
0x14004be6f  mov     rax, cs:WPP_GLOBAL_Control
0x14004be76  cmp     rax, r14
0x14004be79  jz      short loc_14004BEA7
0x14004be7b  test    byte ptr [rax+1Ch], 1
0x14004be7f  jz      short loc_14004BEA7
0x14004be81  cmp     byte ptr [rax+19h], 2
0x14004be85  jb      short loc_14004BEA7
0x14004be87  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004be8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004be93  mov     edx, 11h
0x14004be98  mov     r9d, eax
0x14004be9b  mov     r8, r12
0x14004be9e  mov     rcx, [rcx+10h]
0x14004bea2  call    WPP_SF_d
0x14004bea7  mov     [rsp+300h+var_2BC], 5
0x14004beaf  xor     ecx, ecx; hdc
0x14004beb1  call    cs:__imp_CreateCompatibleDC
0x14004beb7  mov     rsi, rax
0x14004beba  test    rax, rax
0x14004bebd  jz      loc_14004C23B
0x14004bec3  mov     rdx, rbx; h
0x14004bec6  mov     [rsp+300h+h], r15
0x14004becb  mov     rcx, rax; hdc
0x14004bece  mov     r14, r15
0x14004bed1  call    cs:__imp_SelectObject
0x14004bed7  mov     edx, 993300h; color
0x14004bedc  mov     rcx, rsi; hdc
0x14004bedf  mov     [rsp+300h+var_2A8], rax
0x14004bee4  call    cs:__imp_SetTextColor
0x14004beea  mov     r12d, 1
0x14004bef0  mov     rcx, rsi; hdc
0x14004bef3  mov     edx, r12d; mode
0x14004bef6  call    cs:__imp_SetBkMode
0x14004befc  mov     edx, r12d; iMode
0x14004beff  mov     rcx, rsi; hdc
0x14004bf02  call    cs:__imp_SetMapMode
0x14004bf08  mov     rcx, [r13+8]; hWnd
0x14004bf0c  lea     rdx, [rsp+300h+Rect]; lpRect
0x14004bf11  call    cs:__imp_GetClientRect
0x14004bf17  mov     ebx, [rsp+300h+Rect.right]
0x14004bf1b  mov     rcx, r13; this
0x14004bf1e  cmp     [r13+20h], ebx
0x14004bf22  mov     edx, [rdi+4]; int
0x14004bf25  cmovl   ebx, [r13+20h]
0x14004bf2a  call    ?ScaleForCurrentDpi@CBrandingBar@@IEAAHH@Z; CBrandingBar::ScaleForCurrentDpi(int)
0x14004bf2f  mov     rcx, [r13+8]; hWnd
0x14004bf33  lea     edx, [r12-15h]; nIndex
0x14004bf38  mov     [rsp+300h+rc.top], eax
0x14004bf3c  mov     [rsp+300h+rc.bottom], 64h ; 'd'
0x14004bf44  call    cs:__imp_GetWindowLongPtrW
0x14004bf4a  bt      rax, 16h
0x14004bf4f  jnb     short loc_14004BF58
0x14004bf51  mov     eax, [rdi+8]
0x14004bf54  sub     ebx, [rdi]
0x14004bf56  jmp     short loc_14004BF5D
0x14004bf58  mov     eax, [rdi]
0x14004bf5a  sub     ebx, [rdi+8]
0x14004bf5d  mov     [rsp+300h+rc.right], ebx
0x14004bf61  mov     [rsp+300h+rc.left], eax
0x14004bf65  mov     rax, cs:WPP_GLOBAL_Control
0x14004bf6c  lea     r11, WPP_GLOBAL_Control
0x14004bf73  cmp     rax, r11
0x14004bf76  jz      short loc_14004BFCF
0x14004bf78  test    [rax+1Ch], r12b
0x14004bf7c  jz      short loc_14004BFCF
0x14004bf7e  cmp     byte ptr [rax+19h], 4
0x14004bf82  jb      short loc_14004BFCF
0x14004bf84  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004bf89  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bf90  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004bf97  mov     r9d, eax
0x14004bf9a  mov     edx, 12h
0x14004bf9f  mov     eax, [rsp+300h+rc.bottom]
0x14004bfa3  mov     [rsp+300h+var_2C8], eax
0x14004bfa7  mov     eax, [rsp+300h+rc.right]
0x14004bfab  mov     rcx, [rcx+10h]
0x14004bfaf  mov     [rsp+300h+var_2D0], eax
0x14004bfb3  mov     eax, [rsp+300h+rc.top]
0x14004bfb7  mov     [rsp+300h+var_2D8], eax
0x14004bfbb  mov     eax, [rsp+300h+rc.left]
0x14004bfbf  mov     [rsp+300h+format], eax
0x14004bfc3  call    WPP_SF_Ddddd
0x14004bfc8  lea     r11, WPP_GLOBAL_Control
0x14004bfcf  cmp     r15d, [rdi+10h]
0x14004bfd3  jnb     loc_14004C1EE
0x14004bfd9  mov     eax, r15d
0x14004bfdc  xor     r12d, r12d
0x14004bfdf  lea     rbx, [rax+rax*2]
0x14004bfe3  mov     r8, [rdi+rbx*8+18h]; unsigned __int16 *
0x14004bfe8  test    r8, r8
0x14004bfeb  jz      short loc_14004C03D
0x14004bfed  mov     edx, 104h; unsigned __int64
0x14004bff2  lea     rcx, [rbp+200h+chText]; unsigned __int16 *
0x14004bff6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14004bffb  test    eax, eax
0x14004bffd  jns     short loc_14004C05C
0x14004bfff  mov     rax, cs:WPP_GLOBAL_Control
0x14004c006  cmp     rax, r11
0x14004c009  jz      short loc_14004C05C
0x14004c00b  test    byte ptr [rax+1Ch], 1
0x14004c00f  jz      short loc_14004C05C
0x14004c011  cmp     byte ptr [rax+19h], 2
0x14004c015  jb      short loc_14004C05C
0x14004c017  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004c01c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c023  lea     edx, [r12+13h]
0x14004c028  mov     r9d, eax
0x14004c02b  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004c032  mov     rcx, [rcx+10h]
0x14004c036  call    WPP_SF_d
0x14004c03b  jmp     short loc_14004C05C
0x14004c03d  mov     edx, [rdi+rbx*8+20h]; unsigned int
0x14004c041  lea     r8, [rbp+200h+chText]; unsigned __int16 *
0x14004c045  mov     rcx, [r13+10h]; HINSTANCE
0x14004c049  mov     r9d, 104h; int
0x14004c04f  call    ?TSLoadString@@YAHPEAUHINSTANCE__@@IPEAGH@Z; TSLoadString(HINSTANCE__ *,uint,ushort *,int)
0x14004c054  test    eax, eax
0x14004c056  jz      loc_14004C1A9
0x14004c05c  test    r14, r14
0x14004c05f  jz      short loc_14004C06A
0x14004c061  mov     rcx, r14; ho
0x14004c064  call    cs:__imp_DeleteObject
0x14004c06a  mov     r9d, [rdi+rbx*8+2Ch]; int
0x14004c06f  mov     rcx, r13; this
0x14004c072  mov     r8d, [rdi+rbx*8+28h]; unsigned int
0x14004c077  mov     edx, [rdi+rbx*8+24h]; unsigned int
0x14004c07b  call    ?LoadFontFromResourceInfo@CBrandingBar@@IEAAPEAUHFONT__@@IIH@Z; CBrandingBar::LoadFontFromResourceInfo(uint,uint,int)
0x14004c080  mov     r14, rax
0x14004c083  test    rax, rax
0x14004c086  jz      loc_14004C150
0x14004c08c  mov     rdx, rax; h
0x14004c08f  mov     rcx, rsi; hdc
0x14004c092  test    r15d, r15d
0x14004c095  jnz     short loc_14004C0A4
0x14004c097  call    cs:__imp_SelectObject
0x14004c09d  mov     [rsp+300h+h], rax
0x14004c0a2  jmp     short loc_14004C0AA
0x14004c0a4  call    cs:__imp_SelectObject
0x14004c0aa  lea     rax, [rbp+200h+chText]
0x14004c0ae  or      r8, 0FFFFFFFFFFFFFFFFh
0x14004c0b2  inc     r8; cchText
0x14004c0b5  cmp     [rax+r8*2], r12w
0x14004c0ba  jnz     short loc_14004C0B2
0x14004c0bc  mov     eax, [rsp+300h+var_2C0]
0x14004c0c0  lea     r9, [rsp+300h+rc]; lprc
0x14004c0c5  lea     rdx, [rbp+200h+chText]; lpchText
0x14004c0c9  mov     [rsp+300h+format], eax; format
0x14004c0cd  mov     rcx, rsi; hdc
0x14004c0d0  call    cs:__imp_DrawTextW
0x14004c0d6  mov     r12d, eax
0x14004c0d9  test    eax, eax
0x14004c0db  jnz     short loc_14004C12C
0x14004c0dd  mov     rax, cs:WPP_GLOBAL_Control
0x14004c0e4  lea     r11, WPP_GLOBAL_Control
0x14004c0eb  cmp     rax, r11
0x14004c0ee  jz      short loc_14004C133
0x14004c0f0  test    byte ptr [rax+1Ch], 1
0x14004c0f4  jz      short loc_14004C133
0x14004c0f6  cmp     byte ptr [rax+19h], 2
0x14004c0fa  jb      short loc_14004C133
0x14004c0fc  call    cs:__imp_GetLastError
0x14004c102  mov     ebx, eax
0x14004c104  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004c109  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c110  lea     edx, [r12+16h]
0x14004c115  mov     r9d, eax
0x14004c118  mov     [rsp+300h+format], ebx
0x14004c11c  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004c123  mov     rcx, [rcx+10h]
0x14004c127  call    WPP_SF_Dd
0x14004c12c  lea     r11, WPP_GLOBAL_Control
0x14004c133  mov     eax, r12d
0x14004c136  sub     r12d, [rsp+300h+var_2BC]
0x14004c13b  sub     eax, [rsp+300h+var_2BC]
0x14004c13f  add     [rsp+300h+rc.top], eax
0x14004c143  add     [rsp+300h+rc.bottom], r12d
0x14004c148  inc     r15d
0x14004c14b  jmp     loc_14004BFCF
0x14004c150  mov     rax, cs:WPP_GLOBAL_Control
0x14004c157  lea     rcx, WPP_GLOBAL_Control
0x14004c15e  cmp     rax, rcx
0x14004c161  jz      loc_14004C273
0x14004c167  test    byte ptr [rax+1Ch], 1
0x14004c16b  jz      loc_14004C273
0x14004c171  cmp     byte ptr [rax+19h], 2
0x14004c175  jb      loc_14004C273
0x14004c17b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004c180  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c187  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004c18e  mov     edx, 15h
0x14004c193  mov     [rsp+300h+format], r15d
0x14004c198  mov     r9d, eax
0x14004c19b  mov     rcx, [rcx+10h]
0x14004c19f  call    WPP_SF_Dd
0x14004c1a4  jmp     loc_14004C273
0x14004c1a9  mov     rax, cs:WPP_GLOBAL_Control
0x14004c1b0  lea     rcx, WPP_GLOBAL_Control
0x14004c1b7  cmp     rax, rcx
0x14004c1ba  jz      short loc_14004C22B
0x14004c1bc  test    byte ptr [rax+1Ch], 1
0x14004c1c0  jz      short loc_14004C22B
0x14004c1c2  cmp     byte ptr [rax+19h], 2
0x14004c1c6  jb      short loc_14004C22B
0x14004c1c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004c1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c1d4  lea     r8, WPP_1af8da3092413da1a7897833402d1c53_Traceguids
0x14004c1db  mov     edx, 14h
0x14004c1e0  mov     r9d, eax
0x14004c1e3  mov     rcx, [rcx+10h]
0x14004c1e7  call    WPP_SF_d
0x14004c1ec  jmp     short loc_14004C22B
0x14004c1ee  mov     r12, [rsp+300h+h]
0x14004c1f3  test    r12, r12
0x14004c1f6  jz      short loc_14004C204
0x14004c1f8  mov     rdx, r12; h
0x14004c1fb  mov     rcx, rsi; hdc
0x14004c1fe  call    cs:__imp_SelectObject
0x14004c204  mov     rax, [rsp+300h+var_2A8]
0x14004c209  test    rax, rax
0x14004c20c  jz      short loc_14004C21A
0x14004c20e  mov     rdx, rax; h
0x14004c211  mov     rcx, rsi; hdc
0x14004c214  call    cs:__imp_SelectObject
0x14004c21a  mov     rcx, rsi; hdc
0x14004c21d  call    cs:__imp_DeleteDC
0x14004c223  mov     [rsp+300h+var_2B8], 1
0x14004c22b  test    r14, r14
0x14004c22e  jz      short loc_14004C273
0x14004c230  mov     rcx, r14; ho
0x14004c233  call    cs:__imp_DeleteObject
0x14004c239  jmp     short loc_14004C273
0x14004c23b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c242  cmp     rcx, r14
0x14004c245  jz      short loc_14004C273
0x14004c247  test    byte ptr [rcx+1Ch], 1
0x14004c24b  jz      short loc_14004C273
0x14004c24d  cmp     byte ptr [rcx+19h], 2
0x14004c251  jb      short loc_14004C273
0x14004c253  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004c258  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c25f  mov     edx, 17h
0x14004c264  mov     r9d, eax
0x14004c267  mov     r8, r12
  ... truncated ...
```
