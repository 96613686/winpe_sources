# CLogonTaskFramework::s_AppResolverWork(CLogonTaskFramework *)

- ea: `0x14001d100`
- end: `0x14001d3c4`
- name: `?s_AppResolverWork@CLogonTaskFramework@@CAJPEAV1@@Z`
- size: `708`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14001d020`
- `0x14015b044`

## callees

- `0x140006b98`
- `0x14000edcc`
- `0x14000f400`
- `0x1400179d0`
- `0x140017ce8`
- `0x140018044`
- `0x14001c980`
- `0x14001d100`
- `0x14001eba8`
- `0x14008fa10`
- `0x1400a4580`
- `0x1400a69d0`
- `0x1400adac0`
- `0x1400b5990`
- `0x1401040e0`
- `0x1401a8fdc`
- `0x1401db010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001d1c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001d1c9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001d2fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001d2fa`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x14001d299`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x14001d2b0`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x14001d299`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x14001d2b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001d1f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001d1f3`

## string_xrefs

- `0x14001d21f`: `shell\lib\logontasks\logontasks.cpp`
- `0x14001d33c`: `shell\lib\logontasks\logontasks.cpp`

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
    (char *)a1 + 608);
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
        (void *)0xC9D,
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
    v14 = 3278;
  }
  else
  {
    v14 = 3275;
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
0x14001d100  push    rbp
0x14001d102  push    rbx
0x14001d103  push    rsi
0x14001d104  push    rdi
0x14001d105  push    r13
0x14001d107  push    r15
0x14001d109  lea     rbp, [rsp-0C8h]
0x14001d111  sub     rsp, 1C8h
0x14001d118  mov     rax, cs:__security_cookie
0x14001d11f  xor     rax, rsp
0x14001d122  mov     [rbp+0F0h+var_40], rax
0x14001d129  mov     rsi, rcx
0x14001d12c  lea     rdx, aAppresolverwor; "AppResolverWork"
0x14001d133  lea     rcx, [rsp+1F0h+var_190]; struct wil::details::IFailureCallback *
0x14001d138  call    ??0?$ActivityBase@VLogonFrameworkLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14001d13d  lea     r13, ??_7AppResolverWork@LogonFrameworkTelemetry@@6B@; const LogonFrameworkTelemetry::AppResolverWork::`vftable'
0x14001d144  mov     [rsp+1F0h+var_190], r13
0x14001d149  lea     rdx, [rsi+260h]
0x14001d150  lea     rcx, [rsp+1F0h+var_190]
0x14001d155  call    ??$SetRelatedActivity@VAllLogonTasks@LogonFrameworkTelemetry@@@?$ActivityBase@VLogonFrameworkLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBVAllLogonTasks@LogonFrameworkTelemetry@@@Z; wil::ActivityBase<LogonFrameworkLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivity<LogonFrameworkTelemetry::AllLogonTasks>(LogonFrameworkTelemetry::AllLogonTasks const &)
0x14001d15a  lea     rcx, [rsp+1F0h+var_190]; this
0x14001d15f  call    ?StartActivity@AppResolverWork@LogonFrameworkTelemetry@@QEAAXXZ; LogonFrameworkTelemetry::AppResolverWork::StartActivity(void)
0x14001d164  call    ?GetShellVersion@ShellVersion@@YAKXZ; ShellVersion::GetShellVersion(void)
0x14001d169  mov     ebx, eax
0x14001d16b  test    dword ptr [rsi+0D8h], 4000h
0x14001d175  jz      short loc_14001D17F
0x14001d177  xor     ecx, ecx
0x14001d179  cmp     eax, 0Dh
0x14001d17c  cmovz   ebx, ecx
0x14001d17f  mov     qword ptr [rsp+1F0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x14001d188  mov     edi, 8
0x14001d18d  mov     [rsp+1F0h+var_1B0], edi
0x14001d191  lea     rax, [rsp+1F0h+var_1B0]
0x14001d196  mov     [rsp+1F0h+pcbData], rax; pcbData
0x14001d19b  lea     rax, [rsp+1F0h+SystemTimeAsFileTime]
0x14001d1a0  mov     [rsp+1F0h+pvData], rax; pvData
0x14001d1a5  mov     [rsp+1F0h+pdwType], 0; int
0x14001d1ae  mov     r9d, edi; dwFlags
0x14001d1b1  lea     r8, aStartJumplistm; "Start_JumpListModernTime"
0x14001d1b8  lea     rdx, aSoftwareMicros_106; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001d1bf  mov     r15, 0FFFFFFFF80000001h
0x14001d1c6  mov     rcx, r15; hkey
0x14001d1c9  call    cs:__imp_RegGetValueW
0x14001d1cf  test    eax, eax
0x14001d1d1  jle     short loc_14001D1DD
0x14001d1d3  movzx   eax, ax
0x14001d1d6  or      eax, 80070000h
0x14001d1db  test    eax, eax
0x14001d1dd  js      short loc_14001D1E5
0x14001d1df  cmp     [rsp+1F0h+var_1B0], edi
0x14001d1e3  jz      short loc_14001D230
0x14001d1e5  mov     qword ptr [rsp+1F0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x14001d1ee  lea     rcx, [rsp+1F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14001d1f3  call    cs:__imp_GetSystemTimeAsFileTime
0x14001d1f9  lea     r9, [rsp+1F0h+SystemTimeAsFileTime]; struct _FILETIME *
0x14001d1fe  lea     r8, aStartJumplistm; "Start_JumpListModernTime"
0x14001d205  lea     rdx, aSoftwareMicros_106; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001d20c  call    ?SHRegSetFILETIME@@YAJPEAUHKEY__@@PEBG1PEBU_FILETIME@@@Z; SHRegSetFILETIME(HKEY__ *,ushort const *,ushort const *,_FILETIME const *)
0x14001d211  mov     rcx, [rbp+0F8h]; this
0x14001d218  test    eax, eax
0x14001d21a  jns     short loc_14001D230
0x14001d21c  mov     r9d, eax; char *
0x14001d21f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14001d226  mov     edx, 0C9Dh; void *
0x14001d22b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001d230  cmp     ebx, 0Dh
0x14001d233  jnb     short loc_14001D283
0x14001d235  mov     edi, 4Ch ; 'L'
0x14001d23a  mov     eax, ebx
0x14001d23c  sub     eax, 4
0x14001d23f  jz      short loc_14001D260
0x14001d241  sub     eax, 1
0x14001d244  jz      short loc_14001D259
0x14001d246  cmp     eax, 1
0x14001d249  jnz     short loc_14001D2B6
0x14001d24b  mov     edi, 44Ch
0x14001d250  lea     r8, aDefaultstartla; "DefaultStartLayout_UseWin8UpgradeBehavi"...
0x14001d257  jmp     short loc_14001D26C
0x14001d259  mov     edi, 24Ch
0x14001d25e  jmp     short loc_14001D250
0x14001d260  mov     edi, 6Ch ; 'l'
0x14001d265  lea     r8, aDefaultstartla_0; "DefaultStartLayout_UseWin7UpgradeBehavi"...
0x14001d26c  mov     r9d, 1; unsigned int
0x14001d272  lea     rdx, aSoftwareMicros_119; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001d279  mov     rcx, r15; HKEY
0x14001d27c  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x14001d281  jmp     short loc_14001D2B6
0x14001d283  mov     edi, 0Ch
0x14001d288  lea     r8, aDefaultstartla_0; "DefaultStartLayout_UseWin7UpgradeBehavi"...
0x14001d28f  lea     rdx, aSoftwareMicros_119; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001d296  mov     rcx, r15; hkey
0x14001d299  call    cs:__imp_SHDeleteValueW
0x14001d29f  lea     r8, aDefaultstartla; "DefaultStartLayout_UseWin8UpgradeBehavi"...
0x14001d2a6  lea     rdx, aSoftwareMicros_119; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14001d2ad  mov     rcx, r15; hkey
0x14001d2b0  call    cs:__imp_SHDeleteValueW
0x14001d2b6  test    byte ptr [rsi+0D8h], 2
0x14001d2bd  jz      short loc_14001D2C9
0x14001d2bf  cmp     ebx, 0Bh
0x14001d2c2  ja      short loc_14001D2C9
0x14001d2c4  call    ?s_CleanUpRemovedSystemShortcuts@CLogonTaskFramework@@CAXXZ; CLogonTaskFramework::s_CleanUpRemovedSystemShortcuts(void)
0x14001d2c9  mov     [rsp+1F0h+ppv], 0
0x14001d2d2  lea     rcx, [rsp+1F0h+ppv]
0x14001d2d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x14001d2dc  lea     rax, [rsp+1F0h+ppv]
0x14001d2e1  mov     [rsp+1F0h+pdwType], rax; int
0x14001d2e6  lea     r9, _GUID_ba5a92ae_bfd7_4916_854f_6b3a402b84a8; riid
0x14001d2ed  xor     edx, edx; pUnkOuter
0x14001d2ef  lea     r8d, [rdx+3]; dwClsContext
0x14001d2f3  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x14001d2fa  call    cs:__imp_CoCreateInstance
0x14001d300  mov     ebx, eax
0x14001d302  mov     rcx, [rbp+0F8h]
0x14001d309  test    eax, eax
0x14001d30b  jns     short loc_14001D314
0x14001d30d  mov     edx, 0CCBh
0x14001d312  jmp     short loc_14001D339
0x14001d314  mov     rcx, [rsp+1F0h+ppv]
0x14001d319  mov     rax, [rcx]
0x14001d31c  mov     edx, edi
0x14001d31e  mov     rax, [rax+48h]
0x14001d322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d327  mov     ebx, eax
0x14001d329  mov     rcx, [rbp+0F8h]; this
0x14001d330  test    eax, eax
0x14001d332  jns     short loc_14001D348
0x14001d334  mov     edx, 0CCEh; void *
0x14001d339  mov     r9d, eax; char *
0x14001d33c  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14001d343  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001d348  mov     edx, ebx
0x14001d34a  lea     rcx, [rsp+1F0h+var_190]
0x14001d34f  call    ?Stop@?$ActivityBase@VLogonFrameworkLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14001d354  nop
0x14001d355  mov     rcx, [rsp+1F0h+ppv]
0x14001d35a  test    rcx, rcx
0x14001d35d  jz      short loc_14001D375
0x14001d35f  mov     [rsp+1F0h+ppv], 0
0x14001d368  mov     rax, [rcx]
0x14001d36b  mov     rax, [rax+10h]
0x14001d36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d374  nop
0x14001d375  mov     [rsp+1F0h+var_190], r13
0x14001d37a  lea     rcx, [rsp+1F0h+var_190]
0x14001d37f  call    ?Destroy@?$ActivityBase@VLogonFrameworkLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x14001d384  lea     rcx, [rbp+0F0h+var_70]; this
0x14001d38b  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x14001d390  lea     rcx, [rbp+0F0h+var_78]
0x14001d394  call    ?reset@?$shared_object@V?$ActivityData@VLogonFrameworkLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonFrameworkLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x14001d399  lea     rcx, [rsp+1F0h+var_188]
0x14001d39e  call    ??1?$ActivityData@VLogonFrameworkLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VLogonFrameworkLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LogonFrameworkLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<LogonFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<LogonFrameworkLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x14001d3a3  mov     eax, ebx
0x14001d3a5  mov     rcx, [rbp+0F0h+var_40]
0x14001d3ac  xor     rcx, rsp; StackCookie
0x14001d3af  call    __security_check_cookie
0x14001d3b4  add     rsp, 1C8h
0x14001d3bb  pop     r15
0x14001d3bd  pop     r13
0x14001d3bf  pop     rdi
0x14001d3c0  pop     rsi
0x14001d3c1  pop     rbx
0x14001d3c2  pop     rbp
0x14001d3c3  retn
```
