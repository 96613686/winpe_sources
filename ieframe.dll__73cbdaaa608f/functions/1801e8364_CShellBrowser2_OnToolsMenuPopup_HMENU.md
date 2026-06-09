# CShellBrowser2::_OnToolsMenuPopup(HMENU__ *)

- ea: `0x1801e8364`
- end: `0x1801e878c`
- name: `?_OnToolsMenuPopup@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z`
- size: `1064`
- prototype: `void __fastcall(CShellBrowser2 *__hidden this, HMENU)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801eda80`

## callees

- `0x18000b9e0`
- `0x180015150`
- `0x18006f940`
- `0x180075598`
- `0x1800c16bc`
- `0x1801e58d4`
- `0x1801e8364`
- `0x1801e8794`
- `0x1801e88b8`
- `0x18026ad50`
- `0x1803eb9d0`
- `0x1803f65e8`
- `0x1804026f8`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801e8648`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1801e8648`
- `USER32!SetMenuItemInfoW` at `0x1801e868e`
- `USER32!SetMenuItemInfoW` at `0x1801e868e`
- `USER32!DeleteMenu` at `0x1801e839d`
- `USER32!DeleteMenu` at `0x1801e83b0`
- `USER32!DeleteMenu` at `0x1801e852b`
- `USER32!DeleteMenu` at `0x1801e86a1`
- `USER32!DeleteMenu` at `0x1801e86c3`
- `USER32!DeleteMenu` at `0x1801e86f1`
- `USER32!DeleteMenu` at `0x1801e839d`
- `USER32!DeleteMenu` at `0x1801e83b0`
- `USER32!DeleteMenu` at `0x1801e852b`
- `USER32!DeleteMenu` at `0x1801e86a1`
- `USER32!DeleteMenu` at `0x1801e86c3`
- `USER32!DeleteMenu` at `0x1801e86f1`
- `USER32!CheckMenuItem` at `0x1801e8484`
- `USER32!CheckMenuItem` at `0x1801e8507`
- `USER32!CheckMenuItem` at `0x1801e873a`
- `USER32!CheckMenuItem` at `0x1801e8484`
- `USER32!CheckMenuItem` at `0x1801e8507`
- `USER32!CheckMenuItem` at `0x1801e873a`
- `USER32!EnableMenuItem` at `0x1801e8450`
- `USER32!EnableMenuItem` at `0x1801e851a`
- `USER32!EnableMenuItem` at `0x1801e85fe`
- `USER32!EnableMenuItem` at `0x1801e8450`
- `USER32!EnableMenuItem` at `0x1801e851a`
- `USER32!EnableMenuItem` at `0x1801e85fe`
- `iertutil!__imp_IERegGetBool` at `0x1801e8430`
- `iertutil!__imp_IERegGetBool` at `0x1801e8430`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x1801e853b`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x1801e8747`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x1801e853b`
- `iertutil!__imp_IsPolicyEnabledValue` at `0x1801e8747`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801e83eb`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IUnknown_QueryService` at `0x1801e83eb`

## pseudocode

```c
void __fastcall CShellBrowser2::_OnToolsMenuPopup(CShellBrowser2 *this, HMENU a2)
{
  IUnknown *v4; // rcx
  bool IsLocationDnsErrorUrl; // al
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  UINT v9; // r8d
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
  EnableMenuItem(a2, 0xA133u, v16 != 0);
  IsLocationDnsErrorUrl = CShellBrowser2::_IsLocationDnsErrorUrl(this);
  SHEnableMenuItem(a2, 41266, IsLocationDnsErrorUrl);
  LODWORD(ppvOut) = 1;
  CheckMenuItem(a2, 0xA23Au, 0);
  v14 = 0;
  CLayerParticipant::LayerGetBool((CShellBrowser2 *)((char *)this + 232), &v14, 69722, 0);
  if ( v14 || (GetBOOL((__int64 *)SettingStore::IEVALUE_IEDevTools_Disabled[0], &ppvOut), (_DWORD)ppvOut) )
  {
    EnableMenuItem(a2, 0xA23Au, 1u);
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
  v9 = (int)InPrivateBrowsingAllowed() < 0;
  EnableMenuItem(a2, 0xA134u, v9);
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
0x1801e8364  mov     [rsp-8+arg_10], rbx
0x1801e8369  mov     [rsp-8+arg_18], rsi
0x1801e836e  push    rbp
0x1801e836f  push    rdi
0x1801e8370  push    r14
0x1801e8372  lea     rbp, [rsp-60h]
0x1801e8377  sub     rsp, 160h
0x1801e837e  mov     rax, cs:__security_cookie
0x1801e8385  xor     rax, rsp
0x1801e8388  mov     [rbp+70h+var_20], rax
0x1801e838c  mov     rdi, rdx
0x1801e838f  mov     rsi, rcx
0x1801e8392  mov     rcx, rdi; hMenu
0x1801e8395  xor     r8d, r8d; uFlags
0x1801e8398  mov     edx, 156h; uPosition
0x1801e839d  call    cs:__imp_DeleteMenu
0x1801e83a3  mov     ebx, 0A150h
0x1801e83a8  xor     r8d, r8d; uFlags
0x1801e83ab  mov     edx, ebx; uPosition
0x1801e83ad  mov     rcx, rdi; hMenu
0x1801e83b0  call    cs:__imp_DeleteMenu
0x1801e83b6  xor     r8d, r8d
0x1801e83b9  xor     edx, edx
0x1801e83bb  mov     ecx, 60000025h
0x1801e83c0  call    SHRestricted2W
0x1801e83c5  xor     r14d, r14d
0x1801e83c8  test    eax, eax
0x1801e83ca  jnz     short loc_1801E8421
0x1801e83cc  mov     rcx, [rsi+190h]; punk
0x1801e83d3  lea     r9, [rsp+170h+ppvOut]; ppvOut
0x1801e83d8  lea     r8, _GUID_b5ecdf5d_f3f9_4392_bac5_248961093fa2; riid
0x1801e83df  mov     [rsp+170h+ppvOut], r14
0x1801e83e4  lea     rdx, IID_INewWindowManagerCallback; guidService
0x1801e83eb  call    cs:__imp_IUnknown_QueryService
0x1801e83f1  test    eax, eax
0x1801e83f3  js      short loc_1801E8421
0x1801e83f5  mov     rcx, [rsp+170h+ppvOut]
0x1801e83fa  lea     r9d, [rbx-19h]
0x1801e83fe  mov     r8d, ebx
0x1801e8401  mov     rdx, rdi
0x1801e8404  mov     rax, [rcx]
0x1801e8407  mov     rax, [rax+30h]
0x1801e840b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e8410  mov     rcx, [rsp+170h+ppvOut]
0x1801e8415  mov     rax, [rcx]
0x1801e8418  mov     rax, [rax+10h]
0x1801e841c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e8421  lea     rdx, [rsp+170h+var_130]
0x1801e8426  mov     [rsp+170h+var_130], r14d
0x1801e842b  mov     ecx, 8
0x1801e8430  call    cs:__imp_IERegGetBool
0x1801e8436  mov     edx, 0A133h; uIDEnableItem
0x1801e843b  mov     rcx, rdi; hMenu
0x1801e843e  cmp     [rsp+170h+var_130], r14d
0x1801e8443  jz      short loc_1801E844D
0x1801e8445  mov     r8d, 1
0x1801e844b  jmp     short loc_1801E8450
0x1801e844d  xor     r8d, r8d; uEnable
0x1801e8450  call    cs:__imp_EnableMenuItem
0x1801e8456  mov     rcx, rsi; this
0x1801e8459  call    ?_IsLocationDnsErrorUrl@CShellBrowser2@@AEBA_NXZ; CShellBrowser2::_IsLocationDnsErrorUrl(void)
0x1801e845e  movzx   r8d, al
0x1801e8462  mov     edx, 0A132h
0x1801e8467  mov     rcx, rdi
0x1801e846a  call    SHEnableMenuItem
0x1801e846f  mov     ebx, 0A23Ah
0x1801e8474  mov     dword ptr [rsp+170h+ppvOut], 1
0x1801e847c  mov     edx, ebx; uIDCheckItem
0x1801e847e  xor     r8d, r8d; uCheck
0x1801e8481  mov     rcx, rdi; hMenu
0x1801e8484  call    cs:__imp_CheckMenuItem
0x1801e848a  lea     rcx, [rsi+0E8h]; this
0x1801e8491  mov     [rsp+170h+var_140], r14b
0x1801e8496  xor     r9d, r9d; int
0x1801e8499  lea     rdx, [rsp+170h+var_140]; bool *
0x1801e849e  mov     r8d, 1105Ah; int
0x1801e84a4  call    ?LayerGetBool@CLayerParticipant@@IEAAJPEA_NHH@Z; CLayerParticipant::LayerGetBool(bool *,int,int)
0x1801e84a9  cmp     [rsp+170h+var_140], r14b
0x1801e84ae  jnz     short loc_1801E850F
0x1801e84b0  mov     rcx, cs:?IEVALUE_IEDevTools_Disabled@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_IEDevTools_Disabled
0x1801e84b7  lea     rdx, [rsp+170h+ppvOut]
0x1801e84bc  call    GetBOOL
0x1801e84c1  cmp     dword ptr [rsp+170h+ppvOut], r14d
0x1801e84c6  jnz     short loc_1801E850F
0x1801e84c8  mov     rcx, [rsi+1AD8h]
0x1801e84cf  mov     eax, r14d
0x1801e84d2  mov     dword ptr [rsp+170h+ppvOut], eax
0x1801e84d6  test    rcx, rcx
0x1801e84d9  jz      short loc_1801E84F0
0x1801e84db  mov     rax, [rcx]
0x1801e84de  lea     rdx, [rsp+170h+ppvOut]
0x1801e84e3  mov     rax, [rax+38h]
0x1801e84e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e84ec  mov     eax, dword ptr [rsp+170h+ppvOut]
0x1801e84f0  cmp     [rsi+1964h], ebx
0x1801e84f6  jz      short loc_1801E84FC
0x1801e84f8  test    eax, eax
0x1801e84fa  jz      short loc_1801E8520
0x1801e84fc  mov     r8d, 8; uCheck
0x1801e8502  mov     edx, ebx; uIDCheckItem
0x1801e8504  mov     rcx, rdi; hMenu
0x1801e8507  call    cs:__imp_CheckMenuItem
0x1801e850d  jmp     short loc_1801E8520
0x1801e850f  mov     r8d, 1; uEnable
0x1801e8515  mov     edx, ebx; uIDEnableItem
0x1801e8517  mov     rcx, rdi; hMenu
0x1801e851a  call    cs:__imp_EnableMenuItem
0x1801e8520  xor     r8d, r8d; uFlags
0x1801e8523  mov     edx, 0A1C7h; uPosition
0x1801e8528  mov     rcx, rdi; hMenu
0x1801e852b  call    cs:__imp_DeleteMenu
0x1801e8531  mov     rcx, cs:?IEVALUE_Recovery_NoReopenLastSession@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_Recovery_NoReopenLastSession
0x1801e8538  mov     ebx, r14d
0x1801e853b  call    cs:__imp_IsPolicyEnabledValue
0x1801e8541  test    eax, eax
0x1801e8543  jnz     loc_1801E85D2
0x1801e8549  lea     rcx, [rsi+20h]
0x1801e854d  mov     [rsp+170h+var_120], r14
0x1801e8552  mov     rax, [rcx]
0x1801e8555  lea     r9, [rsp+170h+var_120]
0x1801e855a  lea     r8, _GUID_feefb420_9399_492d_969c_51af6dc38fb1
0x1801e8561  lea     rdx, SID_STabWindowManager
0x1801e8568  mov     rax, [rax+18h]
0x1801e856c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e8571  test    eax, eax
0x1801e8573  js      short loc_1801E85C8
0x1801e8575  mov     rcx, [rsp+170h+var_120]
0x1801e857a  lea     rdx, [rsp+170h+var_128]
0x1801e857f  mov     [rsp+170h+var_128], r14
0x1801e8584  mov     dword ptr [rsp+170h+ppvOut], r14d
0x1801e8589  mov     rax, [rcx]
0x1801e858c  mov     rax, [rax+0C0h]
0x1801e8593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e8598  test    eax, eax
0x1801e859a  js      short loc_1801E85BE
0x1801e859c  mov     rcx, [rsp+170h+var_128]
0x1801e85a1  lea     rdx, [rsp+170h+ppvOut]
0x1801e85a6  mov     rax, [rcx]
0x1801e85a9  mov     rax, [rax+20h]
0x1801e85ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e85b2  test    eax, eax
0x1801e85b4  js      short loc_1801E85BE
0x1801e85b6  cmp     dword ptr [rsp+170h+ppvOut], r14d
0x1801e85bb  setnbe  bl
0x1801e85be  lea     rcx, [rsp+170h+var_128]; void *
0x1801e85c3  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1801e85c8  lea     rcx, [rsp+170h+var_120]; void *
0x1801e85cd  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1801e85d2  mov     r8d, ebx
0x1801e85d5  mov     edx, 0A136h
0x1801e85da  mov     rcx, rdi
0x1801e85dd  call    SHEnableMenuItem
0x1801e85e2  call    ?InPrivateBrowsingAllowed@@YAJXZ; InPrivateBrowsingAllowed(void)
0x1801e85e7  mov     edx, 0A134h; uIDEnableItem
0x1801e85ec  mov     rcx, rdi; hMenu
0x1801e85ef  test    eax, eax
0x1801e85f1  js      short loc_1801E85F8
0x1801e85f3  xor     r8d, r8d
0x1801e85f6  jmp     short loc_1801E85FE
0x1801e85f8  mov     r8d, 1; uEnable
0x1801e85fe  call    cs:__imp_EnableMenuItem
0x1801e8604  mov     rcx, cs:?IEVALUE_PrivacIE_DisableInPrivateBlocking@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_PrivacIE_DisableInPrivateBlocking
0x1801e860b  lea     rdx, [rsp+170h+ppvOut]
0x1801e8610  mov     dword ptr [rsp+170h+ppvOut], r14d
0x1801e8615  call    GetBOOL
0x1801e861a  test    eax, eax
0x1801e861c  js      short loc_1801E8625
0x1801e861e  cmp     dword ptr [rsp+170h+ppvOut], r14d
0x1801e8623  jnz     short loc_1801E8696
0x1801e8625  call    ?GetPrivacIESettingsMode@@YAKXZ; GetPrivacIESettingsMode(void)
0x1801e862a  mov     rcx, cs:g_hinstMUI; hInstance
0x1801e8631  lea     r8, [rbp+70h+Buffer]; lpBuffer
0x1801e8635  and     eax, 4
0x1801e8638  mov     r9d, 50h ; 'P'; cchBufferMax
0x1801e863e  or      eax, 119C8h
0x1801e8643  shr     eax, 2
0x1801e8646  mov     edx, eax; uID
0x1801e8648  call    cs:__imp_LoadStringW
0x1801e864e  xor     edx, edx; Val
0x1801e8650  lea     rcx, [rsp+170h+mii]; void *
0x1801e8655  mov     ebx, eax
0x1801e8657  lea     r8d, [rdx+50h]; Size
0x1801e865b  call    memset_0
0x1801e8660  cmp     ebx, 1
0x1801e8663  jbe     short loc_1801E8696
0x1801e8665  lea     rax, [rbp+70h+Buffer]
0x1801e8669  mov     [rsp+170h+mii.cbSize], 50h ; 'P'
0x1801e8671  lea     r9, [rsp+170h+mii]; lpmii
0x1801e8676  mov     [rbp+70h+mii.dwTypeData], rax
0x1801e867a  xor     r8d, r8d; fByPositon
0x1801e867d  mov     qword ptr [rsp+170h+mii.fMask], 10h
0x1801e8686  mov     edx, 0A1CEh; item
0x1801e868b  mov     rcx, rdi; hmenu
0x1801e868e  call    cs:__imp_SetMenuItemInfoW
0x1801e8694  jmp     short loc_1801E86A7
0x1801e8696  xor     r8d, r8d; uFlags
0x1801e8699  mov     edx, 0A1CEh; uPosition
0x1801e869e  mov     rcx, rdi; hMenu
0x1801e86a1  call    cs:__imp_DeleteMenu
0x1801e86a7  mov     edx, 3; unsigned __int16
0x1801e86ac  lea     ecx, [rdx+3]; unsigned __int16
0x1801e86af  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1801e86b4  test    al, al
0x1801e86b6  jnz     short loc_1801E86C9
0x1801e86b8  xor     r8d, r8d; uFlags
0x1801e86bb  mov     edx, 0A137h; uPosition
0x1801e86c0  mov     rcx, rdi; hMenu
0x1801e86c3  call    cs:__imp_DeleteMenu
0x1801e86c9  mov     rcx, cs:?IEVALUE_ReportSiteProblems_NoReportSiteProblems@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_ReportSiteProblems_NoReportSiteProblems
0x1801e86d0  lea     rdx, [rsp+170h+ppvOut]
0x1801e86d5  mov     dword ptr [rsp+170h+ppvOut], r14d
0x1801e86da  call    GetBOOL
0x1801e86df  cmp     dword ptr [rsp+170h+ppvOut], r14d
0x1801e86e4  jz      short loc_1801E86F7
0x1801e86e6  xor     r8d, r8d; uFlags
0x1801e86e9  mov     edx, 0A160h; uPosition
0x1801e86ee  mov     rcx, rdi; hMenu
0x1801e86f1  call    cs:__imp_DeleteMenu
0x1801e86f7  mov     rdx, rdi; HMENU
0x1801e86fa  mov     rcx, rsi; this
0x1801e86fd  call    ?_OnToolsMenuPopup_AddToStart@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z; CShellBrowser2::_OnToolsMenuPopup_AddToStart(HMENU__ *)
0x1801e8702  mov     rdx, rdi; HMENU
0x1801e8705  mov     rcx, rsi; this
0x1801e8708  call    ?_OnToolsMenuPopup_EnterpriseMode@CShellBrowser2@@AEAAXPEAUHMENU__@@@Z; CShellBrowser2::_OnToolsMenuPopup_EnterpriseMode(HMENU__ *)
0x1801e870d  mov     rcx, cs:?IEVALUE_ActiveXFiltering_IsEnabled@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_ActiveXFiltering_IsEnabled
0x1801e8714  lea     rdx, [rsp+170h+ppvOut]
0x1801e8719  mov     dword ptr [rsp+170h+ppvOut], r14d
0x1801e871e  call    GetBOOL
0x1801e8723  mov     eax, dword ptr [rsp+170h+ppvOut]
0x1801e8727  mov     ebx, 0A1CFh
0x1801e872c  neg     eax
0x1801e872e  mov     edx, ebx; uIDCheckItem
0x1801e8730  mov     rcx, rdi; hMenu
0x1801e8733  sbb     r8d, r8d
0x1801e8736  and     r8d, 8; uCheck
0x1801e873a  call    cs:__imp_CheckMenuItem
0x1801e8740  mov     rcx, cs:?IEVALUE_ActiveXFiltering_IsEnabled@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_ActiveXFiltering_IsEnabled
0x1801e8747  call    cs:__imp_IsPolicyEnabledValue
0x1801e874d  mov     r8d, r14d
0x1801e8750  mov     edx, ebx
0x1801e8752  test    eax, eax
0x1801e8754  mov     rcx, rdi
0x1801e8757  setz    r8b
0x1801e875b  call    SHEnableMenuItem
0x1801e8760  mov     rcx, rdi; hmenu
0x1801e8763  call    _SHPrettyMenu
0x1801e8768  mov     rcx, [rbp+70h+var_20]
0x1801e876c  xor     rcx, rsp; StackCookie
0x1801e876f  call    __security_check_cookie
0x1801e8774  lea     r11, [rsp+170h+var_10]
0x1801e877c  mov     rbx, [r11+30h]
0x1801e8780  mov     rsi, [r11+38h]
0x1801e8784  mov     rsp, r11
0x1801e8787  pop     r14
0x1801e8789  pop     rdi
0x1801e878a  pop     rbp
0x1801e878b  retn
```
