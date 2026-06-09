# ComboBox_ShowListBoxWindow(tagCBox *,int)

- ea: `0x18013e5c0`
- end: `0x18013e9fa`
- name: `?ComboBox_ShowListBoxWindow@@YAXPEAUtagCBox@@H@Z`
- size: `1082`
- prototype: `void __fastcall(struct tagCBox *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b36a0`
- `0x1801486c8`

## callees

- `0x1800bddac`
- `0x1800cadcc`
- `0x1800df60c`
- `0x180114520`
- `0x18013e5c0`
- `0x18013ea00`
- `0x18013edf0`

## import_xrefs

- `USER32!GetMonitorInfoW` at `0x18013e7f2`
- `USER32!GetMonitorInfoW` at `0x18013e7f2`
- `USER32!MonitorFromWindow` at `0x18013e7de`
- `USER32!MonitorFromWindow` at `0x18013e7de`
- `USER32!SystemParametersInfoW` at `0x18013e94f`
- `USER32!SystemParametersInfoW` at `0x18013e94f`
- `USER32!ShowWindow` at `0x18013e962`
- `USER32!ShowWindow` at `0x18013e962`
- `USER32!SetWindowPos` at `0x18013e8ab`
- `USER32!SetWindowPos` at `0x18013e8ab`
- `USER32!GetWindowRect` at `0x18013e70a`
- `USER32!GetWindowRect` at `0x18013e74c`
- `USER32!GetWindowRect` at `0x18013e70a`
- `USER32!GetWindowRect` at `0x18013e74c`
- `USER32!SendMessageW` at `0x18013e6a4`
- `USER32!SendMessageW` at `0x18013e6c1`
- `USER32!SendMessageW` at `0x18013e6d6`
- `USER32!SendMessageW` at `0x18013e735`
- `USER32!SendMessageW` at `0x18013e76f`
- `USER32!SendMessageW` at `0x18013e9d4`
- `USER32!SendMessageW` at `0x18013e6a4`
- `USER32!SendMessageW` at `0x18013e6c1`
- `USER32!SendMessageW` at `0x18013e6d6`
- `USER32!SendMessageW` at `0x18013e735`
- `USER32!SendMessageW` at `0x18013e76f`
- `USER32!SendMessageW` at `0x18013e9d4`
- `USER32!GetSystemMetrics` at `0x18013e781`
- `USER32!GetSystemMetrics` at `0x18013e7b5`
- `USER32!GetSystemMetrics` at `0x18013e7c4`
- `USER32!GetSystemMetrics` at `0x18013e81a`
- `USER32!GetSystemMetrics` at `0x18013e84e`
- `USER32!GetSystemMetrics` at `0x18013e781`
- `USER32!GetSystemMetrics` at `0x18013e7b5`
- `USER32!GetSystemMetrics` at `0x18013e7c4`
- `USER32!GetSystemMetrics` at `0x18013e81a`
- `USER32!GetSystemMetrics` at `0x18013e84e`
- `USER32!GetWindowLongPtrW` at `0x18013e9aa`
- `USER32!GetWindowLongPtrW` at `0x18013e9aa`
- `USER32!UpdateWindow` at `0x18013e8b4`
- `USER32!UpdateWindow` at `0x18013e8b4`
- `USER32!InvalidateRect` at `0x18013e65d`
- `USER32!InvalidateRect` at `0x18013e6fd`
- `USER32!InvalidateRect` at `0x18013e65d`
- `USER32!InvalidateRect` at `0x18013e6fd`
- `USER32!AnimateWindow` at `0x18013e972`
- `USER32!AnimateWindow` at `0x18013e972`
- `USER32!SetWindowCompositionAttribute` at `0x18013e92a`
- `USER32!SetWindowCompositionAttribute` at `0x18013e92a`
- `USER32!NotifyWinEvent` at `0x18013e98a`
- `USER32!NotifyWinEvent` at `0x18013e99e`
- `USER32!NotifyWinEvent` at `0x18013e98a`
- `USER32!NotifyWinEvent` at `0x18013e99e`
- `USER32!__imp_EnableChildWindowDpiMessage` at `0x18013e63b`
- `USER32!__imp_EnableChildWindowDpiMessage` at `0x18013e63b`
- `USER32!__imp_IsChildWindowDpiMessageEnabled` at `0x18013e616`
- `USER32!__imp_IsChildWindowDpiMessageEnabled` at `0x18013e616`
- `USER32!__imp_IsWindowBroadcastingDpiToChildren` at `0x18013e625`
- `USER32!__imp_IsWindowBroadcastingDpiToChildren` at `0x18013e625`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18013e937`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18013e937`
- `UxTheme!GetThemeColor` at `0x18013e8f6`
- `UxTheme!GetThemeColor` at `0x18013e8f6`
- `UxTheme!__imp_IsDarkModeAllowedForWindow` at `0x18013e8cf`
- `UxTheme!__imp_IsDarkModeAllowedForWindow` at `0x18013e8cf`

## pseudocode

```c
void __fastcall ComboBox_ShowListBoxWindow(struct tagCBox *a1, int a2)
{
  HWND v2; // r14
  HWND v3; // r15
  bool v5; // bl
  int v6; // eax
  int v7; // ecx
  const RECT *v8; // rdx
  HWND v9; // rcx
  int v10; // r13d
  int v11; // r12d
  int cy; // esi
  int v13; // eax
  unsigned int v14; // edx
  int v15; // ebx
  HMONITOR v16; // rax
  BOOL MonitorInfoW; // eax
  int v18; // ebx
  DWORD v19; // r12d
  LONG v20; // ecx
  int v21; // r8d
  int v22; // ecx
  COLORREF v23; // r8d
  void *v24; // rcx
  LONG_PTR WindowLongPtrW; // rax
  LONG top; // [rsp+40h] [rbp-69h]
  _QWORD v28[3]; // [rsp+48h] [rbp-61h] BYREF
  COLORREF pColor; // [rsp+60h] [rbp-49h] BYREF
  COLORREF v30; // [rsp+64h] [rbp-45h] BYREF
  int pvParam; // [rsp+68h] [rbp-41h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp-39h] BYREF
  struct tagRECT v33; // [rsp+80h] [rbp-29h] BYREF
  struct tagMONITORINFO mi; // [rsp+90h] [rbp-19h] BYREF

  v2 = *(HWND *)a1;
  v3 = (HWND)*((_QWORD *)a1 + 12);
  pvParam = 0;
  Rect = 0;
  v33 = 0;
  memset(&mi, 0, sizeof(mi));
  v5 = (unsigned int)IsChildWindowDpiMessageEnabled(v2) != 0;
  if ( v5 != ((unsigned int)IsWindowBroadcastingDpiToChildren(*((_QWORD *)a1 + 12)) != 0) )
    EnableChildWindowDpiMessage(*((_QWORD *)a1 + 12), v5);
  ComboBox_NotifyParent(a1, 7);
  InvalidateRect(v2, (const RECT *)((char *)a1 + 40), 1);
  *((_DWORD *)a1 + 26) |= 0x40u;
  if ( (*((_BYTE *)a1 + 104) & 3) == 3 )
  {
    ComboBox_UpdateListBoxWindow(a1, ((*((_DWORD *)a1 + 26) >> 4) & 1) == 0);
    if ( (*((_BYTE *)a1 + 104) & 0x10) == 0 )
      ComboBox_CompleteEditWindow(a1);
  }
  else
  {
    v6 = SendMessageW(*((HWND *)a1 + 12), 0x188u, 0, 0);
    v7 = 0;
    if ( v6 != -1 )
      v7 = v6;
    SendMessageW(*((HWND *)a1 + 12), 0x197u, v7, 0);
    SendMessageW(*((HWND *)a1 + 12), 0x1A3u, 0, 0);
    if ( *((_QWORD *)a1 + 2) && (unsigned int)Combo_IsReadOnly(a1) )
      v8 = 0;
    else
      v8 = (const RECT *)((char *)a1 + 24);
    InvalidateRect(v2, v8, 1);
  }
  GetWindowRect(*(HWND *)a1, &Rect);
  v9 = (HWND)*((_QWORD *)a1 + 12);
  v10 = *((_DWORD *)a1 + 14);
  pColor = Rect.left;
  top = Rect.top;
  v30 = *((_DWORD *)a1 + 15);
  v11 = SendMessageW(v9, 0x1A1u, 0, 0);
  if ( !v11 )
    v11 = 16;
  GetWindowRect(*((HWND *)a1 + 12), &v33);
  cy = *((_DWORD *)a1 + 17);
  if ( cy <= v33.bottom - v33.top )
    cy = v33.bottom - v33.top;
  v13 = SendMessageW(*((HWND *)a1 + 12), 0x18Bu, 0, 0);
  if ( v13 )
  {
    v14 = GetSystemMetrics(46) + v11 * (unsigned __int16)v13;
    if ( v14 < 0x7FFF && (unsigned __int16)v14 < cy )
      cy = (unsigned __int16)v14;
  }
  if ( (*(_DWORD *)(*((_QWORD *)a1 + 16) + 12LL) & 0x400) == 0 )
  {
    v15 = cy - GetSystemMetrics(46);
    cy = v15 - v15 % v11 + GetSystemMetrics(46);
  }
  v16 = MonitorFromWindow(*(HWND *)a1, 1u);
  mi.cbSize = 40;
  MonitorInfoW = GetMonitorInfoW(v16, &mi);
  if ( MonitorInfoW )
  {
    v18 = top + v30;
    if ( (int)(top + v30 + cy) <= mi.rcMonitor.bottom )
    {
      if ( (*((_DWORD *)a1 + 26) & 0x2000) == 0 )
        v18 -= GetSystemMetrics(6);
      v19 = 262148;
      goto LABEL_35;
    }
    v20 = mi.rcMonitor.top;
  }
  else
  {
    v20 = 0;
  }
  v18 = top - cy;
  if ( top - cy <= v20 )
    v18 = MonitorInfoW ? mi.rcMonitor.top : 0;
  if ( (*((_DWORD *)a1 + 26) & 0x2000) == 0 )
    v18 += GetSystemMetrics(6);
  v19 = 262152;
LABEL_35:
  v21 = *((_DWORD *)a1 + 14);
  v22 = *((_DWORD *)a1 + 16);
  if ( (*(_DWORD *)(*((_QWORD *)a1 + 16) + 8LL) & 0x400000) != 0 )
  {
    if ( v22 <= v21 )
      v22 = *((_DWORD *)a1 + 14);
    v23 = pColor + v10 - v22;
  }
  else
  {
    if ( v22 <= v21 )
      v22 = *((_DWORD *)a1 + 14);
    v23 = pColor;
  }
  SetWindowPos(v3, HWND_MESSAGE|0x2LL, v23, v18, v22, cy, 0x10u);
  UpdateWindow(v2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DarkModeComboboxDropDownFlickerFix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DarkModeComboboxDropDownFlickerFix>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)IsDarkModeAllowedForWindow(v2) )
    {
      v24 = (void *)*((_QWORD *)a1 + 2);
      pColor = 0;
      if ( GetThemeColor(v24, 9, 1, 3802, &pColor) >= 0 )
      {
        v28[0] = 35;
        v30 = pColor | 0xFF000000;
        v28[2] = 4;
        v28[1] = &v30;
        SetWindowCompositionAttribute(v3, v28);
      }
    }
  }
  if ( !(unsigned int)SHWindowsPolicy(&POLID_TurnOffSPIAnimations) )
    SystemParametersInfoW(0x1004u, 0, &pvParam, 0);
  if ( pvParam )
    AnimateWindow(v3, 0xA5u, v19);
  else
    ShowWindow(v3, 8);
  NotifyWinEvent(0x800Au, v2, -4, 0);
  NotifyWinEvent(0x7576u, v2, -4, 0);
  WindowLongPtrW = GetWindowLongPtrW(*((HWND *)a1 + 12), 0);
  if ( (unsigned __int64)(WindowLongPtrW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    *(_DWORD *)(WindowLongPtrW + 180) = 0;
  if ( a2 )
    SendMessageW(*((HWND *)a1 + 12), 0x1AEu, 0, 0);
}

```

## disassembly

```asm
0x18013e5c0  push    rbp
0x18013e5c2  push    rbx
0x18013e5c3  push    rsi
0x18013e5c4  push    rdi
0x18013e5c5  push    r12
0x18013e5c7  push    r13
0x18013e5c9  push    r14
0x18013e5cb  push    r15
0x18013e5cd  lea     rbp, [rsp-1Fh]
0x18013e5d2  sub     rsp, 0C8h
0x18013e5d9  mov     rax, cs:__security_cookie
0x18013e5e0  xor     rax, rsp
0x18013e5e3  mov     [rbp+57h+var_48], rax
0x18013e5e7  mov     r14, [rcx]
0x18013e5ea  xorps   xmm0, xmm0
0x18013e5ed  mov     r15, [rcx+60h]
0x18013e5f1  xor     eax, eax
0x18013e5f3  mov     rdi, rcx
0x18013e5f6  mov     [rbp+57h+var_BC], edx
0x18013e5f9  xorps   xmm1, xmm1
0x18013e5fc  mov     qword ptr [rbp+57h+mi.rcWork.bottom], rax
0x18013e600  mov     rcx, r14
0x18013e603  mov     [rbp+57h+pvParam], eax
0x18013e606  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18013e60a  movups  xmmword ptr [rbp+57h+var_80.left], xmm1
0x18013e60e  movups  xmmword ptr [rbp+57h+mi.cbSize], xmm0
0x18013e612  movups  xmmword ptr [rbp+57h+mi.rcMonitor.bottom], xmm0
0x18013e616  call    cs:__imp_IsChildWindowDpiMessageEnabled
0x18013e61c  mov     rcx, [rdi+60h]
0x18013e620  test    eax, eax
0x18013e622  setnz   bl
0x18013e625  call    cs:__imp_IsWindowBroadcastingDpiToChildren
0x18013e62b  test    eax, eax
0x18013e62d  setnz   al
0x18013e630  cmp     bl, al
0x18013e632  jz      short loc_18013E641
0x18013e634  mov     rcx, [rdi+60h]
0x18013e638  movzx   edx, bl
0x18013e63b  call    cs:__imp_EnableChildWindowDpiMessage
0x18013e641  mov     edx, 7; __int16
0x18013e646  mov     rcx, rdi; struct tagCBox *
0x18013e649  call    ?ComboBox_NotifyParent@@YAXPEAUtagCBox@@F@Z; ComboBox_NotifyParent(tagCBox *,short)
0x18013e64e  mov     ebx, 1
0x18013e653  lea     rdx, [rdi+28h]; lpRect
0x18013e657  mov     r8d, ebx; bErase
0x18013e65a  mov     rcx, r14; hWnd
0x18013e65d  call    cs:__imp_InvalidateRect
0x18013e663  or      dword ptr [rdi+68h], 40h
0x18013e667  lea     esi, [rbx+0Fh]
0x18013e66a  mov     edx, [rdi+68h]
0x18013e66d  mov     eax, edx
0x18013e66f  and     eax, 3
0x18013e672  cmp     al, 3
0x18013e674  jnz     short loc_18013E695
0x18013e676  shr     edx, 4
0x18013e679  mov     rcx, rdi; struct tagCBox *
0x18013e67c  not     edx
0x18013e67e  and     edx, ebx; int
0x18013e680  call    ?ComboBox_UpdateListBoxWindow@@YAXPEAUtagCBox@@H@Z; ComboBox_UpdateListBoxWindow(tagCBox *,int)
0x18013e685  test    [rdi+68h], sil
0x18013e689  jnz     short loc_18013E703
0x18013e68b  mov     rcx, rdi; struct tagCBox *
0x18013e68e  call    ?ComboBox_CompleteEditWindow@@YAXPEAUtagCBox@@@Z; ComboBox_CompleteEditWindow(tagCBox *)
0x18013e693  jmp     short loc_18013E703
0x18013e695  mov     rcx, [rdi+60h]; hWnd
0x18013e699  xor     r9d, r9d; lParam
0x18013e69c  xor     r8d, r8d; wParam
0x18013e69f  mov     edx, 188h; Msg
0x18013e6a4  call    cs:__imp_SendMessageW
0x18013e6aa  xor     ecx, ecx
0x18013e6ac  mov     edx, 197h; Msg
0x18013e6b1  cmp     eax, 0FFFFFFFFh
0x18013e6b4  cmovnz  ecx, eax
0x18013e6b7  xor     r9d, r9d; lParam
0x18013e6ba  movsxd  r8, ecx; wParam
0x18013e6bd  mov     rcx, [rdi+60h]; hWnd
0x18013e6c1  call    cs:__imp_SendMessageW
0x18013e6c7  mov     rcx, [rdi+60h]; hWnd
0x18013e6cb  xor     r9d, r9d; lParam
0x18013e6ce  xor     r8d, r8d; wParam
0x18013e6d1  mov     edx, 1A3h; Msg
0x18013e6d6  call    cs:__imp_SendMessageW
0x18013e6dc  cmp     qword ptr [rdi+10h], 0
0x18013e6e1  jz      short loc_18013E6F3
0x18013e6e3  mov     rcx, rdi; struct tagCBox *
0x18013e6e6  call    ?Combo_IsReadOnly@@YAHPEAUtagCBox@@@Z; Combo_IsReadOnly(tagCBox *)
0x18013e6eb  test    eax, eax
0x18013e6ed  jz      short loc_18013E6F3
0x18013e6ef  xor     edx, edx
0x18013e6f1  jmp     short loc_18013E6F7
0x18013e6f3  lea     rdx, [rdi+18h]; lpRect
0x18013e6f7  mov     r8d, ebx; bErase
0x18013e6fa  mov     rcx, r14; hWnd
0x18013e6fd  call    cs:__imp_InvalidateRect
0x18013e703  mov     rcx, [rdi]; hWnd
0x18013e706  lea     rdx, [rbp+57h+Rect]; lpRect
0x18013e70a  call    cs:__imp_GetWindowRect
0x18013e710  mov     eax, [rbp+57h+Rect.left]
0x18013e713  xor     r9d, r9d; lParam
0x18013e716  mov     rcx, [rdi+60h]; hWnd
0x18013e71a  xor     r8d, r8d; wParam
0x18013e71d  mov     r13d, [rdi+38h]
0x18013e721  mov     edx, 1A1h; Msg
0x18013e726  mov     [rbp+57h+var_A0], eax
0x18013e729  mov     eax, [rbp+57h+Rect.top]
0x18013e72c  mov     [rbp+57h+var_C0], eax
0x18013e72f  mov     eax, [rdi+3Ch]
0x18013e732  mov     [rbp+57h+var_9C], eax
0x18013e735  call    cs:__imp_SendMessageW
0x18013e73b  mov     rcx, [rdi+60h]; hWnd
0x18013e73f  lea     rdx, [rbp+57h+var_80]; lpRect
0x18013e743  test    eax, eax
0x18013e745  mov     r12, rax
0x18013e748  cmovz   r12d, esi
0x18013e74c  call    cs:__imp_GetWindowRect
0x18013e752  mov     ecx, [rbp+57h+var_80.bottom]
0x18013e755  mov     edx, 18Bh; Msg
0x18013e75a  sub     ecx, [rbp+57h+var_80.top]
0x18013e75d  mov     esi, [rdi+44h]
0x18013e760  cmp     esi, ecx
0x18013e762  cmovle  esi, ecx
0x18013e765  mov     rcx, [rdi+60h]; hWnd
0x18013e769  xor     r9d, r9d; lParam
0x18013e76c  xor     r8d, r8d; wParam
0x18013e76f  call    cs:__imp_SendMessageW
0x18013e775  mov     rbx, rax
0x18013e778  test    eax, eax
0x18013e77a  jz      short loc_18013E7A0
0x18013e77c  mov     ecx, 2Eh ; '.'; nIndex
0x18013e781  call    cs:__imp_GetSystemMetrics
0x18013e787  movzx   edx, bx
0x18013e78a  imul    edx, r12d
0x18013e78e  add     edx, eax
0x18013e790  cmp     edx, 7FFFh
0x18013e796  jnb     short loc_18013E7A0
0x18013e798  movzx   eax, dx
0x18013e79b  cmp     eax, esi
0x18013e79d  cmovl   esi, eax
0x18013e7a0  mov     rax, [rdi+80h]
0x18013e7a7  test    dword ptr [rax+0Ch], 400h
0x18013e7ae  jnz     short loc_18013E7D6
0x18013e7b0  mov     ecx, 2Eh ; '.'; nIndex
0x18013e7b5  call    cs:__imp_GetSystemMetrics
0x18013e7bb  sub     esi, eax
0x18013e7bd  mov     ecx, 2Eh ; '.'; nIndex
0x18013e7c2  mov     ebx, esi
0x18013e7c4  call    cs:__imp_GetSystemMetrics
0x18013e7ca  mov     esi, eax
0x18013e7cc  mov     eax, ebx
0x18013e7ce  cdq
0x18013e7cf  idiv    r12d
0x18013e7d2  sub     ebx, edx
0x18013e7d4  add     esi, ebx
0x18013e7d6  mov     rcx, [rdi]; hwnd
0x18013e7d9  mov     edx, 1; dwFlags
0x18013e7de  call    cs:__imp_MonitorFromWindow
0x18013e7e4  lea     rdx, [rbp+57h+mi]; lpmi
0x18013e7e8  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x18013e7ef  mov     rcx, rax; hMonitor
0x18013e7f2  call    cs:__imp_GetMonitorInfoW
0x18013e7f8  mov     edx, [rbp+57h+var_C0]
0x18013e7fb  test    eax, eax
0x18013e7fd  jz      short loc_18013E82F
0x18013e7ff  mov     ebx, [rbp+57h+var_9C]
0x18013e802  add     ebx, edx
0x18013e804  lea     ecx, [rbx+rsi]
0x18013e807  cmp     ecx, [rbp+57h+mi.rcMonitor.bottom]
0x18013e80a  jg      short loc_18013E82A
0x18013e80c  test    dword ptr [rdi+68h], 2000h
0x18013e813  jnz     short loc_18013E822
0x18013e815  mov     ecx, 6; nIndex
0x18013e81a  call    cs:__imp_GetSystemMetrics
0x18013e820  sub     ebx, eax
0x18013e822  mov     r12d, 40004h
0x18013e828  jmp     short loc_18013E85C
0x18013e82a  mov     ecx, [rbp+57h+mi.rcMonitor.top]
0x18013e82d  jmp     short loc_18013E831
0x18013e82f  xor     ecx, ecx
0x18013e831  mov     ebx, edx
0x18013e833  sub     ebx, esi
0x18013e835  cmp     ebx, ecx
0x18013e837  jg      short loc_18013E840
0x18013e839  neg     eax
0x18013e83b  sbb     ebx, ebx
0x18013e83d  and     ebx, [rbp+57h+mi.rcMonitor.top]
0x18013e840  test    dword ptr [rdi+68h], 2000h
0x18013e847  jnz     short loc_18013E856
0x18013e849  mov     ecx, 6; nIndex
0x18013e84e  call    cs:__imp_GetSystemMetrics
0x18013e854  add     ebx, eax
0x18013e856  mov     r12d, 40008h
0x18013e85c  mov     rax, [rdi+80h]
0x18013e863  mov     r9d, ebx; Y
0x18013e866  mov     r8d, [rdi+38h]
0x18013e86a  mov     ecx, [rdi+40h]
0x18013e86d  mov     [rsp+100h+uFlags], 10h; uFlags
0x18013e875  test    dword ptr [rax+8], 400000h
0x18013e87c  mov     [rsp+100h+cy], esi; cy
0x18013e880  jnz     short loc_18013E88F
0x18013e882  cmp     ecx, r8d
0x18013e885  cmovle  ecx, r8d
0x18013e889  mov     r8d, [rbp+57h+var_A0]
0x18013e88d  jmp     short loc_18013E8A0
0x18013e88f  cmp     ecx, r8d
0x18013e892  cmovle  ecx, r8d
0x18013e896  sub     r13d, ecx
0x18013e899  add     r13d, [rbp+57h+var_A0]
0x18013e89d  mov     r8d, r13d; X
0x18013e8a0  mov     dword ptr [rsp+100h+pColor], ecx; cx
0x18013e8a4  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x18013e8a8  mov     rcx, r15; hWnd
0x18013e8ab  call    cs:__imp_SetWindowPos
0x18013e8b1  mov     rcx, r14; hWnd
0x18013e8b4  call    cs:__imp_UpdateWindow
0x18013e8ba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DarkModeComboboxDropDownFlickerFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DarkModeComboboxDropDownFlickerFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DarkModeComboboxDropDownFlickerFix> `wil::Feature<__WilFeatureTraits_Feature_DarkModeComboboxDropDownFlickerFix>::GetImpl(void)'::`2'::impl
0x18013e8c1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DarkModeComboboxDropDownFlickerFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DarkModeComboboxDropDownFlickerFix>::__private_IsEnabled(void)
0x18013e8c6  xor     esi, esi
0x18013e8c8  test    al, al
0x18013e8ca  jz      short loc_18013E930
0x18013e8cc  mov     rcx, r14
0x18013e8cf  call    cs:__imp_IsDarkModeAllowedForWindow
0x18013e8d5  test    al, al
0x18013e8d7  jz      short loc_18013E930
0x18013e8d9  mov     rcx, [rdi+10h]; hTheme
0x18013e8dd  lea     rax, [rbp+57h+var_A0]
0x18013e8e1  lea     edx, [rsi+9]; iPartId
0x18013e8e4  mov     [rsp+100h+pColor], rax; pColor
0x18013e8e9  mov     r9d, 0EDAh; iPropId
0x18013e8ef  mov     [rbp+57h+var_A0], esi
0x18013e8f2  lea     r8d, [rsi+1]; iStateId
0x18013e8f6  call    cs:__imp_GetThemeColor
0x18013e8fc  test    eax, eax
0x18013e8fe  js      short loc_18013E930
0x18013e900  mov     eax, [rbp+57h+var_A0]
0x18013e903  lea     rdx, [rbp+57h+var_B8]
0x18013e907  or      eax, 0FF000000h
0x18013e90c  mov     [rbp+57h+var_B8], 23h ; '#'
0x18013e914  mov     [rbp+57h+var_9C], eax
0x18013e917  mov     rcx, r15
0x18013e91a  lea     rax, [rbp+57h+var_9C]
0x18013e91e  mov     [rbp+57h+var_A8], 4
0x18013e926  mov     [rbp+57h+var_B0], rax
0x18013e92a  call    cs:__imp_SetWindowCompositionAttribute
0x18013e930  lea     rcx, POLID_TurnOffSPIAnimations
0x18013e937  call    cs:__imp_SHWindowsPolicy
0x18013e93d  test    eax, eax
0x18013e93f  jnz     short loc_18013E955
0x18013e941  xor     r9d, r9d; fWinIni
0x18013e944  lea     r8, [rbp+57h+pvParam]; pvParam
0x18013e948  xor     edx, edx; uiParam
0x18013e94a  mov     ecx, 1004h; uiAction
0x18013e94f  call    cs:__imp_SystemParametersInfoW
0x18013e955  mov     rcx, r15; hWnd
0x18013e958  cmp     [rbp+57h+pvParam], esi
0x18013e95b  jnz     short loc_18013E96A
0x18013e95d  mov     edx, 8; nCmdShow
0x18013e962  call    cs:__imp_ShowWindow
0x18013e968  jmp     short loc_18013E978
0x18013e96a  mov     r8d, r12d; dwFlags
0x18013e96d  mov     edx, 0A5h; dwTime
0x18013e972  call    cs:__imp_AnimateWindow
0x18013e978  xor     r9d, r9d; idChild
0x18013e97b  mov     rdx, r14; hwnd
0x18013e97e  mov     ecx, 800Ah; event
0x18013e983  lea     ebx, [r9-4]
0x18013e987  mov     r8d, ebx; idObject
0x18013e98a  call    cs:__imp_NotifyWinEvent
0x18013e990  xor     r9d, r9d; idChild
0x18013e993  mov     r8d, ebx; idObject
0x18013e996  mov     rdx, r14; hwnd
0x18013e999  mov     ecx, 7576h; event
0x18013e99e  call    cs:__imp_NotifyWinEvent
0x18013e9a4  mov     rcx, [rdi+60h]; hWnd
0x18013e9a8  xor     edx, edx; nIndex
0x18013e9aa  call    cs:__imp_GetWindowLongPtrW
0x18013e9b0  lea     rcx, [rax-1]
0x18013e9b4  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18013e9b8  ja      short loc_18013E9C0
0x18013e9ba  mov     [rax+0B4h], esi
0x18013e9c0  cmp     [rbp+57h+var_BC], esi
0x18013e9c3  jz      short loc_18013E9DA
0x18013e9c5  mov     rcx, [rdi+60h]; hWnd
0x18013e9c9  xor     r9d, r9d; lParam
0x18013e9cc  xor     r8d, r8d; wParam
0x18013e9cf  mov     edx, 1AEh; Msg
0x18013e9d4  call    cs:__imp_SendMessageW
0x18013e9da  mov     rcx, [rbp+57h+var_48]
0x18013e9de  xor     rcx, rsp; StackCookie
0x18013e9e1  call    __security_check_cookie
0x18013e9e6  add     rsp, 0C8h
0x18013e9ed  pop     r15
0x18013e9ef  pop     r14
0x18013e9f1  pop     r13
0x18013e9f3  pop     r12
0x18013e9f5  pop     rdi
0x18013e9f6  pop     rsi
0x18013e9f7  pop     rbx
0x18013e9f8  pop     rbp
0x18013e9f9  retn
```
