# MMC21ADDREMOVEUI::CSnapinMainPage::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x1800b7e0c`
- end: `0x1800b8481`
- name: `?OnInitDialog@CSnapinMainPage@MMC21ADDREMOVEUI@@QEAA_JI_K_JAEAH@Z`
- size: `1653`
- prototype: `__int64 __fastcall(MMC21ADDREMOVEUI::CSnapinMainPage *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b93f0`

## callees

- `0x180004998`
- `0x1800074d0`
- `0x180057074`
- `0x18006ec08`
- `0x1800711a4`
- `0x1800743b4`
- `0x18007b95c`
- `0x18007b990`
- `0x180082998`
- `0x180082c78`
- `0x1800b2984`
- `0x1800b3a18`
- `0x1800b3e3c`
- `0x1800b499c`
- `0x1800b4b5c`
- `0x1800b504c`
- `0x1800b7e0c`
- `0x1800bbad4`
- `0x1800bbc64`
- `0x1800bef50`
- `0x180134540`
- `0x18013f010`

## import_xrefs

- `mmcbase!?LoadDynamicLayoutResource@DialogBoxDpiTracker@@QEAAXPEAUHINSTANCE__@@PEAUHRSRC__@@@Z` at `0x1800b83c9`
- `mmcbase!?LoadDynamicLayoutResource@DialogBoxDpiTracker@@QEAAXPEAUHINSTANCE__@@PEAUHRSRC__@@@Z` at `0x1800b83c9`
- `mmcbase!?SetModalHWND@SC@mmcerror@@SAPEAUHWND__@@PEAU3@@Z` at `0x1800b7f51`
- `mmcbase!?SetModalHWND@SC@mmcerror@@SAPEAUHWND__@@PEAU3@@Z` at `0x1800b7f51`
- `mmcbase!GetStringModule` at `0x1800b81b8`
- `mmcbase!GetStringModule` at `0x1800b827f`
- `mmcbase!GetStringModule` at `0x1800b81b8`
- `mmcbase!GetStringModule` at `0x1800b827f`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800b839b`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800b83b1`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800b839b`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800b83b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b8381`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b8381`
- `USER32!GetDpiForWindow` at `0x1800b8356`
- `USER32!GetDpiForWindow` at `0x1800b8356`
- `USER32!GetSystemMetrics` at `0x1800b80b5`
- `USER32!GetSystemMetrics` at `0x1800b81a8`
- `USER32!GetSystemMetrics` at `0x1800b80b5`
- `USER32!GetSystemMetrics` at `0x1800b81a8`
- `USER32!GetClientRect` at `0x1800b808a`
- `USER32!GetClientRect` at `0x1800b817f`
- `USER32!GetClientRect` at `0x1800b808a`
- `USER32!GetClientRect` at `0x1800b817f`
- `USER32!EndDialog` at `0x1800b8436`
- `USER32!EndDialog` at `0x1800b8436`
- `USER32!SendMessageW` at `0x1800b80dd`
- `USER32!SendMessageW` at `0x1800b8162`
- `USER32!SendMessageW` at `0x1800b8193`
- `USER32!SendMessageW` at `0x1800b824a`
- `USER32!SendMessageW` at `0x1800b82f0`
- `USER32!SendMessageW` at `0x1800b80dd`
- `USER32!SendMessageW` at `0x1800b8162`
- `USER32!SendMessageW` at `0x1800b8193`
- `USER32!SendMessageW` at `0x1800b824a`
- `USER32!SendMessageW` at `0x1800b82f0`
- `USER32!GetDlgItem` at `0x1800b7ea2`
- `USER32!GetDlgItem` at `0x1800b7f0d`
- `USER32!GetDlgItem` at `0x1800b7fe9`
- `USER32!GetDlgItem` at `0x1800b7fff`
- `USER32!GetDlgItem` at `0x1800b8011`
- `USER32!GetDlgItem` at `0x1800b7ea2`
- `USER32!GetDlgItem` at `0x1800b7f0d`
- `USER32!GetDlgItem` at `0x1800b7fe9`
- `USER32!GetDlgItem` at `0x1800b7fff`
- `USER32!GetDlgItem` at `0x1800b8011`
- `ole32!CoCreateInstance` at `0x1800b7e65`
- `ole32!CoCreateInstance` at `0x1800b7e65`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MMC21ADDREMOVEUI::CSnapinMainPage::OnInitDialog(MMC21ADDREMOVEUI::CSnapinMainPage *this)
{
  char *v2; // rsi
  __int64 v3; // rdi
  void (__fastcall *v4)(__int64, HWND, __int64, _QWORD, GUID *, GUID *); // rbx
  HWND DlgItem; // rax
  GUID v6; // xmm8
  __int64 v7; // rdi
  void (__fastcall *v8)(__int64, HWND, __int64, _QWORD, GUID *, GUID *); // rbx
  HWND v9; // rax
  unsigned int v10; // edx
  DialogBoxDpiTracker *v11; // rcx
  DialogBoxDpiTracker *v12; // rax
  DialogBoxDpiTracker *v13; // rax
  HWND *v14; // rsi
  HWND *v15; // rdi
  int v16; // ebx
  int v17; // ebx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  HINSTANCE StringModule; // rax
  int StringW; // eax
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  HINSTANCE v26; // rax
  int v27; // eax
  HMODULE ModuleHandleW; // rbx
  HRSRC ResourceW; // rax
  unsigned int v30; // edx
  DialogBoxDpiTracker *v31; // rcx
  GUID v33; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h]
  int v35; // [rsp+58h] [rbp-A8h]
  GUID v36; // [rsp+60h] [rbp-A0h] BYREF
  LPARAM lParam[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v38; // [rsp+90h] [rbp-70h]
  __int128 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  _BYTE v41[80]; // [rsp+C0h] [rbp-40h] BYREF
  struct tagRECT Rect; // [rsp+110h] [rbp+10h] BYREF

  v2 = (char *)this + 176;
  CoCreateInstance(&CLSID_AccPropServices, 0, 0x15u, &IID_IAccPropServices, (LPVOID *)this + 22);
  v36 = 0;
  LOWORD(v36.Data1) = 3;
  *(_DWORD *)v36.Data4 = 2;
  v3 = *(_QWORD *)v2;
  v4 = *(void (__fastcall **)(__int64, HWND, __int64, _QWORD, GUID *, GUID *))(**(_QWORD **)v2 + 48LL);
  DlgItem = GetDlgItem(*((HWND *)this + 1), 4008);
  v6 = v36;
  v33 = v36;
  v34 = 0;
  v36 = LiveSetting_Property_GUID;
  v4(v3, DlgItem, 4294967292LL, 0, &v36, &v33);
  v7 = *(_QWORD *)v2;
  v8 = *(void (__fastcall **)(__int64, HWND, __int64, _QWORD, GUID *, GUID *))(**(_QWORD **)v2 + 48LL);
  v9 = GetDlgItem(*((HWND *)this + 1), 4174);
  v33 = v6;
  v34 = 0;
  v36 = LiveSetting_Property_GUID;
  v8(v7, v9, 4294967292LL, 0, &v36, &v33);
  mmcerror::SC::SetModalHWND(*((HWND *)this + 1));
  Rect = 0;
  *(_OWORD *)lParam = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  *(_QWORD *)&v33.Data1 = &CStr::`vftable';
  *(_QWORD *)v33.Data4 = &CStr::s_rgwchEmptyStringBuffer;
  v34 = 0;
  v35 = 0;
  v11 = (DialogBoxDpiTracker *)*((_QWORD *)this + 21);
  if ( v11 )
  {
    DialogBoxDpiTracker::`scalar deleting destructor'(v11, v10);
    *((_QWORD *)this + 21) = 0;
  }
  v12 = (DialogBoxDpiTracker *)operator new(0x20u);
  *(_QWORD *)&v36.Data1 = v12;
  if ( v12 )
    v13 = DialogBoxDpiTracker::DialogBoxDpiTracker(v12, *((HWND *)this + 1));
  else
    v13 = 0;
  *((_QWORD *)this + 21) = v13;
  v14 = (HWND *)((char *)this + 64);
  *((_QWORD *)this + 8) = GetDlgItem(*((HWND *)this + 1), 4175);
  v15 = (HWND *)((char *)this + 72);
  *((_QWORD *)this + 9) = GetDlgItem(*((HWND *)this + 1), 4173);
  *((_QWORD *)this + 10) = GetDlgItem(*((HWND *)this + 1), 4180);
  WTL::CListViewCtrlT<ATL::CWindow>::SetImageList(
    (char *)this + 64,
    &v36,
    *(_QWORD *)(*((_QWORD *)this + 7) + 248LL),
    1);
  WTL::CListViewCtrlT<ATL::CWindow>::SetImageList(
    (char *)this + 72,
    &v36,
    *(_QWORD *)(*((_QWORD *)this + 7) + 248LL),
    1);
  CComboBoxEx2::SetImageList((char *)this + 80, &v36, *(_QWORD *)(*((_QWORD *)this + 7) + 248LL));
  MMC21ADDREMOVEUI::CSnapinMainPage::AddSnapinNodesToComboBox(this, *((_QWORD *)this + 7) + 200LL);
  GetClientRect(*((HWND *)this + 8), &Rect);
  *(_OWORD *)lParam = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  LODWORD(lParam[0]) = 10;
  v16 = Rect.right - Rect.left;
  v17 = v16 - GetSystemMetrics(2);
  if ( v17 <= 0 )
    v17 = 1;
  LODWORD(lParam[1]) = v17;
  HIDWORD(v38) = 0;
  if ( (unsigned int)SendMessageW(*v14, 0x1061u, 0, (LPARAM)lParam) == -1 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_45;
    v19 = 69;
    goto LABEL_44;
  }
  v20 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 7) + 200LL) + 16LL);
  *((_QWORD *)this + 11) = v20;
  if ( !v20 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_45;
    v19 = 70;
LABEL_44:
    WPP_SF_(*(_QWORD *)(v18 + 16), v19, WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids);
    goto LABEL_45;
  }
  MMC21ADDREMOVEUI::CSnapinMainPage::DisplayCurrentSnapinList(this);
  MMC21ADDREMOVEUI::CSnapinMainPage::SelectParentNodeItem(this, *((struct MMC21ADDREMOVEUI::CManagerNode **)this + 11));
  MMC21ADDREMOVEUI::CSnapinMainPage::SetupChildNode(this, 0);
  SendMessageW(*v14, 0x101Eu, 0, 0xFFFF);
  WTL::CListViewCtrlT<ATL::CWindow>::SetItemState((char *)this + 64, 0, 2, 2);
  GetClientRect(*v15, &Rect);
  if ( (int)SendMessageW(*v15, 0x1028u, 0, 0) < *(_DWORD *)(*((_QWORD *)this + 7) + 268LL) )
    Rect.right -= GetSystemMetrics(2);
  LODWORD(lParam[0]) = 14;
  StringModule = GetStringModule();
  StringW = CStr::LoadStringW((CStr *)&v33, StringModule, 0x36BDu);
  v23 = (unsigned int)StringW;
  if ( StringW < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_45;
    v25 = 71;
    goto LABEL_19;
  }
  *(_QWORD *)&v38 = *(_QWORD *)v33.Data4;
  LODWORD(lParam[1]) = 3 * Rect.right / 5;
  HIDWORD(v38) = 0;
  if ( (unsigned int)SendMessageW(*v15, 0x1061u, 0, (LPARAM)lParam) == -1 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_45;
    v19 = 72;
    goto LABEL_44;
  }
  v26 = GetStringModule();
  v27 = CStr::LoadStringW((CStr *)&v33, v26, 0x36C1u);
  v23 = (unsigned int)v27;
  if ( v27 < 0 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      goto LABEL_45;
    v25 = 73;
LABEL_19:
    WPP_SF_d(*(_QWORD *)(v24 + 16), v25, WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids, v23);
LABEL_45:
    EndDialog(*((HWND *)this + 1), -1);
    goto LABEL_46;
  }
  *(_QWORD *)&v38 = *(_QWORD *)v33.Data4;
  LODWORD(lParam[1]) = Rect.right - LODWORD(lParam[1]);
  HIDWORD(v38) = 1;
  if ( (unsigned int)SendMessageW(*v15, 0x1061u, 1u, (LPARAM)lParam) == -1 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 74, WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids);
  }
  else
  {
    *((_DWORD *)this + 30) = -1;
    MMC21ADDREMOVEUI::CSnapinMainPage::BuildSnapinList(this);
    if ( *((_DWORD *)this + 40) )
      MMC21ADDREMOVEUI::CSnapinMainPage::ChangeConfigurationMode(this);
    MMC21ADDREMOVEUI::CSnapinMainPage::lastDpi = GetDpiForWindow(*((_QWORD *)this + 1));
    MMC21ADDREMOVEUI::CSnapinMainPage::lfTextOrig.lfHeight = UpdateChildWindowsForDpi(
                                                               *((HWND *)this + 1),
                                                               MMC21ADDREMOVEUI::CSnapinMainPage::lastDpi,
                                                               &MMC21ADDREMOVEUI::CSnapinMainPage::lfTextOrig);
    ModuleHandleW = GetModuleHandleW(L"mmc.exe");
    ResourceW = FindResourceW(ModuleHandleW, (LPCWSTR)0x3A99, L"AFX_DIALOG_LAYOUT");
    if ( !ResourceW )
      ResourceW = FindResourceW(0, (LPCWSTR)0x3A99, L"AFX_DIALOG_LAYOUT");
    v31 = (DialogBoxDpiTracker *)*((_QWORD *)this + 21);
    if ( ResourceW )
    {
      DialogBoxDpiTracker::LoadDynamicLayoutResource(v31, ModuleHandleW, ResourceW);
      MMC21ADDREMOVEUI::CSnapinManagerDpiTracker::CSnapinManagerDpiTracker(
        (MMC21ADDREMOVEUI::CSnapinManagerDpiTracker *)v41,
        *((HWND *)this + 1));
      MMC21ADDREMOVEUI::CSnapinManagerDpiTracker::AdjustWindowSize(
        (MMC21ADDREMOVEUI::CSnapinManagerDpiTracker *)v41,
        &MMC21ADDREMOVEUI::CSnapinMainPage::lfTextOrig);
    }
    else
    {
      if ( v31 )
        DialogBoxDpiTracker::`scalar deleting destructor'(v31, v30);
      *((_QWORD *)this + 21) = 0;
    }
  }
LABEL_46:
  *(_QWORD *)&v33.Data1 = &CStr::`vftable';
  CStr::Empty((CStr *)&v33);
  return 0;
}

```

## disassembly

```asm
0x1800b7e0c  mov     rax, rsp
0x1800b7e0f  push    rbp
0x1800b7e10  push    rbx
0x1800b7e11  push    rsi
0x1800b7e12  push    rdi
0x1800b7e13  push    r12
0x1800b7e15  push    r13
0x1800b7e17  push    r14
0x1800b7e19  push    r15
0x1800b7e1b  lea     rbp, [rsp-68h]
0x1800b7e20  sub     rsp, 168h
0x1800b7e27  movaps  xmmword ptr [rax-58h], xmm6
0x1800b7e2b  movaps  xmmword ptr [rax-68h], xmm7
0x1800b7e2f  movaps  xmmword ptr [rax-78h], xmm8
0x1800b7e34  mov     rax, cs:__security_cookie
0x1800b7e3b  xor     rax, rsp
0x1800b7e3e  mov     [rbp+0A0h+var_80], rax
0x1800b7e42  mov     r14, rcx
0x1800b7e45  lea     rsi, [rcx+0B0h]
0x1800b7e4c  mov     [rsp+1A0h+ppv], rsi; ppv
0x1800b7e51  lea     r9, IID_IAccPropServices; riid
0x1800b7e58  xor     edx, edx; pUnkOuter
0x1800b7e5a  lea     r8d, [rdx+15h]; dwClsContext
0x1800b7e5e  lea     rcx, CLSID_AccPropServices; rclsid
0x1800b7e65  call    cs:__imp_CoCreateInstance
0x1800b7e6b  xorps   xmm0, xmm0
0x1800b7e6e  xor     r15d, r15d
0x1800b7e71  movups  xmmword ptr [rsp+1A0h+var_140.Data1], xmm0
0x1800b7e76  lea     eax, [r15+3]
0x1800b7e7a  mov     word ptr [rsp+1A0h+var_140.Data1], ax
0x1800b7e7f  lea     r12d, [r15+2]
0x1800b7e83  mov     dword ptr [rsp+1A0h+var_140.Data4], r12d
0x1800b7e88  mov     rdi, [rsi]
0x1800b7e8b  mov     rax, [rdi]
0x1800b7e8e  mov     rbx, [rax+30h]
0x1800b7e92  movups  xmm6, xmmword ptr cs:LiveSetting_Property_GUID.Data1
0x1800b7e99  mov     edx, 0FA8h; nIDDlgItem
0x1800b7e9e  mov     rcx, [r14+8]; hDlg
0x1800b7ea2  call    cs:__imp_GetDlgItem
0x1800b7ea8  movups  xmm8, xmmword ptr [rsp+1A0h+var_140.Data1]
0x1800b7eae  movaps  [rsp+1A0h+var_160], xmm8
0x1800b7eb4  movq    xmm7, r15
0x1800b7eb9  movsd   [rsp+1A0h+var_150], xmm7
0x1800b7ebf  movdqu  xmmword ptr [rsp+1A0h+var_140.Data1], xmm6
0x1800b7ec5  lea     rcx, [rsp+1A0h+var_160]
0x1800b7eca  mov     [rsp+1A0h+var_178], rcx
0x1800b7ecf  lea     rcx, [rsp+1A0h+var_140]
0x1800b7ed4  mov     [rsp+1A0h+ppv], rcx
0x1800b7ed9  xor     r9d, r9d
0x1800b7edc  mov     r15d, 0FFFFFFFCh
0x1800b7ee2  mov     r8d, r15d
0x1800b7ee5  mov     rdx, rax
0x1800b7ee8  mov     rcx, rdi
0x1800b7eeb  mov     rax, rbx
0x1800b7eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7ef3  mov     rdi, [rsi]
0x1800b7ef6  mov     rax, [rdi]
0x1800b7ef9  mov     rbx, [rax+30h]
0x1800b7efd  movups  xmm6, xmmword ptr cs:LiveSetting_Property_GUID.Data1
0x1800b7f04  mov     edx, 104Eh; nIDDlgItem
0x1800b7f09  mov     rcx, [r14+8]; hDlg
0x1800b7f0d  call    cs:__imp_GetDlgItem
0x1800b7f13  movaps  [rsp+1A0h+var_160], xmm8
0x1800b7f19  movsd   [rsp+1A0h+var_150], xmm7
0x1800b7f1f  movdqu  xmmword ptr [rsp+1A0h+var_140.Data1], xmm6
0x1800b7f25  lea     rcx, [rsp+1A0h+var_160]
0x1800b7f2a  mov     [rsp+1A0h+var_178], rcx
0x1800b7f2f  lea     rcx, [rsp+1A0h+var_140]
0x1800b7f34  mov     [rsp+1A0h+ppv], rcx
0x1800b7f39  xor     r9d, r9d
0x1800b7f3c  mov     r8d, r15d
0x1800b7f3f  mov     rdx, rax
0x1800b7f42  mov     rcx, rdi
0x1800b7f45  mov     rax, rbx
0x1800b7f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7f4d  mov     rcx, [r14+8]
0x1800b7f51  call    cs:__imp_?SetModalHWND@SC@mmcerror@@SAPEAUHWND__@@PEAU3@@Z; mmcerror::SC::SetModalHWND(HWND__ *)
0x1800b7f57  xorps   xmm0, xmm0
0x1800b7f5a  movups  xmmword ptr [rbp+0A0h+Rect.left], xmm0
0x1800b7f5e  xorps   xmm1, xmm1
0x1800b7f61  xor     eax, eax
0x1800b7f63  movups  xmmword ptr [rbp+0A0h+lParam], xmm1
0x1800b7f67  movups  [rbp+0A0h+var_110], xmm1
0x1800b7f6b  movups  [rbp+0A0h+var_100], xmm1
0x1800b7f6f  mov     [rbp+0A0h+var_F0], rax
0x1800b7f73  lea     r13, ??_7CStr@@6B@; const CStr::`vftable'
0x1800b7f7a  mov     qword ptr [rsp+1A0h+var_160], r13
0x1800b7f7f  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x1800b7f86  mov     qword ptr [rsp+1A0h+var_160+8], rax
0x1800b7f8b  xor     r15d, r15d
0x1800b7f8e  mov     [rsp+1A0h+var_150], r15
0x1800b7f93  mov     [rsp+1A0h+var_148], r15d
0x1800b7f98  mov     rcx, [r14+0A8h]; this
0x1800b7f9f  test    rcx, rcx
0x1800b7fa2  jz      short loc_1800B7FB0
0x1800b7fa4  call    ??_GDialogBoxDpiTracker@@QEAAPEAXI@Z; DialogBoxDpiTracker::`scalar deleting destructor'(uint)
0x1800b7fa9  mov     [r14+0A8h], r15
0x1800b7fb0  mov     ecx, 20h ; ' '; Size
0x1800b7fb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b7fba  mov     qword ptr [rsp+1A0h+var_140.Data1], rax
0x1800b7fbf  test    rax, rax
0x1800b7fc2  jz      short loc_1800B7FD2
0x1800b7fc4  mov     rdx, [r14+8]; HWND
0x1800b7fc8  mov     rcx, rax; this
0x1800b7fcb  call    ??0DialogBoxDpiTracker@@QEAA@PEAUHWND__@@@Z; DialogBoxDpiTracker::DialogBoxDpiTracker(HWND__ *)
0x1800b7fd0  jmp     short loc_1800B7FD5
0x1800b7fd2  mov     rax, r15
0x1800b7fd5  mov     [r14+0A8h], rax
0x1800b7fdc  lea     rsi, [r14+40h]
0x1800b7fe0  mov     edx, 104Fh; nIDDlgItem
0x1800b7fe5  mov     rcx, [r14+8]; hDlg
0x1800b7fe9  call    cs:__imp_GetDlgItem
0x1800b7fef  mov     [rsi], rax
0x1800b7ff2  lea     rdi, [r14+48h]
0x1800b7ff6  mov     edx, 104Dh; nIDDlgItem
0x1800b7ffb  mov     rcx, [r14+8]; hDlg
0x1800b7fff  call    cs:__imp_GetDlgItem
0x1800b8005  mov     [rdi], rax
0x1800b8008  mov     edx, 1054h; nIDDlgItem
0x1800b800d  mov     rcx, [r14+8]; hDlg
0x1800b8011  call    cs:__imp_GetDlgItem
0x1800b8017  mov     [r14+50h], rax
0x1800b801b  mov     r8, [r14+38h]
0x1800b801f  mov     r9d, 1
0x1800b8025  mov     r8, [r8+0F8h]
0x1800b802c  lea     rdx, [rsp+1A0h+var_140]
0x1800b8031  mov     rcx, rsi
0x1800b8034  call    ?SetImageList@?$CListViewCtrlT@VCWindow@ATL@@@WTL@@QEAA?AVCImageList@2@PEAU_IMAGELIST@@H@Z; WTL::CListViewCtrlT<ATL::CWindow>::SetImageList(_IMAGELIST *,int)
0x1800b8039  mov     r8, [r14+38h]
0x1800b803d  mov     r9d, 1
0x1800b8043  mov     r8, [r8+0F8h]
0x1800b804a  lea     rdx, [rsp+1A0h+var_140]
0x1800b804f  mov     rcx, rdi
0x1800b8052  call    ?SetImageList@?$CListViewCtrlT@VCWindow@ATL@@@WTL@@QEAA?AVCImageList@2@PEAU_IMAGELIST@@H@Z; WTL::CListViewCtrlT<ATL::CWindow>::SetImageList(_IMAGELIST *,int)
0x1800b8057  mov     r8, [r14+38h]
0x1800b805b  mov     r8, [r8+0F8h]
0x1800b8062  lea     rdx, [rsp+1A0h+var_140]
0x1800b8067  lea     rcx, [r14+50h]
0x1800b806b  call    ?SetImageList@CComboBoxEx2@@QEAA?AVCImageList@WTL@@V23@@Z; CComboBoxEx2::SetImageList(WTL::CImageList)
0x1800b8070  mov     rdx, [r14+38h]
0x1800b8074  add     rdx, 0C8h
0x1800b807b  mov     rcx, r14
0x1800b807e  call    ?AddSnapinNodesToComboBox@CSnapinMainPage@MMC21ADDREMOVEUI@@AEAAXAEAV?$CList@PEAVCManagerNode@MMC21ADDREMOVEUI@@PEAV12@@@@Z; MMC21ADDREMOVEUI::CSnapinMainPage::AddSnapinNodesToComboBox(CList<MMC21ADDREMOVEUI::CManagerNode *,MMC21ADDREMOVEUI::CManagerNode *> &)
0x1800b8083  lea     rdx, [rbp+0A0h+Rect]; lpRect
0x1800b8087  mov     rcx, [rsi]; hWnd
0x1800b808a  call    cs:__imp_GetClientRect
0x1800b8090  xorps   xmm0, xmm0
0x1800b8093  xor     eax, eax
0x1800b8095  movups  xmmword ptr [rbp+0A0h+lParam], xmm0
0x1800b8099  movups  [rbp+0A0h+var_110], xmm0
0x1800b809d  movups  [rbp+0A0h+var_100], xmm0
0x1800b80a1  mov     [rbp+0A0h+var_F0], rax
0x1800b80a5  mov     dword ptr [rbp+0A0h+lParam], 0Ah
0x1800b80ac  mov     ebx, [rbp+0A0h+Rect.right]
0x1800b80af  sub     ebx, [rbp+0A0h+Rect.left]
0x1800b80b2  mov     ecx, r12d; nIndex
0x1800b80b5  call    cs:__imp_GetSystemMetrics
0x1800b80bb  sub     ebx, eax
0x1800b80bd  test    ebx, ebx
0x1800b80bf  mov     eax, 1
0x1800b80c4  cmovle  ebx, eax
0x1800b80c7  mov     dword ptr [rbp+0A0h+lParam+8], ebx
0x1800b80ca  mov     dword ptr [rbp+0A0h+var_110+0Ch], r15d
0x1800b80ce  lea     r9, [rbp+0A0h+lParam]; lParam
0x1800b80d2  xor     r8d, r8d; wParam
0x1800b80d5  mov     edx, 1061h; Msg
0x1800b80da  mov     rcx, [rsi]; hWnd
0x1800b80dd  call    cs:__imp_SendMessageW
0x1800b80e3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b80e7  cmp     eax, ebx
0x1800b80e9  jnz     short loc_1800B8114
0x1800b80eb  lea     rax, WPP_GLOBAL_Control
0x1800b80f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b80f9  cmp     rcx, rax
0x1800b80fc  jz      loc_1800B842F
0x1800b8102  cmp     [rcx+19h], r12b
0x1800b8106  jb      loc_1800B842F
0x1800b810c  lea     edx, [rbx+46h]
0x1800b810f  jmp     loc_1800B841F
0x1800b8114  mov     rdx, [r14+38h]
0x1800b8118  add     rdx, 0C8h
0x1800b811f  mov     rax, [rdx]
0x1800b8122  mov     rcx, [rax+10h]
0x1800b8126  mov     [r14+58h], rcx
0x1800b812a  test    rcx, rcx
0x1800b812d  jz      loc_1800B8401
0x1800b8133  mov     rcx, r14
0x1800b8136  call    ?DisplayCurrentSnapinList@CSnapinMainPage@MMC21ADDREMOVEUI@@AEAAXAEAV?$CList@PEAVCManagerNode@MMC21ADDREMOVEUI@@PEAV12@@@@Z; MMC21ADDREMOVEUI::CSnapinMainPage::DisplayCurrentSnapinList(CList<MMC21ADDREMOVEUI::CManagerNode *,MMC21ADDREMOVEUI::CManagerNode *> &)
0x1800b813b  mov     rdx, [r14+58h]; struct MMC21ADDREMOVEUI::CManagerNode *
0x1800b813f  mov     rcx, r14; this
0x1800b8142  call    ?SelectParentNodeItem@CSnapinMainPage@MMC21ADDREMOVEUI@@AEAAXPEAVCManagerNode@2@@Z; MMC21ADDREMOVEUI::CSnapinMainPage::SelectParentNodeItem(MMC21ADDREMOVEUI::CManagerNode *)
0x1800b8147  xor     edx, edx; struct MMC21ADDREMOVEUI::CManagerNode *
0x1800b8149  mov     rcx, r14; this
0x1800b814c  call    ?SetupChildNode@CSnapinMainPage@MMC21ADDREMOVEUI@@AEAAXPEAVCManagerNode@2@@Z; MMC21ADDREMOVEUI::CSnapinMainPage::SetupChildNode(MMC21ADDREMOVEUI::CManagerNode *)
0x1800b8151  mov     r9d, 0FFFFh; lParam
0x1800b8157  xor     r8d, r8d; wParam
0x1800b815a  mov     edx, 101Eh; Msg
0x1800b815f  mov     rcx, [rsi]; hWnd
0x1800b8162  call    cs:__imp_SendMessageW
0x1800b8168  mov     r9d, r12d
0x1800b816b  mov     r8d, r12d
0x1800b816e  xor     edx, edx
0x1800b8170  mov     rcx, rsi
0x1800b8173  call    ?SetItemState@?$CListViewCtrlT@VCWindow@ATL@@@WTL@@QEAAHHII@Z; WTL::CListViewCtrlT<ATL::CWindow>::SetItemState(int,uint,uint)
0x1800b8178  lea     rdx, [rbp+0A0h+Rect]; lpRect
0x1800b817c  mov     rcx, [rdi]; hWnd
0x1800b817f  call    cs:__imp_GetClientRect
0x1800b8185  xor     r9d, r9d; lParam
0x1800b8188  xor     r8d, r8d; wParam
0x1800b818b  mov     edx, 1028h; Msg
0x1800b8190  mov     rcx, [rdi]; hWnd
0x1800b8193  call    cs:__imp_SendMessageW
0x1800b8199  mov     rcx, [r14+38h]
0x1800b819d  cmp     eax, [rcx+10Ch]
0x1800b81a3  jge     short loc_1800B81B1
0x1800b81a5  mov     ecx, r12d; nIndex
0x1800b81a8  call    cs:__imp_GetSystemMetrics
0x1800b81ae  sub     [rbp+0A0h+Rect.right], eax
0x1800b81b1  mov     dword ptr [rbp+0A0h+lParam], 0Eh
0x1800b81b8  call    cs:__imp_?GetStringModule@@YAPEAUHINSTANCE__@@XZ; GetStringModule(void)
0x1800b81be  mov     rdx, rax; hInstance
0x1800b81c1  mov     r8d, 36BDh; uID
0x1800b81c7  lea     rcx, [rsp+1A0h+var_160]; this
0x1800b81cc  call    ?LoadStringW@CStr@@QEAAJPEAUHINSTANCE__@@I@Z; CStr::LoadStringW(HINSTANCE__ *,uint)
0x1800b81d1  mov     r9d, eax
0x1800b81d4  test    eax, eax
0x1800b81d6  jns     short loc_1800B8213
0x1800b81d8  lea     rax, WPP_GLOBAL_Control
0x1800b81df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b81e6  cmp     rcx, rax
0x1800b81e9  jz      loc_1800B842F
0x1800b81ef  cmp     [rcx+19h], r12b
0x1800b81f3  jb      loc_1800B842F
0x1800b81f9  mov     edx, 47h ; 'G'
0x1800b81fe  lea     r8, WPP_e6286f7ff16332d569bebdaa5a195f02_Traceguids
0x1800b8205  mov     rcx, [rcx+10h]
0x1800b8209  call    WPP_SF_d
0x1800b820e  jmp     loc_1800B842F
0x1800b8213  mov     rax, qword ptr [rsp+1A0h+var_160+8]
0x1800b8218  mov     qword ptr [rbp+0A0h+var_110], rax
0x1800b821c  mov     eax, [rbp+0A0h+Rect.right]
0x1800b821f  lea     ecx, [rax+rax*2]
0x1800b8222  mov     eax, 66666667h
0x1800b8227  imul    ecx
0x1800b8229  sar     edx, 1
0x1800b822b  mov     eax, edx
0x1800b822d  shr     eax, 1Fh
0x1800b8230  add     edx, eax
0x1800b8232  mov     dword ptr [rbp+0A0h+lParam+8], edx
0x1800b8235  mov     dword ptr [rbp+0A0h+var_110+0Ch], r15d
0x1800b8239  lea     r9, [rbp+0A0h+lParam]; lParam
0x1800b823d  xor     r8d, r8d; wParam
0x1800b8240  mov     esi, 1061h
0x1800b8245  mov     edx, esi; Msg
0x1800b8247  mov     rcx, [rdi]; hWnd
0x1800b824a  call    cs:__imp_SendMessageW
0x1800b8250  cmp     eax, ebx
0x1800b8252  jnz     short loc_1800B827F
0x1800b8254  lea     rax, WPP_GLOBAL_Control
0x1800b825b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8262  cmp     rcx, rax
0x1800b8265  jz      loc_1800B842F
0x1800b826b  cmp     [rcx+19h], r12b
0x1800b826f  jb      loc_1800B842F
0x1800b8275  mov     edx, 48h ; 'H'
0x1800b827a  jmp     loc_1800B841F
0x1800b827f  call    cs:__imp_?GetStringModule@@YAPEAUHINSTANCE__@@XZ; GetStringModule(void)
0x1800b8285  mov     rdx, rax; hInstance
0x1800b8288  mov     r8d, 36C1h; uID
0x1800b828e  lea     rcx, [rsp+1A0h+var_160]; this
0x1800b8293  call    ?LoadStringW@CStr@@QEAAJPEAUHINSTANCE__@@I@Z; CStr::LoadStringW(HINSTANCE__ *,uint)
0x1800b8298  mov     r9d, eax
0x1800b829b  test    eax, eax
0x1800b829d  jns     short loc_1800B82CA
0x1800b829f  lea     rax, WPP_GLOBAL_Control
0x1800b82a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b82ad  cmp     rcx, rax
0x1800b82b0  jz      loc_1800B842F
0x1800b82b6  cmp     [rcx+19h], r12b
0x1800b82ba  jb      loc_1800B842F
0x1800b82c0  mov     edx, 49h ; 'I'
0x1800b82c5  jmp     loc_1800B81FE
0x1800b82ca  mov     rax, qword ptr [rsp+1A0h+var_160+8]
0x1800b82cf  mov     qword ptr [rbp+0A0h+var_110], rax
0x1800b82d3  mov     eax, [rbp+0A0h+Rect.right]
0x1800b82d6  sub     eax, dword ptr [rbp+0A0h+lParam+8]
0x1800b82d9  mov     dword ptr [rbp+0A0h+lParam+8], eax
0x1800b82dc  mov     eax, 1
0x1800b82e1  mov     dword ptr [rbp+0A0h+var_110+0Ch], eax
0x1800b82e4  lea     r9, [rbp+0A0h+lParam]; lParam
0x1800b82e8  mov     r8d, eax; wParam
0x1800b82eb  mov     edx, esi; Msg
0x1800b82ed  mov     rcx, [rdi]; hWnd
0x1800b82f0  call    cs:__imp_SendMessageW
0x1800b82f6  cmp     eax, ebx
0x1800b82f8  jnz     short loc_1800B8335
0x1800b82fa  lea     rax, WPP_GLOBAL_Control
0x1800b8301  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8308  cmp     rcx, rax
0x1800b830b  jz      loc_1800B843D
  ... truncated ...
```
