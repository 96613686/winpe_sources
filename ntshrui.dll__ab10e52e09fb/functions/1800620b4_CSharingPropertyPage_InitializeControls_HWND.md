# CSharingPropertyPage::_InitializeControls(HWND__ *)

- ea: `0x1800620b4`
- end: `0x180062420`
- name: `?_InitializeControls@CSharingPropertyPage@@IEAAXPEAUHWND__@@@Z`
- size: `876`
- prototype: `void __fastcall(CSharingPropertyPage *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180062788`
- `0x1800629cc`

## callees

- `0x18001c4a8`
- `0x1800254e0`
- `0x1800341c4`
- `0x180035248`
- `0x180060740`
- `0x180061094`
- `0x1800616e8`
- `0x1800619b4`
- `0x180061eec`
- `0x1800620b4`
- `0x180073598`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180062123`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006229c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800622ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180062123`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006229c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800622ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800623a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800623a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800621df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800621df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062324`
- `SHCORE!IsOS` at `0x18006234d`
- `SHCORE!IsOS` at `0x18006234d`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x1800621a8`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x1800621a8`
- `SHELL32!SHCreateItemFromParsingName` at `0x180062173`
- `SHELL32!SHCreateItemFromParsingName` at `0x180062173`
- `SHLWAPI!PathFindFileNameW` at `0x180062141`
- `SHLWAPI!PathFindFileNameW` at `0x180062141`
- `USER32!ShowWindow` at `0x1800623bd`
- `USER32!ShowWindow` at `0x1800623d6`
- `USER32!ShowWindow` at `0x1800623bd`
- `USER32!ShowWindow` at `0x1800623d6`
- `USER32!EnableWindow` at `0x180062239`
- `USER32!EnableWindow` at `0x180062239`
- `USER32!SetDlgItemTextW` at `0x180062152`
- `USER32!SetDlgItemTextW` at `0x1800622b5`
- `USER32!SetDlgItemTextW` at `0x1800622ca`
- `USER32!SetDlgItemTextW` at `0x180062306`
- `USER32!SetDlgItemTextW` at `0x180062319`
- `USER32!SetDlgItemTextW` at `0x180062397`
- `USER32!SetDlgItemTextW` at `0x180062152`
- `USER32!SetDlgItemTextW` at `0x1800622b5`
- `USER32!SetDlgItemTextW` at `0x1800622ca`
- `USER32!SetDlgItemTextW` at `0x180062306`
- `USER32!SetDlgItemTextW` at `0x180062319`
- `USER32!SetDlgItemTextW` at `0x180062397`
- `USER32!SetWindowTextW` at `0x180062137`
- `USER32!SetWindowTextW` at `0x180062137`
- `USER32!GetDlgItem` at `0x18006222e`
- `USER32!GetDlgItem` at `0x1800623b2`
- `USER32!GetDlgItem` at `0x1800623cb`
- `USER32!GetDlgItem` at `0x18006222e`
- `USER32!GetDlgItem` at `0x1800623b2`
- `USER32!GetDlgItem` at `0x1800623cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CSharingPropertyPage::_InitializeControls(LPCWSTR *this, HWND a2)
{
  const WCHAR *FileNameW; // rax
  HRESULT SharingInfo; // ebx
  BOOL v6; // ebx
  HWND DlgItem; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // ecx
  int v11; // eax
  __int64 v12; // rdx
  HWND v13; // rax
  HWND v14; // rax
  LPCWSTR lpString; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-C8h] BYREF
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v18; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v20[42]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String[104]; // [rsp+1B0h] [rbp+B0h] BYREF
  WCHAR Buffer[256]; // [rsp+280h] [rbp+180h] BYREF

  wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v20);
  v20[0] = &SharingWizardTelemetry::InitializeSharingPropertyPage::`vftable';
  SharingWizardTelemetry::InitializeSharingPropertyPage::StartActivity((SharingWizardTelemetry::InitializeSharingPropertyPage *)v20);
  if ( LoadStringW(g_hInstance, 0xC80u, Buffer, 256) )
    SetWindowTextW(a2, Buffer);
  FileNameW = PathFindFileNameW(this[2]);
  SetDlgItemTextW(a2, 1058, FileNameW);
  ppv[0] = 0;
  SharingInfo = SHCreateItemFromParsingName(this[2], 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, ppv);
  if ( SharingInfo >= 0 )
  {
    CSharingPropertyPage::_BeginSetFolderIcon((CSharingPropertyPage *)this, a2);
    v17 = 0;
    SharingInfo = SHCreateShellItemArrayFromShellItem(
                    (IShellItem *)ppv[0],
                    &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                    &v17);
    if ( SharingInfo >= 0 )
    {
      v18 = 0;
      SharingInfo = CoCreateInstance(
                      &CLSID_SharingConfigurationManager,
                      0,
                      1u,
                      &GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2,
                      &v18);
      if ( SharingInfo >= 0 )
      {
        v16 = 0;
        SharingInfo = (*(__int64 (__fastcall **)(LPVOID, void *, unsigned int *))(*(_QWORD *)v18 + 88LL))(
                        v18,
                        v17,
                        &v16);
        if ( SharingInfo >= 0 )
        {
          v6 = v16 != 3;
          DlgItem = GetDlgItem(a2, 1059);
          EnableWindow(DlgItem, v6);
          lpString = 0;
          SharingInfo = CSharingPropertyPage::_GetSharingInfo(v8, v17, 0, &lpString);
          if ( SharingInfo >= 0
            || v16 - 1 <= 1
            && (SharingInfo = CSharingPropertyPage::_GetSharingInfo(v9, v17, v16, &lpString), SharingInfo >= 0) )
          {
            if ( LoadStringW(g_hInstance, 0xC82u, String, 100) )
              SetDlgItemTextW(a2, 4407, String);
            SetDlgItemTextW(a2, 4406, lpString);
            CoTaskMemFree((LPVOID)lpString);
          }
          else
          {
            if ( LoadStringW(g_hInstance, 0xC83u, String, 100) )
            {
              SetDlgItemTextW(a2, 4407, String);
              SetDlgItemTextW(a2, 4406, String);
            }
            SharingInfo = 0;
          }
        }
      }
      ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v18);
    }
    ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v17);
    if ( SharingInfo >= 0 )
    {
      if ( IsOS(0x1Cu) )
      {
        v13 = GetDlgItem(a2, 1056);
        ShowWindow(v13, 0);
        v14 = GetDlgItem(a2, 1061);
        ShowWindow(v14, 0);
      }
      else
      {
        lpString = 0;
        v11 = IsGuestAccountEnabled(v10);
        v12 = 5102;
        if ( !v11 )
          v12 = 5103;
        SharingInfo = SHFormatResMessageArgAlloc(g_hInstance, v12, &lpString);
        if ( SharingInfo >= 0 )
        {
          SetDlgItemTextW(a2, 1061, lpString);
          LocalFree((HLOCAL)lpString);
        }
      }
    }
  }
  wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v20,
    (unsigned int)SharingInfo);
  ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(ppv);
  SharingWizardTelemetry::InitializeSharingPropertyPage::~InitializeSharingPropertyPage((SharingWizardTelemetry::InitializeSharingPropertyPage *)v20);
}

```

## disassembly

```asm
0x1800620b4  mov     [rsp-8+arg_10], rbx
0x1800620b9  push    rbp
0x1800620ba  push    rsi
0x1800620bb  push    rdi
0x1800620bc  lea     rbp, [rsp-390h]
0x1800620c4  sub     rsp, 490h
0x1800620cb  mov     rax, cs:__security_cookie
0x1800620d2  xor     rax, rsp
0x1800620d5  mov     [rbp+3A0h+var_20], rax
0x1800620dc  mov     rdi, rdx
0x1800620df  mov     rsi, rcx
0x1800620e2  lea     rdx, aInitializeshar; "InitializeSharingPropertyPage"
0x1800620e9  lea     rcx, [rsp+4A0h+var_440]; struct wil::details::IFailureCallback *
0x1800620ee  call    ??0?$ActivityBase@VSharingWizardLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800620f3  lea     rax, ??_7InitializeSharingPropertyPage@SharingWizardTelemetry@@6B@; const SharingWizardTelemetry::InitializeSharingPropertyPage::`vftable'
0x1800620fa  mov     [rsp+4A0h+var_440], rax
0x1800620ff  lea     rcx, [rsp+4A0h+var_440]; this
0x180062104  call    ?StartActivity@InitializeSharingPropertyPage@SharingWizardTelemetry@@QEAAXXZ; SharingWizardTelemetry::InitializeSharingPropertyPage::StartActivity(void)
0x180062109  nop
0x18006210a  mov     r9d, 100h; cchBufferMax
0x180062110  lea     r8, [rbp+3A0h+Buffer]; lpBuffer
0x180062117  mov     edx, 0C80h; uID
0x18006211c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180062123  call    cs:__imp_LoadStringW
0x180062129  test    eax, eax
0x18006212b  jz      short loc_18006213D
0x18006212d  lea     rdx, [rbp+3A0h+Buffer]; lpString
0x180062134  mov     rcx, rdi; hWnd
0x180062137  call    cs:__imp_SetWindowTextW
0x18006213d  mov     rcx, [rsi+10h]; pszPath
0x180062141  call    cs:__imp_PathFindFileNameW
0x180062147  mov     r8, rax; lpString
0x18006214a  mov     edx, 422h; nIDDlgItem
0x18006214f  mov     rcx, rdi; hDlg
0x180062152  call    cs:__imp_SetDlgItemTextW
0x180062158  mov     [rsp+4A0h+ppv], 0
0x180062161  lea     r9, [rsp+4A0h+ppv]; ppv
0x180062166  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18006216d  xor     edx, edx; pbc
0x18006216f  mov     rcx, [rsi+10h]; pszPath
0x180062173  call    cs:__imp_SHCreateItemFromParsingName
0x180062179  mov     ebx, eax
0x18006217b  test    eax, eax
0x18006217d  js      loc_1800623DC
0x180062183  mov     rdx, rdi; HWND
0x180062186  mov     rcx, rsi; this
0x180062189  call    ?_BeginSetFolderIcon@CSharingPropertyPage@@IEAAXPEAUHWND__@@@Z; CSharingPropertyPage::_BeginSetFolderIcon(HWND__ *)
0x18006218e  mov     [rsp+4A0h+var_460], 0
0x180062197  lea     r8, [rsp+4A0h+var_460]; ppv
0x18006219c  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x1800621a3  mov     rcx, [rsp+4A0h+ppv]; psi
0x1800621a8  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x1800621ae  mov     ebx, eax
0x1800621b0  test    eax, eax
0x1800621b2  js      loc_180062336
0x1800621b8  mov     [rsp+4A0h+var_458], 0
0x1800621c1  lea     rax, [rsp+4A0h+var_458]
0x1800621c6  mov     [rsp+4A0h+var_480], rax; ppv
0x1800621cb  lea     r9, _GUID_14aa4ab8_abe3_4a07_a290_1d5dccdd2fc2; riid
0x1800621d2  xor     edx, edx; pUnkOuter
0x1800621d4  lea     r8d, [rdx+1]; dwClsContext
0x1800621d8  lea     rcx, CLSID_SharingConfigurationManager; rclsid
0x1800621df  call    cs:__imp_CoCreateInstance
0x1800621e5  mov     ebx, eax
0x1800621e7  test    eax, eax
0x1800621e9  js      loc_18006232B
0x1800621ef  mov     [rsp+4A0h+var_468], 0
0x1800621f7  mov     rcx, [rsp+4A0h+var_458]
0x1800621fc  mov     rax, [rcx]
0x1800621ff  lea     r8, [rsp+4A0h+var_468]
0x180062204  mov     rdx, [rsp+4A0h+var_460]
0x180062209  mov     rax, [rax+58h]
0x18006220d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062212  mov     ebx, eax
0x180062214  test    eax, eax
0x180062216  js      loc_18006232B
0x18006221c  xor     ebx, ebx
0x18006221e  cmp     [rsp+4A0h+var_468], 3
0x180062223  setnz   bl
0x180062226  mov     edx, 423h; nIDDlgItem
0x18006222b  mov     rcx, rdi; hDlg
0x18006222e  call    cs:__imp_GetDlgItem
0x180062234  mov     rcx, rax; hWnd
0x180062237  mov     edx, ebx; bEnable
0x180062239  call    cs:__imp_EnableWindow
0x18006223f  mov     [rsp+4A0h+lpString], 0
0x180062248  lea     r9, [rsp+4A0h+lpString]
0x18006224d  xor     r8d, r8d
0x180062250  mov     rdx, [rsp+4A0h+var_460]
0x180062255  call    ?_GetSharingInfo@CSharingPropertyPage@@IEAAJPEAUIShellItemArray@@W4SHARE_MODE@@PEAPEAG@Z; CSharingPropertyPage::_GetSharingInfo(IShellItemArray *,SHARE_MODE,ushort * *)
0x18006225a  mov     ebx, eax
0x18006225c  test    eax, eax
0x18006225e  jns     short loc_1800622D4
0x180062260  mov     r8d, [rsp+4A0h+var_468]
0x180062265  lea     eax, [r8-1]
0x180062269  cmp     eax, 1
0x18006226c  ja      short loc_180062283
0x18006226e  lea     r9, [rsp+4A0h+lpString]
0x180062273  mov     rdx, [rsp+4A0h+var_460]
0x180062278  call    ?_GetSharingInfo@CSharingPropertyPage@@IEAAJPEAUIShellItemArray@@W4SHARE_MODE@@PEAPEAG@Z; CSharingPropertyPage::_GetSharingInfo(IShellItemArray *,SHARE_MODE,ushort * *)
0x18006227d  mov     ebx, eax
0x18006227f  test    eax, eax
0x180062281  jns     short loc_1800622D4
0x180062283  mov     r9d, 64h ; 'd'; cchBufferMax
0x180062289  lea     r8, [rbp+3A0h+String]; lpBuffer
0x180062290  mov     edx, 0C83h; uID
0x180062295  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006229c  call    cs:__imp_LoadStringW
0x1800622a2  test    eax, eax
0x1800622a4  jz      short loc_1800622D0
0x1800622a6  lea     r8, [rbp+3A0h+String]; lpString
0x1800622ad  mov     edx, 1137h; nIDDlgItem
0x1800622b2  mov     rcx, rdi; hDlg
0x1800622b5  call    cs:__imp_SetDlgItemTextW
0x1800622bb  lea     r8, [rbp+3A0h+String]; lpString
0x1800622c2  mov     edx, 1136h; nIDDlgItem
0x1800622c7  mov     rcx, rdi; hDlg
0x1800622ca  call    cs:__imp_SetDlgItemTextW
0x1800622d0  xor     ebx, ebx
0x1800622d2  jmp     short loc_18006232B
0x1800622d4  mov     r9d, 64h ; 'd'; cchBufferMax
0x1800622da  lea     r8, [rbp+3A0h+String]; lpBuffer
0x1800622e1  mov     edx, 0C82h; uID
0x1800622e6  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800622ed  call    cs:__imp_LoadStringW
0x1800622f3  test    eax, eax
0x1800622f5  jz      short loc_18006230C
0x1800622f7  lea     r8, [rbp+3A0h+String]; lpString
0x1800622fe  mov     edx, 1137h; nIDDlgItem
0x180062303  mov     rcx, rdi; hDlg
0x180062306  call    cs:__imp_SetDlgItemTextW
0x18006230c  mov     r8, [rsp+4A0h+lpString]; lpString
0x180062311  mov     edx, 1136h; nIDDlgItem
0x180062316  mov     rcx, rdi; hDlg
0x180062319  call    cs:__imp_SetDlgItemTextW
0x18006231f  mov     rcx, [rsp+4A0h+lpString]; pv
0x180062324  call    cs:__imp_CoTaskMemFree
0x18006232a  nop
0x18006232b  lea     rcx, [rsp+4A0h+var_458]
0x180062330  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180062335  nop
0x180062336  lea     rcx, [rsp+4A0h+var_460]
0x18006233b  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180062340  test    ebx, ebx
0x180062342  js      loc_1800623DC
0x180062348  mov     ecx, 1Ch; dwOS
0x18006234d  call    cs:__imp_IsOS
0x180062353  test    eax, eax
0x180062355  jnz     short loc_1800623AA
0x180062357  mov     [rsp+4A0h+lpString], 0
0x180062360  call    ?IsGuestAccountEnabled@@YAHK@Z; IsGuestAccountEnabled(ulong)
0x180062365  lea     r8, [rsp+4A0h+lpString]
0x18006236a  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180062371  test    eax, eax
0x180062373  mov     edx, 13EEh
0x180062378  jnz     short loc_18006237F
0x18006237a  mov     edx, 13EFh
0x18006237f  call    SHFormatResMessageArgAlloc
0x180062384  mov     ebx, eax
0x180062386  test    eax, eax
0x180062388  js      short loc_1800623DC
0x18006238a  mov     r8, [rsp+4A0h+lpString]; lpString
0x18006238f  mov     edx, 425h; nIDDlgItem
0x180062394  mov     rcx, rdi; hDlg
0x180062397  call    cs:__imp_SetDlgItemTextW
0x18006239d  mov     rcx, [rsp+4A0h+lpString]; hMem
0x1800623a2  call    cs:__imp_LocalFree
0x1800623a8  jmp     short loc_1800623DC
0x1800623aa  mov     edx, 420h; nIDDlgItem
0x1800623af  mov     rcx, rdi; hDlg
0x1800623b2  call    cs:__imp_GetDlgItem
0x1800623b8  mov     rcx, rax; hWnd
0x1800623bb  xor     edx, edx; nCmdShow
0x1800623bd  call    cs:__imp_ShowWindow
0x1800623c3  mov     edx, 425h; nIDDlgItem
0x1800623c8  mov     rcx, rdi; hDlg
0x1800623cb  call    cs:__imp_GetDlgItem
0x1800623d1  mov     rcx, rax; hWnd
0x1800623d4  xor     edx, edx; nCmdShow
0x1800623d6  call    cs:__imp_ShowWindow
0x1800623dc  mov     edx, ebx
0x1800623de  lea     rcx, [rsp+4A0h+var_440]
0x1800623e3  call    ?Stop@?$ActivityBase@VSharingWizardLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800623e8  nop
0x1800623e9  lea     rcx, [rsp+4A0h+ppv]
0x1800623ee  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x1800623f3  nop
0x1800623f4  lea     rcx, [rsp+4A0h+var_440]; this
0x1800623f9  call    ??1InitializeSharingPropertyPage@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::InitializeSharingPropertyPage::~InitializeSharingPropertyPage(void)
0x1800623fe  mov     rcx, [rbp+3A0h+var_20]
0x180062405  xor     rcx, rsp; StackCookie
0x180062408  call    __security_check_cookie
0x18006240d  mov     rbx, [rsp+4A0h+arg_10]
0x180062415  add     rsp, 490h
0x18006241c  pop     rdi
0x18006241d  pop     rsi
0x18006241e  pop     rbp
0x18006241f  retn
```
