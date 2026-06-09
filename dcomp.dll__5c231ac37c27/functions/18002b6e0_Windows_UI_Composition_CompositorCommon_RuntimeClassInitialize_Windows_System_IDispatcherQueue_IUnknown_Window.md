# Windows::UI::Composition::CompositorCommon::RuntimeClassInitialize(Windows::System::IDispatcherQueue *,IUnknown *,Windows::UI::Composition::Core::CompositorController *,Windows::UI::Composition::CompositorCommon::CreationFlags,DirectComposition::DeviceVersion)

- ea: `0x18002b6e0`
- end: `0x18002bae2`
- name: `?RuntimeClassInitialize@CompositorCommon@Composition@UI@Windows@@IEAAJPEAUIDispatcherQueue@System@4@PEAUIUnknown@@PEAVCompositorController@Core@234@W4CreationFlags@1234@W4DeviceVersion@DirectComposition@@@Z`
- size: `1026`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002da00`

## callees

- `0x1800093f4`
- `0x18001358c`
- `0x18002b3c4`
- `0x18002b6e0`
- `0x18002bae8`
- `0x18002bd18`
- `0x18002bd6c`
- `0x18002be50`
- `0x18002c170`
- `0x18002d280`
- `0x180039590`
- `0x180073388`
- `0x1800e08a0`
- `0x1800f8e54`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b7eb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b7eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b826`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b826`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b7f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b7f1`
- `CoreMessaging!CoreUICreate` at `0x18002b7d4`
- `CoreMessaging!CoreUICreate` at `0x18002b7d4`

## string_xrefs

- `0x18002b768`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x18002b7a8`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x18002b9f2`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x18002ba69`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x18002ba97`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x18002bac6`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x18017d4ca`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositor.cpp`
- `0x18002ba83`: `The caller must initialize DispatcherQueue on this thread before this operation.`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositorCommon::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5,
        unsigned int a6)
{
  int v9; // eax
  int v10; // ebx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v12)(_QWORD, GUID *, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, struct IMessageSession **); // rbx
  int v16; // eax
  int v17; // eax
  struct Windows::UI::Composition::Compositor *v18; // rax
  DirectComposition::CDevice **v19; // rdi
  const char *v20; // r9
  __int64 v21; // rcx
  struct IMessageSession *v22; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  struct IMessageSession *v26; // rcx
  __int64 v27; // rdx
  int v28; // [rsp+20h] [rbp-30h]
  const char *v29; // [rsp+28h] [rbp-28h]
  __int64 v30; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  struct IMessageSession *v32; // [rsp+80h] [rbp+30h] BYREF
  __int64 v33; // [rsp+98h] [rbp+48h] BYREF

  *(_QWORD *)(a1 + 448) = a4;
  v32 = 0;
  v9 = Microsoft::WRL2::ContextSession::RuntimeClassInitialize((Microsoft::WRL2::ContextSession *)a1);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DD,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
      (const char *)(unsigned int)v9,
      v28);
LABEL_27:
    v26 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(struct IMessageSession *))(*(_QWORD *)v26 + 16LL))(v26);
    }
    return (unsigned int)v10;
  }
  Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueue>::operator=(a1 + 488, a2);
  v11 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 488);
  v33 = 0;
  if ( v11 )
  {
    v12 = **v11;
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v33);
    v13 = v12(v11, &GUID_1574672c_d483_40de_a90a_83923881cb6e, &v33);
    if ( v13 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
        (const char *)(unsigned int)v13,
        v28);
    v14 = v33;
    v15 = *(__int64 (__fastcall **)(__int64, struct IMessageSession **))(*(_QWORD *)v33 + 24LL);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v32);
    v16 = v15(v14, &v32);
    if ( v16 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
        (const char *)(unsigned int)v16,
        v28);
  }
  else
  {
    if ( (a5 & 1) != 0 )
    {
      v10 = -2147024891;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
        (const char *)0x80070005LL,
        (int)"The caller must initialize DispatcherQueue on this thread before this operation.",
        v29);
LABEL_41:
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v33);
      Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v32);
      return (unsigned int)v10;
    }
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(&v32);
    v17 = CoreUICreate(&v32);
    v10 = v17;
    if ( v17 < 0 )
    {
      v27 = 500;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
        (const char *)(unsigned int)v17,
        v28);
      goto LABEL_41;
    }
  }
  AcquireSRWLockExclusive(&Windows::UI::Composition::CompositorCommon::s_lockCompositors);
  GetCurrentThreadId();
  v18 = Windows::UI::Composition::CompositorCommon::s_pFirstCompositorWeak;
  *(_QWORD *)(a1 + 400) = Windows::UI::Composition::CompositorCommon::s_pFirstCompositorWeak;
  if ( v18 )
    *((_QWORD *)v18 + 49) = a1;
  Windows::UI::Composition::CompositorCommon::s_pFirstCompositorWeak = (struct Windows::UI::Composition::Compositor *)a1;
  dword_1801E14D8 = 0;
  ReleaseSRWLockExclusive(&Windows::UI::Composition::CompositorCommon::s_lockCompositors);
  v30 = a1;
  v17 = Microsoft::WRL2::Details::MakeAndInitialize2<Windows::UI::Composition::DeviceOwner,Windows::UI::Composition::DeviceOwner,Windows::UI::Composition::Compositor *>(
          a1 + 496,
          &v30);
  v10 = v17;
  if ( v17 < 0 )
  {
    v27 = 544;
    goto LABEL_40;
  }
  v19 = (DirectComposition::CDevice **)(a1 + 440);
  v10 = DirectComposition::CDevice::Create(
          (*(_QWORD *)(a1 + 496) + 24LL) & -(__int64)(*(_QWORD *)(a1 + 496) != 0),
          a6,
          a3,
          a1 + 440);
  if ( v10 < 0 )
  {
    v24 = 550;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
      (const char *)(unsigned int)v10,
      v28);
    v25 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    goto LABEL_27;
  }
  (*(void (__fastcall **)(__int64, __int64))(*((_QWORD *)*v19 + 3) + 256LL))((__int64)*v19 + 24, 1);
  if ( !v32 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositor.cpp",
      v20);
  DirectComposition::CDevice::ConfigureMessageSession(*v19, v32);
  Microsoft::WRL2::ContextSession::SetMessageSession((Microsoft::WRL2::ContextSession *)a1, v32);
  v28 = 0;
  v17 = (*(__int64 (__fastcall **)(struct IMessageSession *, __int64 (__fastcall *)(void *), __int64, __int64 (__fastcall *)()))(*(_QWORD *)v32 + 96LL))(
          v32,
          Windows::UI::Composition::CompositorCommon::StaticCallCommit_NoLock,
          a1,
          DwmpEnableDDASupport);
  v10 = v17;
  if ( v17 < 0 )
  {
    v27 = 574;
    goto LABEL_40;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 416) + 32LL))(*(_QWORD *)(a1 + 416), 2);
  if ( v10 < 0 )
  {
    v24 = 586;
    goto LABEL_25;
  }
  v28 = 0;
  v10 = (*(__int64 (__fastcall **)(struct IMessageSession *, __int64 (__fastcall *)(Windows::UI::Composition::CompositorCommon *), __int64, __int64 (__fastcall *)()))(*(_QWORD *)v32 + 96LL))(
          v32,
          Windows::UI::Composition::CompositorCommon::Static_InvokeDeferredCallbacks_NoLock,
          a1,
          DwmpEnableDDASupport);
  if ( v10 < 0 )
  {
    v24 = 593;
    goto LABEL_25;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 424) + 32LL))(*(_QWORD *)(a1 + 424), 3);
  if ( v10 < 0 )
  {
    v24 = 595;
    goto LABEL_25;
  }
  *(_QWORD *)(a1 + 616) = a1;
  *(_QWORD *)(a1 + 688) = a1;
  *(_QWORD *)(a1 + 760) = a1;
  v10 = DirectComposition::CMessageConversationHost::Create(
          *v19,
          0,
          (int (*)(const void *, const void *, const void *, unsigned int))Windows::UI::Composition::CompositorCommon::s_OnCallbackMessage_NoLock,
          (void *)a1,
          (struct DirectComposition::CMessageConversationHost **)(a1 + 408));
  if ( v10 < 0 )
  {
    v24 = 608;
    goto LABEL_25;
  }
  Windows::UI::Composition::CompositorCommon::MarkDirty((Windows::UI::Composition::CompositorCommon *)a1);
  v21 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(struct IMessageSession *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b6e0  mov     [rsp-28h+arg_8], rbx
0x18002b6e5  push    rbp
0x18002b6e6  push    rsi
0x18002b6e7  push    rdi
0x18002b6e8  push    r14
0x18002b6ea  push    r15
0x18002b6ec  mov     rbp, rsp
0x18002b6ef  sub     rsp, 50h
0x18002b6f3  xor     r15d, r15d
0x18002b6f6  mov     [rcx+1C0h], r9
0x18002b6fd  mov     [rbp+arg_0], r15
0x18002b701  mov     r14, r8
0x18002b704  mov     rdi, rdx
0x18002b707  mov     rsi, rcx
0x18002b70a  call    ?RuntimeClassInitialize@ContextSession@WRL2@Microsoft@@IEAAJXZ; Microsoft::WRL2::ContextSession::RuntimeClassInitialize(void)
0x18002b70f  mov     ebx, eax
0x18002b711  test    eax, eax
0x18002b713  js      loc_18002BA65
0x18002b719  lea     rbx, [rsi+1E8h]
0x18002b720  mov     rdx, rdi
0x18002b723  mov     rcx, rbx
0x18002b726  call    ??4?$ComPtr@UIDispatcherQueue@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDispatcherQueue@System@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueue>::operator=(Windows::System::IDispatcherQueue *)
0x18002b72b  mov     rdi, [rbx]
0x18002b72e  mov     [rbp+arg_18], r15
0x18002b732  test    rdi, rdi
0x18002b735  jz      loc_18002B7BD
0x18002b73b  mov     rax, [rdi]
0x18002b73e  lea     rcx, [rbp+arg_18]
0x18002b742  mov     rbx, [rax]
0x18002b745  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18002b74a  lea     r8, [rbp+arg_18]
0x18002b74e  mov     rcx, rdi
0x18002b751  lea     rdx, _GUID_1574672c_d483_40de_a90a_83923881cb6e
0x18002b758  mov     rax, rbx
0x18002b75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b760  test    eax, eax
0x18002b762  jns     short loc_18002B77D
0x18002b764  mov     rcx, [rbp+28h]; this
0x18002b768  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18002b76f  mov     r9d, eax; char *
0x18002b772  mov     edx, 1FBh; void *
0x18002b777  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002b77d  mov     rdi, [rbp+arg_18]
0x18002b781  lea     rcx, [rbp+arg_0]
0x18002b785  mov     rax, [rdi]
0x18002b788  mov     rbx, [rax+18h]
0x18002b78c  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18002b791  lea     rdx, [rbp+arg_0]
0x18002b795  mov     rcx, rdi
0x18002b798  mov     rax, rbx
0x18002b79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7a0  test    eax, eax
0x18002b7a2  jns     short loc_18002B7E4
0x18002b7a4  mov     rcx, [rbp+28h]; this
0x18002b7a8  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18002b7af  mov     r9d, eax; char *
0x18002b7b2  mov     edx, 1FDh; void *
0x18002b7b7  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002b7bd  test    [rbp+arg_20], 1
0x18002b7c1  jnz     loc_18002BA7F
0x18002b7c7  lea     rcx, [rbp+arg_0]
0x18002b7cb  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18002b7d0  lea     rcx, [rbp+arg_0]
0x18002b7d4  call    cs:__imp_CoreUICreate
0x18002b7da  mov     ebx, eax
0x18002b7dc  test    eax, eax
0x18002b7de  js      loc_18002BAAE
0x18002b7e4  lea     rcx, ?s_lockCompositors@CompositorCommon@Composition@UI@Windows@@0VCReadWriteLock@@A; SRWLock
0x18002b7eb  call    cs:__imp_AcquireSRWLockExclusive
0x18002b7f1  call    cs:__imp_GetCurrentThreadId
0x18002b7f7  mov     rax, cs:?s_pFirstCompositorWeak@CompositorCommon@Composition@UI@Windows@@0PEAVCompositor@234@EA; Windows::UI::Composition::Compositor * Windows::UI::Composition::CompositorCommon::s_pFirstCompositorWeak
0x18002b7fe  mov     [rsi+190h], rax
0x18002b805  test    rax, rax
0x18002b808  jz      short loc_18002B811
0x18002b80a  mov     [rax+188h], rsi
0x18002b811  lea     rcx, ?s_lockCompositors@CompositorCommon@Composition@UI@Windows@@0VCReadWriteLock@@A; SRWLock
0x18002b818  mov     cs:?s_pFirstCompositorWeak@CompositorCommon@Composition@UI@Windows@@0PEAVCompositor@234@EA, rsi; Windows::UI::Composition::Compositor * Windows::UI::Composition::CompositorCommon::s_pFirstCompositorWeak
0x18002b81f  mov     cs:dword_1801E14D8, r15d
0x18002b826  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b82c  lea     rdi, [rsi+1F0h]
0x18002b833  mov     [rbp+var_10], rsi
0x18002b837  mov     rcx, rdi
0x18002b83a  lea     rdx, [rbp+var_10]
0x18002b83e  call    ??$MakeAndInitialize2@VDeviceOwner@Composition@UI@Windows@@V1234@PEAVCompositor@234@@Details@WRL2@Microsoft@@YAJPEAPEAVDeviceOwner@Composition@UI@Windows@@$$QEAPEAVCompositor@456@@Z; Microsoft::WRL2::Details::MakeAndInitialize2<Windows::UI::Composition::DeviceOwner,Windows::UI::Composition::DeviceOwner,Windows::UI::Composition::Compositor *>(Windows::UI::Composition::DeviceOwner * *,Windows::UI::Composition::Compositor * &&)
0x18002b843  mov     ebx, eax
0x18002b845  test    eax, eax
0x18002b847  js      loc_18002BAB8
0x18002b84d  mov     rcx, [rdi]
0x18002b850  mov     r8, r14
0x18002b853  mov     edx, [rbp+arg_28]
0x18002b856  lea     rdi, [rsi+1B8h]
0x18002b85d  mov     r9, rdi
0x18002b860  lea     rax, [rcx+18h]
0x18002b864  neg     rcx
0x18002b867  sbb     rcx, rcx
0x18002b86a  and     rcx, rax
0x18002b86d  call    ?Create@CDevice@DirectComposition@@SAJPEAUIDeviceOwner@2@W4DeviceVersion@2@PEAUIUnknown@@PEAPEAV12@@Z; DirectComposition::CDevice::Create(DirectComposition::IDeviceOwner *,DirectComposition::DeviceVersion,IUnknown *,DirectComposition::CDevice * *)
0x18002b872  mov     ebx, eax
0x18002b874  test    eax, eax
0x18002b876  js      loc_18002BA5E
0x18002b87c  mov     rcx, [rdi]
0x18002b87f  mov     edx, 1
0x18002b884  add     rcx, 18h
0x18002b888  mov     rax, [rcx]
0x18002b88b  mov     rax, [rax+100h]
0x18002b892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b897  mov     rdx, [rbp+arg_0]; struct IMessageSession *
0x18002b89b  test    rdx, rdx
0x18002b89e  jz      loc_18002BAC2
0x18002b8a4  mov     rcx, [rdi]; this
0x18002b8a7  call    ?ConfigureMessageSession@CDevice@DirectComposition@@QEAAXPEAUIMessageSession@@@Z; DirectComposition::CDevice::ConfigureMessageSession(IMessageSession *)
0x18002b8ac  mov     rdx, [rbp+arg_0]; struct IMessageSession *
0x18002b8b0  mov     rcx, rsi; this
0x18002b8b3  call    ?SetMessageSession@ContextSession@WRL2@Microsoft@@IEAAXPEAUIMessageSession@@@Z; Microsoft::WRL2::ContextSession::SetMessageSession(IMessageSession *)
0x18002b8b8  mov     rcx, [rbp+arg_0]
0x18002b8bc  lea     r14, [rsi+1A0h]
0x18002b8c3  mov     [rsp+50h+var_28], r14
0x18002b8c8  lea     r9, DwmpEnableDDASupport
0x18002b8cf  mov     r8, rsi
0x18002b8d2  mov     [rsp+50h+var_30], r15; int
0x18002b8d7  lea     rdx, ?StaticCallCommit_NoLock@CompositorCommon@Composition@UI@Windows@@CAJPEAX@Z; Windows::UI::Composition::CompositorCommon::StaticCallCommit_NoLock(void *)
0x18002b8de  mov     rax, [rcx]
0x18002b8e1  mov     rax, [rax+60h]
0x18002b8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8ea  mov     ebx, eax
0x18002b8ec  test    eax, eax
0x18002b8ee  js      loc_18002BAD8
0x18002b8f4  mov     rcx, [r14]
0x18002b8f7  mov     edx, 2
0x18002b8fc  mov     rax, [rcx]
0x18002b8ff  mov     rax, [rax+20h]
0x18002b903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b908  mov     ebx, eax
0x18002b90a  test    eax, eax
0x18002b90c  js      loc_18002B9E9
0x18002b912  mov     rcx, [rbp+arg_0]
0x18002b916  lea     r14, [rsi+1A8h]
0x18002b91d  mov     [rsp+50h+var_28], r14
0x18002b922  lea     r9, DwmpEnableDDASupport
0x18002b929  mov     r8, rsi
0x18002b92c  mov     [rsp+50h+var_30], r15
0x18002b931  lea     rdx, ?Static_InvokeDeferredCallbacks_NoLock@CompositorCommon@Composition@UI@Windows@@CAJPEAX@Z; Windows::UI::Composition::CompositorCommon::Static_InvokeDeferredCallbacks_NoLock(void *)
0x18002b938  mov     rax, [rcx]
0x18002b93b  mov     rax, [rax+60h]
0x18002b93f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b944  mov     ebx, eax
0x18002b946  test    eax, eax
0x18002b948  js      loc_18002BA57
0x18002b94e  mov     rcx, [r14]
0x18002b951  mov     edx, 3
0x18002b956  mov     rax, [rcx]
0x18002b959  mov     rax, [rax+20h]
0x18002b95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b962  mov     ebx, eax
0x18002b964  test    eax, eax
0x18002b966  js      loc_18002BA49
0x18002b96c  mov     [rsi+268h], rsi
0x18002b973  lea     rax, [rsi+198h]
0x18002b97a  mov     [rsi+2B0h], rsi
0x18002b981  lea     r8, ?s_OnCallbackMessage_NoLock@CompositorCommon@Composition@UI@Windows@@SAJPEBX00I@Z; int (*)(const void *, const void *, const void *, unsigned int)
0x18002b988  mov     [rsi+2F8h], rsi
0x18002b98f  mov     r9, rsi; void *
0x18002b992  mov     rcx, [rdi]; struct DirectComposition::CDevice *
0x18002b995  xor     edx, edx; bool
0x18002b997  mov     [rsp+50h+var_30], rax; struct DirectComposition::CMessageConversationHost **
0x18002b99c  call    ?Create@CMessageConversationHost@DirectComposition@@SAJPEAVCDevice@2@_NP6AJPEBX22I@ZPEAXPEAPEAV12@@Z; DirectComposition::CMessageConversationHost::Create(DirectComposition::CDevice *,bool,long (*)(void const *,void const *,void const *,uint),void *,DirectComposition::CMessageConversationHost * *)
0x18002b9a1  mov     ebx, eax
0x18002b9a3  test    eax, eax
0x18002b9a5  js      loc_18002BA50
0x18002b9ab  mov     rcx, rsi; this
0x18002b9ae  call    ?MarkDirty@CompositorCommon@Composition@UI@Windows@@QEAAXXZ; Windows::UI::Composition::CompositorCommon::MarkDirty(void)
0x18002b9b3  mov     rcx, [rbp+arg_18]
0x18002b9b7  test    rcx, rcx
0x18002b9ba  jz      short loc_18002B9CC
0x18002b9bc  mov     [rbp+arg_18], r15
0x18002b9c0  mov     rax, [rcx]
0x18002b9c3  mov     rax, [rax+10h]
0x18002b9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9cc  mov     rcx, [rbp+arg_0]
0x18002b9d0  test    rcx, rcx
0x18002b9d3  jz      short loc_18002B9E5
0x18002b9d5  mov     [rbp+arg_0], r15
0x18002b9d9  mov     rax, [rcx]
0x18002b9dc  mov     rax, [rax+10h]
0x18002b9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9e5  xor     eax, eax
0x18002b9e7  jmp     short loc_18002BA35
0x18002b9e9  mov     edx, 24Ah; void *
0x18002b9ee  mov     rcx, [rbp+28h]; this
0x18002b9f2  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18002b9f9  mov     r9d, ebx; char *
0x18002b9fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ba01  mov     rcx, [rbp+arg_18]
0x18002ba05  test    rcx, rcx
0x18002ba08  jz      short loc_18002BA1A
0x18002ba0a  mov     [rbp+arg_18], r15
0x18002ba0e  mov     rax, [rcx]
0x18002ba11  mov     rax, [rax+10h]
0x18002ba15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba1a  mov     rcx, [rbp+arg_0]
0x18002ba1e  test    rcx, rcx
0x18002ba21  jz      short loc_18002BA33
0x18002ba23  mov     [rbp+arg_0], r15
0x18002ba27  mov     rax, [rcx]
0x18002ba2a  mov     rax, [rax+10h]
0x18002ba2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba33  mov     eax, ebx
0x18002ba35  mov     rbx, [rsp+50h+arg_8]
0x18002ba3d  add     rsp, 50h
0x18002ba41  pop     r15
0x18002ba43  pop     r14
0x18002ba45  pop     rdi
0x18002ba46  pop     rsi
0x18002ba47  pop     rbp
0x18002ba48  retn
0x18002ba49  mov     edx, 253h
0x18002ba4e  jmp     short loc_18002B9EE
0x18002ba50  mov     edx, 260h
0x18002ba55  jmp     short loc_18002B9EE
0x18002ba57  mov     edx, 251h
0x18002ba5c  jmp     short loc_18002B9EE
0x18002ba5e  mov     edx, 226h
0x18002ba63  jmp     short loc_18002B9EE
0x18002ba65  mov     rcx, [rbp+28h]; this
0x18002ba69  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18002ba70  mov     r9d, ebx; char *
0x18002ba73  mov     edx, 1DDh; void *
0x18002ba78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ba7d  jmp     short loc_18002BA1A
0x18002ba7f  mov     rcx, [rbp+28h]; this
0x18002ba83  lea     rax, aTheCallerMustI; "The caller must initialize DispatcherQu"...
0x18002ba8a  mov     ebx, 80070005h
0x18002ba8f  mov     [rsp+50h+var_30], rax; int
0x18002ba94  mov     r9d, ebx; char *
0x18002ba97  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18002ba9e  mov     edx, 1ECh; void *
0x18002baa3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002baa8  nop
0x18002baa9  jmp     loc_18017D4D9
0x18002baae  mov     edx, 1F4h; void *
0x18002bab3  jmp     loc_18017D4C6
0x18002bab8  mov     edx, 220h
0x18002babd  jmp     loc_18017D4C6
0x18002bac2  mov     rcx, [rbp+28h]; this
0x18002bac6  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18002bacd  mov     edx, 234h; void *
0x18002bad2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002bad8  mov     edx, 23Eh
0x18002badd  jmp     loc_18017D4C6
0x18017d4c6  mov     rcx, [rbp+28h]; this
0x18017d4ca  lea     r8, aOnecoreuapWind_158; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18017d4d1  mov     r9d, eax; char *
0x18017d4d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017d4d9  lea     rcx, [rbp+arg_18]
0x18017d4dd  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18017d4e2  lea     rcx, [rbp+arg_0]
0x18017d4e6  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x18017d4eb  nop
0x18017d4ec  jmp     loc_18002BA33
```
