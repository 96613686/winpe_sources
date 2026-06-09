# AddFavoritesWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800dd370`
- end: `0x1800ddaae`
- name: `?AddFavoritesWndProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1854`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800144d0`
- `0x1800b2930`
- `0x1800dd370`
- `0x1800ddab4`
- `0x1800de1b4`
- `0x1800de248`
- `0x1800de5cc`
- `0x1800de674`
- `0x1800de854`
- `0x1800df35c`
- `0x1800df8d0`
- `0x18042c4c8`
- `0x180438518`
- `0x180438bdc`
- `0x18047da7c`
- `0x1805251e4`
- `0x180528158`
- `0x180566458`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x1800dd4cc`
- `KERNEL32!CreateDirectoryW` at `0x1800dd4cc`
- `KERNEL32!GetLastError` at `0x1800dd57e`
- `KERNEL32!GetLastError` at `0x1800dd57e`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1800dd96a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1800dd96a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBlanksW` at `0x1800dd661`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveBlanksW` at `0x1800dd661`
- `USER32!GetPropW` at `0x1800dd3b5`
- `USER32!GetPropW` at `0x1800dd3b5`
- `USER32!SetDlgItemTextW` at `0x1800dd8e1`
- `USER32!SetDlgItemTextW` at `0x1800dd8e1`
- `USER32!SetFocus` at `0x1800dd9b9`
- `USER32!SetFocus` at `0x1800dd9b9`
- `USER32!GetDlgItemTextW` at `0x1800dd651`
- `USER32!GetDlgItemTextW` at `0x1800dd651`
- `USER32!SetPropW` at `0x1800dd850`
- `USER32!SetPropW` at `0x1800dd850`
- `USER32!RemovePropW` at `0x1800dda75`
- `USER32!RemovePropW` at `0x1800dda75`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800dd473`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800dd4ad`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800dd473`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800dd4ad`
- `USER32!SendMessageW` at `0x1800dd45d`
- `USER32!SendMessageW` at `0x1800dd535`
- `USER32!SendMessageW` at `0x1800dd8cb`
- `USER32!SendMessageW` at `0x1800dd9e5`
- `USER32!SendMessageW` at `0x1800dd45d`
- `USER32!SendMessageW` at `0x1800dd535`
- `USER32!SendMessageW` at `0x1800dd8cb`
- `USER32!SendMessageW` at `0x1800dd9e5`
- `USER32!IsWindowVisible` at `0x1800dd68c`
- `USER32!IsWindowVisible` at `0x1800dd68c`
- `USER32!EnableWindow` at `0x1800dd915`
- `USER32!EnableWindow` at `0x1800dd915`
- `USER32!EndDialog` at `0x1800dd5fe`
- `USER32!EndDialog` at `0x1800dd7f1`
- `USER32!EndDialog` at `0x1800dd5fe`
- `USER32!EndDialog` at `0x1800dd7f1`
- `USER32!GetDlgItem` at `0x1800dd443`
- `USER32!GetDlgItem` at `0x1800dd507`
- `USER32!GetDlgItem` at `0x1800dd5af`
- `USER32!GetDlgItem` at `0x1800dd675`
- `USER32!GetDlgItem` at `0x1800dd8b1`
- `USER32!GetDlgItem` at `0x1800dd8ff`
- `USER32!GetDlgItem` at `0x1800dd9aa`
- `USER32!GetDlgItem` at `0x1800dd9cb`
- `USER32!GetDlgItem` at `0x1800dd443`
- `USER32!GetDlgItem` at `0x1800dd507`
- `USER32!GetDlgItem` at `0x1800dd5af`
- `USER32!GetDlgItem` at `0x1800dd675`
- `USER32!GetDlgItem` at `0x1800dd8b1`
- `USER32!GetDlgItem` at `0x1800dd8ff`
- `USER32!GetDlgItem` at `0x1800dd9aa`
- `USER32!GetDlgItem` at `0x1800dd9cb`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1800dd875`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1800dd875`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800dd756`
- `SHELL32!__imp_PathCleanupSpec` at `0x1800dd756`

## string_xrefs

- `0x1800dd4f3`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x1800dd71b`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x1800dd949`: `Software\Microsoft\Internet Explorer\LowRegistry`

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
0x1800dd370  mov     [rsp-8+arg_8], rbx
0x1800dd375  push    rbp
0x1800dd376  push    rsi
0x1800dd377  push    rdi
0x1800dd378  push    r12
0x1800dd37a  push    r13
0x1800dd37c  push    r14
0x1800dd37e  push    r15
0x1800dd380  lea     rbp, [rsp-390h]
0x1800dd388  sub     rsp, 490h
0x1800dd38f  mov     rax, cs:__security_cookie
0x1800dd396  xor     rax, rsp
0x1800dd399  mov     [rbp+3C0h+var_40], rax
0x1800dd3a0  mov     edi, edx
0x1800dd3a2  lea     r13, aShdocAtfprop; "SHDOC_ATFPROP"
0x1800dd3a9  mov     rdx, r13; lpString
0x1800dd3ac  mov     rbx, r9
0x1800dd3af  mov     rsi, r8
0x1800dd3b2  mov     r14, rcx
0x1800dd3b5  call    cs:__imp_GetPropW
0x1800dd3bc  nop     dword ptr [rax+rax+00h]
0x1800dd3c1  mov     r12d, 2
0x1800dd3c7  mov     r15, rax
0x1800dd3ca  sub     edi, r12d
0x1800dd3cd  jz      loc_1800DDA64
0x1800dd3d3  sub     edi, 4Ch ; 'L'
0x1800dd3d6  jz      loc_1800DD9F6
0x1800dd3dc  sub     edi, 0C2h
0x1800dd3e2  jz      loc_1800DD847
0x1800dd3e8  cmp     edi, 1
0x1800dd3eb  jnz     loc_1800DDA81
0x1800dd3f1  movzx   ecx, si
0x1800dd3f4  sub     ecx, edi
0x1800dd3f6  jz      loc_1800DD614
0x1800dd3fc  sub     ecx, edi
0x1800dd3fe  jz      loc_1800DD5F0
0x1800dd404  sub     ecx, 3EBh
0x1800dd40a  jz      loc_1800DD5CE
0x1800dd410  cmp     ecx, r12d
0x1800dd413  jnz     loc_1800DDA81
0x1800dd419  xor     esi, esi
0x1800dd41b  test    rax, rax
0x1800dd41e  jz      loc_1800DDA81
0x1800dd424  xor     edx, edx; Val
0x1800dd426  lea     rcx, [rsp+4C0h+PathName]; void *
0x1800dd42b  mov     r8d, 218h; Size
0x1800dd431  call    memset_0
0x1800dd436  mov     edx, 407h; nIDDlgItem
0x1800dd43b  mov     qword ptr [rsp+4C0h+pszSpec], r15
0x1800dd440  mov     rcx, r14; hDlg
0x1800dd443  call    cs:__imp_GetDlgItem
0x1800dd44a  nop     dword ptr [rax+rax+00h]
0x1800dd44f  xor     r9d, r9d; lParam
0x1800dd452  xor     r8d, r8d; wParam
0x1800dd455  mov     rcx, rax; hWnd
0x1800dd458  mov     edx, 147h; Msg
0x1800dd45d  call    cs:__imp_SendMessageW
0x1800dd464  nop     dword ptr [rax+rax+00h]
0x1800dd469  lea     rcx, [rsi-2]
0x1800dd46d  mov     [rbp+3C0h+var_258], eax
0x1800dd473  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800dd47a  nop     dword ptr [rax+rax+00h]
0x1800dd47f  mov     rcx, cs:g_hinstMUI; hInstance
0x1800dd486  lea     r9, ?NewFavoritesFolderDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800dd48d  mov     rdi, rax
0x1800dd490  mov     r8, r14; hWndParent
0x1800dd493  lea     rax, [rsp+4C0h+pszSpec]
0x1800dd498  mov     edx, 1180h; lpTemplateName
0x1800dd49d  mov     [rsp+4C0h+pdwType], rax; LPARAM
0x1800dd4a2  call    SHFusionDialogBoxParam
0x1800dd4a7  mov     rcx, rdi
0x1800dd4aa  mov     rbx, rax
0x1800dd4ad  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800dd4b4  nop     dword ptr [rax+rax+00h]
0x1800dd4b9  lea     edi, [rsi+1]
0x1800dd4bc  cmp     rbx, rdi
0x1800dd4bf  jnz     loc_1800DDA81
0x1800dd4c5  xor     edx, edx; lpSecurityAttributes
0x1800dd4c7  lea     rcx, [rsp+4C0h+PathName]; lpPathName
0x1800dd4cc  call    cs:__imp_CreateDirectoryW
0x1800dd4d3  nop     dword ptr [rax+rax+00h]
0x1800dd4d8  test    eax, eax
0x1800dd4da  jz      loc_1800DD57E
0x1800dd4e0  lea     r9, [rsp+4C0h+PathName]; unsigned __int16 *
0x1800dd4e5  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800dd4ec  lea     r8, pszValue; "AddToFavoritesInitialSelection"
0x1800dd4f3  lea     rdx, pszSubKey; "Software\\Microsoft\\Internet Explorer"...
0x1800dd4fa  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800dd4ff  mov     edx, 407h; nIDDlgItem
0x1800dd504  mov     rcx, r14; hDlg
0x1800dd507  call    cs:__imp_GetDlgItem
0x1800dd50e  nop     dword ptr [rax+rax+00h]
0x1800dd513  mov     rbx, rax
0x1800dd516  test    rax, rax
0x1800dd519  jz      loc_1800DD5AA
0x1800dd51f  mov     rcx, r14
0x1800dd522  call    FreeComboStrings
0x1800dd527  xor     r9d, r9d; lParam
0x1800dd52a  xor     r8d, r8d; wParam
0x1800dd52d  mov     edx, 14Bh; Msg
0x1800dd532  mov     rcx, rbx; hWnd
0x1800dd535  call    cs:__imp_SendMessageW
0x1800dd53c  nop     dword ptr [rax+rax+00h]
0x1800dd541  mov     r8, [r15]; unsigned __int16 *
0x1800dd544  lea     rax, [rsp+4C0h+ppidl]
0x1800dd549  mov     [rsp+4C0h+var_488], rsi; struct IShellFolder *
0x1800dd54e  lea     r9, [rsp+4C0h+PathName]; unsigned __int16 *
0x1800dd553  mov     [rsp+4C0h+pcbData], rsi; struct _ITEMIDLIST_ABSOLUTE *
0x1800dd558  mov     rdx, r15; struct _ADDTOFAV *
0x1800dd55b  mov     [rsp+4C0h+pvData], rax; ppidl
0x1800dd560  mov     rcx, rbx; HWND
0x1800dd563  mov     dword ptr [rsp+4C0h+pdwType], esi; int
0x1800dd567  mov     [rsp+4C0h+ppidl], esi
0x1800dd56b  call    ?AddFoldersToCB@@YAXPEAUHWND__@@PEAU_ADDTOFAV@@PEBG2HPEAHPEBU_ITEMIDLIST_ABSOLUTE@@PEAUIShellFolder@@@Z; AddFoldersToCB(HWND__ *,_ADDTOFAV *,ushort const *,ushort const *,int,int *,_ITEMIDLIST_ABSOLUTE const *,IShellFolder *)
0x1800dd570  mov     edx, [rsp+4C0h+ppidl]; int
0x1800dd574  mov     rcx, rbx; hWnd
0x1800dd577  call    ?AdjustCBDropWidth@@YAXPEAUHWND__@@H@Z; AdjustCBDropWidth(HWND__ *,int)
0x1800dd57c  jmp     short loc_1800DD5AA
0x1800dd57e  call    cs:__imp_GetLastError
0x1800dd585  nop     dword ptr [rax+rax+00h]
0x1800dd58a  mov     rcx, cs:g_hinstMUI; hAppInst
0x1800dd591  mov     r9d, 2F5h; unsigned int
0x1800dd597  mov     r8d, eax; unsigned int
0x1800dd59a  mov     dword ptr [rsp+4C0h+pdwType], 40h ; '@'; unsigned int
0x1800dd5a2  mov     rdx, r14; hWnd
0x1800dd5a5  call    ?ShowFormattedSystemErrorDialog@@YAXPEAUHINSTANCE__@@PEAUHWND__@@KII@Z; ShowFormattedSystemErrorDialog(HINSTANCE__ *,HWND__ *,ulong,uint,uint)
0x1800dd5aa  mov     edx, edi; nIDDlgItem
0x1800dd5ac  mov     rcx, r14; hDlg
0x1800dd5af  call    cs:__imp_GetDlgItem
0x1800dd5b6  nop     dword ptr [rax+rax+00h]
0x1800dd5bb  mov     r9, rdi
0x1800dd5be  mov     edx, 28h ; '('
0x1800dd5c3  mov     r8, rax
0x1800dd5c6  mov     rcx, r14
0x1800dd5c9  jmp     loc_1800DD9E5
0x1800dd5ce  shr     rsi, 10h
0x1800dd5d2  mov     eax, 400h
0x1800dd5d7  cmp     si, ax
0x1800dd5da  jnz     loc_1800DDA81
0x1800dd5e0  lea     edx, [rax-13h]
0x1800dd5e3  mov     rcx, r14; hWnd
0x1800dd5e6  call    EnableOKButtonFromID
0x1800dd5eb  jmp     loc_1800DDA81
0x1800dd5f0  mov     rcx, r14
0x1800dd5f3  call    FreeComboStrings
0x1800dd5f8  mov     rdx, r12; nResult
0x1800dd5fb  mov     rcx, r14; hDlg
0x1800dd5fe  call    cs:__imp_EndDialog
0x1800dd605  nop     dword ptr [rax+rax+00h]
0x1800dd60a  mov     eax, 1
0x1800dd60f  jmp     loc_1800DDA83
0x1800dd614  mov     edi, 1
0x1800dd619  lea     rcx, [rbp+3C0h+var_24E]; void *
0x1800dd620  xor     esi, esi
0x1800dd622  xor     edx, edx; Val
0x1800dd624  mov     r8d, 206h; Size
0x1800dd62a  mov     [rbp+3C0h+var_250], si
0x1800dd631  mov     ebx, edi
0x1800dd633  call    memset_0
0x1800dd638  test    r15, r15
0x1800dd63b  jz      loc_1800DD83F
0x1800dd641  mov     r9d, [r15+18h]; cchMax
0x1800dd645  mov     edx, 3EDh; nIDDlgItem
0x1800dd64a  mov     r8, [r15+10h]; lpString
0x1800dd64e  mov     rcx, r14; hDlg
0x1800dd651  call    cs:__imp_GetDlgItemTextW
0x1800dd658  nop     dword ptr [rax+rax+00h]
0x1800dd65d  mov     rcx, [r15+10h]; pszPath
0x1800dd661  call    cs:__imp_PathRemoveBlanksW
0x1800dd668  nop     dword ptr [rax+rax+00h]
0x1800dd66d  mov     edx, 407h; nIDDlgItem
0x1800dd672  mov     rcx, r14; hDlg
0x1800dd675  call    cs:__imp_GetDlgItem
0x1800dd67c  nop     dword ptr [rax+rax+00h]
0x1800dd681  mov     r12, rax
0x1800dd684  test    rax, rax
0x1800dd687  jz      short loc_1800DD69C
0x1800dd689  mov     rcx, rax; hWnd
0x1800dd68c  call    cs:__imp_IsWindowVisible
0x1800dd693  nop     dword ptr [rax+rax+00h]
0x1800dd698  test    eax, eax
0x1800dd69a  jnz     short loc_1800DD69E
0x1800dd69c  mov     ebx, esi
0x1800dd69e  mov     r8, [r15]; unsigned __int16 *
0x1800dd6a1  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x1800dd6a8  mov     edx, 104h; unsigned __int64
0x1800dd6ad  mov     [rsp+4C0h+var_47C], ebx
0x1800dd6b1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800dd6b6  test    eax, eax
0x1800dd6b8  js      loc_1800DD83D
0x1800dd6be  test    ebx, ebx
0x1800dd6c0  jz      short loc_1800DD6D6
0x1800dd6c2  mov     r8d, [r15+8]; int
0x1800dd6c6  mov     rcx, r12; hWnd
0x1800dd6c9  mov     rdx, [r15]; unsigned __int16 *
0x1800dd6cc  call    ?GetFavoritePathFromCB@@YAHPEAUHWND__@@PEAGH@Z; GetFavoritePathFromCB(HWND__ *,ushort *,int)
0x1800dd6d1  mov     r13d, eax
0x1800dd6d4  jmp     short loc_1800DD6D9
0x1800dd6d6  mov     r13d, edi
0x1800dd6d9  mov     ebx, r13d
0x1800dd6dc  test    r13d, r13d
0x1800dd6df  jz      loc_1800DD828
0x1800dd6e5  mov     rcx, [r15+10h]
0x1800dd6e9  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800dd6ed  mov     rax, r12
0x1800dd6f0  inc     rax
0x1800dd6f3  cmp     [rcx+rax*2], si
0x1800dd6f7  jnz     short loc_1800DD6F0
0x1800dd6f9  mov     ebx, 104h
0x1800dd6fe  mov     [rsp+4C0h+ppidl], edi
0x1800dd702  cmp     rax, rbx
0x1800dd705  jnb     loc_1800DD7FF
0x1800dd70b  cmp     [rsp+4C0h+var_47C], esi
0x1800dd70f  jz      short loc_1800DD72E
0x1800dd711  mov     r9, [r15]; unsigned __int16 *
0x1800dd714  lea     r8, pszValue; "AddToFavoritesInitialSelection"
0x1800dd71b  lea     rdx, pszSubKey; "Software\\Microsoft\\Internet Explorer"...
0x1800dd722  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800dd729  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800dd72e  mov     r8, [r15+10h]; unsigned __int16 *
0x1800dd732  lea     rcx, [rsp+4C0h+pszSpec]; unsigned __int16 *
0x1800dd737  mov     rdx, rbx; unsigned __int64
0x1800dd73a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800dd73f  test    eax, eax
0x1800dd741  mov     ebx, esi
0x1800dd743  cmovns  ebx, r13d
0x1800dd747  test    ebx, ebx
0x1800dd749  jz      loc_1800DD7DF
0x1800dd74f  lea     rdx, [rsp+4C0h+pszSpec]; pszSpec
0x1800dd754  xor     ecx, ecx; pszDir
0x1800dd756  call    cs:__imp_PathCleanupSpec
0x1800dd75d  nop     dword ptr [rax+rax+00h]
0x1800dd762  test    eax, eax
0x1800dd764  jz      short loc_1800DD789
0x1800dd766  mov     rcx, cs:g_hinstMUI; HINSTANCE
0x1800dd76d  mov     r9d, 2F5h; unsigned __int16 *
0x1800dd773  mov     rdx, r14; hWnd
0x1800dd776  mov     dword ptr [rsp+4C0h+pdwType], 10h; unsigned int
0x1800dd77e  lea     r8d, [r9+26h]; unsigned __int16 *
0x1800dd782  call    ?IEMessageBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@PEBG2IZZ; IEMessageBox(HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,uint,...)
0x1800dd787  jmp     short loc_1800DD7DF
0x1800dd789  mov     rcx, r15; struct _ADDTOFAV *
0x1800dd78c  mov     [rsp+4C0h+ppidl], edi
0x1800dd790  call    ?QualifyFileName@@YAHPEAU_ADDTOFAV@@@Z; QualifyFileName(_ADDTOFAV *)
0x1800dd795  test    eax, eax
0x1800dd797  jz      short loc_1800DD7FF
0x1800dd799  mov     rcx, [r15]
0x1800dd79c  mov     rax, r12
0x1800dd79f  inc     rax
0x1800dd7a2  cmp     [rcx+rax*2], si
0x1800dd7a6  jnz     short loc_1800DD79F
0x1800dd7a8  mov     rcx, [r15+10h]
0x1800dd7ac  inc     r12
0x1800dd7af  cmp     [rcx+r12*2], si
0x1800dd7b4  jnz     short loc_1800DD7AC
0x1800dd7b6  add     rax, 2
0x1800dd7ba  mov     [rsp+4C0h+ppidl], edi
0x1800dd7be  add     rax, r12
0x1800dd7c1  cmp     rax, 104h
0x1800dd7c7  jnb     short loc_1800DD7FF
0x1800dd7c9  cmp     dword ptr [r15+28h], 2
0x1800dd7ce  jz      short loc_1800DD7E3
0x1800dd7d0  mov     rdx, r15; struct _ADDTOFAV *
0x1800dd7d3  mov     rcx, r14; hWnd
0x1800dd7d6  call    ?ConfirmAddToFavorites@@YAHPEAUHWND__@@PEBU_ADDTOFAV@@@Z; ConfirmAddToFavorites(HWND__ *,_ADDTOFAV const *)
0x1800dd7db  test    eax, eax
0x1800dd7dd  jnz     short loc_1800DD7E3
0x1800dd7df  mov     ebx, esi
0x1800dd7e1  jmp     short loc_1800DD828
0x1800dd7e3  mov     rcx, r14
0x1800dd7e6  call    FreeComboStrings
0x1800dd7eb  mov     rdx, rdi; nResult
0x1800dd7ee  mov     rcx, r14; hDlg
0x1800dd7f1  call    cs:__imp_EndDialog
0x1800dd7f8  nop     dword ptr [rax+rax+00h]
0x1800dd7fd  jmp     short loc_1800DD83F
0x1800dd7ff  mov     rcx, cs:g_hinstMUI; HINSTANCE
0x1800dd806  mov     r9d, 2F5h; unsigned __int16 *
0x1800dd80c  mov     rdx, r14; hWnd
0x1800dd80f  mov     dword ptr [rsp+4C0h+pdwType], 10h; unsigned int
0x1800dd817  lea     r8d, [r9+35h]; unsigned __int16 *
0x1800dd81b  call    ?IEMessageBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@PEBG2IZZ; IEMessageBox(HINSTANCE__ *,HWND__ *,ushort const *,ushort const *,uint,...)
0x1800dd820  mov     ebx, esi
0x1800dd822  cmp     [rsp+4C0h+ppidl], esi
0x1800dd826  jz      short loc_1800DD83F
0x1800dd828  mov     edx, [r15+8]; unsigned __int64
0x1800dd82c  lea     r8, [rbp+3C0h+var_250]; unsigned __int16 *
0x1800dd833  mov     rcx, [r15]; unsigned __int16 *
0x1800dd836  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800dd83b  jmp     short loc_1800DD83F
0x1800dd83d  mov     ebx, esi
0x1800dd83f  movsxd  rax, ebx
0x1800dd842  jmp     loc_1800DDA83
0x1800dd847  mov     r8, rbx; hData
0x1800dd84a  mov     rdx, r13; lpString
0x1800dd84d  mov     rcx, r14; hWnd
0x1800dd850  call    cs:__imp_SetPropW
0x1800dd857  nop     dword ptr [rax+rax+00h]
0x1800dd85c  mov     edi, 1
0x1800dd861  lea     rdx, [rsp+4C0h+pszSpec]; pszPath
  ... truncated ...
```
