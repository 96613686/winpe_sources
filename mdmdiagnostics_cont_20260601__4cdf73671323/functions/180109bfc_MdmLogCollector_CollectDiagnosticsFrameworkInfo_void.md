# MdmLogCollector::CollectDiagnosticsFrameworkInfo(void)

- ea: `0x180109bfc`
- end: `0x18010a498`
- name: `?CollectDiagnosticsFrameworkInfo@MdmLogCollector@@AEAAJXZ`
- size: `2204`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010a670`

## callees

- `0x180019000`
- `0x18001981c`
- `0x180019fa0`
- `0x18001a0a0`
- `0x1800e66b8`
- `0x1800e7aa8`
- `0x1800ead14`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x1800f9534`
- `0x180105180`
- `0x180107e60`
- `0x180107eec`
- `0x1801089c0`
- `0x180109bfc`
- `0x18010e09c`
- `0x18010f704`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010a085`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010a085`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010a0b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010a0b8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010a30f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18010a30f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010a180`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010a259`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010a180`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010a259`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010a158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010a232`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010a158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010a232`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180109c93`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180109c93`

## string_xrefs

- `0x180109d6e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109dfd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109e5d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109ee2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109f69`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109ff4`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a0d8`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a198`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a26f`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a325`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a442`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010a061`: `\DiagnosticsFrameworkData.json`
- `0x180109d1a`: `CommercialOOBE`

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
      (void *)0x856,
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
          (void *)0x863,
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
                              (void *)0x880,
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
                              (void *)0x891,
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
                            (void *)0x88A,
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
                          (void *)0x884,
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
                (void *)0x870,
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
              (void *)0x86B,
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
            (void *)0x867,
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
        (void *)0x862,
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
      (void *)0x85B,
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
0x180109bfc  mov     [rsp+arg_8], rbx
0x180109c01  mov     [rsp+arg_10], rsi
0x180109c06  push    rdi
0x180109c07  push    r14
0x180109c09  push    r15
0x180109c0b  sub     rsp, 0F0h
0x180109c12  mov     rax, cs:__security_cookie
0x180109c19  xor     rax, rsp
0x180109c1c  mov     [rsp+108h+var_20], rax
0x180109c24  mov     r14, rcx
0x180109c27  lea     rcx, aCollectingDiag; "Collecting diagnostics information. Thi"...
0x180109c2e  call    wprintf
0x180109c33  xor     r15d, r15d
0x180109c36  mov     [rsp+108h+var_C0], r15
0x180109c3b  mov     [rsp+108h+var_68], r15
0x180109c43  lea     r9d, [r15+39h]; unsigned int
0x180109c47  lea     r8d, [r15+3Ah]; unsigned int
0x180109c4b  lea     rdx, ?RuntimeClass_ModernDeployment_Autopilot_Core_DiagnosticAnalysisManager@@3QBGB; "ModernDeployment.Autopilot.Core.Diagnos"...
0x180109c52  lea     rcx, [rsp+108h+hstringHeader]; hstringHeader
0x180109c5a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180109c5f  nop
0x180109c60  mov     rcx, [rsp+108h+var_C0]
0x180109c65  mov     [rsp+108h+var_C0], r15
0x180109c6a  test    rcx, rcx
0x180109c6d  jz      short loc_180109C7C
0x180109c6f  mov     rax, [rcx]
0x180109c72  mov     rax, [rax+10h]
0x180109c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109c7b  nop
0x180109c7c  mov     [rsp+108h+var_C0], r15
0x180109c81  mov     [rsp+108h+var_98], r15
0x180109c86  lea     rdx, [rsp+108h+var_98]
0x180109c8b  mov     rcx, [rsp+108h+var_68]
0x180109c93  call    cs:__imp_RoActivateInstance
0x180109c99  mov     ebx, eax
0x180109c9b  test    eax, eax
0x180109c9d  js      loc_18010A437
0x180109ca3  mov     r8d, 10h; Size
0x180109ca9  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180109cb0  lea     rcx, _GUID_9a6c136a_c65b_4410_aca3_4122aebeb808; Buf1
0x180109cb7  call    memcmp_0
0x180109cbc  test    eax, eax
0x180109cbe  jnz     short loc_180109CCC
0x180109cc0  mov     rax, [rsp+108h+var_98]
0x180109cc5  mov     [rsp+108h+var_C0], rax
0x180109cca  jmp     short loc_180109D03
0x180109ccc  mov     rcx, [rsp+108h+var_98]
0x180109cd1  mov     rax, [rcx]
0x180109cd4  lea     r8, [rsp+108h+var_C0]
0x180109cd9  lea     rdx, _GUID_9a6c136a_c65b_4410_aca3_4122aebeb808
0x180109ce0  mov     rax, [rax]
0x180109ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109ce8  mov     ebx, eax
0x180109cea  mov     rcx, [rsp+108h+var_98]
0x180109cef  mov     rax, [rcx]
0x180109cf2  mov     rax, [rax+10h]
0x180109cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109cfb  test    ebx, ebx
0x180109cfd  js      loc_18010A437
0x180109d03  mov     [rsp+108h+var_B8], r15
0x180109d08  mov     [rsp+108h+var_48], r15
0x180109d10  mov     r9d, 0Eh; unsigned int
0x180109d16  lea     r8d, [r9+1]; unsigned int
0x180109d1a  lea     rdx, sourceString; "CommercialOOBE"
0x180109d21  lea     rcx, [rsp+108h+var_60]; hstringHeader
0x180109d29  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180109d2e  nop
0x180109d2f  mov     rdi, [rsp+108h+var_C0]
0x180109d34  mov     rax, [rdi]
0x180109d37  mov     rbx, [rax+30h]
0x180109d3b  lea     rcx, [rsp+108h+var_B8]
0x180109d40  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109d45  lea     r8, [rsp+108h+var_B8]
0x180109d4a  mov     rdx, [rsp+108h+var_48]
0x180109d52  mov     rcx, rdi
0x180109d55  mov     rax, rbx
0x180109d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109d5d  mov     ebx, eax
0x180109d5f  test    eax, eax
0x180109d61  jns     short loc_180109DAC
0x180109d63  mov     rcx, [rsp+108h]; this
0x180109d6b  mov     r9d, eax; char *
0x180109d6e  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109d75  mov     edx, 85Bh; void *
0x180109d7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109d7f  nop
0x180109d80  mov     [rsp+108h+var_48], r15
0x180109d88  lea     rcx, [rsp+108h+var_B8]
0x180109d8d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109d92  nop
0x180109d93  mov     [rsp+108h+var_68], r15
0x180109d9b  lea     rcx, [rsp+108h+var_C0]
0x180109da0  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109da5  mov     eax, ebx
0x180109da7  jmp     loc_18010A46E
0x180109dac  mov     [rsp+108h+var_B0], r15
0x180109db1  mov     [rsp+108h+var_C8], r15b
0x180109db6  lea     rcx, [rsp+108h+var_B0]
0x180109dbb  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109dc0  mov     rdi, [rsp+108h+var_B8]
0x180109dc5  lea     r9, [rsp+108h+var_C8]
0x180109dca  mov     rcx, rdi
0x180109dcd  call    ??$WaitForCompletion@PEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperationWithProgress@PEAUIDiagnosticAnalysisResult@Core@Autopilot@ModernDeployment@@UDiagnosticAnalysisProgress@234@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *>(Windows::Foundation::IAsyncOperationWithProgress<ModernDeployment::Autopilot::Core::IDiagnosticAnalysisResult *,ModernDeployment::Autopilot::Core::DiagnosticAnalysisProgress> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180109dd2  mov     ebx, eax
0x180109dd4  test    eax, eax
0x180109dd6  js      short loc_180109DEE
0x180109dd8  mov     rax, [rdi]
0x180109ddb  lea     rdx, [rsp+108h+var_B0]
0x180109de0  mov     rcx, rdi
0x180109de3  mov     rax, [rax+50h]
0x180109de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109dec  mov     ebx, eax
0x180109dee  test    ebx, ebx
0x180109df0  jns     short loc_180109E46
0x180109df2  mov     rcx, [rsp+108h]; this
0x180109dfa  mov     r9d, ebx; char *
0x180109dfd  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109e04  mov     edx, 862h; void *
0x180109e09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109e0e  nop
0x180109e0f  lea     rcx, [rsp+108h+var_B0]
0x180109e14  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109e19  nop
0x180109e1a  mov     [rsp+108h+var_48], r15
0x180109e22  lea     rcx, [rsp+108h+var_B8]
0x180109e27  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109e2c  nop
0x180109e2d  mov     [rsp+108h+var_68], r15
0x180109e35  lea     rcx, [rsp+108h+var_C0]
0x180109e3a  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109e3f  mov     eax, ebx
0x180109e41  jmp     loc_18010A46E
0x180109e46  cmp     [rsp+108h+var_C8], r15b
0x180109e4b  jz      short loc_180109EA6
0x180109e4d  mov     rcx, [rsp+108h]; this
0x180109e55  mov     ebx, 800705B4h
0x180109e5a  mov     r9d, ebx; char *
0x180109e5d  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109e64  mov     edx, 863h; void *
0x180109e69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109e6e  nop
0x180109e6f  lea     rcx, [rsp+108h+var_B0]
0x180109e74  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109e79  nop
0x180109e7a  mov     [rsp+108h+var_48], r15
0x180109e82  lea     rcx, [rsp+108h+var_B8]
0x180109e87  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109e8c  nop
0x180109e8d  mov     [rsp+108h+var_68], r15
0x180109e95  lea     rcx, [rsp+108h+var_C0]
0x180109e9a  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109e9f  mov     eax, ebx
0x180109ea1  jmp     loc_18010A46E
0x180109ea6  mov     [rsp+108h+var_A0], r15
0x180109eab  mov     rdi, [rsp+108h+var_B0]
0x180109eb0  mov     rax, [rdi]
0x180109eb3  mov     rbx, [rax+30h]
0x180109eb7  lea     rcx, [rsp+108h+var_A0]
0x180109ebc  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109ec1  lea     rdx, [rsp+108h+var_A0]
0x180109ec6  mov     rcx, rdi
0x180109ec9  mov     rax, rbx
0x180109ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109ed1  mov     ebx, eax
0x180109ed3  test    eax, eax
0x180109ed5  jns     short loc_180109F36
0x180109ed7  mov     rcx, [rsp+108h]; this
0x180109edf  mov     r9d, eax; char *
0x180109ee2  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109ee9  mov     edx, 867h; void *
0x180109eee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109ef3  nop
0x180109ef4  lea     rcx, [rsp+108h+var_A0]
0x180109ef9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109efe  nop
0x180109eff  lea     rcx, [rsp+108h+var_B0]
0x180109f04  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109f09  nop
0x180109f0a  mov     [rsp+108h+var_48], r15
0x180109f12  lea     rcx, [rsp+108h+var_B8]
0x180109f17  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109f1c  nop
0x180109f1d  mov     [rsp+108h+var_68], r15
0x180109f25  lea     rcx, [rsp+108h+var_C0]
0x180109f2a  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109f2f  mov     eax, ebx
0x180109f31  jmp     loc_18010A46E
0x180109f36  mov     [rsp+108h+string], r15
0x180109f3b  mov     rcx, [rsp+108h+var_A0]
0x180109f40  mov     rax, [rcx]
0x180109f43  mov     [rsp+108h+string], r15
0x180109f48  lea     r8, [rsp+108h+string]
0x180109f4d  xor     edx, edx
0x180109f4f  mov     rax, [rax+30h]
0x180109f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109f58  mov     ebx, eax
0x180109f5a  test    eax, eax
0x180109f5c  jns     short loc_180109FC8
0x180109f5e  mov     rcx, [rsp+108h]; this
0x180109f66  mov     r9d, eax; char *
0x180109f69  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109f70  mov     edx, 86Bh; void *
0x180109f75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109f7a  nop
0x180109f7b  lea     rcx, [rsp+108h+string]
0x180109f80  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180109f85  nop
0x180109f86  lea     rcx, [rsp+108h+var_A0]
0x180109f8b  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109f90  nop
0x180109f91  lea     rcx, [rsp+108h+var_B0]
0x180109f96  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109f9b  nop
0x180109f9c  mov     [rsp+108h+var_48], r15
0x180109fa4  lea     rcx, [rsp+108h+var_B8]
0x180109fa9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180109fae  nop
0x180109faf  mov     [rsp+108h+var_68], r15
0x180109fb7  lea     rcx, [rsp+108h+var_C0]
0x180109fbc  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109fc1  mov     eax, ebx
0x180109fc3  jmp     loc_18010A46E
0x180109fc8  lea     rcx, [rsp+108h+var_40]
0x180109fd0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180109fd5  nop
0x180109fd6  lea     rdx, [rsp+108h+var_40]
0x180109fde  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x180109fe3  mov     ebx, eax
0x180109fe5  test    eax, eax
0x180109fe7  jns     short loc_18010A061
0x180109fe9  mov     rcx, [rsp+108h]; this
0x180109ff1  mov     r9d, eax; char *
0x180109ff4  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109ffb  mov     edx, 870h; void *
0x18010a000  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010a005  nop
0x18010a006  lea     rcx, [rsp+108h+var_40]
0x18010a00e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010a013  nop
0x18010a014  lea     rcx, [rsp+108h+string]
0x18010a019  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010a01e  nop
0x18010a01f  lea     rcx, [rsp+108h+var_A0]
0x18010a024  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010a029  nop
0x18010a02a  lea     rcx, [rsp+108h+var_B0]
0x18010a02f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010a034  nop
0x18010a035  mov     [rsp+108h+var_48], r15
0x18010a03d  lea     rcx, [rsp+108h+var_B8]
0x18010a042  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010a047  nop
0x18010a048  mov     [rsp+108h+var_68], r15
0x18010a050  lea     rcx, [rsp+108h+var_C0]
0x18010a055  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010a05a  mov     eax, ebx
0x18010a05c  jmp     loc_18010A46E
0x18010a061  lea     rdx, aDiagnosticsfra; "\\DiagnosticsFrameworkData.json"
0x18010a068  lea     rcx, [rsp+108h+var_40]
0x18010a070  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010a075  lea     rcx, [rsp+108h+var_40]
0x18010a07d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010a082  mov     rcx, rax; lpFileName
0x18010a085  call    cs:__imp_DeleteFileW
0x18010a08b  lea     rcx, [rsp+108h+var_40]
0x18010a093  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010a098  mov     rcx, rax; lpFileName
0x18010a09b  mov     [rsp+108h+hTemplateFile], r15; hTemplateFile
0x18010a0a0  mov     [rsp+108h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18010a0a5  mov     [rsp+108h+dwCreationDisposition], 2; dwCreationDisposition
0x18010a0ad  xor     r9d, r9d; lpSecurityAttributes
0x18010a0b0  xor     r8d, r8d; dwShareMode
0x18010a0b3  mov     edx, 10000000h; dwDesiredAccess
0x18010a0b8  call    cs:__imp_CreateFileW
0x18010a0be  mov     rbx, rax
0x18010a0c1  mov     [rsp+108h+var_98], rax
0x18010a0c6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010a0ca  jnz     loc_18010A151
0x18010a0d0  mov     rcx, [rsp+108h]; this
0x18010a0d8  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010a0df  mov     edx, 880h; void *
0x18010a0e4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010a0e9  mov     ebx, eax
0x18010a0eb  lea     rcx, [rsp+108h+var_98]
0x18010a0f0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18010a0f5  nop
0x18010a0f6  lea     rcx, [rsp+108h+var_40]
0x18010a0fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010a103  nop
0x18010a104  lea     rcx, [rsp+108h+string]
0x18010a109  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010a10e  nop
0x18010a10f  lea     rcx, [rsp+108h+var_A0]
0x18010a114  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010a119  nop
0x18010a11a  lea     rcx, [rsp+108h+var_B0]
0x18010a11f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18010a124  nop
0x18010a125  mov     [rsp+108h+var_48], r15
0x18010a12d  lea     rcx, [rsp+108h+var_B8]
  ... truncated ...
```
