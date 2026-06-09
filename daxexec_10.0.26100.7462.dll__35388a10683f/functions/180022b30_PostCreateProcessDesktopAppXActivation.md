# PostCreateProcessDesktopAppXActivation

- ea: `0x180022b30`
- end: `0x1800231a5`
- name: `PostCreateProcessDesktopAppXActivation`
- size: `1653`
- prototype: ``
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800016e0`
- `0x1800053a0`
- `0x180006158`
- `0x18001031c`
- `0x180010a84`
- `0x180013100`
- `0x180014ed8`
- `0x180015ec8`
- `0x180016dd4`
- `0x180017374`
- `0x1800182f4`
- `0x180018ce4`
- `0x18001c8bc`
- `0x18001df90`
- `0x18001e840`
- `0x18001eb48`
- `0x18002031c`
- `0x180020338`
- `0x180020e74`
- `0x180021ed0`
- `0x180022b30`
- `0x1800521b8`
- `0x1800528e4`
- `0x1800957f8`
- `0x18009681c`
- `0x18009e87c`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022fe2`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180022fd1`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x180022fd1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180022dc4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x180022dc4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022d85`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180022d85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ee8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023046`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023062`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002307e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022ee8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023046`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023062`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002307e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022d3f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180022d3f`
- `ext-ms-win-com-psmregister-l1-1-0!PsmRegisterApplicationProcess` at `0x180022f7c`
- `ext-ms-win-com-psmregister-l1-1-0!PsmRegisterApplicationProcess` at `0x180022f7c`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x180022f36`
- `ext-ms-win-com-psmregister-l1-1-0!PsmQueryBackgroundActivationType` at `0x180022f36`
- `RMCLIENT!HamRegisterDesktopProcessWithAppContainerToken` at `0x180022ec5`
- `RMCLIENT!HamRegisterDesktopProcessWithAppContainerToken` at `0x180022ec5`

## string_xrefs

- `0x1800230e0`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x1800230f2`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023107`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023124`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023141`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023156`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18002316a`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x18002317e`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`
- `0x180023192`: `onecore\base\appmodel\execmodel\desktopappx\lib\processcreationextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PostCreateProcessDesktopAppXActivation(
        void *a1,
        const unsigned __int16 **a2,
        struct _PROCESS_INFORMATION *a3)
{
  void *v6; // rdi
  __int64 v7; // rcx
  int v8; // r9d
  unsigned int v9; // r8d
  HANDLE v10; // rax
  const char *v11; // r9
  void **v12; // rax
  const char *v13; // r9
  unsigned int v14; // r12d
  HANDLE v15; // rax
  const char *v16; // r9
  void *v17; // r14
  bool v18; // di
  int v19; // eax
  unsigned int v20; // esi
  char v21; // r15
  int v22; // edi
  int v23; // eax
  char IsEnabled; // al
  void **v25; // r9
  struct _PROCESS_INFORMATION *v26; // rdi
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  int v30; // eax
  DWORD LastError; // eax
  const char *v32; // r9
  __int64 result; // rax
  int *v34; // [rsp+20h] [rbp-208h]
  int v35; // [rsp+40h] [rbp-1E8h] BYREF
  __int16 v36; // [rsp+44h] [rbp-1E4h]
  HANDLE ProcessHandle; // [rsp+48h] [rbp-1E0h] BYREF
  HANDLE v38; // [rsp+50h] [rbp-1D8h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-1D0h] BYREF
  struct _PROCESS_INFORMATION *v40; // [rsp+60h] [rbp-1C8h]
  __int64 v41; // [rsp+68h] [rbp-1C0h]
  _QWORD v42[2]; // [rsp+70h] [rbp-1B8h] BYREF
  char v43; // [rsp+80h] [rbp-1A8h]
  void **v44; // [rsp+90h] [rbp-198h] BYREF
  int v45; // [rsp+98h] [rbp-190h] BYREF
  char v46; // [rsp+9Ch] [rbp-18Ch]
  int v47; // [rsp+C0h] [rbp-168h] BYREF
  const char *v48; // [rsp+C8h] [rbp-160h]
  __int64 v49; // [rsp+D0h] [rbp-158h]
  char v50; // [rsp+D8h] [rbp-150h]
  int v51; // [rsp+E0h] [rbp-148h]
  _BYTE v52[168]; // [rsp+E8h] [rbp-140h] BYREF
  int v53; // [rsp+190h] [rbp-98h]
  __int64 v54; // [rsp+198h] [rbp-90h]
  int *v55; // [rsp+1A0h] [rbp-88h]
  __int64 v56; // [rsp+1A8h] [rbp-80h]
  __int64 v57; // [rsp+1B0h] [rbp-78h]
  void ***v58; // [rsp+1B8h] [rbp-70h]
  __int64 v59; // [rsp+1C0h] [rbp-68h]
  int v60; // [rsp+1C8h] [rbp-60h]
  int *v61; // [rsp+1D0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v40 = a3;
  v45 = 0;
  v46 = 0;
  v50 = 0;
  v47 = 0;
  v48 = "PostDesktopActivation";
  v49 = 0;
  v51 = 0;
  *(_OWORD *)&v52[152] = 0;
  memset_0(v52, 0, 0x98u);
  v53 = 1;
  v54 = 0;
  v55 = &v45;
  v56 = 0;
  v57 = 0;
  v58 = &v44;
  v59 = 0;
  v60 = 0;
  v61 = &v47;
  v44 = &DesktopAppXProvider::PostDesktopActivation::`vftable';
  try
  {
    DesktopAppXProvider::PostDesktopActivation::StartActivity(
      (DesktopAppXProvider::PostDesktopActivation *)&v44,
      *a2,
      a2[1]);
    if ( !*((_DWORD *)a2 + 12) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)a2[19] + 32LL))(a2[19]) )
      {
        v6 = (void *)(*(__int64 (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)a2[19] + 24LL))(a2[19]);
        v7 = *((_QWORD *)DesktopAppXProvider::Instance() + 1);
        if ( *(_DWORD *)v7 > 5u
          && (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0
          && (*(_QWORD *)(v7 + 24) & 0x400000000000LL) == *(_QWORD *)(v7 + 24) )
        {
          hObject = v6;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v7,
            (unsigned int)&unk_1800E2882,
            0,
            v8,
            (__int64)&hObject);
        }
      }
    }
    v9 = `wil::Feature<__WilFeatureTraits_Feature_ID51912085>::GetImpl'::`2'::impl;
    if ( (`wil::Feature<__WilFeatureTraits_Feature_ID51912085>::GetImpl'::`2'::impl & 4) == 0 )
    {
      v41 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID51912085>::GetCachedFeatureEnabledState(
                         &`wil::Feature<__WilFeatureTraits_Feature_ID51912085>::GetImpl'::`2'::impl,
                         v42);
      v9 = v41;
    }
    v35 = 0;
    v36 = 3;
    v34 = &v35;
    wil::details::ReportUsageToService(&unk_1801085F0, 51912085, (v9 >> 10) & 1, (v9 >> 11) & 1);
    v10 = OpenProcess(0x1101u, 0, a3->dwProcessId);
    if ( !v10 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x26C,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v11);
    ProcessHandle = v10;
    v38 = 0;
    v12 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator&(&v38);
    if ( !OpenProcessToken(ProcessHandle, 8u, v12) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x271,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v13);
    v14 = helium::ContainerTypeForPackagedToken(v38, a2);
    v42[1] = &ProcessHandle;
    v43 = 1;
    v15 = OpenThread(2u, 0, a3->dwThreadId);
    v17 = v15;
    if ( !v15 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x27D,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
        v16);
    v42[0] = v15;
    PlaceProcessIntoUIContainer(ProcessHandle, (struct DESKTOP_APPX_LAUNCH_CONTEXT *)a2);
    v18 = IsLifecycleManagedCentennialApplication(v38);
    if ( !v18 )
    {
      v19 = DamRegisterProcess(ProcessHandle);
      if ( v19 < 0 && v19 != -2147467262 && v19 != -2147024846 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2B4,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          (const char *)(unsigned int)v19,
          (int)&v35);
    }
    v20 = 0;
    if ( !*((_DWORD *)a2 + 12) && !v18 )
      v20 = helium::AddProcessToHeliumContainer(ProcessHandle, a2[19], a1, v14);
    v21 = v20 != 0;
    if ( *((_BYTE *)a2 + 64) )
    {
      if ( !v18 && v20 )
      {
        LODWORD(v34) = v14;
        v21 = CheckContainerInActivatableStatePostAddProcess(a2[19], a1, v20, 0);
      }
      if ( *((_BYTE *)a2 + 65) || v18 )
      {
        v35 = 0;
        v28 = PsmQueryBackgroundActivationType(v38, &v35);
        if ( v28 < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x2F2,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)v28,
            (int)v34);
        v29 = 0;
        if ( v35 )
        {
          if ( v35 == 2 )
          {
            v29 = 8;
          }
          else if ( v35 == 3 )
          {
            v29 = 4;
          }
        }
        else
        {
          v29 = 1;
        }
        v30 = PsmRegisterApplicationProcess(ProcessHandle, v29);
        if ( v30 < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x307,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)v30,
            (int)v34);
      }
      else
      {
        v22 = *((_DWORD *)a2 + 4) != 0 ? 2 : 0;
        GetAppContainerTokenForPackageAndUser(&hObject, *a2, a1, v14);
        v23 = HamRegisterDesktopProcessWithAppContainerToken(ProcessHandle, (unsigned int)(v22 + 128), hObject);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_NtStatus(
            retaddr,
            (void *)0x2EC,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)(unsigned int)v23,
            (int)v34);
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
      }
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::GetImpl'::`2'::impl);
    v26 = v40;
    if ( IsEnabled )
    {
      v27 = CAMHandlePackagedProcessLaunch(v40->dwProcessId);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x312,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
          (const char *)(unsigned int)v27,
          (int)v34);
    }
    if ( *((_DWORD *)a2 + 4) )
    {
      if ( v21 )
      {
        LODWORD(v34) = v14;
        v21 = CheckContainerInActivatableStatePostAddProcess(a2[19], a1, v20, 1);
      }
      if ( ((_BYTE)a2[5] & 4) != 0 && SuspendThread(v17) == -1 )
      {
        LastError = GetLastError();
        if ( LastError )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x320,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
            (const char *)LastError,
            (unsigned int)v34);
      }
      LaunchDebugger(a2[3], v26, a1, v25);
    }
    if ( v21 )
      CheckContainerInActivatableStatePostAddProcess(a2[19], a1, v20, 2);
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v44);
    if ( v17 != (void *)-1LL )
      CloseHandle(v17);
    if ( (char *)v38 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v38);
    if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(ProcessHandle);
    v44 = &DesktopAppXProvider::PostDesktopActivation::`vftable';
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v44);
    wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(&v44);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x32B,
                           (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\processcreationextensions.cpp",
                           v32);
  }
  return result;
}

```

## disassembly

```asm
0x180022b30  mov     r11, rsp
0x180022b33  push    rbx
0x180022b34  push    rsi
0x180022b35  push    rdi
0x180022b36  push    r12
0x180022b38  push    r13
0x180022b3a  push    r14
0x180022b3c  push    r15
0x180022b3e  sub     rsp, 1F0h
0x180022b45  mov     rax, cs:__security_cookie
0x180022b4c  xor     rax, rsp
0x180022b4f  mov     [rsp+228h+var_48], rax
0x180022b57  mov     rsi, r8
0x180022b5a  mov     [rsp+228h+var_1C8], r8
0x180022b5f  mov     rbx, rdx
0x180022b62  mov     r13, rcx
0x180022b65  xor     r15d, r15d
0x180022b68  mov     [r11-190h], r15d
0x180022b6f  mov     [r11-18Ch], r15b
0x180022b76  mov     [r11-150h], r15b
0x180022b7d  mov     [r11-168h], r15d
0x180022b84  lea     rax, aPostdesktopact; "PostDesktopActivation"
0x180022b8b  mov     [r11-160h], rax
0x180022b92  mov     [r11-158h], r15
0x180022b99  mov     [r11-148h], r15d
0x180022ba0  xorps   xmm0, xmm0
0x180022ba3  movdqa  [rsp+228h+var_A8], xmm0
0x180022bac  xor     edx, edx; Val
0x180022bae  mov     r8d, 98h; Size
0x180022bb4  lea     rcx, [r11-140h]; void *
0x180022bbb  call    memset_0
0x180022bc0  lea     r14d, [r15+1]
0x180022bc4  mov     [rsp+228h+var_98], r14d
0x180022bcc  xor     eax, eax
0x180022bce  mov     [rsp+228h+var_90], rax
0x180022bd6  lea     rax, [rsp+228h+var_190]
0x180022bde  mov     [rsp+228h+var_88], rax
0x180022be6  mov     [rsp+228h+var_80], r15
0x180022bee  mov     [rsp+228h+var_78], r15
0x180022bf6  lea     rax, [rsp+228h+var_198]
0x180022bfe  mov     [rsp+228h+var_70], rax
0x180022c06  mov     [rsp+228h+var_68], r15
0x180022c0e  mov     [rsp+228h+var_60], r15d
0x180022c16  lea     rax, [rsp+228h+var_168]
0x180022c1e  mov     [rsp+228h+var_58], rax
0x180022c26  lea     rax, ??_7PostDesktopActivation@DesktopAppXProvider@@6B@; const DesktopAppXProvider::PostDesktopActivation::`vftable'
0x180022c2d  mov     [rsp+228h+var_198], rax
0x180022c35  mov     r8, [rbx+8]; unsigned __int16 *
0x180022c39  mov     rdx, [rbx]; unsigned __int16 *
0x180022c3c  lea     rcx, [rsp+228h+var_198]; this
0x180022c44  call    ?StartActivity@PostDesktopActivation@DesktopAppXProvider@@QEAAXPEBG0@Z; DesktopAppXProvider::PostDesktopActivation::StartActivity(ushort const *,ushort const *)
0x180022c49  nop
0x180022c4a  cmp     [rbx+30h], r15d
0x180022c4e  jnz     short loc_180022CC6
0x180022c50  mov     rcx, [rbx+98h]
0x180022c57  mov     rax, [rcx]
0x180022c5a  mov     rax, [rax+20h]
0x180022c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c63  test    al, al
0x180022c65  jz      short loc_180022CC6
0x180022c67  mov     rcx, [rbx+98h]
0x180022c6e  mov     rax, [rcx]
0x180022c71  mov     rax, [rax+18h]
0x180022c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c7a  mov     rdi, rax
0x180022c7d  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x180022c82  mov     rcx, [rax+8]
0x180022c86  cmp     dword ptr [rcx], 5
0x180022c89  jbe     short loc_180022CC6
0x180022c8b  mov     rdx, 400000000000h
0x180022c95  test    [rcx+10h], rdx
0x180022c99  jz      short loc_180022CC6
0x180022c9b  mov     rax, [rcx+18h]
0x180022c9f  and     rax, rdx
0x180022ca2  cmp     rax, [rcx+18h]
0x180022ca6  jnz     short loc_180022CC6
0x180022ca8  mov     [rsp+228h+hObject], rdi
0x180022cad  lea     rax, [rsp+228h+hObject]
0x180022cb2  mov     qword ptr [rsp+228h+var_208], rax
0x180022cb7  xor     r8d, r8d
0x180022cba  lea     rdx, unk_1800E2882
0x180022cc1  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180022cc6  mov     r8d, cs:?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID51912085@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID51912085@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID51912085> `wil::Feature<__WilFeatureTraits_Feature_ID51912085>::GetImpl(void)'::`2'::impl
0x180022ccd  test    r8b, 4
0x180022cd1  jnz     short loc_180022CEF
0x180022cd3  lea     rdx, [rsp+228h+var_1B8]
0x180022cd8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID51912085@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID51912085@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID51912085> `wil::Feature<__WilFeatureTraits_Feature_ID51912085>::GetImpl(void)'::`2'::impl
0x180022cdf  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID51912085@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID51912085>::GetCachedFeatureEnabledState(void)
0x180022ce4  mov     rax, [rax]
0x180022ce7  mov     [rsp+228h+var_1C0], rax
0x180022cec  mov     r8d, eax
0x180022cef  mov     [rsp+228h+var_1E8], r15d
0x180022cf4  mov     [rsp+228h+var_1E4], 3
0x180022cfb  mov     r9d, r8d
0x180022cfe  shr     r9d, 0Bh
0x180022d02  and     r9d, r14d
0x180022d05  shr     r8d, 0Ah
0x180022d09  and     r8d, r14d
0x180022d0c  mov     [rsp+228h+var_1F8], 3
0x180022d14  mov     [rsp+228h+var_200], r14d
0x180022d19  lea     rax, [rsp+228h+var_1E8]
0x180022d1e  mov     qword ptr [rsp+228h+var_208], rax; int
0x180022d23  mov     edx, 3181D95h
0x180022d28  lea     rcx, unk_1801085F0
0x180022d2f  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180022d34  mov     r8d, [rsi+10h]; dwProcessId
0x180022d38  xor     edx, edx; bInheritHandle
0x180022d3a  mov     ecx, 1101h; dwDesiredAccess
0x180022d3f  call    cs:__imp_OpenProcess
0x180022d46  nop     dword ptr [rax+rax+00h]
0x180022d4b  mov     rcx, [rsp+228h]; this
0x180022d53  test    rax, rax
0x180022d56  jz      loc_1800230E0
0x180022d5c  mov     [rsp+228h+ProcessHandle], rax
0x180022d61  mov     [rsp+228h+var_1D8], r15
0x180022d66  lea     rcx, [rsp+228h+var_1D8]
0x180022d6b  call    ??I?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator&(void)
0x180022d70  mov     rdi, [rsp+228h]
0x180022d78  mov     r8, rax; TokenHandle
0x180022d7b  mov     edx, 8; DesiredAccess
0x180022d80  mov     rcx, [rsp+228h+ProcessHandle]; ProcessHandle
0x180022d85  call    cs:__imp_OpenProcessToken
0x180022d8c  nop     dword ptr [rax+rax+00h]
0x180022d91  test    eax, eax
0x180022d93  jz      loc_1800230F2
0x180022d99  mov     rdx, rbx
0x180022d9c  mov     rcx, [rsp+228h+var_1D8]
0x180022da1  call    ?ContainerTypeForPackagedToken@helium@@YA?AW4ContainerType@1@PEAXPEBUDESKTOP_APPX_LAUNCH_CONTEXT@@@Z; helium::ContainerTypeForPackagedToken(void *,DESKTOP_APPX_LAUNCH_CONTEXT const *)
0x180022da6  mov     r12d, eax
0x180022da9  lea     rax, [rsp+228h+ProcessHandle]
0x180022dae  mov     [rsp+228h+var_1B0], rax
0x180022db3  mov     [rsp+228h+var_1A8], r14b
0x180022dbb  mov     r8d, [rsi+14h]; dwThreadId
0x180022dbf  xor     edx, edx; bInheritHandle
0x180022dc1  lea     ecx, [rdx+2]; dwDesiredAccess
0x180022dc4  call    cs:__imp_OpenThread
0x180022dcb  nop     dword ptr [rax+rax+00h]
0x180022dd0  mov     r14, rax
0x180022dd3  mov     rcx, [rsp+228h]; this
0x180022ddb  test    rax, rax
0x180022dde  jz      loc_180023107
0x180022de4  mov     [rsp+228h+var_1B8], r14
0x180022de9  mov     rdx, rbx; struct DESKTOP_APPX_LAUNCH_CONTEXT *
0x180022dec  mov     rcx, [rsp+228h+ProcessHandle]; hProcess
0x180022df1  call    ?PlaceProcessIntoUIContainer@@YAXPEAXPEAUDESKTOP_APPX_LAUNCH_CONTEXT@@@Z; PlaceProcessIntoUIContainer(void *,DESKTOP_APPX_LAUNCH_CONTEXT *)
0x180022df6  mov     rcx, [rsp+228h+var_1D8]; void *
0x180022dfb  call    ?IsLifecycleManagedCentennialApplication@@YA_NPEAX@Z; IsLifecycleManagedCentennialApplication(void *)
0x180022e00  mov     dil, al
0x180022e03  test    al, al
0x180022e05  jnz     short loc_180022E27
0x180022e07  mov     rcx, [rsp+228h+ProcessHandle]; ProcessHandle
0x180022e0c  call    DamRegisterProcess
0x180022e11  test    eax, eax
0x180022e13  jns     short loc_180022E27
0x180022e15  cmp     eax, 80004002h
0x180022e1a  jz      short loc_180022E27
0x180022e1c  cmp     eax, 80070032h
0x180022e21  jnz     loc_180023119
0x180022e27  mov     esi, r15d
0x180022e2a  cmp     [rbx+30h], r15d
0x180022e2e  jnz     short loc_180022E4E
0x180022e30  test    dil, dil
0x180022e33  jnz     short loc_180022E4E
0x180022e35  mov     r9d, r12d
0x180022e38  mov     r8, r13
0x180022e3b  mov     rdx, [rbx+98h]
0x180022e42  mov     rcx, [rsp+228h+ProcessHandle]
0x180022e47  call    ?AddProcessToHeliumContainer@helium@@YA?AW4ProcessContainerDisposition@1@PEAXAEBVHeliumSpecification@1@0W4ContainerType@1@@Z; helium::AddProcessToHeliumContainer(void *,helium::HeliumSpecification const &,void *,helium::ContainerType)
0x180022e4c  mov     esi, eax
0x180022e4e  test    esi, esi
0x180022e50  setnz   r15b
0x180022e54  cmp     byte ptr [rbx+40h], 0
0x180022e58  jz      loc_180022EF4
0x180022e5e  test    dil, dil
0x180022e61  jnz     short loc_180022E84
0x180022e63  test    esi, esi
0x180022e65  jz      short loc_180022E84
0x180022e67  mov     [rsp+228h+var_208], r12d; int
0x180022e6c  xor     r9d, r9d
0x180022e6f  mov     r8d, esi
0x180022e72  mov     rdx, r13
0x180022e75  mov     rcx, [rbx+98h]
0x180022e7c  call    ?CheckContainerInActivatableStatePostAddProcess@@YA_NAEBVHeliumSpecification@helium@@PEAXW4ProcessContainerDisposition@2@W4PostAddProcessCheckpoint@@W4ContainerType@2@@Z; CheckContainerInActivatableStatePostAddProcess(helium::HeliumSpecification const &,void *,helium::ProcessContainerDisposition,PostAddProcessCheckpoint,helium::ContainerType)
0x180022e81  mov     r15b, al
0x180022e84  cmp     byte ptr [rbx+41h], 0
0x180022e88  jnz     loc_180022F27
0x180022e8e  test    dil, dil
0x180022e91  jnz     loc_180022F27
0x180022e97  mov     ecx, [rbx+10h]
0x180022e9a  neg     ecx
0x180022e9c  sbb     edi, edi
0x180022e9e  and     edi, 2
0x180022ea1  mov     r9d, r12d
0x180022ea4  mov     r8, r13
0x180022ea7  mov     rdx, [rbx]
0x180022eaa  lea     rcx, [rsp+228h+hObject]
0x180022eaf  call    ?GetAppContainerTokenForPackageAndUser@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEBGPEAXW4ContainerType@helium@@@Z; GetAppContainerTokenForPackageAndUser(ushort const *,void *,helium::ContainerType)
0x180022eb4  nop
0x180022eb5  mov     r8, [rsp+228h+hObject]
0x180022eba  lea     edx, [rdi+80h]
0x180022ec0  mov     rcx, [rsp+228h+ProcessHandle]
0x180022ec5  call    cs:__imp_HamRegisterDesktopProcessWithAppContainerToken
0x180022ecc  nop     dword ptr [rax+rax+00h]
0x180022ed1  test    eax, eax
0x180022ed3  js      loc_180023136
0x180022ed9  mov     rcx, [rsp+228h+hObject]; hObject
0x180022ede  lea     rax, [rcx-1]
0x180022ee2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022ee6  ja      short loc_180022EF4
0x180022ee8  call    cs:__imp_CloseHandle
0x180022eef  nop     dword ptr [rax+rax+00h]
0x180022ef4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Win32ProcessCapabilities> `wil::Feature<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::GetImpl(void)'::`2'::impl
0x180022efb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Win32ProcessCapabilities@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Win32ProcessCapabilities>::__private_IsEnabled(void)
0x180022f00  mov     rdi, [rsp+228h+var_1C8]
0x180022f05  test    al, al
0x180022f07  jz      loc_180022F9D
0x180022f0d  mov     ecx, [rdi+10h]; unsigned int
0x180022f10  call    CAMHandlePackagedProcessLaunch
0x180022f15  mov     rcx, [rsp+228h]; this
0x180022f1d  test    eax, eax
0x180022f1f  js      loc_180023153
0x180022f25  jmp     short loc_180022F9D
0x180022f27  and     [rsp+228h+var_1E8], 0
0x180022f2c  lea     rdx, [rsp+228h+var_1E8]
0x180022f31  mov     rcx, [rsp+228h+var_1D8]
0x180022f36  call    cs:__imp_PsmQueryBackgroundActivationType
0x180022f3d  nop     dword ptr [rax+rax+00h]
0x180022f42  mov     rcx, [rsp+228h]; this
0x180022f4a  test    eax, eax
0x180022f4c  js      loc_180023167
0x180022f52  xor     edx, edx
0x180022f54  mov     ecx, [rsp+228h+var_1E8]
0x180022f58  test    ecx, ecx
0x180022f5a  jz      short loc_180022F72
0x180022f5c  sub     ecx, 2
0x180022f5f  jz      short loc_180022F6B
0x180022f61  cmp     ecx, 1
0x180022f64  jnz     short loc_180022F77
0x180022f66  lea     edx, [rcx+3]
0x180022f69  jmp     short loc_180022F77
0x180022f6b  mov     edx, 8
0x180022f70  jmp     short loc_180022F77
0x180022f72  mov     edx, 1
0x180022f77  mov     rcx, [rsp+228h+ProcessHandle]
0x180022f7c  call    cs:__imp_PsmRegisterApplicationProcess
0x180022f83  nop     dword ptr [rax+rax+00h]
0x180022f88  mov     rcx, [rsp+228h]; this
0x180022f90  test    eax, eax
0x180022f92  js      loc_18002317B
0x180022f98  jmp     loc_180022EF4
0x180022f9d  cmp     dword ptr [rbx+10h], 0
0x180022fa1  jz      short loc_18002300D
0x180022fa3  test    r15b, r15b
0x180022fa6  jz      short loc_180022FC8
0x180022fa8  mov     [rsp+228h+var_208], r12d; unsigned int
0x180022fad  mov     r9d, 1
0x180022fb3  mov     r8d, esi
0x180022fb6  mov     rdx, r13
0x180022fb9  mov     rcx, [rbx+98h]
0x180022fc0  call    ?CheckContainerInActivatableStatePostAddProcess@@YA_NAEBVHeliumSpecification@helium@@PEAXW4ProcessContainerDisposition@2@W4PostAddProcessCheckpoint@@W4ContainerType@2@@Z; CheckContainerInActivatableStatePostAddProcess(helium::HeliumSpecification const &,void *,helium::ProcessContainerDisposition,PostAddProcessCheckpoint,helium::ContainerType)
0x180022fc5  mov     r15b, al
0x180022fc8  test    byte ptr [rbx+28h], 4
0x180022fcc  jz      short loc_180022FFE
0x180022fce  mov     rcx, r14; hThread
0x180022fd1  call    cs:__imp_SuspendThread
0x180022fd8  nop     dword ptr [rax+rax+00h]
0x180022fdd  cmp     eax, 0FFFFFFFFh
0x180022fe0  jnz     short loc_180022FFE
0x180022fe2  call    cs:__imp_GetLastError
0x180022fe9  nop     dword ptr [rax+rax+00h]
0x180022fee  mov     rcx, [rsp+228h]; this
0x180022ff6  test    eax, eax
0x180022ff8  jnz     loc_18002318F
0x180022ffe  mov     r8, r13; void *
0x180023001  mov     rdx, rdi; struct _PROCESS_INFORMATION *
0x180023004  mov     rcx, [rbx+18h]; unsigned __int16 *
0x180023008  call    ?LaunchDebugger@@YAXPEBGPEAU_PROCESS_INFORMATION@@PEAXPEAPEAX@Z; LaunchDebugger(ushort const *,_PROCESS_INFORMATION *,void *,void * *)
0x18002300d  test    r15b, r15b
0x180023010  jz      short loc_18002302F
0x180023012  mov     [rsp+228h+var_208], r12d
0x180023017  mov     r9d, 2
0x18002301d  mov     r8d, esi
0x180023020  mov     rdx, r13
0x180023023  mov     rcx, [rbx+98h]
0x18002302a  call    ?CheckContainerInActivatableStatePostAddProcess@@YA_NAEBVHeliumSpecification@helium@@PEAXW4ProcessContainerDisposition@2@W4PostAddProcessCheckpoint@@W4ContainerType@2@@Z; CheckContainerInActivatableStatePostAddProcess(helium::HeliumSpecification const &,void *,helium::ProcessContainerDisposition,PostAddProcessCheckpoint,helium::ContainerType)
0x18002302f  lea     rcx, [rsp+228h+var_198]
0x180023037  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002303c  nop
0x18002303d  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180023041  jz      short loc_180023053
0x180023043  mov     rcx, r14; hObject
0x180023046  call    cs:__imp_CloseHandle
0x18002304d  nop     dword ptr [rax+rax+00h]
0x180023052  nop
0x180023053  mov     rcx, [rsp+228h+var_1D8]; hObject
0x180023058  lea     rax, [rcx-1]
0x18002305c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023060  ja      short loc_18002306F
0x180023062  call    cs:__imp_CloseHandle
0x180023069  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
