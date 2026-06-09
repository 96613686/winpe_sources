# DesktopShellHostExtensions::RestartShell(void)

- ea: `0x1800260d8`
- end: `0x1800263f7`
- name: `?RestartShell@DesktopShellHostExtensions@@AEAAXXZ`
- size: `799`
- prototype: `void __fastcall(DesktopShellHostExtensions *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027090`

## callees

- `0x1800087a0`
- `0x1800087e0`
- `0x180008b58`
- `0x18000aeb0`
- `0x18000bdf0`
- `0x180015618`
- `0x18001a18c`
- `0x18001a7c8`
- `0x18001a918`
- `0x18001cef8`
- `0x18002052c`
- `0x1800260d8`
- `0x18002661c`
- `0x180028bf8`
- `0x18002a3d0`
- `0x18002af50`
- `0x180034e40`
- `0x180037e4c`
- `0x180037f78`
- `0x180039420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800262e7`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800262e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002630e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002630e`

## string_xrefs

- `0x18002623d`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`
- `0x1800262f8`: `shell\onecore\desktopshellext\lib\desktophostextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall DesktopShellHostExtensions::RestartShell(DesktopShellHostExtensions *this)
{
  void *v2; // rax
  __int64 v3; // rax
  _QWORD *v4; // r9
  int v5; // eax
  const WCHAR *lpCurrentDirectory; // rax
  const WCHAR *v7; // rcx
  const char *v8; // r9
  BOOL bInheritHandles; // [rsp+20h] [rbp-E0h]
  LPWSTR lpCommandLine[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+60h] [rbp-A0h]
  __int128 v12; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v15[42]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v16[2]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v17; // [rsp+270h] [rbp+170h]
  unsigned __int64 v18; // [rsp+278h] [rbp+178h]
  LPCWSTR lpApplicationName[2]; // [rsp+280h] [rbp+180h] BYREF
  __int128 v20; // [rsp+290h] [rbp+190h]
  _OWORD v21[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  LPCWSTR v22[4]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _QWORD v23[42]; // [rsp+2E0h] [rbp+1E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+348h]

  wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v23,
    "RestartShell");
  v23[0] = &DesktopShellHostExtensionsTelemetry::RestartShell::`vftable';
  DesktopShellHostExtensionsTelemetry::RestartShell::StartActivity((DesktopShellHostExtensionsTelemetry::RestartShell *)v23);
  GetShellExecutableName(v16);
  GetSystemRootDirectory(v22);
  v2 = (void *)std::operator+<unsigned short>(v21, v22);
  v3 = std::wstring::_Append<unsigned short>(v2);
  *(_OWORD *)lpApplicationName = 0;
  v20 = 0;
  *(_OWORD *)lpApplicationName = *(_OWORD *)v3;
  v20 = *(_OWORD *)(v3 + 16);
  *(_QWORD *)(v3 + 16) = 0;
  *(_QWORD *)(v3 + 24) = 7;
  *(_WORD *)v3 = 0;
  std::wstring::~wstring(v21);
  *(_OWORD *)lpCommandLine = 0;
  v11 = 0;
  if ( v17 != -20 )
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(lpCommandLine, v17 + 20);
  v4 = v16;
  if ( v18 > 7 )
    v4 = (_QWORD *)v16[0];
  v5 = StringCchPrintfW(lpCommandLine[0], lpCommandLine[1] - lpCommandLine[0], L"%s /LOADSAVEDWINDOWS", v4);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B4,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
      (const char *)(unsigned int)v5,
      bInheritHandles);
  CreateShellLauncherReadyEvent(&v12);
  *(_QWORD *)&StartupInfo.cb = 104;
  memset_0(&StartupInfo.lpReserved, 0, 0x60u);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  lpCurrentDirectory = (const WCHAR *)v22;
  if ( v22[3] > (LPCWSTR)7 )
    lpCurrentDirectory = v22[0];
  v7 = (const WCHAR *)lpApplicationName;
  if ( *((_QWORD *)&v20 + 1) > 7u )
    v7 = lpApplicationName[0];
  if ( !CreateProcessW(v7, lpCommandLine[0], 0, 0, 0, 0x20u, 0, lpCurrentDirectory, &StartupInfo, &ProcessInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\desktophostextensions.cpp",
      v8);
  CloseHandle(ProcessInformation.hThread);
  v21[0] = 0;
  if ( *((_QWORD *)&v12 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v12 + 1) + 8LL));
  v21[0] = v12;
  wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    v23);
  v15[0] = &DesktopShellHostExtensionsTelemetry::RestartShell::`vftable';
  DesktopShellHostExtensions::MonitorShellStartupAsync<DesktopShellHostExtensionsTelemetry::RestartShell>(
    this,
    v15,
    v21,
    ProcessInformation.hProcess);
  __1__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA_XZ(&v12);
  if ( lpCommandLine[0] )
  {
    std::_Deallocate<16>(lpCommandLine[0], 2 * ((signed __int64)(v11 - (unsigned __int64)lpCommandLine[0]) >> 1));
    *(_OWORD *)lpCommandLine = 0;
    v11 = 0;
  }
  std::wstring::~wstring(lpApplicationName);
  std::wstring::~wstring(v22);
  std::wstring::~wstring(v16);
  DesktopShellHostExtensionsTelemetry::RestartShell::~RestartShell((DesktopShellHostExtensionsTelemetry::RestartShell *)v23);
}

```

## disassembly

```asm
0x1800260d8  mov     [rsp-8+arg_8], rbx
0x1800260dd  mov     [rsp-8+arg_10], r14
0x1800260e2  push    rbp
0x1800260e3  lea     rbp, [rsp-340h]
0x1800260eb  sub     rsp, 440h
0x1800260f2  mov     rax, cs:__security_cookie
0x1800260f9  xor     rax, rsp
0x1800260fc  mov     [rbp+340h+var_10], rax
0x180026103  mov     rbx, rcx
0x180026106  lea     rdx, aRestartshell; "RestartShell"
0x18002610d  lea     rcx, [rbp+340h+var_160]
0x180026114  call    ??0?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180026119  lea     r14, ??_7RestartShell@DesktopShellHostExtensionsTelemetry@@6B@; const DesktopShellHostExtensionsTelemetry::RestartShell::`vftable'
0x180026120  mov     [rbp+340h+var_160], r14
0x180026127  lea     rcx, [rbp+340h+var_160]; this
0x18002612e  call    ?StartActivity@RestartShell@DesktopShellHostExtensionsTelemetry@@QEAAXXZ; DesktopShellHostExtensionsTelemetry::RestartShell::StartActivity(void)
0x180026133  nop
0x180026134  lea     rcx, [rbp+340h+var_1E0]
0x18002613b  call    ?GetShellExecutableName@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetShellExecutableName(void)
0x180026140  nop
0x180026141  lea     rcx, [rbp+340h+var_180]
0x180026148  call    ?GetSystemRootDirectory@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetSystemRootDirectory(void)
0x18002614d  nop
0x18002614e  lea     rdx, [rbp+340h+var_180]
0x180026155  lea     rcx, [rbp+340h+var_1A0]
0x18002615c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180026161  nop
0x180026162  lea     rdx, [rbp+340h+var_1E0]
0x180026169  cmp     [rbp+340h+var_1C8], 7
0x180026171  cmova   rdx, [rbp+340h+var_1E0]
0x180026179  mov     r8, [rbp+340h+var_1D0]
0x180026180  mov     rcx, rax; Src
0x180026183  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180026188  xorps   xmm0, xmm0
0x18002618b  movups  xmmword ptr [rbp+340h+lpApplicationName], xmm0
0x180026192  xorps   xmm1, xmm1
0x180026195  movdqu  [rbp+340h+var_1B0], xmm1
0x18002619d  movups  xmm0, xmmword ptr [rax]
0x1800261a0  movups  xmmword ptr [rbp+340h+lpApplicationName], xmm0
0x1800261a7  movups  xmm1, xmmword ptr [rax+10h]
0x1800261ab  movups  [rbp+340h+var_1B0], xmm1
0x1800261b2  mov     qword ptr [rax+10h], 0
0x1800261ba  mov     qword ptr [rax+18h], 7
0x1800261c2  xor     ecx, ecx
0x1800261c4  mov     [rax], cx
0x1800261c7  lea     rcx, [rbp+340h+var_1A0]
0x1800261ce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800261d3  xorps   xmm0, xmm0
0x1800261d6  movdqu  xmmword ptr [rsp+440h+lpCommandLine], xmm0
0x1800261dc  mov     [rsp+440h+var_3E0], 0
0x1800261e5  mov     rdx, [rbp+340h+var_1D0]
0x1800261ec  add     rdx, 14h
0x1800261f0  jz      short loc_1800261FC
0x1800261f2  lea     rcx, [rsp+440h+lpCommandLine]
0x1800261f7  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800261fc  lea     r9, [rbp+340h+var_1E0]
0x180026203  cmp     [rbp+340h+var_1C8], 7
0x18002620b  cmova   r9, [rbp+340h+var_1E0]
0x180026213  mov     rcx, [rsp+440h+lpCommandLine]; unsigned __int16 *
0x180026218  mov     rdx, [rsp+440h+lpCommandLine+8]
0x18002621d  sub     rdx, rcx
0x180026220  sar     rdx, 1; unsigned __int64
0x180026223  lea     r8, aSLoadsavedwind; "%s /LOADSAVEDWINDOWS"
0x18002622a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002622f  mov     rcx, [rbp+348h]; this
0x180026236  test    eax, eax
0x180026238  jns     short loc_18002624F
0x18002623a  mov     r9d, eax; char *
0x18002623d  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x180026244  mov     edx, 1B4h; void *
0x180026249  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002624f  lea     rcx, [rsp+440h+var_3D0]
0x180026254  call    ?CreateShellLauncherReadyEvent@@YA?AV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@XZ
0x180026259  nop
0x18002625a  mov     qword ptr [rbp+340h+StartupInfo.cb], 68h ; 'h'
0x180026262  xor     edx, edx; Val
0x180026264  lea     r8d, [rdx+60h]; Size
0x180026268  lea     rcx, [rbp+340h+StartupInfo.lpReserved]; void *
0x18002626c  call    memset_0
0x180026271  xorps   xmm0, xmm0
0x180026274  xor     eax, eax
0x180026276  movups  xmmword ptr [rbp+340h+ProcessInformation.hProcess], xmm0
0x18002627a  mov     qword ptr [rbp+340h+ProcessInformation.dwProcessId], rax
0x18002627e  lea     rax, [rbp+340h+var_180]
0x180026285  cmp     [rbp+340h+var_168], 7
0x18002628d  cmova   rax, [rbp+340h+var_180]
0x180026295  lea     rcx, [rbp+340h+lpApplicationName]
0x18002629c  cmp     qword ptr [rbp+340h+var_1B0+8], 7
0x1800262a4  cmova   rcx, [rbp+340h+lpApplicationName]; lpApplicationName
0x1800262ac  lea     rdx, [rbp+340h+ProcessInformation]
0x1800262b0  mov     [rsp+440h+lpProcessInformation], rdx; lpProcessInformation
0x1800262b5  lea     rdx, [rbp+340h+StartupInfo]
0x1800262b9  mov     [rsp+440h+lpStartupInfo], rdx; lpStartupInfo
0x1800262be  mov     [rsp+440h+lpCurrentDirectory], rax; lpCurrentDirectory
0x1800262c3  mov     [rsp+440h+lpEnvironment], 0; lpEnvironment
0x1800262cc  mov     [rsp+440h+dwCreationFlags], 20h ; ' '; dwCreationFlags
0x1800262d4  mov     [rsp+440h+bInheritHandles], 0; bInheritHandles
0x1800262dc  xor     r9d, r9d; lpThreadAttributes
0x1800262df  xor     r8d, r8d; lpProcessAttributes
0x1800262e2  mov     rdx, [rsp+440h+lpCommandLine]; lpCommandLine
0x1800262e7  call    cs:__imp_CreateProcessW
0x1800262ed  mov     rcx, [rbp+348h]; this
0x1800262f4  test    eax, eax
0x1800262f6  jnz     short loc_18002630A
0x1800262f8  lea     r8, aShellOnecoreDe_1; "shell\\onecore\\desktopshellext\\lib\\d"...
0x1800262ff  mov     edx, 1BBh; void *
0x180026304  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002630a  mov     rcx, [rbp+340h+ProcessInformation.hThread]; hObject
0x18002630e  call    cs:__imp_CloseHandle
0x180026314  xorps   xmm0, xmm0
0x180026317  movdqa  [rbp+340h+var_1A0], xmm0
0x18002631f  mov     rax, qword ptr [rsp+440h+var_3D0+8]
0x180026324  test    rax, rax
0x180026327  jz      short loc_18002632D
0x180026329  lock inc dword ptr [rax+8]
0x18002632d  movaps  xmm0, [rsp+440h+var_3D0]
0x180026332  movdqa  [rbp+340h+var_1A0], xmm0
0x18002633a  lea     rdx, [rbp+340h+var_160]
0x180026341  lea     rcx, [rbp+340h+var_330]
0x180026345  call    ??0?$ActivityBase@VDesktopShellHostExtensionsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@AEBV01@@Z; wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<DesktopShellHostExtensionsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType> const &)
0x18002634a  mov     [rbp+340h+var_330], r14
0x18002634e  mov     r9, [rbp+340h+ProcessInformation.hProcess]
0x180026352  lea     r8, [rbp+340h+var_1A0]
0x180026359  lea     rdx, [rbp+340h+var_330]
0x18002635d  mov     rcx, rbx
0x180026360  call    ??$MonitorShellStartupAsync@VRestartShell@DesktopShellHostExtensionsTelemetry@@@DesktopShellHostExtensions@@AEAAXVRestartShell@DesktopShellHostExtensionsTelemetry@@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@PEAX@Z
0x180026365  nop
0x180026366  lea     rcx, [rsp+440h+var_3D0]
0x18002636b  call    ??1?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@XZ
0x180026370  nop
0x180026371  mov     rcx, [rsp+440h+lpCommandLine]
0x180026376  test    rcx, rcx
0x180026379  jz      short loc_1800263A0
0x18002637b  mov     rdx, [rsp+440h+var_3E0]
0x180026380  sub     rdx, rcx
0x180026383  sar     rdx, 1
0x180026386  add     rdx, rdx
0x180026389  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002638e  xorps   xmm0, xmm0
0x180026391  movdqu  xmmword ptr [rsp+440h+lpCommandLine], xmm0
0x180026397  mov     [rsp+440h+var_3E0], 0
0x1800263a0  lea     rcx, [rbp+340h+lpApplicationName]
0x1800263a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800263ac  nop
0x1800263ad  lea     rcx, [rbp+340h+var_180]
0x1800263b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800263b9  nop
0x1800263ba  lea     rcx, [rbp+340h+var_1E0]
0x1800263c1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800263c6  nop
0x1800263c7  lea     rcx, [rbp+340h+var_160]; this
0x1800263ce  call    ??1RestartShell@DesktopShellHostExtensionsTelemetry@@QEAA@XZ; DesktopShellHostExtensionsTelemetry::RestartShell::~RestartShell(void)
0x1800263d3  mov     rcx, [rbp+340h+var_10]
0x1800263da  xor     rcx, rsp; StackCookie
0x1800263dd  call    __security_check_cookie
0x1800263e2  lea     r11, [rsp+440h+var_s0]
0x1800263ea  mov     rbx, [r11+18h]
0x1800263ee  mov     r14, [r11+20h]
0x1800263f2  mov     rsp, r11
0x1800263f5  pop     rbp
0x1800263f6  retn
```
