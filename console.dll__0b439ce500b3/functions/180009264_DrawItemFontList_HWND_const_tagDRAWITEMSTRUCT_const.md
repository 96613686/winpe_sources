# DrawItemFontList(HWND__ * const,tagDRAWITEMSTRUCT * const)

- ea: `0x180009264`
- end: `0x18000956f`
- name: `?DrawItemFontList@@YAXQEAUHWND__@@QEAUtagDRAWITEMSTRUCT@@@Z`
- size: `779`
- prototype: `void __fastcall(HWND, struct tagDRAWITEMSTRUCT *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009980`

## callees

- `0x1800015b0`
- `0x180009264`
- `0x18000a87c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18000937c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x18000937c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000939f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800093c6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800093e1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000939f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800093c6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x1800093e1`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180009470`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800094ec`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180009470`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800094ec`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800094fb`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800094fb`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18000944e`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18000944e`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18000932b`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18000951f`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18000932b`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x18000951f`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x1800094d0`
- `ext-ms-win-gdi-draw-l1-1-0!BitBlt` at `0x1800094d0`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18000933c`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18000933c`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x1800092db`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x180009304`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x18000950d`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x1800092db`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x180009304`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x18000950d`
- `ext-ms-win-ntuser-draw-l1-1-0!DrawFocusRect` at `0x180009537`
- `ext-ms-win-ntuser-draw-l1-1-0!DrawFocusRect` at `0x180009537`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x18000935a`
- `ext-ms-win-ntuser-gui-l1-1-0!FillRect` at `0x18000935a`
- `ext-ms-win-ntuser-misc-l1-1-0!TabbedTextOutW` at `0x180009437`
- `ext-ms-win-ntuser-misc-l1-1-0!TabbedTextOutW` at `0x180009437`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180009369`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180009369`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x1800092ca`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x1800092f3`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180009318`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x1800092ca`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x1800092f3`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180009318`

## pseudocode

```c
void __fastcall DrawItemFontList(HWND a1, struct tagDRAWITEMSTRUCT *const a2)
{
  HDC hDC; // rsi
  UINT v4; // eax
  RECT *p_rcItem; // rdx
  DWORD SysColor; // eax
  COLORREF v7; // eax
  int v8; // ecx
  DWORD v9; // eax
  COLORREF v10; // r12d
  DWORD v11; // ebx
  COLORREF v12; // r13d
  HBRUSH SolidBrush; // rax
  HBRUSH v14; // rbx
  HWND hwndItem; // rbx
  int v16; // eax
  int nTabOrigin; // r15d
  int v18; // ebx
  __int64 chCount; // rcx
  HDC CompatibleDC; // rax
  HDC v21; // rbp
  int v22; // ebx
  int ItemHeight; // eax
  HGDIOBJ h; // [rsp+58h] [rbp-90h]
  WCHAR lParam[32]; // [rsp+60h] [rbp-88h] BYREF

  if ( (a2->itemID & 0x80000000) == 0 )
  {
    hDC = a2->hDC;
    v4 = a2->itemState & 1;
    if ( (a2->itemAction & 4) != 0 )
    {
      if ( !v4 )
        return;
      p_rcItem = &a2->rcItem;
      goto LABEL_23;
    }
    if ( v4 )
    {
      SysColor = GetSysColor(14);
      v7 = SetTextColor(hDC, SysColor);
      v8 = 13;
    }
    else
    {
      v9 = GetSysColor(8);
      v7 = SetTextColor(hDC, v9);
      v8 = 5;
    }
    v10 = v7;
    v11 = GetSysColor(v8);
    v12 = SetBkColor(hDC, v11);
    SolidBrush = CreateSolidBrush(v11);
    v14 = SolidBrush;
    if ( SolidBrush )
    {
      FillRect(hDC, &a2->rcItem, SolidBrush);
      DeleteObject(v14);
    }
    hwndItem = a2->hwndItem;
    if ( IsWindow(hwndItem) && (unsigned __int64)SendMessageW(hwndItem, 0x18Au, a2->itemID, 0) < 0x20 )
    {
      SendMessageW(hwndItem, 0x189u, a2->itemID, (LPARAM)lParam);
      v16 = SendMessageW(hwndItem, 0x199u, a2->itemID, 0);
      nTabOrigin = dword_1800237A4;
      v18 = v16;
      if ( v16 )
        nTabOrigin = 0;
      chCount = -1;
      do
        ++chCount;
      while ( lParam[chCount] );
      TabbedTextOutW(hDC, nTabOrigin + a2->rcItem.left, a2->rcItem.top, lParam, chCount, 0, 0, nTabOrigin);
      if ( !v18 )
      {
        CompatibleDC = CreateCompatibleDC(hDC);
        v21 = CompatibleDC;
        if ( CompatibleDC )
        {
          h = SelectObject(CompatibleDC, hbmTT);
          v22 = (a2->rcItem.bottom - a2->rcItem.top - dword_1800237A8) / 2;
          ItemHeight = GetItemHeight(a1);
          BitBlt(hDC, a2->rcItem.left, v22 + a2->rcItem.top, nTabOrigin, ItemHeight, v21, 0, 0, 0x660046u);
          if ( h )
            SelectObject(v21, h);
          DeleteDC(v21);
        }
      }
      SetTextColor(hDC, v10);
      SetBkColor(hDC, v12);
      if ( (a2->itemState & 0x10) != 0 )
      {
        p_rcItem = &a2->rcItem;
LABEL_23:
        DrawFocusRect(hDC, p_rcItem);
      }
    }
  }
}

```

## disassembly

```asm
0x180009264  mov     [rsp+arg_10], rbx
0x180009269  push    rbp
0x18000926a  push    rsi
0x18000926b  push    rdi
0x18000926c  push    r12
0x18000926e  push    r13
0x180009270  push    r14
0x180009272  push    r15
0x180009274  sub     rsp, 0B0h
0x18000927b  mov     rax, cs:__security_cookie
0x180009282  xor     rax, rsp
0x180009285  mov     [rsp+0E8h+var_48], rax
0x18000928d  xor     ebp, ebp
0x18000928f  mov     [rsp+0E8h+hWnd], rcx
0x180009294  mov     rdi, rdx
0x180009297  cmp     [rdx+8], ebp
0x18000929a  jl      loc_180009543
0x1800092a0  mov     eax, [rdx+10h]
0x1800092a3  mov     rsi, [rdx+20h]
0x1800092a7  and     eax, 1
0x1800092aa  test    byte ptr [rdx+0Ch], 4
0x1800092ae  jz      short loc_1800092C1
0x1800092b0  test    eax, eax
0x1800092b2  jz      loc_180009543
0x1800092b8  add     rdx, 28h ; '('
0x1800092bc  jmp     loc_180009534
0x1800092c1  test    eax, eax
0x1800092c3  jz      short loc_1800092EE
0x1800092c5  mov     ecx, 0Eh; nIndex
0x1800092ca  call    cs:__imp_GetSysColor
0x1800092d1  nop     dword ptr [rax+rax+00h]
0x1800092d6  mov     edx, eax; color
0x1800092d8  mov     rcx, rsi; hdc
0x1800092db  call    cs:__imp_SetTextColor
0x1800092e2  nop     dword ptr [rax+rax+00h]
0x1800092e7  mov     ecx, 0Dh
0x1800092ec  jmp     short loc_180009315
0x1800092ee  mov     ecx, 8; nIndex
0x1800092f3  call    cs:__imp_GetSysColor
0x1800092fa  nop     dword ptr [rax+rax+00h]
0x1800092ff  mov     edx, eax; color
0x180009301  mov     rcx, rsi; hdc
0x180009304  call    cs:__imp_SetTextColor
0x18000930b  nop     dword ptr [rax+rax+00h]
0x180009310  mov     ecx, 5; nIndex
0x180009315  mov     r12d, eax
0x180009318  call    cs:__imp_GetSysColor
0x18000931f  nop     dword ptr [rax+rax+00h]
0x180009324  mov     edx, eax; color
0x180009326  mov     rcx, rsi; hdc
0x180009329  mov     ebx, eax
0x18000932b  call    cs:__imp_SetBkColor
0x180009332  nop     dword ptr [rax+rax+00h]
0x180009337  mov     ecx, ebx; color
0x180009339  mov     r13d, eax
0x18000933c  call    cs:__imp_CreateSolidBrush
0x180009343  nop     dword ptr [rax+rax+00h]
0x180009348  mov     rbx, rax
0x18000934b  test    rax, rax
0x18000934e  jz      short loc_180009375
0x180009350  lea     rdx, [rdi+28h]; lprc
0x180009354  mov     r8, rax; hbr
0x180009357  mov     rcx, rsi; hDC
0x18000935a  call    cs:__imp_FillRect
0x180009361  nop     dword ptr [rax+rax+00h]
0x180009366  mov     rcx, rbx; ho
0x180009369  call    cs:__imp_DeleteObject
0x180009370  nop     dword ptr [rax+rax+00h]
0x180009375  mov     rbx, [rdi+18h]
0x180009379  mov     rcx, rbx; hWnd
0x18000937c  call    cs:__imp_IsWindow
0x180009383  nop     dword ptr [rax+rax+00h]
0x180009388  test    eax, eax
0x18000938a  jz      loc_180009543
0x180009390  mov     r8d, [rdi+8]; wParam
0x180009394  xor     r9d, r9d; lParam
0x180009397  mov     edx, 18Ah; Msg
0x18000939c  mov     rcx, rbx; hWnd
0x18000939f  call    cs:__imp_SendMessageW
0x1800093a6  nop     dword ptr [rax+rax+00h]
0x1800093ab  cmp     rax, 20h ; ' '
0x1800093af  jnb     loc_180009543
0x1800093b5  mov     r8d, [rdi+8]; wParam
0x1800093b9  lea     r9, [rsp+0E8h+lParam]; lParam
0x1800093be  mov     edx, 189h; Msg
0x1800093c3  mov     rcx, rbx; hWnd
0x1800093c6  call    cs:__imp_SendMessageW
0x1800093cd  nop     dword ptr [rax+rax+00h]
0x1800093d2  mov     r8d, [rdi+8]; wParam
0x1800093d6  xor     r9d, r9d; lParam
0x1800093d9  mov     edx, 199h; Msg
0x1800093de  mov     rcx, rbx; hWnd
0x1800093e1  call    cs:__imp_SendMessageW
0x1800093e8  nop     dword ptr [rax+rax+00h]
0x1800093ed  mov     r15d, cs:dword_1800237A4
0x1800093f4  test    eax, eax
0x1800093f6  mov     rbx, rax
0x1800093f9  lea     rax, [rsp+0E8h+lParam]
0x1800093fe  cmovnz  r15d, ebp
0x180009402  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180009406  inc     rcx
0x180009409  cmp     [rax+rcx*2], bp
0x18000940d  jnz     short loc_180009406
0x18000940f  mov     [rsp+0E8h+nTabOrigin], r15d; nTabOrigin
0x180009414  lea     r14, [rdi+28h]
0x180009418  mov     edx, [r14]
0x18000941b  lea     r9, [rsp+0E8h+lParam]; lpString
0x180009420  mov     r8d, [r14+4]; y
0x180009424  add     edx, r15d; x
0x180009427  mov     [rsp+0E8h+lpnTabStopPositions], rbp; lpnTabStopPositions
0x18000942c  mov     [rsp+0E8h+nTabPositions], ebp; nTabPositions
0x180009430  mov     [rsp+0E8h+chCount], ecx; chCount
0x180009434  mov     rcx, rsi; hdc
0x180009437  call    cs:__imp_TabbedTextOutW
0x18000943e  nop     dword ptr [rax+rax+00h]
0x180009443  test    ebx, ebx
0x180009445  jnz     loc_180009507
0x18000944b  mov     rcx, rsi; hdc
0x18000944e  call    cs:__imp_CreateCompatibleDC
0x180009455  nop     dword ptr [rax+rax+00h]
0x18000945a  mov     rbp, rax
0x18000945d  test    rax, rax
0x180009460  jz      loc_180009507
0x180009466  mov     rdx, cs:?hbmTT@@3PEAUHBITMAP__@@EA; h
0x18000946d  mov     rcx, rax; hdc
0x180009470  call    cs:__imp_SelectObject
0x180009477  nop     dword ptr [rax+rax+00h]
0x18000947c  mov     [rsp+0E8h+h], rax
0x180009481  lea     ecx, [rbx+2]
0x180009484  mov     eax, [rdi+34h]
0x180009487  sub     eax, [rdi+2Ch]
0x18000948a  sub     eax, cs:dword_1800237A8
0x180009490  cdq
0x180009491  idiv    ecx
0x180009493  mov     rcx, [rsp+0E8h+hWnd]; hWnd
0x180009498  mov     ebx, eax
0x18000949a  call    ?GetItemHeight@@YAIQEAUHWND__@@@Z; GetItemHeight(HWND__ * const)
0x18000949f  mov     r8d, [rdi+2Ch]
0x1800094a3  mov     r9d, r15d; cx
0x1800094a6  mov     edx, [r14]; x
0x1800094a9  add     r8d, ebx; y
0x1800094ac  mov     [rsp+0E8h+rop], 660046h; rop
0x1800094b4  mov     rcx, rsi; hdc
0x1800094b7  mov     [rsp+0E8h+nTabOrigin], 0; y1
0x1800094bf  mov     dword ptr [rsp+0E8h+lpnTabStopPositions], 0; x1
0x1800094c7  mov     qword ptr [rsp+0E8h+nTabPositions], rbp; hdcSrc
0x1800094cc  mov     [rsp+0E8h+chCount], eax; cy
0x1800094d0  call    cs:__imp_BitBlt
0x1800094d7  nop     dword ptr [rax+rax+00h]
0x1800094dc  mov     rax, [rsp+0E8h+h]
0x1800094e1  test    rax, rax
0x1800094e4  jz      short loc_1800094F8
0x1800094e6  mov     rdx, rax; h
0x1800094e9  mov     rcx, rbp; hdc
0x1800094ec  call    cs:__imp_SelectObject
0x1800094f3  nop     dword ptr [rax+rax+00h]
0x1800094f8  mov     rcx, rbp; hdc
0x1800094fb  call    cs:__imp_DeleteDC
0x180009502  nop     dword ptr [rax+rax+00h]
0x180009507  mov     edx, r12d; color
0x18000950a  mov     rcx, rsi; hdc
0x18000950d  call    cs:__imp_SetTextColor
0x180009514  nop     dword ptr [rax+rax+00h]
0x180009519  mov     edx, r13d; color
0x18000951c  mov     rcx, rsi; hdc
0x18000951f  call    cs:__imp_SetBkColor
0x180009526  nop     dword ptr [rax+rax+00h]
0x18000952b  test    byte ptr [rdi+10h], 10h
0x18000952f  jz      short loc_180009543
0x180009531  mov     rdx, r14; lprc
0x180009534  mov     rcx, rsi; hDC
0x180009537  call    cs:__imp_DrawFocusRect
0x18000953e  nop     dword ptr [rax+rax+00h]
0x180009543  mov     rcx, [rsp+0E8h+var_48]
0x18000954b  xor     rcx, rsp; StackCookie
0x18000954e  call    __security_check_cookie
0x180009553  mov     rbx, [rsp+0E8h+arg_10]
0x18000955b  add     rsp, 0B0h
0x180009562  pop     r15
0x180009564  pop     r14
0x180009566  pop     r13
0x180009568  pop     r12
0x18000956a  pop     rdi
0x18000956b  pop     rsi
0x18000956c  pop     rbp
0x18000956d  retn
```
