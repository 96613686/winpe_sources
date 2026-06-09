# PostCreateProcessDesktopAppXActivation

- ea: `0x1800234e0`
- end: `0x180023ab7`
- name: `PostCreateProcessDesktopAppXActivation`
- size: `1495`
- prototype: `__int64 __fastcall(void *, _QWORD *, struct _PROCESS_INFORMATION *)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016e4`
- `0x180004f70`
- `0x180011e9c`
- `0x1800125f4`
- `0x180014e74`
- `0x180016434`
- `0x180016b18`
- `0x180017aa4`
- `0x180018a1c`
- `0x180018fc0`
- `0x180019e90`
- `0x18001a7ec`
- `0x18001d2fc`
- `0x18001ebe0`
- `0x18001f38c`
- `0x18001f6a0`
- `0x1800210fc`
- `0x180021118`
- `0x180021254`
- `0x1800226f0`
- `0x1800234e0`
- `0x180053d40`
- `0x180054380`
- `0x180097158`
- `0x1800981cc`
- `0x1800a01c0`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800238f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023699`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180023699`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800236d5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800236d5`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x1800238e3`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x1800238e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800237dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023958`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023990`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800237dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023958`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023974`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023990`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180023653`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180023653`
- `ext-ms-win-com-psmregister-l1-1-0!PsmRegisterApplicationProcess` at `0x18002388e`
- `ext-ms-win-com-psmregister-l1-1-0!PsmRegisterApplicationProcess` at `0x18002388e`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x180023848`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x180023848`
- `RMCLIENT!HamRegisterDesktopProcessWithAppContainerToken` at `0x1800237ba`
- `RMCLIENT!HamRegisterDesktopProcessWithAppContainerToken` at `0x1800237ba`

## string_xrefs

- `0x1800239f2`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023a04`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023a19`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023a36`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023a53`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023a68`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023a7c`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023a90`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023aa4`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
__int64 __fastcall PostCreateProcessDesktopAppXActivation(void *a1, _QWORD *a2, struct _PROCESS_INFORMATION *a3)
{
  __int64 v6; // rcx
  void *v7; // rdi
  unsigned int *v8; // r9
  unsigned int v9; // r8d
  HANDLE v10; // rax
  const char *v11; // r9
  void **v12; // rax
  const char *v13; // r9
  unsigned int v14; // r12d
  HANDLE v15; // rax
  const char *v16; // r9
  void *v17; // r15
  bool v18; // di
  int v19; // eax
  unsigned int v20; // esi
  char v21; // r14
  int v22; // edi
  int v23; // eax
  unsigned int v24; // edi
  char IsEnabled; // al
  const unsigned __int16 *v26; // rdx
  struct _PROCESS_INFORMATION *v27; // rdi
  int v28; // eax
  void **v29; // r9
  int v30; // eax
  __int64 v31; // rdx
  int v32; // eax
  DWORD LastError; // eax
  const char *v34; // r9
  __int64 result; // rax
  HANDLE *p_hObject; // [rsp+20h] [rbp-1F8h]
  HANDLE hObject; // [rsp+40h] [rbp-1D8h] BYREF
  HANDLE ProcessHandle; // [rsp+48h] [rbp-1D0h] BYREF
  HANDLE v39; // [rsp+50h] [rbp-1C8h] BYREF
  HANDLE v40; // [rsp+58h] [rbp-1C0h] BYREF
  struct _PROCESS_INFORMATION *v41; // [rsp+60h] [rbp-1B8h]
  HANDLE *p_ProcessHandle; // [rsp+68h] [rbp-1B0h]
  char v43; // [rsp+70h] [rbp-1A8h]
  _QWORD v44[42]; // [rsp+80h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v41 = a3;
  wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v44,
    "PostDesktopActivation");
  v44[0] = &DesktopAppXProvider::PostDesktopActivation::`vftable';
  try
  {
    DesktopAppXProvider::PostDesktopActivation::StartActivity(
      (DesktopAppXProvider::PostDesktopActivation *)v44,
      (const unsigned __int16 *)*a2,
      (const unsigned __int16 *)a2[1]);
    if ( !*((_DWORD *)a2 + 12) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)a2[20] + 32LL))(a2[20]) )
      {
        v7 = (void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a2[20] + 24LL))(a2[20]);
        v8 = (unsigned int *)*((_QWORD *)DesktopAppXProvider::Instance() + 1);
        v6 = *v8;
        if ( (unsigned int)v6 > 5 )
        {
          v6 = *((_QWORD *)v8 + 2);
          if ( (v6 & 0x400000000000LL) != 0 && (*((_QWORD *)v8 + 3) & 0x400000000000LL) == *((_QWORD *)v8 + 3) )
          {
            hObject = v7;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (_DWORD)v8,
              (unsigned int)&unk_1800E4D08,
              0,
              (_DWORD)v8,
              (__int64)&hObject);
          }
        }
      }
    }
    v9 = *(_DWORD *)Feature_ID51912085__descriptor;
    if ( (*(_DWORD *)Feature_ID51912085__descriptor & 4) == 0 )
    {
      v40 = *(HANDLE *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID51912085>::GetCachedFeatureEnabledState(
                         v6,
                         &v40);
      v9 = (unsigned int)v40;
    }
    LODWORD(hObject) = 0;
    WORD2(hObject) = 3;
    p_hObject = &hObject;
    wil::details::ReportUsageToService(&qword_18010A1D8, 51912085, (v9 >> 10) & 1, (v9 >> 11) & 1);
    v10 = OpenProcess(0x1101u, 0, a3->dwProcessId);
    if ( !v10 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x25E,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v11);
    ProcessHandle = v10;
    v39 = 0;
    v12 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&v39);
    if ( !OpenProcessToken(ProcessHandle, 8u, v12) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x263,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v13);
    v14 = helium::ContainerTypeForPackagedToken(v39, a2);
    p_ProcessHandle = &ProcessHandle;
    v43 = 1;
    v15 = OpenThread(2u, 0, a3->dwThreadId);
    v17 = v15;
    if ( !v15 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x26F,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v16);
    v40 = v15;
    v18 = IsLifecycleManagedCentennialApplication(v39);
    if ( !v18 )
    {
      v19 = DamRegisterProcess(ProcessHandle);
      if ( v19 < 0 && v19 != -2147467262 && v19 != -2147024846 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2A3,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          (const char *)(unsigned int)v19,
          (int)&hObject);
    }
    v20 = 0;
    if ( !*((_DWORD *)a2 + 12) && !v18 )
      v20 = helium::AddProcessToHeliumContainer(ProcessHandle, a2[20], a1, v14);
    v21 = v20 != 0;
    if ( *((_BYTE *)a2 + 72) )
    {
      if ( v18 )
      {
        LODWORD(hObject) = 0;
        v30 = PsmQueryBackgroundActivationType(v39, &hObject);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x2DE,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)v30,
            (int)&hObject);
        v31 = 0;
        if ( (_DWORD)hObject )
        {
          if ( (_DWORD)hObject == 2 )
          {
            v31 = 8;
          }
          else if ( (_DWORD)hObject == 3 )
          {
            v31 = 4;
          }
        }
        else
        {
          v31 = 1;
        }
        v32 = PsmRegisterApplicationProcess(ProcessHandle, v31);
        if ( v32 < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x2F3,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)v32,
            (int)&hObject);
      }
      else
      {
        if ( v20 )
        {
          LODWORD(p_hObject) = v14;
          v21 = CheckContainerInActivatableStatePostAddProcess(a2[20], a1, v20, 0);
        }
        v22 = *((_DWORD *)a2 + 4) != 0 ? 2 : 0;
        GetAppContainerTokenForPackageAndUser(&hObject, *a2, a1, v14);
        v23 = HamRegisterDesktopProcessWithAppContainerToken(ProcessHandle, (unsigned int)(v22 + 128), hObject);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x2D8,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)v23,
            (int)p_hObject);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
      }
    }
    v24 = *((_DWORD *)a2 + 19);
    if ( v24 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialInUIJob>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CentennialInUIJob>::GetImpl'::`2'::impl);
      v26 = 0;
      if ( IsEnabled && *((_BYTE *)a2 + 72) )
        v26 = (const unsigned __int16 *)*a2;
      PlaceProcessIntoUIContainer(ProcessHandle, v26, v24);
    }
    v27 = v41;
    v28 = CAMHandlePackagedProcessLaunch(v41->dwProcessId);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x318,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        (const char *)(unsigned int)v28,
        (int)p_hObject);
    if ( *((_DWORD *)a2 + 4) )
    {
      if ( v21 )
      {
        LODWORD(p_hObject) = v14;
        v21 = CheckContainerInActivatableStatePostAddProcess(a2[20], a1, v20, 1);
      }
      if ( (a2[5] & 4) != 0 && SuspendThread(v17) == -1 )
      {
        LastError = GetLastError();
        if ( LastError )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x324,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)LastError,
            (unsigned int)p_hObject);
      }
      LaunchDebugger((const unsigned __int16 *)a2[3], v27, a1, v29);
    }
    if ( v21 )
      CheckContainerInActivatableStatePostAddProcess(a2[20], a1, v20, 2);
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44);
    if ( v17 != (void *)-1LL )
      CloseHandle(v17);
    if ( (char *)v39 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v39);
    if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(ProcessHandle);
    v44[0] = &DesktopAppXProvider::PostDesktopActivation::`vftable';
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v44);
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(v44);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x32F,
                           (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                           v34);
  }
  return result;
}

```

## disassembly

```asm
0x1800234e0  push    rbx
0x1800234e2  push    rsi
0x1800234e3  push    rdi
0x1800234e4  push    r12
0x1800234e6  push    r13
0x1800234e8  push    r14
0x1800234ea  push    r15
0x1800234ec  sub     rsp, 1E0h
0x1800234f3  mov     rax, cs:__security_cookie
0x1800234fa  xor     rax, rsp
0x1800234fd  mov     [rsp+218h+var_48], rax
0x180023505  mov     rsi, r8
0x180023508  mov     [rsp+218h+var_1B8], r8
0x18002350d  mov     rbx, rdx
0x180023510  mov     r13, rcx
0x180023513  lea     rdx, aPostdesktopact; "PostDesktopActivation"
0x18002351a  lea     rcx, [rsp+218h+var_198]
0x180023522  call    ??0?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180023527  lea     rax, ??_7PostDesktopActivation@DesktopAppXProvider@@6B@; const DesktopAppXProvider::PostDesktopActivation::`vftable'
0x18002352e  mov     [rsp+218h+var_198], rax
0x180023536  mov     r8, [rbx+8]; unsigned __int16 *
0x18002353a  mov     rdx, [rbx]; unsigned __int16 *
0x18002353d  lea     rcx, [rsp+218h+var_198]; this
0x180023545  call    ?StartActivity@PostDesktopActivation@DesktopAppXProvider@@QEAAXPEBG0@Z; DesktopAppXProvider::PostDesktopActivation::StartActivity(ushort const *,ushort const *)
0x18002354a  nop
0x18002354b  xor     r14d, r14d
0x18002354e  cmp     [rbx+30h], r14d
0x180023552  jnz     loc_1800235D9
0x180023558  mov     rcx, [rbx+0A0h]
0x18002355f  mov     rax, [rcx]
0x180023562  mov     rax, [rax+20h]
0x180023566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002356b  test    al, al
0x18002356d  jz      short loc_1800235D9
0x18002356f  mov     rcx, [rbx+0A0h]
0x180023576  mov     rax, [rcx]
0x180023579  mov     rax, [rax+18h]
0x18002357d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023582  mov     rdi, rax
0x180023585  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x18002358a  mov     r9, [rax+8]
0x18002358e  mov     ecx, [r9]
0x180023591  cmp     ecx, 5
0x180023594  jbe     short loc_1800235D9
0x180023596  mov     rdx, [r9+18h]
0x18002359a  mov     rcx, [r9+10h]
0x18002359e  mov     r8, 400000000000h
0x1800235a8  test    r8, rcx
0x1800235ab  jz      short loc_1800235D9
0x1800235ad  mov     rax, rdx
0x1800235b0  and     rax, r8
0x1800235b3  cmp     rax, rdx
0x1800235b6  jnz     short loc_1800235D9
0x1800235b8  mov     [rsp+218h+hObject], rdi
0x1800235bd  lea     rax, [rsp+218h+hObject]
0x1800235c2  mov     qword ptr [rsp+218h+var_1F8], rax
0x1800235c7  xor     r8d, r8d
0x1800235ca  lea     rdx, unk_1800E4D08
0x1800235d1  mov     rcx, r9
0x1800235d4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800235d9  mov     rax, cs:Feature_ID51912085__descriptor
0x1800235e0  mov     r8d, [rax]
0x1800235e3  test    r8b, 4
0x1800235e7  jnz     short loc_1800235FE
0x1800235e9  lea     rdx, [rsp+218h+var_1C0]
0x1800235ee  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID51912085@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID51912085>::GetCachedFeatureEnabledState(void)
0x1800235f3  mov     rax, [rax]
0x1800235f6  mov     [rsp+218h+var_1C0], rax
0x1800235fb  mov     r8d, eax
0x1800235fe  mov     dword ptr [rsp+218h+hObject], r14d
0x180023603  mov     word ptr [rsp+218h+hObject+4], 3
0x18002360a  mov     r9d, r8d
0x18002360d  shr     r9d, 0Bh
0x180023611  and     r9d, 1
0x180023615  shr     r8d, 0Ah
0x180023619  and     r8d, 1
0x18002361d  mov     [rsp+218h+var_1E8], 3
0x180023625  mov     [rsp+218h+var_1F0], 1
0x18002362d  lea     rax, [rsp+218h+hObject]
0x180023632  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x180023637  mov     edx, 3181D95h
0x18002363c  lea     rcx, qword_18010A1D8
0x180023643  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180023648  mov     r8d, [rsi+10h]; dwProcessId
0x18002364c  xor     edx, edx; bInheritHandle
0x18002364e  mov     ecx, 1101h; dwDesiredAccess
0x180023653  call    cs:__imp_OpenProcess
0x18002365a  nop     dword ptr [rax+rax+00h]
0x18002365f  mov     rcx, [rsp+218h]; this
0x180023667  test    rax, rax
0x18002366a  jz      loc_1800239F2
0x180023670  mov     [rsp+218h+ProcessHandle], rax
0x180023675  mov     [rsp+218h+var_1C8], r14
0x18002367a  lea     rcx, [rsp+218h+var_1C8]
0x18002367f  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180023684  mov     rdi, [rsp+218h]
0x18002368c  mov     r8, rax; TokenHandle
0x18002368f  mov     edx, 8; DesiredAccess
0x180023694  mov     rcx, [rsp+218h+ProcessHandle]; ProcessHandle
0x180023699  call    cs:__imp_OpenProcessToken
0x1800236a0  nop     dword ptr [rax+rax+00h]
0x1800236a5  test    eax, eax
0x1800236a7  jz      loc_180023A04
0x1800236ad  mov     rdx, rbx
0x1800236b0  mov     rcx, [rsp+218h+var_1C8]
0x1800236b5  call    ?ContainerTypeForPackagedToken@helium@@YA?AW4ContainerType@1@PEAXPEBUDESKTOP_APPX_LAUNCH_CONTEXT@@@Z; helium::ContainerTypeForPackagedToken(void *,DESKTOP_APPX_LAUNCH_CONTEXT const *)
0x1800236ba  mov     r12d, eax
0x1800236bd  lea     rax, [rsp+218h+ProcessHandle]
0x1800236c2  mov     [rsp+218h+var_1B0], rax
0x1800236c7  mov     [rsp+218h+var_1A8], 1
0x1800236cc  mov     r8d, [rsi+14h]; dwThreadId
0x1800236d0  xor     edx, edx; bInheritHandle
0x1800236d2  lea     ecx, [rdx+2]; dwDesiredAccess
0x1800236d5  call    cs:__imp_OpenThread
0x1800236dc  nop     dword ptr [rax+rax+00h]
0x1800236e1  mov     r15, rax
0x1800236e4  mov     rcx, [rsp+218h]; this
0x1800236ec  test    rax, rax
0x1800236ef  jz      loc_180023A19
0x1800236f5  mov     [rsp+218h+var_1C0], r15
0x1800236fa  mov     rcx, [rsp+218h+var_1C8]; void *
0x1800236ff  call    ?IsLifecycleManagedCentennialApplication@@YA_NPEAX@Z; IsLifecycleManagedCentennialApplication(void *)
0x180023704  mov     dil, al
0x180023707  test    al, al
0x180023709  jnz     short loc_18002372B
0x18002370b  mov     rcx, [rsp+218h+ProcessHandle]; ProcessHandle
0x180023710  call    DamRegisterProcess
0x180023715  test    eax, eax
0x180023717  jns     short loc_18002372B
0x180023719  cmp     eax, 80004002h
0x18002371e  jz      short loc_18002372B
0x180023720  cmp     eax, 80070032h
0x180023725  jnz     loc_180023A2B
0x18002372b  mov     esi, r14d
0x18002372e  cmp     [rbx+30h], r14d
0x180023732  jnz     short loc_180023752
0x180023734  test    dil, dil
0x180023737  jnz     short loc_180023752
0x180023739  mov     r9d, r12d
0x18002373c  mov     r8, r13
0x18002373f  mov     rdx, [rbx+0A0h]
0x180023746  mov     rcx, [rsp+218h+ProcessHandle]
0x18002374b  call    ?AddProcessToHeliumContainer@helium@@YA?AW4ProcessContainerDisposition@1@PEAXAEBVHeliumSpecification@1@0W4ContainerType@1@@Z; helium::AddProcessToHeliumContainer(void *,helium::HeliumSpecification const &,void *,helium::ContainerType)
0x180023750  mov     esi, eax
0x180023752  test    esi, esi
0x180023754  setnz   r14b
0x180023758  cmp     byte ptr [rbx+48h], 0
0x18002375c  jz      loc_1800237E9
0x180023762  test    dil, dil
0x180023765  jnz     loc_180023836
0x18002376b  test    esi, esi
0x18002376d  jz      short loc_18002378C
0x18002376f  mov     [rsp+218h+var_1F8], r12d; int
0x180023774  xor     r9d, r9d
0x180023777  mov     r8d, esi
0x18002377a  mov     rdx, r13
0x18002377d  mov     rcx, [rbx+0A0h]
0x180023784  call    ?CheckContainerInActivatableStatePostAddProcess@@YA_NAEBVHeliumSpecification@helium@@PEAXW4ProcessContainerDisposition@2@W4PostAddProcessCheckpoint@@W4ContainerType@2@@Z; CheckContainerInActivatableStatePostAddProcess(helium::HeliumSpecification const &,void *,helium::ProcessContainerDisposition,PostAddProcessCheckpoint,helium::ContainerType)
0x180023789  mov     r14b, al
0x18002378c  mov     ecx, [rbx+10h]
0x18002378f  neg     ecx
0x180023791  sbb     edi, edi
0x180023793  and     edi, 2
0x180023796  mov     r9d, r12d
0x180023799  mov     r8, r13
0x18002379c  mov     rdx, [rbx]
0x18002379f  lea     rcx, [rsp+218h+hObject]
0x1800237a4  call    ?GetAppContainerTokenForPackageAndUser@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAXW4ContainerType@helium@@@Z; GetAppContainerTokenForPackageAndUser(ushort const *,void *,helium::ContainerType)
0x1800237a9  nop
0x1800237aa  mov     r8, [rsp+218h+hObject]
0x1800237af  lea     edx, [rdi+80h]
0x1800237b5  mov     rcx, [rsp+218h+ProcessHandle]
0x1800237ba  call    cs:__imp_HamRegisterDesktopProcessWithAppContainerToken
0x1800237c1  nop     dword ptr [rax+rax+00h]
0x1800237c6  test    eax, eax
0x1800237c8  js      loc_180023A48
0x1800237ce  mov     rcx, [rsp+218h+hObject]; hObject
0x1800237d3  lea     rax, [rcx-1]
0x1800237d7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800237db  ja      short loc_1800237E9
0x1800237dd  call    cs:__imp_CloseHandle
0x1800237e4  nop     dword ptr [rax+rax+00h]
0x1800237e9  mov     edi, [rbx+4Ch]
0x1800237ec  test    edi, edi
0x1800237ee  jz      short loc_180023817
0x1800237f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CentennialInUIJob@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialInUIJob@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialInUIJob> `wil::Feature<__WilFeatureTraits_Feature_CentennialInUIJob>::GetImpl(void)'::`2'::impl
0x1800237f7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CentennialInUIJob@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CentennialInUIJob>::__private_IsEnabled(void)
0x1800237fc  xor     edx, edx
0x1800237fe  test    al, al
0x180023800  jz      short loc_18002380A
0x180023802  cmp     [rbx+48h], dl
0x180023805  jz      short loc_18002380A
0x180023807  mov     rdx, [rbx]; unsigned __int16 *
0x18002380a  mov     r8d, edi; unsigned int
0x18002380d  mov     rcx, [rsp+218h+ProcessHandle]; hProcess
0x180023812  call    ?PlaceProcessIntoUIContainer@@YAXPEAXPEBGK@Z; PlaceProcessIntoUIContainer(void *,ushort const *,ulong)
0x180023817  mov     rdi, [rsp+218h+var_1B8]
0x18002381c  mov     ecx, [rdi+10h]; unsigned int
0x18002381f  call    CAMHandlePackagedProcessLaunch
0x180023824  mov     rcx, [rsp+218h]; this
0x18002382c  test    eax, eax
0x18002382e  js      loc_180023A65
0x180023834  jmp     short loc_1800238AF
0x180023836  mov     dword ptr [rsp+218h+hObject], 0
0x18002383e  lea     rdx, [rsp+218h+hObject]
0x180023843  mov     rcx, [rsp+218h+var_1C8]
0x180023848  call    cs:__imp_PsmQueryBackgroundActivationType
0x18002384f  nop     dword ptr [rax+rax+00h]
0x180023854  mov     rcx, [rsp+218h]; this
0x18002385c  test    eax, eax
0x18002385e  js      loc_180023A79
0x180023864  xor     edx, edx
0x180023866  mov     ecx, dword ptr [rsp+218h+hObject]
0x18002386a  test    ecx, ecx
0x18002386c  jz      short loc_180023884
0x18002386e  sub     ecx, 2
0x180023871  jz      short loc_18002387D
0x180023873  cmp     ecx, 1
0x180023876  jnz     short loc_180023889
0x180023878  lea     edx, [rcx+3]
0x18002387b  jmp     short loc_180023889
0x18002387d  mov     edx, 8
0x180023882  jmp     short loc_180023889
0x180023884  mov     edx, 1
0x180023889  mov     rcx, [rsp+218h+ProcessHandle]
0x18002388e  call    cs:__imp_PsmRegisterApplicationProcess
0x180023895  nop     dword ptr [rax+rax+00h]
0x18002389a  mov     rcx, [rsp+218h]; this
0x1800238a2  test    eax, eax
0x1800238a4  js      loc_180023A8D
0x1800238aa  jmp     loc_1800237E9
0x1800238af  cmp     dword ptr [rbx+10h], 0
0x1800238b3  jz      short loc_18002391F
0x1800238b5  test    r14b, r14b
0x1800238b8  jz      short loc_1800238DA
0x1800238ba  mov     [rsp+218h+var_1F8], r12d; unsigned int
0x1800238bf  mov     r9d, 1
0x1800238c5  mov     r8d, esi
0x1800238c8  mov     rdx, r13
0x1800238cb  mov     rcx, [rbx+0A0h]
0x1800238d2  call    ?CheckContainerInActivatableStatePostAddProcess@@YA_NAEBVHeliumSpecification@helium@@PEAXW4ProcessContainerDisposition@2@W4PostAddProcessCheckpoint@@W4ContainerType@2@@Z; CheckContainerInActivatableStatePostAddProcess(helium::HeliumSpecification const &,void *,helium::ProcessContainerDisposition,PostAddProcessCheckpoint,helium::ContainerType)
0x1800238d7  mov     r14b, al
0x1800238da  test    byte ptr [rbx+28h], 4
0x1800238de  jz      short loc_180023910
0x1800238e0  mov     rcx, r15; hThread
0x1800238e3  call    cs:__imp_SuspendThread
0x1800238ea  nop     dword ptr [rax+rax+00h]
0x1800238ef  cmp     eax, 0FFFFFFFFh
0x1800238f2  jnz     short loc_180023910
0x1800238f4  call    cs:__imp_GetLastError
0x1800238fb  nop     dword ptr [rax+rax+00h]
0x180023900  mov     rcx, [rsp+218h]; this
0x180023908  test    eax, eax
0x18002390a  jnz     loc_180023AA1
0x180023910  mov     r8, r13; void *
0x180023913  mov     rdx, rdi; struct _PROCESS_INFORMATION *
0x180023916  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18002391a  call    ?LaunchDebugger@@YAXPEBGPEAU_PROCESS_INFORMATION@@PEAXPEAPEAX@Z; LaunchDebugger(ushort const *,_PROCESS_INFORMATION *,void *,void * *)
0x18002391f  test    r14b, r14b
0x180023922  jz      short loc_180023941
0x180023924  mov     [rsp+218h+var_1F8], r12d
0x180023929  mov     r9d, 2
0x18002392f  mov     r8d, esi
0x180023932  mov     rdx, r13
0x180023935  mov     rcx, [rbx+0A0h]
0x18002393c  call    ?CheckContainerInActivatableStatePostAddProcess@@YA_NAEBVHeliumSpecification@helium@@PEAXW4ProcessContainerDisposition@2@W4PostAddProcessCheckpoint@@W4ContainerType@2@@Z; CheckContainerInActivatableStatePostAddProcess(helium::HeliumSpecification const &,void *,helium::ProcessContainerDisposition,PostAddProcessCheckpoint,helium::ContainerType)
0x180023941  lea     rcx, [rsp+218h+var_198]
0x180023949  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002394e  nop
0x18002394f  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180023953  jz      short loc_180023965
0x180023955  mov     rcx, r15; hObject
0x180023958  call    cs:__imp_CloseHandle
0x18002395f  nop     dword ptr [rax+rax+00h]
0x180023964  nop
0x180023965  mov     rcx, [rsp+218h+var_1C8]; hObject
0x18002396a  lea     rax, [rcx-1]
0x18002396e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023972  ja      short loc_180023981
0x180023974  call    cs:__imp_CloseHandle
0x18002397b  nop     dword ptr [rax+rax+00h]
0x180023980  nop
0x180023981  mov     rcx, [rsp+218h+ProcessHandle]; hObject
0x180023986  lea     rax, [rcx-1]
0x18002398a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002398e  ja      short loc_18002399D
0x180023990  call    cs:__imp_CloseHandle
0x180023997  nop     dword ptr [rax+rax+00h]
0x18002399c  nop
0x18002399d  lea     rax, ??_7PostDesktopActivation@DesktopAppXProvider@@6B@; const DesktopAppXProvider::PostDesktopActivation::`vftable'
0x1800239a4  mov     [rsp+218h+var_198], rax
0x1800239ac  lea     rcx, [rsp+218h+var_198]
0x1800239b4  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800239b9  lea     rcx, [rsp+218h+var_198]
0x1800239c1  call    ??1?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800239c6  xor     eax, eax
0x1800239c8  jmp     short loc_1800239CE
0x1800239ca  mov     eax, dword ptr [rsp+218h+hObject]
0x1800239ce  mov     rcx, [rsp+218h+var_48]
0x1800239d6  xor     rcx, rsp; StackCookie
  ... truncated ...
```
