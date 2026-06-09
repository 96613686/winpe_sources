# CDatePicker::_LBD_MonthCal(int)

- ea: `0x1801528e0`
- end: `0x180152d94`
- name: `?_LBD_MonthCal@CDatePicker@@AEAAXH@Z`
- size: `1204`
- prototype: `void __fastcall(CDatePicker *__hidden this, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800497f4`
- `0x180151ec8`
- `0x180152d9c`

## callees

- `0x180022b28`
- `0x180036850`
- `0x180114520`
- `0x180150c28`
- `0x1801528e0`
- `0x180152f3c`
- `0x180153fa4`
- `0x180154310`
- `0x18015447c`
- `0x1801c2c68`

## import_xrefs

- `api-ms-win-core-calendar-l1-1-0!ConvertCalDateTimeToSystemTime` at `0x180152b7f`
- `api-ms-win-core-calendar-l1-1-0!ConvertCalDateTimeToSystemTime` at `0x180152b90`
- `api-ms-win-core-calendar-l1-1-0!ConvertCalDateTimeToSystemTime` at `0x180152bc6`
- `api-ms-win-core-calendar-l1-1-0!ConvertCalDateTimeToSystemTime` at `0x180152b7f`
- `api-ms-win-core-calendar-l1-1-0!ConvertCalDateTimeToSystemTime` at `0x180152b90`
- `api-ms-win-core-calendar-l1-1-0!ConvertCalDateTimeToSystemTime` at `0x180152bc6`
- `USER32!AdjustWindowRectEx` at `0x180152c4d`
- `USER32!AdjustWindowRectEx` at `0x180152c4d`
- `USER32!MapWindowPoints` at `0x18015299d`
- `USER32!MapWindowPoints` at `0x18015299d`
- `USER32!MoveWindow` at `0x180152c8a`
- `USER32!MoveWindow` at `0x180152cef`
- `USER32!MoveWindow` at `0x180152c8a`
- `USER32!MoveWindow` at `0x180152cef`
- `USER32!DestroyWindow` at `0x180152d67`
- `USER32!DestroyWindow` at `0x180152d67`
- `USER32!SendMessageW` at `0x180152a66`
- `USER32!SendMessageW` at `0x180152ae3`
- `USER32!SendMessageW` at `0x180152b1c`
- `USER32!SendMessageW` at `0x180152b4c`
- `USER32!SendMessageW` at `0x180152ba9`
- `USER32!SendMessageW` at `0x180152bdf`
- `USER32!SendMessageW` at `0x180152bff`
- `USER32!SendMessageW` at `0x180152c17`
- `USER32!SendMessageW` at `0x180152d29`
- `USER32!SendMessageW` at `0x180152d40`
- `USER32!SendMessageW` at `0x180152a66`
- `USER32!SendMessageW` at `0x180152ae3`
- `USER32!SendMessageW` at `0x180152b1c`
- `USER32!SendMessageW` at `0x180152b4c`
- `USER32!SendMessageW` at `0x180152ba9`
- `USER32!SendMessageW` at `0x180152bdf`
- `USER32!SendMessageW` at `0x180152bff`
- `USER32!SendMessageW` at `0x180152c17`
- `USER32!SendMessageW` at `0x180152d29`
- `USER32!SendMessageW` at `0x180152d40`
- `USER32!GetClientRect` at `0x180152cb2`
- `USER32!GetClientRect` at `0x180152cb2`
- `USER32!InvalidateRect` at `0x18015293d`
- `USER32!InvalidateRect` at `0x180152971`
- `USER32!InvalidateRect` at `0x180152d53`
- `USER32!InvalidateRect` at `0x18015293d`
- `USER32!InvalidateRect` at `0x180152971`
- `USER32!InvalidateRect` at `0x180152d53`

## pseudocode

```c
void __fastcall CDatePicker::_LBD_MonthCal(CDatePicker *this)
{
  int v2; // eax
  HWND *v3; // rsi
  int v4; // eax
  HWND v5; // rcx
  HWND v6; // rcx
  DWORD v7; // r14d
  HWND Window; // rax
  HWND v9; // rax
  WPARAM i; // rbx
  WPARAM v11; // r8
  __int128 v12; // xmm1
  HWND v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // ecx
  HWND v16; // rcx
  HWND v17; // rcx
  __int128 v18; // xmm1
  __int64 v19; // xmm0_8
  HWND v20; // rcx
  HWND v21; // [rsp+40h] [rbp-C0h]
  ULONG_PTR ulCookie; // [rsp+50h] [rbp-B0h]
  _OWORD v23[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  struct tagPOINT Points[2]; // [rsp+88h] [rbp-78h] BYREF
  LPARAM v26[2]; // [rsp+98h] [rbp-68h] BYREF
  LPARAM lParam[2]; // [rsp+A8h] [rbp-58h] BYREF
  struct tagRECT Rect; // [rsp+B8h] [rbp-48h] BYREF
  LPARAM v29[2]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v30[16]; // [rsp+D8h] [rbp-28h] BYREF
  LPARAM v31[2]; // [rsp+E8h] [rbp-18h] BYREF

  if ( *((_QWORD *)this + 37) )
  {
    CDatePicker::_CloseMonthCal(this, 0);
  }
  else
  {
    v2 = *((_DWORD *)this + 150);
    v3 = (HWND *)((char *)this + 56);
    if ( (v2 & 0x80u) == 0 )
    {
      *((_DWORD *)this + 150) = v2 | 0x80;
      InvalidateRect(*v3, 0, 1);
      CDatePicker::_NotifyDateChange(this);
    }
    v4 = *((_DWORD *)this + 150);
    if ( (v4 & 0x100) != 0 )
    {
      v5 = *v3;
      *((_DWORD *)this + 150) = v4 & 0xFFFFFEFF;
      InvalidateRect(v5, (const RECT *)((char *)this + 540), 1);
    }
    CDatePicker::_SetCurSubed(this, -1);
    v6 = *v3;
    *(_OWORD *)&Points[0].x = *(_OWORD *)((char *)this + 556);
    MapWindowPoints(v6, 0, Points, 2u);
    Points[0].y = Points[1].y + 1;
    Points[1].y += 2;
    v21 = *v3;
    v7 = *((_QWORD *)this + 77) != 0 ? -2113929119 : -2105540511;
    *(_OWORD *)lParam = 0;
    Window = (HWND)SHFusionCreateWindowEx(
                     0x8000000u,
                     L"DropDown",
                     0,
                     v7,
                     Points[0].x,
                     Points[0].y,
                     Points[1].x - Points[0].x,
                     1,
                     v21,
                     0,
                     g_hinst,
                     0);
    *((_QWORD *)this + 37) = Window;
    if ( Window )
    {
      lParam[0] = 0x300000003LL;
      lParam[1] = 0x300000003LL;
      SendMessageW(Window, 0x2705u, 0, (LPARAM)lParam);
      v9 = (HWND)SHFusionCreateWindow(
                   L"SysMonthCal32",
                   0,
                   *((_DWORD *)this + 78) & 0x2DFFFFFF | 0x52000000u,
                   0,
                   0,
                   0x80000000,
                   0x80000000,
                   *((HWND *)this + 37),
                   0,
                   g_hinst,
                   ulCookie);
      *((_QWORD *)this + 36) = v9;
      if ( v9 )
        SendMessageW(v9, 0x101Eu, 1u, 0);
    }
    if ( *((_QWORD *)this + 36) )
    {
      if ( (*((_DWORD *)this + 150) & 0x1000) != 0 )
      {
        for ( i = 0; i != 6; ++i )
          SendMessageW(*((HWND *)this + 36), 0x100Au, i, *((unsigned int *)this + i + 79));
      }
      v11 = *((_QWORD *)this + 38);
      if ( !v11 )
        v11 = *((_QWORD *)this + 81);
      SendMessageW(*((HWND *)this + 36), 0x30u, v11, 0);
      v12 = *(_OWORD *)((char *)this + 436);
      v23[0] = *(_OWORD *)((char *)this + 420);
      v24 = *(_QWORD *)((char *)this + 452);
      v23[1] = v12;
      ConvertCalDateTimeToSystemTime((char *)this + 340, v29);
      ConvertCalDateTimeToSystemTime((char *)this + 380, v30);
      SendMessageW(*((HWND *)this + 36), 0x1012u, 3u, (LPARAM)v29);
      CDatePicker::_SetDate(this, (const struct CALDATETIME *)v23, 0);
      ConvertCalDateTimeToSystemTime((char *)this + 420, v31);
      SendMessageW(*((HWND *)this + 36), 0x1002u, 0, (LPARAM)v31);
      v13 = (HWND)*((_QWORD *)this + 36);
      *(_OWORD *)v26 = 0;
      SendMessageW(v13, 0x1009u, 0, (LPARAM)v26);
      v14 = SendMessageW(*((HWND *)this + 36), 0x1015u, 0, 0);
      v15 = v26[1];
      if ( v14 > LODWORD(v26[1]) )
        v15 = v14;
      LODWORD(v26[0]) -= LODWORD(lParam[0]);
      HIDWORD(v26[0]) -= LODWORD(lParam[1]);
      HIDWORD(v26[1]) += HIDWORD(lParam[1]);
      LODWORD(v26[1]) = HIDWORD(lParam[0]) + v15;
      AdjustWindowRectEx((LPRECT)v26, v7, 0, 0x8000000u);
      CDatePicker::_RecomputeMonthCalRect(this, (struct tagRECT *)Points, (const struct tagRECT *)v26);
      MoveWindow(
        *((HWND *)this + 37),
        Points[0].x,
        Points[0].y,
        Points[1].x - Points[0].x,
        Points[1].y - Points[0].y,
        0);
      CCSendNotify((__int64)v3, -754, 0);
      v16 = (HWND)*((_QWORD *)this + 37);
      Rect = 0;
      GetClientRect(v16, &Rect);
      CDatePicker::_RecomputeMonthCalRect(this, (struct tagRECT *)Points, &Rect);
      MoveWindow(
        *((HWND *)this + 37),
        Points[0].x,
        Points[0].y,
        Points[1].x - Points[0].x,
        Points[1].y - Points[0].y,
        0);
      v17 = (HWND)*((_QWORD *)this + 37);
      v18 = *(_OWORD *)((char *)this + 436);
      *(_OWORD *)((char *)this + 500) = *(_OWORD *)((char *)this + 420);
      v19 = *(_QWORD *)((char *)this + 452);
      *(_OWORD *)((char *)this + 516) = v18;
      *(_QWORD *)((char *)this + 532) = v19;
      SendMessageW(v17, 0x2703u, 0, 0);
      SendMessageW(*((HWND *)this + 36), 7u, 0, 0);
      InvalidateRect(*v3, (const RECT *)((char *)this + 572), 0);
    }
    else
    {
      v20 = (HWND)*((_QWORD *)this + 37);
      if ( v20 )
      {
        DestroyWindow(v20);
        *((_QWORD *)this + 37) = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1801528e0  push    rbp
0x1801528e2  push    rbx
0x1801528e3  push    rsi
0x1801528e4  push    rdi
0x1801528e5  push    r13
0x1801528e7  push    r14
0x1801528e9  lea     rbp, [rsp-8]
0x1801528ee  sub     rsp, 108h
0x1801528f5  mov     rax, cs:__security_cookie
0x1801528fc  xor     rax, rsp
0x1801528ff  mov     [rbp+30h+var_38], rax
0x180152903  cmp     qword ptr [rcx+128h], 0
0x18015290b  mov     rdi, rcx
0x18015290e  jz      short loc_18015291C
0x180152910  xor     edx, edx; int
0x180152912  call    ?_CloseMonthCal@CDatePicker@@AEAAXH@Z; CDatePicker::_CloseMonthCal(int)
0x180152917  jmp     loc_180152D78
0x18015291c  mov     eax, [rcx+258h]
0x180152922  lea     rsi, [rcx+38h]
0x180152926  test    al, al
0x180152928  js      short loc_18015294B
0x18015292a  xor     edx, edx; lpRect
0x18015292c  bts     eax, 7
0x180152930  mov     [rcx+258h], eax
0x180152936  mov     rcx, [rsi]; hWnd
0x180152939  lea     r8d, [rdx+1]; bErase
0x18015293d  call    cs:__imp_InvalidateRect
0x180152943  mov     rcx, rdi; this
0x180152946  call    ?_NotifyDateChange@CDatePicker@@AEAAXXZ; CDatePicker::_NotifyDateChange(void)
0x18015294b  mov     eax, [rdi+258h]
0x180152951  bt      eax, 8
0x180152955  jnb     short loc_180152977
0x180152957  mov     rcx, [rsi]; hWnd
0x18015295a  lea     rdx, [rdi+21Ch]; lpRect
0x180152961  btr     eax, 8
0x180152965  mov     r8d, 1; bErase
0x18015296b  mov     [rdi+258h], eax
0x180152971  call    cs:__imp_InvalidateRect
0x180152977  or      edx, 0FFFFFFFFh; int
0x18015297a  mov     rcx, rdi; this
0x18015297d  call    ?_SetCurSubed@CDatePicker@@AEAAXH@Z; CDatePicker::_SetCurSubed(int)
0x180152982  movups  xmm0, xmmword ptr [rdi+22Ch]
0x180152989  mov     rcx, [rsi]; hWndFrom
0x18015298c  lea     r8, [rbp+30h+Points]; lpPoints
0x180152990  mov     r9d, 2; cPoints
0x180152996  xor     edx, edx; hWndTo
0x180152998  movdqu  xmmword ptr [rbp+30h+Points.x], xmm0
0x18015299d  call    cs:__imp_MapWindowPoints
0x1801529a3  mov     r8d, [rbp+30h+Points.y+8]
0x1801529a7  xorps   xmm0, xmm0
0x1801529aa  mov     edx, [rbp+30h+Points.x]
0x1801529ad  inc     r8d
0x1801529b0  mov     ecx, [rbp+30h+Points.x+8]
0x1801529b3  mov     [rsp+130h+var_D8], 0; LPVOID
0x1801529bc  mov     [rbp+30h+Points.y], r8d
0x1801529c0  lea     eax, [r8+1]
0x1801529c4  mov     [rbp+30h+Points.y+8], eax
0x1801529c7  mov     rax, [rdi+268h]
0x1801529ce  neg     rax
0x1801529d1  mov     rax, cs:g_hinst
0x1801529d8  mov     [rsp+130h+ulCookie], rax; ulCookie
0x1801529dd  sbb     r14d, r14d
0x1801529e0  mov     rax, [rsi]
0x1801529e3  sub     ecx, edx
0x1801529e5  mov     [rsp+130h+var_E8], 0; HMENU
0x1801529ee  and     r14d, 0FF800000h
0x1801529f5  mov     [rsp+130h+var_F0], rax; HWND
0x1801529fa  add     r14d, 82800061h
0x180152a01  mov     dword ptr [rsp+130h+var_F8], 1; int
0x180152a09  mov     r9d, r14d; dwStyle
0x180152a0c  mov     [rsp+130h+var_100], ecx; int
0x180152a10  mov     ecx, 8000000h; dwExStyle
0x180152a15  mov     [rsp+130h+bRepaint], r8d; int
0x180152a1a  xor     r8d, r8d; lpWindowName
0x180152a1d  mov     [rsp+130h+nHeight], edx; int
0x180152a21  lea     rdx, aDropdown; "DropDown"
0x180152a28  movups  xmmword ptr [rbp+30h+lParam], xmm0
0x180152a2c  call    SHFusionCreateWindowEx
0x180152a31  mov     [rdi+128h], rax
0x180152a38  mov     r13d, 3
0x180152a3e  test    rax, rax
0x180152a41  jz      loc_180152AE9
0x180152a47  lea     r9, [rbp+30h+lParam]; lParam
0x180152a4b  mov     dword ptr [rbp+30h+lParam], r13d
0x180152a4f  xor     r8d, r8d; wParam
0x180152a52  mov     dword ptr [rbp+30h+lParam+4], r13d
0x180152a56  mov     edx, 2705h; Msg
0x180152a5b  mov     dword ptr [rbp+30h+lParam+0Ch], r13d
0x180152a5f  mov     rcx, rax; hWnd
0x180152a62  mov     dword ptr [rbp+30h+lParam+8], r13d
0x180152a66  call    cs:__imp_SendMessageW
0x180152a6c  mov     rax, cs:g_hinst
0x180152a73  lea     rcx, aSysmonthcal32; "SysMonthCal32"
0x180152a7a  mov     r8d, [rdi+138h]
0x180152a81  xor     r9d, r9d; X
0x180152a84  mov     [rsp+130h+var_E8], rax; HINSTANCE
0x180152a89  and     r8d, 2DFFFFFFh
0x180152a90  mov     rax, [rdi+128h]
0x180152a97  or      r8d, 52000000h; dwStyle
0x180152a9e  mov     [rsp+130h+var_F0], 0; HMENU
0x180152aa7  xor     edx, edx; lpWindowName
0x180152aa9  mov     [rsp+130h+var_F8], rax; HWND
0x180152aae  mov     eax, 80000000h
0x180152ab3  mov     [rsp+130h+var_100], eax; int
0x180152ab7  mov     [rsp+130h+bRepaint], eax; int
0x180152abb  mov     [rsp+130h+nHeight], 0; int
0x180152ac3  call    SHFusionCreateWindow
0x180152ac8  mov     [rdi+120h], rax
0x180152acf  test    rax, rax
0x180152ad2  jz      short loc_180152AE9
0x180152ad4  xor     r9d, r9d; lParam
0x180152ad7  lea     r8d, [r13-2]; wParam
0x180152adb  mov     edx, 101Eh; Msg
0x180152ae0  mov     rcx, rax; hWnd
0x180152ae3  call    cs:__imp_SendMessageW
0x180152ae9  cmp     qword ptr [rdi+120h], 0
0x180152af1  jz      loc_180152D5B
0x180152af7  test    dword ptr [rdi+258h], 1000h
0x180152b01  jz      short loc_180152B2B
0x180152b03  xor     ebx, ebx
0x180152b05  mov     r9d, [rdi+rbx*4+13Ch]; lParam
0x180152b0d  mov     r8, rbx; wParam
0x180152b10  mov     rcx, [rdi+120h]; hWnd
0x180152b17  mov     edx, 100Ah; Msg
0x180152b1c  call    cs:__imp_SendMessageW
0x180152b22  inc     rbx
0x180152b25  cmp     rbx, 6
0x180152b29  jnz     short loc_180152B05
0x180152b2b  mov     r8, [rdi+130h]
0x180152b32  xor     r9d, r9d; lParam
0x180152b35  mov     rcx, [rdi+120h]; hWnd
0x180152b3c  lea     edx, [r9+30h]; Msg
0x180152b40  test    r8, r8
0x180152b43  jnz     short loc_180152B4C
0x180152b45  mov     r8, [rdi+288h]; wParam
0x180152b4c  call    cs:__imp_SendMessageW
0x180152b52  lea     rbx, [rdi+1A4h]
0x180152b59  movups  xmm0, xmmword ptr [rbx]
0x180152b5c  lea     rcx, [rdi+154h]
0x180152b63  movups  xmm1, xmmword ptr [rbx+10h]
0x180152b67  lea     rdx, [rbp+30h+var_68]
0x180152b6b  movups  [rsp+130h+var_D0], xmm0
0x180152b70  movsd   xmm0, qword ptr [rbx+20h]
0x180152b75  movsd   [rbp+30h+var_B0], xmm0
0x180152b7a  movups  [rsp+130h+var_C0], xmm1
0x180152b7f  call    cs:__imp_ConvertCalDateTimeToSystemTime
0x180152b85  lea     rcx, [rdi+17Ch]
0x180152b8c  lea     rdx, [rbp+30h+var_58]
0x180152b90  call    cs:__imp_ConvertCalDateTimeToSystemTime
0x180152b96  mov     rcx, [rdi+120h]; hWnd
0x180152b9d  lea     r9, [rbp+30h+var_68]; lParam
0x180152ba1  mov     r8, r13; wParam
0x180152ba4  mov     edx, 1012h; Msg
0x180152ba9  call    cs:__imp_SendMessageW
0x180152baf  xor     r8d, r8d; int
0x180152bb2  lea     rdx, [rsp+130h+var_D0]; struct CALDATETIME *
0x180152bb7  mov     rcx, rdi; this
0x180152bba  call    ?_SetDate@CDatePicker@@AEAAHPEBUCALDATETIME@@H@Z; CDatePicker::_SetDate(CALDATETIME const *,int)
0x180152bbf  lea     rdx, [rbp+30h+var_48]
0x180152bc3  mov     rcx, rbx
0x180152bc6  call    cs:__imp_ConvertCalDateTimeToSystemTime
0x180152bcc  mov     rcx, [rdi+120h]; hWnd
0x180152bd3  lea     r9, [rbp+30h+var_48]; lParam
0x180152bd7  xor     r8d, r8d; wParam
0x180152bda  mov     edx, 1002h; Msg
0x180152bdf  call    cs:__imp_SendMessageW
0x180152be5  mov     rcx, [rdi+120h]; hWnd
0x180152bec  lea     r9, [rbp+30h+var_98]; lParam
0x180152bf0  xorps   xmm0, xmm0
0x180152bf3  xor     r8d, r8d; wParam
0x180152bf6  mov     edx, 1009h; Msg
0x180152bfb  movups  xmmword ptr [rbp+30h+var_98], xmm0
0x180152bff  call    cs:__imp_SendMessageW
0x180152c05  mov     rcx, [rdi+120h]; hWnd
0x180152c0c  xor     r9d, r9d; lParam
0x180152c0f  xor     r8d, r8d; wParam
0x180152c12  mov     edx, 1015h; Msg
0x180152c17  call    cs:__imp_SendMessageW
0x180152c1d  mov     ecx, dword ptr [rbp+30h+var_98+8]
0x180152c20  mov     r9d, 8000000h; dwExStyle
0x180152c26  cmp     eax, ecx
0x180152c28  mov     edx, r14d; dwStyle
0x180152c2b  cmova   ecx, eax
0x180152c2e  mov     eax, dword ptr [rbp+30h+lParam]
0x180152c31  sub     dword ptr [rbp+30h+var_98], eax
0x180152c34  xor     r8d, r8d; bMenu
0x180152c37  add     ecx, dword ptr [rbp+30h+lParam+4]
0x180152c3a  mov     eax, dword ptr [rbp+30h+lParam+8]
0x180152c3d  sub     dword ptr [rbp+30h+var_98+4], eax
0x180152c40  mov     eax, dword ptr [rbp+30h+lParam+0Ch]
0x180152c43  add     dword ptr [rbp+30h+var_98+0Ch], eax
0x180152c46  mov     dword ptr [rbp+30h+var_98+8], ecx
0x180152c49  lea     rcx, [rbp+30h+var_98]; lpRect
0x180152c4d  call    cs:__imp_AdjustWindowRectEx
0x180152c53  lea     r8, [rbp+30h+var_98]; struct tagRECT *
0x180152c57  mov     rcx, rdi; this
0x180152c5a  lea     rdx, [rbp+30h+Points]; struct tagRECT *
0x180152c5e  call    ?_RecomputeMonthCalRect@CDatePicker@@AEAAXPEAUtagRECT@@PEBU2@@Z; CDatePicker::_RecomputeMonthCalRect(tagRECT *,tagRECT const *)
0x180152c63  mov     eax, [rbp+30h+Points.y+8]
0x180152c66  mov     r8d, [rbp+30h+Points.y]; Y
0x180152c6a  sub     eax, r8d
0x180152c6d  mov     r9d, [rbp+30h+Points.x+8]
0x180152c71  mov     edx, [rbp+30h+Points.x]; X
0x180152c74  sub     r9d, edx; nWidth
0x180152c77  mov     rcx, [rdi+128h]; hWnd
0x180152c7e  mov     [rsp+130h+bRepaint], 0; bRepaint
0x180152c86  mov     [rsp+130h+nHeight], eax; nHeight
0x180152c8a  call    cs:__imp_MoveWindow
0x180152c90  xor     r8d, r8d
0x180152c93  mov     edx, 0FFFFFD0Eh
0x180152c98  mov     rcx, rsi
0x180152c9b  call    CCSendNotify
0x180152ca0  mov     rcx, [rdi+128h]; hWnd
0x180152ca7  lea     rdx, [rbp+30h+Rect]; lpRect
0x180152cab  xorps   xmm0, xmm0
0x180152cae  movups  xmmword ptr [rbp+30h+Rect.left], xmm0
0x180152cb2  call    cs:__imp_GetClientRect
0x180152cb8  lea     r8, [rbp+30h+Rect]; struct tagRECT *
0x180152cbc  mov     rcx, rdi; this
0x180152cbf  lea     rdx, [rbp+30h+Points]; struct tagRECT *
0x180152cc3  call    ?_RecomputeMonthCalRect@CDatePicker@@AEAAXPEAUtagRECT@@PEBU2@@Z; CDatePicker::_RecomputeMonthCalRect(tagRECT *,tagRECT const *)
0x180152cc8  mov     eax, [rbp+30h+Points.y+8]
0x180152ccb  mov     r8d, [rbp+30h+Points.y]; Y
0x180152ccf  sub     eax, r8d
0x180152cd2  mov     r9d, [rbp+30h+Points.x+8]
0x180152cd6  mov     edx, [rbp+30h+Points.x]; X
0x180152cd9  sub     r9d, edx; nWidth
0x180152cdc  mov     rcx, [rdi+128h]; hWnd
0x180152ce3  mov     [rsp+130h+bRepaint], 0; bRepaint
0x180152ceb  mov     [rsp+130h+nHeight], eax; nHeight
0x180152cef  call    cs:__imp_MoveWindow
0x180152cf5  movups  xmm0, xmmword ptr [rbx]
0x180152cf8  mov     rcx, [rdi+128h]; hWnd
0x180152cff  xor     r9d, r9d; lParam
0x180152d02  movups  xmm1, xmmword ptr [rbx+10h]
0x180152d06  xor     r8d, r8d; wParam
0x180152d09  mov     edx, 2703h; Msg
0x180152d0e  movups  xmmword ptr [rdi+1F4h], xmm0
0x180152d15  movsd   xmm0, qword ptr [rbx+20h]
0x180152d1a  movups  xmmword ptr [rdi+204h], xmm1
0x180152d21  movsd   qword ptr [rdi+214h], xmm0
0x180152d29  call    cs:__imp_SendMessageW
0x180152d2f  mov     rcx, [rdi+120h]; hWnd
0x180152d36  xor     r9d, r9d; lParam
0x180152d39  xor     r8d, r8d; wParam
0x180152d3c  lea     edx, [r9+7]; Msg
0x180152d40  call    cs:__imp_SendMessageW
0x180152d46  mov     rcx, [rsi]; hWnd
0x180152d49  lea     rdx, [rdi+23Ch]; lpRect
0x180152d50  xor     r8d, r8d; bErase
0x180152d53  call    cs:__imp_InvalidateRect
0x180152d59  jmp     short loc_180152D78
0x180152d5b  mov     rcx, [rdi+128h]; hWnd
0x180152d62  test    rcx, rcx
0x180152d65  jz      short loc_180152D78
0x180152d67  call    cs:__imp_DestroyWindow
0x180152d6d  mov     qword ptr [rdi+128h], 0
0x180152d78  mov     rcx, [rbp+30h+var_38]
0x180152d7c  xor     rcx, rsp; StackCookie
0x180152d7f  call    __security_check_cookie
0x180152d84  add     rsp, 108h
0x180152d8b  pop     r14
0x180152d8d  pop     r13
0x180152d8f  pop     rdi
0x180152d90  pop     rsi
0x180152d91  pop     rbx
0x180152d92  pop     rbp
0x180152d93  retn
```
