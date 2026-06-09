# MdmLogCollector::CollectDiagnosticsFrameworkInfo(void)

- ea: `0x18010afa8`
- end: `0x18010b874`
- name: `?CollectDiagnosticsFrameworkInfo@MdmLogCollector@@AEAAJXZ`
- size: `2252`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010ba4c`

## callees

- `0x180019080`
- `0x18001989c`
- `0x18001a030`
- `0x18001a130`
- `0x1800e688c`
- `0x1800e7c78`
- `0x1800eb1ac`
- `0x1800ed44c`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x1800fa50c`
- `0x180106464`
- `0x180109140`
- `0x1801091bc`
- `0x180109d50`
- `0x18010afa8`
- `0x18010f60c`
- `0x180110d34`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010b437`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010b437`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010b470`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010b470`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010b6e5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010b6e5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010b544`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010b629`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010b544`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010b629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010b516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010b5fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010b516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010b5fc`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18010b03f`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18010b03f`

## string_xrefs

- `0x18010b120`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b1af`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b20f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b294`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b31b`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b3a6`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b496`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b562`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b645`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b701`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b81e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010b413`: `\DiagnosticsFrameworkData.json`
- `0x18010b0cc`: `CommercialOOBE`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall MdmLogCollector::CollectDiagnosticsFrameworkInfo(MdmLogCollector *this)
{
  int v2; // ebx
  HANDLE v3; // rdi
  __int64 (__fastcall *v4)(HANDLE, __int64, __int64 *); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 **); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rcx
  int TemporaryOutputPath; // eax
  unsigned int v21; // ebx
  const WCHAR *v22; // rax
  const WCHAR *v23; // rax
  HANDLE FileW; // rbx
  const char *v25; // r9
  unsigned int LastError; // ebx
  const WCHAR *StringRawBuffer; // rax
  unsigned int v28; // eax
  const char *v29; // r9
  int v30; // esi
  unsigned int v31; // ebx
  CHAR *v32; // rdi
  const WCHAR *v33; // rax
  int v34; // eax
  const char *v35; // r9
  unsigned int v36; // ebx
  const char *v37; // r9
  unsigned int v38; // ebx
  __int64 v39; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-E8h]
  char v41[8]; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE v42; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v43; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+58h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A8h] BYREF
  __int64 *v46; // [rsp+68h] [rbp-A0h] BYREF
  HANDLE v47; // [rsp+70h] [rbp-98h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+78h] [rbp-90h] BYREF
  CHAR *v49; // [rsp+80h] [rbp-88h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-80h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-68h]
  HSTRING_HEADER v52; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v53; // [rsp+C0h] [rbp-48h]
  _BYTE v54[32]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  wprintf(L"Collecting diagnostics information. This may take up to one minute...\n");
  v51 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"ModernDeployment.Autopilot.Core.DiagnosticAnalysisManager",
    0x3Au,
    0x39u);
  v42 = 0;
  v47 = 0;
  v2 = RoActivateInstance(v51, &v47);
  if ( v2 < 0 )
    goto LABEL_28;
  if ( !memcmp_0(&GUID_9a6c136a_c65b_4410_aca3_4122aebeb808, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
  {
    v42 = v47;
    goto LABEL_5;
  }
  v2 = (**(__int64 (__fastcall ***)(HANDLE, GUID *, HANDLE *))v47)(
         v47,
         &GUID_9a6c136a_c65b_4410_aca3_4122aebeb808,
         &v42);
  (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v47 + 16LL))(v47);
  if ( v2 < 0 )
  {
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x82D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)v2,
      dwCreationDisposition);
    v51 = 0;
    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
    return (unsigned int)v2;
  }
LABEL_5:
  v43 = 0;
  v53 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v52, L"CommercialOOBE", 0xFu, 0xEu);
  v3 = v42;
  v4 = *(__int64 (__fastcall **)(HANDLE, __int64, __int64 *))(*(_QWORD *)v42 + 48LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
  v5 = v4(v3, v53, &v43);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v44 = 0;
    v41[0] = 0;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
    v8 = v43;
    v11 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(
            v43,
            v9,
            v10,
            v41);
    if ( v11 >= 0 )
      v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 80LL))(v8, &v44);
    if ( v11 >= 0 )
    {
      if ( v41[0] )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x83A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)0x800705B4LL,
          dwCreationDisposition);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
        v53 = 0;
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
        v51 = 0;
        wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
        return 2147943860LL;
      }
      else
      {
        v46 = 0;
        v12 = v44;
        v13 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v44 + 48LL);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
        v14 = v13(v12, &v46);
        v15 = v14;
        if ( v14 >= 0 )
        {
          string = 0;
          v16 = *v46;
          string = 0;
          v17 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING *))(v16 + 48))(v46, 0, &string);
          v18 = v17;
          if ( v17 >= 0 )
          {
            std::wstring::wstring(v54);
            TemporaryOutputPath = MdmLogCollector::GetTemporaryOutputPath(v19, v54);
            v21 = TemporaryOutputPath;
            if ( TemporaryOutputPath >= 0 )
            {
              std::wstring::append(v54, L"\\DiagnosticsFrameworkData.json");
              v22 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
              DeleteFileW(v22);
              v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
              FileW = CreateFileW(v23, 0x10000000u, 0, 0, 2u, 0, 0);
              v47 = FileW;
              if ( FileW == (HANDLE)-1LL )
              {
                LastError = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x857,
                              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                              v25);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v47);
                std::wstring::_Tidy_deallocate(v54);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                v53 = 0;
                Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
                v51 = 0;
                wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
                return LastError;
              }
              else
              {
                StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                v28 = WideCharToMultiByte(0xFDE9u, 0, StringRawBuffer, -1, 0, 0, 0, 0);
                v30 = v28;
                if ( v28 )
                {
                  v32 = (CHAR *)operator new[](v28, (const struct std::nothrow_t *)std::nothrow);
                  v49 = v32;
                  v33 = WindowsGetStringRawBuffer(string, 0);
                  v34 = WideCharToMultiByte(0xFDE9u, 0, v33, -1, v32, v30, 0, 0);
                  if ( v34 )
                  {
                    NumberOfBytesWritten = 0;
                    if ( WriteFile(FileW, v32, v34 - 1, &NumberOfBytesWritten, 0) )
                    {
                      v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v54);
                      MdmLogCollector::AddEntry(v39, (char *)this + 32);
                      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v49);
                      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v47);
                      std::wstring::_Tidy_deallocate(v54);
                      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                      v53 = 0;
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
                      v51 = 0;
                      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
                      return 0;
                    }
                    else
                    {
                      v38 = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0x868,
                              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                              v37);
                      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v49);
                      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v47);
                      std::wstring::_Tidy_deallocate(v54);
                      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                      v53 = 0;
                      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
                      v51 = 0;
                      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
                      return v38;
                    }
                  }
                  else
                  {
                    v36 = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0x861,
                            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                            v35);
                    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v49);
                    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v47);
                    std::wstring::_Tidy_deallocate(v54);
                    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                    v53 = 0;
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
                    v51 = 0;
                    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
                    return v36;
                  }
                }
                else
                {
                  v31 = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x85B,
                          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                          v29);
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v47);
                  std::wstring::_Tidy_deallocate(v54);
                  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                  v53 = 0;
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
                  v51 = 0;
                  wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
                  return v31;
                }
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x847,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                (const char *)(unsigned int)TemporaryOutputPath,
                dwCreationDisposition);
              std::wstring::_Tidy_deallocate(v54);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
              v53 = 0;
              Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
              v51 = 0;
              wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
              return v21;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x842,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
              (const char *)(unsigned int)v17,
              dwCreationDisposition);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
            v53 = 0;
            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
            v51 = 0;
            wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
            return v18;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x83E,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
            (const char *)(unsigned int)v14,
            dwCreationDisposition);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v46);
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
          v53 = 0;
          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
          v51 = 0;
          wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
          return v15;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x839,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v11,
        dwCreationDisposition);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
      v53 = 0;
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
      v51 = 0;
      wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
      return (unsigned int)v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x832,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)v5,
      dwCreationDisposition);
    v53 = 0;
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
    v51 = 0;
    wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v42);
    return v6;
  }
}

```

## disassembly

```asm
0x18010afa8  mov     [rsp+arg_8], rbx
0x18010afad  mov     [rsp+arg_10], rsi
0x18010afb2  push    rdi
0x18010afb3  push    r14
0x18010afb5  push    r15
0x18010afb7  sub     rsp, 0F0h
0x18010afbe  mov     rax, cs:__security_cookie
0x18010afc5  xor     rax, rsp
0x18010afc8  mov     [rsp+108h+var_20], rax
0x18010afd0  mov     r14, rcx
0x18010afd3  lea     rcx, aCollectingDiag; "Collecting diagnostics information. Thi"...
0x18010afda  call    wprintf
0x18010afdf  xor     r15d, r15d
0x18010afe2  mov     [rsp+108h+var_C0], r15
0x18010afe7  mov     [rsp+108h+var_68], r15
0x18010afef  lea     r9d, [r15+39h]; unsigned int
0x18010aff3  lea     r8d, [r15+3Ah]; unsigned int
0x18010aff7  lea     rdx, ?RuntimeClass_ModernDeployment_Autopilot_Core_DiagnosticAnalysisManager@@3QBGB; "ModernDeployment.Autopilot.Core.Diagnos"...
0x18010affe  lea     rcx, [rsp+108h+hstringHeader]; hstringHeader
0x18010b006  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18010b00b  nop
0x18010b00c  mov     rcx, [rsp+108h+var_C0]
0x18010b011  mov     [rsp+108h+var_C0], r15
0x18010b016  test    rcx, rcx
0x18010b019  jz      short loc_18010B028
0x18010b01b  mov     rax, [rcx]
0x18010b01e  mov     rax, [rax+10h]
0x18010b022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b027  nop
0x18010b028  mov     [rsp+108h+var_C0], r15
0x18010b02d  mov     [rsp+108h+var_98], r15
0x18010b032  lea     rdx, [rsp+108h+var_98]
0x18010b037  mov     rcx, [rsp+108h+var_68]
0x18010b03f  call    cs:__imp_RoActivateInstance
0x18010b046  nop     dword ptr [rax+rax+00h]
0x18010b04b  mov     ebx, eax
0x18010b04d  test    eax, eax
0x18010b04f  js      loc_18010B813
0x18010b055  mov     r8d, 10h; Size
0x18010b05b  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18010b062  lea     rcx, _GUID_9a6c136a_c65b_4410_aca3_4122aebeb808; Buf1
0x18010b069  call    memcmp_0
0x18010b06e  test    eax, eax
0x18010b070  jnz     short loc_18010B07E
0x18010b072  mov     rax, [rsp+108h+var_98]
0x18010b077  mov     [rsp+108h+var_C0], rax
0x18010b07c  jmp     short loc_18010B0B5
0x18010b07e  mov     rcx, [rsp+108h+var_98]
0x18010b083  mov     rax, [rcx]
0x18010b086  lea     r8, [rsp+108h+var_C0]
0x18010b08b  lea     rdx, _GUID_9a6c136a_c65b_4410_aca3_4122aebeb808
0x18010b092  mov     rax, [rax]
0x18010b095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b09a  mov     ebx, eax
0x18010b09c  mov     rcx, [rsp+108h+var_98]
0x18010b0a1  mov     rax, [rcx]
0x18010b0a4  mov     rax, [rax+10h]
0x18010b0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b0ad  test    ebx, ebx
0x18010b0af  js      loc_18010B813
0x18010b0b5  mov     [rsp+108h+var_B8], r15
0x18010b0ba  mov     [rsp+108h+var_48], r15
0x18010b0c2  mov     r9d, 0Eh; unsigned int
0x18010b0c8  lea     r8d, [r9+1]; unsigned int
0x18010b0cc  lea     rdx, sourceString; "CommercialOOBE"
0x18010b0d3  lea     rcx, [rsp+108h+var_60]; hstringHeader
0x18010b0db  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18010b0e0  nop
0x18010b0e1  mov     rdi, [rsp+108h+var_C0]
0x18010b0e6  mov     rax, [rdi]
0x18010b0e9  mov     rbx, [rax+30h]
0x18010b0ed  lea     rcx, [rsp+108h+var_B8]
0x18010b0f2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b0f7  lea     r8, [rsp+108h+var_B8]
0x18010b0fc  mov     rdx, [rsp+108h+var_48]
0x18010b104  mov     rcx, rdi
0x18010b107  mov     rax, rbx
0x18010b10a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b10f  mov     ebx, eax
0x18010b111  test    eax, eax
0x18010b113  jns     short loc_18010B15E
0x18010b115  mov     rcx, [rsp+108h]; this
0x18010b11d  mov     r9d, eax; char *
0x18010b120  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b127  mov     edx, 832h; void *
0x18010b12c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b131  nop
0x18010b132  mov     [rsp+108h+var_48], r15
0x18010b13a  lea     rcx, [rsp+108h+var_B8]
0x18010b13f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b144  nop
0x18010b145  mov     [rsp+108h+var_68], r15
0x18010b14d  lea     rcx, [rsp+108h+var_C0]
0x18010b152  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010b157  mov     eax, ebx
0x18010b159  jmp     loc_18010B84A
0x18010b15e  mov     [rsp+108h+var_B0], r15
0x18010b163  mov     [rsp+108h+var_C8], r15b
0x18010b168  lea     rcx, [rsp+108h+var_B0]
0x18010b16d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b172  mov     rdi, [rsp+108h+var_B8]
0x18010b177  lea     r9, [rsp+108h+var_C8]
0x18010b17c  mov     rcx, rdi
0x18010b17f  call    ??$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18010b184  mov     ebx, eax
0x18010b186  test    eax, eax
0x18010b188  js      short loc_18010B1A0
0x18010b18a  mov     rax, [rdi]
0x18010b18d  lea     rdx, [rsp+108h+var_B0]
0x18010b192  mov     rcx, rdi
0x18010b195  mov     rax, [rax+50h]
0x18010b199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b19e  mov     ebx, eax
0x18010b1a0  test    ebx, ebx
0x18010b1a2  jns     short loc_18010B1F8
0x18010b1a4  mov     rcx, [rsp+108h]; this
0x18010b1ac  mov     r9d, ebx; char *
0x18010b1af  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b1b6  mov     edx, 839h; void *
0x18010b1bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b1c0  nop
0x18010b1c1  lea     rcx, [rsp+108h+var_B0]
0x18010b1c6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b1cb  nop
0x18010b1cc  mov     [rsp+108h+var_48], r15
0x18010b1d4  lea     rcx, [rsp+108h+var_B8]
0x18010b1d9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b1de  nop
0x18010b1df  mov     [rsp+108h+var_68], r15
0x18010b1e7  lea     rcx, [rsp+108h+var_C0]
0x18010b1ec  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010b1f1  mov     eax, ebx
0x18010b1f3  jmp     loc_18010B84A
0x18010b1f8  cmp     [rsp+108h+var_C8], r15b
0x18010b1fd  jz      short loc_18010B258
0x18010b1ff  mov     rcx, [rsp+108h]; this
0x18010b207  mov     ebx, 800705B4h
0x18010b20c  mov     r9d, ebx; char *
0x18010b20f  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b216  mov     edx, 83Ah; void *
0x18010b21b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b220  nop
0x18010b221  lea     rcx, [rsp+108h+var_B0]
0x18010b226  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b22b  nop
0x18010b22c  mov     [rsp+108h+var_48], r15
0x18010b234  lea     rcx, [rsp+108h+var_B8]
0x18010b239  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b23e  nop
0x18010b23f  mov     [rsp+108h+var_68], r15
0x18010b247  lea     rcx, [rsp+108h+var_C0]
0x18010b24c  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010b251  mov     eax, ebx
0x18010b253  jmp     loc_18010B84A
0x18010b258  mov     [rsp+108h+var_A0], r15
0x18010b25d  mov     rdi, [rsp+108h+var_B0]
0x18010b262  mov     rax, [rdi]
0x18010b265  mov     rbx, [rax+30h]
0x18010b269  lea     rcx, [rsp+108h+var_A0]
0x18010b26e  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b273  lea     rdx, [rsp+108h+var_A0]
0x18010b278  mov     rcx, rdi
0x18010b27b  mov     rax, rbx
0x18010b27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b283  mov     ebx, eax
0x18010b285  test    eax, eax
0x18010b287  jns     short loc_18010B2E8
0x18010b289  mov     rcx, [rsp+108h]; this
0x18010b291  mov     r9d, eax; char *
0x18010b294  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b29b  mov     edx, 83Eh; void *
0x18010b2a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b2a5  nop
0x18010b2a6  lea     rcx, [rsp+108h+var_A0]
0x18010b2ab  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b2b0  nop
0x18010b2b1  lea     rcx, [rsp+108h+var_B0]
0x18010b2b6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b2bb  nop
0x18010b2bc  mov     [rsp+108h+var_48], r15
0x18010b2c4  lea     rcx, [rsp+108h+var_B8]
0x18010b2c9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b2ce  nop
0x18010b2cf  mov     [rsp+108h+var_68], r15
0x18010b2d7  lea     rcx, [rsp+108h+var_C0]
0x18010b2dc  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010b2e1  mov     eax, ebx
0x18010b2e3  jmp     loc_18010B84A
0x18010b2e8  mov     [rsp+108h+string], r15
0x18010b2ed  mov     rcx, [rsp+108h+var_A0]
0x18010b2f2  mov     rax, [rcx]
0x18010b2f5  mov     [rsp+108h+string], r15
0x18010b2fa  lea     r8, [rsp+108h+string]
0x18010b2ff  xor     edx, edx
0x18010b301  mov     rax, [rax+30h]
0x18010b305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010b30a  mov     ebx, eax
0x18010b30c  test    eax, eax
0x18010b30e  jns     short loc_18010B37A
0x18010b310  mov     rcx, [rsp+108h]; this
0x18010b318  mov     r9d, eax; char *
0x18010b31b  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b322  mov     edx, 842h; void *
0x18010b327  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b32c  nop
0x18010b32d  lea     rcx, [rsp+108h+string]
0x18010b332  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010b337  nop
0x18010b338  lea     rcx, [rsp+108h+var_A0]
0x18010b33d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b342  nop
0x18010b343  lea     rcx, [rsp+108h+var_B0]
0x18010b348  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b34d  nop
0x18010b34e  mov     [rsp+108h+var_48], r15
0x18010b356  lea     rcx, [rsp+108h+var_B8]
0x18010b35b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b360  nop
0x18010b361  mov     [rsp+108h+var_68], r15
0x18010b369  lea     rcx, [rsp+108h+var_C0]
0x18010b36e  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010b373  mov     eax, ebx
0x18010b375  jmp     loc_18010B84A
0x18010b37a  lea     rcx, [rsp+108h+var_40]
0x18010b382  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010b387  nop
0x18010b388  lea     rdx, [rsp+108h+var_40]
0x18010b390  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010b395  mov     ebx, eax
0x18010b397  test    eax, eax
0x18010b399  jns     short loc_18010B413
0x18010b39b  mov     rcx, [rsp+108h]; this
0x18010b3a3  mov     r9d, eax; char *
0x18010b3a6  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b3ad  mov     edx, 847h; void *
0x18010b3b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b3b7  nop
0x18010b3b8  lea     rcx, [rsp+108h+var_40]
0x18010b3c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b3c5  nop
0x18010b3c6  lea     rcx, [rsp+108h+string]
0x18010b3cb  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010b3d0  nop
0x18010b3d1  lea     rcx, [rsp+108h+var_A0]
0x18010b3d6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b3db  nop
0x18010b3dc  lea     rcx, [rsp+108h+var_B0]
0x18010b3e1  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b3e6  nop
0x18010b3e7  mov     [rsp+108h+var_48], r15
0x18010b3ef  lea     rcx, [rsp+108h+var_B8]
0x18010b3f4  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b3f9  nop
0x18010b3fa  mov     [rsp+108h+var_68], r15
0x18010b402  lea     rcx, [rsp+108h+var_C0]
0x18010b407  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010b40c  mov     eax, ebx
0x18010b40e  jmp     loc_18010B84A
0x18010b413  lea     rdx, aDiagnosticsfra; "\\DiagnosticsFrameworkData.json"
0x18010b41a  lea     rcx, [rsp+108h+var_40]
0x18010b422  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010b427  lea     rcx, [rsp+108h+var_40]
0x18010b42f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010b434  mov     rcx, rax; lpFileName
0x18010b437  call    cs:__imp_DeleteFileW
0x18010b43e  nop     dword ptr [rax+rax+00h]
0x18010b443  lea     rcx, [rsp+108h+var_40]
0x18010b44b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010b450  mov     rcx, rax; lpFileName
0x18010b453  mov     [rsp+108h+hTemplateFile], r15; hTemplateFile
0x18010b458  mov     [rsp+108h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18010b45d  mov     [rsp+108h+dwCreationDisposition], 2; dwCreationDisposition
0x18010b465  xor     r9d, r9d; lpSecurityAttributes
0x18010b468  xor     r8d, r8d; dwShareMode
0x18010b46b  mov     edx, 10000000h; dwDesiredAccess
0x18010b470  call    cs:__imp_CreateFileW
0x18010b477  nop     dword ptr [rax+rax+00h]
0x18010b47c  mov     rbx, rax
0x18010b47f  mov     [rsp+108h+var_98], rax
0x18010b484  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010b488  jnz     loc_18010B50F
0x18010b48e  mov     rcx, [rsp+108h]; this
0x18010b496  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010b49d  mov     edx, 857h; void *
0x18010b4a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010b4a7  mov     ebx, eax
0x18010b4a9  lea     rcx, [rsp+108h+var_98]
0x18010b4ae  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010b4b3  nop
0x18010b4b4  lea     rcx, [rsp+108h+var_40]
0x18010b4bc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010b4c1  nop
0x18010b4c2  lea     rcx, [rsp+108h+string]
0x18010b4c7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010b4cc  nop
0x18010b4cd  lea     rcx, [rsp+108h+var_A0]
0x18010b4d2  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010b4d7  nop
0x18010b4d8  lea     rcx, [rsp+108h+var_B0]
0x18010b4dd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
  ... truncated ...
```
