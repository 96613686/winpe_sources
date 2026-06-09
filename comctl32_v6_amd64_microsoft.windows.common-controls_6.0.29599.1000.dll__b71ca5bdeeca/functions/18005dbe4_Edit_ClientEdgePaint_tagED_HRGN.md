# Edit_ClientEdgePaint(tagED *,HRGN__ *)

- ea: `0x18005dbe4`
- end: `0x18005e05d`
- name: `?Edit_ClientEdgePaint@@YAHPEAUtagED@@PEAUHRGN__@@@Z`
- size: `1145`
- prototype: `__int64 __fastcall(struct tagED *, HRGN)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180059720`

## callees

- `0x18005c9f4`
- `0x18005dbe4`
- `0x18005e114`
- `0x18005ea8c`
- `0x180106414`
- `0x180114520`

## import_xrefs

- `GDI32!DeleteObject` at `0x18005deff`
- `GDI32!DeleteObject` at `0x18005deff`
- `GDI32!CombineRgn` at `0x18005e052`
- `GDI32!CombineRgn` at `0x18005e052`
- `GDI32!ExcludeClipRect` at `0x18005df5c`
- `GDI32!ExcludeClipRect` at `0x18005df5c`
- `GDI32!CreateRectRgn` at `0x18005ded1`
- `GDI32!CreateRectRgn` at `0x18005ded1`
- `USER32!GetDCEx` at `0x18005dc2b`
- `USER32!GetDCEx` at `0x18005dc2b`
- `USER32!OffsetRect` at `0x18005dc81`
- `USER32!OffsetRect` at `0x18005dc81`
- `USER32!CopyRect` at `0x18005dd39`
- `USER32!CopyRect` at `0x18005dd39`
- `USER32!IsWindowEnabled` at `0x18005dcbb`
- `USER32!IsWindowEnabled` at `0x18005dcbb`
- `USER32!DefWindowProcW` at `0x18005def6`
- `USER32!DefWindowProcW` at `0x18005def6`
- `USER32!GetWindowRect` at `0x18005dc6b`
- `USER32!GetWindowRect` at `0x18005de92`
- `USER32!GetWindowRect` at `0x18005dc6b`
- `USER32!GetWindowRect` at `0x18005de92`
- `USER32!InflateRect` at `0x18005dd64`
- `USER32!InflateRect` at `0x18005debd`
- `USER32!InflateRect` at `0x18005dd64`
- `USER32!InflateRect` at `0x18005debd`
- `USER32!GetSystemMetrics` at `0x18005dd44`
- `USER32!GetSystemMetrics` at `0x18005dd53`
- `USER32!GetSystemMetrics` at `0x18005de9d`
- `USER32!GetSystemMetrics` at `0x18005deac`
- `USER32!GetSystemMetrics` at `0x18005df94`
- `USER32!GetSystemMetrics` at `0x18005dfa2`
- `USER32!GetSystemMetrics` at `0x18005dd44`
- `USER32!GetSystemMetrics` at `0x18005dd53`
- `USER32!GetSystemMetrics` at `0x18005de9d`
- `USER32!GetSystemMetrics` at `0x18005deac`
- `USER32!GetSystemMetrics` at `0x18005df94`
- `USER32!GetSystemMetrics` at `0x18005dfa2`
- `USER32!ReleaseDC` at `0x18005df0c`
- `USER32!ReleaseDC` at `0x18005df0c`
- `UxTheme!GetThemeMargins` at `0x18005dcfc`
- `UxTheme!GetThemeMargins` at `0x18005dcfc`
- `UxTheme!EndBufferedAnimation` at `0x18005de84`
- `UxTheme!EndBufferedAnimation` at `0x18005de84`
- `UxTheme!BeginBufferedAnimation` at `0x18005de28`
- `UxTheme!BeginBufferedAnimation` at `0x18005de28`
- `UxTheme!BufferedPaintRenderAnimation` at `0x18005dd92`
- `UxTheme!BufferedPaintRenderAnimation` at `0x18005dd92`
- `UxTheme!BufferedPaintInit` at `0x18005e00b`
- `UxTheme!BufferedPaintInit` at `0x18005e00b`

## pseudocode

```c
__int64 __fastcall Edit_ClientEdgePaint(struct tagED *a1, HRGN a2)
{
  unsigned int v2; // r13d
  HWND v4; // rcx
  DWORD v5; // r8d
  HDC DCEx; // rax
  HDC v7; // r15
  HWND v8; // rcx
  __int64 v9; // rax
  int v10; // ecx
  int v11; // esi
  int v12; // r14d
  int cyTopHeight; // r12d
  int v14; // ebx
  int v15; // eax
  DWORD v16; // eax
  HWND v17; // rcx
  int v18; // ebx
  int v19; // eax
  HRGN RectRgn; // rax
  HRGN v21; // rbx
  int SystemMetrics; // [rsp+40h] [rbp-69h]
  HBRUSH Brush; // [rsp+48h] [rbp-61h]
  HANIMATIONBUFFER hbpAnimation; // [rsp+50h] [rbp-59h]
  struct tagRECT Rect; // [rsp+60h] [rbp-49h] BYREF
  HDC phdcFrom; // [rsp+70h] [rbp-39h] BYREF
  HDC phdcTo; // [rsp+78h] [rbp-31h] BYREF
  BP_PAINTPARAMS pPaintParams; // [rsp+80h] [rbp-29h] BYREF
  struct tagRECT rcDst; // [rsp+98h] [rbp-11h] BYREF
  MARGINS pMargins; // [rsp+A8h] [rbp-1h] BYREF
  BP_ANIMATIONPARAMS pAnimationParams; // [rsp+B8h] [rbp+Fh] BYREF

  v2 = 0;
  v4 = (HWND)*((_QWORD *)a1 + 8);
  if ( a2 )
    v5 = 328833;
  else
    v5 = 66561;
  DCEx = GetDCEx(v4, a2, v5);
  v7 = DCEx;
  if ( DCEx )
  {
    Brush = Edit_GetBrush(a1, DCEx);
    if ( !Brush )
    {
LABEL_30:
      ReleaseDC(*((HWND *)a1 + 8), v7);
      return v2;
    }
    v8 = (HWND)*((_QWORD *)a1 + 8);
    Rect = 0;
    pMargins = 0;
    GetWindowRect(v8, &Rect);
    OffsetRect(&Rect, -Rect.left, -Rect.top);
    if ( !a1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v9 = *((_QWORD *)a1 + 46);
    v10 = *(_DWORD *)(v9 + 12) & 0x200000;
    if ( (*(_DWORD *)(v9 + 12) & 0x100000) != 0 )
      v11 = v10 != 0 ? 9 : 7;
    else
      v11 = v10 != 0 ? 8 : 6;
    v2 = 1;
    if ( IsWindowEnabled(*((HWND *)a1 + 8)) )
    {
      if ( (*((_BYTE *)a1 + 116) & 8) != 0 )
        v12 = 3;
      else
        v12 = ((*((_BYTE *)a1 + 400) & 1) != 0) + 1;
    }
    else
    {
      v12 = 4;
    }
    if ( GetThemeMargins(*((HTHEME *)a1 + 45), 0, v11, v12, 3601, 0, &pMargins) < 0 )
    {
      SystemMetrics = GetSystemMetrics(5);
      cyTopHeight = GetSystemMetrics(6);
    }
    else
    {
      if ( pMargins.cxLeftWidth != pMargins.cxRightWidth )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      cyTopHeight = pMargins.cyTopHeight;
      if ( pMargins.cyTopHeight != pMargins.cyBottomHeight )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        cyTopHeight = pMargins.cyTopHeight;
      }
      SystemMetrics = pMargins.cxLeftWidth;
    }
    rcDst = 0;
    CopyRect(&rcDst, &Rect);
    v14 = -GetSystemMetrics(46);
    v15 = GetSystemMetrics(45);
    InflateRect(&rcDst, -v15, v14);
    if ( (*(_DWORD *)(*((_QWORD *)a1 + 46) + 12LL) & 0x300000) != 0 )
      goto LABEL_33;
    if ( (*((_BYTE *)a1 + 404) & 4) == 0 )
    {
      BufferedPaintInit();
      *((_BYTE *)a1 + 404) |= 4u;
    }
    if ( BufferedPaintRenderAnimation(*((HWND *)a1 + 8), v7) )
      goto LABEL_27;
    v16 = Edit_SoftFadeDuration(*((HTHEME *)a1 + 45), v11, *((_DWORD *)a1 + 144), v12);
    pAnimationParams.cbSize = 16;
    pAnimationParams.dwFlags = 0;
    pAnimationParams.style = BPAS_LINEAR;
    pAnimationParams.dwDuration = v16;
    phdcFrom = 0;
    memset(&pPaintParams.dwFlags, 0, 20);
    phdcTo = 0;
    v17 = (HWND)*((_QWORD *)a1 + 8);
    pPaintParams.prcExclude = &rcDst;
    pPaintParams.cbSize = 24;
    pPaintParams.dwFlags = 4;
    hbpAnimation = BeginBufferedAnimation(
                     v17,
                     v7,
                     &Rect,
                     BPBF_COMPATIBLEBITMAP,
                     &pPaintParams,
                     &pAnimationParams,
                     &phdcFrom,
                     &phdcTo);
    if ( !hbpAnimation )
    {
LABEL_33:
      ExcludeClipRect(v7, rcDst.left, rcDst.top, rcDst.right, rcDst.bottom);
      Edit_ClientEdgePaintImpl(a1, v7, Brush, &Rect, v11, v12, SystemMetrics, cyTopHeight);
    }
    else
    {
      if ( phdcFrom )
        Edit_ClientEdgePaintImpl(a1, phdcFrom, Brush, &Rect, v11, *((_DWORD *)a1 + 144), SystemMetrics, cyTopHeight);
      if ( phdcTo )
        Edit_ClientEdgePaintImpl(a1, phdcTo, Brush, &Rect, v11, v12, SystemMetrics, cyTopHeight);
      *((_DWORD *)a1 + 144) = v12;
      EndBufferedAnimation(hbpAnimation, 1);
    }
LABEL_27:
    GetWindowRect(*((HWND *)a1 + 8), &Rect);
    v18 = -GetSystemMetrics(46);
    v19 = GetSystemMetrics(45);
    InflateRect(&Rect, -v19, v18);
    RectRgn = CreateRectRgn(Rect.left, Rect.top, Rect.right, Rect.bottom);
    v21 = RectRgn;
    if ( a2 )
      CombineRgn(RectRgn, a2, RectRgn, 1);
    DefWindowProcW(*((HWND *)a1 + 8), 0x85u, (WPARAM)v21, 0);
    DeleteObject(v21);
    goto LABEL_30;
  }
  return v2;
}

```

## disassembly

```asm
0x18005dbe4  mov     [rsp-8+arg_10], rbx
0x18005dbe9  push    rbp
0x18005dbea  push    rsi
0x18005dbeb  push    rdi
0x18005dbec  push    r12
0x18005dbee  push    r13
0x18005dbf0  push    r14
0x18005dbf2  push    r15
0x18005dbf4  lea     rbp, [rsp-27h]
0x18005dbf9  sub     rsp, 0D0h
0x18005dc00  mov     rax, cs:__security_cookie
0x18005dc07  xor     rax, rsp
0x18005dc0a  mov     [rbp+57h+var_38], rax
0x18005dc0e  xor     r13d, r13d
0x18005dc11  mov     [rbp+57h+hrgnSrc1], rdx
0x18005dc15  mov     rdi, rcx
0x18005dc18  mov     rcx, [rcx+40h]; hWnd
0x18005dc1c  test    rdx, rdx
0x18005dc1f  jz      loc_18005DF3C
0x18005dc25  mov     r8d, 50481h; flags
0x18005dc2b  call    cs:__imp_GetDCEx
0x18005dc31  mov     r15, rax
0x18005dc34  test    rax, rax
0x18005dc37  jz      loc_18005DF12
0x18005dc3d  mov     rdx, rax; HDC
0x18005dc40  mov     rcx, rdi; struct tagED *
0x18005dc43  call    ?Edit_GetBrush@@YAPEAUHBRUSH__@@PEAUtagED@@PEAUHDC__@@@Z; Edit_GetBrush(tagED *,HDC__ *)
0x18005dc48  mov     [rbp+57h+var_B8], rax
0x18005dc4c  test    rax, rax
0x18005dc4f  jz      loc_18005DF05
0x18005dc55  mov     rcx, [rdi+40h]; hWnd
0x18005dc59  lea     rdx, [rbp+57h+Rect]; lpRect
0x18005dc5d  xorps   xmm0, xmm0
0x18005dc60  xorps   xmm1, xmm1
0x18005dc63  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18005dc67  movups  xmmword ptr [rbp+57h+var_58.cxLeftWidth], xmm1
0x18005dc6b  call    cs:__imp_GetWindowRect
0x18005dc71  mov     r8d, [rbp+57h+Rect.top]
0x18005dc75  lea     rcx, [rbp+57h+Rect]; lprc
0x18005dc79  mov     edx, [rbp+57h+Rect.left]
0x18005dc7c  neg     r8d; dy
0x18005dc7f  neg     edx; dx
0x18005dc81  call    cs:__imp_OffsetRect
0x18005dc87  test    rdi, rdi
0x18005dc8a  jz      loc_18005DFB0
0x18005dc90  mov     rax, [rdi+170h]
0x18005dc97  mov     ecx, [rax+0Ch]
0x18005dc9a  and     ecx, 200000h
0x18005dca0  test    dword ptr [rax+0Ch], 100000h
0x18005dca7  jnz     loc_18005DFBA
0x18005dcad  neg     ecx
0x18005dcaf  sbb     esi, esi
0x18005dcb1  and     esi, 2
0x18005dcb4  add     esi, 6
0x18005dcb7  mov     rcx, [rdi+40h]; hWnd
0x18005dcbb  call    cs:__imp_IsWindowEnabled
0x18005dcc1  mov     r13d, 1
0x18005dcc7  test    eax, eax
0x18005dcc9  jnz     loc_18005DFC9
0x18005dccf  lea     r14d, [r13+3]
0x18005dcd3  mov     rcx, [rdi+168h]; hTheme
0x18005dcda  lea     rax, [rbp+57h+var_58]
0x18005dcde  mov     [rsp+100h+pMargins], rax; pMargins
0x18005dce3  mov     r9d, r14d; iStateId
0x18005dce6  mov     [rsp+100h+prc], 0; prc
0x18005dcef  mov     r8d, esi; iPartId
0x18005dcf2  xor     edx, edx; hdc
0x18005dcf4  mov     [rsp+100h+iPropId], 0E11h; iPropId
0x18005dcfc  call    cs:__imp_GetThemeMargins
0x18005dd02  test    eax, eax
0x18005dd04  js      loc_18005DF8F
0x18005dd0a  mov     eax, [rbp+57h+var_58.cxRightWidth]
0x18005dd0d  cmp     [rbp+57h+var_58.cxLeftWidth], eax
0x18005dd10  jnz     loc_18005DFF3
0x18005dd16  mov     r12d, [rbp+57h+var_58.cyTopHeight]
0x18005dd1a  cmp     r12d, [rbp+57h+var_58.cyBottomHeight]
0x18005dd1e  jnz     loc_18005DFFD
0x18005dd24  mov     eax, [rbp+57h+var_58.cxLeftWidth]
0x18005dd27  mov     [rbp+57h+var_C0], eax
0x18005dd2a  xorps   xmm0, xmm0
0x18005dd2d  lea     rdx, [rbp+57h+Rect]; lprcSrc
0x18005dd31  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18005dd35  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x18005dd39  call    cs:__imp_CopyRect
0x18005dd3f  mov     ecx, 2Eh ; '.'; nIndex
0x18005dd44  call    cs:__imp_GetSystemMetrics
0x18005dd4a  mov     ebx, eax
0x18005dd4c  mov     ecx, 2Dh ; '-'; nIndex
0x18005dd51  neg     ebx
0x18005dd53  call    cs:__imp_GetSystemMetrics
0x18005dd59  mov     r8d, ebx; dy
0x18005dd5c  lea     rcx, [rbp+57h+rcDst]; lprc
0x18005dd60  neg     eax
0x18005dd62  mov     edx, eax; dx
0x18005dd64  call    cs:__imp_InflateRect
0x18005dd6a  mov     rax, [rdi+170h]
0x18005dd71  test    dword ptr [rax+0Ch], 300000h
0x18005dd78  jnz     loc_18005DF47
0x18005dd7e  test    byte ptr [rdi+194h], 4
0x18005dd85  jz      loc_18005E00B
0x18005dd8b  mov     rcx, [rdi+40h]; hwnd
0x18005dd8f  mov     rdx, r15; hdcTarget
0x18005dd92  call    cs:__imp_BufferedPaintRenderAnimation
0x18005dd98  test    eax, eax
0x18005dd9a  jnz     loc_18005DE8A
0x18005dda0  mov     r8d, [rdi+240h]; int
0x18005dda7  mov     r9d, r14d; int
0x18005ddaa  mov     rcx, [rdi+168h]; hTheme
0x18005ddb1  mov     edx, esi; iPartId
0x18005ddb3  call    ?Edit_SoftFadeDuration@@YAKPEAXHHH@Z; Edit_SoftFadeDuration(void *,int,int,int)
0x18005ddb8  xor     ecx, ecx
0x18005ddba  mov     [rbp+57h+pAnimationParams.cbSize], 10h
0x18005ddc1  mov     qword ptr [rbp+57h+pAnimationParams.dwFlags], rcx
0x18005ddc5  lea     r8, [rbp+57h+Rect]; prcTarget
0x18005ddc9  mov     qword ptr [rbp+57h+pAnimationParams.style], r13
0x18005ddcd  xorps   xmm0, xmm0
0x18005ddd0  mov     [rbp+57h+pAnimationParams.dwDuration], eax
0x18005ddd3  xor     r9d, r9d; dwFormat
0x18005ddd6  xor     eax, eax
0x18005ddd8  mov     [rbp+57h+phdcFrom], rcx
0x18005dddc  mov     dword ptr [rbp+57h+pPaintParams.pBlendFunction+4], eax
0x18005dddf  mov     rdx, r15; hdcTarget
0x18005dde2  movups  xmmword ptr [rbp+57h+pPaintParams.dwFlags], xmm0
0x18005dde6  lea     rax, [rbp+57h+rcDst]
0x18005ddea  mov     [rbp+57h+var_88], rcx
0x18005ddee  mov     rcx, [rdi+40h]; hwnd
0x18005ddf2  mov     [rbp+57h+pPaintParams.prcExclude], rax
0x18005ddf6  lea     rax, [rbp+57h+var_88]
0x18005ddfa  mov     [rsp+100h+phdcTo], rax; phdcTo
0x18005ddff  lea     rax, [rbp+57h+phdcFrom]
0x18005de03  mov     [rsp+100h+pMargins], rax; phdcFrom
0x18005de08  lea     rax, [rbp+57h+pAnimationParams]
0x18005de0c  mov     [rsp+100h+prc], rax; pAnimationParams
0x18005de11  lea     rax, [rbp+57h+pPaintParams]
0x18005de15  mov     qword ptr [rsp+100h+iPropId], rax; pPaintParams
0x18005de1a  mov     [rbp+57h+pPaintParams.cbSize], 18h
0x18005de21  mov     [rbp+57h+pPaintParams.dwFlags], 4
0x18005de28  call    cs:__imp_BeginBufferedAnimation
0x18005de2e  mov     [rbp+57h+hbpAnimation], rax
0x18005de32  test    rax, rax
0x18005de35  jz      loc_18005DF47
0x18005de3b  mov     rdx, [rbp+57h+phdcFrom]; HDC
0x18005de3f  mov     ebx, [rbp+57h+var_C0]
0x18005de42  test    rdx, rdx
0x18005de45  jnz     loc_18005E01D
0x18005de4b  mov     rdx, [rbp+57h+var_88]; HDC
0x18005de4f  test    rdx, rdx
0x18005de52  jz      short loc_18005DE76
0x18005de54  mov     r8, [rbp+57h+var_B8]; HBRUSH
0x18005de58  lea     r9, [rbp+57h+Rect]; struct tagRECT *
0x18005de5c  mov     dword ptr [rsp+100h+phdcTo], r12d; int
0x18005de61  mov     rcx, rdi; struct tagED *
0x18005de64  mov     dword ptr [rsp+100h+pMargins], ebx; int
0x18005de68  mov     dword ptr [rsp+100h+prc], r14d; int
0x18005de6d  mov     [rsp+100h+iPropId], esi; int
0x18005de71  call    ?Edit_ClientEdgePaintImpl@@YAXPEAUtagED@@PEAUHDC__@@PEAUHBRUSH__@@AEBUtagRECT@@HHHH@Z; Edit_ClientEdgePaintImpl(tagED *,HDC__ *,HBRUSH__ *,tagRECT const &,int,int,int,int)
0x18005de76  mov     rcx, [rbp+57h+hbpAnimation]; hbpAnimation
0x18005de7a  mov     edx, r13d; fUpdateTarget
0x18005de7d  mov     [rdi+240h], r14d
0x18005de84  call    cs:__imp_EndBufferedAnimation
0x18005de8a  mov     rcx, [rdi+40h]; hWnd
0x18005de8e  lea     rdx, [rbp+57h+Rect]; lpRect
0x18005de92  call    cs:__imp_GetWindowRect
0x18005de98  mov     ecx, 2Eh ; '.'; nIndex
0x18005de9d  call    cs:__imp_GetSystemMetrics
0x18005dea3  mov     ebx, eax
0x18005dea5  mov     ecx, 2Dh ; '-'; nIndex
0x18005deaa  neg     ebx
0x18005deac  call    cs:__imp_GetSystemMetrics
0x18005deb2  mov     r8d, ebx; dy
0x18005deb5  lea     rcx, [rbp+57h+Rect]; lprc
0x18005deb9  neg     eax
0x18005debb  mov     edx, eax; dx
0x18005debd  call    cs:__imp_InflateRect
0x18005dec3  mov     r9d, [rbp+57h+Rect.bottom]; y2
0x18005dec7  mov     r8d, [rbp+57h+Rect.right]; x2
0x18005decb  mov     edx, [rbp+57h+Rect.top]; y1
0x18005dece  mov     ecx, [rbp+57h+Rect.left]; x1
0x18005ded1  call    cs:__imp_CreateRectRgn
0x18005ded7  mov     rdx, [rbp+57h+hrgnSrc1]; hrgnSrc1
0x18005dedb  mov     rbx, rax
0x18005dede  test    rdx, rdx
0x18005dee1  jnz     loc_18005E049
0x18005dee7  mov     rcx, [rdi+40h]; hWnd
0x18005deeb  xor     r9d, r9d; lParam
0x18005deee  mov     r8, rbx; wParam
0x18005def1  mov     edx, 85h; Msg
0x18005def6  call    cs:__imp_DefWindowProcW
0x18005defc  mov     rcx, rbx; ho
0x18005deff  call    cs:__imp_DeleteObject
0x18005df05  mov     rcx, [rdi+40h]; hWnd
0x18005df09  mov     rdx, r15; hDC
0x18005df0c  call    cs:__imp_ReleaseDC
0x18005df12  mov     eax, r13d
0x18005df15  mov     rcx, [rbp+57h+var_38]
0x18005df19  xor     rcx, rsp; StackCookie
0x18005df1c  call    __security_check_cookie
0x18005df21  mov     rbx, [rsp+100h+arg_10]
0x18005df29  add     rsp, 0D0h
0x18005df30  pop     r15
0x18005df32  pop     r14
0x18005df34  pop     r13
0x18005df36  pop     r12
0x18005df38  pop     rdi
0x18005df39  pop     rsi
0x18005df3a  pop     rbp
0x18005df3b  retn
0x18005df3c  mov     r8d, 10401h
0x18005df42  jmp     loc_18005DC2B
0x18005df47  mov     eax, [rbp+57h+rcDst.bottom]
0x18005df4a  mov     rcx, r15; hdc
0x18005df4d  mov     r9d, [rbp+57h+rcDst.right]; right
0x18005df51  mov     r8d, [rbp+57h+rcDst.top]; top
0x18005df55  mov     edx, [rbp+57h+rcDst.left]; left
0x18005df58  mov     [rsp+100h+iPropId], eax; bottom
0x18005df5c  call    cs:__imp_ExcludeClipRect
0x18005df62  mov     ebx, [rbp+57h+var_C0]
0x18005df65  lea     r9, [rbp+57h+Rect]; struct tagRECT *
0x18005df69  mov     r8, [rbp+57h+var_B8]; HBRUSH
0x18005df6d  mov     rdx, r15; HDC
0x18005df70  mov     dword ptr [rsp+100h+phdcTo], r12d; int
0x18005df75  mov     rcx, rdi; struct tagED *
0x18005df78  mov     dword ptr [rsp+100h+pMargins], ebx; int
0x18005df7c  mov     dword ptr [rsp+100h+prc], r14d; int
0x18005df81  mov     [rsp+100h+iPropId], esi; int
0x18005df85  call    ?Edit_ClientEdgePaintImpl@@YAXPEAUtagED@@PEAUHDC__@@PEAUHBRUSH__@@AEBUtagRECT@@HHHH@Z; Edit_ClientEdgePaintImpl(tagED *,HDC__ *,HBRUSH__ *,tagRECT const &,int,int,int,int)
0x18005df8a  jmp     loc_18005DE8A
0x18005df8f  mov     ecx, 5; nIndex
0x18005df94  call    cs:__imp_GetSystemMetrics
0x18005df9a  mov     ecx, 6; nIndex
0x18005df9f  mov     [rbp+57h+var_C0], eax
0x18005dfa2  call    cs:__imp_GetSystemMetrics
0x18005dfa8  mov     r12d, eax
0x18005dfab  jmp     loc_18005DD2A
0x18005dfb0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005dfb5  jmp     loc_18005DC90
0x18005dfba  neg     ecx
0x18005dfbc  sbb     esi, esi
0x18005dfbe  and     esi, 2
0x18005dfc1  add     esi, 7
0x18005dfc4  jmp     loc_18005DCB7
0x18005dfc9  test    byte ptr [rdi+74h], 8
0x18005dfcd  jz      short loc_18005DFDA
0x18005dfcf  mov     r14d, 3
0x18005dfd5  jmp     loc_18005DCD3
0x18005dfda  mov     al, [rdi+190h]
0x18005dfe0  and     al, r13b
0x18005dfe3  neg     al
0x18005dfe5  sbb     r14d, r14d
0x18005dfe8  neg     r14d
0x18005dfeb  add     r14d, r13d
0x18005dfee  jmp     loc_18005DCD3
0x18005dff3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005dff8  jmp     loc_18005DD16
0x18005dffd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005e002  mov     r12d, [rbp+57h+var_58.cyTopHeight]
0x18005e006  jmp     loc_18005DD24
0x18005e00b  call    cs:__imp_BufferedPaintInit
0x18005e011  or      byte ptr [rdi+194h], 4
0x18005e018  jmp     loc_18005DD8B
0x18005e01d  mov     eax, [rdi+240h]
0x18005e023  lea     r9, [rbp+57h+Rect]; struct tagRECT *
0x18005e027  mov     r8, [rbp+57h+var_B8]; HBRUSH
0x18005e02b  mov     rcx, rdi; struct tagED *
0x18005e02e  mov     dword ptr [rsp+100h+phdcTo], r12d; int
0x18005e033  mov     dword ptr [rsp+100h+pMargins], ebx; int
0x18005e037  mov     dword ptr [rsp+100h+prc], eax; int
0x18005e03b  mov     [rsp+100h+iPropId], esi; int
0x18005e03f  call    ?Edit_ClientEdgePaintImpl@@YAXPEAUtagED@@PEAUHDC__@@PEAUHBRUSH__@@AEBUtagRECT@@HHHH@Z; Edit_ClientEdgePaintImpl(tagED *,HDC__ *,HBRUSH__ *,tagRECT const &,int,int,int,int)
0x18005e044  jmp     loc_18005DE4B
0x18005e049  mov     r9d, r13d; iMode
0x18005e04c  mov     r8, rbx; hrgnSrc2
0x18005e04f  mov     rcx, rbx; hrgnDst
0x18005e052  call    cs:__imp_CombineRgn
0x18005e058  jmp     loc_18005DEE7
```
