# AddPackageInstallNode::LaunchAddPackage(void)

- ea: `0x180023680`
- end: `0x180024300`
- name: `?LaunchAddPackage@AddPackageInstallNode@@AEAAJXZ`
- size: `3200`
- prototype: `__int64 __fastcall(AddPackageInstallNode *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180024310`

## callees

- `0x180001a70`
- `0x1800030e8`
- `0x18000526c`
- `0x180006974`
- `0x1800083e8`
- `0x180023238`
- `0x180023680`
- `0x180024508`
- `0x1800245fc`
- `0x180032c84`
- `0x180032f08`
- `0x180035846`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002376e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023882`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023ab5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002376e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023882`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023ab5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023927`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180023e81`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180023e81`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002390f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18002390f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023ad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023864`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023ad6`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800236bd`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800236bd`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023721`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023835`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800238e6`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023a64`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023c3c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023d35`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023e58`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023f8d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180024083`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800241a3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180024284`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023721`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023835`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800238e6`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023a64`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023c3c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023d35`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023e58`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180023f8d`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180024083`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800241a3`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180024284`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180023792`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180023792`

## string_xrefs

- `0x1800242d3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800242ed`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800236dd`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x18002370f`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x180023807`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x1800238b8`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x1800239c2`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x180023b80`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x180023c78`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x180023d9b`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x180023ed0`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x180023fc6`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`
- `0x1800241c7`: `onecoreuap\admin\prov\provcsp\addpackageinstallnode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall AddPackageInstallNode::LaunchAddPackage(AddPackageInstallNode *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 result; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  HANDLE Event; // rbx
  const char *v13; // r9
  void *v14; // rax
  volatile signed __int32 *v15; // rdi
  void **v16; // r12
  __int64 v17; // r14
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  __int64 v21; // rcx
  const char *v22; // r9
  const WCHAR *v23; // r15
  unsigned __int64 v24; // rbx
  int CurrentTurn; // r15d
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64, HSTRING, __int128 *, __int64); // r13
  _QWORD *v28; // rcx
  int v29; // eax
  _QWORD *v30; // rcx
  _QWORD *v31; // rcx
  int v32; // eax
  _QWORD *v33; // rcx
  _QWORD *v34; // rcx
  _QWORD *v35; // rbx
  __int64 (__fastcall *v36)(_QWORD *, GUID *, _QWORD **); // r15
  _QWORD *v37; // rcx
  int v38; // eax
  _QWORD *v39; // rcx
  _QWORD *v40; // rcx
  void *v41; // rcx
  DWORD v42; // eax
  const char *v43; // r9
  int v44; // eax
  _QWORD *v45; // rcx
  _QWORD *v46; // rcx
  int v47; // eax
  _QWORD *v48; // rcx
  _QWORD *v49; // rcx
  __int64 v50; // rdx
  _QWORD *v51; // rcx
  _QWORD *v52; // rcx
  __int64 v53; // rcx
  _QWORD *v54; // rcx
  _QWORD *v55; // rcx
  __int64 v56; // rcx
  int v57; // [rsp+20h] [rbp-168h]
  int v58; // [rsp+20h] [rbp-168h]
  __int64 v59; // [rsp+40h] [rbp-148h] BYREF
  _QWORD *v60; // [rsp+48h] [rbp-140h]
  _QWORD *v61; // [rsp+50h] [rbp-138h] BYREF
  int v62; // [rsp+58h] [rbp-130h] BYREF
  _QWORD v63[2]; // [rsp+60h] [rbp-128h] BYREF
  char v64; // [rsp+71h] [rbp-117h]
  __int128 v65; // [rsp+78h] [rbp-110h] BYREF
  _BYTE v66[24]; // [rsp+88h] [rbp-100h] BYREF
  __int128 v67; // [rsp+A0h] [rbp-E8h] BYREF
  HSTRING string; // [rsp+B0h] [rbp-D8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-D0h] BYREF
  HSTRING v70; // [rsp+D0h] [rbp-B8h] BYREF
  HSTRING_HEADER v71; // [rsp+D8h] [rbp-B0h] BYREF
  HSTRING v72; // [rsp+F0h] [rbp-98h] BYREF
  HSTRING_HEADER v73; // [rsp+F8h] [rbp-90h] BYREF
  char v74[32]; // [rsp+110h] [rbp-78h] BYREF
  _QWORD *v75; // [rsp+130h] [rbp-58h]
  __int64 v76; // [rsp+138h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v2 = RoInitialize(1);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
      (const char *)(unsigned int)v2,
      v57);
    return v3;
  }
  v64 = 1;
  if ( !*((_QWORD *)this + 4) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
      (const char *)0x86000011LL,
      v57);
    RoUninitialize(v6, v5);
    return 2248146961LL;
  }
  if ( WindowsCreateStringReference(L"Windows.Management.Provisioning.PackageManager", 0x2Eu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v59 = 0;
  v63[0] = 0;
  v7 = RoActivateInstance(string, v63);
  try
  {
    v8 = v7;
    if ( v7 >= 0 )
    {
      if ( !memcmp_0(&GUID_f6efa550_3514_4bed_800b_a2f68e0972b3, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
      {
        v59 = v63[0];
      }
      else
      {
        v8 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v63[0])(
               v63[0],
               &GUID_f6efa550_3514_4bed_800b_a2f68e0972b3,
               &v59);
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v63[0] + 16LL))(v63[0]);
      }
    }
    if ( v8 >= 0 )
    {
      if ( WindowsCreateStringReference(L"ProvisioningCSP", 0xFu, &v71, &v70) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v11 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v59 + 88LL))(v59, v70);
      v8 = v11;
      if ( v11 >= 0 )
      {
        v65 = 0;
        Event = CreateEventExW(0, 0, 0, 0x1F0003u);
        if ( !Event )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x1CC8,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            v13);
        GetLastError();
        _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
          &v65,
          Event);
        v60 = 0;
        v61 = 0;
        v14 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
        if ( v14 )
        {
          v15 = (volatile signed __int32 *)*((_QWORD *)&v65 + 1);
          v16 = (void **)v65;
          if ( *((_QWORD *)&v65 + 1) )
            _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v65 + 1) + 8LL), 1u);
          v63[1] = v15;
          v63[0] = v16;
          v17 = EventCompletedHandler<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>::EventCompletedHandler<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>(
                  v14,
                  v63);
        }
        else
        {
          v17 = 0;
          v15 = (volatile signed __int32 *)*((_QWORD *)&v65 + 1);
          v16 = (void **)v65;
        }
        v63[0] = v17;
        if ( !v17 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x72,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
            (const char *)0x8007000ELL,
            v57);
          v19 = v61;
          if ( v61 )
          {
            v61 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
          }
          v20 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
          }
          if ( v15 )
          {
            if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
              if ( !_InterlockedDecrement(v15 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
            }
          }
          v21 = v59;
          if ( v59 )
          {
            v59 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
          RoUninitialize(v21, v18);
          return 2147942414LL;
        }
        v23 = (const WCHAR *)(*((_QWORD *)this + 4) + 24LL);
        if ( *(_QWORD *)(*((_QWORD *)this + 4) + 48LL) >= 8u )
          v23 = *(const WCHAR **)v23;
        v24 = -1;
        do
          ++v24;
        while ( v23[v24] );
        if ( v24 > 0xFFFFFFFF )
        {
          LODWORD(v24) = -1;
          RaiseException(0xC000000D, 1u, 0, 0);
        }
        WindowsCreateStringReference(v23, v24, &v73, &v72);
        ProvAgent::ProvAgent((ProvAgent *)v66);
        CurrentTurn = ProvAgent::GetCurrentTurn(v66);
        v26 = v59;
        v27 = *(__int64 (__fastcall **)(__int64, HSTRING, __int128 *, __int64))(*(_QWORD *)v59 + 48LL);
        v28 = v60;
        if ( v60 )
        {
          v60 = 0;
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v28 + 16LL))(v28, *v28);
        }
        v67 = 0;
        v58 = CurrentTurn;
        v29 = v27(v26, v72, &v67, 1);
        v8 = v29;
        if ( v29 >= 0 )
        {
          v32 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v60 + 48LL))(v60, v17);
          v8 = v32;
          if ( v32 >= 0 )
          {
            v35 = v60;
            v36 = *(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD **))*v60;
            v37 = v61;
            if ( v61 )
            {
              v61 = 0;
              (*(void (__fastcall **)(_QWORD *, _QWORD))(*v37 + 16LL))(v37, *v37);
            }
            v38 = v36(v35, &GUID_00000036_0000_0000_c000_000000000046, &v61);
            v8 = v38;
            if ( v38 >= 0 )
            {
              if ( v16 )
                v41 = *v16;
              else
                v41 = 0;
              v42 = WaitForSingleObjectEx(v41, 0xFFFFFFFF, 0);
              if ( v42 == 258 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x84,
                  (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
                  (const char *)0x800705B4LL,
                  v58);
                ProvAgent::~ProvAgent((ProvAgent *)v66);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                v54 = v61;
                if ( v61 )
                {
                  v61 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v54 + 16LL))(v54);
                }
                v55 = v60;
                if ( v60 )
                {
                  v60 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v55 + 16LL))(v55);
                }
                if ( v15 )
                {
                  if ( !_InterlockedDecrement(v15 + 2) )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
                    if ( !_InterlockedDecrement(v15 + 3) )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
                  }
                }
                v56 = v59;
                if ( v59 )
                {
                  v59 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
                }
                ((void (*)(void))RoUninitialize)();
                return 2147943860LL;
              }
              if ( v42 )
                wil::details::in1diag3::FailFast_Unexpected(
                  retaddr,
                  (void *)0xB0F,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                  v43);
              v62 = 0;
              v44 = (*(__int64 (__fastcall **)(_QWORD *, int *))(*v60 + 64LL))(v60, &v62);
              v8 = v44;
              if ( v44 >= 0 )
              {
                v47 = (*(__int64 (__fastcall **)(_QWORD *))(*v61 + 80LL))(v61);
                v8 = v47;
                if ( v47 >= 0 )
                {
                  if ( v62 && (unsigned int)dword_1800495B0 > 2 )
                  {
                    LODWORD(v63[0]) = v62;
                    v75 = v63;
                    v76 = 4;
                    tlgWriteTransfer_EventWriteTransfer(&dword_1800495B0, byte_1800416B3, 0, 0, 3, v74);
                  }
                  ProvAgent::~ProvAgent((ProvAgent *)v66);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                  v51 = v61;
                  if ( v61 )
                  {
                    v61 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v51 + 16LL))(v51);
                  }
                  v52 = v60;
                  if ( v60 )
                  {
                    v60 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v52 + 16LL))(v52);
                  }
                  if ( v15 )
                  {
                    if ( !_InterlockedDecrement(v15 + 2) )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
                      if ( !_InterlockedDecrement(v15 + 3) )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
                    }
                  }
                  v53 = v59;
                  if ( v59 )
                  {
                    v59 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
                  }
                  RoUninitialize(v53, v50);
                  return 0;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x89,
                  (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
                  (const char *)(unsigned int)v47,
                  v58);
                ProvAgent::~ProvAgent((ProvAgent *)v66);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                v48 = v61;
                if ( v61 )
                {
                  v61 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
                }
                v49 = v60;
                if ( v60 )
                {
                  v60 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
                }
                if ( v15 )
                {
                  if ( !_InterlockedDecrement(v15 + 2) )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
                    if ( !_InterlockedDecrement(v15 + 3) )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
                  }
                }
                v10 = v59;
                if ( v59 )
                {
                  v59 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x88,
                  (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
                  (const char *)(unsigned int)v44,
                  v58);
                ProvAgent::~ProvAgent((ProvAgent *)v66);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
                v45 = v61;
                if ( v61 )
                {
                  v61 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v45 + 16LL))(v45);
                }
                v46 = v60;
                if ( v60 )
                {
                  v60 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
                }
                if ( v15 )
                {
                  if ( !_InterlockedDecrement(v15 + 2) )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
                    if ( !_InterlockedDecrement(v15 + 3) )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
                  }
                }
                v10 = v59;
                if ( v59 )
                {
                  v59 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
                }
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x80,
                (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
                (const char *)(unsigned int)v38,
                v58);
              ProvAgent::~ProvAgent((ProvAgent *)v66);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              v39 = v61;
              if ( v61 )
              {
                v61 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v39 + 16LL))(v39);
              }
              v40 = v60;
              if ( v60 )
              {
                v60 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
              }
              if ( v15 )
              {
                if ( !_InterlockedDecrement(v15 + 2) )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
                  if ( !_InterlockedDecrement(v15 + 3) )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
                }
              }
              v10 = v59;
              if ( v59 )
              {
                v59 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
              }
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7F,
              (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
              (const char *)(unsigned int)v32,
              CurrentTurn);
            ProvAgent::~ProvAgent((ProvAgent *)v66);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            v33 = v61;
            if ( v61 )
            {
              v61 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v33 + 16LL))(v33);
            }
            v34 = v60;
            if ( v60 )
            {
              v60 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v34 + 16LL))(v34);
            }
            if ( v15 )
            {
              if ( !_InterlockedDecrement(v15 + 2) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
                if ( !_InterlockedDecrement(v15 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
              }
            }
            v10 = v59;
            if ( v59 )
            {
              v59 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7C,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
            (const char *)(unsigned int)v29,
            CurrentTurn);
          ProvAgent::~ProvAgent((ProvAgent *)v66);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          v30 = v61;
          if ( v61 )
          {
            v61 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
          }
          v31 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
          }
          if ( v15 )
          {
            if ( !_InterlockedDecrement(v15 + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
              if ( !_InterlockedDecrement(v15 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
            }
          }
          v10 = v59;
          if ( v59 )
          {
            v59 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x69,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
          (const char *)(unsigned int)v11,
          v57);
        v10 = v59;
        if ( v59 )
        {
          v59 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
        (const char *)(unsigned int)v8,
        v57);
      v10 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    RoUninitialize(v10, v9);
    result = (unsigned int)v8;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x93,
                           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackageinstallnode.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x180023680  mov     rax, rsp
0x180023683  mov     [rax+10h], rbx
0x180023687  mov     [rax+18h], rsi
0x18002368b  push    rdi
0x18002368c  push    r12
0x18002368e  push    r13
0x180023690  push    r14
0x180023692  push    r15
0x180023694  sub     rsp, 160h
0x18002369b  movaps  xmmword ptr [rax-38h], xmm6
0x18002369f  mov     rax, cs:__security_cookie
0x1800236a6  xor     rax, rsp
0x1800236a9  mov     [rsp+188h+var_48], rax
0x1800236b1  mov     rsi, rcx
0x1800236b4  mov     r14d, 1
0x1800236ba  mov     ecx, r14d
0x1800236bd  call    cs:__imp_RoInitialize
0x1800236c4  nop     dword ptr [rax+rax+00h]
0x1800236c9  mov     ebx, eax
0x1800236cb  xor     r13d, r13d
0x1800236ce  test    eax, eax
0x1800236d0  jns     short loc_1800236F4
0x1800236d2  mov     rcx, [rsp+188h]; this
0x1800236da  mov     r9d, eax; char *
0x1800236dd  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\provcsp\\addpa"...
0x1800236e4  lea     edx, [r14+5Bh]; void *
0x1800236e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800236ed  mov     eax, ebx
0x1800236ef  jmp     loc_180024298
0x1800236f4  mov     [rsp+188h+var_117], r14b
0x1800236f9  cmp     [rsi+20h], r13
0x1800236fd  jnz     short loc_180023734
0x1800236ff  mov     rcx, [rsp+188h]; this
0x180023707  mov     ebx, 86000011h
0x18002370c  mov     r9d, ebx; char *
0x18002370f  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\provcsp\\addpa"...
0x180023716  mov     edx, 61h ; 'a'; void *
0x18002371b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023720  nop
0x180023721  call    cs:__imp_RoUninitialize
0x180023728  nop     dword ptr [rax+rax+00h]
0x18002372d  mov     eax, ebx
0x18002372f  jmp     loc_180024298
0x180023734  lea     r9, [rsp+188h+string]; string
0x18002373c  lea     r8, [rsp+188h+hstringHeader]; hstringHeader
0x180023744  mov     edx, 2Eh ; '.'; length
0x180023749  lea     rcx, ?RuntimeClass_Windows_Management_Provisioning_PackageManager@@3QBGB; "Windows.Management.Provisioning.Package"...
0x180023750  call    cs:__imp_WindowsCreateStringReference
0x180023757  nop     dword ptr [rax+rax+00h]
0x18002375c  test    eax, eax
0x18002375e  jns     short loc_18002377B
0x180023760  xor     r9d, r9d; lpArguments
0x180023763  xor     r8d, r8d; nNumberOfArguments
0x180023766  mov     edx, r14d; dwExceptionFlags
0x180023769  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002376e  call    cs:__imp_RaiseException
0x180023775  nop     dword ptr [rax+rax+00h]
0x18002377a  nop
0x18002377b  mov     [rsp+188h+var_148], r13
0x180023780  mov     [rsp+188h+var_128], r13
0x180023785  lea     rdx, [rsp+188h+var_128]
0x18002378a  mov     rcx, [rsp+188h+string]
0x180023792  call    cs:__imp_RoActivateInstance
0x180023799  nop     dword ptr [rax+rax+00h]
0x18002379e  mov     ebx, eax
0x1800237a0  test    eax, eax
0x1800237a2  js      short loc_1800237F8
0x1800237a4  mov     r8d, 10h; Size
0x1800237aa  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800237b1  lea     rcx, _GUID_f6efa550_3514_4bed_800b_a2f68e0972b3; Buf1
0x1800237b8  call    memcmp_0
0x1800237bd  mov     rcx, [rsp+188h+var_128]
0x1800237c2  test    eax, eax
0x1800237c4  jnz     short loc_1800237CD
0x1800237c6  mov     [rsp+188h+var_148], rcx
0x1800237cb  jmp     short loc_1800237F8
0x1800237cd  mov     rax, [rcx]
0x1800237d0  lea     r8, [rsp+188h+var_148]
0x1800237d5  lea     rdx, _GUID_f6efa550_3514_4bed_800b_a2f68e0972b3
0x1800237dc  mov     rax, [rax]
0x1800237df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237e4  mov     ebx, eax
0x1800237e6  mov     rcx, [rsp+188h+var_128]
0x1800237eb  mov     rax, [rcx]
0x1800237ee  mov     rax, [rax+10h]
0x1800237f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237f7  nop
0x1800237f8  test    ebx, ebx
0x1800237fa  jns     short loc_180023848
0x1800237fc  mov     rcx, [rsp+188h]; this
0x180023804  mov     r9d, ebx; char *
0x180023807  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\provcsp\\addpa"...
0x18002380e  mov     edx, 66h ; 'f'; void *
0x180023813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023818  nop
0x180023819  mov     rcx, [rsp+188h+var_148]
0x18002381e  test    rcx, rcx
0x180023821  jz      short loc_180023835
0x180023823  mov     [rsp+188h+var_148], r13
0x180023828  mov     rax, [rcx]
0x18002382b  mov     rax, [rax+10h]
0x18002382f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023834  nop
0x180023835  call    cs:__imp_RoUninitialize
0x18002383c  nop     dword ptr [rax+rax+00h]
0x180023841  mov     eax, ebx
0x180023843  jmp     loc_180024298
0x180023848  lea     r9, [rsp+188h+var_B8]; string
0x180023850  lea     r8, [rsp+188h+var_B0]; hstringHeader
0x180023858  mov     edx, 0Fh; length
0x18002385d  lea     rcx, sourceString; "ProvisioningCSP"
0x180023864  call    cs:__imp_WindowsCreateStringReference
0x18002386b  nop     dword ptr [rax+rax+00h]
0x180023870  test    eax, eax
0x180023872  jns     short loc_18002388E
0x180023874  xor     r9d, r9d; lpArguments
0x180023877  xor     r8d, r8d; nNumberOfArguments
0x18002387a  mov     edx, r14d; dwExceptionFlags
0x18002387d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180023882  call    cs:__imp_RaiseException
0x180023889  nop     dword ptr [rax+rax+00h]
0x18002388e  mov     rcx, [rsp+188h+var_148]
0x180023893  mov     rax, [rcx]
0x180023896  mov     rdx, [rsp+188h+var_B8]
0x18002389e  mov     rax, [rax+58h]
0x1800238a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238a7  mov     ebx, eax
0x1800238a9  test    eax, eax
0x1800238ab  jns     short loc_1800238F9
0x1800238ad  mov     rcx, [rsp+188h]; this
0x1800238b5  mov     r9d, eax; char *
0x1800238b8  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\provcsp\\addpa"...
0x1800238bf  mov     edx, 69h ; 'i'; void *
0x1800238c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800238c9  nop
0x1800238ca  mov     rcx, [rsp+188h+var_148]
0x1800238cf  test    rcx, rcx
0x1800238d2  jz      short loc_1800238E6
0x1800238d4  mov     [rsp+188h+var_148], r13
0x1800238d9  mov     rax, [rcx]
0x1800238dc  mov     rax, [rax+10h]
0x1800238e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238e5  nop
0x1800238e6  call    cs:__imp_RoUninitialize
0x1800238ed  nop     dword ptr [rax+rax+00h]
0x1800238f2  mov     eax, ebx
0x1800238f4  jmp     loc_180024298
0x1800238f9  xorps   xmm0, xmm0
0x1800238fc  movdqu  [rsp+188h+var_110], xmm0
0x180023902  mov     r9d, 1F0003h; dwDesiredAccess
0x180023908  xor     r8d, r8d; dwFlags
0x18002390b  xor     edx, edx; lpName
0x18002390d  xor     ecx, ecx; lpEventAttributes
0x18002390f  call    cs:__imp_CreateEventExW
0x180023916  nop     dword ptr [rax+rax+00h]
0x18002391b  mov     rbx, rax
0x18002391e  test    rax, rax
0x180023921  jz      loc_1800242E5
0x180023927  call    cs:__imp_GetLastError
0x18002392e  nop     dword ptr [rax+rax+00h]
0x180023933  mov     rdx, rbx
0x180023936  lea     rcx, [rsp+188h+var_110]
0x18002393b  call    ?reset@?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAAXPEAX@Z
0x180023940  nop
0x180023941  mov     [rsp+188h+var_140], r13
0x180023946  mov     [rsp+188h+var_138], r13
0x18002394b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023952  mov     ecx, 20h ; ' '; unsigned __int64
0x180023957  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002395c  test    rax, rax
0x18002395f  jz      short loc_180023994
0x180023961  mov     rdi, qword ptr [rsp+188h+var_110+8]
0x180023969  mov     r12, qword ptr [rsp+188h+var_110]
0x18002396e  test    rdi, rdi
0x180023971  jz      short loc_180023978
0x180023973  lock add [rdi+8], r14d
0x180023978  mov     [rsp+188h+var_120], rdi
0x18002397d  mov     [rsp+188h+var_128], r12
0x180023982  lea     rdx, [rsp+188h+var_128]
0x180023987  mov     rcx, rax
0x18002398a  call    ??0?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@QEAA@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z
0x18002398f  mov     r14, rax
0x180023992  jmp     short loc_1800239A4
0x180023994  mov     r14, r13
0x180023997  mov     rdi, qword ptr [rsp+188h+var_110+8]
0x18002399f  mov     r12, qword ptr [rsp+188h+var_110]
0x1800239a4  mov     [rsp+188h+var_128], r14
0x1800239a9  test    r14, r14
0x1800239ac  jnz     loc_180023A77
0x1800239b2  mov     rcx, [rsp+188h]; this
0x1800239ba  mov     ebx, 8007000Eh
0x1800239bf  mov     r9d, ebx; char *
0x1800239c2  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\prov\\provcsp\\addpa"...
0x1800239c9  lea     edx, [r14+72h]; void *
0x1800239cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239d2  nop
0x1800239d3  mov     rcx, [rsp+188h+var_138]
0x1800239d8  test    rcx, rcx
0x1800239db  jz      short loc_1800239EF
0x1800239dd  mov     [rsp+188h+var_138], r13
0x1800239e2  mov     rax, [rcx]
0x1800239e5  mov     rax, [rax+10h]
0x1800239e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239ee  nop
0x1800239ef  mov     rcx, [rsp+188h+var_140]
0x1800239f4  test    rcx, rcx
0x1800239f7  jz      short loc_180023A0B
0x1800239f9  mov     [rsp+188h+var_140], r13
0x1800239fe  mov     rax, [rcx]
0x180023a01  mov     rax, [rax+10h]
0x180023a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a0a  nop
0x180023a0b  test    rdi, rdi
0x180023a0e  jz      short loc_180023A48
0x180023a10  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023a14  mov     eax, esi
0x180023a16  lock xadd [rdi+8], eax
0x180023a1b  add     eax, esi
0x180023a1d  jnz     short loc_180023A48
0x180023a1f  mov     rax, [rdi]
0x180023a22  mov     rcx, rdi
0x180023a25  mov     rax, [rax]
0x180023a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a2d  mov     eax, esi
0x180023a2f  lock xadd [rdi+0Ch], eax
0x180023a34  add     eax, esi
0x180023a36  jnz     short loc_180023A48
0x180023a38  mov     rax, [rdi]
0x180023a3b  mov     rcx, rdi
0x180023a3e  mov     rax, [rax+8]
0x180023a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a47  nop
0x180023a48  mov     rcx, [rsp+188h+var_148]
0x180023a4d  test    rcx, rcx
0x180023a50  jz      short loc_180023A64
0x180023a52  mov     [rsp+188h+var_148], r13
0x180023a57  mov     rdx, [rcx]
0x180023a5a  mov     rax, [rdx+10h]
0x180023a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a63  nop
0x180023a64  call    cs:__imp_RoUninitialize
0x180023a6b  nop     dword ptr [rax+rax+00h]
0x180023a70  mov     eax, ebx
0x180023a72  jmp     loc_180024298
0x180023a77  mov     r15, [rsi+20h]
0x180023a7b  add     r15, 18h
0x180023a7f  cmp     qword ptr [r15+18h], 8
0x180023a84  jb      short loc_180023A89
0x180023a86  mov     r15, [r15]
0x180023a89  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023a8d  mov     rbx, rsi
0x180023a90  inc     rbx
0x180023a93  cmp     [r15+rbx*2], r13w
0x180023a98  jnz     short loc_180023A90
0x180023a9a  mov     eax, 0FFFFFFFFh
0x180023a9f  cmp     rbx, rax
0x180023aa2  jbe     short loc_180023AC1
0x180023aa4  mov     ebx, eax
0x180023aa6  xor     r9d, r9d; lpArguments
0x180023aa9  xor     r8d, r8d; nNumberOfArguments
0x180023aac  lea     edx, [r9+1]; dwExceptionFlags
0x180023ab0  mov     ecx, 0C000000Dh; dwExceptionCode
0x180023ab5  call    cs:__imp_RaiseException
0x180023abc  nop     dword ptr [rax+rax+00h]
0x180023ac1  lea     r9, [rsp+188h+var_98]; string
0x180023ac9  lea     r8, [rsp+188h+var_90]; hstringHeader
0x180023ad1  mov     edx, ebx; length
0x180023ad3  mov     rcx, r15; sourceString
0x180023ad6  call    cs:__imp_WindowsCreateStringReference
0x180023add  nop     dword ptr [rax+rax+00h]
0x180023ae2  xorps   xmm6, xmm6
0x180023ae5  lea     rcx, [rsp+188h+var_100]; this
0x180023aed  call    ??0ProvAgent@@QEAA@XZ; ProvAgent::ProvAgent(void)
0x180023af2  nop
0x180023af3  lea     rcx, [rsp+188h+var_100]
0x180023afb  call    ?GetCurrentTurn@ProvAgent@@QEBA?AW4ProvisioningTurn@Provisioning@Management@Windows@@XZ; ProvAgent::GetCurrentTurn(void)
0x180023b00  mov     r15d, eax
0x180023b03  mov     rbx, [rsp+188h+var_148]
0x180023b08  mov     rcx, [rbx]
0x180023b0b  mov     r13, [rcx+30h]
0x180023b0f  mov     rcx, [rsp+188h+var_140]
0x180023b14  test    rcx, rcx
0x180023b17  jz      short loc_180023B2F
0x180023b19  mov     [rsp+188h+var_140], 0
0x180023b22  mov     rdx, [rcx]
0x180023b25  mov     rax, [rdx+10h]
0x180023b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b2e  nop
0x180023b2f  movdqa  [rsp+188h+var_E8], xmm6
0x180023b38  lea     rax, [rsp+188h+var_140]
0x180023b3d  mov     [rsp+188h+var_160], rax
0x180023b42  mov     [rsp+188h+var_168], r15d; int
0x180023b47  mov     r9d, 1
0x180023b4d  lea     r8, [rsp+188h+var_E8]
0x180023b55  mov     rdx, [rsp+188h+var_98]
0x180023b5d  mov     rcx, rbx
0x180023b60  mov     rax, r13
0x180023b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b68  mov     ebx, eax
0x180023b6a  xor     r13d, r13d
  ... truncated ...
```
