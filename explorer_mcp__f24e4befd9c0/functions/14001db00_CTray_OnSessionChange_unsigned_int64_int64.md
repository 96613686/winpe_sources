# CTray::_OnSessionChange(unsigned __int64,__int64)

- ea: `0x14001db00`
- end: `0x14001e07f`
- name: `?_OnSessionChange@CTray@@IEAA_J_K_J@Z`
- size: `1407`
- prototype: `__int64 __fastcall(CTray *__hidden this, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140019eb0`

## callees

- `0x14000a79c`
- `0x14001144c`
- `0x14001b2c8`
- `0x14001d2dc`
- `0x14001d6f0`
- `0x14001d78c`
- `0x14001d7c0`
- `0x14001d8fc`
- `0x14001db00`
- `0x14001e088`
- `0x140066ba0`
- `0x14007a684`
- `0x140080924`
- `0x1400939ac`
- `0x1400b122c`
- `0x14010e160`
- `0x14010ed00`
- `0x14011e3d8`
- `0x1401201c0`
- `0x14012ca44`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001dbe3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14001dbe3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14001dbc9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14001dbc9`
- `ntdll!RtlPublishWnfStateData` at `0x14001dbaa`
- `ntdll!RtlPublishWnfStateData` at `0x14001df13`
- `ntdll!RtlPublishWnfStateData` at `0x14001dbaa`
- `ntdll!RtlPublishWnfStateData` at `0x14001df13`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001dca0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14001dca0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001de13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001de13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001dd54`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001dd54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001dd20`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14001dd20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001dc16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001dc16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001dcbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001dd70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001dcbd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001dd70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001dc69`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001dc69`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14001dc89`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x14001dc89`
- `SHELL32!SHUpdateRecycleBinIcon` at `0x14001ddfd`
- `SHELL32!SHUpdateRecycleBinIcon` at `0x14001ddfd`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x14001ddc0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostMessageW` at `0x14001ddc0`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x14001dea9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x14001e058`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x14001dea9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!SetCoalescableTimer` at `0x14001e058`

## string_xrefs

- `0x14001de53`: `SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger`
- `0x14001dbbb`: `Software\Microsoft\EdgeUpdate\Clients\`

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
0x14001db00  mov     [rsp-8+arg_18], rbx
0x14001db05  push    rbp
0x14001db06  push    rsi
0x14001db07  push    rdi
0x14001db08  push    r12
0x14001db0a  push    r13
0x14001db0c  push    r14
0x14001db0e  push    r15
0x14001db10  lea     rbp, [rsp-390h]
0x14001db18  sub     rsp, 490h
0x14001db1f  mov     rax, cs:__security_cookie
0x14001db26  xor     rax, rsp
0x14001db29  mov     [rbp+3C0h+var_40], rax
0x14001db30  mov     r13d, 1
0x14001db36  mov     rbx, rdx
0x14001db39  test    cs:Microsoft_Windows_Shell_CoreEnableBits, r13b
0x14001db40  mov     rdi, rcx
0x14001db43  jnz     loc_14001DF64
0x14001db49  xor     r12d, r12d
0x14001db4c  mov     [rdi+1ECh], ebx
0x14001db52  cmp     rbx, 8
0x14001db56  ja      loc_14001DF7B
0x14001db5c  mov     eax, 10Ah
0x14001db61  bt      rax, rbx
0x14001db65  jnb     loc_14001DF7B
0x14001db6b  lea     rax, [rbx-1]
0x14001db6f  mov     [rdi+1DCh], r13d
0x14001db76  test    rax, 0FFFFFFFFFFFFFFFDh
0x14001db7c  jz      loc_14001DDE7
0x14001db82  cmp     rbx, 7
0x14001db86  jz      loc_14001DEF2
0x14001db8c  cmp     rbx, 8
0x14001db90  jnz     loc_14001DDD2
0x14001db96  mov     rcx, cs:WNF_SHEL_DEVICE_UNLOCKED
0x14001db9d  xor     r9d, r9d
0x14001dba0  xor     r8d, r8d
0x14001dba3  mov     [rsp+4C0h+phkResult], r12
0x14001dba8  xor     edx, edx
0x14001dbaa  call    cs:__imp_RtlPublishWnfStateData
0x14001dbb1  nop     dword ptr [rax+rax+00h]
0x14001dbb6  mov     esi, 104h
0x14001dbbb  lea     r8, aSoftwareMicros_144; "Software\\Microsoft\\EdgeUpdate\\Client"...
0x14001dbc2  mov     edx, esi
0x14001dbc4  lea     rcx, [rsp+4C0h+SubKey]
0x14001dbc9  call    cs:__imp__o_wcscpy_s
0x14001dbd0  nop     dword ptr [rax+rax+00h]
0x14001dbd5  lea     r8, a56eb18f8B0084c; "{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}"
0x14001dbdc  mov     edx, esi
0x14001dbde  lea     rcx, [rsp+4C0h+SubKey]
0x14001dbe3  call    cs:__imp__o_wcscat_s
0x14001dbea  nop     dword ptr [rax+rax+00h]
0x14001dbef  lea     rax, [rsp+4C0h+hkey]
0x14001dbf4  mov     [rsp+4C0h+hkey], r12
0x14001dbf9  mov     r9d, 20219h; samDesired
0x14001dbff  mov     [rsp+4C0h+phkResult], rax; phkResult
0x14001dc04  xor     r8d, r8d; ulOptions
0x14001dc07  lea     rdx, [rsp+4C0h+SubKey]; lpSubKey
0x14001dc0c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001dc13  mov     r14b, r12b
0x14001dc16  call    cs:__imp_RegOpenKeyExW
0x14001dc1d  nop     dword ptr [rax+rax+00h]
0x14001dc22  test    eax, eax
0x14001dc24  jnz     loc_14001DCC9
0x14001dc2a  mov     rcx, [rsp+4C0h+hkey]; hkey
0x14001dc2f  lea     rax, [rsp+4C0h+var_470]
0x14001dc34  mov     [rsp+4C0h+pcbData], rax; pcbData
0x14001dc39  lea     r9d, [rbx-6]; dwFlags
0x14001dc3d  lea     rax, [rbp+3C0h+pszPath]
0x14001dc44  mov     [rsp+4C0h+var_470], 208h
0x14001dc4c  mov     [rsp+4C0h+pvData], rax; struct BrowserChannels::Info *
0x14001dc51  lea     r8, aLocation; "location"
0x14001dc58  lea     rax, [rsp+4C0h+pdwType]
0x14001dc5d  mov     [rsp+4C0h+pdwType], r12d
0x14001dc62  xor     edx, edx; lpSubKey
0x14001dc64  mov     [rsp+4C0h+phkResult], rax; unsigned int
0x14001dc69  call    cs:__imp_RegGetValueW
0x14001dc70  nop     dword ptr [rax+rax+00h]
0x14001dc75  test    eax, eax
0x14001dc77  jnz     short loc_14001DCB8
0x14001dc79  lea     r8, pszMore; "msedge.exe"
0x14001dc80  mov     edx, esi; cchPath
0x14001dc82  lea     rcx, [rbp+3C0h+pszPath]; pszPath
0x14001dc89  call    cs:__imp_PathCchAppend
0x14001dc90  nop     dword ptr [rax+rax+00h]
0x14001dc95  test    eax, eax
0x14001dc97  jnz     short loc_14001DCB8
0x14001dc99  lea     rcx, [rbp+3C0h+pszPath]; lpFileName
0x14001dca0  call    cs:__imp_GetFileAttributesW
0x14001dca7  nop     dword ptr [rax+rax+00h]
0x14001dcac  cmp     eax, 0FFFFFFFFh
0x14001dcaf  jz      short loc_14001DCB8
0x14001dcb1  test    al, 10h
0x14001dcb3  jnz     short loc_14001DCB8
0x14001dcb5  mov     r14b, r13b
0x14001dcb8  mov     rcx, [rsp+4C0h+hkey]; hKey
0x14001dcbd  call    cs:__imp_RegCloseKey
0x14001dcc4  nop     dword ptr [rax+rax+00h]
0x14001dcc9  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x14001dcd0  test    r14b, r14b
0x14001dcd3  jz      loc_14001DFA0
0x14001dcd9  lea     rdx, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001dce0  mov     r15d, 0BB8h
0x14001dce6  test    r14b, r14b
0x14001dce9  jz      loc_14001DFC0
0x14001dcef  mov     [rsp+4C0h+lpdwDisposition], r12; lpdwDisposition
0x14001dcf4  lea     rax, [rsp+4C0h+hkey]
0x14001dcf9  mov     [rsp+4C0h+var_488], rax; phkResult
0x14001dcfe  xor     r9d, r9d; lpClass
0x14001dd01  mov     [rsp+4C0h+pcbData], r12; lpSecurityAttributes
0x14001dd06  xor     r8d, r8d; Reserved
0x14001dd09  mov     dword ptr [rsp+4C0h+pvData], 2; samDesired
0x14001dd11  mov     dword ptr [rsp+4C0h+phkResult], r12d; dwOptions
0x14001dd16  mov     [rsp+4C0h+pdwType], r13d
0x14001dd1b  mov     [rsp+4C0h+hkey], r12
0x14001dd20  call    cs:__imp_RegCreateKeyExW
0x14001dd27  nop     dword ptr [rax+rax+00h]
0x14001dd2c  mov     esi, eax
0x14001dd2e  test    eax, eax
0x14001dd30  jnz     short loc_14001DD7C
0x14001dd32  mov     rcx, [rsp+4C0h+hkey]; hKey
0x14001dd37  lea     r9d, [rax+4]; dwType
0x14001dd3b  lea     rax, [rsp+4C0h+pdwType]
0x14001dd40  mov     dword ptr [rsp+4C0h+pvData], r9d; cbData
0x14001dd45  xor     r8d, r8d; Reserved
0x14001dd48  mov     [rsp+4C0h+phkResult], rax; int
0x14001dd4d  lea     rdx, aExcludedfromst; "ExcludedFromStableAnaheimDownloadPromot"...
0x14001dd54  call    cs:__imp_RegSetValueExW
0x14001dd5b  nop     dword ptr [rax+rax+00h]
0x14001dd60  mov     rcx, [rsp+4C0h+hkey]; hKey
0x14001dd65  mov     esi, eax
0x14001dd67  cmp     rcx, 0FFFFFFFF80000001h
0x14001dd6e  jz      short loc_14001DD7C
0x14001dd70  call    cs:__imp_RegCloseKey
0x14001dd77  nop     dword ptr [rax+rax+00h]
0x14001dd7c  test    esi, esi
0x14001dd7e  jle     short loc_14001DD8B
0x14001dd80  movzx   esi, si
0x14001dd83  or      esi, 80070000h
0x14001dd89  test    esi, esi
0x14001dd8b  js      loc_14001DF24
0x14001dd91  test    r14b, r14b
0x14001dd94  jnz     loc_14001DE53
0x14001dd9a  mov     cl, 2
0x14001dd9c  call    ?ReportUsageIfAppropriate@Triggers@MobilityExperience@@YAJW4MobilityExperienceUsageType@12@@Z; MobilityExperience::Triggers::ReportUsageIfAppropriate(MobilityExperience::Triggers::MobilityExperienceUsageType)
0x14001dda1  test    eax, eax
0x14001dda3  js      loc_14001DF44
0x14001dda9  mov     rcx, [rdi+8]; hWnd
0x14001ddad  cmp     rbx, 7
0x14001ddb1  mov     r8, r12
0x14001ddb4  mov     edx, 581h; Msg
0x14001ddb9  setz    r8b; wParam
0x14001ddbd  xor     r9d, r9d; lParam
0x14001ddc0  call    cs:__imp_PostMessageW
0x14001ddc7  nop     dword ptr [rax+rax+00h]
0x14001ddcc  cmp     rbx, 8
0x14001ddd0  jz      short loc_14001DE13
0x14001ddd2  cmp     rbx, 2
0x14001ddd6  jz      short loc_14001DDDE
0x14001ddd8  cmp     rbx, 7
0x14001dddc  jnz     short loc_14001DE25
0x14001ddde  mov     [rdi+1F4h], r12d
0x14001dde5  jmp     short loc_14001DE25
0x14001dde7  mov     rcx, [rdi+428h]
0x14001ddee  mov     rax, [rcx]
0x14001ddf1  mov     rax, [rax+0F0h]
0x14001ddf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ddfd  call    cs:__imp_SHUpdateRecycleBinIcon
0x14001de04  nop     dword ptr [rax+rax+00h]
0x14001de09  call    ?_NotifyCDBurnSessionChange@CTray@@IEAAXXZ; CTray::_NotifyCDBurnSessionChange(void)
0x14001de0e  cmp     rbx, r13
0x14001de11  jnz     short loc_14001DDCC
0x14001de13  call    cs:__imp_GetCurrentThreadId
0x14001de1a  nop     dword ptr [rax+rax+00h]
0x14001de1f  mov     [rdi+1F4h], eax
0x14001de25  mov     rax, r13
0x14001de28  mov     rcx, [rbp+3C0h+var_40]
0x14001de2f  xor     rcx, rsp; StackCookie
0x14001de32  call    __security_check_cookie
0x14001de37  mov     rbx, [rsp+4C0h+arg_18]
0x14001de3f  add     rsp, 490h
0x14001de46  pop     r15
0x14001de48  pop     r14
0x14001de4a  pop     r13
0x14001de4c  pop     r12
0x14001de4e  pop     rdi
0x14001de4f  pop     rsi
0x14001de50  pop     rbp
0x14001de51  retn
0x14001de53  lea     rdx, aSettimerforana; "SetTimerForAnaheimPostInstallPromotionS"...
0x14001de5a  lea     rcx, [rsp+4C0h+SubKey]; struct wil::details::IFailureCallback *
0x14001de5f  call    ??0?$ActivityBase@VAnaheimPromotionSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14001de64  lea     rsi, ??_7SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger@AnaheimPromotionSoftLandingTelemetry@@6B@; const AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger::`vftable'
0x14001de6b  lea     rcx, [rsp+4C0h+SubKey]; this
0x14001de70  mov     qword ptr [rsp+4C0h+SubKey], rsi
0x14001de75  call    ?StartActivity@SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger@AnaheimPromotionSoftLandingTelemetry@@QEAAXXZ; AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPostInstallPromotionSoftLandingTrigger::StartActivity(void)
0x14001de7a  movsd   xmm0, cs:__real@40a7700000000000
0x14001de82  call    _o_ceil_0
0x14001de87  mov     rcx, [rdi+8]; hWnd
0x14001de8b  mov     r8d, 0EA60h; uElapse
0x14001de91  cvttsd2si rax, xmm0
0x14001de96  cmp     eax, r15d
0x14001de99  cmovb   r15d, eax
0x14001de9d  xor     r9d, r9d; lpTimerFunc
0x14001dea0  mov     dword ptr [rsp+4C0h+phkResult], r15d; uToleranceDelay
0x14001dea5  lea     edx, [r9+1Ch]; nIDEvent
0x14001dea9  call    cs:__imp_SetCoalescableTimer
0x14001deb0  nop     dword ptr [rax+rax+00h]
0x14001deb5  lea     rcx, [rsp+4C0h+SubKey]
0x14001deba  call    ?Stop@?$ActivityBase@VAnaheimPromotionSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14001debf  lea     rcx, [rsp+4C0h+SubKey]
0x14001dec4  mov     qword ptr [rsp+4C0h+SubKey], rsi
0x14001dec9  call    ?Destroy@?$ActivityBase@VAnaheimPromotionSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14001dece  lea     rcx, [rbp+3C0h+var_340]; this
0x14001ded5  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x14001deda  lea     rcx, [rbp+3C0h+var_348]
0x14001dede  call    ?reset@?$shared_object@V?$ActivityData@VAnaheimPromotionSoftLandingLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAnaheimPromotionSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnaheimPromotionSoftLandingLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x14001dee3  lea     rcx, [rsp+4C0h+var_458]
0x14001dee8  call    ??1?$ActivityData@VAnaheimPromotionSoftLandingLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAnaheimPromotionSoftLandingLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AnaheimPromotionSoftLandingLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnaheimPromotionSoftLandingLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<AnaheimPromotionSoftLandingLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x14001deed  jmp     loc_14001DD9A
0x14001def2  cmp     [rdi+0E4h], r12d
0x14001def9  jnz     loc_14001DDA9
0x14001deff  mov     rcx, cs:WNF_SHEL_DEVICE_LOCKED
0x14001df06  xor     r9d, r9d
0x14001df09  xor     r8d, r8d
0x14001df0c  mov     [rsp+4C0h+phkResult], r12
0x14001df11  xor     edx, edx
0x14001df13  call    cs:__imp_RtlPublishWnfStateData
0x14001df1a  nop     dword ptr [rax+rax+00h]
0x14001df1f  jmp     loc_14001DDA9
0x14001df24  mov     rcx, [rbp+3C8h]; this
0x14001df2b  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14001df32  mov     r9d, esi; char *
0x14001df35  mov     edx, 1398h; void *
0x14001df3a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001df3f  jmp     loc_14001DD91
0x14001df44  mov     rcx, [rbp+3C8h]; this
0x14001df4b  lea     r8, aPcshellShellEx_7; "pcshell\\shell\\explorer\\tray.cpp"
0x14001df52  mov     r9d, eax; char *
0x14001df55  mov     edx, 13A5h; void *
0x14001df5a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001df5f  jmp     loc_14001DDA9
0x14001df64  mov     r9d, r8d
0x14001df67  lea     rdx, Explorer_SessionChangeMessage_Info
0x14001df6e  mov     r8d, ebx
0x14001df71  call    McTemplateU0qq_EventWriteTransfer
0x14001df76  jmp     loc_14001DB49
0x14001df7b  cmp     rbx, 7
0x14001df7f  ja      loc_14001DB8C
0x14001df85  mov     eax, 94h
0x14001df8a  bt      rax, rbx
0x14001df8e  jnb     loc_14001DB82
0x14001df94  mov     [rdi+1DCh], r12d
0x14001df9b  jmp     loc_14001DB82
0x14001dfa0  lea     r8, [rbp+3C0h+pszPath]; unsigned __int16 *
0x14001dfa7  lea     rdx, [rsp+4C0h+SubKey]; HKEY
0x14001dfac  call    ?GetInstalledInfo@Private@BrowserChannels@@YA_NPEAUHKEY__@@PEAG1KPEAUInfo@2@@Z; BrowserChannels::Private::GetInstalledInfo(HKEY__ *,ushort *,ushort *,ulong,BrowserChannels::Info *)
0x14001dfb1  mov     r14b, al
0x14001dfb4  mov     rcx, 0FFFFFFFF80000001h
0x14001dfbb  jmp     loc_14001DCD9
0x14001dfc0  lea     rax, [rsp+4C0h+var_470]
0x14001dfc5  mov     [rsp+4C0h+var_470], r12d
0x14001dfca  lea     r8, aExcludedfromst; "ExcludedFromStableAnaheimDownloadPromot"...
0x14001dfd1  mov     [rsp+4C0h+phkResult], rax; int *
0x14001dfd6  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x14001dfdb  test    eax, eax
0x14001dfdd  js      short loc_14001DFEA
0x14001dfdf  cmp     [rsp+4C0h+var_470], r12d
0x14001dfe4  jnz     loc_14001DD91
0x14001dfea  mov     esi, 3
0x14001dfef  mov     ecx, r13d
0x14001dff2  mov     edx, esi
0x14001dff4  call    ?GetInstalledBrowserChannelInfo@@YA_NW4ChannelId@BrowserChannels@@W4InstallationLevel@2@PEAUInfo@2@@Z; GetInstalledBrowserChannelInfo(BrowserChannels::ChannelId,BrowserChannels::InstallationLevel,BrowserChannels::Info *)
0x14001dff9  test    al, al
0x14001dffb  jnz     short loc_14001E01B
0x14001dffd  mov     edx, esi
0x14001dfff  lea     ecx, [rsi-1]
0x14001e002  call    ?GetInstalledBrowserChannelInfo@@YA_NW4ChannelId@BrowserChannels@@W4InstallationLevel@2@PEAUInfo@2@@Z; GetInstalledBrowserChannelInfo(BrowserChannels::ChannelId,BrowserChannels::InstallationLevel,BrowserChannels::Info *)
0x14001e007  test    al, al
0x14001e009  jnz     short loc_14001E01B
0x14001e00b  mov     edx, esi
0x14001e00d  mov     ecx, esi
0x14001e00f  call    ?GetInstalledBrowserChannelInfo@@YA_NW4ChannelId@BrowserChannels@@W4InstallationLevel@2@PEAUInfo@2@@Z; GetInstalledBrowserChannelInfo(BrowserChannels::ChannelId,BrowserChannels::InstallationLevel,BrowserChannels::Info *)
0x14001e014  mov     esi, r12d
0x14001e017  test    al, al
0x14001e019  jz      short loc_14001E01E
0x14001e01b  mov     esi, r13d
0x14001e01e  lea     rcx, [rsp+4C0h+SubKey]; this
0x14001e023  call    ??$Start@$$V@SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger@AnaheimPromotionSoftLandingTelemetry@@SA?AV01@XZ; AnaheimPromotionSoftLandingTelemetry::SetTimerForAnaheimPreInstallPromotionSoftLandingTrigger::Start<>(void)
0x14001e028  movsd   xmm0, cs:__real@40a7700000000000
0x14001e030  call    _o_ceil_0
0x14001e035  cvttsd2si rax, xmm0
0x14001e03a  mov     ecx, r15d
0x14001e03d  mov     r8d, 0EA60h; uElapse
0x14001e043  cmp     eax, r15d
0x14001e046  cmovb   ecx, eax
0x14001e049  xor     r9d, r9d; lpTimerFunc
0x14001e04c  mov     dword ptr [rsp+4C0h+phkResult], ecx; uToleranceDelay
0x14001e050  mov     rcx, [rdi+8]; hWnd
0x14001e054  lea     edx, [r9+1Ch]; nIDEvent
0x14001e058  call    cs:__imp_SetCoalescableTimer
  ... truncated ...
```
