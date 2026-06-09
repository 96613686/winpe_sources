# OneCoreUAPInputHost::Initialize(void *)

- ea: `0x180029684`
- end: `0x180029990`
- name: `?Initialize@OneCoreUAPInputHost@@IEAAJPEAX@Z`
- size: `780`
- prototype: `__int64 __fastcall(OneCoreUAPInputHost *__hidden this, void *)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180078f74`

## callees

- `0x180012b74`
- `0x180025470`
- `0x180029160`
- `0x180029684`
- `0x1800299b8`
- `0x1800299e4`
- `0x180029c28`
- `0x18002a770`
- `0x18002ec48`
- `0x180030260`
- `0x18008dcac`
- `0x18008e194`
- `0x18008ead4`
- `0x18008ee44`
- `0x180093358`
- `0x1800f15f8`
- `0x1800f651c`
- `0x1800f7978`
- `0x18013fef8`
- `0x18019fb5c`
- `0x1801ce010`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x1800296c1`
- `CoreMessaging!CoreUICreate` at `0x1800296c1`
- `win32u!NtMITSetInputCallbacks` at `0x18002972d`
- `win32u!NtMITSetInputCallbacks` at `0x18002972d`

## string_xrefs

- `0x180029780`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\inputsinkdatacache\lib\inputsinkdatacache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OneCoreUAPInputHost::Initialize(OneCoreUAPInputHost *this, void *a2)
{
  __int64 v3; // r14
  int v4; // eax
  const char *v5; // r9
  InputSinkDataCache *Instance; // r13
  struct IMessageSession *v7; // rsi
  __int64 (__fastcall *v8)(struct IMessageSession *, __int64 (__fastcall *)(void *), InputSinkDataCache *, char *); // rdi
  int v9; // eax
  struct ISystemInputRouter **v10; // rdi
  char MPCInputPostProcessorPresent; // al
  struct ISystemInputRouter **v12; // r8
  struct IInputFocusListener *v13; // rdx
  int v14; // eax
  int v15; // ebx
  __int64 v16; // rdx
  struct IRawInputClient **v17; // rsi
  int v18; // eax
  int v19; // eax
  const char *v20; // r9
  __int64 v21; // rdx
  int v22; // eax
  int v23; // eax
  struct IMessageSession *v24; // rcx
  int v26; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  struct IMessageSession *v28; // [rsp+60h] [rbp+30h] BYREF
  struct SessionMonitor *v29; // [rsp+70h] [rbp+40h] BYREF

  v3 = *(_QWORD *)&OneCoreUAPInputHost::s_pInputHost;
  v28 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  v4 = CoreUICreate(&v28);
  if ( v4 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\onecoreuap\\lib\\onecoreuapinputhost.cpp",
      (const char *)(unsigned int)v4,
      v26);
  (*(void (__fastcall **)(struct IMessageSession *, int (*)(void *, bool, struct _FILETIME *), __int64))(*(_QWORD *)v28 + 256LL))(
    v28,
    OneCoreUAPInputHost::DeferredInitializeStatic,
    v3);
  if ( !ISMTestMode::s_instance )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\ismstatics\\system\\ismtestmode.cpp",
      v5);
  if ( !*(_BYTE *)ISMTestMode::s_instance )
    NtMITSetInputCallbacks(Win32kInterop::s_DeviceNotificationsCallback);
  ISMStatics::GetForegroundManager();
  ISMStatics::GetInputSiteHierarchyManager();
  Instance = InputSinkDataCache::GetInstance();
  v7 = v28;
  v8 = *(__int64 (__fastcall **)(struct IMessageSession *, __int64 (__fastcall *)(void *), InputSinkDataCache *, char *))(*(_QWORD *)v28 + 144LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)Instance + 96);
  v9 = v8(v7, InputSinkDataCache::OnCacheTimerStatic, Instance, (char *)Instance + 96);
  if ( v9 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\inputsinkdatacache\\lib\\inp"
                    "utsinkdatacache.cpp",
      (const char *)(unsigned int)v9,
      v26);
  InputSinkDataCache::OnCacheTimer(Instance);
  v10 = (struct ISystemInputRouter **)(v3 + 56);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v3 + 56);
  *(_QWORD *)(v3 + 56) = 0;
  MPCInputPostProcessorPresent = IsGetMPCInputPostProcessorPresent();
  v12 = (struct ISystemInputRouter **)(v3 + 56);
  v13 = (struct IInputFocusListener *)((v3 + 8) & -(__int64)(v3 != 0));
  if ( MPCInputPostProcessorPresent )
  {
    v14 = MPCInputRouter::Create(a2, v13, v12);
    v15 = v14;
    if ( v14 < 0 )
    {
      v16 = 30;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\factory\\lib\\inputrouterfactory.cpp",
        (const char *)(unsigned int)v14,
        v26);
      goto LABEL_16;
    }
  }
  else
  {
    v14 = DWMInputRouter::Create((struct IDWMInputProxy *)a2, v13, v12);
    v15 = v14;
    if ( v14 < 0 )
    {
      v16 = 34;
      goto LABEL_12;
    }
  }
  v15 = 0;
LABEL_16:
  if ( v15 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\onecoreuap\\lib\\onecoreuapinputhost.cpp",
      (const char *)(unsigned int)v15,
      v26);
  v17 = (struct IRawInputClient **)(v3 + 64);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v3 + 64);
  v18 = InputStateManager::Create(*v10, (struct IRawInputClient **)(v3 + 64));
  if ( v18 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\onecoreuap\\lib\\onecoreuapinputhost.cpp",
      (const char *)(unsigned int)v18,
      v26);
  v19 = InputProviderManager::InitializeHelper(v3 + 72, *v17, 0);
  if ( v19 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\onecoreuap\\lib\\onecoreuapinputhost.cpp",
      (const char *)(unsigned int)v19,
      v26);
  if ( IsEdition(0xAu) )
  {
    v29 = 0;
    SessionMonitor::Create((struct ISessionMonitorOwner *)((v3 + 16) & -(__int64)(v3 != 0)), v28, &v29);
    v21 = *(_QWORD *)(v3 + 120);
    *(_QWORD *)(v3 + 120) = v29;
    if ( v21 )
      std::default_delete<SessionMonitor>::operator()();
  }
  else if ( IsEdition(0x3DDA1u) )
  {
    v22 = RotationWatcher::Initialize();
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\onecoreuap\\lib\\onecoreuapinputhost.cpp",
        (const char *)(unsigned int)v22,
        v26);
  }
  if ( !ISMTestMode::s_instance )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\ismstatics\\system\\ismtestmode.cpp",
      v20);
  if ( !*(_BYTE *)ISMTestMode::s_instance )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v3 + 104);
    v23 = Win32kInterop::Create(*v17, *v10, (struct Win32kInterop **)(v3 + 104));
    if ( v23 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\onecoreuap\\lib\\onecoreuapinputhost.cpp",
        (const char *)(unsigned int)v23,
        v26);
  }
  v24 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(struct IMessageSession *))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x180029684  mov     [rsp-28h+arg_8], rbx
0x180029689  mov     [rsp-28h+arg_18], rsi
0x18002968e  mov     [rsp-28h+arg_0], rcx
0x180029693  push    rbp
0x180029694  push    rdi
0x180029695  push    r13
0x180029697  push    r14
0x180029699  push    r15
0x18002969b  mov     rbp, rsp
0x18002969e  sub     rsp, 30h
0x1800296a2  mov     r15, rdx
0x1800296a5  mov     r14, cs:?s_pInputHost@OneCoreUAPInputHost@@0PEAV1@EA; OneCoreUAPInputHost * OneCoreUAPInputHost::s_pInputHost
0x1800296ac  mov     [rbp+arg_0], 0
0x1800296b4  lea     rcx, [rbp+arg_0]
0x1800296b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800296bd  lea     rcx, [rbp+arg_0]
0x1800296c1  call    cs:__imp_CoreUICreate
0x1800296c7  mov     rcx, [rbp+28h]; this
0x1800296cb  test    eax, eax
0x1800296cd  jns     short loc_1800296E4
0x1800296cf  mov     r9d, eax; char *
0x1800296d2  lea     r8, aOnecoreuapWind_111; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800296d9  mov     edx, 50h ; 'P'; void *
0x1800296de  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800296e4  mov     rcx, [rbp+arg_0]
0x1800296e8  mov     rax, [rcx]
0x1800296eb  mov     r8, r14
0x1800296ee  lea     rdx, ?DeferredInitializeStatic@OneCoreUAPInputHost@@SAJPEAX_NPEAU_FILETIME@@@Z; OneCoreUAPInputHost::DeferredInitializeStatic(void *,bool,_FILETIME *)
0x1800296f5  mov     rax, [rax+100h]
0x1800296fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029701  mov     rcx, [rbp+28h]; this
0x180029705  mov     rax, cs:?s_instance@ISMTestMode@@0PEAV1@EA; ISMTestMode * ISMTestMode::s_instance
0x18002970c  test    rax, rax
0x18002970f  jnz     short loc_180029721
0x180029711  lea     r8, aOnecoreuapWind_223; "onecoreuap\\windows\\moderncore\\inputv"...
0x180029718  lea     edx, [rax+21h]; void *
0x18002971b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180029721  cmp     byte ptr [rax], 0
0x180029724  jnz     short loc_180029733
0x180029726  lea     rcx, ?s_DeviceNotificationsCallback@Win32kInterop@@SAHPEAU_CLIENT_DEVICE_NOTIFICATION@@@Z; Win32kInterop::s_DeviceNotificationsCallback(_CLIENT_DEVICE_NOTIFICATION *)
0x18002972d  call    cs:__imp_NtMITSetInputCallbacks
0x180029733  call    ?GetForegroundManager@ISMStatics@@SAPEAVForegroundManager@@XZ; ISMStatics::GetForegroundManager(void)
0x180029738  call    ?GetInputSiteHierarchyManager@ISMStatics@@SAPEAUIInputSiteHierarchyManager@@XZ; ISMStatics::GetInputSiteHierarchyManager(void)
0x18002973d  call    ?GetInstance@InputSinkDataCache@@SAAEAV1@XZ; InputSinkDataCache::GetInstance(void)
0x180029742  mov     r13, rax
0x180029745  mov     rsi, [rbp+arg_0]
0x180029749  mov     rdx, [rsi]
0x18002974c  mov     rdi, [rdx+90h]
0x180029753  lea     rcx, [rax+60h]
0x180029757  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002975c  lea     r9, [r13+60h]
0x180029760  mov     r8, r13
0x180029763  lea     rdx, ?OnCacheTimerStatic@InputSinkDataCache@@SAJPEAX@Z; InputSinkDataCache::OnCacheTimerStatic(void *)
0x18002976a  mov     rcx, rsi
0x18002976d  mov     rax, rdi
0x180029770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029775  mov     rcx, [rbp+28h]; this
0x180029779  test    eax, eax
0x18002977b  jns     short loc_180029792
0x18002977d  mov     r9d, eax; char *
0x180029780  lea     r8, aOnecoreuapWind_190; "onecoreuap\\windows\\moderncore\\inputv"...
0x180029787  mov     edx, 0A9h; void *
0x18002978c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180029792  mov     rcx, r13; this
0x180029795  call    ?OnCacheTimer@InputSinkDataCache@@QEAAXXZ; InputSinkDataCache::OnCacheTimer(void)
0x18002979a  lea     rdi, [r14+38h]
0x18002979e  mov     rcx, rdi
0x1800297a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800297a6  mov     rax, r14
0x1800297a9  lea     rcx, [r14+8]
0x1800297ad  neg     rax
0x1800297b0  sbb     rbx, rbx
0x1800297b3  and     rbx, rcx
0x1800297b6  mov     qword ptr [rdi], 0
0x1800297bd  call    IsGetMPCInputPostProcessorPresent
0x1800297c2  mov     r8, rdi; struct ISystemInputRouter **
0x1800297c5  mov     rdx, rbx; struct IInputFocusListener *
0x1800297c8  mov     rcx, r15; struct IDWMInputProxy *
0x1800297cb  test    al, al
0x1800297cd  jz      short loc_1800297F4
0x1800297cf  call    ?Create@MPCInputRouter@@SAJPEAXPEAUIInputFocusListener@@PEAPEAUISystemInputRouter@@@Z; MPCInputRouter::Create(void *,IInputFocusListener *,ISystemInputRouter * *)
0x1800297d4  mov     ebx, eax
0x1800297d6  test    eax, eax
0x1800297d8  jns     short loc_180029806
0x1800297da  mov     edx, 1Eh; void *
0x1800297df  lea     r8, aOnecoreuapWind_238; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800297e6  mov     r9d, eax; char *
0x1800297e9  mov     rcx, [rbp+28h]; this
0x1800297ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800297f2  jmp     short loc_180029808
0x1800297f4  call    ?Create@DWMInputRouter@@SAJPEAXPEAUIInputFocusListener@@PEAPEAUISystemInputRouter@@@Z; DWMInputRouter::Create(void *,IInputFocusListener *,ISystemInputRouter * *)
0x1800297f9  mov     ebx, eax
0x1800297fb  test    eax, eax
0x1800297fd  jns     short loc_180029806
0x1800297ff  mov     edx, 22h ; '"'
0x180029804  jmp     short loc_1800297DF
0x180029806  xor     ebx, ebx
0x180029808  mov     rcx, [rbp+28h]; this
0x18002980c  test    ebx, ebx
0x18002980e  jns     short loc_180029825
0x180029810  mov     r9d, ebx; char *
0x180029813  lea     r8, aOnecoreuapWind_111; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002981a  mov     edx, 64h ; 'd'; void *
0x18002981f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180029825  lea     rsi, [r14+40h]
0x180029829  mov     rcx, rsi
0x18002982c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029831  mov     rdx, rsi; struct IRawInputClient **
0x180029834  mov     rcx, [rdi]; struct ISystemInputRouter *
0x180029837  call    ?Create@InputStateManager@@SAJPEAUISystemInputRouter@@PEAPEAUIRawInputClient@@@Z; InputStateManager::Create(ISystemInputRouter *,IRawInputClient * *)
0x18002983c  mov     rcx, [rbp+28h]; this
0x180029840  test    eax, eax
0x180029842  jns     short loc_180029859
0x180029844  mov     r9d, eax; char *
0x180029847  lea     r8, aOnecoreuapWind_111; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002984e  mov     edx, 66h ; 'f'; void *
0x180029853  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180029859  lea     rcx, [r14+48h]
0x18002985d  xor     r8d, r8d
0x180029860  mov     rdx, [rsi]
0x180029863  call    ?InitializeHelper@InputProviderManager@@AEAAJPEAUIRawInputClient@@W4InputProviderInitialization@@@Z; InputProviderManager::InitializeHelper(IRawInputClient *,InputProviderInitialization)
0x180029868  mov     rcx, [rbp+28h]; this
0x18002986c  test    eax, eax
0x18002986e  jns     short loc_180029885
0x180029870  mov     r9d, eax; char *
0x180029873  lea     r8, aOnecoreuapWind_111; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002987a  mov     edx, 68h ; 'h'; void *
0x18002987f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180029885  mov     ecx, 0Ah; unsigned __int64
0x18002988a  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x18002988f  test    al, al
0x180029891  jz      short loc_1800298D0
0x180029893  mov     [rbp+arg_10], 0
0x18002989b  mov     rax, r14
0x18002989e  lea     rdx, [r14+10h]
0x1800298a2  neg     rax
0x1800298a5  sbb     rcx, rcx
0x1800298a8  and     rcx, rdx; struct ISessionMonitorOwner *
0x1800298ab  lea     r8, [rbp+arg_10]; struct SessionMonitor **
0x1800298af  mov     rdx, [rbp+arg_0]; struct IMessageSession *
0x1800298b3  call    ?Create@SessionMonitor@@SAJPEAUISessionMonitorOwner@@PEAUIMessageSession@@PEAPEAV1@@Z; SessionMonitor::Create(ISessionMonitorOwner *,IMessageSession *,SessionMonitor * *)
0x1800298b8  mov     rdx, [r14+78h]
0x1800298bc  mov     rax, [rbp+arg_10]
0x1800298c0  mov     [r14+78h], rax
0x1800298c4  test    rdx, rdx
0x1800298c7  jz      short loc_1800298FF
0x1800298c9  call    ??R?$default_delete@VSessionMonitor@@@std@@QEBAXPEAVSessionMonitor@@@Z; std::default_delete<SessionMonitor>::operator()(SessionMonitor *)
0x1800298ce  jmp     short loc_1800298FF
0x1800298d0  mov     ecx, 3DDA1h; unsigned __int64
0x1800298d5  call    ?IsEdition@@YA_N_K@Z; IsEdition(unsigned __int64)
0x1800298da  test    al, al
0x1800298dc  jz      short loc_1800298FF
0x1800298de  call    ?Initialize@RotationWatcher@@SAJXZ; RotationWatcher::Initialize(void)
0x1800298e3  mov     rcx, [rbp+28h]; this
0x1800298e7  test    eax, eax
0x1800298e9  jns     short loc_1800298FF
0x1800298eb  mov     r9d, eax; char *
0x1800298ee  lea     r8, aOnecoreuapWind_111; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800298f5  mov     edx, 72h ; 'r'; void *
0x1800298fa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800298ff  mov     rcx, [rbp+28h]; this
0x180029903  mov     rax, cs:?s_instance@ISMTestMode@@0PEAV1@EA; ISMTestMode * ISMTestMode::s_instance
0x18002990a  test    rax, rax
0x18002990d  jnz     short loc_18002991F
0x18002990f  lea     r8, aOnecoreuapWind_223; "onecoreuap\\windows\\moderncore\\inputv"...
0x180029916  lea     edx, [rax+21h]; void *
0x180029919  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002991f  cmp     byte ptr [rax], 0
0x180029922  jnz     short loc_180029959
0x180029924  lea     rcx, [r14+68h]
0x180029928  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002992d  lea     r8, [r14+68h]; struct Win32kInterop **
0x180029931  mov     rdx, [rdi]; struct ISystemInputRouter *
0x180029934  mov     rcx, [rsi]; struct IRawInputClient *
0x180029937  call    ?Create@Win32kInterop@@SAJPEAUIRawInputClient@@PEAUISystemInputRouter@@PEAPEAV1@@Z; Win32kInterop::Create(IRawInputClient *,ISystemInputRouter *,Win32kInterop * *)
0x18002993c  mov     rcx, [rbp+28h]; this
0x180029940  test    eax, eax
0x180029942  jns     short loc_180029959
0x180029944  mov     r9d, eax; char *
0x180029947  lea     r8, aOnecoreuapWind_111; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002994e  mov     edx, 77h ; 'w'; void *
0x180029953  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180029959  mov     rcx, [rbp+arg_0]
0x18002995d  test    rcx, rcx
0x180029960  jz      short loc_180029977
0x180029962  mov     [rbp+arg_0], 0
0x18002996a  mov     rax, [rcx]
0x18002996d  mov     rax, [rax+10h]
0x180029971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029976  nop
0x180029977  xor     eax, eax
0x180029979  mov     rbx, [rsp+30h+arg_8]
0x18002997e  mov     rsi, [rsp+30h+arg_18]
0x180029983  add     rsp, 30h
0x180029987  pop     r15
0x180029989  pop     r14
0x18002998b  pop     r13
0x18002998d  pop     rdi
0x18002998e  pop     rbp
0x18002998f  retn
```
