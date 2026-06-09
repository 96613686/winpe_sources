# CTray::_OnSessionChange(unsigned __int64,__int64)

- ea: `0x140013150`
- end: `0x140013668`
- name: `?_OnSessionChange@CTray@@IEAA_J_K_J@Z`
- size: `1304`
- prototype: `__int64 __fastcall(CTray *__hidden this, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001d860`

## callees

- `0x14000de44`
- `0x140012df0`
- `0x140012e9c`
- `0x140012f54`
- `0x140013150`
- `0x140013670`
- `0x1400179d0`
- `0x140017dbc`
- `0x140017e58`
- `0x140017e8c`
- `0x14001eba8`
- `0x1400632b0`
- `0x1400751d8`
- `0x14007b354`
- `0x1400ab510`
- `0x1401040e0`
- `0x140104c50`
- `0x140113b0c`
- `0x1401158d4`
- `0x1401214a0`
- `0x1401db010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140013227`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x140013227`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140013213`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x140013213`
- `ntdll!RtlPublishWnfStateData` at `0x1400131fa`
- `ntdll!RtlPublishWnfStateData` at `0x140013508`
- `ntdll!RtlPublishWnfStateData` at `0x1400131fa`
- `ntdll!RtlPublishWnfStateData` at `0x140013508`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400132cc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400132cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140013415`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140013415`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140013340`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140013340`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400132e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013384`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400132e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013384`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013254`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013254`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001336e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001336e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400132a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400132a1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1400132bb`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1400132bb`
- `SHELL32!SHUpdateRecycleBinIcon` at `0x140013405`
- `SHELL32!SHUpdateRecycleBinIcon` at `0x140013405`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x1400133ce`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x1400133ce`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x1400134a4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x140013647`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x1400134a4`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x140013647`

## string_xrefs

- `0x14001344e`: `SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger`
- `0x140013205`: `Software\Microsoft\EdgeUpdate\Clients\`

## pseudocode

```c
__int64 __fastcall CTray::_OnSessionChange(HWND *this, unsigned __int64 a2, unsigned int a3)
{
  __int64 v5; // rax
  bool InstalledInfo; // r14
  unsigned __int16 *v7; // r9
  DWORD FileAttributesW; // eax
  ULONG v9; // r15d
  HKEY v10; // rcx
  int v11; // esi
  LSTATUS v12; // eax
  bool v13; // sf
  int v14; // eax
  CTray *v15; // rcx
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // esi
  unsigned int v20; // eax
  ULONG v21; // ecx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  struct BrowserChannels::Info *pvData; // [rsp+28h] [rbp-D8h]
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pdwType; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v29[272]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v30[8]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v31[240]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR pszPath[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McTemplateU0qq_EventWriteTransfer(this, Explorer_SessionChangeMessage_Info, (unsigned int)a2, a3);
  *((_DWORD *)this + 123) = a2;
  if ( a2 <= 8 && (v5 = 266, _bittest64(&v5, a2)) )
  {
    *((_DWORD *)this + 119) = 1;
    if ( ((a2 - 1) & 0xFFFFFFFFFFFFFFFDuLL) == 0 )
    {
      (*(void (__fastcall **)(HWND))(*(_QWORD *)this[133] + 240LL))(this[133]);
      SHUpdateRecycleBinIcon();
      CTray::_NotifyCDBurnSessionChange(v15);
      if ( a2 == 1 )
        goto LABEL_33;
      goto LABEL_28;
    }
  }
  else
  {
    if ( a2 > 7 )
      goto LABEL_7;
    v18 = 148;
    if ( _bittest64(&v18, a2) )
      *((_DWORD *)this + 119) = 0;
  }
  if ( a2 == 7 )
  {
    if ( !*((_DWORD *)this + 57) )
      RtlPublishWnfStateData(WNF_SHEL_DEVICE_LOCKED, 0, 0, 0);
    goto LABEL_27;
  }
LABEL_7:
  if ( a2 == 8 )
  {
    RtlPublishWnfStateData(WNF_SHEL_DEVICE_UNLOCKED, 0, 0, 0);
    _o_wcscpy_s(SubKey, 260, L"Software\\Microsoft\\EdgeUpdate\\Clients\\");
    _o_wcscat_s(SubKey, 260, L"{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}");
    hkey = 0;
    InstalledInfo = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20219u, &hkey) )
    {
      pcbData = 520;
      pdwType = 0;
      if ( !RegGetValueW(hkey, 0, L"location", 2u, &pdwType, pszPath, &pcbData)
        && !PathCchAppend(pszPath, 0x104u, L"msedge.exe") )
      {
        FileAttributesW = GetFileAttributesW(pszPath);
        if ( FileAttributesW != -1 )
          InstalledInfo = (FileAttributesW & 0x10) == 0;
      }
      RegCloseKey(hkey);
    }
    if ( !InstalledInfo )
      InstalledInfo = BrowserChannels::Private::GetInstalledInfo(
                        (BrowserChannels::Private *)0xFFFFFFFF80000001LL,
                        (HKEY)SubKey,
                        pszPath,
                        v7,
                        phkResult,
                        pvData);
    v9 = 3000;
    if ( InstalledInfo )
    {
      pdwType = 1;
      hkey = 0;
      v11 = RegCreateKeyExW(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
              0,
              0,
              0,
              2u,
              0,
              &hkey,
              0);
      if ( !v11 )
      {
        v12 = RegSetValueExW(hkey, L"ExcludedFromStableAnaheimDownloadPromotionSL", 0, 4u, (const BYTE *)&pdwType, 4u);
        v10 = hkey;
        v11 = v12;
        if ( hkey != HKEY_CURRENT_USER )
          RegCloseKey(hkey);
      }
      v13 = v11 < 0;
      if ( v11 > 0 )
      {
        v11 = (unsigned __int16)v11 | 0x80070000;
        v13 = v11 < 0;
      }
      if ( v13 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1398,
          (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
          (const char *)(unsigned int)v11,
          phkResulta);
    }
    else
    {
      pcbData = 0;
      if ( (int)SHRegGetBOOLWithREGSAM(
                  HKEY_CURRENT_USER,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
                  L"ExcludedFromStableAnaheimDownloadPromotionSL",
                  (unsigned int)v7,
                  (int *)&pcbData) < 0
        || !pcbData )
      {
        if ( (unsigned __int8)GetInstalledBrowserChannelInfo(1, 3)
          || (unsigned __int8)GetInstalledBrowserChannelInfo(2, 3)
          || (v19 = 0, (unsigned __int8)GetInstalledBrowserChannelInfo(3, 3)) )
        {
          v19 = 1;
        }
        AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger::Start<>((AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger *)SubKey);
        v20 = (int)o_ceil_0();
        v21 = 3000;
        if ( v20 < 0xBB8 )
          v21 = v20;
        SetCoalescableTimer(this[1], 0x1Cu, 0xEA60u, 0, v21);
        AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger::Stop(SubKey, v19);
        AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger::~SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger((AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger *)SubKey);
      }
    }
    if ( InstalledInfo )
    {
      wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)SubKey);
      *(_QWORD *)SubKey = &AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger::`vftable';
      AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger::StartActivity((AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger *)SubKey);
      v17 = (int)o_ceil_0();
      if ( v17 < 0xBB8 )
        v9 = v17;
      SetCoalescableTimer(this[1], 0x1Cu, 0xEA60u, 0, v9);
      wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(SubKey);
      *(_QWORD *)SubKey = &AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger::`vftable';
      wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(SubKey);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v31);
      wil::details::shared_object<wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnaheimPromotionSoftLandingLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v30);
      wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnaheimPromotionSoftLandingLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AnaheimPromotionSoftLandingLogging,_TlgReflectorTag_Param0IsProviderType>(v29);
    }
    LOBYTE(v10) = 2;
    v14 = MobilityExperience::Triggers::ReportUsageIfAppropriate(v10);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13A5,
        (unsigned int)"pcshell\\shell\\explorer\\tray.cpp",
        (const char *)(unsigned int)v14,
        phkResulta);
LABEL_27:
    PostMessageW(this[1], 0x581u, a2 == 7, 0);
LABEL_28:
    if ( a2 != 8 )
      goto LABEL_29;
LABEL_33:
    *((_DWORD *)this + 125) = GetCurrentThreadId();
    return 1;
  }
LABEL_29:
  if ( a2 == 2 || a2 == 7 )
    *((_DWORD *)this + 125) = 0;
  return 1;
}

```

## disassembly

```asm
0x140013150  mov     [rsp-8+arg_18], rbx
0x140013155  push    rbp
0x140013156  push    rsi
0x140013157  push    rdi
0x140013158  push    r12
0x14001315a  push    r13
0x14001315c  push    r14
0x14001315e  push    r15
0x140013160  lea     rbp, [rsp-390h]
0x140013168  sub     rsp, 490h
0x14001316f  mov     rax, cs:__security_cookie
0x140013176  xor     rax, rsp
0x140013179  mov     [rbp+3C0h+var_40], rax
0x140013180  mov     r13d, 1
0x140013186  mov     rbx, rdx
0x140013189  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r13b
0x140013190  mov     rdi, rcx
0x140013193  jnz     loc_140013553
0x140013199  xor     r12d, r12d
0x14001319c  mov     [rdi+1ECh], ebx
0x1400131a2  cmp     rbx, 8
0x1400131a6  ja      loc_14001356A
0x1400131ac  mov     eax, 10Ah
0x1400131b1  bt      rax, rbx
0x1400131b5  jnb     loc_14001356A
0x1400131bb  lea     rax, [rbx-1]
0x1400131bf  mov     [rdi+1DCh], r13d
0x1400131c6  test    rax, 0FFFFFFFFFFFFFFFDh
0x1400131cc  jz      loc_1400133EF
0x1400131d2  cmp     rbx, 7
0x1400131d6  jz      loc_1400134E7
0x1400131dc  cmp     rbx, 8
0x1400131e0  jnz     loc_1400133DA
0x1400131e6  mov     rcx, cs:WNF_SHEL_DEVICE_UNLOCKED
0x1400131ed  xor     r9d, r9d
0x1400131f0  xor     r8d, r8d
0x1400131f3  mov     [rsp+4C0h+phkResult], r12
0x1400131f8  xor     edx, edx
0x1400131fa  call    cs:__imp_RtlPublishWnfStateData
0x140013200  mov     esi, 104h
0x140013205  lea     r8, aSoftwareMicros_143; "Software\\Microsoft\\EdgeUpdate\\Client"...
0x14001320c  mov     edx, esi
0x14001320e  lea     rcx, [rsp+4C0h+SubKey]
0x140013213  call    cs:__imp__o_wcscpy_s
0x140013219  lea     r8, a56eb18f8B0084c; "{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}"
0x140013220  mov     edx, esi
0x140013222  lea     rcx, [rsp+4C0h+SubKey]
0x140013227  call    cs:__imp__o_wcscat_s
0x14001322d  lea     rax, [rsp+4C0h+hkey]
0x140013232  mov     [rsp+4C0h+hkey], r12
0x140013237  mov     r9d, 20219h; samDesired
0x14001323d  mov     [rsp+4C0h+phkResult], rax; phkResult
0x140013242  xor     r8d, r8d; ulOptions
0x140013245  lea     rdx, [rsp+4C0h+SubKey]; lpSubKey
0x14001324a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140013251  mov     r14b, r12b
0x140013254  call    cs:__imp_RegOpenKeyExW
0x14001325a  test    eax, eax
0x14001325c  jnz     loc_1400132E9
0x140013262  mov     rcx, [rsp+4C0h+hkey]; hkey
0x140013267  lea     rax, [rsp+4C0h+var_470]
0x14001326c  mov     [rsp+4C0h+pcbData], rax; pcbData
0x140013271  lea     r9d, [rbx-6]; dwFlags
0x140013275  lea     rax, [rbp+3C0h+pszPath]
0x14001327c  mov     [rsp+4C0h+var_470], 208h
0x140013284  mov     [rsp+4C0h+pvData], rax; struct BrowserChannels::Info *
0x140013289  lea     r8, aLocation; "location"
0x140013290  lea     rax, [rsp+4C0h+pdwType]
0x140013295  mov     [rsp+4C0h+pdwType], r12d
0x14001329a  xor     edx, edx; lpSubKey
0x14001329c  mov     [rsp+4C0h+phkResult], rax; unsigned int
0x1400132a1  call    cs:__imp_RegGetValueW
0x1400132a7  test    eax, eax
0x1400132a9  jnz     short loc_1400132DE
0x1400132ab  lea     r8, pszMore; "msedge.exe"
0x1400132b2  mov     edx, esi; cchPath
0x1400132b4  lea     rcx, [rbp+3C0h+pszPath]; pszPath
0x1400132bb  call    cs:__imp_PathCchAppend
0x1400132c1  test    eax, eax
0x1400132c3  jnz     short loc_1400132DE
0x1400132c5  lea     rcx, [rbp+3C0h+pszPath]; lpFileName
0x1400132cc  call    cs:__imp_GetFileAttributesW
0x1400132d2  cmp     eax, 0FFFFFFFFh
0x1400132d5  jz      short loc_1400132DE
0x1400132d7  test    al, 10h
0x1400132d9  jnz     short loc_1400132DE
0x1400132db  mov     r14b, r13b
0x1400132de  mov     rcx, [rsp+4C0h+hkey]; hKey
0x1400132e3  call    cs:__imp_RegCloseKey
0x1400132e9  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1400132f0  test    r14b, r14b
0x1400132f3  jz      loc_14001358F
0x1400132f9  lea     rdx, aSoftwareMicros_119; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140013300  mov     r15d, 0BB8h
0x140013306  test    r14b, r14b
0x140013309  jz      loc_1400135AF
0x14001330f  mov     [rsp+4C0h+lpdwDisposition], r12; lpdwDisposition
0x140013314  lea     rax, [rsp+4C0h+hkey]
0x140013319  mov     [rsp+4C0h+var_488], rax; phkResult
0x14001331e  xor     r9d, r9d; lpClass
0x140013321  mov     [rsp+4C0h+pcbData], r12; lpSecurityAttributes
0x140013326  xor     r8d, r8d; Reserved
0x140013329  mov     dword ptr [rsp+4C0h+pvData], 2; samDesired
0x140013331  mov     dword ptr [rsp+4C0h+phkResult], r12d; dwOptions
0x140013336  mov     [rsp+4C0h+pdwType], r13d
0x14001333b  mov     [rsp+4C0h+hkey], r12
0x140013340  call    cs:__imp_RegCreateKeyExW
0x140013346  mov     esi, eax
0x140013348  test    eax, eax
0x14001334a  jnz     short loc_14001338A
0x14001334c  mov     rcx, [rsp+4C0h+hkey]; hKey
0x140013351  lea     r9d, [rax+4]; dwType
0x140013355  lea     rax, [rsp+4C0h+pdwType]
0x14001335a  mov     dword ptr [rsp+4C0h+pvData], r9d; cbData
0x14001335f  xor     r8d, r8d; Reserved
0x140013362  mov     [rsp+4C0h+phkResult], rax; int
0x140013367  lea     rdx, ValueName; "ExcludedFromStableAnaheimDownloadPromot"...
0x14001336e  call    cs:__imp_RegSetValueExW
0x140013374  mov     rcx, [rsp+4C0h+hkey]; hKey
0x140013379  mov     esi, eax
0x14001337b  cmp     rcx, 0FFFFFFFF80000001h
0x140013382  jz      short loc_14001338A
0x140013384  call    cs:__imp_RegCloseKey
0x14001338a  test    esi, esi
0x14001338c  jle     short loc_140013399
0x14001338e  movzx   esi, si
0x140013391  or      esi, 80070000h
0x140013397  test    esi, esi
0x140013399  js      loc_140013513
0x14001339f  test    r14b, r14b
0x1400133a2  jnz     loc_14001344E
0x1400133a8  mov     cl, 2
0x1400133aa  call    ?ReportUsageIfAppropriate@Triggers@MobilityExperience@@YAJW4MobilityExperienceUsageType@12@@Z; MobilityExperience::Triggers::ReportUsageIfAppropriate(MobilityExperience::Triggers::MobilityExperienceUsageType)
0x1400133af  test    eax, eax
0x1400133b1  js      loc_140013533
0x1400133b7  mov     rcx, [rdi+8]; hWnd
0x1400133bb  cmp     rbx, 7
0x1400133bf  mov     r8, r12
0x1400133c2  mov     edx, 581h; Msg
0x1400133c7  setz    r8b; wParam
0x1400133cb  xor     r9d, r9d; lParam
0x1400133ce  call    cs:__imp_PostMessageW
0x1400133d4  cmp     rbx, 8
0x1400133d8  jz      short loc_140013415
0x1400133da  cmp     rbx, 2
0x1400133de  jz      short loc_1400133E6
0x1400133e0  cmp     rbx, 7
0x1400133e4  jnz     short loc_140013421
0x1400133e6  mov     [rdi+1F4h], r12d
0x1400133ed  jmp     short loc_140013421
0x1400133ef  mov     rcx, [rdi+428h]
0x1400133f6  mov     rax, [rcx]
0x1400133f9  mov     rax, [rax+0F0h]
0x140013400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013405  call    cs:__imp_SHUpdateRecycleBinIcon
0x14001340b  call    ?_NotifyCDBurnSessionChange@CTray@@IEAAXXZ; CTray::_NotifyCDBurnSessionChange(void)
0x140013410  cmp     rbx, r13
0x140013413  jnz     short loc_1400133D4
0x140013415  call    cs:__imp_GetCurrentThreadId
0x14001341b  mov     [rdi+1F4h], eax
0x140013421  mov     rax, r13
0x140013424  mov     rcx, [rbp+3C0h+var_40]
0x14001342b  xor     rcx, rsp; StackCookie
0x14001342e  call    __security_check_cookie
0x140013433  mov     rbx, [rsp+4C0h+arg_18]
0x14001343b  add     rsp, 490h
0x140013442  pop     r15
0x140013444  pop     r14
0x140013446  pop     r13
0x140013448  pop     r12
0x14001344a  pop     rdi
0x14001344b  pop     rsi
0x14001344c  pop     rbp
0x14001344d  retn
0x14001344e  lea     rdx, aSettimerforana; "SetTimerForAnaheimPostInstallPromotionS"...
0x140013455  lea     rcx, [rsp+4C0h+SubKey]; struct wil::details::IFailureCallback *
0x14001345a  call    ??0?$ActivityBase@VAnaheimPromotionSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14001345f  lea     rsi, ??_7SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger@AnaheimPromotionSoftLandingTelemetry@@6B@; const AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger::`vftable'
0x140013466  lea     rcx, [rsp+4C0h+SubKey]; this
0x14001346b  mov     qword ptr [rsp+4C0h+SubKey], rsi
0x140013470  call    ?StartActivity@SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger@AnaheimPromotionSoftLandingTelemetry@@QEAAXXZ; AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger::StartActivity(void)
0x140013475  movsd   xmm0, cs:__real@40a7700000000000
0x14001347d  call    _o_ceil_0
0x140013482  mov     rcx, [rdi+8]; hWnd
0x140013486  mov     r8d, 0EA60h; uElapse
0x14001348c  cvttsd2si rax, xmm0
0x140013491  cmp     eax, r15d
0x140013494  cmovb   r15d, eax
0x140013498  xor     r9d, r9d; lpTimerFunc
0x14001349b  mov     dword ptr [rsp+4C0h+phkResult], r15d; uToleranceDelay
0x1400134a0  lea     edx, [r9+1Ch]; nIDEvent
0x1400134a4  call    cs:__imp_SetCoalescableTimer
0x1400134aa  lea     rcx, [rsp+4C0h+SubKey]
0x1400134af  call    ?Stop@?$ActivityBase@VAnaheimPromotionSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400134b4  lea     rcx, [rsp+4C0h+SubKey]
0x1400134b9  mov     qword ptr [rsp+4C0h+SubKey], rsi
0x1400134be  call    ?Destroy@?$ActivityBase@VAnaheimPromotionSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1400134c3  lea     rcx, [rbp+3C0h+var_340]; this
0x1400134ca  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1400134cf  lea     rcx, [rbp+3C0h+var_348]
0x1400134d3  call    ?reset@?$shared_object@V?$ActivityData@VAnaheimPromotionSoftLandingLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAnaheimPromotionSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnaheimPromotionSoftLandingLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1400134d8  lea     rcx, [rsp+4C0h+var_458]
0x1400134dd  call    ??1?$ActivityData@VAnaheimPromotionSoftLandingLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAnaheimPromotionSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnaheimPromotionSoftLandingLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AnaheimPromotionSoftLandingLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x1400134e2  jmp     loc_1400133A8
0x1400134e7  cmp     [rdi+0E4h], r12d
0x1400134ee  jnz     loc_1400133B7
0x1400134f4  mov     rcx, cs:WNF_SHEL_DEVICE_LOCKED
0x1400134fb  xor     r9d, r9d
0x1400134fe  xor     r8d, r8d
0x140013501  mov     [rsp+4C0h+phkResult], r12
0x140013506  xor     edx, edx
0x140013508  call    cs:__imp_RtlPublishWnfStateData
0x14001350e  jmp     loc_1400133B7
0x140013513  mov     rcx, [rbp+3C8h]; this
0x14001351a  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x140013521  mov     r9d, esi; char *
0x140013524  mov     edx, 1398h; void *
0x140013529  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001352e  jmp     loc_14001339F
0x140013533  mov     rcx, [rbp+3C8h]; this
0x14001353a  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x140013541  mov     r9d, eax; char *
0x140013544  mov     edx, 13A5h; void *
0x140013549  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001354e  jmp     loc_1400133B7
0x140013553  mov     r9d, r8d
0x140013556  lea     rdx, Explorer_SessionChangeMessage_Info
0x14001355d  mov     r8d, ebx
0x140013560  call    McTemplateU0qq_EventWriteTransfer
0x140013565  jmp     loc_140013199
0x14001356a  cmp     rbx, 7
0x14001356e  ja      loc_1400131DC
0x140013574  mov     eax, 94h
0x140013579  bt      rax, rbx
0x14001357d  jnb     loc_1400131D2
0x140013583  mov     [rdi+1DCh], r12d
0x14001358a  jmp     loc_1400131D2
0x14001358f  lea     r8, [rbp+3C0h+pszPath]; unsigned __int16 *
0x140013596  lea     rdx, [rsp+4C0h+SubKey]; HKEY
0x14001359b  call    ?GetInstalledInfo@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAG1KPEAUInfo@2@@Z; BrowserChannels::Private::GetInstalledInfo(HKEY__ *,ushort *,ushort *,ulong,BrowserChannels::Info *)
0x1400135a0  mov     r14b, al
0x1400135a3  mov     rcx, 0FFFFFFFF80000001h
0x1400135aa  jmp     loc_1400132F9
0x1400135af  lea     rax, [rsp+4C0h+var_470]
0x1400135b4  mov     [rsp+4C0h+var_470], r12d
0x1400135b9  lea     r8, ValueName; "ExcludedFromStableAnaheimDownloadPromot"...
0x1400135c0  mov     [rsp+4C0h+phkResult], rax; int *
0x1400135c5  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x1400135ca  test    eax, eax
0x1400135cc  js      short loc_1400135D9
0x1400135ce  cmp     [rsp+4C0h+var_470], r12d
0x1400135d3  jnz     loc_14001339F
0x1400135d9  mov     esi, 3
0x1400135de  mov     ecx, r13d
0x1400135e1  mov     edx, esi
0x1400135e3  call    ?GetInstalledBrowserChannelInfo@@YA_NW4ChannelId@BrowserChannels@@W4InstallationLevel@2@PEAUInfo@2@@Z; GetInstalledBrowserChannelInfo(BrowserChannels::ChannelId,BrowserChannels::InstallationLevel,BrowserChannels::Info *)
0x1400135e8  test    al, al
0x1400135ea  jnz     short loc_14001360A
0x1400135ec  mov     edx, esi
0x1400135ee  lea     ecx, [rsi-1]
0x1400135f1  call    ?GetInstalledBrowserChannelInfo@@YA_NW4ChannelId@BrowserChannels@@W4InstallationLevel@2@PEAUInfo@2@@Z; GetInstalledBrowserChannelInfo(BrowserChannels::ChannelId,BrowserChannels::InstallationLevel,BrowserChannels::Info *)
0x1400135f6  test    al, al
0x1400135f8  jnz     short loc_14001360A
0x1400135fa  mov     edx, esi
0x1400135fc  mov     ecx, esi
0x1400135fe  call    ?GetInstalledBrowserChannelInfo@@YA_NW4ChannelId@BrowserChannels@@W4InstallationLevel@2@PEAUInfo@2@@Z; GetInstalledBrowserChannelInfo(BrowserChannels::ChannelId,BrowserChannels::InstallationLevel,BrowserChannels::Info *)
0x140013603  mov     esi, r12d
0x140013606  test    al, al
0x140013608  jz      short loc_14001360D
0x14001360a  mov     esi, r13d
0x14001360d  lea     rcx, [rsp+4C0h+SubKey]; this
0x140013612  call    ??$Start@$$V@SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger@AnaheimPromotionSoftLandingTelemetry@@SA?AV01@XZ; AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger::Start<>(void)
0x140013617  movsd   xmm0, cs:__real@40a7700000000000
0x14001361f  call    _o_ceil_0
0x140013624  cvttsd2si rax, xmm0
0x140013629  mov     ecx, r15d
0x14001362c  mov     r8d, 0EA60h; uElapse
0x140013632  cmp     eax, r15d
0x140013635  cmovb   ecx, eax
0x140013638  xor     r9d, r9d; lpTimerFunc
0x14001363b  mov     dword ptr [rsp+4C0h+phkResult], ecx; uToleranceDelay
0x14001363f  mov     rcx, [rdi+8]; hWnd
0x140013643  lea     edx, [r9+1Ch]; nIDEvent
0x140013647  call    cs:__imp_SetCoalescableTimer
0x14001364d  mov     edx, esi
0x14001364f  lea     rcx, [rsp+4C0h+SubKey]
0x140013654  call    ?Stop@SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger@AnaheimPromotionSoftLandingTelemetry@@QEAAXW4AnaheimSoftLandingTriggerType@2@@Z; AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger::Stop(AnaheimPromotionSoftLandingTelemetry::AnaheimSoftLandingTriggerType)
0x140013659  lea     rcx, [rsp+4C0h+SubKey]; this
0x14001365e  call    ??1SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger@AnaheimPromotionSoftLandingTelemetry@@QEAA@XZ; AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger::~SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger(void)
0x140013663  jmp     loc_14001339F
```
