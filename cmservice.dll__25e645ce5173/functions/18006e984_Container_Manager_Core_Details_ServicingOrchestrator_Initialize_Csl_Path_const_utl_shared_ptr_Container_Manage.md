# Container::Manager::Core::Details::ServicingOrchestrator::Initialize(Csl::Path const &,utl::shared_ptr<Container::Manager::Core::Details::ResourceBroker> const &,utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> const &)

- ea: `0x18006e984`
- end: `0x18006eea1`
- name: `?Initialize@ServicingOrchestrator@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@AEBV?$shared_ptr@VResourceBroker@Details@Core@Manager@Container@@@utl@@AEBV?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@9@@Z`
- size: `1309`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180075104`

## callees

- `0x18000da68`
- `0x18000da88`
- `0x180016658`
- `0x180023b68`
- `0x1800262e4`
- `0x1800471dc`
- `0x1800493c8`
- `0x180069e6c`
- `0x180069f38`
- `0x180069fb4`
- `0x18006e0e8`
- `0x18006e984`
- `0x18006eea8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006eb9b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006ec47`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006eb9b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18006ec47`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ec15`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ec8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ed85`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006eddd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006edff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ee2c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ec15`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ec8e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ed85`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006eddd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006edff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18006ee2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006edcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006edcc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ed93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006edeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006ed93`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006edeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ebfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ec77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ee14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ebfe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ec77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ee14`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 Container::Manager::Core::Details::ServicingOrchestrator::Initialize(
        char *pv,
        const struct Path *a2,
        __int64 a3,
        ...)
{
  int v4; // eax
  int LastError; // ebx
  int GuidSetValue; // eax
  int v7; // eax
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v9; // r9
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  int v11; // r14d
  unsigned int v12; // r8d
  const char *v13; // r9
  const char *v14; // r9
  struct _TP_WORK *v15; // r15
  int v16; // edi
  unsigned int v17; // r8d
  const char *v18; // r9
  Container::Manager::Core::Details::ResourceBroker *v20; // rcx
  utl::_RefCountBase *v21; // rax
  utl::_RefCountBase *v22; // rcx
  Container::Manager::Core::Details::PolicyManager *v23; // rcx
  utl::_RefCountBase *v24; // rax
  utl::_RefCountBase *v25; // rcx
  struct _TP_WORK **v26; // r14
  struct _TP_WORK *v27; // r12
  DWORD v28; // edi
  char *v29; // rsi
  struct _TP_WORK *v30; // r14
  DWORD v31; // edi
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+28h] [rbp-E0h]
  __int64 v35; // [rsp+38h] [rbp-D0h] BYREF
  __int64 *v36; // [rsp+40h] [rbp-C8h]
  __int64 *v37; // [rsp+48h] [rbp-C0h]
  __int64 v38; // [rsp+50h] [rbp-B8h]
  _QWORD v39[4]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v40[4]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v41[2]; // [rsp+98h] [rbp-70h] BYREF
  _WORD v42[8]; // [rsp+A8h] [rbp-60h] BYREF
  _WORD *v43; // [rsp+B8h] [rbp-50h]
  _WORD *v44; // [rsp+C0h] [rbp-48h]
  _WORD v45[8]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v46; // [rsp+D8h] [rbp-30h]
  __int128 v47; // [rsp+E8h] [rbp-20h]
  __int128 v48; // [rsp+F8h] [rbp-10h]
  __int128 v49; // [rsp+108h] [rbp+0h]
  char v50; // [rsp+118h] [rbp+10h] BYREF
  char v51; // [rsp+120h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]
  HANDLE hObject; // [rsp+170h] [rbp+68h] BYREF
  va_list hObjecta; // [rsp+170h] [rbp+68h]
  va_list va1; // [rsp+178h] [rbp+70h] BYREF

  va_start(va1, a3);
  va_start(hObjecta, a3);
  hObject = va_arg(va1, HANDLE);
  v41[0] = v42;
  v41[1] = v42;
  v42[0] = 0;
  v43 = v45;
  v44 = v45;
  v45[0] = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v4 = Container::Manager::Core::Details::ServicingStore::Initialize(
         (Container::Manager::Core::Details::ServicingStore *)v41,
         a2);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x897,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)(unsigned int)v4,
      v34);
LABEL_25:
    Container::Manager::Core::Details::ServicingStore::~ServicingStore((Container::Manager::Core::Details::ServicingStore *)v41);
    return (unsigned int)LastError;
  }
  v39[0] = v39;
  v39[1] = v39;
  v39[2] = v39;
  v39[3] = 0;
  v35 = (__int64)&v35;
  v36 = &v35;
  v37 = &v35;
  v38 = 0;
  GuidSetValue = Container::Manager::Core::Details::ServicingStore::GetGuidSetValue(v41, L"RegisteredLayers", &v35);
  LastError = GuidSetValue;
  if ( GuidSetValue >= 0 )
  {
    utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>::operator=(v39, &v35);
    LastError = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)(unsigned int)GuidSetValue,
      v34);
  }
  utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(&v35);
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89D,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)(unsigned int)LastError,
      v34);
LABEL_8:
    utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v39);
    goto LABEL_25;
  }
  v40[0] = v40;
  v40[1] = v40;
  v40[2] = v40;
  v40[3] = 0;
  v35 = (__int64)&v35;
  v36 = &v35;
  v37 = &v35;
  v38 = 0;
  v7 = Container::Manager::Core::Details::ServicingStore::GetGuidSetValue(v41, L"RegisteredStorages", &v35);
  LastError = v7;
  if ( v7 >= 0 )
  {
    utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>::operator=(v40, &v35);
    LastError = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x700,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)(unsigned int)v7,
      v34);
  }
  utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(&v35);
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8A3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)(unsigned int)LastError,
      v34);
LABEL_14:
    utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v40);
    goto LABEL_8;
  }
  ThreadpoolWork = CreateThreadpoolWork(
                     Container::Manager::Core::Details::ServicingOrchestrator::WaitForUpdatesToCompleteWork,
                     pv,
                     0);
  if ( !ThreadpoolWork )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x8AB,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
                  v9);
    goto LABEL_14;
  }
  hObject = 0;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((HANDLE *)hObjecta, 0);
  v11 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8AF,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
      (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      v34);
    if ( hObject )
    {
      if ( !CloseHandle(hObject) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
    }
    CloseThreadpoolWork(ThreadpoolWork);
    utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v40);
    utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v39);
    LastError = v11;
    goto LABEL_25;
  }
  v15 = CreateThreadpoolWork(Container::Manager::Core::Details::ServicingOrchestrator::CleanupWorkThread, pv, 0);
  if ( !v15 )
  {
    v16 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x8B7,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\servicing.cpp",
            v14);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
    CloseThreadpoolWork(ThreadpoolWork);
    utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v40);
    utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v39);
    LastError = v16;
    goto LABEL_25;
  }
  v20 = Container::Manager::Core::g_resourceBroker;
  v21 = qword_18021F518;
  if ( qword_18021F518 )
    _InterlockedIncrement((volatile signed __int32 *)qword_18021F518 + 2);
  *((_QWORD *)pv + 16) = v20;
  v22 = (utl::_RefCountBase *)*((_QWORD *)pv + 17);
  *((_QWORD *)pv + 17) = v21;
  if ( v22 )
    utl::_RefCountBase::_DecStrong(v22);
  v23 = Container::Manager::Core::g_policyManager;
  v24 = qword_18021F478;
  if ( qword_18021F478 )
    _InterlockedIncrement((volatile signed __int32 *)qword_18021F478 + 2);
  *((_QWORD *)pv + 18) = v23;
  v25 = (utl::_RefCountBase *)*((_QWORD *)pv + 19);
  *((_QWORD *)pv + 19) = v24;
  if ( v25 )
    utl::_RefCountBase::_DecStrong(v25);
  Container::Manager::Core::Details::ServicingStore::operator=(pv, v41);
  utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>::operator=(pv + 176, v39);
  utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>::operator=(pv + 208, v40);
  v26 = (struct _TP_WORK **)(pv + 288);
  if ( pv + 288 != &v50 )
  {
    v27 = *v26;
    if ( *v26 )
    {
      v28 = GetLastError();
      CloseThreadpoolWork(v27);
      SetLastError(v28);
    }
    *v26 = ThreadpoolWork;
    ThreadpoolWork = 0;
  }
  __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
    pv + 296,
    (HANDLE *)hObjecta);
  v29 = pv + 304;
  if ( v29 == &v51 )
  {
    CloseThreadpoolWork(v15);
  }
  else
  {
    v30 = *(struct _TP_WORK **)v29;
    if ( *(_QWORD *)v29 )
    {
      v31 = GetLastError();
      CloseThreadpoolWork(v30);
      SetLastError(v31);
    }
    *(_QWORD *)v29 = v15;
  }
  if ( hObject && !CloseHandle(hObject) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
  utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v40);
  utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v39);
  Container::Manager::Core::Details::ServicingStore::~ServicingStore((Container::Manager::Core::Details::ServicingStore *)v41);
  return 0;
}

```

## disassembly

```asm
0x18006e984  mov     rax, rsp
0x18006e987  mov     [rax+8], rbx
0x18006e98b  mov     [rax+10h], rsi
0x18006e98f  mov     [rax+20h], r9
0x18006e993  push    rbp
0x18006e994  push    rdi
0x18006e995  push    r12
0x18006e997  push    r14
0x18006e999  push    r15
0x18006e99b  lea     rbp, [rax-48h]
0x18006e99f  sub     rsp, 120h
0x18006e9a6  mov     rsi, rcx
0x18006e9a9  lea     rax, [rbp+40h+var_A0]
0x18006e9ad  mov     [rbp+40h+var_B0], rax
0x18006e9b1  lea     rax, [rbp+40h+var_A0]
0x18006e9b5  mov     [rbp+40h+var_A8], rax
0x18006e9b9  xor     eax, eax
0x18006e9bb  mov     [rbp+40h+var_A0], ax
0x18006e9bf  lea     rax, [rbp+40h+var_80]
0x18006e9c3  mov     [rbp+40h+var_90], rax
0x18006e9c7  lea     rax, [rbp+40h+var_80]
0x18006e9cb  mov     [rbp+40h+var_88], rax
0x18006e9cf  xor     eax, eax
0x18006e9d1  mov     [rbp+40h+var_80], ax
0x18006e9d5  xorps   xmm0, xmm0
0x18006e9d8  movdqa  [rbp+40h+var_70], xmm0
0x18006e9dd  xorps   xmm1, xmm1
0x18006e9e0  movdqa  [rbp+40h+var_60], xmm1
0x18006e9e5  movdqa  [rbp+40h+var_50], xmm0
0x18006e9ea  movdqa  [rbp+40h+var_40], xmm1
0x18006e9ef  lea     rcx, [rbp+40h+var_B0]; this
0x18006e9f3  call    ?Initialize@ServicingStore@Details@Core@Manager@Container@@QEAAJAEBVPath@Csl@@@Z; Container::Manager::Core::Details::ServicingStore::Initialize(Csl::Path const &)
0x18006e9f8  mov     ebx, eax
0x18006e9fa  test    eax, eax
0x18006e9fc  jns     short loc_18006EA1B
0x18006e9fe  mov     rcx, [rbp+48h]; this
0x18006ea02  mov     r9d, eax; char *
0x18006ea05  lea     r8, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006ea0c  mov     edx, 897h; void *
0x18006ea11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ea16  jmp     loc_18006ECB0
0x18006ea1b  lea     rax, [rsp+140h+var_F0]
0x18006ea20  mov     [rsp+140h+var_F0], rax
0x18006ea25  lea     rax, [rsp+140h+var_F0]
0x18006ea2a  mov     [rsp+140h+var_E8], rax
0x18006ea2f  mov     [rsp+140h+var_E0], rax
0x18006ea34  mov     [rsp+140h+var_D8], 0
0x18006ea3d  lea     rax, [rsp+140h+var_110]
0x18006ea42  mov     [rsp+140h+var_110], rax
0x18006ea47  lea     rax, [rsp+140h+var_110]
0x18006ea4c  mov     [rsp+140h+var_108], rax
0x18006ea51  mov     [rsp+140h+var_100], rax
0x18006ea56  mov     [rsp+140h+var_F8], 0
0x18006ea5f  lea     r8, [rsp+140h+var_110]
0x18006ea64  lea     rdx, aRegisteredlaye; "RegisteredLayers"
0x18006ea6b  lea     rcx, [rbp+40h+var_B0]
0x18006ea6f  call    ?GetGuidSetValue@ServicingStore@Details@Core@Manager@Container@@AEBAJPEBGAEAV?$set@U_GUID@@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@@utl@@@Z; Container::Manager::Core::Details::ServicingStore::GetGuidSetValue(ushort const *,utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>> &)
0x18006ea74  mov     ebx, eax
0x18006ea76  lea     rdi, aOnecoreBaseGen_65; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18006ea7d  test    eax, eax
0x18006ea7f  jns     short loc_18006EA97
0x18006ea81  mov     rcx, [rbp+48h]; this
0x18006ea85  mov     r9d, eax; char *
0x18006ea88  mov     r8, rdi; unsigned int
0x18006ea8b  mov     edx, 6DFh; void *
0x18006ea90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ea95  jmp     short loc_18006EAA8
0x18006ea97  lea     rdx, [rsp+140h+var_110]
0x18006ea9c  lea     rcx, [rsp+140h+var_F0]
0x18006eaa1  call    ??4?$set@U_GUID@@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>::operator=(utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>> &&)
0x18006eaa6  xor     ebx, ebx
0x18006eaa8  lea     rcx, [rsp+140h+var_110]
0x18006eaad  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006eab2  test    ebx, ebx
0x18006eab4  jns     short loc_18006EAD9
0x18006eab6  mov     rcx, [rbp+48h]; this
0x18006eaba  mov     r9d, ebx; char *
0x18006eabd  mov     r8, rdi; unsigned int
0x18006eac0  mov     edx, 89Dh; void *
0x18006eac5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006eaca  lea     rcx, [rsp+140h+var_F0]
0x18006eacf  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006ead4  jmp     loc_18006ECB0
0x18006ead9  lea     rax, [rsp+140h+var_D0]
0x18006eade  mov     [rsp+140h+var_D0], rax
0x18006eae3  lea     rax, [rsp+140h+var_D0]
0x18006eae8  mov     [rsp+140h+var_C8], rax
0x18006eaed  mov     [rbp+40h+var_C0], rax
0x18006eaf1  mov     [rbp+40h+var_B8], 0
0x18006eaf9  lea     rax, [rsp+140h+var_110]
0x18006eafe  mov     [rsp+140h+var_110], rax
0x18006eb03  lea     rax, [rsp+140h+var_110]
0x18006eb08  mov     [rsp+140h+var_108], rax
0x18006eb0d  mov     [rsp+140h+var_100], rax
0x18006eb12  mov     [rsp+140h+var_F8], 0
0x18006eb1b  lea     r8, [rsp+140h+var_110]
0x18006eb20  lea     rdx, aRegisteredstor; "RegisteredStorages"
0x18006eb27  lea     rcx, [rbp+40h+var_B0]
0x18006eb2b  call    ?GetGuidSetValue@ServicingStore@Details@Core@Manager@Container@@AEBAJPEBGAEAV?$set@U_GUID@@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@@utl@@@Z; Container::Manager::Core::Details::ServicingStore::GetGuidSetValue(ushort const *,utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>> &)
0x18006eb30  mov     ebx, eax
0x18006eb32  test    eax, eax
0x18006eb34  jns     short loc_18006EB4C
0x18006eb36  mov     rcx, [rbp+48h]; this
0x18006eb3a  mov     r9d, eax; char *
0x18006eb3d  mov     r8, rdi; unsigned int
0x18006eb40  mov     edx, 700h; void *
0x18006eb45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006eb4a  jmp     short loc_18006EB5D
0x18006eb4c  lea     rdx, [rsp+140h+var_110]
0x18006eb51  lea     rcx, [rsp+140h+var_D0]
0x18006eb56  call    ??4?$set@U_GUID@@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>::operator=(utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>> &&)
0x18006eb5b  xor     ebx, ebx
0x18006eb5d  lea     rcx, [rsp+140h+var_110]
0x18006eb62  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006eb67  test    ebx, ebx
0x18006eb69  jns     short loc_18006EB8E
0x18006eb6b  mov     rcx, [rbp+48h]; this
0x18006eb6f  mov     r9d, ebx; char *
0x18006eb72  mov     r8, rdi; unsigned int
0x18006eb75  mov     edx, 8A3h; void *
0x18006eb7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006eb7f  lea     rcx, [rsp+140h+var_D0]
0x18006eb84  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006eb89  jmp     loc_18006EACA
0x18006eb8e  xor     r8d, r8d; pcbe
0x18006eb91  mov     rdx, rsi; pv
0x18006eb94  lea     rcx, ?WaitForUpdatesToCompleteWork@ServicingOrchestrator@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006eb9b  call    cs:__imp_CreateThreadpoolWork
0x18006eba2  nop     dword ptr [rax+rax+00h]
0x18006eba7  mov     rbx, rax
0x18006ebaa  test    rax, rax
0x18006ebad  jnz     short loc_18006EBC4
0x18006ebaf  mov     rcx, [rbp+48h]; this
0x18006ebb3  mov     r8, rdi; unsigned int
0x18006ebb6  mov     edx, 8ABh; void *
0x18006ebbb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006ebc0  mov     ebx, eax
0x18006ebc2  jmp     short loc_18006EB7F
0x18006ebc4  mov     [rbp+40h+hObject], 0
0x18006ebcc  xor     r9d, r9d
0x18006ebcf  xor     edx, edx
0x18006ebd1  lea     rcx, [rbp+40h+hObject]
0x18006ebd5  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18006ebda  mov     r14d, eax
0x18006ebdd  test    eax, eax
0x18006ebdf  jns     short loc_18006EC3A
0x18006ebe1  mov     rcx, [rbp+48h]; this
0x18006ebe5  mov     r9d, eax; char *
0x18006ebe8  mov     r8, rdi; unsigned int
0x18006ebeb  mov     edx, 8AFh; void *
0x18006ebf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ebf5  mov     rcx, [rbp+40h+hObject]; hObject
0x18006ebf9  test    rcx, rcx
0x18006ebfc  jz      short loc_18006EC12
0x18006ebfe  call    cs:__imp_CloseHandle
0x18006ec05  nop     dword ptr [rax+rax+00h]
0x18006ec0a  test    eax, eax
0x18006ec0c  jz      loc_18006EE83
0x18006ec12  mov     rcx, rbx; pwk
0x18006ec15  call    cs:__imp_CloseThreadpoolWork
0x18006ec1c  nop     dword ptr [rax+rax+00h]
0x18006ec21  lea     rcx, [rsp+140h+var_D0]
0x18006ec26  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006ec2b  lea     rcx, [rsp+140h+var_F0]
0x18006ec30  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006ec35  mov     ebx, r14d
0x18006ec38  jmp     short loc_18006ECB0
0x18006ec3a  xor     r8d, r8d; pcbe
0x18006ec3d  mov     rdx, rsi; pv
0x18006ec40  lea     rcx, ?CleanupWorkThread@ServicingOrchestrator@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18006ec47  call    cs:__imp_CreateThreadpoolWork
0x18006ec4e  nop     dword ptr [rax+rax+00h]
0x18006ec53  mov     r15, rax
0x18006ec56  test    rax, rax
0x18006ec59  jnz     short loc_18006ECC0
0x18006ec5b  mov     rcx, [rbp+48h]; this
0x18006ec5f  mov     r8, rdi; unsigned int
0x18006ec62  mov     edx, 8B7h; void *
0x18006ec67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18006ec6c  mov     edi, eax
0x18006ec6e  mov     rcx, [rbp+40h+hObject]; hObject
0x18006ec72  test    rcx, rcx
0x18006ec75  jz      short loc_18006EC8B
0x18006ec77  call    cs:__imp_CloseHandle
0x18006ec7e  nop     dword ptr [rax+rax+00h]
0x18006ec83  test    eax, eax
0x18006ec85  jz      loc_18006EE92
0x18006ec8b  mov     rcx, rbx; pwk
0x18006ec8e  call    cs:__imp_CloseThreadpoolWork
0x18006ec95  nop     dword ptr [rax+rax+00h]
0x18006ec9a  lea     rcx, [rsp+140h+var_D0]
0x18006ec9f  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006eca4  lea     rcx, [rsp+140h+var_F0]
0x18006eca9  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006ecae  mov     ebx, edi
0x18006ecb0  lea     rcx, [rbp+40h+var_B0]; this
0x18006ecb4  call    ??1ServicingStore@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ServicingStore::~ServicingStore(void)
0x18006ecb9  mov     eax, ebx
0x18006ecbb  jmp     loc_18006EE57
0x18006ecc0  mov     rcx, cs:?g_resourceBroker@Core@Manager@Container@@3V?$shared_ptr@VResourceBroker@Details@Core@Manager@Container@@@utl@@A; utl::shared_ptr<Container::Manager::Core::Details::ResourceBroker> Container::Manager::Core::g_resourceBroker
0x18006ecc7  mov     rax, cs:qword_18021F518
0x18006ecce  test    rax, rax
0x18006ecd1  jz      short loc_18006ECD7
0x18006ecd3  lock inc dword ptr [rax+8]
0x18006ecd7  mov     [rsi+80h], rcx
0x18006ecde  mov     rcx, [rsi+88h]; this
0x18006ece5  mov     [rsi+88h], rax
0x18006ecec  test    rcx, rcx
0x18006ecef  jz      short loc_18006ECF7
0x18006ecf1  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18006ecf6  nop
0x18006ecf7  mov     rcx, cs:?g_policyManager@Core@Manager@Container@@3V?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@A; utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> Container::Manager::Core::g_policyManager
0x18006ecfe  mov     rax, cs:qword_18021F478
0x18006ed05  test    rax, rax
0x18006ed08  jz      short loc_18006ED0E
0x18006ed0a  lock inc dword ptr [rax+8]
0x18006ed0e  mov     [rsi+90h], rcx
0x18006ed15  mov     rcx, [rsi+98h]; this
0x18006ed1c  mov     [rsi+98h], rax
0x18006ed23  test    rcx, rcx
0x18006ed26  jz      short loc_18006ED2E
0x18006ed28  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18006ed2d  nop
0x18006ed2e  lea     rdx, [rbp+40h+var_B0]
0x18006ed32  mov     rcx, rsi
0x18006ed35  call    ??4ServicingStore@Details@Core@Manager@Container@@QEAAAEAV01234@$$QEAV01234@@Z; Container::Manager::Core::Details::ServicingStore::operator=(Container::Manager::Core::Details::ServicingStore &&)
0x18006ed3a  lea     rcx, [rsi+0B0h]
0x18006ed41  lea     rdx, [rsp+140h+var_F0]
0x18006ed46  call    ??4?$set@U_GUID@@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>::operator=(utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>> &&)
0x18006ed4b  lea     rcx, [rsi+0D0h]
0x18006ed52  lea     rdx, [rsp+140h+var_D0]
0x18006ed57  call    ??4?$set@U_GUID@@U?$less@U_GUID@@@utl@@V?$allocator@U_GUID@@@3@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>>::operator=(utl::set<_GUID,utl::less<_GUID>,utl::allocator<_GUID>> &&)
0x18006ed5c  lea     r14, [rsi+120h]
0x18006ed63  lea     rax, [rbp+40h+var_30]
0x18006ed67  cmp     r14, rax
0x18006ed6a  jz      short loc_18006EDA4
0x18006ed6c  mov     r12, [r14]
0x18006ed6f  test    r12, r12
0x18006ed72  jz      short loc_18006ED9F
0x18006ed74  call    cs:__imp_GetLastError
0x18006ed7b  nop     dword ptr [rax+rax+00h]
0x18006ed80  mov     edi, eax
0x18006ed82  mov     rcx, r12; pwk
0x18006ed85  call    cs:__imp_CloseThreadpoolWork
0x18006ed8c  nop     dword ptr [rax+rax+00h]
0x18006ed91  mov     ecx, edi; dwErrCode
0x18006ed93  call    cs:__imp_SetLastError
0x18006ed9a  nop     dword ptr [rax+rax+00h]
0x18006ed9f  mov     [r14], rbx
0x18006eda2  xor     ebx, ebx
0x18006eda4  lea     rcx, [rsi+128h]
0x18006edab  lea     rdx, [rbp+40h+hObject]
0x18006edaf  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18006edb4  add     rsi, 130h
0x18006edbb  lea     rax, [rbp+40h+var_28]
0x18006edbf  cmp     rsi, rax
0x18006edc2  jz      short loc_18006EDFC
0x18006edc4  mov     r14, [rsi]
0x18006edc7  test    r14, r14
0x18006edca  jz      short loc_18006EDF7
0x18006edcc  call    cs:__imp_GetLastError
0x18006edd3  nop     dword ptr [rax+rax+00h]
0x18006edd8  mov     edi, eax
0x18006edda  mov     rcx, r14; pwk
0x18006eddd  call    cs:__imp_CloseThreadpoolWork
0x18006ede4  nop     dword ptr [rax+rax+00h]
0x18006ede9  mov     ecx, edi; dwErrCode
0x18006edeb  call    cs:__imp_SetLastError
0x18006edf2  nop     dword ptr [rax+rax+00h]
0x18006edf7  mov     [rsi], r15
0x18006edfa  jmp     short loc_18006EE0B
0x18006edfc  mov     rcx, r15; pwk
0x18006edff  call    cs:__imp_CloseThreadpoolWork
0x18006ee06  nop     dword ptr [rax+rax+00h]
0x18006ee0b  mov     rcx, [rbp+40h+hObject]; hObject
0x18006ee0f  test    rcx, rcx
0x18006ee12  jz      short loc_18006EE24
0x18006ee14  call    cs:__imp_CloseHandle
0x18006ee1b  nop     dword ptr [rax+rax+00h]
0x18006ee20  test    eax, eax
0x18006ee22  jz      short loc_18006EE74
0x18006ee24  test    rbx, rbx
0x18006ee27  jz      short loc_18006EE38
0x18006ee29  mov     rcx, rbx; pwk
0x18006ee2c  call    cs:__imp_CloseThreadpoolWork
0x18006ee33  nop     dword ptr [rax+rax+00h]
0x18006ee38  lea     rcx, [rsp+140h+var_D0]
0x18006ee3d  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006ee42  lea     rcx, [rsp+140h+var_F0]
0x18006ee47  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18006ee4c  lea     rcx, [rbp+40h+var_B0]; this
0x18006ee50  call    ??1ServicingStore@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ServicingStore::~ServicingStore(void)
0x18006ee55  xor     eax, eax
0x18006ee57  lea     r11, [rsp+140h+var_20]
0x18006ee5f  mov     rbx, [r11+30h]
0x18006ee63  mov     rsi, [r11+38h]
0x18006ee67  mov     rsp, r11
0x18006ee6a  pop     r15
0x18006ee6c  pop     r14
0x18006ee6e  pop     r12
  ... truncated ...
```
