# CLogonTaskFramework::s_AppResolverWork(CLogonTaskFramework *)

- ea: `0x140045bb0`
- end: `0x140045e93`
- name: `?s_AppResolverWork@CLogonTaskFramework@@CAJPEAV1@@Z`
- size: `739`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140045ac0`
- `0x140159150`

## callees

- `0x140007c08`
- `0x140012594`
- `0x14001b2c8`
- `0x14001d2dc`
- `0x14001d61c`
- `0x14002ab70`
- `0x140045488`
- `0x140045524`
- `0x140045588`
- `0x140045bb0`
- `0x1400aa96c`
- `0x1400acaec`
- `0x1400b3b40`
- `0x1400bba78`
- `0x14010e160`
- `0x1401a91a4`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140045c79`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140045c79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140045dc2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140045dc2`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x140045d55`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x140045d72`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x140045d55`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x140045d72`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140045ca9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140045ca9`

## string_xrefs

- `0x140045cdb`: `shell\lib\logontasks\logontasks.cpp`
- `0x140045e0a`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLogonTaskFramework::s_AppResolverWork(struct CLogonTaskFramework *a1)
{
  ShellVersion *v2; // rcx
  unsigned int ShellVersion; // eax
  unsigned int v4; // ebx
  LSTATUS ValueW; // eax
  bool v6; // sf
  HKEY v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  const unsigned __int16 *v10; // r8
  HRESULT v11; // eax
  unsigned int v12; // ebx
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rdx
  LPVOID v15; // rcx
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-B0h] BYREF
  void **v22; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v23[272]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[8]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v25[48]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v22);
  v22 = &LogonFrameworkTelemetry::AppResolverWork::`vftable';
  wil::ActivityBase<LogonFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivity<LogonFrameworkTelemetry::AllLogonTasks>(
    &v22,
    (char *)a1 + 624);
  LogonFrameworkTelemetry::AppResolverWork::StartActivity((LogonFrameworkTelemetry::AppResolverWork *)&v22);
  ShellVersion = ShellVersion::GetShellVersion(v2);
  v4 = ShellVersion;
  if ( (*((_DWORD *)a1 + 54) & 0x4000) != 0 && ShellVersion == 13 )
    v4 = 0;
  SystemTimeAsFileTime = 0;
  pcbData = 8;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\StartPage",
             L"Start_JumpListModernTime",
             8u,
             0,
             &SystemTimeAsFileTime,
             &pcbData);
  v6 = ValueW < 0;
  if ( ValueW > 0 )
    v6 = 1;
  if ( v6 || pcbData != 8 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v8 = SHRegSetFILETIME(
           v7,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer\\StartPage",
           L"Start_JumpListModernTime",
           &SystemTimeAsFileTime);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCA1,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v8,
        pdwType);
  }
  if ( v4 >= 0xD )
  {
    v9 = 12;
    SHDeleteValueW(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
      L"DefaultStartLayout_UseWin7UpgradeBehavior");
    SHDeleteValueW(
      HKEY_CURRENT_USER,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer",
      L"DefaultStartLayout_UseWin8UpgradeBehavior");
    goto LABEL_20;
  }
  v9 = 76;
  switch ( v4 )
  {
    case 4u:
      v9 = 108;
      v10 = L"DefaultStartLayout_UseWin7UpgradeBehavior";
      goto LABEL_18;
    case 5u:
      v9 = 588;
      goto LABEL_15;
    case 6u:
      v9 = 1100;
LABEL_15:
      v10 = L"DefaultStartLayout_UseWin8UpgradeBehavior";
LABEL_18:
      SHRegSetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer", v10, 1u);
      break;
  }
LABEL_20:
  if ( (*((_BYTE *)a1 + 216) & 2) != 0 && v4 <= 0xB )
    CLogonTaskFramework::s_CleanUpRemovedSystemShortcuts();
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
  v11 = CoCreateInstance(&CLSID_StartMenuCacheAndAppResolver, 0, 3u, &GUID_ba5a92ae_bfd7_4916_854f_6b3a402b84a8, &ppv);
  v12 = v11;
  v13 = retaddr;
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 72LL))(ppv, v9);
    v12 = v11;
    v13 = retaddr;
    if ( v11 >= 0 )
      goto LABEL_28;
    v14 = 3282;
  }
  else
  {
    v14 = 3279;
  }
  wil::details::in1diag3::_Log_Hr(
    v13,
    (void *)v14,
    (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
    (const char *)(unsigned int)v11,
    pdwTypea);
LABEL_28:
  wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v22, v12);
  v15 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v22 = &LogonFrameworkTelemetry::AppResolverWork::`vftable';
  wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v22);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v25);
  wil::details::shared_object<wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v24);
  wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LogonFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>(v23);
  return v12;
}

```

## disassembly

```asm
0x140045bb0  push    rbp
0x140045bb2  push    rbx
0x140045bb3  push    rsi
0x140045bb4  push    rdi
0x140045bb5  push    r13
0x140045bb7  push    r15
0x140045bb9  lea     rbp, [rsp-0C8h]
0x140045bc1  sub     rsp, 1C8h
0x140045bc8  mov     rax, cs:__security_cookie
0x140045bcf  xor     rax, rsp
0x140045bd2  mov     [rbp+0F0h+var_40], rax
0x140045bd9  mov     rsi, rcx
0x140045bdc  lea     rdx, aAppresolverwor; "AppResolverWork"
0x140045be3  lea     rcx, [rsp+1F0h+var_190]; struct wil::details::IFailureCallback *
0x140045be8  call    ??0?$ActivityBase@VLogonFrameworkLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140045bed  lea     r13, ??_7AppResolverWork@LogonFrameworkTelemetry@@6B@; const LogonFrameworkTelemetry::AppResolverWork::`vftable'
0x140045bf4  mov     [rsp+1F0h+var_190], r13
0x140045bf9  lea     rdx, [rsi+270h]
0x140045c00  lea     rcx, [rsp+1F0h+var_190]
0x140045c05  call    ??$SetRelatedActivity@VAllLogonTasks@LogonFrameworkTelemetry@@@?$ActivityBase@VLogonFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBVAllLogonTasks@LogonFrameworkTelemetry@@@Z; wil::ActivityBase<LogonFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivity<LogonFrameworkTelemetry::AllLogonTasks>(LogonFrameworkTelemetry::AllLogonTasks const &)
0x140045c0a  lea     rcx, [rsp+1F0h+var_190]; this
0x140045c0f  call    ?StartActivity@AppResolverWork@LogonFrameworkTelemetry@@QEAAXXZ; LogonFrameworkTelemetry::AppResolverWork::StartActivity(void)
0x140045c14  call    ?GetShellVersion@ShellVersion@@YAKXZ; ShellVersion::GetShellVersion(void)
0x140045c19  mov     ebx, eax
0x140045c1b  test    dword ptr [rsi+0D8h], 4000h
0x140045c25  jz      short loc_140045C2F
0x140045c27  xor     ecx, ecx
0x140045c29  cmp     eax, 0Dh
0x140045c2c  cmovz   ebx, ecx
0x140045c2f  mov     qword ptr [rsp+1F0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140045c38  mov     edi, 8
0x140045c3d  mov     [rsp+1F0h+var_1B0], edi
0x140045c41  lea     rax, [rsp+1F0h+var_1B0]
0x140045c46  mov     [rsp+1F0h+pcbData], rax; pcbData
0x140045c4b  lea     rax, [rsp+1F0h+SystemTimeAsFileTime]
0x140045c50  mov     [rsp+1F0h+pvData], rax; pvData
0x140045c55  mov     [rsp+1F0h+pdwType], 0; int
0x140045c5e  mov     r9d, edi; dwFlags
0x140045c61  lea     r8, aStartJumplistm; "Start_JumpListModernTime"
0x140045c68  lea     rdx, aSoftwareMicros_107; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140045c6f  mov     r15, 0FFFFFFFF80000001h
0x140045c76  mov     rcx, r15; hkey
0x140045c79  call    cs:__imp_RegGetValueW
0x140045c80  nop     dword ptr [rax+rax+00h]
0x140045c85  test    eax, eax
0x140045c87  jle     short loc_140045C93
0x140045c89  movzx   eax, ax
0x140045c8c  or      eax, 80070000h
0x140045c91  test    eax, eax
0x140045c93  js      short loc_140045C9B
0x140045c95  cmp     [rsp+1F0h+var_1B0], edi
0x140045c99  jz      short loc_140045CEC
0x140045c9b  mov     qword ptr [rsp+1F0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140045ca4  lea     rcx, [rsp+1F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140045ca9  call    cs:__imp_GetSystemTimeAsFileTime
0x140045cb0  nop     dword ptr [rax+rax+00h]
0x140045cb5  lea     r9, [rsp+1F0h+SystemTimeAsFileTime]; struct _FILETIME *
0x140045cba  lea     r8, aStartJumplistm; "Start_JumpListModernTime"
0x140045cc1  lea     rdx, aSoftwareMicros_107; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140045cc8  call    ?SHRegSetFILETIME@@YAJPEAUHKEY__@@PEBG1PEBU_FILETIME@@@Z; SHRegSetFILETIME(HKEY__ *,ushort const *,ushort const *,_FILETIME const *)
0x140045ccd  mov     rcx, [rbp+0F8h]; this
0x140045cd4  test    eax, eax
0x140045cd6  jns     short loc_140045CEC
0x140045cd8  mov     r9d, eax; char *
0x140045cdb  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140045ce2  mov     edx, 0CA1h; void *
0x140045ce7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140045cec  cmp     ebx, 0Dh
0x140045cef  jnb     short loc_140045D3F
0x140045cf1  mov     edi, 4Ch ; 'L'
0x140045cf6  mov     eax, ebx
0x140045cf8  sub     eax, 4
0x140045cfb  jz      short loc_140045D1C
0x140045cfd  sub     eax, 1
0x140045d00  jz      short loc_140045D15
0x140045d02  cmp     eax, 1
0x140045d05  jnz     short loc_140045D7E
0x140045d07  mov     edi, 44Ch
0x140045d0c  lea     r8, aDefaultstartla; "DefaultStartLayout_UseWin8UpgradeBehavi"...
0x140045d13  jmp     short loc_140045D28
0x140045d15  mov     edi, 24Ch
0x140045d1a  jmp     short loc_140045D0C
0x140045d1c  mov     edi, 6Ch ; 'l'
0x140045d21  lea     r8, aDefaultstartla_0; "DefaultStartLayout_UseWin7UpgradeBehavi"...
0x140045d28  mov     r9d, 1; unsigned int
0x140045d2e  lea     rdx, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140045d35  mov     rcx, r15; HKEY
0x140045d38  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x140045d3d  jmp     short loc_140045D7E
0x140045d3f  mov     edi, 0Ch
0x140045d44  lea     r8, aDefaultstartla_0; "DefaultStartLayout_UseWin7UpgradeBehavi"...
0x140045d4b  lea     rdx, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140045d52  mov     rcx, r15; hkey
0x140045d55  call    cs:__imp_SHDeleteValueW
0x140045d5c  nop     dword ptr [rax+rax+00h]
0x140045d61  lea     r8, aDefaultstartla; "DefaultStartLayout_UseWin8UpgradeBehavi"...
0x140045d68  lea     rdx, aSoftwareMicros_120; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140045d6f  mov     rcx, r15; hkey
0x140045d72  call    cs:__imp_SHDeleteValueW
0x140045d79  nop     dword ptr [rax+rax+00h]
0x140045d7e  test    byte ptr [rsi+0D8h], 2
0x140045d85  jz      short loc_140045D91
0x140045d87  cmp     ebx, 0Bh
0x140045d8a  ja      short loc_140045D91
0x140045d8c  call    ?s_CleanUpRemovedSystemShortcuts@CLogonTaskFramework@@CAXXZ; CLogonTaskFramework::s_CleanUpRemovedSystemShortcuts(void)
0x140045d91  mov     [rsp+1F0h+ppv], 0
0x140045d9a  lea     rcx, [rsp+1F0h+ppv]
0x140045d9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x140045da4  lea     rax, [rsp+1F0h+ppv]
0x140045da9  mov     [rsp+1F0h+pdwType], rax; int
0x140045dae  lea     r9, _GUID_ba5a92ae_bfd7_4916_854f_6b3a402b84a8; riid
0x140045db5  xor     edx, edx; pUnkOuter
0x140045db7  lea     r8d, [rdx+3]; dwClsContext
0x140045dbb  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x140045dc2  call    cs:__imp_CoCreateInstance
0x140045dc9  nop     dword ptr [rax+rax+00h]
0x140045dce  mov     ebx, eax
0x140045dd0  mov     rcx, [rbp+0F8h]
0x140045dd7  test    eax, eax
0x140045dd9  jns     short loc_140045DE2
0x140045ddb  mov     edx, 0CCFh
0x140045de0  jmp     short loc_140045E07
0x140045de2  mov     rcx, [rsp+1F0h+ppv]
0x140045de7  mov     rax, [rcx]
0x140045dea  mov     edx, edi
0x140045dec  mov     rax, [rax+48h]
0x140045df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045df5  mov     ebx, eax
0x140045df7  mov     rcx, [rbp+0F8h]; this
0x140045dfe  test    eax, eax
0x140045e00  jns     short loc_140045E16
0x140045e02  mov     edx, 0CD2h; void *
0x140045e07  mov     r9d, eax; char *
0x140045e0a  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140045e11  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140045e16  mov     edx, ebx
0x140045e18  lea     rcx, [rsp+1F0h+var_190]
0x140045e1d  call    ?Stop@?$ActivityBase@VLogonFrameworkLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140045e22  nop
0x140045e23  mov     rcx, [rsp+1F0h+ppv]
0x140045e28  test    rcx, rcx
0x140045e2b  jz      short loc_140045E43
0x140045e2d  mov     [rsp+1F0h+ppv], 0
0x140045e36  mov     rax, [rcx]
0x140045e39  mov     rax, [rax+10h]
0x140045e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045e42  nop
0x140045e43  mov     [rsp+1F0h+var_190], r13
0x140045e48  lea     rcx, [rsp+1F0h+var_190]
0x140045e4d  call    ?Destroy@?$ActivityBase@VLogonFrameworkLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140045e52  lea     rcx, [rbp+0F0h+var_70]; this
0x140045e59  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140045e5e  lea     rcx, [rbp+0F0h+var_78]
0x140045e62  call    ?reset@?$shared_object@V?$ActivityData@VLogonFrameworkLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonFrameworkLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x140045e67  lea     rcx, [rsp+1F0h+var_188]
0x140045e6c  call    ??1?$ActivityData@VLogonFrameworkLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonFrameworkLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LogonFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x140045e71  mov     eax, ebx
0x140045e73  mov     rcx, [rbp+0F0h+var_40]
0x140045e7a  xor     rcx, rsp; StackCookie
0x140045e7d  call    __security_check_cookie
0x140045e82  add     rsp, 1C8h
0x140045e89  pop     r15
0x140045e8b  pop     r13
0x140045e8d  pop     rdi
0x140045e8e  pop     rsi
0x140045e8f  pop     rbx
0x140045e90  pop     rbp
0x140045e91  retn
```
