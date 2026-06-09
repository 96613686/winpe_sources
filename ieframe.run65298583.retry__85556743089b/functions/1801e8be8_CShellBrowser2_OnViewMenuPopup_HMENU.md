# CShellBrowser2::_OnViewMenuPopup(HMENU__ *)

- ea: `0x1801e8be8`
- end: `0x1801e9308`
- name: `?_OnViewMenuPopup@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z`
- size: `1824`
- prototype: `void __fastcall(CShellBrowser2 *__hidden this, HMENU)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801eda80`

## callees

- `0x18000b9e0`
- `0x180012140`
- `0x180015150`
- `0x1800231c4`
- `0x18003abb0`
- `0x18004a080`
- `0x18006f940`
- `0x180075598`
- `0x1800a40b8`
- `0x1800c16a4`
- `0x1800c16bc`
- `0x1800c2f9c`
- `0x1800c87e8`
- `0x1800c9f70`
- `0x1801d72cc`
- `0x1801e3fcc`
- `0x1801e8be8`
- `0x1801edec8`
- `0x18029b5b4`
- `0x1804026f8`
- `0x18053c4cc`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegGetUSValueW` at `0x1801e8f51`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegGetUSValueW` at `0x1801e8f51`
- `USER32!SetMenuItemInfoW` at `0x1801e8dcc`
- `USER32!SetMenuItemInfoW` at `0x1801e8dcc`
- `USER32!DeleteMenu` at `0x1801e8df8`
- `USER32!DeleteMenu` at `0x1801e8e28`
- `USER32!DeleteMenu` at `0x1801e8e85`
- `USER32!DeleteMenu` at `0x1801e9215`
- `USER32!DeleteMenu` at `0x1801e8df8`
- `USER32!DeleteMenu` at `0x1801e8e28`
- `USER32!DeleteMenu` at `0x1801e8e85`
- `USER32!DeleteMenu` at `0x1801e9215`
- `USER32!CheckMenuItem` at `0x1801e9130`
- `USER32!CheckMenuItem` at `0x1801e9157`
- `USER32!CheckMenuItem` at `0x1801e9287`
- `USER32!CheckMenuItem` at `0x1801e9130`
- `USER32!CheckMenuItem` at `0x1801e9157`
- `USER32!CheckMenuItem` at `0x1801e9287`
- `USER32!EnableMenuItem` at `0x1801e8c85`
- `USER32!EnableMenuItem` at `0x1801e8ca9`
- `USER32!EnableMenuItem` at `0x1801e8cd1`
- `USER32!EnableMenuItem` at `0x1801e8d01`
- `USER32!EnableMenuItem` at `0x1801e8d10`
- `USER32!EnableMenuItem` at `0x1801e8d21`
- `USER32!EnableMenuItem` at `0x1801e8d32`
- `USER32!EnableMenuItem` at `0x1801e8d43`
- `USER32!EnableMenuItem` at `0x1801e8d54`
- `USER32!EnableMenuItem` at `0x1801e8e74`
- `USER32!EnableMenuItem` at `0x1801e8ea9`
- `USER32!EnableMenuItem` at `0x1801e8ee3`
- `USER32!EnableMenuItem` at `0x1801e8ef4`
- `USER32!EnableMenuItem` at `0x1801e91a9`
- `USER32!EnableMenuItem` at `0x1801e8c85`
- `USER32!EnableMenuItem` at `0x1801e8ca9`
- `USER32!EnableMenuItem` at `0x1801e8cd1`
- `USER32!EnableMenuItem` at `0x1801e8d01`
- `USER32!EnableMenuItem` at `0x1801e8d10`
- `USER32!EnableMenuItem` at `0x1801e8d21`
- `USER32!EnableMenuItem` at `0x1801e8d32`
- `USER32!EnableMenuItem` at `0x1801e8d43`
- `USER32!EnableMenuItem` at `0x1801e8d54`
- `USER32!EnableMenuItem` at `0x1801e8e74`
- `USER32!EnableMenuItem` at `0x1801e8ea9`
- `USER32!EnableMenuItem` at `0x1801e8ee3`
- `USER32!EnableMenuItem` at `0x1801e8ef4`
- `USER32!EnableMenuItem` at `0x1801e91a9`
- `USER32!RemoveMenu` at `0x1801e8f69`
- `USER32!RemoveMenu` at `0x1801e929a`
- `USER32!RemoveMenu` at `0x1801e8f69`
- `USER32!RemoveMenu` at `0x1801e929a`
- `OLEAUT32!__imp_SysFreeString` at `0x1801e92b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801e92b9`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801e8e13`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801e8e13`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x1801e8e94`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x1801e9196`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x1801e8e94`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x1801e9196`

## pseudocode

```c
void __fastcall CShellBrowser2::_OnViewMenuPopup(CShellBrowser2 *this, HMENU a2)
{
  CLayerParticipant *v4; // rdi
  int v5; // r12d
  __int64 v6; // rcx
  HMENU v7; // rdi
  HMENU v8; // rcx
  struct IUnknown *v9; // rsi
  __int64 v10; // rcx
  int UrlSchemeW; // eax
  __int64 v12; // r8
  bool v13; // si
  unsigned int v14; // r13d
  int v15; // r15d
  unsigned int v16; // eax
  const ITEMIDLIST *v17; // rcx
  __int64 v18; // rcx
  UINT v19; // r8d
  bool v20[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-BCh] BYREF
  int pvData; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  struct IBrowserFrame *v24; // [rsp+58h] [rbp-A8h] BYREF
  int pvDefaultData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-9Ch] BYREF
  int (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  __int64 v28; // [rsp+70h] [rbp-90h] BYREF
  __int128 v29; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h]
  __int64 v31; // [rsp+90h] [rbp-70h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h]
  int v33; // [rsp+A0h] [rbp-60h] BYREF
  int v34; // [rsp+A4h] [rbp-5Ch]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  MENUITEMINFOW mii; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v37[4176]; // [rsp+100h] [rbp+0h] BYREF

  v31 = 23;
  v32 = 13;
  v4 = (CShellBrowser2 *)((char *)this + 232);
  v5 = 0;
  if ( (unsigned int)SHRestricted2W(1610612748, 0, 0)
    || (v20[0] = 0, CLayerParticipant::LayerGetBool(v4, v20, 69722, 0), v20[0]) )
  {
    EnableMenuItem(a2, 0xC5Bu, 1u);
  }
  if ( (unsigned int)SHRestricted2W(1610612746, 0, 0) )
    EnableMenuItem(a2, 0xA21Bu, 1u);
  if ( (unsigned int)SHRestricted2W(1610612774, 0, 0) )
    EnableMenuItem(a2, 0xA219u, 1u);
  v20[0] = 0;
  CLayerParticipant::LayerGetBool(v4, v20, 69722, 0);
  if ( v20[0] )
  {
    EnableMenuItem(a2, 0xC5Bu, 1u);
    EnableMenuItem(a2, 0xA219u, 1u);
    EnableMenuItem(a2, 0xA207u, 1u);
    EnableMenuItem(a2, 0xA21Eu, 1u);
    EnableMenuItem(a2, 0xA204u, 1u);
    EnableMenuItem(a2, 0xD84u, 1u);
  }
  v6 = *((_QWORD *)this + 816);
  if ( v6 )
    IUnknown_QueryStatus(v6, (unsigned int)&CGID_PrivCITCommands, 2, (unsigned int)&v31, 0);
  v7 = (HMENU)SHLoadMenuPopup(g_hinstMUI, 264);
  memset_0(&mii, 0, sizeof(mii));
  v8 = (HMENU)*((_QWORD *)this + 796);
  mii.cbSize = 80;
  mii.fMask = 4;
  mii.hSubMenu = v7;
  SetMenuItemInfoW(v8, 0xA201u, 0, &mii);
  if ( (unsigned int)SHIsRestricted2W(*((HWND *)this + 43)) )
    DeleteMenu(v7, 0xA227u, 0);
  else
    SHCheckMenuItem(v7, 41511, ((HIDWORD(v32) >> 2) & 1) == 0);
  if ( LCIEIsCurrentProcessInPrivate() )
  {
    v21 = 1;
    GetBOOL((__int64 *)SettingStore::IEVALUE_PrivacIE_DisableToolbars[0], &v21);
    SHCheckMenuItem(v7, 42448, v21);
  }
  else
  {
    DeleteMenu(v7, 0xA5D0u, 0);
  }
  if ( (unsigned int)SHRestricted2W(2, 0, 0) )
  {
    EnableMenuItem(v7, 0xA227u, 1u);
    DeleteMenu(v7, 0xA20Cu, 0);
  }
  else
  {
    if ( (unsigned int)IsPolicyEnabledValue((__int64 *)SettingStore::IEVALUE_Browser_ToolBarsLocked[0]) )
      EnableMenuItem(v7, 0xA20Cu, 1u);
    SHCheckMenuItem(v7, 41484, HIDWORD(v31));
  }
  v9 = (struct IUnknown *)*((_QWORD *)this + 816);
  if ( (unsigned int)SHRestricted2W(2, 0, 0) )
  {
    EnableMenuItem(a2, 0xA20Au, 1u);
    EnableMenuItem(a2, 0xA205u, 1u);
  }
  PopulateItbarToolbarBands(a2, v9, 0xA208u);
  pvData = 0;
  pcbData = 4;
  pvDefaultData = 0;
  SHRegGetUSValueW(L"Software\\Microsoft\\Java VM", L"EnableJavaConsole", 0, &pvData, &pcbData, 0, &pvDefaultData, 4u);
  if ( !pvData )
    RemoveMenu(a2, 0xA21Cu, 0);
  v10 = *((_QWORD *)this + 46);
  v27 = 0;
  v28 = 0;
  bstrString = 0;
  if ( (*(int (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v10 + 144LL))(
         v10,
         &v27) >= 0
    && v27
    && (**v27)(v27, &GUID_332c4425_26cb_11d0_b483_00c04fd90119, &v28) >= 0
    && v28
    && (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v28 + 320LL))(v28, &bstrString) >= 0 )
  {
    UrlSchemeW = GetUrlSchemeW(bstrString);
    if ( UrlSchemeW == 2 || (v12 = 0, UrlSchemeW == 11) )
      v12 = 1;
    SHEnableMenuItem(a2, 41507, v12);
  }
  v20[0] = 0;
  v24 = 0;
  v13 = 0;
  if ( (int)CShellBrowser2::_GetBrowserFrame(this, &v24) < 0 )
    goto LABEL_41;
  v33 = 1;
  v34 = 0;
  v35 = 8;
  if ( (int)IUnknown_QueryStatus(
              (_DWORD)v24,
              (unsigned int)&GUID_d4d21454_070f_4033_88f6_1b8d7ba630a9,
              2,
              (unsigned int)&v33,
              0) >= 0 )
  {
    v13 = (v34 & 2) != 0;
    v20[0] = (v35 & 0x200000000LL) != 0;
  }
  *(_QWORD *)&v29 = 4;
  *((_QWORD *)&v29 + 1) = 5;
  if ( (int)IUnknown_QueryStatus((_DWORD)v24, (unsigned int)&CGID_BrowserFrame, 2, (unsigned int)&v29, 0) < 0 )
  {
LABEL_41:
    v15 = 0;
    v21 = 0;
    v14 = 0;
  }
  else
  {
    v14 = (DWORD1(v29) >> 1) & 1;
    v15 = (DWORD1(v29) >> 2) & 1;
    v21 = (HIDWORD(v29) >> 1) & 1;
    v5 = (HIDWORD(v29) >> 2) & 1;
  }
  SHEnableMenuItem(a2, 41509, v13);
  SHEnableMenuItem(a2, 41521, v20[0]);
  SHEnableMenuItem(v7, 41478, v14);
  CheckMenuItem(v7, 0xA206u, 8 * v15);
  SHEnableMenuItem(v7, 41481, v21);
  CheckMenuItem(v7, 0xA209u, 8 * v5);
  v16 = CShellBrowser2::v_ShowControl((DWORD_PTR)this, 1u, 3);
  SHCheckMenuItem(v7, 41474, v16 == 1);
  if ( (unsigned int)IsPolicyEnabledValue((__int64 *)SettingStore::IEVALUE_Browser_ShowStatusBar[0]) )
    EnableMenuItem(a2, 0xA202u, 1u);
  v17 = (const ITEMIDLIST *)*((_QWORD *)this + 51);
  if ( v17
    && (int)SHGetNameAndFlags(v17, 0) >= 0
    && (unsigned int)GetUrlSchemeW(v37) == 1
    && !SHRegGetBoolValueFromHKCUHKLM(L"Software\\Microsoft\\Ftp", L"Use Web Based FTP", 0) )
  {
    AssureOpenFtpInExplorerMenuItem(a2);
  }
  else
  {
    DeleteMenu(a2, 0xA1CDu, 0);
  }
  if ( (unsigned int)IsPanToolSupported() )
  {
    v18 = *((_QWORD *)this + 50);
    if ( v18 )
    {
      v30 = 0;
      v29 = 0;
      LOWORD(v29) = 11;
      if ( (int)IUnknown_Exec(v18, (unsigned int)&CGID_Explorer, 67, 0, 0, (__int64)&v29) >= 0 )
      {
        v19 = 0;
        if ( WORD4(v29) == 0xFFFF )
          v19 = 8;
        CheckMenuItem(a2, 0x17Cu, v19);
      }
    }
  }
  else
  {
    RemoveMenu(a2, 0x17Cu, 0);
  }
  ATL::CComPtr<IPrivacIEDatabase>::Release(&v27);
  ATL::CComPtr<IPrivacIEDatabase>::Release(&v28);
  SysFreeString(bstrString);
  bstrString = 0;
  SHPrettyMenu(a2);
  SHPrettyMenu(v7);
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v24);
}

```

## disassembly

```asm
0x1801e8be8  mov     [rsp-8+arg_10], rbx
0x1801e8bed  push    rbp
0x1801e8bee  push    rsi
0x1801e8bef  push    rdi
0x1801e8bf0  push    r12
0x1801e8bf2  push    r13
0x1801e8bf4  push    r14
0x1801e8bf6  push    r15
0x1801e8bf8  lea     rbp, [rsp-1060h]
0x1801e8c00  mov     eax, 1160h
0x1801e8c05  call    _alloca_probe
0x1801e8c0a  sub     rsp, rax
0x1801e8c0d  mov     rax, cs:__security_cookie
0x1801e8c14  xor     rax, rsp
0x1801e8c17  mov     [rbp+1090h+var_40], rax
0x1801e8c1e  mov     rbx, rdx
0x1801e8c21  mov     [rbp+1090h+var_1100], 17h
0x1801e8c29  mov     r14, rcx
0x1801e8c2c  mov     [rbp+1090h+var_10F8], 0Dh
0x1801e8c34  lea     rdi, [rcx+0E8h]
0x1801e8c3b  xor     edx, edx
0x1801e8c3d  mov     ecx, 6000000Ch
0x1801e8c42  xor     r8d, r8d
0x1801e8c45  xor     r12d, r12d
0x1801e8c48  call    SHRestricted2W
0x1801e8c4d  lea     r15d, [r12+1]
0x1801e8c52  mov     esi, 1105Ah
0x1801e8c57  test    eax, eax
0x1801e8c59  jnz     short loc_1801E8C7A
0x1801e8c5b  xor     r9d, r9d; int
0x1801e8c5e  mov     [rsp+1190h+var_1150], r12b
0x1801e8c63  mov     r8d, esi; int
0x1801e8c66  lea     rdx, [rsp+1190h+var_1150]; bool *
0x1801e8c6b  mov     rcx, rdi; this
0x1801e8c6e  call    ?LayerGetBool@CLayerParticipant@@IEAAJPEA_NHH@Z; CLayerParticipant::LayerGetBool(bool *,int,int)
0x1801e8c73  cmp     [rsp+1190h+var_1150], r12b
0x1801e8c78  jz      short loc_1801E8C8B
0x1801e8c7a  mov     r8d, r15d; uEnable
0x1801e8c7d  mov     edx, 0C5Bh; uIDEnableItem
0x1801e8c82  mov     rcx, rbx; hMenu
0x1801e8c85  call    cs:__imp_EnableMenuItem
0x1801e8c8b  xor     r8d, r8d
0x1801e8c8e  xor     edx, edx
0x1801e8c90  mov     ecx, 6000000Ah
0x1801e8c95  call    SHRestricted2W
0x1801e8c9a  test    eax, eax
0x1801e8c9c  jz      short loc_1801E8CAF
0x1801e8c9e  mov     r8d, r15d; uEnable
0x1801e8ca1  mov     edx, 0A21Bh; uIDEnableItem
0x1801e8ca6  mov     rcx, rbx; hMenu
0x1801e8ca9  call    cs:__imp_EnableMenuItem
0x1801e8caf  xor     r8d, r8d
0x1801e8cb2  xor     edx, edx
0x1801e8cb4  mov     ecx, 60000026h
0x1801e8cb9  call    SHRestricted2W
0x1801e8cbe  mov     r13d, 0A219h
0x1801e8cc4  test    eax, eax
0x1801e8cc6  jz      short loc_1801E8CD7
0x1801e8cc8  mov     r8d, r15d; uEnable
0x1801e8ccb  mov     edx, r13d; uIDEnableItem
0x1801e8cce  mov     rcx, rbx; hMenu
0x1801e8cd1  call    cs:__imp_EnableMenuItem
0x1801e8cd7  xor     r9d, r9d; int
0x1801e8cda  mov     [rsp+1190h+var_1150], r12b
0x1801e8cdf  mov     r8d, esi; int
0x1801e8ce2  lea     rdx, [rsp+1190h+var_1150]; bool *
0x1801e8ce7  mov     rcx, rdi; this
0x1801e8cea  call    ?LayerGetBool@CLayerParticipant@@IEAAJPEA_NHH@Z; CLayerParticipant::LayerGetBool(bool *,int,int)
0x1801e8cef  cmp     [rsp+1190h+var_1150], r12b
0x1801e8cf4  jz      short loc_1801E8D5A
0x1801e8cf6  mov     r8d, r15d; uEnable
0x1801e8cf9  mov     edx, 0C5Bh; uIDEnableItem
0x1801e8cfe  mov     rcx, rbx; hMenu
0x1801e8d01  call    cs:__imp_EnableMenuItem
0x1801e8d07  mov     r8d, r15d; uEnable
0x1801e8d0a  mov     edx, r13d; uIDEnableItem
0x1801e8d0d  mov     rcx, rbx; hMenu
0x1801e8d10  call    cs:__imp_EnableMenuItem
0x1801e8d16  mov     r8d, r15d; uEnable
0x1801e8d19  mov     edx, 0A207h; uIDEnableItem
0x1801e8d1e  mov     rcx, rbx; hMenu
0x1801e8d21  call    cs:__imp_EnableMenuItem
0x1801e8d27  mov     r8d, r15d; uEnable
0x1801e8d2a  mov     edx, 0A21Eh; uIDEnableItem
0x1801e8d2f  mov     rcx, rbx; hMenu
0x1801e8d32  call    cs:__imp_EnableMenuItem
0x1801e8d38  mov     r8d, r15d; uEnable
0x1801e8d3b  mov     edx, 0A204h; uIDEnableItem
0x1801e8d40  mov     rcx, rbx; hMenu
0x1801e8d43  call    cs:__imp_EnableMenuItem
0x1801e8d49  mov     r8d, r15d; uEnable
0x1801e8d4c  mov     edx, 0D84h; uIDEnableItem
0x1801e8d51  mov     rcx, rbx; hMenu
0x1801e8d54  call    cs:__imp_EnableMenuItem
0x1801e8d5a  mov     rcx, [r14+1980h]
0x1801e8d61  mov     r13d, 2
0x1801e8d67  test    rcx, rcx
0x1801e8d6a  jz      short loc_1801E8D84
0x1801e8d6c  lea     r9, [rbp+1090h+var_1100]
0x1801e8d70  mov     [rsp+1190h+pcbData], r12
0x1801e8d75  mov     r8d, r13d
0x1801e8d78  lea     rdx, CGID_PrivCITCommands
0x1801e8d7f  call    IUnknown_QueryStatus
0x1801e8d84  mov     rcx, cs:g_hinstMUI
0x1801e8d8b  mov     edx, 108h
0x1801e8d90  call    SHLoadMenuPopup
0x1801e8d95  mov     esi, 50h ; 'P'
0x1801e8d9a  lea     rcx, [rbp+1090h+mii]; void *
0x1801e8d9e  mov     r8d, esi; Size
0x1801e8da1  xor     edx, edx; Val
0x1801e8da3  mov     rdi, rax
0x1801e8da6  call    memset_0
0x1801e8dab  mov     rcx, [r14+18E0h]; hmenu
0x1801e8db2  lea     r9, [rbp+1090h+mii]; lpmii
0x1801e8db6  xor     r8d, r8d; fByPositon
0x1801e8db9  mov     [rbp+1090h+mii.cbSize], esi
0x1801e8dbc  mov     edx, 0A201h; item
0x1801e8dc1  mov     [rbp+1090h+mii.fMask], 4
0x1801e8dc8  mov     [rbp+1090h+mii.hSubMenu], rdi
0x1801e8dcc  call    cs:__imp_SetMenuItemInfoW
0x1801e8dd2  mov     rcx, [r14+158h]; hWnd
0x1801e8dd9  xor     r9d, r9d
0x1801e8ddc  xor     r8d, r8d
0x1801e8ddf  mov     edx, 6000000Eh
0x1801e8de4  call    SHIsRestricted2W
0x1801e8de9  mov     edx, 0A227h; uPosition
0x1801e8dee  mov     rcx, rdi; hMenu
0x1801e8df1  test    eax, eax
0x1801e8df3  jz      short loc_1801E8E00
0x1801e8df5  xor     r8d, r8d; uFlags
0x1801e8df8  call    cs:__imp_DeleteMenu
0x1801e8dfe  jmp     short loc_1801E8E13
0x1801e8e00  mov     r8d, dword ptr [rbp+1090h+var_10F8+4]
0x1801e8e04  shr     r8d, 2
0x1801e8e08  not     r8d
0x1801e8e0b  and     r8d, r15d
0x1801e8e0e  call    SHCheckMenuItem
0x1801e8e13  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1801e8e19  test    al, al
0x1801e8e1b  jnz     short loc_1801E8E30
0x1801e8e1d  xor     r8d, r8d; uFlags
0x1801e8e20  mov     edx, 0A5D0h; uPosition
0x1801e8e25  mov     rcx, rdi; hMenu
0x1801e8e28  call    cs:__imp_DeleteMenu
0x1801e8e2e  jmp     short loc_1801E8E58
0x1801e8e30  mov     rcx, cs:?IEVALUE_PrivacIE_DisableToolbars@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_PrivacIE_DisableToolbars
0x1801e8e37  lea     rdx, [rsp+1190h+var_114C]
0x1801e8e3c  mov     [rsp+1190h+var_114C], r15d
0x1801e8e41  call    GetBOOL
0x1801e8e46  mov     r8d, [rsp+1190h+var_114C]
0x1801e8e4b  mov     edx, 0A5D0h
0x1801e8e50  mov     rcx, rdi
0x1801e8e53  call    SHCheckMenuItem
0x1801e8e58  xor     r8d, r8d
0x1801e8e5b  xor     edx, edx
0x1801e8e5d  mov     ecx, r13d
0x1801e8e60  call    SHRestricted2W
0x1801e8e65  test    eax, eax
0x1801e8e67  jz      short loc_1801E8E8D
0x1801e8e69  mov     r8d, r15d; uEnable
0x1801e8e6c  mov     edx, 0A227h; uIDEnableItem
0x1801e8e71  mov     rcx, rdi; hMenu
0x1801e8e74  call    cs:__imp_EnableMenuItem
0x1801e8e7a  xor     r8d, r8d; uFlags
0x1801e8e7d  mov     edx, 0A20Ch; uPosition
0x1801e8e82  mov     rcx, rdi; hMenu
0x1801e8e85  call    cs:__imp_DeleteMenu
0x1801e8e8b  jmp     short loc_1801E8EC0
0x1801e8e8d  mov     rcx, cs:?IEVALUE_Browser_ToolBarsLocked@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Browser_ToolBarsLocked
0x1801e8e94  call    cs:__imp_IsPolicyEnabledValue
0x1801e8e9a  test    eax, eax
0x1801e8e9c  jz      short loc_1801E8EAF
0x1801e8e9e  mov     r8d, r15d; uEnable
0x1801e8ea1  mov     edx, 0A20Ch; uIDEnableItem
0x1801e8ea6  mov     rcx, rdi; hMenu
0x1801e8ea9  call    cs:__imp_EnableMenuItem
0x1801e8eaf  mov     r8d, dword ptr [rbp+1090h+var_1100+4]
0x1801e8eb3  mov     edx, 0A20Ch
0x1801e8eb8  mov     rcx, rdi
0x1801e8ebb  call    SHCheckMenuItem
0x1801e8ec0  mov     rsi, [r14+1980h]
0x1801e8ec7  xor     r8d, r8d
0x1801e8eca  xor     edx, edx
0x1801e8ecc  mov     ecx, r13d
0x1801e8ecf  call    SHRestricted2W
0x1801e8ed4  test    eax, eax
0x1801e8ed6  jz      short loc_1801E8EFA
0x1801e8ed8  mov     r8d, r15d; uEnable
0x1801e8edb  mov     edx, 0A20Ah; uIDEnableItem
0x1801e8ee0  mov     rcx, rbx; hMenu
0x1801e8ee3  call    cs:__imp_EnableMenuItem
0x1801e8ee9  mov     r8d, r15d; uEnable
0x1801e8eec  mov     edx, 0A205h; uIDEnableItem
0x1801e8ef1  mov     rcx, rbx; hMenu
0x1801e8ef4  call    cs:__imp_EnableMenuItem
0x1801e8efa  mov     r8d, 0A208h; unsigned int
0x1801e8f00  mov     rdx, rsi; struct IUnknown *
0x1801e8f03  mov     rcx, rbx; hMenu
0x1801e8f06  call    ?PopulateItbarToolbarBands@@YAXPEAUHMENU__@@PEAUIUnknown@@I@Z; PopulateItbarToolbarBands(HMENU__ *,IUnknown *,uint)
0x1801e8f0b  mov     eax, 4
0x1801e8f10  mov     [rsp+1190h+pvData], r12d
0x1801e8f15  mov     [rsp+1190h+dwDefaultDataSize], eax; dwDefaultDataSize
0x1801e8f19  lea     r9, [rsp+1190h+pvData]; pvData
0x1801e8f1e  mov     [rsp+1190h+var_112C], eax
0x1801e8f22  lea     rdx, aEnablejavacons; "EnableJavaConsole"
0x1801e8f29  lea     rax, [rsp+1190h+var_1130]
0x1801e8f2e  mov     [rsp+1190h+var_1130], r12d
0x1801e8f33  mov     [rsp+1190h+pvDefaultData], rax; pvDefaultData
0x1801e8f38  lea     rcx, aSoftwareMicros_24; "Software\\Microsoft\\Java VM"
0x1801e8f3f  lea     rax, [rsp+1190h+var_112C]
0x1801e8f44  mov     [rsp+1190h+fIgnoreHKCU], r12d; fIgnoreHKCU
0x1801e8f49  xor     r8d, r8d; pdwType
0x1801e8f4c  mov     [rsp+1190h+pcbData], rax; pcbData
0x1801e8f51  call    cs:__imp_SHRegGetUSValueW
0x1801e8f57  cmp     [rsp+1190h+pvData], r12d
0x1801e8f5c  jnz     short loc_1801E8F6F
0x1801e8f5e  xor     r8d, r8d; uFlags
0x1801e8f61  mov     edx, 0A21Ch; uPosition
0x1801e8f66  mov     rcx, rbx; hMenu
0x1801e8f69  call    cs:__imp_RemoveMenu
0x1801e8f6f  mov     rcx, [r14+170h]
0x1801e8f76  lea     rdx, [rsp+1190h+var_1128]
0x1801e8f7b  mov     [rsp+1190h+var_1128], r12
0x1801e8f80  mov     [rsp+1190h+var_1120], r12
0x1801e8f85  mov     [rsp+1190h+bstrString], r12
0x1801e8f8a  mov     rax, [rcx]
0x1801e8f8d  mov     rax, [rax+90h]
0x1801e8f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e8f99  test    eax, eax
0x1801e8f9b  js      short loc_1801E900B
0x1801e8f9d  mov     rcx, [rsp+1190h+var_1128]
0x1801e8fa2  test    rcx, rcx
0x1801e8fa5  jz      short loc_1801E900B
0x1801e8fa7  mov     rax, [rcx]
0x1801e8faa  lea     r8, [rsp+1190h+var_1120]
0x1801e8faf  lea     rdx, _GUID_332c4425_26cb_11d0_b483_00c04fd90119
0x1801e8fb6  mov     rax, [rax]
0x1801e8fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e8fbe  test    eax, eax
0x1801e8fc0  js      short loc_1801E900B
0x1801e8fc2  mov     rcx, [rsp+1190h+var_1120]
0x1801e8fc7  test    rcx, rcx
0x1801e8fca  jz      short loc_1801E900B
0x1801e8fcc  mov     rax, [rcx]
0x1801e8fcf  lea     rdx, [rsp+1190h+bstrString]
0x1801e8fd4  mov     rax, [rax+140h]
0x1801e8fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e8fe0  test    eax, eax
0x1801e8fe2  js      short loc_1801E900B
0x1801e8fe4  mov     rcx, [rsp+1190h+bstrString]
0x1801e8fe9  call    GetUrlSchemeW
0x1801e8fee  cmp     eax, r13d
0x1801e8ff1  jz      short loc_1801E8FFB
0x1801e8ff3  mov     r8d, r12d
0x1801e8ff6  cmp     eax, 0Bh
0x1801e8ff9  jnz     short loc_1801E8FFE
0x1801e8ffb  mov     r8d, r15d
0x1801e8ffe  mov     edx, 0A223h
0x1801e9003  mov     rcx, rbx
0x1801e9006  call    SHEnableMenuItem
0x1801e900b  lea     rdx, [rsp+1190h+var_1138]; struct IBrowserFrame **
0x1801e9010  mov     [rsp+1190h+var_1150], r12b
0x1801e9015  mov     rcx, r14; this
0x1801e9018  mov     [rsp+1190h+var_1138], r12
0x1801e901d  mov     sil, r12b
0x1801e9020  call    ?_GetBrowserFrame@CShellBrowser2@@AEAAJPEAPEAUIBrowserFrame@@@Z; CShellBrowser2::_GetBrowserFrame(IBrowserFrame * *)
0x1801e9025  test    eax, eax
0x1801e9027  js      loc_1801E90E2
0x1801e902d  mov     rcx, [rsp+1190h+var_1138]
0x1801e9032  lea     r9, [rbp+1090h+var_10F0]
0x1801e9036  xor     eax, eax
0x1801e9038  mov     [rbp+1090h+var_10F0], r15d
0x1801e903c  mov     [rbp+1090h+var_10EC], rax
0x1801e9040  lea     rdx, _GUID_d4d21454_070f_4033_88f6_1b8d7ba630a9
0x1801e9047  mov     r8d, r13d
0x1801e904a  mov     [rbp+1090h+var_10EC+4], 8
0x1801e9052  mov     [rsp+1190h+pcbData], r12
0x1801e9057  call    IUnknown_QueryStatus
0x1801e905c  test    eax, eax
0x1801e905e  js      short loc_1801E9078
0x1801e9060  mov     esi, dword ptr [rbp+1090h+var_10EC]
0x1801e9063  shr     esi, 1
0x1801e9065  and     sil, r15b
0x1801e9068  mov     [rsp+1190h+var_1150], r15b
0x1801e906d  test    [rbp+1090h+var_10E4], r13b
0x1801e9071  jnz     short loc_1801E9078
0x1801e9073  mov     [rsp+1190h+var_1150], r12b
0x1801e9078  mov     rcx, [rsp+1190h+var_1138]
0x1801e907d  lea     r9, [rsp+1190h+var_1118]
0x1801e9082  xor     eax, eax
0x1801e9084  mov     dword ptr [rsp+1190h+var_1118], 4
0x1801e908c  mov     qword ptr [rsp+1190h+var_1118+4], rax
0x1801e9091  lea     rdx, CGID_BrowserFrame
0x1801e9098  mov     r8d, r13d
0x1801e909b  mov     qword ptr [rbp+1090h+var_1118+8], 5
0x1801e90a3  mov     [rsp+1190h+pcbData], r12
0x1801e90a8  call    IUnknown_QueryStatus
0x1801e90ad  test    eax, eax
0x1801e90af  js      short loc_1801E90E2
0x1801e90b1  mov     r15d, dword ptr [rsp+1190h+var_1118+4]
  ... truncated ...
```
