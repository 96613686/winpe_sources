# CIsoBurnUI::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x14000ad38`
- end: `0x14000ae54`
- name: `?OnInitDialog@CIsoBurnUI@@IEAA_JI_K_JAEAH@Z`
- size: `284`
- prototype: `__int64 __fastcall(CIsoBurnUI *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000b3c0`

## callees

- `0x140001fa0`
- `0x14000a514`
- `0x14000ad38`
- `0x14000be50`

## import_xrefs

- `USER32!SendMessageW` at `0x14000ad9f`
- `USER32!SendMessageW` at `0x14000ad9f`
- `USER32!PostMessageW` at `0x14000ae36`
- `USER32!PostMessageW` at `0x14000ae36`
- `USER32!SetFocus` at `0x14000adf5`
- `USER32!SetFocus` at `0x14000adf5`
- `USER32!SetDlgItemTextW` at `0x14000add1`
- `USER32!SetDlgItemTextW` at `0x14000add1`
- `USER32!RegisterWindowMessageW` at `0x14000adac`
- `USER32!RegisterWindowMessageW` at `0x14000adac`
- `USER32!LoadIconW` at `0x14000ad8a`
- `USER32!LoadIconW` at `0x14000ad8a`
- `USER32!GetDlgItem` at `0x14000adec`
- `USER32!GetDlgItem` at `0x14000ae0d`
- `USER32!GetDlgItem` at `0x14000adec`
- `USER32!GetDlgItem` at `0x14000ae0d`
- `SHLWAPI!PathFindFileNameW` at `0x14000adbf`
- `SHLWAPI!PathFindFileNameW` at `0x14000adbf`
- `UxTheme!EnableThemeDialogTexture` at `0x14000ad78`
- `UxTheme!EnableThemeDialogTexture` at `0x14000ad78`

## pseudocode

```c
__int64 __fastcall CIsoBurnUI::OnInitDialog(HWND *this, __int64 a2, __int64 a3, __int64 a4)
{
  HICON IconW; // rax
  UINT v6; // eax
  const WCHAR *v7; // rcx
  const WCHAR *FileNameW; // rax
  int v9; // eax
  HWND v10; // rcx
  HWND DlgItem; // rax
  HWND v12; // rax
  UINT v13; // edx
  LPARAM v14; // r9
  WPARAM v15; // r8
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      (__int64)this,
      (const EVENT_DESCRIPTOR *)&CDBurn_IsoBurn_Launch_Info,
      a3,
      a4,
      &v17);
  EnableThemeDialogTexture(this[1], 0xAu);
  IconW = LoadIconW(hInstance, (LPCWSTR)0x65);
  SendMessageW(this[1], 0x80u, 0, (LPARAM)IconW);
  v6 = RegisterWindowMessageW(L"QueryCancelAutoPlay");
  v7 = (const WCHAR *)this[16];
  *((_DWORD *)this + 47) = v6;
  FileNameW = PathFindFileNameW(v7);
  SetDlgItemTextW(this[1], 203, FileNameW);
  v9 = CIsoBurnUI::_PopulateDriveList((CIsoBurnUI *)this);
  v10 = this[1];
  if ( v9 < 0 )
  {
    v13 = 32769;
    v14 = 3232428033LL;
    v15 = 1;
    goto LABEL_7;
  }
  DlgItem = GetDlgItem(v10, 205);
  SetFocus(DlgItem);
  if ( *((_DWORD *)this + 34) )
  {
    v12 = GetDlgItem(this[1], 205);
    v10 = this[1];
    v13 = 273;
    v14 = (LPARAM)v12;
    v15 = 205;
LABEL_7:
    PostMessageW(v10, v13, v15, v14);
  }
  return 1;
}

```

## disassembly

```asm
0x14000ad38  push    rbx
0x14000ad3a  sub     rsp, 50h
0x14000ad3e  mov     rax, cs:__security_cookie
0x14000ad45  xor     rax, rsp
0x14000ad48  mov     [rsp+58h+var_18], rax
0x14000ad4d  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x14000ad54  mov     rbx, rcx
0x14000ad57  jz      short loc_14000AD6F
0x14000ad59  lea     rax, [rsp+58h+var_28]
0x14000ad5e  lea     rdx, CDBurn_IsoBurn_Launch_Info; int
0x14000ad65  mov     [rsp+58h+var_38], rax; PEVENT_DATA_DESCRIPTOR
0x14000ad6a  call    McGenEventWrite_EventWriteTransfer
0x14000ad6f  mov     rcx, [rbx+8]; hwnd
0x14000ad73  mov     edx, 0Ah; dwFlags
0x14000ad78  call    cs:__imp_EnableThemeDialogTexture
0x14000ad7e  mov     rcx, cs:hInstance; hInstance
0x14000ad85  mov     edx, 65h ; 'e'; lpIconName
0x14000ad8a  call    cs:__imp_LoadIconW
0x14000ad90  mov     rcx, [rbx+8]; hWnd
0x14000ad94  xor     r8d, r8d; wParam
0x14000ad97  mov     r9, rax; lParam
0x14000ad9a  mov     edx, 80h; Msg
0x14000ad9f  call    cs:__imp_SendMessageW
0x14000ada5  lea     rcx, String; "QueryCancelAutoPlay"
0x14000adac  call    cs:__imp_RegisterWindowMessageW
0x14000adb2  mov     rcx, [rbx+80h]; pszPath
0x14000adb9  mov     [rbx+0BCh], eax
0x14000adbf  call    cs:__imp_PathFindFileNameW
0x14000adc5  mov     rcx, [rbx+8]; hDlg
0x14000adc9  mov     edx, 0CBh; nIDDlgItem
0x14000adce  mov     r8, rax; lpString
0x14000add1  call    cs:__imp_SetDlgItemTextW
0x14000add7  mov     rcx, rbx; this
0x14000adda  call    ?_PopulateDriveList@CIsoBurnUI@@AEAAJXZ; CIsoBurnUI::_PopulateDriveList(void)
0x14000addf  mov     rcx, [rbx+8]; hWnd
0x14000ade3  test    eax, eax
0x14000ade5  js      short loc_14000AE25
0x14000ade7  mov     edx, 0CDh; nIDDlgItem
0x14000adec  call    cs:__imp_GetDlgItem
0x14000adf2  mov     rcx, rax; hWnd
0x14000adf5  call    cs:__imp_SetFocus
0x14000adfb  cmp     dword ptr [rbx+88h], 0
0x14000ae02  jz      short loc_14000AE3C
0x14000ae04  mov     rcx, [rbx+8]; hDlg
0x14000ae08  mov     edx, 0CDh; nIDDlgItem
0x14000ae0d  call    cs:__imp_GetDlgItem
0x14000ae13  mov     rcx, [rbx+8]
0x14000ae17  mov     edx, 111h
0x14000ae1c  mov     r9, rax
0x14000ae1f  lea     r8d, [rdx-44h]
0x14000ae23  jmp     short loc_14000AE36
0x14000ae25  mov     edx, 8001h; Msg
0x14000ae2a  mov     r9d, 0C0AAF001h; lParam
0x14000ae30  mov     r8d, 1; wParam
0x14000ae36  call    cs:__imp_PostMessageW
0x14000ae3c  mov     eax, 1
0x14000ae41  mov     rcx, [rsp+58h+var_18]
0x14000ae46  xor     rcx, rsp; StackCookie
0x14000ae49  call    __security_check_cookie
0x14000ae4e  add     rsp, 50h
0x14000ae52  pop     rbx
0x14000ae53  retn
```
