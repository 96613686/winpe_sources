# FontDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180009980`
- end: `0x18000a015`
- name: `?FontDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1685`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update`

## callees

- `0x1800015b0`
- `0x180005e60`
- `0x18000705c`
- `0x180007998`
- `0x180007a68`
- `0x180008714`
- `0x180008d68`
- `0x180009264`
- `0x180009578`
- `0x180009980`
- `0x18000a01c`
- `0x18000a87c`
- `0x18000aa6c`
- `0x18000ab50`
- `0x18000ac68`
- `0x18000b020`
- `0x180010470`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180009c32`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180009c56`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180009c32`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180009c56`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x180009e30`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x180009e30`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetFocus` at `0x180009aab`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetFocus` at `0x180009aab`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x180009dea`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x180009dea`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x180009d74`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x180009d74`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180009c9e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180009e57`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180009e6b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180009c9e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180009e57`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x180009e6b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsChild` at `0x180009ac9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsChild` at `0x180009ac9`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180009a22`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180009b97`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180009bb9`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180009be4`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180009a22`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180009b97`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180009bb9`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x180009be4`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180009ae3`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180009d63`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180009ddb`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180009e1a`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180009ae3`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180009d63`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180009ddb`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180009e1a`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180009b1e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180009b1e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CheckDlgButton` at `0x180009d26`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CheckDlgButton` at `0x180009d26`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180009fd7`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180009fd7`

## string_xrefs

- `0x180009cd0`: `onecore\windows\core\console\open\src\propsheet\fontdlg.cpp`

## pseudocode

```c
__int64 __fastcall FontDlgProc(HWND hDlg, int a2, unsigned __int64 a3, struct tagDRAWITEMSTRUCT *a4)
{
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  unsigned int ItemHeight; // eax
  __int64 v14; // rbx
  int v15; // edx
  unsigned __int64 v16; // r8
  HWND Focus; // rax
  HWND v18; // rsi
  WPARAM v19; // r14
  int v20; // ebp
  wchar_t *v21; // rdx
  int v22; // eax
  wchar_t *v23; // rbx
  int v24; // eax
  int FontAndUpdateState; // eax
  char v26; // si
  HWND v27; // rax
  int v28; // ebx
  HWND v29; // rax
  UINT itemState; // eax
  HWND DlgItem; // rax
  _DWORD *v32; // rdx
  struct _CONSOLE_STATE_INFO *v33; // rcx
  __int64 v34; // r8
  int v35; // eax
  BOOL v36; // ebx
  int Font; // eax
  wchar_t *v38; // rbx
  int v39; // esi
  wchar_t *v40; // rdx
  int v41; // eax
  int lParam; // [rsp+20h] [rbp-78h]
  LPARAM v44[8]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v5 = a2 - 2;
  if ( !v5 )
  {
    if ( hbmTT )
    {
      DeleteObject(hbmTT);
      hbmTT = 0;
    }
    return 1;
  }
  v6 = v5 - 13;
  if ( !v6 )
  {
    v38 = 0;
    if ( fChangeCodePage )
    {
      fChangeCodePage = 0;
      if ( (*((_BYTE *)gpStateInfo + 20) & 4) != 0 )
      {
        v39 = 0;
        v40 = 0;
      }
      else
      {
        v39 = 1;
        v40 = (wchar_t *)((char *)gpStateInfo + 28);
      }
      FontListCreate(hDlg, v40, 1);
      if ( !v39 )
        v38 = (wchar_t *)((char *)gpStateInfo + 28);
      FontListCreate(hDlg, v38, 1);
      v41 = PreviewInit(hDlg);
      PreviewUpdate(hDlg, v41);
    }
    return 0;
  }
  v7 = v6 - 14;
  if ( !v7 )
  {
    gbEnumerateFaces = 1;
    v36 = (*((_DWORD *)gpStateInfo + 5) & 4) == 0;
    FontListCreate(hDlg, 0, 1);
    Font = FindCreateFont(
             *((_DWORD *)gpStateInfo + 5),
             (wchar_t *)gpStateInfo + 14,
             *(struct _COORD *)((char *)gpStateInfo + 16),
             *((_DWORD *)gpStateInfo + 6),
             *((_DWORD *)gpStateInfo + 52));
    SelectCurrentSize(hDlg, v36, Font);
    return 1;
  }
  v8 = v7 - 14;
  if ( !v8 )
  {
    DrawItemFontList(hDlg, a4);
    return 1;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    a4->itemState = GetItemHeight(hDlg);
    return 1;
  }
  v10 = v9 - 34;
  if ( !v10 )
  {
    itemState = a4->itemState;
    if ( itemState == -202 )
    {
      EndDlgPage(hDlg, a4->hwndItem == 0);
      return 1;
    }
    if ( itemState == -201 )
    {
      DlgItem = GetDlgItem(hDlg, 213);
      if ( DlgItem && IsWindowVisible(DlgItem) )
      {
        if ( !(unsigned int)PreviewUpdate(hDlg, 0) )
        {
          SetWindowLongPtrW(hDlg, 0, 1);
          return 1;
        }
        SetWindowLongPtrW(hDlg, 0, 0);
      }
      v32 = FontInfo;
      v33 = gpStateInfo;
      v34 = 5LL * (int)g_currentFontIndex;
      if ( *((_WORD *)FontInfo + 20 * (int)g_currentFontIndex + 7) )
        v35 = *((_DWORD *)FontInfo + 10 * (int)g_currentFontIndex + 3);
      else
        v35 = *((_DWORD *)FontInfo + 10 * (int)g_currentFontIndex + 2);
      *((_DWORD *)gpStateInfo + 4) = v35;
      *((_DWORD *)v33 + 6) = v32[2 * v34 + 4];
      *((_DWORD *)v33 + 5) = LOBYTE(v32[2 * v34 + 8]);
      StringCchCopyW((wchar_t *)v33 + 14, 0x20u, *(const wchar_t **)&v32[2 * v34 + 6]);
      return 1;
    }
    return 0;
  }
  v11 = v10 - 194;
  if ( !v11 )
  {
    LoadStringW(ghInstance, 4u, &wszRasterFonts, 25);
    LoadStringW(ghInstance, 6u, &wszSelectedFont, 31);
    v23 = 0;
    if ( g_fEastAsianSystem )
      v24 = *((unsigned __int8 *)FontInfo + 40 * g_currentFontIndex + 33);
    else
      v24 = *((unsigned __int16 *)FontInfo + 20 * g_currentFontIndex + 4);
    SetWindowLongPtrW(hDlg, -21, v24 | (*((unsigned __int16 *)FontInfo + 20 * g_currentFontIndex + 5) << 16));
    if ( g_fHostedInFileProperties || *((char *)gpStateInfo + 96) < 0 )
    {
      FontAndUpdateState = FindFontAndUpdateState();
      if ( FontAndUpdateState < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x101,
          (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\fontdlg.cpp",
          (const char *)(unsigned int)FontAndUpdateState,
          lParam);
    }
    gbEnumerateFaces = 1;
    v26 = *((_BYTE *)FontInfo + 40 * g_currentFontIndex + 32) & 4;
    gbBold = *((_DWORD *)FontInfo + 10 * g_currentFontIndex + 4) >= 600;
    CheckDlgButton(hDlg, 203, gbBold);
    if ( gbBold )
    {
      if ( (unsigned int)IsBoldOnlyTTFont(*((LPCWSTR *)FontInfo + 5 * g_currentFontIndex + 3), 0) )
      {
        v27 = GetDlgItem(hDlg, 203);
        EnableWindow(v27, 0);
      }
      else
      {
        gbUserChoseBold = 1;
      }
    }
    if ( v26 )
      v23 = (wchar_t *)*((_QWORD *)FontInfo + 5 * g_currentFontIndex + 3);
    FontListCreate(hDlg, v23, 1);
    v28 = PreviewInit(hDlg);
    PreviewUpdate(hDlg, v28);
    v29 = GetDlgItem(hDlg, (unsigned int)(v28 != 0) + 213);
    SetFocus(v29);
    return 0;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 == 465 )
    {
      RecreateFontHandles(hDlg);
      ItemHeight = GetItemHeight(hDlg);
      SendDlgItemMessageW(hDlg, 202, 0x1A0u, 0, ItemHeight);
    }
    return 0;
  }
  v14 = (int)g_currentFontIndex;
  if ( (unsigned __int16)a3 == 202 )
  {
    if ( WORD1(a3) != 1 )
      return 0;
    goto LABEL_28;
  }
  if ( (unsigned __int16)a3 == 203 )
  {
    gbBold = IsDlgButtonChecked(hDlg, 203);
    gbUserChoseBold = gbBold;
    UpdateApplyButton(hDlg);
LABEL_28:
    if ( *((int *)FontInfo + 10 * v14 + 4) >= 600
      && (unsigned int)IsBoldOnlyTTFont(*((LPCWSTR *)FontInfo + 5 * v14 + 3), 0)
      && !gbUserChoseBold )
    {
      gbBold = 0;
    }
    v19 = (int)SendDlgItemMessageW(hDlg, 202, 0x188u, 0, 0);
    v20 = SendDlgItemMessageW(hDlg, 202, 0x199u, v19, 0);
    if ( !v20 )
      SendDlgItemMessageW(hDlg, 202, 0x189u, v19, (LPARAM)v44);
    v21 = (wchar_t *)v44;
    if ( v20 )
      v21 = 0;
    v22 = FontListCreate(hDlg, v21, 0);
    SelectCurrentSize(hDlg, v20, v22);
    v15 = v20;
    goto LABEL_17;
  }
  if ( (unsigned __int16)a3 != 213 )
  {
    if ( (unsigned __int16)a3 != 214 || WORD1(a3) != 1 )
      return 0;
    v15 = 1;
    goto LABEL_17;
  }
  v16 = a3 >> 16;
  if ( (unsigned __int16)v16 != 1 )
  {
    if ( (unsigned __int16)v16 == 4 )
    {
      if ( !gbPointSizeError )
      {
        Focus = GetFocus();
        v18 = Focus;
        if ( Focus )
        {
          if ( IsChild(hDlg, Focus) && v18 != GetDlgItem(hDlg, 2) )
          {
            AddCustomFontSizeToListIfNeeded(hDlg);
            PreviewUpdate(hDlg, 0);
          }
        }
      }
      return 1;
    }
    return 0;
  }
  v15 = 0;
LABEL_17:
  PreviewUpdate(hDlg, v15);
  UpdateApplyButton(hDlg);
  return 1;
}

```

## disassembly

```asm
0x180009980  mov     [rsp+arg_8], rbx
0x180009985  mov     [rsp+arg_10], rbp
0x18000998a  push    rsi
0x18000998b  push    rdi
0x18000998c  push    r14
0x18000998e  sub     rsp, 80h
0x180009995  mov     rax, cs:__security_cookie
0x18000999c  xor     rax, rsp
0x18000999f  mov     [rsp+98h+var_28], rax
0x1800099a4  mov     rsi, r9
0x1800099a7  mov     rdi, rcx
0x1800099aa  sub     edx, 2
0x1800099ad  jz      loc_180009FC9
0x1800099b3  sub     edx, 0Dh
0x1800099b6  jz      loc_180009F5D
0x1800099bc  sub     edx, 0Eh
0x1800099bf  jz      loc_180009EFF
0x1800099c5  sub     edx, 0Eh
0x1800099c8  jz      loc_180009EF2
0x1800099ce  sub     edx, 1
0x1800099d1  jz      loc_180009EE5
0x1800099d7  sub     edx, 22h ; '"'
0x1800099da  jz      loc_180009DFB
0x1800099e0  sub     edx, 0C2h
0x1800099e6  jz      loc_180009C1A
0x1800099ec  sub     edx, 1
0x1800099ef  jz      short loc_180009A33
0x1800099f1  cmp     edx, 1D1h
0x1800099f7  jnz     loc_180009FC5
0x1800099fd  call    ?RecreateFontHandles@@YAXQEAUHWND__@@@Z; RecreateFontHandles(HWND__ * const)
0x180009a02  mov     rcx, rdi; hWnd
0x180009a05  call    ?GetItemHeight@@YAIQEAUHWND__@@@Z; GetItemHeight(HWND__ * const)
0x180009a0a  mov     eax, eax
0x180009a0c  xor     r9d, r9d; wParam
0x180009a0f  mov     edx, 0CAh; nIDDlgItem
0x180009a14  mov     qword ptr [rsp+98h+lParam], rax; lParam
0x180009a19  mov     r8d, 1A0h; Msg
0x180009a1f  mov     rcx, rdi; hDlg
0x180009a22  call    cs:__imp_SendDlgItemMessageW
0x180009a29  nop     dword ptr [rax+rax+00h]
0x180009a2e  jmp     loc_180009FC5
0x180009a33  movsxd  rbx, cs:?g_currentFontIndex@@3KA; ulong g_currentFontIndex
0x180009a3a  mov     esi, 0CAh
0x180009a3f  movzx   ecx, r8w
0x180009a43  sub     ecx, esi
0x180009a45  jz      loc_180009B40
0x180009a4b  sub     ecx, 1
0x180009a4e  jz      loc_180009B16
0x180009a54  sub     ecx, 0Ah
0x180009a57  jz      short loc_180009A87
0x180009a59  cmp     ecx, 1
0x180009a5c  jnz     loc_180009FC5
0x180009a62  shr     r8, 10h
0x180009a66  cmp     r8w, cx
0x180009a6a  jnz     loc_180009FC5
0x180009a70  mov     edx, ecx; int
0x180009a72  mov     rcx, rdi; hDlg
0x180009a75  call    ?PreviewUpdate@@YAHPEAUHWND__@@H@Z; PreviewUpdate(HWND__ *,int)
0x180009a7a  mov     rcx, rdi; wParam
0x180009a7d  call    ?UpdateApplyButton@@YAXQEAUHWND__@@@Z; UpdateApplyButton(HWND__ * const)
0x180009a82  jmp     loc_180009FEA
0x180009a87  shr     r8, 10h
0x180009a8b  movzx   ecx, r8w
0x180009a8f  sub     ecx, 1
0x180009a92  jz      short loc_180009B0F
0x180009a94  cmp     ecx, 3
0x180009a97  jnz     loc_180009FC5
0x180009a9d  xor     ebx, ebx
0x180009a9f  cmp     cs:?gbPointSizeError@@3HA, ebx; int gbPointSizeError
0x180009aa5  jnz     loc_180009FEA
0x180009aab  call    cs:__imp_GetFocus
0x180009ab2  nop     dword ptr [rax+rax+00h]
0x180009ab7  mov     rsi, rax
0x180009aba  test    rax, rax
0x180009abd  jz      loc_180009FEA
0x180009ac3  mov     rdx, rax; hWnd
0x180009ac6  mov     rcx, rdi; hWndParent
0x180009ac9  call    cs:__imp_IsChild
0x180009ad0  nop     dword ptr [rax+rax+00h]
0x180009ad5  test    eax, eax
0x180009ad7  jz      loc_180009FEA
0x180009add  lea     edx, [rbx+2]; nIDDlgItem
0x180009ae0  mov     rcx, rdi; hDlg
0x180009ae3  call    cs:__imp_GetDlgItem
0x180009aea  nop     dword ptr [rax+rax+00h]
0x180009aef  cmp     rsi, rax
0x180009af2  jz      loc_180009FEA
0x180009af8  mov     rcx, rdi; hDlg
0x180009afb  call    AddCustomFontSizeToListIfNeeded
0x180009b00  xor     edx, edx; int
0x180009b02  mov     rcx, rdi; hDlg
0x180009b05  call    ?PreviewUpdate@@YAHPEAUHWND__@@H@Z; PreviewUpdate(HWND__ *,int)
0x180009b0a  jmp     loc_180009FEA
0x180009b0f  xor     edx, edx
0x180009b11  jmp     loc_180009A72
0x180009b16  mov     edx, 0CBh; nIDButton
0x180009b1b  mov     rcx, rdi; hDlg
0x180009b1e  call    cs:__imp_IsDlgButtonChecked
0x180009b25  nop     dword ptr [rax+rax+00h]
0x180009b2a  mov     rcx, rdi; wParam
0x180009b2d  mov     cs:?gbBold@@3HA, eax; int gbBold
0x180009b33  mov     cs:?gbUserChoseBold@@3HA, eax; int gbUserChoseBold
0x180009b39  call    ?UpdateApplyButton@@YAXQEAUHWND__@@@Z; UpdateApplyButton(HWND__ * const)
0x180009b3e  jmp     short loc_180009B4F
0x180009b40  shr     r8, 10h
0x180009b44  cmp     r8w, 1
0x180009b49  jnz     loc_180009FC5
0x180009b4f  mov     rax, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180009b56  lea     rcx, [rbx+rbx*4]
0x180009b5a  xor     ebx, ebx
0x180009b5c  cmp     dword ptr [rax+rcx*8+10h], 258h
0x180009b64  jl      short loc_180009B84
0x180009b66  mov     rcx, [rax+rcx*8+18h]; lpString2
0x180009b6b  xor     edx, edx; LPCWSTR
0x180009b6d  call    ?IsBoldOnlyTTFont@@YAHPEB_W0@Z; IsBoldOnlyTTFont(wchar_t const *,wchar_t const *)
0x180009b72  test    eax, eax
0x180009b74  jz      short loc_180009B84
0x180009b76  cmp     cs:?gbUserChoseBold@@3HA, ebx; int gbUserChoseBold
0x180009b7c  jnz     short loc_180009B84
0x180009b7e  mov     cs:?gbBold@@3HA, ebx; int gbBold
0x180009b84  xor     r9d, r9d; wParam
0x180009b87  mov     qword ptr [rsp+98h+lParam], rbx; lParam
0x180009b8c  mov     r8d, 188h; Msg
0x180009b92  mov     edx, esi; nIDDlgItem
0x180009b94  mov     rcx, rdi; hDlg
0x180009b97  call    cs:__imp_SendDlgItemMessageW
0x180009b9e  nop     dword ptr [rax+rax+00h]
0x180009ba3  mov     r8d, 199h; Msg
0x180009ba9  mov     qword ptr [rsp+98h+lParam], rbx; lParam
0x180009bae  movsxd  r14, eax
0x180009bb1  mov     edx, esi; nIDDlgItem
0x180009bb3  mov     r9, r14; wParam
0x180009bb6  mov     rcx, rdi; hDlg
0x180009bb9  call    cs:__imp_SendDlgItemMessageW
0x180009bc0  nop     dword ptr [rax+rax+00h]
0x180009bc5  mov     rbp, rax
0x180009bc8  test    eax, eax
0x180009bca  jnz     short loc_180009BF0
0x180009bcc  lea     rax, [rsp+98h+var_68]
0x180009bd1  mov     r9, r14; wParam
0x180009bd4  mov     r8d, 189h; Msg
0x180009bda  mov     qword ptr [rsp+98h+lParam], rax; lParam
0x180009bdf  mov     edx, esi; nIDDlgItem
0x180009be1  mov     rcx, rdi; hDlg
0x180009be4  call    cs:__imp_SendDlgItemMessageW
0x180009beb  nop     dword ptr [rax+rax+00h]
0x180009bf0  test    ebp, ebp
0x180009bf2  lea     rdx, [rsp+98h+var_68]
0x180009bf7  mov     rcx, rdi; hDlg
0x180009bfa  cmovnz  rdx, rbx; wchar_t *
0x180009bfe  xor     r8d, r8d; int
0x180009c01  call    ?FontListCreate@@YAHPEAUHWND__@@PEA_WH@Z; FontListCreate(HWND__ *,wchar_t *,int)
0x180009c06  mov     r8d, eax; int
0x180009c09  mov     edx, ebp; int
0x180009c0b  mov     rcx, rdi; hWnd
0x180009c0e  call    ?SelectCurrentSize@@YAHPEAUHWND__@@HH@Z; SelectCurrentSize(HWND__ *,int,int)
0x180009c13  mov     edx, ebp
0x180009c15  jmp     loc_180009A72
0x180009c1a  mov     rcx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180009c21  lea     r8, ?wszRasterFonts@@3PA_WA; lpBuffer
0x180009c28  mov     r9d, 19h; cchBufferMax
0x180009c2e  lea     edx, [r9-15h]; uID
0x180009c32  call    cs:__imp_LoadStringW
0x180009c39  nop     dword ptr [rax+rax+00h]
0x180009c3e  mov     rcx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180009c45  lea     r8, ?wszSelectedFont@@3PA_WA; lpBuffer
0x180009c4c  mov     r9d, 1Fh; cchBufferMax
0x180009c52  lea     edx, [r9-19h]; uID
0x180009c56  call    cs:__imp_LoadStringW
0x180009c5d  nop     dword ptr [rax+rax+00h]
0x180009c62  mov     eax, cs:?g_currentFontIndex@@3KA; ulong g_currentFontIndex
0x180009c68  xor     ebx, ebx
0x180009c6a  lea     rcx, [rax+rax*4]
0x180009c6e  mov     rax, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180009c75  movzx   edx, word ptr [rax+rcx*8+0Ah]
0x180009c7a  shl     edx, 10h
0x180009c7d  cmp     cs:?g_fEastAsianSystem@@3HA, ebx; int g_fEastAsianSystem
0x180009c83  jz      short loc_180009C8C
0x180009c85  movzx   eax, byte ptr [rax+rcx*8+21h]
0x180009c8a  jmp     short loc_180009C91
0x180009c8c  movzx   eax, word ptr [rax+rcx*8+8]
0x180009c91  or      edx, eax
0x180009c93  mov     rcx, rdi; hWnd
0x180009c96  movsxd  r8, edx; dwNewLong
0x180009c99  mov     edx, 0FFFFFFEBh; nIndex
0x180009c9e  call    cs:__imp_SetWindowLongPtrW
0x180009ca5  nop     dword ptr [rax+rax+00h]
0x180009caa  cmp     cs:?g_fHostedInFileProperties@@3HA, ebx; int g_fHostedInFileProperties
0x180009cb0  jnz     short loc_180009CBF
0x180009cb2  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180009cb9  test    byte ptr [rax+60h], 80h
0x180009cbd  jz      short loc_180009CE4
0x180009cbf  call    ?FindFontAndUpdateState@@YAJXZ; FindFontAndUpdateState(void)
0x180009cc4  test    eax, eax
0x180009cc6  jns     short loc_180009CE4
0x180009cc8  mov     rcx, [rsp+98h]; this
0x180009cd0  lea     r8, aOnecoreWindows_2; "onecore\\windows\\core\\console\\open\\"...
0x180009cd7  mov     r9d, eax; char *
0x180009cda  mov     edx, 101h; void *
0x180009cdf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009ce4  mov     eax, cs:?g_currentFontIndex@@3KA; ulong g_currentFontIndex
0x180009cea  mov     r8d, ebx
0x180009ced  mov     edx, 0CBh; nIDButton
0x180009cf2  mov     cs:?gbEnumerateFaces@@3HA, 1; int gbEnumerateFaces
0x180009cfc  lea     rcx, [rax+rax*4]
0x180009d00  mov     rax, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180009d07  mov     sil, [rax+rcx*8+20h]
0x180009d0c  and     sil, 4
0x180009d10  cmp     dword ptr [rax+rcx*8+10h], 258h
0x180009d18  mov     rcx, rdi; hDlg
0x180009d1b  setnl   r8b; uCheck
0x180009d1f  mov     cs:?gbBold@@3HA, r8d; int gbBold
0x180009d26  call    cs:__imp_CheckDlgButton
0x180009d2d  nop     dword ptr [rax+rax+00h]
0x180009d32  cmp     cs:?gbBold@@3HA, ebx; int gbBold
0x180009d38  jz      short loc_180009D8C
0x180009d3a  mov     eax, cs:?g_currentFontIndex@@3KA; ulong g_currentFontIndex
0x180009d40  xor     edx, edx; LPCWSTR
0x180009d42  mov     rcx, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180009d49  lea     r8, [rax+rax*4]
0x180009d4d  mov     rcx, [rcx+r8*8+18h]; lpString2
0x180009d52  call    ?IsBoldOnlyTTFont@@YAHPEB_W0@Z; IsBoldOnlyTTFont(wchar_t const *,wchar_t const *)
0x180009d57  test    eax, eax
0x180009d59  jz      short loc_180009D82
0x180009d5b  mov     edx, 0CBh; nIDDlgItem
0x180009d60  mov     rcx, rdi; hDlg
0x180009d63  call    cs:__imp_GetDlgItem
0x180009d6a  nop     dword ptr [rax+rax+00h]
0x180009d6f  mov     rcx, rax; hWnd
0x180009d72  xor     edx, edx; bEnable
0x180009d74  call    cs:__imp_EnableWindow
0x180009d7b  nop     dword ptr [rax+rax+00h]
0x180009d80  jmp     short loc_180009D8C
0x180009d82  mov     cs:?gbUserChoseBold@@3HA, 1; int gbUserChoseBold
0x180009d8c  test    sil, sil
0x180009d8f  jz      short loc_180009DA7
0x180009d91  mov     eax, cs:?g_currentFontIndex@@3KA; ulong g_currentFontIndex
0x180009d97  lea     rcx, [rax+rax*4]
0x180009d9b  mov     rax, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180009da2  mov     rbx, [rax+rcx*8+18h]
0x180009da7  mov     r8d, 1; int
0x180009dad  mov     rdx, rbx; wchar_t *
0x180009db0  mov     rcx, rdi; hDlg
0x180009db3  call    ?FontListCreate@@YAHPEAUHWND__@@PEA_WH@Z; FontListCreate(HWND__ *,wchar_t *,int)
0x180009db8  mov     rcx, rdi; hWnd
0x180009dbb  call    ?PreviewInit@@YAHPEAUHWND__@@@Z; PreviewInit(HWND__ *)
0x180009dc0  mov     edx, eax; int
0x180009dc2  mov     rcx, rdi; hDlg
0x180009dc5  mov     ebx, eax
0x180009dc7  call    ?PreviewUpdate@@YAHPEAUHWND__@@H@Z; PreviewUpdate(HWND__ *,int)
0x180009dcc  neg     ebx
0x180009dce  mov     rcx, rdi; hDlg
0x180009dd1  sbb     edx, edx
0x180009dd3  neg     edx
0x180009dd5  add     edx, 0D5h; nIDDlgItem
0x180009ddb  call    cs:__imp_GetDlgItem
0x180009de2  nop     dword ptr [rax+rax+00h]
0x180009de7  mov     rcx, rax; hWnd
0x180009dea  call    cs:__imp_SetFocus
0x180009df1  nop     dword ptr [rax+rax+00h]
0x180009df6  jmp     loc_180009FC5
0x180009dfb  mov     eax, [r9+10h]
0x180009dff  cmp     eax, 0FFFFFF36h
0x180009e04  jz      loc_180009ED0
0x180009e0a  cmp     eax, 0FFFFFF37h
0x180009e0f  jnz     loc_180009FC5
0x180009e15  mov     edx, 0D5h; nIDDlgItem
0x180009e1a  call    cs:__imp_GetDlgItem
0x180009e21  nop     dword ptr [rax+rax+00h]
0x180009e26  xor     ebx, ebx
0x180009e28  test    rax, rax
0x180009e2b  jz      short loc_180009E77
0x180009e2d  mov     rcx, rax; hWnd
0x180009e30  call    cs:__imp_IsWindowVisible
0x180009e37  nop     dword ptr [rax+rax+00h]
0x180009e3c  test    eax, eax
0x180009e3e  jz      short loc_180009E77
0x180009e40  xor     edx, edx; int
0x180009e42  mov     rcx, rdi; hDlg
0x180009e45  call    ?PreviewUpdate@@YAHPEAUHWND__@@H@Z; PreviewUpdate(HWND__ *,int)
0x180009e4a  xor     edx, edx; nIndex
0x180009e4c  mov     rcx, rdi; hWnd
0x180009e4f  test    eax, eax
0x180009e51  jnz     short loc_180009E68
0x180009e53  lea     r8d, [rbx+1]; dwNewLong
0x180009e57  call    cs:__imp_SetWindowLongPtrW
0x180009e5e  nop     dword ptr [rax+rax+00h]
0x180009e63  jmp     loc_180009FEA
0x180009e68  xor     r8d, r8d; dwNewLong
0x180009e6b  call    cs:__imp_SetWindowLongPtrW
0x180009e72  nop     dword ptr [rax+rax+00h]
0x180009e77  movsxd  rax, cs:?g_currentFontIndex@@3KA; ulong g_currentFontIndex
0x180009e7e  mov     rdx, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x180009e85  mov     rcx, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180009e8c  lea     r8, [rax+rax*4]
0x180009e90  cmp     [rdx+r8*8+0Eh], bx
0x180009e96  jnz     short loc_180009E9F
0x180009e98  mov     eax, [rdx+r8*8+8]
0x180009e9d  jmp     short loc_180009EA4
0x180009e9f  mov     eax, [rdx+r8*8+0Ch]
  ... truncated ...
```
