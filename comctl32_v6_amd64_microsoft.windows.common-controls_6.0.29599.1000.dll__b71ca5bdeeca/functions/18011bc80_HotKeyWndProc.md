# HotKeyWndProc

- ea: `0x18011bc80`
- end: `0x18011c266`
- name: `HotKeyWndProc`
- size: `1510`
- prototype: `__int64 __fastcall(HWND, UINT Msg, HGDIOBJ h, LPARAM lParam)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180026340`
- `0x18004c95c`
- `0x1800bcfec`
- `0x1800d70d4`
- `0x180114520`
- `0x18011baa8`
- `0x18011bb70`
- `0x18011bbb0`
- `0x18011bbfc`
- `0x18011bc80`
- `0x18011c26c`
- `0x18011c5a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18011bdb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18011bdb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011bdbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18011bdbf`
- `USER32!GetKeyState` at `0x18011c0b8`
- `USER32!GetKeyState` at `0x18011c0cd`
- `USER32!GetKeyState` at `0x18011c0eb`
- `USER32!GetKeyState` at `0x18011c0b8`
- `USER32!GetKeyState` at `0x18011c0cd`
- `USER32!GetKeyState` at `0x18011c0eb`
- `USER32!DestroyCaret` at `0x18011bd3c`
- `USER32!DestroyCaret` at `0x18011bd3c`
- `USER32!CreateCaret` at `0x18011bd6c`
- `USER32!CreateCaret` at `0x18011bd6c`
- `USER32!GetClassLongPtrW` at `0x18011bf06`
- `USER32!GetClassLongPtrW` at `0x18011bf06`
- `USER32!ShowCaret` at `0x18011bd75`
- `USER32!ShowCaret` at `0x18011be9b`
- `USER32!ShowCaret` at `0x18011bd75`
- `USER32!ShowCaret` at `0x18011be9b`
- `USER32!HideCaret` at `0x18011be40`
- `USER32!HideCaret` at `0x18011be40`
- `USER32!FillRect` at `0x18011be86`
- `USER32!FillRect` at `0x18011be86`
- `USER32!GetSysColorBrush` at `0x18011be75`
- `USER32!GetSysColorBrush` at `0x18011be75`
- `USER32!IsWindowEnabled` at `0x18011be63`
- `USER32!IsWindowEnabled` at `0x18011be63`
- `USER32!SetFocus` at `0x18011c197`
- `USER32!SetFocus` at `0x18011c197`
- `USER32!DefWindowProcW` at `0x18011c18c`
- `USER32!DefWindowProcW` at `0x18011c18c`
- `USER32!GetDC` at `0x18011be49`
- `USER32!GetDC` at `0x18011be49`
- `USER32!SetWindowLongPtrW` at `0x18011bdcf`
- `USER32!SetWindowLongPtrW` at `0x18011be28`
- `USER32!SetWindowLongPtrW` at `0x18011bdcf`
- `USER32!SetWindowLongPtrW` at `0x18011be28`
- `USER32!GetSystemMetrics` at `0x18011bf2a`
- `USER32!GetSystemMetrics` at `0x18011bf37`
- `USER32!GetSystemMetrics` at `0x18011bf2a`
- `USER32!GetSystemMetrics` at `0x18011bf37`
- `USER32!GetWindowLongPtrW` at `0x18011bd1e`
- `USER32!GetWindowLongPtrW` at `0x18011bd5b`
- `USER32!GetWindowLongPtrW` at `0x18011bd85`
- `USER32!GetWindowLongPtrW` at `0x18011bda3`
- `USER32!GetWindowLongPtrW` at `0x18011bedc`
- `USER32!GetWindowLongPtrW` at `0x18011bfb7`
- `USER32!GetWindowLongPtrW` at `0x18011c018`
- `USER32!GetWindowLongPtrW` at `0x18011c12e`
- `USER32!GetWindowLongPtrW` at `0x18011c140`
- `USER32!GetWindowLongPtrW` at `0x18011c1d5`
- `USER32!GetWindowLongPtrW` at `0x18011c1e6`
- `USER32!GetWindowLongPtrW` at `0x18011bd1e`
- `USER32!GetWindowLongPtrW` at `0x18011bd5b`
- `USER32!GetWindowLongPtrW` at `0x18011bd85`
- `USER32!GetWindowLongPtrW` at `0x18011bda3`
- `USER32!GetWindowLongPtrW` at `0x18011bedc`
- `USER32!GetWindowLongPtrW` at `0x18011bfb7`
- `USER32!GetWindowLongPtrW` at `0x18011c018`
- `USER32!GetWindowLongPtrW` at `0x18011c12e`
- `USER32!GetWindowLongPtrW` at `0x18011c140`
- `USER32!GetWindowLongPtrW` at `0x18011c1d5`
- `USER32!GetWindowLongPtrW` at `0x18011c1e6`
- `USER32!GetClientRect` at `0x18011be5a`
- `USER32!GetClientRect` at `0x18011be5a`
- `USER32!InvalidateRect` at `0x18011bd11`
- `USER32!InvalidateRect` at `0x18011bd4d`
- `USER32!InvalidateRect` at `0x18011bd11`
- `USER32!InvalidateRect` at `0x18011bd4d`
- `USER32!ReleaseDC` at `0x18011be92`
- `USER32!ReleaseDC` at `0x18011be92`
- `UxTheme!OpenThemeData` at `0x18011be14`
- `UxTheme!OpenThemeData` at `0x18011be14`
- `UxTheme!CloseThemeData` at `0x18011bd95`
- `UxTheme!CloseThemeData` at `0x18011bd95`

## string_xrefs

- `0x18011be0a`: `Combobox`

## pseudocode

```c
LONG_PTR __fastcall HotKeyWndProc(HWND a1, UINT Msg, char *h, LPARAM lParam)
{
  HRGN v5; // r15
  HWND v7; // rsi
  int v8; // eax
  void *v9; // rax
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  HTHEME v12; // rax
  HDC DC; // rbx
  BOOL v14; // eax
  int v15; // ecx
  HBRUSH SysColorBrush; // rax
  HRGN v17; // r13
  int dy; // ecx
  int v19; // eax
  unsigned __int16 v21; // bx
  unsigned __int16 v22; // di
  unsigned __int16 v23; // r13
  __int64 v24; // rbx
  unsigned __int8 WindowLongPtrW; // bl
  int SystemMetrics; // [rsp+40h] [rbp-78h]
  HBRUSH ClassLongPtrW; // [rsp+48h] [rbp-70h]
  HTHEME hTheme; // [rsp+50h] [rbp-68h]
  struct tagRECT Rect; // [rsp+58h] [rbp-60h] BYREF

  v5 = (HRGN)h;
  v7 = a1;
  Rect = 0;
  if ( Msg > 0x87 )
  {
    if ( Msg > 0x201 )
    {
      switch ( Msg )
      {
        case 0x2E2u:
          if ( !(unsigned int)HotKeyEnsureDPISCALEINFO(a1) || !(unsigned int)DPISCALEINFO::HandleDPIChanged(0, v7, 11) )
            return 0;
          break;
        case 0x31Au:
          break;
        case 0x401u:
LABEL_88:
          SetHotKey(a1);
          return 0;
        case 0x402u:
          WindowLongPtrW = GetWindowLongPtrW(a1, 0);
          return WindowLongPtrW + ((unsigned __int64)(unsigned __int8)GetWindowLongPtrW(v7, 8) << 8);
        case 0x403u:
          HKMSetRules(a1, h, (unsigned __int16)lParam);
          return 0;
        default:
          return DefWindowProcW(v7, Msg, (WPARAM)v5, lParam);
      }
      HKUpdateTheme(v7);
      return 0;
    }
    if ( Msg == 513 )
    {
      SetFocus(a1);
      return 0;
    }
    if ( Msg != 256 )
    {
      if ( Msg == 257 || Msg == 258 )
      {
LABEL_55:
        if ( GetWindowLongPtrW(a1, 0) )
          return 0;
        goto LABEL_77;
      }
      if ( Msg != 260 )
      {
        if ( Msg - 261 > 1 )
          return DefWindowProcW(v7, Msg, (WPARAM)v5, lParam);
        goto LABEL_55;
      }
    }
    if ( (unsigned __int64)h > 0x1B )
    {
      if ( h != (char *)32 && h != (char *)46 && h != (char *)91 && (unsigned __int64)(h - 92) >= 2 )
      {
LABEL_69:
        v21 = (GetKeyState(17) >> 15) & 2;
        v22 = v21 | 1;
        if ( GetKeyState(16) >= 0 )
          v22 = v21;
        v23 = v22 | 4;
        if ( GetKeyState(18) >= 0 )
          v23 = v22;
        if ( (unsigned __int16)((_WORD)v5 - 112) > 0x17u && (unsigned __int16)((_WORD)v5 - 96) > 0xFu )
        {
          v24 = s_Combos[v23];
          if ( (GetWindowLongPtrW(v7, 16) & v24) != 0 )
            GetWindowLongPtrW(v7, 24);
        }
LABEL_77:
        a1 = v7;
        goto LABEL_88;
      }
    }
    else if ( h != (char *)27 && h != (char *)8 && h != (char *)9 && h != (char *)13 )
    {
      if ( h == (char *)16 || (unsigned __int64)(h - 17) <= 1 )
        LOWORD(v5) = 0;
      goto LABEL_69;
    }
    SetHotKey(a1);
    return DefWindowProcW(v7, Msg, (WPARAM)v5, lParam);
  }
  if ( Msg == 135 )
    return 129;
  if ( Msg > 0x14 )
  {
    switch ( Msg )
    {
      case '0':
        return HKMSetFont(a1, h);
      case '1':
        return GetWindowLongPtrW(a1, 32);
      case '=':
        if ( (_DWORD)lParam == -12 )
          return 65552;
        return DefWindowProcW(v7, Msg, (WPARAM)v5, lParam);
    }
    if ( Msg != 129 )
    {
      if ( Msg == 133 )
      {
        hTheme = (HTHEME)GetWindowLongPtrW(a1, 48);
        if ( hTheme )
        {
          v17 = 0;
          if ( v5 != (HRGN)1 )
            v17 = v5;
          ClassLongPtrW = (HBRUSH)GetClassLongPtrW(v7, -10);
          if ( (unsigned int)HotKeyEnsureDPISCALEINFO(v7) )
          {
            SystemMetrics = GetSystemMetrics(45);
            dy = GetSystemMetrics(46);
            v19 = SystemMetrics;
          }
          else
          {
            v19 = 0;
            dy = 0;
          }
          if ( (unsigned int)CCDrawNonClientTheme(hTheme, v7, v17, ClassLongPtrW, 4, 1, v19, dy) )
            return 0;
        }
      }
      return DefWindowProcW(v7, Msg, (WPARAM)v5, lParam);
    }
    SetWindowBits(a1, -20);
    InitGlobalColors();
    return 1;
  }
  switch ( Msg )
  {
    case 0x14u:
      HideCaret(a1);
      DC = GetDC(v7);
      GetClientRect(v7, &Rect);
      v14 = IsWindowEnabled(v7);
      v15 = 5;
      if ( !v14 )
        v15 = 15;
      SysColorBrush = GetSysColorBrush(v15);
      FillRect(DC, &Rect, SysColorBrush);
      ReleaseDC(v7, DC);
      ShowCaret(v7);
      return 1;
    case 1u:
      SetHotKey(a1);
      HKMSetRules(v7, 0, 0);
      HKMSetFont(v7, g_hfontSystem);
      v12 = OpenThemeData(v7, L"Combobox");
      if ( v12 )
        SetWindowLongPtrW(v7, 48, (LONG_PTR)v12);
      HotKeyEnsureDPISCALEINFO(v7);
      return 0;
    case 2u:
      v9 = (void *)GetWindowLongPtrW(a1, 48);
      if ( v9 )
        CloseThemeData(v9);
      v10 = (void *)GetWindowLongPtrW(v7, 56);
      if ( v10 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v10);
      }
      SetWindowLongPtrW(v7, 56, 0);
      return 0;
    case 7u:
      InvalidateRect(a1, 0, 1);
      v8 = GetWindowLongPtrW(v7, 40);
      CreateCaret(v7, 0, 0, v8);
      ShowCaret(v7);
      return 0;
    case 8u:
      if ( !GetWindowLongPtrW(a1, 0) )
        SetHotKey(v7);
      DestroyCaret();
      return 0;
    case 0xAu:
      InvalidateRect(a1, 0, 1);
      return DefWindowProcW(v7, Msg, (WPARAM)v5, lParam);
  }
  if ( Msg != 15 )
    return DefWindowProcW(v7, Msg, (WPARAM)v5, lParam);
  PaintHotKey(a1);
  return 0;
}

```

## disassembly

```asm
0x18011bc80  push    rbx
0x18011bc82  push    rbp
0x18011bc83  push    rsi
0x18011bc84  push    rdi
0x18011bc85  push    r12
0x18011bc87  push    r13
0x18011bc89  push    r14
0x18011bc8b  push    r15
0x18011bc8d  sub     rsp, 78h
0x18011bc91  mov     rax, cs:__security_cookie
0x18011bc98  xor     rax, rsp
0x18011bc9b  mov     [rsp+0B8h+var_50], rax
0x18011bca0  mov     eax, 87h
0x18011bca5  xorps   xmm0, xmm0
0x18011bca8  mov     r12, r9
0x18011bcab  mov     r15, r8
0x18011bcae  mov     ebx, edx
0x18011bcb0  mov     rsi, rcx
0x18011bcb3  movups  xmmword ptr [rsp+0B8h+Rect.left], xmm0
0x18011bcb8  cmp     edx, eax
0x18011bcba  ja      loc_18011BFD9
0x18011bcc0  jz      loc_18011BFCF
0x18011bcc6  cmp     edx, 14h
0x18011bcc9  ja      loc_18011BEA6
0x18011bccf  jz      loc_18011BE40
0x18011bcd5  mov     eax, edx
0x18011bcd7  sub     eax, 1
0x18011bcda  jz      loc_18011BDDA
0x18011bce0  sub     eax, 1
0x18011bce3  jz      loc_18011BD80
0x18011bce9  sub     eax, 5
0x18011bcec  jz      short loc_18011BD47
0x18011bcee  sub     eax, 1
0x18011bcf1  jz      short loc_18011BD1C
0x18011bcf3  sub     eax, 2
0x18011bcf6  jz      short loc_18011BD0B
0x18011bcf8  cmp     eax, 5
0x18011bcfb  jnz     loc_18011C181
0x18011bd01  call    PaintHotKey
0x18011bd06  jmp     loc_18011C246
0x18011bd0b  xor     edx, edx; lpRect
0x18011bd0d  lea     r8d, [rdx+1]; bErase
0x18011bd11  call    cs:__imp_InvalidateRect
0x18011bd17  jmp     loc_18011C181
0x18011bd1c  xor     edx, edx; nIndex
0x18011bd1e  call    cs:__imp_GetWindowLongPtrW
0x18011bd24  xor     ebp, ebp
0x18011bd26  test    rax, rax
0x18011bd29  jnz     short loc_18011BD3C
0x18011bd2b  xor     r8d, r8d
0x18011bd2e  lea     r9d, [rbp+1]
0x18011bd32  xor     edx, edx
0x18011bd34  mov     rcx, rsi; hwnd
0x18011bd37  call    SetHotKey
0x18011bd3c  call    cs:__imp_DestroyCaret
0x18011bd42  jmp     loc_18011C246
0x18011bd47  xor     edx, edx; lpRect
0x18011bd49  lea     r8d, [rdx+1]; bErase
0x18011bd4d  call    cs:__imp_InvalidateRect
0x18011bd53  mov     edx, 28h ; '('; nIndex
0x18011bd58  mov     rcx, rsi; hWnd
0x18011bd5b  call    cs:__imp_GetWindowLongPtrW
0x18011bd61  xor     r8d, r8d; nWidth
0x18011bd64  xor     edx, edx; hBitmap
0x18011bd66  mov     r9, rax; nHeight
0x18011bd69  mov     rcx, rsi; hWnd
0x18011bd6c  call    cs:__imp_CreateCaret
0x18011bd72  mov     rcx, rsi; hWnd
0x18011bd75  call    cs:__imp_ShowCaret
0x18011bd7b  jmp     loc_18011C246
0x18011bd80  mov     edx, 30h ; '0'; nIndex
0x18011bd85  call    cs:__imp_GetWindowLongPtrW
0x18011bd8b  xor     ebp, ebp
0x18011bd8d  test    rax, rax
0x18011bd90  jz      short loc_18011BD9B
0x18011bd92  mov     rcx, rax; hTheme
0x18011bd95  call    cs:__imp_CloseThemeData
0x18011bd9b  mov     edx, 38h ; '8'; nIndex
0x18011bda0  mov     rcx, rsi; hWnd
0x18011bda3  call    cs:__imp_GetWindowLongPtrW
0x18011bda9  mov     rbx, rax
0x18011bdac  test    rax, rax
0x18011bdaf  jz      short loc_18011BDC5
0x18011bdb1  call    cs:__imp_GetProcessHeap
0x18011bdb7  mov     r8, rbx; lpMem
0x18011bdba  xor     edx, edx; dwFlags
0x18011bdbc  mov     rcx, rax; hHeap
0x18011bdbf  call    cs:__imp_HeapFree
0x18011bdc5  xor     r8d, r8d; dwNewLong
0x18011bdc8  mov     rcx, rsi; hWnd
0x18011bdcb  lea     edx, [r8+38h]; nIndex
0x18011bdcf  call    cs:__imp_SetWindowLongPtrW
0x18011bdd5  jmp     loc_18011C246
0x18011bdda  xor     ebp, ebp
0x18011bddc  xor     r8d, r8d
0x18011bddf  xor     edx, edx
0x18011bde1  mov     qword ptr [rsp+0B8h+var_78], rbp
0x18011bde6  xor     r9d, r9d
0x18011bde9  call    SetHotKey
0x18011bdee  xor     r8d, r8d
0x18011bdf1  xor     edx, edx
0x18011bdf3  mov     rcx, rsi
0x18011bdf6  call    HKMSetRules
0x18011bdfb  mov     rdx, cs:g_hfontSystem; h
0x18011be02  mov     rcx, rsi; hWnd
0x18011be05  call    HKMSetFont
0x18011be0a  lea     rdx, pszSubAppName; "Combobox"
0x18011be11  mov     rcx, rsi; hwnd
0x18011be14  call    cs:__imp_OpenThemeData
0x18011be1a  test    rax, rax
0x18011be1d  jz      short loc_18011BE2E
0x18011be1f  mov     r8, rax; dwNewLong
0x18011be22  lea     edx, [rbp+30h]; nIndex
0x18011be25  mov     rcx, rsi; hWnd
0x18011be28  call    cs:__imp_SetWindowLongPtrW
0x18011be2e  lea     rdx, [rsp+0B8h+var_78]
0x18011be33  mov     rcx, rsi; HWND
0x18011be36  call    HotKeyEnsureDPISCALEINFO
0x18011be3b  jmp     loc_18011C246
0x18011be40  call    cs:__imp_HideCaret
0x18011be46  mov     rcx, rsi; hWnd
0x18011be49  call    cs:__imp_GetDC
0x18011be4f  lea     rdx, [rsp+0B8h+Rect]; lpRect
0x18011be54  mov     rcx, rsi; hWnd
0x18011be57  mov     rbx, rax
0x18011be5a  call    cs:__imp_GetClientRect
0x18011be60  mov     rcx, rsi; hWnd
0x18011be63  call    cs:__imp_IsWindowEnabled
0x18011be69  xor     ebp, ebp
0x18011be6b  lea     ecx, [rbp+5]
0x18011be6e  test    eax, eax
0x18011be70  jnz     short loc_18011BE75
0x18011be72  lea     ecx, [rbp+0Fh]; nIndex
0x18011be75  call    cs:__imp_GetSysColorBrush
0x18011be7b  lea     rdx, [rsp+0B8h+Rect]; lprc
0x18011be80  mov     rcx, rbx; hDC
0x18011be83  mov     r8, rax; hbr
0x18011be86  call    cs:__imp_FillRect
0x18011be8c  mov     rdx, rbx; hDC
0x18011be8f  mov     rcx, rsi; hWnd
0x18011be92  call    cs:__imp_ReleaseDC
0x18011be98  mov     rcx, rsi; hWnd
0x18011be9b  call    cs:__imp_ShowCaret
0x18011bea1  jmp     loc_18011BF94
0x18011bea6  mov     eax, ebx
0x18011bea8  sub     eax, 30h ; '0'
0x18011beab  jz      loc_18011BFC2
0x18011beb1  sub     eax, 1
0x18011beb4  jz      loc_18011BFB2
0x18011beba  sub     eax, 0Ch
0x18011bebd  jz      loc_18011BF9E
0x18011bec3  sub     eax, 44h ; 'D'
0x18011bec6  jz      loc_18011BF7C
0x18011becc  mov     edi, 4
0x18011bed1  cmp     eax, edi
0x18011bed3  jnz     loc_18011C181
0x18011bed9  lea     edx, [rdi+2Ch]; nIndex
0x18011bedc  call    cs:__imp_GetWindowLongPtrW
0x18011bee2  xor     ebp, ebp
0x18011bee4  mov     [rsp+0B8h+hTheme], rax
0x18011bee9  test    rax, rax
0x18011beec  jz      loc_18011C181
0x18011bef2  lea     r14d, [rdi-3]
0x18011bef6  mov     r13d, ebp
0x18011bef9  cmp     r15, r14
0x18011befc  lea     edx, [rdi-0Eh]; nIndex
0x18011beff  mov     rcx, rsi; hWnd
0x18011bf02  cmovnz  r13, r15
0x18011bf06  call    cs:__imp_GetClassLongPtrW
0x18011bf0c  lea     rdx, [rsp+0B8h+var_78]
0x18011bf11  mov     qword ptr [rsp+0B8h+var_78], rbp
0x18011bf16  mov     rcx, rsi; HWND
0x18011bf19  mov     [rsp+0B8h+var_70], rax
0x18011bf1e  call    HotKeyEnsureDPISCALEINFO
0x18011bf23  test    eax, eax
0x18011bf25  jz      short loc_18011BF45
0x18011bf27  lea     ecx, [rdi+29h]; nIndex
0x18011bf2a  call    cs:__imp_GetSystemMetrics
0x18011bf30  lea     ecx, [rdi+2Ah]; nIndex
0x18011bf33  mov     [rsp+0B8h+var_78], eax
0x18011bf37  call    cs:__imp_GetSystemMetrics
0x18011bf3d  mov     ecx, eax
0x18011bf3f  mov     eax, [rsp+0B8h+var_78]
0x18011bf43  jmp     short loc_18011BF49
0x18011bf45  mov     eax, ebp
0x18011bf47  mov     ecx, ebp
0x18011bf49  mov     r9, [rsp+0B8h+var_70]
0x18011bf4e  mov     r8, r13; hrgnSrc1
0x18011bf51  mov     [rsp+0B8h+dy], ecx; dy
0x18011bf55  mov     rdx, rsi; hWnd
0x18011bf58  mov     rcx, [rsp+0B8h+hTheme]; hTheme
0x18011bf5d  mov     [rsp+0B8h+var_88], eax; int
0x18011bf61  mov     [rsp+0B8h+iStateId], r14d; iStateId
0x18011bf66  mov     [rsp+0B8h+iPartId], edi; iPartId
0x18011bf6a  call    CCDrawNonClientTheme
0x18011bf6f  test    eax, eax
0x18011bf71  jnz     loc_18011C246
0x18011bf77  jmp     loc_18011C181
0x18011bf7c  mov     r8d, 200h
0x18011bf82  mov     edx, 0FFFFFFECh; nIndex
0x18011bf87  mov     r9d, r8d
0x18011bf8a  call    SetWindowBits
0x18011bf8f  call    InitGlobalColors
0x18011bf94  mov     eax, 1
0x18011bf99  jmp     loc_18011C248
0x18011bf9e  cmp     r12d, 0FFFFFFF4h
0x18011bfa2  jnz     loc_18011C181
0x18011bfa8  mov     eax, 10010h
0x18011bfad  jmp     loc_18011C248
0x18011bfb2  mov     edx, 20h ; ' '; nIndex
0x18011bfb7  call    cs:__imp_GetWindowLongPtrW
0x18011bfbd  jmp     loc_18011C248
0x18011bfc2  mov     rdx, r15; h
0x18011bfc5  call    HKMSetFont
0x18011bfca  jmp     loc_18011C248
0x18011bfcf  mov     eax, 81h
0x18011bfd4  jmp     loc_18011C248
0x18011bfd9  mov     eax, 201h
0x18011bfde  cmp     ebx, eax
0x18011bfe0  ja      loc_18011C1A2
0x18011bfe6  jz      loc_18011C197
0x18011bfec  mov     eax, ebx
0x18011bfee  mov     edi, 2
0x18011bff3  sub     eax, 100h
0x18011bff8  jz      short loc_18011C037
0x18011bffa  sub     eax, 1
0x18011bffd  jz      short loc_18011C016
0x18011bfff  sub     eax, 1
0x18011c002  jz      short loc_18011C016
0x18011c004  sub     eax, edi
0x18011c006  jz      short loc_18011C037
0x18011c008  sub     eax, 1
0x18011c00b  jz      short loc_18011C016
0x18011c00d  cmp     eax, 1
0x18011c010  jnz     loc_18011C181
0x18011c016  xor     edx, edx; nIndex
0x18011c018  call    cs:__imp_GetWindowLongPtrW
0x18011c01e  xor     ebp, ebp
0x18011c020  test    rax, rax
0x18011c023  jnz     loc_18011C246
0x18011c029  xor     r8d, r8d
0x18011c02c  lea     r9d, [rbp+1]
0x18011c030  xor     edx, edx
0x18011c032  jmp     loc_18011C16B
0x18011c037  xor     ebp, ebp
0x18011c039  cmp     r15, 1Bh
0x18011c03d  ja      short loc_18011C07E
0x18011c03f  jz      loc_18011C173
0x18011c045  mov     rax, r15
0x18011c048  sub     rax, 8
0x18011c04c  jz      loc_18011C173
0x18011c052  sub     rax, 1
0x18011c056  jz      loc_18011C173
0x18011c05c  sub     rax, 4
0x18011c060  jz      loc_18011C173
0x18011c066  sub     rax, 3
0x18011c06a  jz      short loc_18011C078
0x18011c06c  sub     rax, 1
0x18011c070  jz      short loc_18011C078
0x18011c072  cmp     rax, 1
0x18011c076  jnz     short loc_18011C0B3
0x18011c078  movzx   r15d, bp
0x18011c07c  jmp     short loc_18011C0B3
0x18011c07e  mov     rax, r15
0x18011c081  sub     rax, 20h ; ' '
0x18011c085  jz      loc_18011C173
0x18011c08b  sub     rax, 0Eh
0x18011c08f  jz      loc_18011C173
0x18011c095  sub     rax, 2Dh ; '-'
0x18011c099  jz      loc_18011C173
0x18011c09f  sub     rax, 1
0x18011c0a3  jz      loc_18011C173
0x18011c0a9  cmp     rax, 1
0x18011c0ad  jz      loc_18011C173
0x18011c0b3  mov     ecx, 11h; nVirtKey
0x18011c0b8  call    cs:__imp_GetKeyState
0x18011c0be  movzx   ebx, ax
0x18011c0c1  mov     ecx, 10h; nVirtKey
0x18011c0c6  sar     bx, 0Fh
0x18011c0ca  and     bx, di
0x18011c0cd  call    cs:__imp_GetKeyState
0x18011c0d3  mov     r14d, 1
0x18011c0d9  movzx   edi, bx
0x18011c0dc  or      di, r14w
0x18011c0e0  test    ax, ax
0x18011c0e3  lea     ecx, [r14+11h]; nVirtKey
0x18011c0e7  cmovns  di, bx
0x18011c0eb  call    cs:__imp_GetKeyState
0x18011c0f1  movzx   r13d, di
0x18011c0f5  or      r13w, 4
0x18011c0fa  test    ax, ax
0x18011c0fd  lea     eax, [r15-70h]
0x18011c101  cmovns  r13w, di
0x18011c106  cmp     ax, 17h
0x18011c10a  jbe     short loc_18011C148
0x18011c10c  lea     eax, [r15-60h]
0x18011c110  lea     ecx, [r14+0Eh]
0x18011c114  cmp     ax, cx
0x18011c117  jbe     short loc_18011C148
0x18011c119  movzx   eax, r13w
  ... truncated ...
```
