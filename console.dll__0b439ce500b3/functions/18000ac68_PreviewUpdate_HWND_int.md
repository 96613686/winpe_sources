# PreviewUpdate(HWND__ *,int)

- ea: `0x18000ac68`
- end: `0x18000b01a`
- name: `?PreviewUpdate@@YAHPEAUHWND__@@H@Z`
- size: `946`
- prototype: `__int64 __fastcall(HWND hDlg, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180009980`

## callees

- `0x1800015b0`
- `0x180005ea4`
- `0x180009578`
- `0x18000a9d0`
- `0x18000ac68`
- `0x18000b254`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ad6e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ad6e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000aeba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000aeba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x18000adcc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x18000adcc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000acd0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000ae23`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000afb8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000acd0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000ae23`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18000afb8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x18000af19`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x18000af75`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x18000af19`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x18000af75`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18000ada1`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowTextW` at `0x18000ada1`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x18000ad06`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x18000ad29`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x18000ad06`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SendDlgItemMessageW` at `0x18000ad29`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SetDlgItemTextW` at `0x18000aed2`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SetDlgItemTextW` at `0x18000aed2`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18000adbd`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x18000adbd`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000aca9`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000af02`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000af5e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000af9e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000afcc`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000aca9`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000af02`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000af5e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000af9e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000afcc`
- `ext-ms-win-ntuser-draw-l1-1-0!InvalidateRect` at `0x18000af2e`
- `ext-ms-win-ntuser-draw-l1-1-0!InvalidateRect` at `0x18000af8a`
- `ext-ms-win-ntuser-draw-l1-1-0!InvalidateRect` at `0x18000afe1`
- `ext-ms-win-ntuser-draw-l1-1-0!InvalidateRect` at `0x18000af2e`
- `ext-ms-win-ntuser-draw-l1-1-0!InvalidateRect` at `0x18000af8a`
- `ext-ms-win-ntuser-draw-l1-1-0!InvalidateRect` at `0x18000afe1`

## string_xrefs

- `0x18000ae47`: `onecore\windows\core\console\open\src\propsheet\fontdlg.cpp`

## pseudocode

```c
__int64 __fastcall PreviewUpdate(HWND hDlg, int a2)
{
  HWND DlgItem; // rdi
  int v5; // eax
  int v6; // eax
  int v7; // edx
  int v8; // r8d
  __int64 result; // rax
  int Font; // eax
  const char *v11; // r9
  __int16 *v12; // rdi
  __int64 v13; // rsi
  HWND v14; // rbx
  HWND v15; // rbx
  HWND v16; // rax
  HWND v17; // rax
  LPARAM lParam; // [rsp+20h] [rbp-E0h]
  struct _COORD v19; // [rsp+40h] [rbp-C0h]
  va_list Arguments[3]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Text[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[64]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t v23[64]; // [rsp+160h] [rbp+60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  DlgItem = GetDlgItem(hDlg, (unsigned int)(a2 != 0) + 213);
  v5 = SendMessageW(DlgItem, a2 != 0 ? 392 : 327, 0, 0);
  if ( v5 >= 0 || a2 )
  {
    Font = SendMessageW(DlgItem, a2 != 0 ? 409 : 336, v5, 0);
  }
  else
  {
    v6 = SendDlgItemMessageW(hDlg, 202, 0x188u, 0, 0);
    SendDlgItemMessageW(hDlg, 202, 0x189u, v6, (LPARAM)v23);
    v19.X = 0;
    v19.Y = GetPointSizeInRange(hDlg, v7, v8);
    if ( !v19.Y )
    {
      gbPointSizeError = 1;
      LoadStringW(ghInstance, 5u, Buffer, 60);
      LODWORD(lParam) = 72;
      StringCchPrintfW(Text, 0x3Cu, Buffer, 5, lParam);
      GetWindowTextW(hDlg, Buffer, 60);
      MessageBoxW(hDlg, Text, Buffer, 0x40u);
      SetFocus(DlgItem);
      result = 0;
      gbPointSizeError = 0;
      return result;
    }
    Font = FindCreateFont(54, v23, v19, 0, *((_DWORD *)gpStateInfo + 52));
  }
  if ( Font < 0 )
    Font = DefaultFontIndex;
  if ( Font >= NumberOfFonts )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x636,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\fontdlg.cpp",
      v11);
  if ( g_currentFontIndex != Font )
    g_currentFontIndex = Font;
  v12 = (__int16 *)FontInfo;
  v13 = 5LL * Font;
  Arguments[0] = (va_list)&wszSelectedFont;
  Arguments[1] = *((va_list *)FontInfo + 5 * Font + 3);
  FormatMessageW(0x2800u, ghInstance, 0x3E8u, 0, v23, 0x3Eu, Arguments);
  SetDlgItemTextW(hDlg, 207, v23);
  StringCchPrintfW(Text, 0x3Cu, L"%u", (unsigned int)v12[4 * v13 + 4]);
  v14 = GetDlgItem(hDlg, 210);
  SetWindowTextW(v14, Text);
  InvalidateRect(v14, 0, 1);
  StringCchPrintfW(Text, 0x3Cu, L"%u", (unsigned int)v12[4 * v13 + 5]);
  v15 = GetDlgItem(hDlg, 211);
  SetWindowTextW(v15, Text);
  InvalidateRect(v15, 0, 1);
  v16 = GetDlgItem(hDlg, 215);
  SendMessageW(v16, 0x402u, 0, 0);
  v17 = GetDlgItem(hDlg, 216);
  InvalidateRect(v17, 0, 1);
  return 1;
}

```

## disassembly

```asm
0x18000ac68  mov     [rsp-8+arg_8], rbx
0x18000ac6d  mov     [rsp-8+arg_10], rsi
0x18000ac72  push    rbp
0x18000ac73  push    rdi
0x18000ac74  push    r14
0x18000ac76  lea     rbp, [rsp-0F0h]
0x18000ac7e  sub     rsp, 1F0h
0x18000ac85  mov     rax, cs:__security_cookie
0x18000ac8c  xor     rax, rsp
0x18000ac8f  mov     [rbp+100h+var_20], rax
0x18000ac96  mov     eax, edx
0x18000ac98  mov     ebx, edx
0x18000ac9a  neg     eax
0x18000ac9c  mov     r14, rcx
0x18000ac9f  sbb     edx, edx
0x18000aca1  neg     edx
0x18000aca3  add     edx, 0D5h; nIDDlgItem
0x18000aca9  call    cs:__imp_GetDlgItem
0x18000acb0  nop     dword ptr [rax+rax+00h]
0x18000acb5  mov     ecx, ebx
0x18000acb7  mov     rdi, rax
0x18000acba  neg     ecx
0x18000acbc  mov     rcx, rax; hWnd
0x18000acbf  sbb     edx, edx
0x18000acc1  xor     r9d, r9d; lParam
0x18000acc4  and     edx, 41h
0x18000acc7  xor     r8d, r8d; wParam
0x18000acca  add     edx, 147h; Msg
0x18000acd0  call    cs:__imp_SendMessageW
0x18000acd7  nop     dword ptr [rax+rax+00h]
0x18000acdc  xor     esi, esi
0x18000acde  test    eax, eax
0x18000ace0  jns     loc_18000AE0D
0x18000ace6  test    ebx, ebx
0x18000ace8  jnz     loc_18000AE0D
0x18000acee  mov     ebx, 0CAh
0x18000acf3  mov     [rsp+200h+lParam], rsi; lParam
0x18000acf8  mov     edx, ebx; nIDDlgItem
0x18000acfa  xor     r9d, r9d; wParam
0x18000acfd  mov     r8d, 188h; Msg
0x18000ad03  mov     rcx, r14; hDlg
0x18000ad06  call    cs:__imp_SendDlgItemMessageW
0x18000ad0d  nop     dword ptr [rax+rax+00h]
0x18000ad12  movsxd  r9, eax; wParam
0x18000ad15  mov     r8d, 189h; Msg
0x18000ad1b  lea     rax, [rbp+100h+var_A0]
0x18000ad1f  mov     edx, ebx; nIDDlgItem
0x18000ad21  mov     rcx, r14; hDlg
0x18000ad24  mov     [rsp+200h+lParam], rax; lParam
0x18000ad29  call    cs:__imp_SendDlgItemMessageW
0x18000ad30  nop     dword ptr [rax+rax+00h]
0x18000ad35  mov     rcx, r14; hDlg
0x18000ad38  mov     [rsp+200h+var_1C0.X], si
0x18000ad3d  call    ?GetPointSizeInRange@@YAIPEAUHWND__@@HH@Z; GetPointSizeInRange(HWND__ *,int,int)
0x18000ad42  mov     [rsp+200h+var_1C0.Y], ax
0x18000ad47  test    ax, ax
0x18000ad4a  jnz     loc_18000ADE5
0x18000ad50  mov     rcx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000ad57  lea     ebx, [rsi+5]
0x18000ad5a  mov     edx, ebx; uID
0x18000ad5c  mov     cs:?gbPointSizeError@@3HA, 1; int gbPointSizeError
0x18000ad66  lea     r9d, [rsi+3Ch]; cchBufferMax
0x18000ad6a  lea     r8, [rbp+100h+Buffer]; lpBuffer
0x18000ad6e  call    cs:__imp_LoadStringW
0x18000ad75  nop     dword ptr [rax+rax+00h]
0x18000ad7a  mov     r9d, ebx
0x18000ad7d  mov     dword ptr [rsp+200h+lParam], 48h ; 'H'
0x18000ad85  lea     r8, [rbp+100h+Buffer]; wchar_t *
0x18000ad89  lea     edx, [rsi+3Ch]; unsigned __int64
0x18000ad8c  lea     rcx, [rsp+200h+Text]; wchar_t *
0x18000ad91  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000ad96  lea     r8d, [rsi+3Ch]; nMaxCount
0x18000ad9a  mov     rcx, r14; hWnd
0x18000ad9d  lea     rdx, [rbp+100h+Buffer]; lpString
0x18000ada1  call    cs:__imp_GetWindowTextW
0x18000ada8  nop     dword ptr [rax+rax+00h]
0x18000adad  lea     r9d, [rsi+40h]; uType
0x18000adb1  mov     rcx, r14; hWnd
0x18000adb4  lea     r8, [rbp+100h+Buffer]; lpCaption
0x18000adb8  lea     rdx, [rsp+200h+Text]; lpText
0x18000adbd  call    cs:__imp_MessageBoxW
0x18000adc4  nop     dword ptr [rax+rax+00h]
0x18000adc9  mov     rcx, rdi; hWnd
0x18000adcc  call    cs:__imp_SetFocus
0x18000add3  nop     dword ptr [rax+rax+00h]
0x18000add8  xor     eax, eax
0x18000adda  mov     cs:?gbPointSizeError@@3HA, esi; int gbPointSizeError
0x18000ade0  jmp     loc_18000AFF2
0x18000ade5  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x18000adec  lea     rdx, [rbp+100h+var_A0]; wchar_t *
0x18000adf0  mov     r8d, dword ptr [rsp+200h+var_1C0.X]; struct _COORD
0x18000adf5  xor     r9d, r9d; int
0x18000adf8  mov     ecx, [rax+0D0h]
0x18000adfe  mov     dword ptr [rsp+200h+lParam], ecx; unsigned int
0x18000ae02  lea     ecx, [r9+36h]; unsigned int
0x18000ae06  call    ?FindCreateFont@@YAHKPEA_WU_COORD@@JI@Z; FindCreateFont(ulong,wchar_t *,_COORD,long,uint)
0x18000ae0b  jmp     short loc_18000AE2F
0x18000ae0d  neg     ebx
0x18000ae0f  movsxd  r8, eax; wParam
0x18000ae12  mov     rcx, rdi; hWnd
0x18000ae15  sbb     edx, edx
0x18000ae17  xor     r9d, r9d; lParam
0x18000ae1a  and     edx, 49h
0x18000ae1d  add     edx, 150h; Msg
0x18000ae23  call    cs:__imp_SendMessageW
0x18000ae2a  nop     dword ptr [rax+rax+00h]
0x18000ae2f  test    eax, eax
0x18000ae31  cmovs   eax, cs:?DefaultFontIndex@@3KA; ulong DefaultFontIndex
0x18000ae38  cmp     eax, cs:?NumberOfFonts@@3KA; ulong NumberOfFonts
0x18000ae3e  jb      short loc_18000AE59
0x18000ae40  mov     rcx, [rbp+108h]; this
0x18000ae47  lea     r8, aOnecoreWindows_2; "onecore\\windows\\core\\console\\open\\"...
0x18000ae4e  mov     edx, 636h; void *
0x18000ae53  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000ae59  cmp     cs:?g_currentFontIndex@@3KA, eax; ulong g_currentFontIndex
0x18000ae5f  jz      short loc_18000AE67
0x18000ae61  mov     cs:?g_currentFontIndex@@3KA, eax; ulong g_currentFontIndex
0x18000ae67  mov     rdi, cs:?FontInfo@@3PEAU_FONT_INFO@@EA; _FONT_INFO * FontInfo
0x18000ae6e  xor     r9d, r9d; dwLanguageId
0x18000ae71  mov     rdx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; lpSource
0x18000ae78  mov     r8d, 3E8h; dwMessageId
0x18000ae7e  cdqe
0x18000ae80  mov     ecx, 2800h; dwFlags
0x18000ae85  lea     rsi, [rax+rax*4]
0x18000ae89  lea     rax, ?wszSelectedFont@@3PA_WA; wchar_t near * wszSelectedFont
0x18000ae90  mov     [rsp+200h+var_1B8], rax
0x18000ae95  mov     rax, [rdi+rsi*8+18h]
0x18000ae9a  mov     [rsp+200h+var_1B0], rax
0x18000ae9f  lea     rax, [rsp+200h+var_1B8]
0x18000aea4  mov     [rsp+200h+Arguments], rax; Arguments
0x18000aea9  lea     rax, [rbp+100h+var_A0]
0x18000aead  mov     [rsp+200h+nSize], 3Eh ; '>'; nSize
0x18000aeb5  mov     [rsp+200h+lParam], rax; lpBuffer
0x18000aeba  call    cs:__imp_FormatMessageW
0x18000aec1  nop     dword ptr [rax+rax+00h]
0x18000aec6  lea     r8, [rbp+100h+var_A0]; lpString
0x18000aeca  mov     edx, 0CFh; nIDDlgItem
0x18000aecf  mov     rcx, r14; hDlg
0x18000aed2  call    cs:__imp_SetDlgItemTextW
0x18000aed9  nop     dword ptr [rax+rax+00h]
0x18000aede  movsx   r9d, word ptr [rdi+rsi*8+8]
0x18000aee4  lea     r8, aU; "%u"
0x18000aeeb  mov     edx, 3Ch ; '<'; unsigned __int64
0x18000aef0  lea     rcx, [rsp+200h+Text]; wchar_t *
0x18000aef5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000aefa  mov     edx, 0D2h; nIDDlgItem
0x18000aeff  mov     rcx, r14; hDlg
0x18000af02  call    cs:__imp_GetDlgItem
0x18000af09  nop     dword ptr [rax+rax+00h]
0x18000af0e  mov     rcx, rax; hWnd
0x18000af11  lea     rdx, [rsp+200h+Text]; lpString
0x18000af16  mov     rbx, rax
0x18000af19  call    cs:__imp_SetWindowTextW
0x18000af20  nop     dword ptr [rax+rax+00h]
0x18000af25  xor     edx, edx; lpRect
0x18000af27  mov     rcx, rbx; hWnd
0x18000af2a  lea     r8d, [rdx+1]; bErase
0x18000af2e  call    cs:__imp_InvalidateRect
0x18000af35  nop     dword ptr [rax+rax+00h]
0x18000af3a  movsx   r9d, word ptr [rdi+rsi*8+0Ah]
0x18000af40  lea     r8, aU; "%u"
0x18000af47  mov     edx, 3Ch ; '<'; unsigned __int64
0x18000af4c  lea     rcx, [rsp+200h+Text]; wchar_t *
0x18000af51  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000af56  mov     edx, 0D3h; nIDDlgItem
0x18000af5b  mov     rcx, r14; hDlg
0x18000af5e  call    cs:__imp_GetDlgItem
0x18000af65  nop     dword ptr [rax+rax+00h]
0x18000af6a  mov     rcx, rax; hWnd
0x18000af6d  lea     rdx, [rsp+200h+Text]; lpString
0x18000af72  mov     rbx, rax
0x18000af75  call    cs:__imp_SetWindowTextW
0x18000af7c  nop     dword ptr [rax+rax+00h]
0x18000af81  xor     edx, edx; lpRect
0x18000af83  mov     rcx, rbx; hWnd
0x18000af86  lea     r8d, [rdx+1]; bErase
0x18000af8a  call    cs:__imp_InvalidateRect
0x18000af91  nop     dword ptr [rax+rax+00h]
0x18000af96  mov     edx, 0D7h; nIDDlgItem
0x18000af9b  mov     rcx, r14; hDlg
0x18000af9e  call    cs:__imp_GetDlgItem
0x18000afa5  nop     dword ptr [rax+rax+00h]
0x18000afaa  xor     r9d, r9d; lParam
0x18000afad  xor     r8d, r8d; wParam
0x18000afb0  mov     rcx, rax; hWnd
0x18000afb3  mov     edx, 402h; Msg
0x18000afb8  call    cs:__imp_SendMessageW
0x18000afbf  nop     dword ptr [rax+rax+00h]
0x18000afc4  mov     edx, 0D8h; nIDDlgItem
0x18000afc9  mov     rcx, r14; hDlg
0x18000afcc  call    cs:__imp_GetDlgItem
0x18000afd3  nop     dword ptr [rax+rax+00h]
0x18000afd8  xor     edx, edx; lpRect
0x18000afda  mov     rcx, rax; hWnd
0x18000afdd  lea     r8d, [rdx+1]; bErase
0x18000afe1  call    cs:__imp_InvalidateRect
0x18000afe8  nop     dword ptr [rax+rax+00h]
0x18000afed  mov     eax, 1
0x18000aff2  mov     rcx, [rbp+100h+var_20]
0x18000aff9  xor     rcx, rsp; StackCookie
0x18000affc  call    __security_check_cookie
0x18000b001  lea     r11, [rsp+200h+var_10]
0x18000b009  mov     rbx, [r11+28h]
0x18000b00d  mov     rsi, [r11+30h]
0x18000b011  mov     rsp, r11
0x18000b014  pop     r14
0x18000b016  pop     rdi
0x18000b017  pop     rbp
0x18000b018  retn
```
