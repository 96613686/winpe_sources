# CShellBrowser2::_OnViewMenuPopup(HMENU__ *)

- ea: `0x1802022ac`
- end: `0x180202a22`
- name: `?_OnViewMenuPopup@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z`
- size: `1910`
- prototype: `void __fastcall(CShellBrowser2 *__hidden this, HMENU)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802073b0`

## callees

- `0x180005030`
- `0x18001546c`
- `0x1800184f0`
- `0x180024b74`
- `0x18003ca80`
- `0x18004d964`
- `0x180074e98`
- `0x18007b178`
- `0x1800aa44c`
- `0x1800c87a0`
- `0x1800c87bc`
- `0x1800ca1c0`
- `0x1800cff60`
- `0x1800d1c00`
- `0x1801efb10`
- `0x1801fd32c`
- `0x1802022ac`
- `0x18020782c`
- `0x1802befc4`
- `0x180439b8c`
- `0x18057f11c`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegGetUSValueW` at `0x180202630`
- `api-ms-win-downlevel-shlwapi-l1-1-0!SHRegGetUSValueW` at `0x180202630`
- `USER32!SetMenuItemInfoW` at `0x180202487`
- `USER32!SetMenuItemInfoW` at `0x180202487`
- `USER32!DeleteMenu` at `0x1802024bd`
- `USER32!DeleteMenu` at `0x1802024f9`
- `USER32!DeleteMenu` at `0x18020255b`
- `USER32!DeleteMenu` at `0x180202916`
- `USER32!DeleteMenu` at `0x1802024bd`
- `USER32!DeleteMenu` at `0x1802024f9`
- `USER32!DeleteMenu` at `0x18020255b`
- `USER32!DeleteMenu` at `0x180202916`
- `USER32!CheckMenuItem` at `0x180202820`
- `USER32!CheckMenuItem` at `0x180202850`
- `USER32!CheckMenuItem` at `0x18020298e`
- `USER32!CheckMenuItem` at `0x180202820`
- `USER32!CheckMenuItem` at `0x180202850`
- `USER32!CheckMenuItem` at `0x18020298e`
- `USER32!RemoveMenu` at `0x18020264e`
- `USER32!RemoveMenu` at `0x1802029a7`
- `USER32!RemoveMenu` at `0x18020264e`
- `USER32!RemoveMenu` at `0x1802029a7`
- `OLEAUT32!__imp_SysFreeString` at `0x1802029cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1802029cc`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1802024de`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1802024de`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x180202570`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x180202892`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x180202570`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x180202892`

## pseudocode

```c
void __fastcall CShellBrowser2::_OnViewMenuPopup(CShellBrowser2 *this, HMENU a2)
{
  CLayerParticipant *v4; // rdi
  int v5; // r12d
  __int64 v6; // rcx
  HMENU v7; // rdi
  HMENU v8; // rcx
  struct IUnknown *v9; // r14
  __int64 v10; // rcx
  int UrlSchemeW; // eax
  __int64 v12; // r8
  bool v13; // r14
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
    SHEnableMenuItem(a2, 3163, 0);
  }
  if ( (unsigned int)SHRestricted2W(1610612746, 0, 0) )
    SHEnableMenuItem(a2, 41499, 0);
  if ( (unsigned int)SHRestricted2W(1610612774, 0, 0) )
    SHEnableMenuItem(a2, 41497, 0);
  v20[0] = 0;
  CLayerParticipant::LayerGetBool(v4, v20, 69722, 0);
  if ( v20[0] )
  {
    SHEnableMenuItem(a2, 3163, 0);
    SHEnableMenuItem(a2, 41497, 0);
    SHEnableMenuItem(a2, 41479, 0);
    SHEnableMenuItem(a2, 41502, 0);
    SHEnableMenuItem(a2, 41476, 0);
    SHEnableMenuItem(a2, 3460, 0);
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
    SHEnableMenuItem(v7, 41511, 0);
    DeleteMenu(v7, 0xA20Cu, 0);
  }
  else
  {
    if ( (unsigned int)IsPolicyEnabledValue((__int64 *)SettingStore::IEVALUE_Browser_ToolBarsLocked[0]) )
      SHEnableMenuItem(v7, 41484, 0);
    SHCheckMenuItem(v7, 41484, HIDWORD(v31));
  }
  v9 = (struct IUnknown *)*((_QWORD *)this + 816);
  if ( (unsigned int)SHRestricted2W(2, 0, 0) )
  {
    SHEnableMenuItem(a2, 41482, 0);
    SHEnableMenuItem(a2, 41477, 0);
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
    SHEnableMenuItem(a2, 41474, 0);
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
0x1802022ac  mov     [rsp-8+arg_10], rbx
0x1802022b1  push    rbp
0x1802022b2  push    rsi
0x1802022b3  push    rdi
0x1802022b4  push    r12
0x1802022b6  push    r13
0x1802022b8  push    r14
0x1802022ba  push    r15
0x1802022bc  lea     rbp, [rsp-1060h]
0x1802022c4  mov     eax, 1160h
0x1802022c9  call    _alloca_probe
0x1802022ce  sub     rsp, rax
0x1802022d1  mov     rax, cs:__security_cookie
0x1802022d8  xor     rax, rsp
0x1802022db  mov     [rbp+1090h+var_40], rax
0x1802022e2  mov     rbx, rdx
0x1802022e5  mov     [rbp+1090h+var_1100], 17h
0x1802022ed  mov     rsi, rcx
0x1802022f0  mov     [rbp+1090h+var_10F8], 0Dh
0x1802022f8  lea     rdi, [rcx+0E8h]
0x1802022ff  xor     edx, edx
0x180202301  mov     ecx, 6000000Ch
0x180202306  xor     r8d, r8d
0x180202309  xor     r12d, r12d
0x18020230c  call    SHRestricted2W
0x180202311  mov     r13d, 0C5Bh
0x180202317  mov     r14d, 1105Ah
0x18020231d  test    eax, eax
0x18020231f  jnz     short loc_180202340
0x180202321  xor     r9d, r9d; int
0x180202324  mov     [rsp+1190h+var_1150], r12b
0x180202329  mov     r8d, r14d; int
0x18020232c  lea     rdx, [rsp+1190h+var_1150]; bool *
0x180202331  mov     rcx, rdi; this
0x180202334  call    ?LayerGetBool@CLayerParticipant@@IEAAJPEA_NHH@Z; CLayerParticipant::LayerGetBool(bool *,int,int)
0x180202339  cmp     [rsp+1190h+var_1150], r12b
0x18020233e  jz      short loc_18020234E
0x180202340  xor     r8d, r8d
0x180202343  mov     edx, r13d
0x180202346  mov     rcx, rbx
0x180202349  call    SHEnableMenuItem
0x18020234e  xor     r8d, r8d
0x180202351  xor     edx, edx
0x180202353  mov     ecx, 6000000Ah
0x180202358  call    SHRestricted2W
0x18020235d  test    eax, eax
0x18020235f  jz      short loc_180202371
0x180202361  xor     r8d, r8d
0x180202364  mov     edx, 0A21Bh
0x180202369  mov     rcx, rbx
0x18020236c  call    SHEnableMenuItem
0x180202371  xor     r8d, r8d
0x180202374  xor     edx, edx
0x180202376  mov     ecx, 60000026h
0x18020237b  call    SHRestricted2W
0x180202380  mov     r15d, 0A219h
0x180202386  test    eax, eax
0x180202388  jz      short loc_180202398
0x18020238a  xor     r8d, r8d
0x18020238d  mov     edx, r15d
0x180202390  mov     rcx, rbx
0x180202393  call    SHEnableMenuItem
0x180202398  xor     r9d, r9d; int
0x18020239b  mov     [rsp+1190h+var_1150], r12b
0x1802023a0  mov     r8d, r14d; int
0x1802023a3  lea     rdx, [rsp+1190h+var_1150]; bool *
0x1802023a8  mov     rcx, rdi; this
0x1802023ab  call    ?LayerGetBool@CLayerParticipant@@IEAAJPEA_NHH@Z; CLayerParticipant::LayerGetBool(bool *,int,int)
0x1802023b0  cmp     [rsp+1190h+var_1150], r12b
0x1802023b5  jz      short loc_180202413
0x1802023b7  xor     r8d, r8d
0x1802023ba  mov     edx, r13d
0x1802023bd  mov     rcx, rbx
0x1802023c0  call    SHEnableMenuItem
0x1802023c5  xor     r8d, r8d
0x1802023c8  mov     edx, r15d
0x1802023cb  mov     rcx, rbx
0x1802023ce  call    SHEnableMenuItem
0x1802023d3  xor     r8d, r8d
0x1802023d6  mov     edx, 0A207h
0x1802023db  mov     rcx, rbx
0x1802023de  call    SHEnableMenuItem
0x1802023e3  xor     r8d, r8d
0x1802023e6  mov     edx, 0A21Eh
0x1802023eb  mov     rcx, rbx
0x1802023ee  call    SHEnableMenuItem
0x1802023f3  xor     r8d, r8d
0x1802023f6  mov     edx, 0A204h
0x1802023fb  mov     rcx, rbx
0x1802023fe  call    SHEnableMenuItem
0x180202403  xor     r8d, r8d
0x180202406  mov     edx, 0D84h
0x18020240b  mov     rcx, rbx
0x18020240e  call    SHEnableMenuItem
0x180202413  mov     rcx, [rsi+1980h]
0x18020241a  mov     r13d, 2
0x180202420  test    rcx, rcx
0x180202423  jz      short loc_18020243D
0x180202425  lea     r9, [rbp+1090h+var_1100]
0x180202429  mov     [rsp+1190h+pcbData], r12
0x18020242e  mov     r8d, r13d
0x180202431  lea     rdx, CGID_PrivCITCommands
0x180202438  call    IUnknown_QueryStatus
0x18020243d  mov     rcx, cs:g_hinstMUI
0x180202444  mov     edx, 108h
0x180202449  call    SHLoadMenuPopup
0x18020244e  mov     r14d, 50h ; 'P'
0x180202454  lea     rcx, [rbp+1090h+mii]; void *
0x180202458  mov     r8d, r14d; Size
0x18020245b  xor     edx, edx; Val
0x18020245d  mov     rdi, rax
0x180202460  call    memset_0
0x180202465  mov     rcx, [rsi+18E0h]; hmenu
0x18020246c  lea     r9, [rbp+1090h+mii]; lpmii
0x180202470  xor     r8d, r8d; fByPositon
0x180202473  mov     [rbp+1090h+mii.cbSize], r14d
0x180202477  mov     edx, 0A201h; item
0x18020247c  mov     [rbp+1090h+mii.fMask], 4
0x180202483  mov     [rbp+1090h+mii.hSubMenu], rdi
0x180202487  call    cs:__imp_SetMenuItemInfoW
0x18020248e  nop     dword ptr [rax+rax+00h]
0x180202493  mov     rcx, [rsi+158h]; hWnd
0x18020249a  xor     r9d, r9d
0x18020249d  xor     r8d, r8d
0x1802024a0  mov     edx, 6000000Eh
0x1802024a5  call    SHIsRestricted2W
0x1802024aa  lea     r15d, [r14-4Fh]
0x1802024ae  mov     edx, 0A227h; uPosition
0x1802024b3  mov     rcx, rdi; hMenu
0x1802024b6  test    eax, eax
0x1802024b8  jz      short loc_1802024CB
0x1802024ba  xor     r8d, r8d; uFlags
0x1802024bd  call    cs:__imp_DeleteMenu
0x1802024c4  nop     dword ptr [rax+rax+00h]
0x1802024c9  jmp     short loc_1802024DE
0x1802024cb  mov     r8d, dword ptr [rbp+1090h+var_10F8+4]
0x1802024cf  shr     r8d, 2
0x1802024d3  not     r8d
0x1802024d6  and     r8d, r15d
0x1802024d9  call    SHCheckMenuItem
0x1802024de  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1802024e5  nop     dword ptr [rax+rax+00h]
0x1802024ea  test    al, al
0x1802024ec  jnz     short loc_180202507
0x1802024ee  xor     r8d, r8d; uFlags
0x1802024f1  mov     edx, 0A5D0h; uPosition
0x1802024f6  mov     rcx, rdi; hMenu
0x1802024f9  call    cs:__imp_DeleteMenu
0x180202500  nop     dword ptr [rax+rax+00h]
0x180202505  jmp     short loc_18020252F
0x180202507  mov     rcx, cs:?IEVALUE_PrivacIE_DisableToolbars@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_PrivacIE_DisableToolbars
0x18020250e  lea     rdx, [rsp+1190h+var_114C]
0x180202513  mov     [rsp+1190h+var_114C], r15d
0x180202518  call    GetBOOL
0x18020251d  mov     r8d, [rsp+1190h+var_114C]
0x180202522  mov     edx, 0A5D0h
0x180202527  mov     rcx, rdi
0x18020252a  call    SHCheckMenuItem
0x18020252f  xor     r8d, r8d
0x180202532  xor     edx, edx
0x180202534  mov     ecx, r13d
0x180202537  call    SHRestricted2W
0x18020253c  test    eax, eax
0x18020253e  jz      short loc_180202569
0x180202540  xor     r8d, r8d
0x180202543  mov     edx, 0A227h
0x180202548  mov     rcx, rdi
0x18020254b  call    SHEnableMenuItem
0x180202550  xor     r8d, r8d; uFlags
0x180202553  mov     edx, 0A20Ch; uPosition
0x180202558  mov     rcx, rdi; hMenu
0x18020255b  call    cs:__imp_DeleteMenu
0x180202562  nop     dword ptr [rax+rax+00h]
0x180202567  jmp     short loc_1802025A1
0x180202569  mov     rcx, cs:?IEVALUE_Browser_ToolBarsLocked@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Browser_ToolBarsLocked
0x180202570  call    cs:__imp_IsPolicyEnabledValue
0x180202577  nop     dword ptr [rax+rax+00h]
0x18020257c  test    eax, eax
0x18020257e  jz      short loc_180202590
0x180202580  xor     r8d, r8d
0x180202583  mov     edx, 0A20Ch
0x180202588  mov     rcx, rdi
0x18020258b  call    SHEnableMenuItem
0x180202590  mov     r8d, dword ptr [rbp+1090h+var_1100+4]
0x180202594  mov     edx, 0A20Ch
0x180202599  mov     rcx, rdi
0x18020259c  call    SHCheckMenuItem
0x1802025a1  mov     r14, [rsi+1980h]
0x1802025a8  xor     r8d, r8d
0x1802025ab  xor     edx, edx
0x1802025ad  mov     ecx, r13d
0x1802025b0  call    SHRestricted2W
0x1802025b5  test    eax, eax
0x1802025b7  jz      short loc_1802025D9
0x1802025b9  xor     r8d, r8d
0x1802025bc  mov     edx, 0A20Ah
0x1802025c1  mov     rcx, rbx
0x1802025c4  call    SHEnableMenuItem
0x1802025c9  xor     r8d, r8d
0x1802025cc  mov     edx, 0A205h
0x1802025d1  mov     rcx, rbx
0x1802025d4  call    SHEnableMenuItem
0x1802025d9  mov     r8d, 0A208h; unsigned int
0x1802025df  mov     rdx, r14; struct IUnknown *
0x1802025e2  mov     rcx, rbx; hMenu
0x1802025e5  call    ?PopulateItbarToolbarBands@@YAXPEAUHMENU__@@PEAUIUnknown@@I@Z; PopulateItbarToolbarBands(HMENU__ *,IUnknown *,uint)
0x1802025ea  mov     eax, 4
0x1802025ef  mov     [rsp+1190h+pvData], r12d
0x1802025f4  mov     [rsp+1190h+dwDefaultDataSize], eax; dwDefaultDataSize
0x1802025f8  lea     r9, [rsp+1190h+pvData]; pvData
0x1802025fd  mov     [rsp+1190h+var_112C], eax
0x180202601  lea     rdx, aEnablejavacons; "EnableJavaConsole"
0x180202608  lea     rax, [rsp+1190h+var_1130]
0x18020260d  mov     [rsp+1190h+var_1130], r12d
0x180202612  mov     [rsp+1190h+pvDefaultData], rax; pvDefaultData
0x180202617  lea     rcx, aSoftwareMicros_24; "Software\\Microsoft\\Java VM"
0x18020261e  lea     rax, [rsp+1190h+var_112C]
0x180202623  mov     [rsp+1190h+fIgnoreHKCU], r12d; fIgnoreHKCU
0x180202628  xor     r8d, r8d; pdwType
0x18020262b  mov     [rsp+1190h+pcbData], rax; pcbData
0x180202630  call    cs:__imp_SHRegGetUSValueW
0x180202637  nop     dword ptr [rax+rax+00h]
0x18020263c  cmp     [rsp+1190h+pvData], r12d
0x180202641  jnz     short loc_18020265A
0x180202643  xor     r8d, r8d; uFlags
0x180202646  mov     edx, 0A21Ch; uPosition
0x18020264b  mov     rcx, rbx; hMenu
0x18020264e  call    cs:__imp_RemoveMenu
0x180202655  nop     dword ptr [rax+rax+00h]
0x18020265a  mov     rcx, [rsi+170h]
0x180202661  lea     rdx, [rsp+1190h+var_1128]
0x180202666  mov     [rsp+1190h+var_1128], r12
0x18020266b  mov     [rsp+1190h+var_1120], r12
0x180202670  mov     [rsp+1190h+bstrString], r12
0x180202675  mov     rax, [rcx]
0x180202678  mov     rax, [rax+90h]
0x18020267f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180202684  test    eax, eax
0x180202686  js      short loc_1802026F6
0x180202688  mov     rcx, [rsp+1190h+var_1128]
0x18020268d  test    rcx, rcx
0x180202690  jz      short loc_1802026F6
0x180202692  mov     rax, [rcx]
0x180202695  lea     r8, [rsp+1190h+var_1120]
0x18020269a  lea     rdx, _GUID_332c4425_26cb_11d0_b483_00c04fd90119
0x1802026a1  mov     rax, [rax]
0x1802026a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802026a9  test    eax, eax
0x1802026ab  js      short loc_1802026F6
0x1802026ad  mov     rcx, [rsp+1190h+var_1120]
0x1802026b2  test    rcx, rcx
0x1802026b5  jz      short loc_1802026F6
0x1802026b7  mov     rax, [rcx]
0x1802026ba  lea     rdx, [rsp+1190h+bstrString]
0x1802026bf  mov     rax, [rax+140h]
0x1802026c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802026cb  test    eax, eax
0x1802026cd  js      short loc_1802026F6
0x1802026cf  mov     rcx, [rsp+1190h+bstrString]
0x1802026d4  call    GetUrlSchemeW
0x1802026d9  cmp     eax, r13d
0x1802026dc  jz      short loc_1802026E6
0x1802026de  mov     r8d, r12d
0x1802026e1  cmp     eax, 0Bh
0x1802026e4  jnz     short loc_1802026E9
0x1802026e6  mov     r8d, r15d
0x1802026e9  mov     edx, 0A223h
0x1802026ee  mov     rcx, rbx
0x1802026f1  call    SHEnableMenuItem
0x1802026f6  lea     rdx, [rsp+1190h+var_1138]; struct IBrowserFrame **
0x1802026fb  mov     [rsp+1190h+var_1150], r12b
0x180202700  mov     rcx, rsi; this
0x180202703  mov     [rsp+1190h+var_1138], r12
0x180202708  mov     r14b, r12b
0x18020270b  call    ?_GetBrowserFrame@CShellBrowser2@@AEAAJPEAPEAUIBrowserFrame@@@Z; CShellBrowser2::_GetBrowserFrame(IBrowserFrame * *)
0x180202710  test    eax, eax
0x180202712  js      loc_1802027CF
0x180202718  mov     rcx, [rsp+1190h+var_1138]
0x18020271d  lea     r9, [rbp+1090h+var_10F0]
0x180202721  xor     eax, eax
0x180202723  mov     [rbp+1090h+var_10F0], r15d
0x180202727  mov     [rbp+1090h+var_10EC], rax
0x18020272b  lea     rdx, _GUID_d4d21454_070f_4033_88f6_1b8d7ba630a9
0x180202732  mov     r8d, r13d
0x180202735  mov     [rbp+1090h+var_10EC+4], 8
0x18020273d  mov     [rsp+1190h+pcbData], r12
0x180202742  call    IUnknown_QueryStatus
0x180202747  test    eax, eax
0x180202749  js      short loc_180202765
0x18020274b  mov     r14d, dword ptr [rbp+1090h+var_10EC]
0x18020274f  shr     r14d, 1
0x180202752  and     r14b, r15b
0x180202755  mov     [rsp+1190h+var_1150], r15b
0x18020275a  test    [rbp+1090h+var_10E4], r13b
0x18020275e  jnz     short loc_180202765
0x180202760  mov     [rsp+1190h+var_1150], r12b
0x180202765  mov     rcx, [rsp+1190h+var_1138]
0x18020276a  lea     r9, [rsp+1190h+var_1118]
0x18020276f  xor     eax, eax
0x180202771  mov     dword ptr [rsp+1190h+var_1118], 4
  ... truncated ...
```
