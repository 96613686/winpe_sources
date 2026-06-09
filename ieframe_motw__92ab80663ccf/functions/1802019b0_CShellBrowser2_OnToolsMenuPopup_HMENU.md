# CShellBrowser2::_OnToolsMenuPopup(HMENU__ *)

- ea: `0x1802019b0`
- end: `0x180201e20`
- name: `?_OnToolsMenuPopup@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z`
- size: `1136`
- prototype: `void __fastcall(CShellBrowser2 *__hidden this, HMENU)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1802073b0`

## callees

- `0x180005030`
- `0x1800184f0`
- `0x180074e98`
- `0x18007b178`
- `0x1800c87bc`
- `0x1801fed48`
- `0x1802019b0`
- `0x180201e28`
- `0x180201f60`
- `0x18028b358`
- `0x1804211f0`
- `0x18042cba0`
- `0x180439b8c`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180201cb1`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180201cb1`
- `USER32!SetMenuItemInfoW` at `0x180201cfd`
- `USER32!SetMenuItemInfoW` at `0x180201cfd`
- `USER32!DeleteMenu` at `0x1802019e9`
- `USER32!DeleteMenu` at `0x180201a02`
- `USER32!DeleteMenu` at `0x180201b90`
- `USER32!DeleteMenu` at `0x180201d16`
- `USER32!DeleteMenu` at `0x180201d3e`
- `USER32!DeleteMenu` at `0x180201d72`
- `USER32!DeleteMenu` at `0x1802019e9`
- `USER32!DeleteMenu` at `0x180201a02`
- `USER32!DeleteMenu` at `0x180201b90`
- `USER32!DeleteMenu` at `0x180201d16`
- `USER32!DeleteMenu` at `0x180201d3e`
- `USER32!DeleteMenu` at `0x180201d72`
- `USER32!CheckMenuItem` at `0x180201ae1`
- `USER32!CheckMenuItem` at `0x180201b6a`
- `USER32!CheckMenuItem` at `0x180201dc1`
- `USER32!CheckMenuItem` at `0x180201ae1`
- `USER32!CheckMenuItem` at `0x180201b6a`
- `USER32!CheckMenuItem` at `0x180201dc1`
- `iertutil!__imp_IERegGetBool` at `0x180201a8e`
- `iertutil!__imp_IERegGetBool` at `0x180201a8e`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x180201ba6`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x180201dd4`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x180201ba6`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x180201dd4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180201a43`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x180201a43`

## pseudocode

```c
void __fastcall CShellBrowser2::_OnToolsMenuPopup(CShellBrowser2 *this, HMENU a2)
{
  IUnknown *v4; // rcx
  bool IsLocationDnsErrorUrl; // al
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  char PrivacIESettingsMode; // al
  unsigned int StringW; // ebx
  unsigned __int16 v12; // r8
  int v13; // eax
  bool v14; // [rsp+30h] [rbp-D0h] BYREF
  void *ppvOut; // [rsp+38h] [rbp-C8h] BYREF
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  MENUITEMINFOW mii; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[80]; // [rsp+B0h] [rbp-50h] BYREF

  DeleteMenu(a2, 0x156u, 0);
  DeleteMenu(a2, 0xA150u, 0);
  if ( !(unsigned int)SHRestricted2W(1610612773, 0, 0) )
  {
    v4 = (IUnknown *)*((_QWORD *)this + 50);
    ppvOut = 0;
    if ( IUnknown_QueryService(v4, &IID_INewWindowManagerCallback, &GUID_b5ecdf5d_f3f9_4392_bac5_248961093fa2, &ppvOut) >= 0 )
    {
      (*(void (__fastcall **)(void *, HMENU, __int64, __int64))(*(_QWORD *)ppvOut + 48LL))(ppvOut, a2, 41296, 41271);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    }
  }
  v16 = 0;
  IERegGetBool(8, &v16);
  SHEnableMenuItem(a2, 41267, v16 == 0);
  IsLocationDnsErrorUrl = CShellBrowser2::_IsLocationDnsErrorUrl(this);
  SHEnableMenuItem(a2, 41266, IsLocationDnsErrorUrl);
  LODWORD(ppvOut) = 1;
  CheckMenuItem(a2, 0xA23Au, 0);
  v14 = 0;
  CLayerParticipant::LayerGetBool((CShellBrowser2 *)((char *)this + 232), &v14, 69722, 0);
  if ( v14 || (GetBOOL((__int64 *)SettingStore::IEVALUE_IEDevTools_Disabled[0], &ppvOut), (_DWORD)ppvOut) )
  {
    SHEnableMenuItem(a2, 41530, 0);
  }
  else
  {
    v6 = *((_QWORD *)this + 859);
    v7 = 0;
    LODWORD(ppvOut) = 0;
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v6 + 56LL))(v6, &ppvOut);
      v7 = (int)ppvOut;
    }
    if ( *((_DWORD *)this + 1625) == 41530 || v7 )
      CheckMenuItem(a2, 0xA23Au, 8u);
  }
  DeleteMenu(a2, 0xA1C7u, 0);
  v8 = 0;
  if ( !(unsigned int)IsPolicyEnabledValue((__int64 *)SettingStore::IEVALUE_Recovery_NoReopenLastSession[0]) )
  {
    v18[0] = 0;
    if ( (*(int (__fastcall **)(char *, SID *, GUID *, _QWORD *))(*((_QWORD *)this + 4) + 24LL))(
           (char *)this + 32,
           &SID_STabWindowManager,
           &GUID_feefb420_9399_492d_969c_51af6dc38fb1,
           v18) >= 0 )
    {
      v17 = 0;
      LODWORD(ppvOut) = 0;
      if ( (*(int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v18[0] + 192LL))(v18[0], &v17) >= 0
        && (*(int (__fastcall **)(__int64, void **))(*(_QWORD *)v17 + 32LL))(v17, &ppvOut) >= 0 )
      {
        LOBYTE(v8) = (_DWORD)ppvOut != 0;
      }
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v17);
    }
    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(v18);
  }
  SHEnableMenuItem(a2, 41270, v8);
  v9 = InPrivateBrowsingAllowed();
  SHEnableMenuItem(a2, 41268, v9 >= 0);
  LODWORD(ppvOut) = 0;
  if ( (int)GetBOOL((__int64 *)SettingStore::IEVALUE_PrivacIE_DisableInPrivateBlocking[0], &ppvOut) >= 0
    && (_DWORD)ppvOut
    || (PrivacIESettingsMode = GetPrivacIESettingsMode(),
        StringW = LoadStringW(g_hinstMUI, (PrivacIESettingsMode & 4 | 0x119C8u) >> 2, Buffer, 80),
        memset_0(&mii, 0, sizeof(mii)),
        StringW <= 1) )
  {
    DeleteMenu(a2, 0xA1CEu, 0);
  }
  else
  {
    mii.cbSize = 80;
    mii.dwTypeData = Buffer;
    *(_QWORD *)&mii.fMask = 16;
    SetMenuItemInfoW(a2, 0xA1CEu, 0, &mii);
  }
  if ( !IsWindowsVersionOrGreater(6u, 3u, v12) )
    DeleteMenu(a2, 0xA137u, 0);
  LODWORD(ppvOut) = 0;
  GetBOOL((__int64 *)SettingStore::IEVALUE_ReportSiteProblems_NoReportSiteProblems[0], &ppvOut);
  if ( (_DWORD)ppvOut )
    DeleteMenu(a2, 0xA160u, 0);
  CShellBrowser2::_OnToolsMenuPopup_AddToStart(this, a2);
  CShellBrowser2::_OnToolsMenuPopup_EnterpriseMode(this, a2);
  LODWORD(ppvOut) = 0;
  GetBOOL((__int64 *)SettingStore::IEVALUE_ActiveXFiltering_IsEnabled[0], &ppvOut);
  CheckMenuItem(a2, 0xA1CFu, (_DWORD)ppvOut != 0 ? 8 : 0);
  v13 = IsPolicyEnabledValue((__int64 *)SettingStore::IEVALUE_ActiveXFiltering_IsEnabled[0]);
  SHEnableMenuItem(a2, 41423, v13 == 0);
  SHPrettyMenu(a2);
}

```

## disassembly

```asm
0x1802019b0  mov     [rsp-8+arg_10], rbx
0x1802019b5  mov     [rsp-8+arg_18], rsi
0x1802019ba  push    rbp
0x1802019bb  push    rdi
0x1802019bc  push    r14
0x1802019be  lea     rbp, [rsp-60h]
0x1802019c3  sub     rsp, 160h
0x1802019ca  mov     rax, cs:__security_cookie
0x1802019d1  xor     rax, rsp
0x1802019d4  mov     [rbp+70h+var_20], rax
0x1802019d8  mov     rdi, rdx
0x1802019db  mov     rsi, rcx
0x1802019de  mov     rcx, rdi; hMenu
0x1802019e1  xor     r8d, r8d; uFlags
0x1802019e4  mov     edx, 156h; uPosition
0x1802019e9  call    cs:__imp_DeleteMenu
0x1802019f0  nop     dword ptr [rax+rax+00h]
0x1802019f5  mov     ebx, 0A150h
0x1802019fa  xor     r8d, r8d; uFlags
0x1802019fd  mov     edx, ebx; uPosition
0x1802019ff  mov     rcx, rdi; hMenu
0x180201a02  call    cs:__imp_DeleteMenu
0x180201a09  nop     dword ptr [rax+rax+00h]
0x180201a0e  xor     r8d, r8d
0x180201a11  xor     edx, edx
0x180201a13  mov     ecx, 60000025h
0x180201a18  call    SHRestricted2W
0x180201a1d  xor     r14d, r14d
0x180201a20  test    eax, eax
0x180201a22  jnz     short loc_180201A7F
0x180201a24  mov     rcx, [rsi+190h]; punk
0x180201a2b  lea     r9, [rsp+170h+ppvOut]; ppvOut
0x180201a30  lea     r8, _GUID_b5ecdf5d_f3f9_4392_bac5_248961093fa2; riid
0x180201a37  mov     [rsp+170h+ppvOut], r14
0x180201a3c  lea     rdx, IID_INewWindowManagerCallback; guidService
0x180201a43  call    cs:__imp_IUnknown_QueryService
0x180201a4a  nop     dword ptr [rax+rax+00h]
0x180201a4f  test    eax, eax
0x180201a51  js      short loc_180201A7F
0x180201a53  mov     rcx, [rsp+170h+ppvOut]
0x180201a58  lea     r9d, [rbx-19h]
0x180201a5c  mov     r8d, ebx
0x180201a5f  mov     rdx, rdi
0x180201a62  mov     rax, [rcx]
0x180201a65  mov     rax, [rax+30h]
0x180201a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201a6e  mov     rcx, [rsp+170h+ppvOut]
0x180201a73  mov     rax, [rcx]
0x180201a76  mov     rax, [rax+10h]
0x180201a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201a7f  lea     rdx, [rsp+170h+var_130]
0x180201a84  mov     [rsp+170h+var_130], r14d
0x180201a89  mov     ecx, 8
0x180201a8e  call    cs:__imp_IERegGetBool
0x180201a95  nop     dword ptr [rax+rax+00h]
0x180201a9a  cmp     [rsp+170h+var_130], r14d
0x180201a9f  mov     r8d, r14d
0x180201aa2  mov     edx, 0A133h
0x180201aa7  mov     rcx, rdi
0x180201aaa  setz    r8b
0x180201aae  call    SHEnableMenuItem
0x180201ab3  mov     rcx, rsi; this
0x180201ab6  call    ?_IsLocationDnsErrorUrl@CShellBrowser2@@AEBA_NXZ; CShellBrowser2::_IsLocationDnsErrorUrl(void)
0x180201abb  movzx   r8d, al
0x180201abf  mov     edx, 0A132h
0x180201ac4  mov     rcx, rdi
0x180201ac7  call    SHEnableMenuItem
0x180201acc  mov     ebx, 0A23Ah
0x180201ad1  mov     dword ptr [rsp+170h+ppvOut], 1
0x180201ad9  mov     edx, ebx; uIDCheckItem
0x180201adb  xor     r8d, r8d; uCheck
0x180201ade  mov     rcx, rdi; hMenu
0x180201ae1  call    cs:__imp_CheckMenuItem
0x180201ae8  nop     dword ptr [rax+rax+00h]
0x180201aed  lea     rcx, [rsi+0E8h]; this
0x180201af4  mov     [rsp+170h+var_140], r14b
0x180201af9  xor     r9d, r9d; int
0x180201afc  lea     rdx, [rsp+170h+var_140]; bool *
0x180201b01  mov     r8d, 1105Ah; int
0x180201b07  call    ?LayerGetBool@CLayerParticipant@@IEAAJPEA_NHH@Z; CLayerParticipant::LayerGetBool(bool *,int,int)
0x180201b0c  cmp     [rsp+170h+var_140], r14b
0x180201b11  jnz     short loc_180201B78
0x180201b13  mov     rcx, cs:?IEVALUE_IEDevTools_Disabled@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_IEDevTools_Disabled
0x180201b1a  lea     rdx, [rsp+170h+ppvOut]
0x180201b1f  call    GetBOOL
0x180201b24  cmp     dword ptr [rsp+170h+ppvOut], r14d
0x180201b29  jnz     short loc_180201B78
0x180201b2b  mov     rcx, [rsi+1AD8h]
0x180201b32  mov     eax, r14d
0x180201b35  mov     dword ptr [rsp+170h+ppvOut], eax
0x180201b39  test    rcx, rcx
0x180201b3c  jz      short loc_180201B53
0x180201b3e  mov     rax, [rcx]
0x180201b41  lea     rdx, [rsp+170h+ppvOut]
0x180201b46  mov     rax, [rax+38h]
0x180201b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201b4f  mov     eax, dword ptr [rsp+170h+ppvOut]
0x180201b53  cmp     [rsi+1964h], ebx
0x180201b59  jz      short loc_180201B5F
0x180201b5b  test    eax, eax
0x180201b5d  jz      short loc_180201B85
0x180201b5f  mov     r8d, 8; uCheck
0x180201b65  mov     edx, ebx; uIDCheckItem
0x180201b67  mov     rcx, rdi; hMenu
0x180201b6a  call    cs:__imp_CheckMenuItem
0x180201b71  nop     dword ptr [rax+rax+00h]
0x180201b76  jmp     short loc_180201B85
0x180201b78  xor     r8d, r8d
0x180201b7b  mov     edx, ebx
0x180201b7d  mov     rcx, rdi
0x180201b80  call    SHEnableMenuItem
0x180201b85  xor     r8d, r8d; uFlags
0x180201b88  mov     edx, 0A1C7h; uPosition
0x180201b8d  mov     rcx, rdi; hMenu
0x180201b90  call    cs:__imp_DeleteMenu
0x180201b97  nop     dword ptr [rax+rax+00h]
0x180201b9c  mov     rcx, cs:?IEVALUE_Recovery_NoReopenLastSession@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Recovery_NoReopenLastSession
0x180201ba3  mov     ebx, r14d
0x180201ba6  call    cs:__imp_IsPolicyEnabledValue
0x180201bad  nop     dword ptr [rax+rax+00h]
0x180201bb2  test    eax, eax
0x180201bb4  jnz     loc_180201C43
0x180201bba  lea     rcx, [rsi+20h]
0x180201bbe  mov     [rsp+170h+var_120], r14
0x180201bc3  mov     rax, [rcx]
0x180201bc6  lea     r9, [rsp+170h+var_120]
0x180201bcb  lea     r8, _GUID_feefb420_9399_492d_969c_51af6dc38fb1
0x180201bd2  lea     rdx, SID_STabWindowManager
0x180201bd9  mov     rax, [rax+18h]
0x180201bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201be2  test    eax, eax
0x180201be4  js      short loc_180201C39
0x180201be6  mov     rcx, [rsp+170h+var_120]
0x180201beb  lea     rdx, [rsp+170h+var_128]
0x180201bf0  mov     [rsp+170h+var_128], r14
0x180201bf5  mov     dword ptr [rsp+170h+ppvOut], r14d
0x180201bfa  mov     rax, [rcx]
0x180201bfd  mov     rax, [rax+0C0h]
0x180201c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201c09  test    eax, eax
0x180201c0b  js      short loc_180201C2F
0x180201c0d  mov     rcx, [rsp+170h+var_128]
0x180201c12  lea     rdx, [rsp+170h+ppvOut]
0x180201c17  mov     rax, [rcx]
0x180201c1a  mov     rax, [rax+20h]
0x180201c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180201c23  test    eax, eax
0x180201c25  js      short loc_180201C2F
0x180201c27  cmp     dword ptr [rsp+170h+ppvOut], r14d
0x180201c2c  setnbe  bl
0x180201c2f  lea     rcx, [rsp+170h+var_128]; void *
0x180201c34  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180201c39  lea     rcx, [rsp+170h+var_120]; void *
0x180201c3e  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180201c43  mov     r8d, ebx
0x180201c46  mov     edx, 0A136h
0x180201c4b  mov     rcx, rdi
0x180201c4e  call    SHEnableMenuItem
0x180201c53  call    ?InPrivateBrowsingAllowed@@YAJXZ; InPrivateBrowsingAllowed(void)
0x180201c58  not     eax
0x180201c5a  mov     edx, 0A134h
0x180201c5f  shr     eax, 1Fh
0x180201c62  mov     rcx, rdi
0x180201c65  mov     r8d, eax
0x180201c68  call    SHEnableMenuItem
0x180201c6d  mov     rcx, cs:?IEVALUE_PrivacIE_DisableInPrivateBlocking@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_PrivacIE_DisableInPrivateBlocking
0x180201c74  lea     rdx, [rsp+170h+ppvOut]
0x180201c79  mov     dword ptr [rsp+170h+ppvOut], r14d
0x180201c7e  call    GetBOOL
0x180201c83  test    eax, eax
0x180201c85  js      short loc_180201C8E
0x180201c87  cmp     dword ptr [rsp+170h+ppvOut], r14d
0x180201c8c  jnz     short loc_180201D0B
0x180201c8e  call    ?GetPrivacIESettingsMode@@YAKXZ; GetPrivacIESettingsMode(void)
0x180201c93  mov     rcx, cs:g_hinstMUI; hInstance
0x180201c9a  lea     r8, [rbp+70h+Buffer]; lpBuffer
0x180201c9e  and     eax, 4
0x180201ca1  mov     r9d, 50h ; 'P'; cchBufferMax
0x180201ca7  or      eax, 119C8h
0x180201cac  shr     eax, 2
0x180201caf  mov     edx, eax; uID
0x180201cb1  call    cs:__imp_LoadStringW
0x180201cb8  nop     dword ptr [rax+rax+00h]
0x180201cbd  xor     edx, edx; Val
0x180201cbf  lea     rcx, [rsp+170h+mii]; void *
0x180201cc4  mov     ebx, eax
0x180201cc6  lea     r8d, [rdx+50h]; Size
0x180201cca  call    memset_0
0x180201ccf  cmp     ebx, 1
0x180201cd2  jbe     short loc_180201D0B
0x180201cd4  lea     rax, [rbp+70h+Buffer]
0x180201cd8  mov     [rsp+170h+mii.cbSize], 50h ; 'P'
0x180201ce0  lea     r9, [rsp+170h+mii]; lpmii
0x180201ce5  mov     [rbp+70h+mii.dwTypeData], rax
0x180201ce9  xor     r8d, r8d; fByPositon
0x180201cec  mov     qword ptr [rsp+170h+mii.fMask], 10h
0x180201cf5  mov     edx, 0A1CEh; item
0x180201cfa  mov     rcx, rdi; hmenu
0x180201cfd  call    cs:__imp_SetMenuItemInfoW
0x180201d04  nop     dword ptr [rax+rax+00h]
0x180201d09  jmp     short loc_180201D22
0x180201d0b  xor     r8d, r8d; uFlags
0x180201d0e  mov     edx, 0A1CEh; uPosition
0x180201d13  mov     rcx, rdi; hMenu
0x180201d16  call    cs:__imp_DeleteMenu
0x180201d1d  nop     dword ptr [rax+rax+00h]
0x180201d22  mov     edx, 3; unsigned __int16
0x180201d27  lea     ecx, [rdx+3]; unsigned __int16
0x180201d2a  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x180201d2f  test    al, al
0x180201d31  jnz     short loc_180201D4A
0x180201d33  xor     r8d, r8d; uFlags
0x180201d36  mov     edx, 0A137h; uPosition
0x180201d3b  mov     rcx, rdi; hMenu
0x180201d3e  call    cs:__imp_DeleteMenu
0x180201d45  nop     dword ptr [rax+rax+00h]
0x180201d4a  mov     rcx, cs:?IEVALUE_ReportSiteProblems_NoReportSiteProblems@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_ReportSiteProblems_NoReportSiteProblems
0x180201d51  lea     rdx, [rsp+170h+ppvOut]
0x180201d56  mov     dword ptr [rsp+170h+ppvOut], r14d
0x180201d5b  call    GetBOOL
0x180201d60  cmp     dword ptr [rsp+170h+ppvOut], r14d
0x180201d65  jz      short loc_180201D7E
0x180201d67  xor     r8d, r8d; uFlags
0x180201d6a  mov     edx, 0A160h; uPosition
0x180201d6f  mov     rcx, rdi; hMenu
0x180201d72  call    cs:__imp_DeleteMenu
0x180201d79  nop     dword ptr [rax+rax+00h]
0x180201d7e  mov     rdx, rdi; HMENU
0x180201d81  mov     rcx, rsi; this
0x180201d84  call    ?_OnToolsMenuPopup_AddToStart@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z; CShellBrowser2::_OnToolsMenuPopup_AddToStart(HMENU__ *)
0x180201d89  mov     rdx, rdi; HMENU
0x180201d8c  mov     rcx, rsi; this
0x180201d8f  call    ?_OnToolsMenuPopup_EnterpriseMode@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z; CShellBrowser2::_OnToolsMenuPopup_EnterpriseMode(HMENU__ *)
0x180201d94  mov     rcx, cs:?IEVALUE_ActiveXFiltering_IsEnabled@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_ActiveXFiltering_IsEnabled
0x180201d9b  lea     rdx, [rsp+170h+ppvOut]
0x180201da0  mov     dword ptr [rsp+170h+ppvOut], r14d
0x180201da5  call    GetBOOL
0x180201daa  mov     eax, dword ptr [rsp+170h+ppvOut]
0x180201dae  mov     ebx, 0A1CFh
0x180201db3  neg     eax
0x180201db5  mov     edx, ebx; uIDCheckItem
0x180201db7  mov     rcx, rdi; hMenu
0x180201dba  sbb     r8d, r8d
0x180201dbd  and     r8d, 8; uCheck
0x180201dc1  call    cs:__imp_CheckMenuItem
0x180201dc8  nop     dword ptr [rax+rax+00h]
0x180201dcd  mov     rcx, cs:?IEVALUE_ActiveXFiltering_IsEnabled@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_ActiveXFiltering_IsEnabled
0x180201dd4  call    cs:__imp_IsPolicyEnabledValue
0x180201ddb  nop     dword ptr [rax+rax+00h]
0x180201de0  mov     r8d, r14d
0x180201de3  mov     edx, ebx
0x180201de5  test    eax, eax
0x180201de7  mov     rcx, rdi
0x180201dea  setz    r8b
0x180201dee  call    SHEnableMenuItem
0x180201df3  mov     rcx, rdi; hmenu
0x180201df6  call    _SHPrettyMenu
0x180201dfb  mov     rcx, [rbp+70h+var_20]
0x180201dff  xor     rcx, rsp; StackCookie
0x180201e02  call    __security_check_cookie
0x180201e07  lea     r11, [rsp+170h+var_10]
0x180201e0f  mov     rbx, [r11+30h]
0x180201e13  mov     rsi, [r11+38h]
0x180201e17  mov     rsp, r11
0x180201e1a  pop     r14
0x180201e1c  pop     rdi
0x180201e1d  pop     rbp
0x180201e1e  retn
```
