# CCatalogServer::ConfigureSystemApp(ushort *,ushort *,ushort *)

- ea: `0x1800274b0`
- end: `0x180028d1c`
- name: `?ConfigureSystemApp@CCatalogServer@@UEAAJPEAG00@Z`
- size: `6252`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180009ee0`
- `0x18000af38`
- `0x1800274b0`
- `0x180029294`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027f0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180027f0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800275ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027f1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800275ac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027f1b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800281bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800281bd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180027597`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180027597`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800275d2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800288ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800275d2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800288ea`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027fb9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027fc2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027fb9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027fc2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180027f63`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180027f63`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x180027fb0`
- `api-ms-win-service-management-l1-1-0!DeleteService` at `0x180027fb0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180027f81`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180027f9f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180027f81`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180027f9f`

## string_xrefs

- `0x180027f04`: `catsrv.dll`
- `0x1800276d2`: `My Computer`
- `0x180027f77`: `COMSysApp`
- `0x18002884f`: `COMSysApp`
- `0x180027f95`: `COM+ System Application`
- `0x180027f14`: `DllRegisterServer`
- `0x180028579`: `%systemroot%\system32\com\dmp`
- `0x18002758d`: `ComSetup.dll`
- `0x1800275e7`: `Dispenser created OK`
- `0x180027e2a`: `System application already present OK`
- `0x180027e47`: `Begining to write the .inf file`
- `0x180027e87`: `WriteExistingUsersInRolesToInfFile returned 0x%x`
- `0x180027ef5`: `System application deleted OK`
- `0x1800288ff`: `Creating the component registrar OK`
- `0x180028c02`: `RegDBCompensator row found`
- `0x180028c45`: `Compensator class deleted OK`

## pseudocode

```c
__int64 __fastcall CCatalogServer::ConfigureSystemApp(
        CCatalogServer *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  CCatalogServer *v8; // rcx
  HRESULT IsCallingUs; // ebx
  FARPROC ProcAddress; // rdi
  HMODULE LibraryW; // rax
  int v12; // eax
  int v13; // eax
  __int64 (__fastcall *v14)(CCatalogServer *, LPVOID, __int128 *); // rax
  HRESULT v15; // eax
  int v16; // eax
  HMODULE ModuleHandleW; // rax
  __int64 (*v18)(void); // rax
  SC_HANDLE v19; // rax
  SC_HANDLE v20; // rbx
  SC_HANDLE v21; // rsi
  HINSTANCE v22; // rax
  __int64 (__fastcall *v23)(LPVOID, __int128 *, wchar_t **, __int64, int, _QWORD, _DWORD, __int64 *, int *, __int64 *, __int64 *, __int64 *, __int64 *); // rax
  __int64 (__fastcall *v24)(CCatalogServer *, LPVOID, __int128 *); // rax
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  __int64 v27; // [rsp+78h] [rbp-88h] BYREF
  __int64 v28; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29; // [rsp+88h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+98h] [rbp-68h] BYREF
  int v32; // [rsp+9Ch] [rbp-64h] BYREF
  int v33; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID v34; // [rsp+A8h] [rbp-58h] BYREF
  __int128 *v35; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v36; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v37; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v38; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v39; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v40; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v41; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v42[4]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v43[5]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int16 v44[128]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR Buffer[256]; // [rsp+240h] [rbp+140h] BYREF

  v31 = 2;
  ppv = 0;
  v27 = 0;
  v43[1] = &GUID_DefaultAppPartition;
  v42[1] = &GUID_DefaultAppPartition;
  v43[2] = &GUID_NULL;
  v43[0] = &CLSID_RegDBCompensator;
  v42[2] = &GUID_NULL;
  v43[3] = &v31;
  v29 = 0;
  v42[0] = &CLSID_CatalogServer;
  v26 = 0;
  v42[3] = &v31;
  v28 = 0;
  v34 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  v37 = 0;
  v33 = 0;
  v35 = 0;
  memset_0(v44, 0, sizeof(v44));
  IsCallingUs = CCatalogServer::VerifyAnAdministratorIsCallingUs(v8);
  if ( IsCallingUs >= 0 )
  {
    ProcAddress = 0;
    LibraryW = LoadLibraryW(L"ComSetup.dll");
    if ( LibraryW )
      ProcAddress = GetProcAddress(LibraryW, "SetupPrintLog");
    IsCallingUs = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, &ppv);
    if ( IsCallingUs >= 0 )
    {
      if ( ProcAddress )
        ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Dispenser created OK");
      IsCallingUs = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, _QWORD, _QWORD, int, _DWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
                      ppv,
                      didCOMSERVICES,
                      tidCOMSERVICES_MACHINESETTINGS,
                      0,
                      0,
                      1,
                      0,
                      &v27);
      if ( IsCallingUs >= 0 )
      {
        if ( ProcAddress )
          ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Getting the machine settings table OK");
        IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 24LL))(v27);
        if ( IsCallingUs >= 0 )
        {
          if ( ProcAddress )
            ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Populating the machine settings table OK");
          v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 40LL))(v27);
          IsCallingUs = v12;
          if ( v12 == -2146367487 )
          {
            IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 120LL))(v27);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            if ( ProcAddress )
              ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Adding a new row machine settings table OK");
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            0,
                            0,
                            L"My Computer");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const WCHAR *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            1,
                            0,
                            &word_18005C890);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            2,
                            0,
                            &ulDefTxnTimeout);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            4,
                            0,
                            L"Y");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const WCHAR *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            6,
                            0,
                            &word_18005C890);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            7,
                            0,
                            &ulDefIMDBMemorySize);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            9,
                            0,
                            L"N");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            10,
                            0,
                            L"N");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            11,
                            0,
                            L"Y");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            12,
                            0,
                            &ulDefAuthenticationLevel);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            13,
                            0,
                            &ulDefImpersonationLevel);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            14,
                            0,
                            L"Y");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            15,
                            0,
                            L"N");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            16,
                            0,
                            L"N");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            17,
                            0,
                            L"N");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            18,
                            0,
                            L"N");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const WCHAR *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            19,
                            0,
                            &word_18005C890);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            22,
                            0,
                            L"N");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            23,
                            0,
                            L"Y");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            24,
                            0,
                            L"Y");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            25,
                            0,
                            &ulDefRpcProxyEnabled);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            27,
                            0,
                            &GUID_NULL);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            28,
                            0,
                            L"Y");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v27 + 160LL))(
                            v27,
                            29,
                            0,
                            L"Y");
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 144LL))(v27);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            if ( ProcAddress )
              ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Set row on machine settings table OK");
            IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 96LL))(v27);
            if ( IsCallingUs < 0 )
              goto LABEL_192;
            if ( ProcAddress )
              ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Saving the machine settings table OK");
          }
          else if ( v12 < 0 )
          {
            goto LABEL_192;
          }
          IsCallingUs = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, _QWORD, _QWORD, int, _DWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          didCOMSERVICES,
                          &TID_APPLICATIONPARTITION,
                          0,
                          0,
                          1,
                          0,
                          &v29);
          if ( IsCallingUs >= 0 )
          {
            if ( ProcAddress )
              ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Getting the application partition table OK");
            IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 24LL))(v29);
            if ( IsCallingUs >= 0 )
            {
              if ( ProcAddress )
                ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Populating the application partition table OK");
              v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 40LL))(v29);
              IsCallingUs = v13;
              if ( v13 == -2146367487 )
              {
                IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 120LL))(v29);
                if ( IsCallingUs < 0 )
                  goto LABEL_192;
                if ( ProcAddress )
                  ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Adding a new row application partition table OK");
                IsCallingUs = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, GUID *))(*(_QWORD *)v29 + 160LL))(
                                v29,
                                0,
                                0,
                                &GUID_DefaultAppPartition);
                if ( IsCallingUs < 0 )
                  goto LABEL_192;
                IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v29 + 160LL))(
                                v29,
                                1,
                                0,
                                L"Base Application Partition");
                if ( IsCallingUs < 0 )
                  goto LABEL_192;
                IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v29 + 160LL))(
                                v29,
                                3,
                                0,
                                L"Y");
                if ( IsCallingUs < 0 )
                  goto LABEL_192;
                IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v29 + 160LL))(
                                v29,
                                4,
                                0,
                                L"Y");
                if ( IsCallingUs < 0 )
                  goto LABEL_192;
                IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 144LL))(v29);
                if ( IsCallingUs < 0 )
                  goto LABEL_192;
                if ( ProcAddress )
                  ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Set row on application partition table OK");
                IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 96LL))(v29);
                if ( IsCallingUs < 0 )
                  goto LABEL_192;
                if ( ProcAddress )
                  ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Saving the application partition table OK");
              }
              else if ( v13 < 0 )
              {
                goto LABEL_192;
              }
              v14 = *(__int64 (__fastcall **)(CCatalogServer *, LPVOID, __int128 *))(*(_QWORD *)this + 40LL);
              v36 = applidSystemApp;
              v15 = v14(this, ppv, &v36);
              IsCallingUs = v15;
              if ( !v15 || v15 == -2146367487 )
              {
                IsCallingUs = (*(__int64 (__fastcall **)(LPVOID, __int64 *, const struct _GUID *, _QWORD, _QWORD, int, _DWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
                                ppv,
                                didCOMSERVICES,
                                &TID_APPLICATION,
                                0,
                                0,
                                1,
                                0,
                                &v26);
                if ( IsCallingUs >= 0 )
                {
                  if ( ProcAddress )
                    ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Getting the application table OK");
                  IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 24LL))(v26);
                  if ( IsCallingUs >= 0 )
                  {
                    if ( ProcAddress )
                      ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Populating the application table OK");
                    v35 = &applidSystemApp;
                    if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, __int128 **))(*(_QWORD *)v26 + 56LL))(
                           v26,
                           0,
                           &v35) )
                    {
                      v19 = OpenSCManagerW(0, 0, 0x80000000);
                      v20 = v19;
                      if ( v19 )
                      {
                        v21 = OpenServiceW(v19, L"COMSysApp", 0x10000u);
                        if ( v21 || (v21 = OpenServiceW(v20, L"COM+ System Application", 0x10000u)) != 0 )
                        {
                          DeleteService(v21);
                          CloseServiceHandle(v21);
                        }
                        CloseServiceHandle(v20);
                      }
                      goto LABEL_101;
                    }
                    if ( ProcAddress )
                      ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"System application already present OK");
                    v32 = 0;
                    if ( a4 )
                    {
                      if ( ProcAddress )
                        ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Begining to write the .inf file");
                      v16 = (*(__int64 (__fastcall **)(char *, LPVOID, __int128 *, unsigned __int16 *, int *))(*((_QWORD *)this + 7) + 40LL))(
                              (char *)this + 56,
                              ppv,
                              &applidSystemApp,
                              a4,
                              &v32);
                      IsCallingUs = v16;
                      if ( v16 < 0 )
                        goto LABEL_192;
                      IsCallingUs = StringCchPrintfW(
                                      v44,
                                      0x80u,
                                      L"WriteExistingUsersInRolesToInfFile returned 0x%x",
                                      (unsigned int)v16);
                      if ( IsCallingUs < 0 )
                        goto LABEL_192;
                      if ( ProcAddress )
                        ((void (__fastcall *)(unsigned __int16 *))ProcAddress)(v44);
                    }
                    IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 136LL))(v26);
                    if ( IsCallingUs >= 0 )
                    {
                      IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 96LL))(v26);
                      if ( IsCallingUs >= 0 )
                      {
                        if ( ProcAddress )
                          ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"System application deleted OK");
                        ModuleHandleW = GetModuleHandleW(L"catsrv.dll");
                        v18 = GetProcAddress(ModuleHandleW, "DllRegisterServer");
                        if ( !v18 )
                        {
                          IsCallingUs = -2147418113;
                          goto LABEL_192;
                        }
                        IsCallingUs = v18();
                        if ( IsCallingUs >= 0 )
                        {
                          if ( ProcAddress )
                            ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Registering the catalog server OK");
LABEL_101:
                          IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 120LL))(v26);
                          if ( IsCallingUs >= 0 )
                          {
                            IsCallingUs = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)v26 + 160LL))(
                                            v26,
                                            0,
                                            0,
                                            &applidSystemApp);
                            if ( IsCallingUs >= 0 )
                            {
                              IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v26 + 160LL))(
                                              v26,
                                              1,
                                              0,
                                              L"System Application");
                              if ( IsCallingUs >= 0 )
                              {
                                IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                v26,
                                                2,
                                                0,
                                                &ulZero);
                                if ( IsCallingUs >= 0 )
                                {
                                  IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v26 + 160LL))(
                                                  v26,
                                                  14,
                                                  0,
                                                  L"Y");
                                  if ( IsCallingUs >= 0 )
                                  {
                                    IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v26 + 160LL))(
                                                    v26,
                                                    11,
                                                    0,
                                                    L"N");
                                    if ( IsCallingUs >= 0 )
                                    {
                                      IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                      v26,
                                                      26,
                                                      0,
                                                      &ulTrue);
                                      if ( IsCallingUs >= 0 )
                                      {
                                        IsCallingUs = (*(__int64 (**)(__int64, __int64, _QWORD, const WCHAR *, ...))(*(_QWORD *)v26 + 160LL))(
                                                        v26,
                                                        34,
                                                        0,
                                                        L"%systemroot%\\Registration");
                                        if ( IsCallingUs >= 0 )
                                        {
                                          if ( !a2
                                            || (IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v26 + 160LL))(
                                                                v26,
                                                                8,
                                                                0,
                                                                a2),
                                                IsCallingUs >= 0) )
                                          {
                                            if ( !a3
                                              || (IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 *))(*(_QWORD *)v26 + 160LL))(
                                                                  v26,
                                                                  15,
                                                                  0,
                                                                  a3),
                                                  IsCallingUs >= 0) )
                                            {
                                              IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                              v26,
                                                              12,
                                                              0,
                                                              &ulAuthentication);
                                              if ( IsCallingUs >= 0 )
                                              {
                                                Buffer[0] = 0;
                                                v22 = COMResModuleInstance();
                                                LoadStringW(v22, 0x65u, Buffer, 256);
                                                IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, WCHAR *))(*(_QWORD *)v26 + 160LL))(
                                                                v26,
                                                                10,
                                                                0,
                                                                Buffer);
                                                if ( IsCallingUs >= 0 )
                                                {
                                                  IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                  v26,
                                                                  13,
                                                                  0,
                                                                  &ulShutdownAfter);
                                                  if ( IsCallingUs >= 0 )
                                                  {
                                                    IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                    v26,
                                                                    22,
                                                                    0,
                                                                    &ulFalse);
                                                    if ( IsCallingUs >= 0 )
                                                    {
                                                      IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v26 + 160LL))(
                                                                      v26,
                                                                      16,
                                                                      0,
                                                                      L"Local");
                                                      if ( IsCallingUs >= 0 )
                                                      {
                                                        IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v26 + 160LL))(
                                                                        v26,
                                                                        17,
                                                                        0,
                                                                        L"Y");
                                                        if ( IsCallingUs >= 0 )
                                                        {
                                                          IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v26 + 160LL))(
                                                                          v26,
                                                                          18,
                                                                          0,
                                                                          L"Y");
                                                          if ( IsCallingUs >= 0 )
                                                          {
                                                            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const WCHAR *))(*(_QWORD *)v26 + 160LL))(
                                                                            v26,
                                                                            19,
                                                                            0,
                                                                            &word_18005C890);
                                                            if ( IsCallingUs >= 0 )
                                                            {
                                                              IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                              v26,
                                                                              21,
                                                                              0,
                                                                              &ulTrue);
                                                              if ( IsCallingUs >= 0 )
                                                              {
                                                                IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const WCHAR *))(*(_QWORD *)v26 + 160LL))(
                                                                                v26,
                                                                                3,
                                                                                0,
                                                                                &word_18005C890);
                                                                if ( IsCallingUs >= 0 )
                                                                {
                                                                  IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                                  v26,
                                                                                  4,
                                                                                  0,
                                                                                  &ulProcessType);
                                                                  if ( IsCallingUs >= 0 )
                                                                  {
                                                                    IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const WCHAR *))(*(_QWORD *)v26 + 160LL))(
                                                                                    v26,
                                                                                    5,
                                                                                    0,
                                                                                    &word_18005C890);
                                                                    if ( IsCallingUs >= 0 )
                                                                    {
                                                                      IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                                      v26,
                                                                                      7,
                                                                                      0,
                                                                                      &ulRunAsUserType);
                                                                      if ( IsCallingUs >= 0 )
                                                                      {
                                                                        IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                                        v26,
                                                                                        24,
                                                                                        0,
                                                                                        &ulImpersonationLevel);
                                                                        if ( IsCallingUs >= 0 )
                                                                        {
                                                                          IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                                          v26,
                                                                                          25,
                                                                                          0,
                                                                                          &ulAuthenticationCapability);
                                                                          if ( IsCallingUs >= 0 )
                                                                          {
                                                                            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                                            v26,
                                                                                            27,
                                                                                            0,
                                                                                            &ulFalse);
                                                                            if ( IsCallingUs >= 0 )
                                                                            {
                                                                              IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                                              v26,
                                                                                              28,
                                                                                              0,
                                                                                              &ulFalse);
                                                                              if ( IsCallingUs >= 0 )
                                                                              {
                                                                                IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *))(*(_QWORD *)v26 + 160LL))(
                                                                                                v26,
                                                                                                29,
                                                                                                0,
                                                                                                L"N");
                                                                                if ( IsCallingUs >= 0 )
                                                                                {
                                                                                  IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                                                  v26,
                                                                                                  30,
                                                                                                  0,
                                                                                                  &ulTrue);
                                                                                  if ( IsCallingUs >= 0 )
                                                                                  {
                                                                                    IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(
                                                                                                    v26,
                                                                                                    35,
                                                                                                    0,
                                                                                                    &ulFalse);
                                                                                    if ( IsCallingUs >= 0 )
                                                                                    {
                                                                                      IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 36, 0, &ulFalse);
                                                                                      if ( IsCallingUs >= 0 )
                                                                                      {
                                                                                        IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 37, 0, &ulFalse);
                                                                                        if ( IsCallingUs >= 0 )
                                                                                        {
                                                                                          IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 38, 0, &ulMaxDumpCount);
                                                                                          if ( IsCallingUs >= 0 )
                                                                                          {
                                                                                            IsCallingUs = (*(__int64 (**)(__int64, __int64, _QWORD, const wchar_t *, ...))(*(_QWORD *)v26 + 160LL))(v26, 39, 0, L"%systemroot%\\system32\\com\\dmp");
                                                                                            if ( IsCallingUs >= 0 )
                                                                                            {
                                                                                              IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 40, 0, &ulTrue);
                                                                                              if ( IsCallingUs >= 0 )
                                                                                              {
                                                                                                IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *))(*(_QWORD *)v26 + 160LL))(v26, 41, 0, &GUID_DefaultAppPartition);
                                                                                                if ( IsCallingUs >= 0 )
                                                                                                {
                                                                                                  IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 42, 0, &ulNumApps);
                                                                                                  if ( IsCallingUs >= 0 )
                                                                                                  {
                                                                                                    IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 43, 0, &ulRecycleLifetimeLimit);
                                                                                                    if ( IsCallingUs >= 0 )
                                                                                                    {
                                                                                                      IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 44, 0, &ulRecycleCallLimit);
                                                                                                      if ( IsCallingUs >= 0 )
                                                                                                      {
                                                                                                        IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 45, 0, &ulRecycleActivationLimit);
                                                                                                        if ( IsCallingUs >= 0 )
                                                                                                        {
                                                                                                          IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 46, 0, &ulRecycleMemoryLimit);
                                                                                                          if ( IsCallingUs >= 0 )
                                                                                                          {
                                                                                                            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 47, 0, &ulRecycleExpirationTimeout);
                                                                                                            if ( IsCallingUs >= 0 )
                                                                                                            {
                                                                                                              IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 49, 0, &ulTrue);
                                                                                                              if ( IsCallingUs >= 0 )
                                                                                                              {
                                                                                                                IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, const WCHAR *))(*(_QWORD *)v26 + 160LL))(v26, 50, 0, &word_18005C890);
                                                                                                                if ( IsCallingUs >= 0 )
                                                                                                                {
                                                                                                                  IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 51, 0, &dwSaferTrustedLevel);
                                                                                                                  if ( IsCallingUs >= 0 )
                                                                                                                  {
                                                                                                                    IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 52, 0, &ulFalse);
                                                                                                                    if ( IsCallingUs >= 0 )
                                                                                                                    {
                                                                                                                      IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v26 + 160LL))(v26, 53, 0, &ulFalse);
                                                                                                                      if ( IsCallingUs >= 0 )
                                                                                                                      {
                                                                                                                        IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v26 + 160LL))(v26, 54, 0, 0);
                                                                                                                        if ( IsCallingUs >= 0 )
                                                                                                                        {
                                                                                                                          IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v26 + 160LL))(v26, 55, 0, 0);
                                                                                                                          if ( IsCallingUs >= 0 )
                                                                                                                          {
                                                                                                                            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)v26 + 160LL))(v26, 56, 0, 0);
                                                                                                                            if ( IsCallingUs >= 0 )
                                                                                                                            {
                                                                                                                              (*(void (__fastcall **)(__int64, __int64, _QWORD, const WCHAR *))(*(_QWORD *)v26 + 160LL))(v26, 6, 0, L"COMSysApp");
                                                                                                                              if ( ProcAddress )
                                                                                                                                ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Before SetRow on the application table OK");
                                                                                                                              IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 144LL))(v26);
                                                                                                                              if ( IsCallingUs >= 0 )
                                                                                                                              {
                                                                                                                                IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 96LL))(v26);
                                                                                                                                if ( IsCallingUs >= 0 )
                                                                                                                                {
                                                                                                                                  if ( ProcAddress )
                                                                                                                                    ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Saving the application table OK");
                                                                                                                                  IsCallingUs = CoCreateInstance(&CLSID_COMComponentRegistrar, 0, 3u, &IID_IRegister, &v34);
                                                                                                                                  if ( IsCallingUs >= 0 )
                                                                                                                                  {
                                                                                                                                    if ( ProcAddress )
                                                                                                                                      ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Creating the component registrar OK");
                                                                                                                                    v23 = *(__int64 (__fastcall **)(LPVOID, __int128 *, wchar_t **, __int64, int, _QWORD, _DWORD, __int64 *, int *, __int64 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v34 + 24LL);
                                                                                                                                    v36 = applidSystemApp;
                                                                                                                                    IsCallingUs = v23(v34, &v36, &off_18005A118, 1, 256, 0, 0, &v41, &v33, &v40, &v39, &v38, &v37);
                                                                                                                                    if ( IsCallingUs >= 0 )
                                                                                                                                    {
                                                                                                                                      if ( ProcAddress )
                                                                                                                                        ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Registering the module OK");
                                                                                                                                      IsCallingUs = (*(__int64 (__fastcall **)(LPVOID, __int64 *, const struct _GUID *, _QWORD, _QWORD, int, _DWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, didCOMSERVICES, &tidCOMSERVICES_CLASSES_INTERNAL, 0, 0, 1, 0, &v28);
                                                                                                                                      if ( IsCallingUs >= 0 )
                                                                                                                                      {
                                                                                                                                        if ( ProcAddress )
                                                                                                                                          ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Getting the classes internal table OK");
                                                                                                                                        IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 24LL))(v28);
                                                                                                                                        if ( IsCallingUs >= 0 )
                                                                                                                                        {
                                                                                                                                          IsCallingUs = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v28 + 56LL))(v28, 0, v42);
                                                                                                                                          if ( IsCallingUs >= 0 )
                                                                                                                                          {
                                                                                                                                            if ( ProcAddress )
                                                                                                                                              ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Catalog server row found");
                                                                                                                                            IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 128LL))(v28);
                                                                                                                                            if ( IsCallingUs >= 0 )
                                                                                                                                            {
                                                                                                                                              IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v28 + 160LL))(v28, 12, 0, &ulTransaction);
                                                                                                                                              if ( IsCallingUs >= 0 )
                                                                                                                                              {
                                                                                                                                                IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v28 + 160LL))(v28, 13, 0, &ulSyncronization);
                                                                                                                                                if ( IsCallingUs >= 0 )
                                                                                                                                                {
                                                                                                                                                  IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v28 + 160LL))(v28, 16, 0, &ulFalse);
                                                                                                                                                  if ( IsCallingUs >= 0 )
                                                                                                                                                  {
                                                                                                                                                    IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v28 + 160LL))(v28, 15, 0, &ulFalse);
                                                                                                                                                    if ( IsCallingUs >= 0 )
                                                                                                                                                    {
                                                                                                                                                      IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v28 + 160LL))(v28, 17, 0, &ulTrue);
                                                                                                                                                      if ( IsCallingUs >= 0 )
                                                                                                                                                      {
                                                                                                                                                        IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v28 + 160LL))(v28, 18, 0, &ulTrue);
                                                                                                                                                        if ( IsCallingUs >= 0 )
                                                                                                                                                        {
                                                                                                                                                          IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v28 + 160LL))(v28, 47, 0, &ulTrue);
                                                                                                                                                          if ( IsCallingUs >= 0 )
                                                                                                                                                          {
                                                                                                                                                            IsCallingUs = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v28 + 160LL))(v28, 49, 0, &ulFalse);
                                                                                                                                                            if ( IsCallingUs >= 0 )
                                                                                                                                                            {
                                                                                                                                                              IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 144LL))(v28);
                                                                                                                                                              if ( IsCallingUs >= 0 )
                                                                                                                                                              {
                                                                                                                                                                if ( ProcAddress )
                                                                                                                                                                  ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Setting the properties OK");
                                                                                                                                                                IsCallingUs = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v28 + 56LL))(v28, 0, v43);
                                                                                                                                                                if ( IsCallingUs >= 0 )
                                                                                                                                                                {
                                                                                                                                                                  if ( ProcAddress )
                                                                                                                                                                    ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"RegDBCompensator row found");
                                                                                                                                                                  IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 136LL))(v28);
                                                                                                                                                                  if ( IsCallingUs >= 0 )
                                                                                                                                                                  {
                                                                                                                                                                    IsCallingUs = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 96LL))(v28);
                                                                                                                                                                    if ( IsCallingUs >= 0 )
                                                                                                                                                                    {
                                                                                                                                                                      if ( ProcAddress )
                                                                                                                                                                        ((void (__fastcall *)(const wchar_t *))ProcAddress)(L"Compensator class deleted OK");
                                                                                                                                                                      v24 = *(__int64 (__fastcall **)(CCatalogServer *, LPVOID, __int128 *))(*(_QWORD *)this + 32LL);
                                                                                                                                                                      v36 = applidSystemApp;
                                                                                                                                                                      IsCallingUs = v24(this, ppv, &v36);
                                                                                                                                                                    }
                                                                                                                                                                  }
                                                                                                                                                                }
                                                                                                                                                              }
                                                                                                                                                            }
                                                                                                                                                          }
                                                                                                                                                        }
                                                                                                                                                      }
                                                                                                                                                    }
                                                                                                                                                  }
                                                                                                                                                }
                                                                                                                                              }
                                                                                                                                            }
                                                                                                                                          }
                                                                                                                                        }
                                                                                                                                      }
                                                                                                                                    }
                                                                                                                                  }
                                                                                                                                }
                                                                                                                              }
                                                                                                                            }
                                                                                                                          }
                                                                                                                        }
                                                                                                                      }
                                                                                                                    }
                                                                                                                  }
                                                                                                                }
                                                                                                              }
                                                                                                            }
                                                                                                          }
                                                                                                        }
                                                                                                      }
                                                                                                    }
                                                                                                  }
                                                                                                }
                                                                                              }
                                                                                            }
                                                                                          }
                                                                                        }
                                                                                      }
                                                                                    }
                                                                                  }
                                                                                }
                                                                              }
                                                                            }
                                                                          }
                                                                        }
                                                                      }
                                                                    }
                                                                  }
                                                                }
                                                              }
                                                            }
                                                          }
                                                        }
                                                      }
                                                    }
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_192:
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v27 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  if ( v34 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
  return (unsigned int)IsCallingUs;
}

```

## disassembly

```asm
0x1800274b0  push    rbp
0x1800274b2  push    rbx
0x1800274b3  push    rsi
0x1800274b4  push    rdi
0x1800274b5  push    r12
0x1800274b7  push    r13
0x1800274b9  push    r14
0x1800274bb  push    r15
0x1800274bd  lea     rbp, [rsp-358h]
0x1800274c5  sub     rsp, 458h
0x1800274cc  mov     rax, cs:__security_cookie
0x1800274d3  xor     rax, rsp
0x1800274d6  mov     [rbp+390h+var_50], rax
0x1800274dd  xor     r13d, r13d
0x1800274e0  mov     [rbp+390h+var_3F8], 2
0x1800274e7  mov     r14, rdx
0x1800274ea  mov     [rbp+390h+var_400], r13
0x1800274ee  lea     rdx, GUID_DefaultAppPartition
0x1800274f5  mov     [rsp+490h+var_418], r13
0x1800274fa  mov     r12, rcx
0x1800274fd  mov     [rbp+390h+var_370], rdx
0x180027501  lea     rcx, GUID_NULL
0x180027508  mov     [rbp+390h+var_390], rdx
0x18002750c  lea     rax, CLSID_RegDBCompensator
0x180027513  mov     [rbp+390h+var_368], rcx
0x180027517  mov     [rbp+390h+var_378], rax
0x18002751b  mov     r15, r8
0x18002751e  lea     rax, [rbp+390h+var_3F8]
0x180027522  mov     [rbp+390h+var_388], rcx
0x180027526  mov     [rbp+390h+var_360], rax
0x18002752a  lea     rcx, [rbp+390h+var_350]; void *
0x18002752e  lea     rax, CLSID_CatalogServer
0x180027535  mov     [rbp+390h+var_408], r13
0x180027539  mov     [rbp+390h+var_398], rax
0x18002753d  xor     edx, edx; Val
0x18002753f  lea     rax, [rbp+390h+var_3F8]
0x180027543  mov     [rsp+490h+var_420], r13
0x180027548  mov     r8d, 100h; Size
0x18002754e  mov     [rbp+390h+var_380], rax
0x180027552  mov     rsi, r9
0x180027555  mov     [rbp+390h+var_410], r13
0x180027559  mov     [rbp+390h+var_3E8], r13
0x18002755d  mov     [rbp+390h+var_3A0], r13
0x180027561  mov     [rbp+390h+var_3A8], r13
0x180027565  mov     [rbp+390h+var_3B0], r13
0x180027569  mov     [rbp+390h+var_3B8], r13
0x18002756d  mov     [rbp+390h+var_3C0], r13
0x180027571  mov     [rbp+390h+var_3F0], r13d
0x180027575  mov     [rbp+390h+var_3E0], r13
0x180027579  call    memset_0
0x18002757e  call    ?VerifyAnAdministratorIsCallingUs@CCatalogServer@@AEAAJXZ; CCatalogServer::VerifyAnAdministratorIsCallingUs(void)
0x180027583  mov     ebx, eax
0x180027585  test    eax, eax
0x180027587  js      loc_180028C7A
0x18002758d  lea     rcx, aComsetupDll; "ComSetup.dll"
0x180027594  mov     edi, r13d
0x180027597  call    cs:__imp_LoadLibraryW
0x18002759d  test    rax, rax
0x1800275a0  jz      short loc_1800275B5
0x1800275a2  lea     rdx, ProcName; "SetupPrintLog"
0x1800275a9  mov     rcx, rax; hModule
0x1800275ac  call    cs:__imp_GetProcAddress
0x1800275b2  mov     rdi, rax
0x1800275b5  xor     edx, edx; pUnkOuter
0x1800275b7  lea     rax, [rbp+390h+var_400]
0x1800275bb  lea     r9, IID_ISimpleTableDispenser; riid
0x1800275c2  mov     [rsp+490h+ppv], rax; ppv
0x1800275c7  lea     rcx, CLSID_STDispenser; rclsid
0x1800275ce  lea     r8d, [rdx+1]; dwClsContext
0x1800275d2  call    cs:__imp_CoCreateInstance
0x1800275d8  mov     ebx, eax
0x1800275da  test    eax, eax
0x1800275dc  js      loc_180028C7A
0x1800275e2  test    rdi, rdi
0x1800275e5  jz      short loc_1800275F6
0x1800275e7  lea     rcx, aDispenserCreat; "Dispenser created OK"
0x1800275ee  mov     rax, rdi
0x1800275f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275f6  mov     rcx, [rbp+390h+var_400]
0x1800275fa  lea     rdx, [rsp+490h+var_418]
0x1800275ff  mov     [rsp+490h+var_458], rdx
0x180027604  lea     r8, tidCOMSERVICES_MACHINESETTINGS
0x18002760b  mov     [rsp+490h+var_460], r13d
0x180027610  lea     rdx, didCOMSERVICES
0x180027617  mov     dword ptr [rsp+490h+var_468], 1
0x18002761f  xor     r9d, r9d
0x180027622  mov     rax, [rcx]
0x180027625  mov     [rsp+490h+ppv], r13
0x18002762a  mov     rax, [rax+18h]
0x18002762e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027633  mov     ebx, eax
0x180027635  test    eax, eax
0x180027637  js      loc_180028C7A
0x18002763d  test    rdi, rdi
0x180027640  jz      short loc_180027651
0x180027642  lea     rcx, aGettingTheMach; "Getting the machine settings table OK"
0x180027649  mov     rax, rdi
0x18002764c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027651  mov     rcx, [rsp+490h+var_418]
0x180027656  mov     rax, [rcx]
0x180027659  mov     rax, [rax+18h]
0x18002765d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027662  mov     ebx, eax
0x180027664  test    eax, eax
0x180027666  js      loc_180028C7A
0x18002766c  test    rdi, rdi
0x18002766f  jz      short loc_180027680
0x180027671  lea     rcx, aPopulatingTheM; "Populating the machine settings table O"...
0x180027678  mov     rax, rdi
0x18002767b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027680  mov     rcx, [rsp+490h+var_418]
0x180027685  mov     rax, [rcx]
0x180027688  mov     rax, [rax+28h]
0x18002768c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027691  mov     ebx, eax
0x180027693  cmp     eax, 80110801h
0x180027698  jnz     loc_180027B4E
0x18002769e  mov     rcx, [rsp+490h+var_418]
0x1800276a3  mov     rax, [rcx]
0x1800276a6  mov     rax, [rax+78h]
0x1800276aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276af  mov     ebx, eax
0x1800276b1  test    eax, eax
0x1800276b3  js      loc_180028C7A
0x1800276b9  test    rdi, rdi
0x1800276bc  jz      short loc_1800276CD
0x1800276be  lea     rcx, aAddingANewRowM; "Adding a new row machine settings table"...
0x1800276c5  mov     rax, rdi
0x1800276c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276cd  mov     rcx, [rsp+490h+var_418]
0x1800276d2  lea     r9, aMyComputer; "My Computer"
0x1800276d9  xor     r8d, r8d
0x1800276dc  xor     edx, edx
0x1800276de  mov     rax, [rcx]
0x1800276e1  mov     rax, [rax+0A0h]
0x1800276e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276ed  mov     ebx, eax
0x1800276ef  test    eax, eax
0x1800276f1  js      loc_180028C7A
0x1800276f7  mov     rcx, [rsp+490h+var_418]
0x1800276fc  lea     r9, word_18005C890
0x180027703  xor     r8d, r8d
0x180027706  mov     rax, [rcx]
0x180027709  lea     edx, [r8+1]
0x18002770d  mov     rax, [rax+0A0h]
0x180027714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027719  mov     ebx, eax
0x18002771b  test    eax, eax
0x18002771d  js      loc_180028C7A
0x180027723  mov     rcx, [rsp+490h+var_418]
0x180027728  lea     r9, ?ulDefTxnTimeout@@3KA; ulong ulDefTxnTimeout
0x18002772f  xor     r8d, r8d
0x180027732  mov     rax, [rcx]
0x180027735  lea     edx, [r8+2]
0x180027739  mov     rax, [rax+0A0h]
0x180027740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027745  mov     ebx, eax
0x180027747  test    eax, eax
0x180027749  js      loc_180028C7A
0x18002774f  mov     rcx, [rsp+490h+var_418]
0x180027754  lea     r9, aY; "Y"
0x18002775b  xor     r8d, r8d
0x18002775e  mov     rax, [rcx]
0x180027761  lea     edx, [r8+4]
0x180027765  mov     rax, [rax+0A0h]
0x18002776c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027771  mov     ebx, eax
0x180027773  test    eax, eax
0x180027775  js      loc_180028C7A
0x18002777b  mov     rcx, [rsp+490h+var_418]
0x180027780  lea     r9, word_18005C890
0x180027787  xor     r8d, r8d
0x18002778a  mov     rax, [rcx]
0x18002778d  lea     edx, [r8+6]
0x180027791  mov     rax, [rax+0A0h]
0x180027798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002779d  mov     ebx, eax
0x18002779f  test    eax, eax
0x1800277a1  js      loc_180028C7A
0x1800277a7  mov     rcx, [rsp+490h+var_418]
0x1800277ac  lea     r9, ?ulDefIMDBMemorySize@@3KA; ulong ulDefIMDBMemorySize
0x1800277b3  xor     r8d, r8d
0x1800277b6  mov     rax, [rcx]
0x1800277b9  lea     edx, [r8+7]
0x1800277bd  mov     rax, [rax+0A0h]
0x1800277c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277c9  mov     ebx, eax
0x1800277cb  test    eax, eax
0x1800277cd  js      loc_180028C7A
0x1800277d3  mov     rcx, [rsp+490h+var_418]
0x1800277d8  lea     r9, aN; "N"
0x1800277df  xor     r8d, r8d
0x1800277e2  mov     rax, [rcx]
0x1800277e5  lea     edx, [r8+9]
0x1800277e9  mov     rax, [rax+0A0h]
0x1800277f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277f5  mov     ebx, eax
0x1800277f7  test    eax, eax
0x1800277f9  js      loc_180028C7A
0x1800277ff  mov     rcx, [rsp+490h+var_418]
0x180027804  lea     r9, aN; "N"
0x18002780b  xor     r8d, r8d
0x18002780e  mov     rax, [rcx]
0x180027811  lea     edx, [r8+0Ah]
0x180027815  mov     rax, [rax+0A0h]
0x18002781c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027821  mov     ebx, eax
0x180027823  test    eax, eax
0x180027825  js      loc_180028C7A
0x18002782b  mov     rcx, [rsp+490h+var_418]
0x180027830  lea     r9, aY; "Y"
0x180027837  xor     r8d, r8d
0x18002783a  mov     rax, [rcx]
0x18002783d  lea     edx, [r8+0Bh]
0x180027841  mov     rax, [rax+0A0h]
0x180027848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002784d  mov     ebx, eax
0x18002784f  test    eax, eax
0x180027851  js      loc_180028C7A
0x180027857  mov     rcx, [rsp+490h+var_418]
0x18002785c  lea     r9, ?ulDefAuthenticationLevel@@3KA; ulong ulDefAuthenticationLevel
0x180027863  xor     r8d, r8d
0x180027866  mov     rax, [rcx]
0x180027869  lea     edx, [r8+0Ch]
0x18002786d  mov     rax, [rax+0A0h]
0x180027874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027879  mov     ebx, eax
0x18002787b  test    eax, eax
0x18002787d  js      loc_180028C7A
0x180027883  mov     rcx, [rsp+490h+var_418]
0x180027888  lea     r9, ?ulDefImpersonationLevel@@3KA; ulong ulDefImpersonationLevel
0x18002788f  xor     r8d, r8d
0x180027892  mov     rax, [rcx]
0x180027895  lea     edx, [r8+0Dh]
0x180027899  mov     rax, [rax+0A0h]
0x1800278a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278a5  mov     ebx, eax
0x1800278a7  test    eax, eax
0x1800278a9  js      loc_180028C7A
0x1800278af  mov     rcx, [rsp+490h+var_418]
0x1800278b4  lea     r9, aY; "Y"
0x1800278bb  xor     r8d, r8d
0x1800278be  mov     rax, [rcx]
0x1800278c1  lea     edx, [r8+0Eh]
0x1800278c5  mov     rax, [rax+0A0h]
0x1800278cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278d1  mov     ebx, eax
0x1800278d3  test    eax, eax
0x1800278d5  js      loc_180028C7A
0x1800278db  mov     rcx, [rsp+490h+var_418]
0x1800278e0  lea     r9, aN; "N"
0x1800278e7  xor     r8d, r8d
0x1800278ea  mov     rax, [rcx]
0x1800278ed  lea     edx, [r8+0Fh]
0x1800278f1  mov     rax, [rax+0A0h]
0x1800278f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278fd  mov     ebx, eax
0x1800278ff  test    eax, eax
0x180027901  js      loc_180028C7A
0x180027907  mov     rcx, [rsp+490h+var_418]
0x18002790c  lea     r9, aN; "N"
0x180027913  xor     r8d, r8d
0x180027916  mov     rax, [rcx]
0x180027919  lea     edx, [r8+10h]
0x18002791d  mov     rax, [rax+0A0h]
0x180027924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027929  mov     ebx, eax
0x18002792b  test    eax, eax
0x18002792d  js      loc_180028C7A
0x180027933  mov     rcx, [rsp+490h+var_418]
0x180027938  lea     r9, aN; "N"
0x18002793f  xor     r8d, r8d
0x180027942  mov     rax, [rcx]
0x180027945  lea     edx, [r8+11h]
0x180027949  mov     rax, [rax+0A0h]
0x180027950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027955  mov     ebx, eax
0x180027957  test    eax, eax
0x180027959  js      loc_180028C7A
0x18002795f  mov     rcx, [rsp+490h+var_418]
0x180027964  lea     r9, aN; "N"
0x18002796b  xor     r8d, r8d
0x18002796e  mov     rax, [rcx]
0x180027971  lea     edx, [r8+12h]
0x180027975  mov     rax, [rax+0A0h]
0x18002797c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027981  mov     ebx, eax
0x180027983  test    eax, eax
0x180027985  js      loc_180028C7A
0x18002798b  mov     rcx, [rsp+490h+var_418]
0x180027990  lea     r9, word_18005C890
0x180027997  xor     r8d, r8d
0x18002799a  mov     rax, [rcx]
0x18002799d  lea     edx, [r8+13h]
0x1800279a1  mov     rax, [rax+0A0h]
0x1800279a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279ad  mov     ebx, eax
0x1800279af  test    eax, eax
0x1800279b1  js      loc_180028C7A
0x1800279b7  mov     rcx, [rsp+490h+var_418]
  ... truncated ...
```
