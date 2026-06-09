# OneCopilotRemediator::ScheduleUninstallation(uint)

- ea: `0x1800206c8`
- end: `0x180020d81`
- name: `?ScheduleUninstallation@OneCopilotRemediator@@AEAAJI@Z`
- size: `1721`
- prototype: `__int64 __fastcall(OneCopilotRemediator *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002663c`

## callees

- `0x180016148`
- `0x180017988`
- `0x1800206c8`
- `0x180020d88`
- `0x18002a3d0`
- `0x18002b00c`
- `0x1800516d4`
- `0x180053898`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b40`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020763`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180020763`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180020b02`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180020b02`
- `OLEAUT32!__imp_VariantInit` at `0x1800206fd`
- `OLEAUT32!__imp_VariantInit` at `0x180020708`
- `OLEAUT32!__imp_VariantInit` at `0x1800206fd`
- `OLEAUT32!__imp_VariantInit` at `0x180020708`
- `OLEAUT32!__imp_VariantClear` at `0x180020d47`
- `OLEAUT32!__imp_VariantClear` at `0x180020d52`
- `OLEAUT32!__imp_VariantClear` at `0x180020d47`
- `OLEAUT32!__imp_VariantClear` at `0x180020d52`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180020b14`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180020b14`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180020b36`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180020b36`

## string_xrefs

- `0x1800209fe`: `<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">\n  <RegistrationInfo>\n    <URI>\\OneCopilot\RemediateCopilot</URI>\n    <!-- Security descriptor ACL:\n        D:P               - DACL present, Protected (no inheritance from parent)\n        (A;;FA;;;SY)      - full access for Local System (SYSTEM)\n        (A;;FA;;;BA)      - full access for Built-in Administrators\n        (A;;FA;;;IU)      - full access for Interactive Users\n    -->\n    <SecurityDescriptor>D:P(A;;FA;;;S`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall OneCopilotRemediator::ScheduleUninstallation(OneCopilotRemediator *this)
{
  LONGLONG v2; // rax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  int v7; // eax
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64, VARIANTARG *, __int64 **); // rsi
  __int64 *v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  __int64 *v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64, __int64, __int64 *); // rdi
  __int64 v28; // rcx
  __int64 v29; // rax
  signed int LastError; // eax
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rax
  int v34; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  __int64 *v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME FileTime; // [rsp+90h] [rbp-70h] BYREF
  __int64 v47; // [rsp+98h] [rbp-68h] BYREF
  __int64 v48; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v50[2]; // [rsp+B0h] [rbp-50h] BYREF
  VARIANTARG v51; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v52; // [rsp+E0h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+F8h] [rbp-8h] BYREF
  VARIANTARG v54; // [rsp+110h] [rbp+10h] BYREF
  VARIANTARG v55; // [rsp+130h] [rbp+30h] BYREF
  VARIANTARG v56; // [rsp+150h] [rbp+50h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+170h] [rbp+70h] BYREF
  wchar_t Buffer[64]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  VariantInit(&pvarg);
  VariantInit(&v52);
  wil::make_bstr(v50, L"D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;FA;;;IU)");
  v52.vt = 8;
  v2 = v50[0];
  v50[0] = 0;
  v52.llVal = v2;
  if ( *((_QWORD *)this + 9) )
    goto LABEL_7;
  FileTime = 0;
  CoCreateInstance(
    &GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd,
    0,
    1u,
    &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
    (LPVOID *)&FileTime);
  wil::com_ptr_t<ITaskService,wil::err_returncode_policy>::operator=((char *)this + 72, &FileTime);
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&FileTime);
  v3 = *((_QWORD *)this + 9);
  if ( v3 )
  {
    v56 = pvarg;
    v54 = pvarg;
    v55 = pvarg;
    v51 = pvarg;
    ppv = (LPVOID *)&v56;
    v7 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v3 + 80LL))(
           v3,
           &v51,
           &v55,
           &v54);
    v4 = v7;
    if ( v7 < 0 )
    {
      v5 = (unsigned int)v7;
      v6 = 354;
      goto LABEL_6;
    }
LABEL_7:
    wil::make_bstr(&v40, L"\\OneCopilot");
    v38 = 0;
    v8 = (__int64 *)*((_QWORD *)this + 9);
    v9 = *v8;
    v38 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, __int64 **))(v9 + 56))(v8, v40, &v38) < 0 || !v38 )
    {
      v47 = 0;
      v10 = (__int64 *)*((_QWORD *)this + 9);
      v11 = *v10;
      v47 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v11 + 56))(v10, 0, &v47);
      v4 = v12;
      if ( v12 < 0 )
      {
        v13 = 364;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
          (const char *)(unsigned int)v12,
          (int)ppv);
        wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v47);
LABEL_12:
        wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v38);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
        goto LABEL_48;
      }
      v14 = v47;
      v15 = *(__int64 (__fastcall **)(__int64, __int64, VARIANTARG *, __int64 **))(*(_QWORD *)v47 + 88LL);
      v16 = v38;
      v38 = 0;
      if ( v16 )
        (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
      v51 = v52;
      v12 = v15(v14, v40, &v51, &v38);
      v4 = v12;
      if ( v12 < 0 )
      {
        v13 = 365;
        goto LABEL_11;
      }
      wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v47);
    }
    wil::make_bstr(&v41, L"\\RemediateCopilot");
    v43 = 0;
    v17 = *v38;
    v43 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, __int64 *))(v17 + 104))(v38, v41, &v43) >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(*v38 + 120))(v38, v41, 0);
      v4 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x176,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
          (const char *)(unsigned int)v18,
          (int)ppv);
LABEL_21:
        wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v43);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
        goto LABEL_12;
      }
    }
    v39 = 0;
    v19 = (__int64 *)*((_QWORD *)this + 9);
    v20 = *v19;
    v39 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v20 + 72))(v19, 0, &v39);
    v4 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17A,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
        (const char *)(unsigned int)v21,
        (int)ppv);
LABEL_24:
      wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v39);
      goto LABEL_21;
    }
    wil::make_bstr(
      &v45,
      L"<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\">\n"
       "  <RegistrationInfo>\n"
       "    <URI>\\\\OneCopilot\\RemediateCopilot</URI>\n"
       "    <!-- Security descriptor ACL:\n"
       "        D:P               - DACL present, Protected (no inheritance from parent)\n"
       "        (A;;FA;;;SY)      - full access for Local System (SYSTEM)\n"
       "        (A;;FA;;;BA)      - full access for Built-in Administrators\n"
       "        (A;;FA;;;IU)      - full access for Interactive Users\n"
       "    -->\n"
       "    <SecurityDescriptor>D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;FA;;;IU)</SecurityDescriptor>\n"
       "    <Version>1.0</Version>\n"
       "  </RegistrationInfo>\n"
       "  <Triggers>\n"
       "  </Triggers>\n"
       "  <Principals>\n"
       "    <!-- Only run this for the currently logged-in user. -->\n"
       "    <Principal id=\"CurrentUser\">\n"
       "      <LogonType>InteractiveToken</LogonType>\n"
       "      <RunLevel>LeastPrivilege</RunLevel>\n"
       "    </Principal>\n"
       "  </Principals>\n"
       "  <Settings>\n"
       "    <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n"
       "    <MultipleInstancesPolicy>IgnoreNew</MultipleInstancesPolicy>\n"
       "    <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n"
       "    <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>\n"
       "    <AllowHardTerminate>true</AllowHardTerminate>\n"
       "    <!--\n"
       "         Allow the task to be run even after it's been missed.\n"
       "         This is critical for our task, which has a time trigger,\n"
       "         but is only allowed to run when the user is idle.\n"
       "    -->\n"
       "    <StartWhenAvailable>true</StartWhenAvailable>\n"
       "    <RunOnlyIfNetworkAvailable>false</RunOnlyIfNetworkAvailable>\n"
       "    <AllowStartOnDemand>true</AllowStartOnDemand>\n"
       "    <Enabled>true</Enabled>\n"
       "    <Hidden>false</Hidden>\n"
       "    <RunOnlyIfIdle>true</RunOnlyIfIdle>\n"
       "    <WakeToRun>false</WakeToRun>\n"
       "    <ExecutionTimeLimit>PT72H</ExecutionTimeLimit>\n"
       "    <Priority>7</Priority>\n"
       "  </Settings>\n"
       "  <Actions Context=\"CurrentUser\">\n"
       "    <ComHandler>\n"
       "      <ClassId>{468e02a7-fb25-41a0-8c60-351401a388e9}</ClassId>\n"
       "    </ComHandler>\n"
       "  </Actions>\n"
       "</Task>\n");
    v22 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v39 + 160))(v39, v45);
    v4 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17D,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
        (const char *)(unsigned int)v22,
        (int)ppv);
LABEL_27:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v45);
      goto LABEL_24;
    }
    v42 = 0;
    v44 = 0;
    v23 = *v39;
    v44 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v23 + 72))(v39, &v44);
    v4 = v24;
    if ( v24 < 0 )
    {
      v25 = 386;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
        (const char *)(unsigned int)v24,
        (int)ppv);
LABEL_31:
      wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v44);
      wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v42);
      goto LABEL_27;
    }
    v26 = v44;
    v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v44 + 80LL);
    v28 = v42;
    v42 = 0;
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v24 = v27(v26, 1, &v42);
    v4 = v24;
    if ( v24 < 0 )
    {
      v25 = 387;
      goto LABEL_30;
    }
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    FileTime = 0;
    SystemTimeToFileTime(&SystemTime, &FileTime);
    v29 = *(_QWORD *)&FileTime + 600000000LL;
    FileTime.dwLowDateTime += 600000000;
    FileTime.dwHighDateTime = HIDWORD(v29);
    if ( !FileTimeToSystemTime(&FileTime, &SystemTime) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_31;
    }
    ppva = SystemTime.wMonth;
    swprintf_s(Buffer, 0x40u, L"%04u-%02u-%02uT%02u:%02u:%02uZ", SystemTime.wYear);
    wil::make_bstr(&v48, Buffer);
    v31 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 120LL))(v42, v48);
    v4 = v31;
    if ( v31 >= 0 )
    {
      v31 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 152LL))(v42, 0xFFFFFFFFLL);
      v4 = v31;
      if ( v31 >= 0 )
      {
        v49 = 0;
        v33 = *v38;
        v49 = 0;
        v51 = pvarg;
        v55 = pvarg;
        v54 = pvarg;
        v34 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *, __int64))(v33 + 136))(v38, v41, v39, 2);
        v4 = v34;
        if ( v34 >= 0 )
        {
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v49);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v44);
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v42);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v45);
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v39);
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v43);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v38);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
          v4 = 0;
          goto LABEL_48;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B5,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
          (const char *)(unsigned int)v34,
          (int)&v54);
        wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v49);
        goto LABEL_42;
      }
      v32 = 425;
    }
    else
    {
      v32 = 424;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
      (const char *)(unsigned int)v31,
      ppva);
LABEL_42:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v48);
    goto LABEL_31;
  }
  v4 = -2147024882;
  v5 = 2147942414LL;
  v6 = 353;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"shell\\onecore\\desktopshellext\\lib\\onecopilotremediator.cpp",
    (const char *)v5,
    (int)ppv);
LABEL_48:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v50);
  VariantClear(&v52);
  VariantClear(&pvarg);
  return v4;
}

```

## disassembly

```asm
0x1800206c8  mov     [rsp-8+arg_8], rbx
0x1800206cd  mov     [rsp-8+arg_10], rsi
0x1800206d2  push    rbp
0x1800206d3  push    rdi
0x1800206d4  push    r14
0x1800206d6  lea     rbp, [rsp-110h]
0x1800206de  sub     rsp, 210h
0x1800206e5  mov     rax, cs:__security_cookie
0x1800206ec  xor     rax, rsp
0x1800206ef  mov     [rbp+120h+var_20], rax
0x1800206f6  mov     rdi, rcx
0x1800206f9  lea     rcx, [rbp+120h+pvarg]; pvarg
0x1800206fd  call    cs:__imp_VariantInit
0x180020703  nop
0x180020704  lea     rcx, [rbp+120h+var_140]; pvarg
0x180020708  call    cs:__imp_VariantInit
0x18002070e  nop
0x18002070f  lea     rdx, aDPAFaSyAFaBaAF; "D:P(A;;FA;;;SY)(A;;FA;;;BA)(A;;FA;;;IU)"
0x180020716  lea     rcx, [rbp+120h+var_170]
0x18002071a  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002071f  nop
0x180020720  mov     eax, 8
0x180020725  mov     word ptr [rbp+120h+var_140], ax
0x180020729  mov     rax, [rbp+120h+var_170]
0x18002072d  xor     r14d, r14d
0x180020730  mov     [rbp+120h+var_170], r14
0x180020734  mov     qword ptr [rbp+120h+var_140+8], rax
0x180020738  cmp     [rdi+48h], r14
0x18002073c  jnz     loc_18002080B
0x180020742  mov     qword ptr [rbp+120h+FileTime.dwLowDateTime], r14
0x180020746  lea     rax, [rbp+120h+FileTime]
0x18002074a  mov     [rsp+220h+ppv], rax; ppv
0x18002074f  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180020756  xor     edx, edx; pUnkOuter
0x180020758  lea     r8d, [r14+1]; dwClsContext
0x18002075c  lea     rcx, _GUID_0f87369f_a4e5_4cfc_bd3e_73e6154572dd; rclsid
0x180020763  call    cs:__imp_CoCreateInstance
0x180020769  lea     rdx, [rbp+120h+FileTime]
0x18002076d  lea     rcx, [rdi+48h]
0x180020771  call    ??4?$com_ptr_t@UITaskService@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<ITaskService,wil::err_returncode_policy>::operator=(wil::com_ptr_t<ITaskService,wil::err_returncode_policy> &&)
0x180020776  lea     rcx, [rbp+120h+FileTime]
0x18002077a  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18002077f  mov     rcx, [rdi+48h]
0x180020783  test    rcx, rcx
0x180020786  jnz     short loc_180020797
0x180020788  mov     ebx, 8007000Eh
0x18002078d  mov     r9d, ebx
0x180020790  mov     edx, 161h
0x180020795  jmp     short loc_1800207F3
0x180020797  movups  xmm1, xmmword ptr [rbp+120h+pvarg]
0x18002079b  movsd   xmm0, qword ptr [rbp+120h+pvarg+10h]
0x1800207a0  movaps  xmmword ptr [rbp+120h+var_D0], xmm1
0x1800207a4  movsd   [rbp+120h+var_C0], xmm0
0x1800207a9  movaps  xmmword ptr [rbp+120h+var_110], xmm1
0x1800207ad  movsd   [rbp+120h+var_100], xmm0
0x1800207b2  movaps  [rbp+120h+var_F0], xmm1
0x1800207b6  movsd   [rbp+120h+var_E0], xmm0
0x1800207bb  movaps  [rbp+120h+var_160], xmm1
0x1800207bf  movsd   [rbp+120h+var_150], xmm0
0x1800207c4  mov     rax, [rcx]
0x1800207c7  lea     rdx, [rbp+120h+var_D0]
0x1800207cb  mov     [rsp+220h+ppv], rdx; int
0x1800207d0  lea     r9, [rbp+120h+var_110]
0x1800207d4  lea     r8, [rbp+120h+var_F0]
0x1800207d8  lea     rdx, [rbp+120h+var_160]
0x1800207dc  mov     rax, [rax+50h]
0x1800207e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207e5  mov     ebx, eax
0x1800207e7  test    eax, eax
0x1800207e9  jns     short loc_18002080B
0x1800207eb  mov     r9d, eax; char *
0x1800207ee  mov     edx, 162h; void *
0x1800207f3  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x1800207fa  mov     rcx, [rbp+128h]; this
0x180020801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020806  jmp     loc_180020D39
0x18002080b  lea     rdx, aOnecopilot; "\\OneCopilot"
0x180020812  lea     rcx, [rsp+220h+var_1C0]
0x180020817  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002081c  nop
0x18002081d  mov     [rsp+220h+var_1D0], r14
0x180020822  mov     rcx, [rdi+48h]
0x180020826  mov     rax, [rcx]
0x180020829  mov     [rsp+220h+var_1D0], r14
0x18002082e  lea     r8, [rsp+220h+var_1D0]
0x180020833  mov     rdx, [rsp+220h+var_1C0]
0x180020838  mov     rax, [rax+38h]
0x18002083c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020841  test    eax, eax
0x180020843  js      short loc_180020850
0x180020845  cmp     [rsp+220h+var_1D0], r14
0x18002084a  jnz     loc_18002091F
0x180020850  mov     [rbp+120h+var_188], r14
0x180020854  mov     rcx, [rdi+48h]
0x180020858  mov     rax, [rcx]
0x18002085b  mov     [rbp+120h+var_188], r14
0x18002085f  lea     r8, [rbp+120h+var_188]
0x180020863  xor     edx, edx
0x180020865  mov     rax, [rax+38h]
0x180020869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002086e  mov     ebx, eax
0x180020870  test    eax, eax
0x180020872  jns     short loc_1800208B4
0x180020874  mov     edx, 16Ch; void *
0x180020879  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x180020880  mov     r9d, eax; char *
0x180020883  mov     rcx, [rbp+128h]; this
0x18002088a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002088f  nop
0x180020890  lea     rcx, [rbp+120h+var_188]
0x180020894  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180020899  nop
0x18002089a  lea     rcx, [rsp+220h+var_1D0]
0x18002089f  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x1800208a4  nop
0x1800208a5  lea     rcx, [rsp+220h+var_1C0]
0x1800208aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800208af  jmp     loc_180020D39
0x1800208b4  mov     rbx, [rbp+120h+var_188]
0x1800208b8  mov     rax, [rbx]
0x1800208bb  mov     rsi, [rax+58h]
0x1800208bf  mov     rcx, [rsp+220h+var_1D0]
0x1800208c4  mov     [rsp+220h+var_1D0], r14
0x1800208c9  test    rcx, rcx
0x1800208cc  jz      short loc_1800208DB
0x1800208ce  mov     rax, [rcx]
0x1800208d1  mov     rax, [rax+10h]
0x1800208d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208da  nop
0x1800208db  movups  xmm0, xmmword ptr [rbp+120h+var_140]
0x1800208df  movaps  [rbp+120h+var_160], xmm0
0x1800208e3  movsd   xmm1, qword ptr [rbp+120h+var_140+10h]
0x1800208e8  movsd   [rbp+120h+var_150], xmm1
0x1800208ed  lea     r9, [rsp+220h+var_1D0]
0x1800208f2  lea     r8, [rbp+120h+var_160]
0x1800208f6  mov     rdx, [rsp+220h+var_1C0]
0x1800208fb  mov     rcx, rbx
0x1800208fe  mov     rax, rsi
0x180020901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020906  mov     ebx, eax
0x180020908  test    eax, eax
0x18002090a  jns     short loc_180020916
0x18002090c  mov     edx, 16Dh
0x180020911  jmp     loc_180020879
0x180020916  lea     rcx, [rbp+120h+var_188]
0x18002091a  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18002091f  lea     rdx, aRemediatecopil; "\\RemediateCopilot"
0x180020926  lea     rcx, [rsp+220h+var_1B8]
0x18002092b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180020930  nop
0x180020931  mov     [rsp+220h+var_1A8], r14
0x180020936  mov     rcx, [rsp+220h+var_1D0]
0x18002093b  mov     rax, [rcx]
0x18002093e  mov     [rsp+220h+var_1A8], r14
0x180020943  lea     r8, [rsp+220h+var_1A8]
0x180020948  mov     rdx, [rsp+220h+var_1B8]
0x18002094d  mov     rax, [rax+68h]
0x180020951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020956  test    eax, eax
0x180020958  js      short loc_1800209AF
0x18002095a  mov     rcx, [rsp+220h+var_1D0]
0x18002095f  mov     rax, [rcx]
0x180020962  xor     r8d, r8d
0x180020965  mov     rdx, [rsp+220h+var_1B8]
0x18002096a  mov     rax, [rax+78h]
0x18002096e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020973  mov     ebx, eax
0x180020975  test    eax, eax
0x180020977  jns     short loc_1800209AF
0x180020979  mov     rcx, [rbp+128h]; this
0x180020980  mov     r9d, eax; char *
0x180020983  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x18002098a  mov     edx, 176h; void *
0x18002098f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020994  nop
0x180020995  lea     rcx, [rsp+220h+var_1A8]
0x18002099a  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18002099f  nop
0x1800209a0  lea     rcx, [rsp+220h+var_1B8]
0x1800209a5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800209aa  jmp     loc_18002089A
0x1800209af  mov     [rsp+220h+var_1C8], r14
0x1800209b4  mov     rcx, [rdi+48h]
0x1800209b8  mov     rax, [rcx]
0x1800209bb  mov     [rsp+220h+var_1C8], r14
0x1800209c0  lea     r8, [rsp+220h+var_1C8]
0x1800209c5  xor     edx, edx
0x1800209c7  mov     rax, [rax+48h]
0x1800209cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209d0  mov     ebx, eax
0x1800209d2  test    eax, eax
0x1800209d4  jns     short loc_1800209FE
0x1800209d6  mov     rcx, [rbp+128h]; this
0x1800209dd  mov     r9d, eax; char *
0x1800209e0  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x1800209e7  mov     edx, 17Ah; void *
0x1800209ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800209f1  nop
0x1800209f2  lea     rcx, [rsp+220h+var_1C8]
0x1800209f7  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x1800209fc  jmp     short loc_180020995
0x1800209fe  lea     rdx, aTaskXmlnsHttpS; "<Task xmlns=\"http://schemas.microsoft."...
0x180020a05  lea     rcx, [rbp+120h+var_198]
0x180020a09  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x180020a0e  nop
0x180020a0f  mov     rcx, [rsp+220h+var_1C8]
0x180020a14  mov     rax, [rcx]
0x180020a17  mov     rdx, [rbp+120h+var_198]
0x180020a1b  mov     rax, [rax+0A0h]
0x180020a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a27  mov     ebx, eax
0x180020a29  test    eax, eax
0x180020a2b  jns     short loc_180020A54
0x180020a2d  mov     rcx, [rbp+128h]; this
0x180020a34  mov     r9d, eax; char *
0x180020a37  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x180020a3e  mov     edx, 17Dh; void *
0x180020a43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a48  nop
0x180020a49  lea     rcx, [rbp+120h+var_198]
0x180020a4d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020a52  jmp     short loc_1800209F2
0x180020a54  mov     [rsp+220h+var_1B0], r14
0x180020a59  mov     [rbp+120h+var_1A0], r14
0x180020a5d  mov     rcx, [rsp+220h+var_1C8]
0x180020a62  mov     rax, [rcx]
0x180020a65  mov     [rbp+120h+var_1A0], r14
0x180020a69  lea     rdx, [rbp+120h+var_1A0]
0x180020a6d  mov     rax, [rax+48h]
0x180020a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a76  mov     ebx, eax
0x180020a78  test    eax, eax
0x180020a7a  jns     short loc_180020AAE
0x180020a7c  mov     edx, 182h; void *
0x180020a81  lea     r8, aShellOnecoreDe_5; "shell\\onecore\\desktopshellext\\lib\\o"...
0x180020a88  mov     r9d, eax; char *
0x180020a8b  mov     rcx, [rbp+128h]; this
0x180020a92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a97  nop
0x180020a98  lea     rcx, [rbp+120h+var_1A0]
0x180020a9c  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180020aa1  nop
0x180020aa2  lea     rcx, [rsp+220h+var_1B0]
0x180020aa7  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180020aac  jmp     short loc_180020A49
0x180020aae  mov     rbx, [rbp+120h+var_1A0]
0x180020ab2  mov     rax, [rbx]
0x180020ab5  mov     rdi, [rax+50h]
0x180020ab9  mov     rcx, [rsp+220h+var_1B0]
0x180020abe  mov     [rsp+220h+var_1B0], r14
0x180020ac3  test    rcx, rcx
0x180020ac6  jz      short loc_180020AD5
0x180020ac8  mov     r8, [rcx]
0x180020acb  mov     rax, [r8+10h]
0x180020acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ad4  nop
0x180020ad5  lea     r8, [rsp+220h+var_1B0]
0x180020ada  mov     edx, 1
0x180020adf  mov     rcx, rbx
0x180020ae2  mov     rax, rdi
0x180020ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aea  mov     ebx, eax
0x180020aec  test    eax, eax
0x180020aee  jns     short loc_180020AF7
0x180020af0  mov     edx, 183h
0x180020af5  jmp     short loc_180020A81
0x180020af7  xorps   xmm0, xmm0
0x180020afa  movups  xmmword ptr [rbp+120h+SystemTime.wYear], xmm0
0x180020afe  lea     rcx, [rbp+120h+SystemTime]; lpSystemTime
0x180020b02  call    cs:__imp_GetSystemTime
0x180020b08  mov     qword ptr [rbp+120h+FileTime.dwLowDateTime], r14
0x180020b0c  lea     rdx, [rbp+120h+FileTime]; lpFileTime
0x180020b10  lea     rcx, [rbp+120h+SystemTime]; lpSystemTime
0x180020b14  call    cs:__imp_SystemTimeToFileTime
0x180020b1a  mov     rax, qword ptr [rbp+120h+FileTime.dwLowDateTime]
0x180020b1e  add     rax, 23C34600h
0x180020b24  mov     [rbp+120h+FileTime.dwLowDateTime], eax
0x180020b27  shr     rax, 20h
0x180020b2b  mov     [rbp+120h+FileTime.dwHighDateTime], eax
0x180020b2e  lea     rdx, [rbp+120h+SystemTime]; lpSystemTime
0x180020b32  lea     rcx, [rbp+120h+FileTime]; lpFileTime
0x180020b36  call    cs:__imp_FileTimeToSystemTime
0x180020b3c  test    eax, eax
0x180020b3e  jnz     short loc_180020B5E
0x180020b40  call    cs:__imp_GetLastError
0x180020b46  mov     ebx, eax
0x180020b48  test    eax, eax
0x180020b4a  jle     loc_180020A98
0x180020b50  movzx   ebx, ax
0x180020b53  or      ebx, 80070000h
0x180020b59  jmp     loc_180020A98
0x180020b5e  movzx   eax, [rbp+120h+SystemTime.wSecond]
0x180020b62  movzx   ecx, [rbp+120h+SystemTime.wMinute]
0x180020b66  movzx   edx, [rbp+120h+SystemTime.wHour]
0x180020b6a  movzx   r8d, [rbp+120h+SystemTime.wDay]
0x180020b6f  movzx   r10d, [rbp+120h+SystemTime.wMonth]
0x180020b74  movzx   r9d, [rbp+120h+SystemTime.wYear]
0x180020b79  mov     dword ptr [rsp+220h+var_1E0], eax
0x180020b7d  mov     dword ptr [rsp+220h+var_1E8], ecx
0x180020b81  mov     [rsp+220h+var_1F0], edx
  ... truncated ...
```
