# Microsoft::IoT::ShellExtension::CCBTLauncher::CreateCBTLauncher(Microsoft::IoT::ShellExtension::ILauncherControl *,std::shared_ptr<Microsoft::IoT::Utility::MTAThreadPool> &,ulong,bool,Microsoft::IoT::ShellExtension::CCBTLauncher * *)

- ea: `0x180011290`
- end: `0x18001144c`
- name: `?CreateCBTLauncher@CCBTLauncher@ShellExtension@IoT@Microsoft@@SAJPEAUILauncherControl@234@AEAV?$shared_ptr@VMTAThreadPool@Utility@IoT@Microsoft@@@std@@K_NPEAPEAV1234@@Z`
- size: `444`
- prototype: `__int64 __fastcall(__int64, int, int, const char *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000bb44`

## callees

- `0x180002b10`
- `0x180008378`
- `0x18000854c`
- `0x1800091c4`
- `0x18000ba64`
- `0x18000bea0`
- `0x18000c3b0`
- `0x18000c3d4`
- `0x18000f4dc`
- `0x180010558`
- `0x1800106a4`
- `0x180011290`
- `0x18001202c`
- `0x1800139f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011353`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011353`

## string_xrefs

- `0x180011345`: `Software\Microsoft\Windows NT\CurrentVersion\Winlogon\IoTShellExtension\CBTConfig`
- `0x1800112f2`: `BackgroundTaskLauncherCreation`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::ShellExtension::CCBTLauncher::CreateCBTLauncher(
        __int64 a1,
        int a2,
        int a3,
        const char *a4,
        _QWORD *a5)
{
  _QWORD *v6; // rbx
  Microsoft::IoT::ShellExtension::RetryParameters *v7; // rcx
  volatile int *v8; // rdx
  const char *v9; // r9
  const char *v10; // r9
  int phkResult; // [rsp+20h] [rbp-1D8h]
  int v13; // [rsp+30h] [rbp-1C8h] BYREF
  char *v14; // [rsp+38h] [rbp-1C0h]
  __int64 v15; // [rsp+40h] [rbp-1B8h] BYREF
  HKEY v16; // [rsp+48h] [rbp-1B0h] BYREF
  wil::ResultException *v17[2]; // [rsp+50h] [rbp-1A8h] BYREF
  char v18; // [rsp+60h] [rbp-198h]
  _QWORD v19[42]; // [rsp+70h] [rbp-188h] BYREF
  std::bad_alloc *v20; // [rsp+1C0h] [rbp-38h] BYREF
  std::invalid_argument *v21; // [rsp+1C8h] [rbp-30h] BYREF
  std::range_error *v22; // [rsp+1D0h] [rbp-28h] BYREF
  std::runtime_error *v23; // [rsp+1D8h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]
  __int64 v25; // [rsp+200h] [rbp+8h] BYREF
  int v26; // [rsp+210h] [rbp+18h] BYREF

  v26 = a3;
  v25 = a1;
  v6 = a5;
  LOBYTE(v13) = 1;
  *a5 = 0;
  if ( !a1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x33D,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      a4);
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v19,
    "BackgroundTaskLauncherCreation");
  v19[0] = &Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLauncherCreation::`vftable';
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLauncherCreation::StartActivity((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLauncherCreation *)v19);
  v17[1] = (wil::ResultException *)v19;
  v18 = 1;
  v16 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon\\IoTShellExtension\\CBTConfig",
          0,
          0x20019u,
          &v16) )
    Microsoft::IoT::ShellExtension::RetryParameters::LoadRegistryOverrides(v7, v16);
  try
  {
    Microsoft::WRL::Details::Make<Microsoft::IoT::ShellExtension::CCBTLauncher,Microsoft::IoT::ShellExtension::ILauncherControl * &,std::shared_ptr<Microsoft::IoT::Utility::MTAThreadPool> &,unsigned long &,bool &>(
      (unsigned int)&v15,
      (unsigned int)&v25,
      a2,
      (unsigned int)&v26,
      (__int64)&v13);
    if ( !v15 )
      wil::details::in1diag3::_FailFast_NullAlloc(
        retaddr,
        (void *)0x345,
        (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
        v9);
    Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v15 + 44), v8);
    *v6 = v15;
    LODWORD(v14) = 0;
    Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(&v15);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v16);
  }
  catch ( wil::ResultException *v17 )
  {
    LODWORD(v14) = *((_DWORD *)v17[0] + 8);
  }
  catch ( std::bad_alloc *v20 )
  {
    LODWORD(v14) = -2147024882;
  }
  catch ( std::invalid_argument *v21 )
  {
    LODWORD(v14) = -2147024809;
  }
  catch ( std::range_error *v22 )
  {
    LODWORD(v14) = -2147483637;
  }
  catch ( std::runtime_error *v23 )
  {
    LODWORD(v14) = -2147467259;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x34A,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      v10);
  }
  if ( (int)v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x34A,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\shellcbt.cpp",
      (const char *)(unsigned int)v14,
      phkResult);
  wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19);
  Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLauncherCreation::~BackgroundTaskLauncherCreation((Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLauncherCreation *)v19);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180011290  mov     [rsp+arg_18], rbx
0x180011295  mov     [rsp+arg_10], r8d
0x18001129a  mov     [rsp+arg_0], rcx
0x18001129f  push    rdi
0x1800112a0  sub     rsp, 1F0h
0x1800112a7  mov     rax, cs:__security_cookie
0x1800112ae  xor     rax, rsp
0x1800112b1  mov     [rsp+1F8h+var_18], rax
0x1800112b9  mov     rdi, rdx
0x1800112bc  mov     rbx, [rsp+1F8h+arg_20]
0x1800112c4  mov     byte ptr [rsp+1F8h+var_1C8], 1
0x1800112c9  mov     qword ptr [rbx], 0
0x1800112d0  mov     rax, [rsp+1F8h]
0x1800112d8  test    rcx, rcx
0x1800112db  jnz     short loc_1800112F2
0x1800112dd  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800112e4  mov     edx, 33Dh; void *
0x1800112e9  mov     rcx, rax; this
0x1800112ec  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800112f2  lea     rdx, aBackgroundtask_1; "BackgroundTaskLauncherCreation"
0x1800112f9  lea     rcx, [rsp+1F8h+var_188]
0x1800112fe  call    ??0?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011303  lea     rax, ??_7BackgroundTaskLauncherCreation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@6B@; const Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLauncherCreation::`vftable'
0x18001130a  mov     [rsp+1F8h+var_188], rax
0x18001130f  lea     rcx, [rsp+1F8h+var_188]; this
0x180011314  call    ?StartActivity@BackgroundTaskLauncherCreation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAAXXZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLauncherCreation::StartActivity(void)
0x180011319  nop
0x18001131a  lea     rax, [rsp+1F8h+var_188]
0x18001131f  mov     [rsp+1F8h+var_1A0], rax
0x180011324  mov     [rsp+1F8h+var_198], 1
0x180011329  mov     [rsp+1F8h+var_1B0], 0
0x180011332  lea     rax, [rsp+1F8h+var_1B0]
0x180011337  mov     qword ptr [rsp+1F8h+phkResult], rax; phkResult
0x18001133c  mov     r9d, 20019h; samDesired
0x180011342  xor     r8d, r8d; ulOptions
0x180011345  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001134c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011353  call    cs:__imp_RegOpenKeyExW
0x180011359  test    eax, eax
0x18001135b  jnz     short loc_180011367
0x18001135d  mov     rdx, [rsp+1F8h+var_1B0]; HKEY
0x180011362  call    ?LoadRegistryOverrides@RetryParameters@ShellExtension@IoT@Microsoft@@QEAAXPEAUHKEY__@@@Z; Microsoft::IoT::ShellExtension::RetryParameters::LoadRegistryOverrides(HKEY__ *)
0x180011367  lea     rax, [rsp+1F8h+var_1C8]
0x18001136c  mov     qword ptr [rsp+1F8h+phkResult], rax; int
0x180011371  lea     r9, [rsp+1F8h+arg_10]
0x180011379  mov     r8, rdi
0x18001137c  lea     rdx, [rsp+1F8h+arg_0]
0x180011384  lea     rcx, [rsp+1F8h+var_1B8]
0x180011389  call    ??$Make@VCCBTLauncher@ShellExtension@IoT@Microsoft@@AEAPEAUILauncherControl@234@AEAV?$shared_ptr@VMTAThreadPool@Utility@IoT@Microsoft@@@std@@AEAKAEA_N@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@12@AEAPEAUILauncherControl@ShellExtension@IoT@2@AEAV?$shared_ptr@VMTAThreadPool@Utility@IoT@Microsoft@@@std@@AEAKAEA_N@Z; Microsoft::WRL::Details::Make<Microsoft::IoT::ShellExtension::CCBTLauncher,Microsoft::IoT::ShellExtension::ILauncherControl * &,std::shared_ptr<Microsoft::IoT::Utility::MTAThreadPool> &,ulong &,bool &>(Microsoft::IoT::ShellExtension::ILauncherControl * &,std::shared_ptr<Microsoft::IoT::Utility::MTAThreadPool> &,ulong &,bool &)
0x18001138e  mov     rax, [rsp+1F8h]
0x180011396  mov     rcx, [rsp+1F8h+var_1B8]
0x18001139b  test    rcx, rcx
0x18001139e  jnz     short loc_1800113B5
0x1800113a0  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x1800113a7  mov     edx, 345h; void *
0x1800113ac  mov     rcx, rax; this
0x1800113af  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x1800113b5  add     rcx, 2Ch ; ','; this
0x1800113b9  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x1800113be  mov     rcx, [rsp+1F8h+var_1B8]
0x1800113c3  mov     [rbx], rcx
0x1800113c6  mov     dword ptr [rsp+1F8h+var_1C0], 0
0x1800113ce  lea     rcx, [rsp+1F8h+var_1B8]
0x1800113d3  call    ?InternalRelease@?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>::InternalRelease(void)
0x1800113d8  nop
0x1800113d9  lea     rcx, [rsp+1F8h+var_1B0]
0x1800113de  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800113e3  nop
0x1800113e4  jmp     short loc_1800113EE
0x1800113e6  jmp     short loc_1800113EE
0x1800113e8  jmp     short loc_1800113EE
0x1800113ea  jmp     short loc_1800113EE
0x1800113ec  jmp     short $+2
0x1800113ee  mov     rcx, [rsp+1F8h]; this
0x1800113f6  mov     r9d, dword ptr [rsp+1F8h+var_1C0]; char *
0x1800113fb  test    r9d, r9d
0x1800113fe  jns     short loc_180011412
0x180011400  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x180011407  mov     edx, 34Ah; void *
0x18001140c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180011411  nop
0x180011412  lea     rcx, [rsp+1F8h+var_188]
0x180011417  call    ?Stop@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001141c  nop
0x18001141d  lea     rcx, [rsp+1F8h+var_188]; this
0x180011422  call    ??1BackgroundTaskLauncherCreation@CTelemetryProvider@ShellExtension@IoT@Microsoft@@QEAA@XZ; Microsoft::IoT::ShellExtension::CTelemetryProvider::BackgroundTaskLauncherCreation::~BackgroundTaskLauncherCreation(void)
0x180011427  mov     eax, dword ptr [rsp+1F8h+var_1C0]
0x18001142b  mov     rcx, [rsp+1F8h+var_18]
0x180011433  xor     rcx, rsp; StackCookie
0x180011436  call    __security_check_cookie
0x18001143b  mov     rbx, [rsp+1F8h+arg_18]
0x180011443  add     rsp, 1F0h
0x18001144a  pop     rdi
0x18001144b  retn
```
