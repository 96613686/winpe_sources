# AddFavoritesWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800d4dc0`
- end: `0x1800d5445`
- name: `?AddFavoritesWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1669`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180011230`
- `0x1800ac198`
- `0x1800d4dc0`
- `0x1800d544c`
- `0x1800d5ac4`
- `0x1800d5b4c`
- `0x1800d5e7c`
- `0x1800d5f04`
- `0x1800d60b8`
- `0x1800d6a90`
- `0x1800d6fa0`
- `0x1803f5fa4`
- `0x180401264`
- `0x1804018b4`
- `0x180442e30`
- `0x1804e6bf0`
- `0x1804e9744`
- `0x180524b78`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x1800d4efe`
- `KERNEL32!CreateDirectoryW` at `0x1800d4efe`
- `KERNEL32!GetLastError` at `0x1800d4f9a`
- `KERNEL32!GetLastError` at `0x1800d4f9a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1800d5326`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1800d5326`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBlanksW` at `0x1800d5065`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBlanksW` at `0x1800d5065`
- `USER32!GetPropW` at `0x1800d4e05`
- `USER32!GetPropW` at `0x1800d4e05`
- `USER32!SetDlgItemTextW` at `0x1800d52af`
- `USER32!SetDlgItemTextW` at `0x1800d52af`
- `USER32!SetFocus` at `0x1800d5369`
- `USER32!SetFocus` at `0x1800d5369`
- `USER32!GetDlgItemTextW` at `0x1800d505b`
- `USER32!GetDlgItemTextW` at `0x1800d505b`
- `USER32!SetPropW` at `0x1800d5236`
- `USER32!SetPropW` at `0x1800d5236`
- `USER32!RemovePropW` at `0x1800d5413`
- `USER32!RemovePropW` at `0x1800d5413`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800d4eb1`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800d4ee5`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800d4eb1`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800d4ee5`
- `USER32!SendMessageW` at `0x1800d4ea1`
- `USER32!SendMessageW` at `0x1800d4f57`
- `USER32!SendMessageW` at `0x1800d529f`
- `USER32!SendMessageW` at `0x1800d5389`
- `USER32!SendMessageW` at `0x1800d4ea1`
- `USER32!SendMessageW` at `0x1800d4f57`
- `USER32!SendMessageW` at `0x1800d529f`
- `USER32!SendMessageW` at `0x1800d5389`
- `USER32!IsWindowVisible` at `0x1800d5084`
- `USER32!IsWindowVisible` at `0x1800d5084`
- `USER32!EnableWindow` at `0x1800d52d7`
- `USER32!EnableWindow` at `0x1800d52d7`
- `USER32!EndDialog` at `0x1800d500e`
- `USER32!EndDialog` at `0x1800d51dd`
- `USER32!EndDialog` at `0x1800d500e`
- `USER32!EndDialog` at `0x1800d51dd`
- `USER32!GetDlgItem` at `0x1800d4e8d`
- `USER32!GetDlgItem` at `0x1800d4f33`
- `USER32!GetDlgItem` at `0x1800d4fc5`
- `USER32!GetDlgItem` at `0x1800d5073`
- `USER32!GetDlgItem` at `0x1800d528b`
- `USER32!GetDlgItem` at `0x1800d52c7`
- `USER32!GetDlgItem` at `0x1800d5360`
- `USER32!GetDlgItem` at `0x1800d5375`
- `USER32!GetDlgItem` at `0x1800d4e8d`
- `USER32!GetDlgItem` at `0x1800d4f33`
- `USER32!GetDlgItem` at `0x1800d4fc5`
- `USER32!GetDlgItem` at `0x1800d5073`
- `USER32!GetDlgItem` at `0x1800d528b`
- `USER32!GetDlgItem` at `0x1800d52c7`
- `USER32!GetDlgItem` at `0x1800d5360`
- `USER32!GetDlgItem` at `0x1800d5375`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1800d5255`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1800d5255`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800d5148`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800d5148`

## string_xrefs

- `0x1800d4f1f`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x1800d510d`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x1800d5305`: `Software\Microsoft\Internet Explorer\LowRegistry`

## pseudocode

```c
__int64 __fastcall AddFavoritesWndProc(HWND hWnd, int a2, int a3, const unsigned __int16 **a4)
{
  struct _ADDTOFAV *PropW; // rax
  __int64 v9; // rcx
  struct _ADDTOFAV *v10; // r15
  int v11; // edi
  int v12; // edi
  int v13; // edi
  HWND v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rbx
  HWND v17; // rbx
  const unsigned __int16 *v18; // r8
  DWORD LastError; // eax
  HWND v20; // rax
  LPARAM v21; // r9
  UINT v22; // edx
  WPARAM v23; // r8
  HWND v24; // rcx
  signed int v26; // ebx
  HWND v27; // rax
  HWND v28; // r12
  const unsigned __int16 *v29; // r8
  int FavoritePathFromCB; // r13d
  __int64 v31; // r12
  unsigned __int64 v32; // rax
  __int64 v33; // rax
  WPARAM v34; // r15
  __int64 v35; // rax
  HWND DlgItem; // rax
  HWND v37; // rax
  HWND v38; // rax
  HWND v39; // rax
  __int64 v40; // rdx
  int ppidl; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-BCh] BYREF
  WCHAR pszSpec[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR PathName[264]; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+268h] [rbp+168h]
  unsigned __int16 pvData; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v47[526]; // [rsp+272h] [rbp+172h] BYREF

  PropW = (struct _ADDTOFAV *)GetPropW(hWnd, L"SHDOC_ATFPROP");
  v10 = PropW;
  v11 = a2 - 2;
  if ( !v11 )
  {
    UnInitATFDialog(hWnd, PropW);
    RemovePropW(hWnd, L"SHDOC_ATFPROP");
    return 0;
  }
  v12 = v11 - 76;
  if ( !v12 )
  {
    if ( a4[1] == (const unsigned __int16 *)1016 )
    {
      if ( ((*((_DWORD *)a4 + 4) + 4) & 0xFFFFFFFD) == 0
        && PropW
        && (unsigned int)SHIsExternalUrlSafeForNavigation((char *)PropW + 64) )
      {
        ShowUrlInNewBrowserInstance((OLECHAR *)v10 + 32);
      }
      return 0;
    }
    if ( a4[1] == (const unsigned __int16 *)1018 )
    {
      if ( ((*((_DWORD *)a4 + 4) + 4) & 0xFFFFFFFD) != 0 )
        return 0;
      v40 = 73;
    }
    else
    {
      if ( a4[1] != (const unsigned __int16 *)1021 || ((*((_DWORD *)a4 + 4) + 4) & 0xFFFFFFFD) != 0 )
        return 0;
      v40 = 78;
    }
    IELaunchPlatformHelp(v9, v40);
    return 0;
  }
  v13 = v12 - 194;
  if ( !v13 )
  {
    SetPropW(hWnd, L"SHDOC_ATFPROP", a4);
    v34 = 259;
    if ( SHGetSpecialFolderPathW(0, pszSpec, 6, 1) )
    {
      v35 = -1;
      do
        ++v35;
      while ( pszSpec[v35] );
      v34 = 253 - v35;
    }
    DlgItem = GetDlgItem(hWnd, 1005);
    SendMessageW(DlgItem, 0xC5u, v34, 0);
    SetDlgItemTextW(hWnd, 1005, a4[2]);
    EnableOKButtonFromID(hWnd);
    v37 = GetDlgItem(hWnd, 1007);
    if ( v37 )
      EnableWindow(v37, 1);
    a4[6] = 0;
    pvData = 0;
    pcbData[0] = 520;
    if ( RegGetValueW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
           L"AddToFavoritesInitialSelection",
           2u,
           0,
           &pvData,
           pcbData) )
    {
      pvData = 0;
    }
    InitATFDialog(hWnd, *a4, (struct _ADDTOFAV *)a4, &pvData, 1);
    if ( *((_DWORD *)a4 + 10) != 3 )
      return 0;
    v38 = GetDlgItem(hWnd, 1005);
    SetFocus(v38);
    v39 = GetDlgItem(hWnd, 1005);
    v21 = -1;
    v23 = 0;
    v24 = v39;
    v22 = 177;
    goto LABEL_61;
  }
  if ( v13 == 1 )
  {
    if ( (unsigned __int16)a3 != 1 )
    {
      switch ( (unsigned __int16)a3 )
      {
        case 2u:
          FreeComboStrings(hWnd);
          EndDialog(hWnd, 2);
          return 1;
        case 0x3EDu:
          if ( HIWORD(a3) == 1024 )
            EnableOKButtonFromID(hWnd);
          return 0;
        case 0x3EFu:
          if ( PropW )
          {
            memset_0(PathName, 0, 0x218u);
            *(_QWORD *)pszSpec = v10;
            v14 = GetDlgItem(hWnd, 1031);
            v45 = SendMessageW(v14, 0x147u, 0, 0);
            v15 = SetThreadDpiAwarenessContext(-2);
            v16 = SHFusionDialogBoxParam(
                    g_hinstMUI,
                    (LPCWSTR)0x1180,
                    hWnd,
                    (DLGPROC)NewFavoritesFolderDlgProc,
                    (LPARAM)pszSpec);
            SetThreadDpiAwarenessContext(v15);
            if ( v16 == 1 )
            {
              if ( CreateDirectoryW(PathName, 0) )
              {
                SHRegSetString(
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
                  L"AddToFavoritesInitialSelection",
                  PathName);
                v17 = GetDlgItem(hWnd, 1031);
                if ( v17 )
                {
                  FreeComboStrings(hWnd);
                  SendMessageW(v17, 0x14Bu, 0, 0);
                  v18 = *(const unsigned __int16 **)v10;
                  ppidl = 0;
                  AddFoldersToCB(v17, v10, v18, PathName, 0, (LPITEMIDLIST)&ppidl, 0, 0);
                  AdjustCBDropWidth(v17, ppidl);
                }
              }
              else
              {
                LastError = GetLastError();
                ShowFormattedSystemErrorDialog(g_hinstMUI, hWnd, LastError, 0x2F5u, 0x40u);
              }
              v20 = GetDlgItem(hWnd, 1);
              v21 = 1;
              v22 = 40;
              v23 = (WPARAM)v20;
              v24 = hWnd;
LABEL_61:
              SendMessageW(v24, v22, v23, v21);
              return 0;
            }
          }
          break;
      }
      return 0;
    }
    pvData = 0;
    v26 = 1;
    memset_0(v47, 0, 0x206u);
    if ( v10 )
    {
      GetDlgItemTextW(hWnd, 1005, *((LPWSTR *)v10 + 2), *((_DWORD *)v10 + 6));
      PathRemoveBlanksW(*((LPWSTR *)v10 + 2));
      v27 = GetDlgItem(hWnd, 1031);
      v28 = v27;
      if ( !v27 || !IsWindowVisible(v27) )
        v26 = 0;
      v29 = *(const unsigned __int16 **)v10;
      pcbData[0] = v26;
      if ( (int)StringCchCopyW(&pvData, 0x104u, v29) < 0 )
        return 0;
      if ( v26 )
        FavoritePathFromCB = GetFavoritePathFromCB(v28, *(unsigned __int16 **)v10, *((_DWORD *)v10 + 2));
      else
        FavoritePathFromCB = 1;
      v26 = FavoritePathFromCB;
      if ( !FavoritePathFromCB )
        goto LABEL_48;
      v31 = -1;
      v32 = -1;
      do
        ++v32;
      while ( *(_WORD *)(*((_QWORD *)v10 + 2) + 2 * v32) );
      ppidl = 1;
      if ( v32 >= 0x104 )
        goto LABEL_47;
      if ( pcbData[0] )
        SHRegSetString(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
          L"AddToFavoritesInitialSelection",
          *(const unsigned __int16 **)v10);
      v26 = 0;
      if ( (int)StringCchCopyW(pszSpec, 0x104u, *((const unsigned __int16 **)v10 + 2)) >= 0 )
        v26 = FavoritePathFromCB;
      if ( !v26 )
        goto LABEL_45;
      if ( PathCleanupSpec(0, pszSpec) )
      {
        IEMessageBox(g_hinstMUI, hWnd, (const unsigned __int16 *)0x31B, (const unsigned __int16 *)0x2F5, 0x10u);
LABEL_45:
        v26 = 0;
LABEL_48:
        StringCchCopyW(*(unsigned __int16 **)v10, *((unsigned int *)v10 + 2), &pvData);
        return v26;
      }
      ppidl = 1;
      if ( !(unsigned int)QualifyFileName(v10) )
        goto LABEL_47;
      v33 = -1;
      do
        ++v33;
      while ( *(_WORD *)(*(_QWORD *)v10 + 2 * v33) );
      do
        ++v31;
      while ( *(_WORD *)(*((_QWORD *)v10 + 2) + 2 * v31) );
      ppidl = 1;
      if ( (unsigned __int64)(v31 + v33 + 2) >= 0x104 )
      {
LABEL_47:
        IEMessageBox(g_hinstMUI, hWnd, (const unsigned __int16 *)0x32A, (const unsigned __int16 *)0x2F5, 0x10u);
        v26 = 0;
        goto LABEL_48;
      }
      if ( *((_DWORD *)v10 + 10) != 2 && !(unsigned int)ConfirmAddToFavorites(hWnd, v10) )
        goto LABEL_45;
      FreeComboStrings(hWnd);
      EndDialog(hWnd, 1);
    }
    return v26;
  }
  return 0;
}

```

## disassembly

```asm
0x1800d4dc0  mov     [rsp-8+arg_8], rbx
0x1800d4dc5  push    rbp
0x1800d4dc6  push    rsi
0x1800d4dc7  push    rdi
0x1800d4dc8  push    r12
0x1800d4dca  push    r13
0x1800d4dcc  push    r14
0x1800d4dce  push    r15
0x1800d4dd0  lea     rbp, [rsp-390h]
0x1800d4dd8  sub     rsp, 490h
0x1800d4ddf  mov     rax, cs:__security_cookie
0x1800d4de6  xor     rax, rsp
0x1800d4de9  mov     [rbp+3C0h+var_40], rax
0x1800d4df0  mov     edi, edx
0x1800d4df2  lea     r13, aShdocAtfprop; "SHDOC_ATFPROP"
0x1800d4df9  mov     rdx, r13; lpString
0x1800d4dfc  mov     rbx, r9
0x1800d4dff  mov     rsi, r8
0x1800d4e02  mov     r14, rcx
0x1800d4e05  call    cs:__imp_GetPropW
0x1800d4e0b  mov     r12d, 2
0x1800d4e11  mov     r15, rax
0x1800d4e14  sub     edi, r12d
0x1800d4e17  jz      loc_1800D5402
0x1800d4e1d  sub     edi, 4Ch ; 'L'
0x1800d4e20  jz      loc_1800D5394
0x1800d4e26  sub     edi, 0C2h
0x1800d4e2c  jz      loc_1800D522D
0x1800d4e32  cmp     edi, 1
0x1800d4e35  jnz     loc_1800D5419
0x1800d4e3b  movzx   ecx, si
0x1800d4e3e  sub     ecx, edi
0x1800d4e40  jz      loc_1800D501E
0x1800d4e46  sub     ecx, edi
0x1800d4e48  jz      loc_1800D5000
0x1800d4e4e  sub     ecx, 3EBh
0x1800d4e54  jz      loc_1800D4FDE
0x1800d4e5a  cmp     ecx, r12d
0x1800d4e5d  jnz     loc_1800D5419
0x1800d4e63  xor     esi, esi
0x1800d4e65  test    rax, rax
0x1800d4e68  jz      loc_1800D5419
0x1800d4e6e  xor     edx, edx; Val
0x1800d4e70  lea     rcx, [rsp+4C0h+PathName]; void *
0x1800d4e75  mov     r8d, 218h; Size
0x1800d4e7b  call    memset_0
0x1800d4e80  mov     edx, 407h; nIDDlgItem
0x1800d4e85  mov     qword ptr [rsp+4C0h+pszSpec], r15
0x1800d4e8a  mov     rcx, r14; hDlg
0x1800d4e8d  call    cs:__imp_GetDlgItem
0x1800d4e93  xor     r9d, r9d; lParam
0x1800d4e96  xor     r8d, r8d; wParam
0x1800d4e99  mov     rcx, rax; hWnd
0x1800d4e9c  mov     edx, 147h; Msg
0x1800d4ea1  call    cs:__imp_SendMessageW
0x1800d4ea7  lea     rcx, [rsi-2]
0x1800d4eab  mov     [rbp+3C0h+var_258], eax
0x1800d4eb1  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800d4eb7  mov     rcx, cs:g_hinstMUI; hInstance
0x1800d4ebe  lea     r9, ?NewFavoritesFolderDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800d4ec5  mov     rdi, rax
0x1800d4ec8  mov     r8, r14; hWndParent
0x1800d4ecb  lea     rax, [rsp+4C0h+pszSpec]
0x1800d4ed0  mov     edx, 1180h; lpTemplateName
0x1800d4ed5  mov     [rsp+4C0h+pdwType], rax; LPARAM
0x1800d4eda  call    SHFusionDialogBoxParam
0x1800d4edf  mov     rcx, rdi
0x1800d4ee2  mov     rbx, rax
0x1800d4ee5  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800d4eeb  lea     edi, [rsi+1]
0x1800d4eee  cmp     rbx, rdi
0x1800d4ef1  jnz     loc_1800D5419
0x1800d4ef7  xor     edx, edx; lpSecurityAttributes
0x1800d4ef9  lea     rcx, [rsp+4C0h+PathName]; lpPathName
0x1800d4efe  call    cs:__imp_CreateDirectoryW
0x1800d4f04  test    eax, eax
0x1800d4f06  jz      loc_1800D4F9A
0x1800d4f0c  lea     r9, [rsp+4C0h+PathName]; unsigned __int16 *
0x1800d4f11  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800d4f18  lea     r8, pszValue; "AddToFavoritesInitialSelection"
0x1800d4f1f  lea     rdx, pszSubKey; "Software\\Microsoft\\Internet Explorer"...
0x1800d4f26  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800d4f2b  mov     edx, 407h; nIDDlgItem
0x1800d4f30  mov     rcx, r14; hDlg
0x1800d4f33  call    cs:__imp_GetDlgItem
0x1800d4f39  mov     rbx, rax
0x1800d4f3c  test    rax, rax
0x1800d4f3f  jz      short loc_1800D4FC0
0x1800d4f41  mov     rcx, r14
0x1800d4f44  call    FreeComboStrings
0x1800d4f49  xor     r9d, r9d; lParam
0x1800d4f4c  xor     r8d, r8d; wParam
0x1800d4f4f  mov     edx, 14Bh; Msg
0x1800d4f54  mov     rcx, rbx; hWnd
0x1800d4f57  call    cs:__imp_SendMessageW
0x1800d4f5d  mov     r8, [r15]; unsigned __int16 *
0x1800d4f60  lea     rax, [rsp+4C0h+ppidl]
0x1800d4f65  mov     [rsp+4C0h+var_488], rsi; struct IShellFolder *
0x1800d4f6a  lea     r9, [rsp+4C0h+PathName]; unsigned __int16 *
0x1800d4f6f  mov     [rsp+4C0h+pcbData], rsi; struct _ITEMIDLIST_ABSOLUTE *
0x1800d4f74  mov     rdx, r15; struct _ADDTOFAV *
0x1800d4f77  mov     [rsp+4C0h+pvData], rax; ppidl
0x1800d4f7c  mov     rcx, rbx; HWND
0x1800d4f7f  mov     dword ptr [rsp+4C0h+pdwType], esi; int
0x1800d4f83  mov     [rsp+4C0h+ppidl], esi
0x1800d4f87  call    ?AddFoldersToCB@@YAXPEAUHWND__@@PEAU_ADDTOFAV@@PEBG2HPEAHPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellFolder@@@Z; AddFoldersToCB(HWND__ *,_ADDTOFAV *,ushort const *,ushort const *,int,int *,_ITEMIDLIST_ABSOLUTE const *,IShellFolder *)
0x1800d4f8c  mov     edx, [rsp+4C0h+ppidl]; int
0x1800d4f90  mov     rcx, rbx; hWnd
0x1800d4f93  call    ?AdjustCBDropWidth@@YAXPEAUHWND__@@H@Z; AdjustCBDropWidth(HWND__ *,int)
0x1800d4f98  jmp     short loc_1800D4FC0
0x1800d4f9a  call    cs:__imp_GetLastError
0x1800d4fa0  mov     rcx, cs:g_hinstMUI; hAppInst
0x1800d4fa7  mov     r9d, 2F5h; unsigned int
0x1800d4fad  mov     r8d, eax; unsigned int
0x1800d4fb0  mov     dword ptr [rsp+4C0h+pdwType], 40h ; '@'; unsigned int
0x1800d4fb8  mov     rdx, r14; hWnd
0x1800d4fbb  call    ?ShowFormattedSystemErrorDialog@@YAXPEAUHINSTANCE__@@PEAUHWND__@@KII@Z; ShowFormattedSystemErrorDialog(HINSTANCE__ *,HWND__ *,ulong,uint,uint)
0x1800d4fc0  mov     edx, edi; nIDDlgItem
0x1800d4fc2  mov     rcx, r14; hDlg
0x1800d4fc5  call    cs:__imp_GetDlgItem
0x1800d4fcb  mov     r9, rdi
0x1800d4fce  mov     edx, 28h ; '('
0x1800d4fd3  mov     r8, rax
0x1800d4fd6  mov     rcx, r14
0x1800d4fd9  jmp     loc_1800D5389
0x1800d4fde  shr     rsi, 10h
0x1800d4fe2  mov     eax, 400h
0x1800d4fe7  cmp     si, ax
0x1800d4fea  jnz     loc_1800D5419
0x1800d4ff0  lea     edx, [rax-13h]
0x1800d4ff3  mov     rcx, r14; hWnd
0x1800d4ff6  call    EnableOKButtonFromID
0x1800d4ffb  jmp     loc_1800D5419
0x1800d5000  mov     rcx, r14
0x1800d5003  call    FreeComboStrings
0x1800d5008  mov     rdx, r12; nResult
0x1800d500b  mov     rcx, r14; hDlg
0x1800d500e  call    cs:__imp_EndDialog
0x1800d5014  mov     eax, 1
0x1800d5019  jmp     loc_1800D541B
0x1800d501e  mov     edi, 1
0x1800d5023  lea     rcx, [rbp+3C0h+var_24E]; void *
0x1800d502a  xor     esi, esi
0x1800d502c  xor     edx, edx; Val
0x1800d502e  mov     r8d, 206h; Size
0x1800d5034  mov     [rbp+3C0h+var_250], si
0x1800d503b  mov     ebx, edi
0x1800d503d  call    memset_0
0x1800d5042  test    r15, r15
0x1800d5045  jz      loc_1800D5225
0x1800d504b  mov     r9d, [r15+18h]; cchMax
0x1800d504f  mov     edx, 3EDh; nIDDlgItem
0x1800d5054  mov     r8, [r15+10h]; lpString
0x1800d5058  mov     rcx, r14; hDlg
0x1800d505b  call    cs:__imp_GetDlgItemTextW
0x1800d5061  mov     rcx, [r15+10h]; pszPath
0x1800d5065  call    cs:__imp_PathRemoveBlanksW
0x1800d506b  mov     edx, 407h; nIDDlgItem
0x1800d5070  mov     rcx, r14; hDlg
0x1800d5073  call    cs:__imp_GetDlgItem
0x1800d5079  mov     r12, rax
0x1800d507c  test    rax, rax
0x1800d507f  jz      short loc_1800D508E
0x1800d5081  mov     rcx, rax; hWnd
0x1800d5084  call    cs:__imp_IsWindowVisible
0x1800d508a  test    eax, eax
0x1800d508c  jnz     short loc_1800D5090
0x1800d508e  mov     ebx, esi
0x1800d5090  mov     r8, [r15]; unsigned __int16 *
0x1800d5093  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x1800d509a  mov     edx, 104h; unsigned __int64
0x1800d509f  mov     [rsp+4C0h+var_47C], ebx
0x1800d50a3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d50a8  test    eax, eax
0x1800d50aa  js      loc_1800D5223
0x1800d50b0  test    ebx, ebx
0x1800d50b2  jz      short loc_1800D50C8
0x1800d50b4  mov     r8d, [r15+8]; int
0x1800d50b8  mov     rcx, r12; hWnd
0x1800d50bb  mov     rdx, [r15]; unsigned __int16 *
0x1800d50be  call    ?GetFavoritePathFromCB@@YAHPEAUHWND__@@PEAGH@Z; GetFavoritePathFromCB(HWND__ *,ushort *,int)
0x1800d50c3  mov     r13d, eax
0x1800d50c6  jmp     short loc_1800D50CB
0x1800d50c8  mov     r13d, edi
0x1800d50cb  mov     ebx, r13d
0x1800d50ce  test    r13d, r13d
0x1800d50d1  jz      loc_1800D520E
0x1800d50d7  mov     rcx, [r15+10h]
0x1800d50db  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800d50df  mov     rax, r12
0x1800d50e2  inc     rax
0x1800d50e5  cmp     [rcx+rax*2], si
0x1800d50e9  jnz     short loc_1800D50E2
0x1800d50eb  mov     ebx, 104h
0x1800d50f0  mov     [rsp+4C0h+ppidl], edi
0x1800d50f4  cmp     rax, rbx
0x1800d50f7  jnb     loc_1800D51E5
0x1800d50fd  cmp     [rsp+4C0h+var_47C], esi
0x1800d5101  jz      short loc_1800D5120
0x1800d5103  mov     r9, [r15]; unsigned __int16 *
0x1800d5106  lea     r8, pszValue; "AddToFavoritesInitialSelection"
0x1800d510d  lea     rdx, pszSubKey; "Software\\Microsoft\\Internet Explorer"...
0x1800d5114  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800d511b  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800d5120  mov     r8, [r15+10h]; unsigned __int16 *
0x1800d5124  lea     rcx, [rsp+4C0h+pszSpec]; unsigned __int16 *
0x1800d5129  mov     rdx, rbx; unsigned __int64
0x1800d512c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d5131  test    eax, eax
0x1800d5133  mov     ebx, esi
0x1800d5135  cmovns  ebx, r13d
0x1800d5139  test    ebx, ebx
0x1800d513b  jz      loc_1800D51CB
0x1800d5141  lea     rdx, [rsp+4C0h+pszSpec]; pszSpec
0x1800d5146  xor     ecx, ecx; pszDir
0x1800d5148  call    cs:__imp_PathCleanupSpec
0x1800d514e  test    eax, eax
0x1800d5150  jz      short loc_1800D5175
0x1800d5152  mov     rcx, cs:g_hinstMUI; HINSTANCE
0x1800d5159  mov     r9d, 2F5h; unsigned __int16 *
0x1800d515f  mov     rdx, r14; hWnd
0x1800d5162  mov     dword ptr [rsp+4C0h+pdwType], 10h; unsigned int
0x1800d516a  lea     r8d, [r9+26h]; unsigned __int16 *
0x1800d516e  call    ?IEMessageBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@PEBG2IZZ; IEMessageBox(HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,uint,...)
0x1800d5173  jmp     short loc_1800D51CB
0x1800d5175  mov     rcx, r15; struct _ADDTOFAV *
0x1800d5178  mov     [rsp+4C0h+ppidl], edi
0x1800d517c  call    ?QualifyFileName@@YAHPEAU_ADDTOFAV@@@Z; QualifyFileName(_ADDTOFAV *)
0x1800d5181  test    eax, eax
0x1800d5183  jz      short loc_1800D51E5
0x1800d5185  mov     rcx, [r15]
0x1800d5188  mov     rax, r12
0x1800d518b  inc     rax
0x1800d518e  cmp     [rcx+rax*2], si
0x1800d5192  jnz     short loc_1800D518B
0x1800d5194  mov     rcx, [r15+10h]
0x1800d5198  inc     r12
0x1800d519b  cmp     [rcx+r12*2], si
0x1800d51a0  jnz     short loc_1800D5198
0x1800d51a2  add     rax, 2
0x1800d51a6  mov     [rsp+4C0h+ppidl], edi
0x1800d51aa  add     rax, r12
0x1800d51ad  cmp     rax, 104h
0x1800d51b3  jnb     short loc_1800D51E5
0x1800d51b5  cmp     dword ptr [r15+28h], 2
0x1800d51ba  jz      short loc_1800D51CF
0x1800d51bc  mov     rdx, r15; struct _ADDTOFAV *
0x1800d51bf  mov     rcx, r14; hWnd
0x1800d51c2  call    ?ConfirmAddToFavorites@@YAHPEAUHWND__@@PEBU_ADDTOFAV@@@Z; ConfirmAddToFavorites(HWND__ *,_ADDTOFAV const *)
0x1800d51c7  test    eax, eax
0x1800d51c9  jnz     short loc_1800D51CF
0x1800d51cb  mov     ebx, esi
0x1800d51cd  jmp     short loc_1800D520E
0x1800d51cf  mov     rcx, r14
0x1800d51d2  call    FreeComboStrings
0x1800d51d7  mov     rdx, rdi; nResult
0x1800d51da  mov     rcx, r14; hDlg
0x1800d51dd  call    cs:__imp_EndDialog
0x1800d51e3  jmp     short loc_1800D5225
0x1800d51e5  mov     rcx, cs:g_hinstMUI; HINSTANCE
0x1800d51ec  mov     r9d, 2F5h; unsigned __int16 *
0x1800d51f2  mov     rdx, r14; hWnd
0x1800d51f5  mov     dword ptr [rsp+4C0h+pdwType], 10h; unsigned int
0x1800d51fd  lea     r8d, [r9+35h]; unsigned __int16 *
0x1800d5201  call    ?IEMessageBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@PEBG2IZZ; IEMessageBox(HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,uint,...)
0x1800d5206  mov     ebx, esi
0x1800d5208  cmp     [rsp+4C0h+ppidl], esi
0x1800d520c  jz      short loc_1800D5225
0x1800d520e  mov     edx, [r15+8]; unsigned __int64
0x1800d5212  lea     r8, [rbp+3C0h+var_250]; unsigned __int16 *
0x1800d5219  mov     rcx, [r15]; unsigned __int16 *
0x1800d521c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d5221  jmp     short loc_1800D5225
0x1800d5223  mov     ebx, esi
0x1800d5225  movsxd  rax, ebx
0x1800d5228  jmp     loc_1800D541B
0x1800d522d  mov     r8, rbx; hData
0x1800d5230  mov     rdx, r13; lpString
0x1800d5233  mov     rcx, r14; hWnd
0x1800d5236  call    cs:__imp_SetPropW
0x1800d523c  mov     edi, 1
0x1800d5241  lea     rdx, [rsp+4C0h+pszSpec]; pszPath
0x1800d5246  mov     r9d, edi; fCreate
0x1800d5249  xor     ecx, ecx; hwnd
0x1800d524b  mov     r15d, 103h
0x1800d5251  lea     r8d, [rdi+5]; csidl
0x1800d5255  call    cs:__imp_SHGetSpecialFolderPathW
0x1800d525b  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800d525f  xor     esi, esi
0x1800d5261  test    eax, eax
0x1800d5263  jz      short loc_1800D527F
0x1800d5265  lea     rcx, [rsp+4C0h+pszSpec]
0x1800d526a  mov     rax, r12
0x1800d526d  inc     rax
0x1800d5270  cmp     [rcx+rax*2], si
0x1800d5274  jnz     short loc_1800D526D
0x1800d5276  mov     r15d, 0FDh
0x1800d527c  sub     r15, rax
0x1800d527f  mov     r13d, 3EDh
0x1800d5285  mov     rcx, r14; hDlg
  ... truncated ...
```
