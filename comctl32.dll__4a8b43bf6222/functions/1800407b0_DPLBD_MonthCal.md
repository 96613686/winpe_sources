# DPLBD_MonthCal

- ea: `0x1800407b0`
- end: `0x180040df1`
- name: `DPLBD_MonthCal`
- size: `1601`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004042c`
- `0x180040df8`
- `0x1800414b0`

## callees

- `0x1800115f0`
- `0x180035fe0`
- `0x1800407b0`
- `0x180040f80`
- `0x18004983c`
- `0x180049f64`
- `0x1800722a0`

## import_xrefs

- `USER32!GetDC` at `0x180040802`
- `USER32!GetDC` at `0x180040802`
- `USER32!ReleaseDC` at `0x180040dbe`
- `USER32!ReleaseDC` at `0x180040dbe`
- `USER32!MapWindowPoints` at `0x1800408bc`
- `USER32!MapWindowPoints` at `0x1800408df`
- `USER32!MapWindowPoints` at `0x1800408bc`
- `USER32!MapWindowPoints` at `0x1800408df`
- `USER32!PtInRect` at `0x180040bb6`
- `USER32!PtInRect` at `0x180040c30`
- `USER32!PtInRect` at `0x180040cb9`
- `USER32!PtInRect` at `0x180040d26`
- `USER32!PtInRect` at `0x180040bb6`
- `USER32!PtInRect` at `0x180040c30`
- `USER32!PtInRect` at `0x180040cb9`
- `USER32!PtInRect` at `0x180040d26`
- `USER32!TranslateMessage` at `0x180040d49`
- `USER32!TranslateMessage` at `0x180040d49`
- `USER32!DispatchMessageW` at `0x180040d53`
- `USER32!DispatchMessageW` at `0x180040d53`
- `USER32!SendMessageW` at `0x180040983`
- `USER32!SendMessageW` at `0x1800409a4`
- `USER32!SendMessageW` at `0x1800409bc`
- `USER32!SendMessageW` at `0x1800409d1`
- `USER32!SendMessageW` at `0x1800409e5`
- `USER32!SendMessageW` at `0x180040a72`
- `USER32!SendMessageW` at `0x180040c8e`
- `USER32!SendMessageW` at `0x180040983`
- `USER32!SendMessageW` at `0x1800409a4`
- `USER32!SendMessageW` at `0x1800409bc`
- `USER32!SendMessageW` at `0x1800409d1`
- `USER32!SendMessageW` at `0x1800409e5`
- `USER32!SendMessageW` at `0x180040a72`
- `USER32!SendMessageW` at `0x180040c8e`
- `USER32!DestroyWindow` at `0x180040db2`
- `USER32!DestroyWindow` at `0x180040db2`
- `USER32!ShowWindow` at `0x180040b10`
- `USER32!ShowWindow` at `0x180040b10`
- `USER32!CreateWindowExW` at `0x18004095b`
- `USER32!CreateWindowExW` at `0x18004095b`
- `USER32!InvalidateRect` at `0x18004082c`
- `USER32!InvalidateRect` at `0x18004085b`
- `USER32!InvalidateRect` at `0x180040d7b`
- `USER32!InvalidateRect` at `0x18004082c`
- `USER32!InvalidateRect` at `0x18004085b`
- `USER32!InvalidateRect` at `0x180040d7b`
- `USER32!GetWindowLongPtrW` at `0x180040ac6`
- `USER32!GetWindowLongPtrW` at `0x180040ac6`
- `USER32!GetMessageW` at `0x180040b41`
- `USER32!GetMessageW` at `0x180040b41`
- `USER32!DrawFrameControl` at `0x180040898`
- `USER32!DrawFrameControl` at `0x180040b9f`
- `USER32!DrawFrameControl` at `0x180040beb`
- `USER32!DrawFrameControl` at `0x180040c20`
- `USER32!DrawFrameControl` at `0x180040898`
- `USER32!DrawFrameControl` at `0x180040b9f`
- `USER32!DrawFrameControl` at `0x180040beb`
- `USER32!DrawFrameControl` at `0x180040c20`
- `USER32!MoveWindow` at `0x180040aab`
- `USER32!MoveWindow` at `0x180040b02`
- `USER32!MoveWindow` at `0x180040aab`
- `USER32!MoveWindow` at `0x180040b02`

## pseudocode

```c
int __fastcall DPLBD_MonthCal(__int64 a1, int a2)
{
  HWND v4; // rcx
  HDC DC; // rax
  int v6; // ecx
  HDC v7; // r15
  int v8; // eax
  HWND v9; // rcx
  HWND v10; // rcx
  HWND v11; // rcx
  __m128i v12; // xmm0
  HWND Window; // rax
  HWND v14; // r14
  WPARAM i; // rbx
  WPARAM v16; // r8
  unsigned int v17; // eax
  unsigned int v18; // ecx
  __int128 v19; // xmm0
  LONG_PTR WindowLongPtrW; // rax
  int v21; // ebx
  __int128 v22; // xmm6
  int v23; // r9d
  UINT message; // ecx
  WPARAM wParam; // rax
  struct tagMSG Msg; // [rsp+68h] [rbp-69h] BYREF
  RECT v28; // [rsp+98h] [rbp-39h] BYREF
  LPARAM lParam[2]; // [rsp+A8h] [rbp-29h] BYREF
  struct tagPOINT Points[2]; // [rsp+B8h] [rbp-19h] BYREF
  LPARAM v31[2]; // [rsp+C8h] [rbp-9h] BYREF
  RECT rc; // [rsp+D8h] [rbp+7h] BYREF

  v4 = *(HWND *)a1;
  *(_OWORD *)&Points[0].x = 0;
  *(_OWORD *)lParam = 0;
  rc = 0;
  v28 = 0;
  *(_OWORD *)v31 = 0;
  DC = GetDC(v4);
  v6 = *(_DWORD *)(a1 + 376);
  v7 = DC;
  if ( (v6 & 0x40) == 0 )
  {
    *(_DWORD *)(a1 + 376) = v6 | 0x40;
    InvalidateRect(*(HWND *)a1, 0, 1);
    DPNotifyDateChange(a1);
  }
  v8 = *(_DWORD *)(a1 + 376);
  if ( (v8 & 0x80u) != 0 )
  {
    v9 = *(HWND *)a1;
    *(_DWORD *)(a1 + 376) = v8 & 0xFFFFFF7F;
    InvalidateRect(v9, (const RECT *)(a1 + 312), 1);
  }
  SECSetCurSubed(a1, 0xFFFFFFFFLL);
  if ( a2 )
    DrawFrameControl(v7, (LPRECT)(a1 + 344), 3u, (((*(_DWORD *)(a1 + 376) & 1) == 0) << 8) + 16897);
  v10 = *(HWND *)a1;
  *(_OWORD *)&Points[0].x = *(_OWORD *)(a1 + 328);
  MapWindowPoints(v10, 0, Points, 2u);
  v11 = *(HWND *)a1;
  rc = *(RECT *)(a1 + 344);
  MapWindowPoints(v11, 0, (LPPOINT)&rc, 2u);
  v28 = *(RECT *)&Points[0].x;
  v12 = _mm_srli_si128(*(__m128i *)&Points[0].x, 8);
  v28.top = v12.m128i_i32[1] + 1;
  v28.bottom = v12.m128i_i32[1] + 2;
  Window = CreateWindowExW(
             0,
             L"SysMonthCal32",
             0,
             0x80800000,
             Points[0].x,
             v12.m128i_i32[1] + 1,
             Points[1].x - Points[0].x,
             1,
             *(HWND *)a1,
             0,
             g_hinst,
             0);
  v14 = Window;
  if ( Window )
  {
    *(_QWORD *)(a1 + 64) = Window;
    for ( i = 0; i != 6; ++i )
      SendMessageW(v14, 0x100Au, i, *(unsigned int *)(a1 + 4 * i + 80));
    v16 = *(_QWORD *)(a1 + 72);
    if ( v16 )
      SendMessageW(v14, 0x30u, v16, 0);
    SendMessageW(v14, 0x1012u, 3u, a1 + 104);
    SendMessageW(v14, 0x1009u, 0, (LPARAM)lParam);
    v17 = SendMessageW(v14, 0x1015u, 0, 0);
    v18 = lParam[1];
    v19 = *(_OWORD *)(a1 + 204);
    if ( v17 > LODWORD(lParam[1]) )
      v18 = v17;
    LODWORD(lParam[1]) = v18;
    *(_OWORD *)v31 = v19;
    WORD2(v31[0]) = ((int)(GetStartDowForMonth((unsigned __int16)v19, WORD1(v19)) + WORD3(v19) - 1) % 7 + 1) % 7;
    SendMessageW(v14, 0x1002u, 0, (LPARAM)v31);
    RecomputeMonthCalRect(a1, &v28, lParam);
    MoveWindow(v14, v28.left, v28.top, v28.right - v28.left, v28.bottom - v28.top, 0);
    CCSendNotify(a1, 4294966542LL, 0);
    WindowLongPtrW = GetWindowLongPtrW(v14, 0);
    RecomputeMonthCalRect(a1, &v28, WindowLongPtrW + 2132);
    MoveWindow(v14, v28.left, v28.top, v28.right - v28.left, v28.bottom - v28.top, 0);
    ShowWindow(v14, 8);
    *(_DWORD *)(a1 + 376) |= 0x20u;
    v21 = a2;
    v22 = *(_OWORD *)(a1 + 204);
    while ( 1 )
    {
      memset(&Msg, 0, sizeof(Msg));
      v23 = *(_DWORD *)(a1 + 376)
          ^ ((unsigned __int8)*(_DWORD *)(a1 + 376)
           ^ (unsigned __int8)(32 * GetMessageW(&Msg, 0, 0, 0)))
          & 0x20;
      message = Msg.message;
      *(_DWORD *)(a1 + 376) = v23;
      if ( v21 )
      {
        if ( message == 512 )
        {
          if ( PtInRect(&rc, Msg.pt) )
          {
            if ( !a2 )
            {
              DrawFrameControl(v7, (LPRECT)(a1 + 344), 3u, (((*(_DWORD *)(a1 + 376) & 1) == 0) << 8) + 16897);
              a2 = 1;
            }
          }
          else
          {
            if ( a2 )
            {
              DrawFrameControl(v7, (LPRECT)(a1 + 344), 3u, (((*(_DWORD *)(a1 + 376) & 1) == 0) << 8) + 1);
              a2 = 0;
            }
            if ( PtInRect(&v28, Msg.pt) )
            {
              v21 = 0;
              SendMessageW(
                v14,
                0x201u,
                0,
                (unsigned __int16)(v28.right / 2 + v28.left / 2)
              | (((unsigned __int64)(unsigned int)(v28.bottom / 2) << 16)
               + ((unsigned __int64)(unsigned int)(v28.top / 2) << 16))
              & 0xFFFF0000);
            }
          }
          goto LABEL_49;
        }
        if ( message == 514 )
        {
          if ( a2 )
          {
            DrawFrameControl(v7, (LPRECT)(a1 + 344), 3u, (((v23 & 1) == 0) << 8) + 1);
            a2 = 0;
          }
          v21 = 0;
          goto LABEL_49;
        }
      }
      if ( message == 513 || message == 161 || message == 515 )
      {
        if ( !PtInRect(&v28, Msg.pt) )
          goto LABEL_48;
        message = Msg.message;
      }
      if ( message - 273 <= 1
        || (wParam = Msg.wParam, message == 260) && Msg.wParam == 38
        || message == 256 && Msg.wParam == 13
        || message == 8 )
      {
LABEL_48:
        *(_DWORD *)(a1 + 376) &= ~0x20u;
        goto LABEL_49;
      }
      if ( message == 516 || message == 164 || message == 518 )
      {
        if ( !PtInRect(&v28, Msg.pt) )
          goto LABEL_47;
        wParam = Msg.wParam;
        message = Msg.message;
      }
      if ( message == 256 && wParam == 27 )
      {
LABEL_47:
        *(_DWORD *)(a1 + 376) &= ~0x20u;
        *(_OWORD *)(a1 + 204) = v22;
        DPNotifyDateChange(a1);
        InvalidateRect(*(HWND *)a1, 0, 1);
        goto LABEL_49;
      }
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
LABEL_49:
      if ( (*(_BYTE *)(a1 + 376) & 0x20) == 0 )
      {
        CCSendNotify(a1, 4294966543LL, 0);
        *(_QWORD *)(a1 + 64) = 0;
        DestroyWindow(v14);
        LODWORD(Window) = ReleaseDC(*(HWND *)a1, v7);
        return (int)Window;
      }
    }
  }
  return (int)Window;
}

```

## disassembly

```asm
0x1800407b0  mov     rax, rsp
0x1800407b3  mov     [rax+10h], rbx
0x1800407b7  mov     [rax+18h], rsi
0x1800407bb  push    rbp
0x1800407bc  push    rdi
0x1800407bd  push    r12
0x1800407bf  push    r14
0x1800407c1  push    r15
0x1800407c3  lea     rbp, [rax-5Fh]
0x1800407c7  sub     rsp, 100h
0x1800407ce  movaps  xmmword ptr [rax-38h], xmm6
0x1800407d2  mov     rax, cs:__security_cookie
0x1800407d9  xor     rax, rsp
0x1800407dc  mov     [rbp+57h+var_40], rax
0x1800407e0  xorps   xmm0, xmm0
0x1800407e3  xorps   xmm1, xmm1
0x1800407e6  mov     rdi, rcx
0x1800407e9  mov     esi, edx
0x1800407eb  mov     rcx, [rcx]; hWnd
0x1800407ee  movups  xmmword ptr [rbp+57h+Points.x], xmm0
0x1800407f2  movups  xmmword ptr [rbp+57h+lParam], xmm1
0x1800407f6  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800407fa  movups  xmmword ptr [rbp+57h+var_90.left], xmm1
0x1800407fe  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180040802  call    cs:__imp_GetDC
0x180040808  mov     ecx, [rdi+178h]
0x18004080e  mov     ebx, 1
0x180040813  mov     r15, rax
0x180040816  test    cl, 40h
0x180040819  jnz     short loc_18004083A
0x18004081b  or      ecx, 40h
0x18004081e  mov     r8d, ebx; bErase
0x180040821  mov     [rdi+178h], ecx
0x180040827  xor     edx, edx; lpRect
0x180040829  mov     rcx, [rdi]; hWnd
0x18004082c  call    cs:__imp_InvalidateRect
0x180040832  mov     rcx, rdi
0x180040835  call    DPNotifyDateChange
0x18004083a  mov     eax, [rdi+178h]
0x180040840  test    al, al
0x180040842  jns     short loc_180040861
0x180040844  mov     rcx, [rdi]; hWnd
0x180040847  lea     rdx, [rdi+138h]; lpRect
0x18004084e  btr     eax, 7
0x180040852  mov     r8d, ebx; bErase
0x180040855  mov     [rdi+178h], eax
0x18004085b  call    cs:__imp_InvalidateRect
0x180040861  or      edx, 0FFFFFFFFh
0x180040864  mov     rcx, rdi
0x180040867  call    SECSetCurSubed
0x18004086c  test    esi, esi
0x18004086e  jz      short loc_18004089E
0x180040870  mov     r9d, [rdi+178h]
0x180040877  lea     rdx, [rdi+158h]; LPRECT
0x18004087e  not     r9d
0x180040881  mov     r8d, 3; UINT
0x180040887  and     r9d, ebx
0x18004088a  mov     rcx, r15; HDC
0x18004088d  shl     r9d, 8
0x180040891  add     r9d, 4201h; UINT
0x180040898  call    cs:__imp_DrawFrameControl
0x18004089e  movups  xmm0, xmmword ptr [rdi+148h]
0x1800408a5  mov     rcx, [rdi]; hWndFrom
0x1800408a8  lea     r8, [rbp+57h+Points]; lpPoints
0x1800408ac  mov     r14d, 2
0x1800408b2  xor     edx, edx; hWndTo
0x1800408b4  mov     r9d, r14d; cPoints
0x1800408b7  movdqu  xmmword ptr [rbp+57h+Points.x], xmm0
0x1800408bc  call    cs:__imp_MapWindowPoints
0x1800408c2  mov     rcx, [rdi]; hWndFrom
0x1800408c5  lea     r12, [rdi+158h]
0x1800408cc  movups  xmm0, xmmword ptr [r12]
0x1800408d1  mov     r9d, r14d; cPoints
0x1800408d4  lea     r8, [rbp+57h+rc]; lpPoints
0x1800408d8  xor     edx, edx; hWndTo
0x1800408da  movdqu  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800408df  call    cs:__imp_MapWindowPoints
0x1800408e5  movaps  xmm0, xmmword ptr [rbp+57h+Points.x]
0x1800408e9  mov     r9d, 80800000h; dwStyle
0x1800408ef  mov     [rsp+120h+lpParam], 0; lpParam
0x1800408f8  movdqa  xmmword ptr [rbp+57h+var_90.left], xmm0
0x1800408fd  mov     edx, [rbp+57h+var_90.left]
0x180040900  mov     ecx, [rbp+57h+var_90.right]
0x180040903  sub     ecx, edx
0x180040905  psrldq  xmm0, 8
0x18004090a  movq    r8, xmm0
0x18004090f  shr     r8, 20h
0x180040913  inc     r8d
0x180040916  mov     [rbp+57h+var_90.top], r8d
0x18004091a  lea     eax, [r8+1]
0x18004091e  mov     [rbp+57h+var_90.bottom], eax
0x180040921  mov     rax, cs:g_hinst
0x180040928  mov     [rsp+120h+hInstance], rax; hInstance
0x18004092d  mov     rax, [rdi]
0x180040930  mov     [rsp+120h+hMenu], 0; hMenu
0x180040939  mov     [rsp+120h+hWndParent], rax; hWndParent
0x18004093e  mov     [rsp+120h+nHeight], ebx; nHeight
0x180040942  mov     [rsp+120h+nWidth], ecx; nWidth
0x180040946  xor     ecx, ecx; dwExStyle
0x180040948  mov     [rsp+120h+Y], r8d; Y
0x18004094d  xor     r8d, r8d; lpWindowName
0x180040950  mov     [rsp+120h+X], edx; X
0x180040954  lea     rdx, aSysmonthcal32_0; "SysMonthCal32"
0x18004095b  call    cs:__imp_CreateWindowExW
0x180040961  mov     r14, rax
0x180040964  test    rax, rax
0x180040967  jz      loc_180040DC4
0x18004096d  mov     [rdi+40h], rax
0x180040971  xor     ebx, ebx
0x180040973  mov     r9d, [rdi+rbx*4+50h]; lParam
0x180040978  mov     r8, rbx; wParam
0x18004097b  mov     edx, 100Ah; Msg
0x180040980  mov     rcx, r14; hWnd
0x180040983  call    cs:__imp_SendMessageW
0x180040989  inc     rbx
0x18004098c  cmp     rbx, 6
0x180040990  jnz     short loc_180040973
0x180040992  mov     r8, [rdi+48h]; wParam
0x180040996  test    r8, r8
0x180040999  jz      short loc_1800409AA
0x18004099b  xor     r9d, r9d; lParam
0x18004099e  lea     edx, [rbx+2Ah]; Msg
0x1800409a1  mov     rcx, r14; hWnd
0x1800409a4  call    cs:__imp_SendMessageW
0x1800409aa  lea     r9, [rdi+68h]; lParam
0x1800409ae  mov     edx, 1012h; Msg
0x1800409b3  mov     r8d, 3; wParam
0x1800409b9  mov     rcx, r14; hWnd
0x1800409bc  call    cs:__imp_SendMessageW
0x1800409c2  lea     r9, [rbp+57h+lParam]; lParam
0x1800409c6  xor     r8d, r8d; wParam
0x1800409c9  mov     edx, 1009h; Msg
0x1800409ce  mov     rcx, r14; hWnd
0x1800409d1  call    cs:__imp_SendMessageW
0x1800409d7  xor     r9d, r9d; lParam
0x1800409da  xor     r8d, r8d; wParam
0x1800409dd  mov     edx, 1015h; Msg
0x1800409e2  mov     rcx, r14; hWnd
0x1800409e5  call    cs:__imp_SendMessageW
0x1800409eb  mov     ecx, dword ptr [rbp+57h+lParam+8]
0x1800409ee  cmp     eax, ecx
0x1800409f0  movups  xmm0, xmmword ptr [rdi+0CCh]
0x1800409f7  cmova   ecx, eax
0x1800409fa  mov     dword ptr [rbp+57h+lParam+8], ecx
0x1800409fd  movq    rbx, xmm0
0x180040a02  mov     rax, rbx
0x180040a05  movzx   ecx, bx
0x180040a08  shr     rax, 10h
0x180040a0c  movzx   edx, ax
0x180040a0f  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180040a13  call    GetStartDowForMonth
0x180040a18  mov     r9d, 92492493h
0x180040a1e  shr     rbx, 30h
0x180040a22  lea     r8d, [rbx-1]
0x180040a26  add     r8d, eax
0x180040a29  mov     eax, r9d
0x180040a2c  imul    r8d
0x180040a2f  mov     eax, r9d
0x180040a32  lea     r9, [rbp+57h+var_60]; lParam
0x180040a36  add     edx, r8d
0x180040a39  sar     edx, 2
0x180040a3c  mov     ecx, edx
0x180040a3e  shr     ecx, 1Fh
0x180040a41  add     edx, ecx
0x180040a43  imul    ecx, edx, 7
0x180040a46  sub     r8d, ecx
0x180040a49  mov     rcx, r14; hWnd
0x180040a4c  inc     r8d
0x180040a4f  imul    r8d
0x180040a52  add     edx, r8d
0x180040a55  sar     edx, 2
0x180040a58  mov     eax, edx
0x180040a5a  shr     eax, 1Fh
0x180040a5d  add     edx, eax
0x180040a5f  imul    eax, edx, 7
0x180040a62  mov     edx, 1002h; Msg
0x180040a67  sub     r8d, eax
0x180040a6a  mov     word ptr [rbp+57h+var_60+4], r8w
0x180040a6f  xor     r8d, r8d; wParam
0x180040a72  call    cs:__imp_SendMessageW
0x180040a78  lea     r8, [rbp+57h+lParam]
0x180040a7c  mov     rcx, rdi
0x180040a7f  lea     rdx, [rbp+57h+var_90]
0x180040a83  call    _RecomputeMonthCalRect
0x180040a88  mov     eax, [rbp+57h+var_90.bottom]
0x180040a8b  mov     rcx, r14; hWnd
0x180040a8e  mov     r8d, [rbp+57h+var_90.top]; Y
0x180040a92  sub     eax, r8d
0x180040a95  mov     r9d, [rbp+57h+var_90.right]
0x180040a99  mov     edx, [rbp+57h+var_90.left]; X
0x180040a9c  sub     r9d, edx; nWidth
0x180040a9f  mov     [rsp+120h+Y], 0; bRepaint
0x180040aa7  mov     [rsp+120h+X], eax; nHeight
0x180040aab  call    cs:__imp_MoveWindow
0x180040ab1  xor     r8d, r8d
0x180040ab4  mov     edx, 0FFFFFD0Eh
0x180040ab9  mov     rcx, rdi
0x180040abc  call    CCSendNotify
0x180040ac1  xor     edx, edx; nIndex
0x180040ac3  mov     rcx, r14; hWnd
0x180040ac6  call    cs:__imp_GetWindowLongPtrW
0x180040acc  lea     rdx, [rbp+57h+var_90]
0x180040ad0  mov     rcx, rdi
0x180040ad3  lea     r8, [rax+854h]
0x180040ada  call    _RecomputeMonthCalRect
0x180040adf  mov     eax, [rbp+57h+var_90.bottom]
0x180040ae2  mov     rcx, r14; hWnd
0x180040ae5  mov     r8d, [rbp+57h+var_90.top]; Y
0x180040ae9  sub     eax, r8d
0x180040aec  mov     r9d, [rbp+57h+var_90.right]
0x180040af0  mov     edx, [rbp+57h+var_90.left]; X
0x180040af3  sub     r9d, edx; nWidth
0x180040af6  mov     [rsp+120h+Y], 0; bRepaint
0x180040afe  mov     [rsp+120h+X], eax; nHeight
0x180040b02  call    cs:__imp_MoveWindow
0x180040b08  mov     edx, 8; nCmdShow
0x180040b0d  mov     rcx, r14; hWnd
0x180040b10  call    cs:__imp_ShowWindow
0x180040b16  or      dword ptr [rdi+178h], 20h
0x180040b1d  mov     ebx, esi
0x180040b1f  movups  xmm6, xmmword ptr [rdi+0CCh]
0x180040b26  xorps   xmm0, xmm0
0x180040b29  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180040b2d  xor     r9d, r9d; wMsgFilterMax
0x180040b30  xor     r8d, r8d; wMsgFilterMin
0x180040b33  xor     edx, edx; hWnd
0x180040b35  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x180040b39  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x180040b3d  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180040b41  call    cs:__imp_GetMessageW
0x180040b47  mov     ecx, [rdi+178h]
0x180040b4d  movzx   r9d, ax
0x180040b51  shl     r9d, 5
0x180040b55  xor     r9d, ecx
0x180040b58  and     r9d, 20h
0x180040b5c  xor     r9d, ecx
0x180040b5f  mov     ecx, [rbp+57h+Msg.message]
0x180040b62  mov     [rdi+178h], r9d
0x180040b69  test    ebx, ebx
0x180040b6b  jz      loc_180040C99
0x180040b71  mov     eax, ecx
0x180040b73  sub     eax, 200h
0x180040b78  jz      short loc_180040BAE
0x180040b7a  cmp     eax, 2
0x180040b7d  jnz     loc_180040C99
0x180040b83  test    esi, esi
0x180040b85  jz      short loc_180040BA7
0x180040b87  not     r9d
0x180040b8a  lea     r8d, [rax+1]; UINT
0x180040b8e  and     r9d, 1
0x180040b92  mov     rdx, r12; LPRECT
0x180040b95  shl     r9d, 8
0x180040b99  mov     rcx, r15; HDC
0x180040b9c  inc     r9d; UINT
0x180040b9f  call    cs:__imp_DrawFrameControl
0x180040ba5  xor     esi, esi
0x180040ba7  xor     ebx, ebx
0x180040ba9  jmp     loc_180040D8A
0x180040bae  mov     rdx, qword ptr [rbp+57h+Msg.pt.x]; pt
0x180040bb2  lea     rcx, [rbp+57h+rc]; lprc
0x180040bb6  call    cs:__imp_PtInRect
0x180040bbc  test    eax, eax
0x180040bbe  jz      short loc_180040BFB
0x180040bc0  test    esi, esi
0x180040bc2  jnz     loc_180040D8A
0x180040bc8  mov     r9d, [rdi+178h]
0x180040bcf  lea     r8d, [rsi+3]; UINT
0x180040bd3  not     r9d
0x180040bd6  mov     rdx, r12; LPRECT
0x180040bd9  and     r9d, 1
0x180040bdd  mov     rcx, r15; HDC
0x180040be0  shl     r9d, 8
0x180040be4  add     r9d, 4201h; UINT
0x180040beb  call    cs:__imp_DrawFrameControl
0x180040bf1  mov     esi, 1
0x180040bf6  jmp     loc_180040D8A
0x180040bfb  test    esi, esi
0x180040bfd  jz      short loc_180040C28
0x180040bff  mov     r9d, [rdi+178h]
0x180040c06  mov     r8d, 3; UINT
0x180040c0c  not     r9d
0x180040c0f  mov     rdx, r12; LPRECT
0x180040c12  and     r9d, 1
0x180040c16  mov     rcx, r15; HDC
0x180040c19  shl     r9d, 8
0x180040c1d  inc     r9d; UINT
0x180040c20  call    cs:__imp_DrawFrameControl
0x180040c26  xor     esi, esi
0x180040c28  mov     rdx, qword ptr [rbp+57h+Msg.pt.x]; pt
0x180040c2c  lea     rcx, [rbp+57h+var_90]; lprc
0x180040c30  call    cs:__imp_PtInRect
0x180040c36  test    eax, eax
0x180040c38  jz      loc_180040D8A
0x180040c3e  mov     eax, [rbp+57h+var_90.top]
0x180040c41  xor     ebx, ebx
0x180040c43  cdq
0x180040c44  xor     r8d, r8d; wParam
0x180040c47  sub     eax, edx
0x180040c49  sar     eax, 1
0x180040c4b  mov     r9d, eax
  ... truncated ...
```
