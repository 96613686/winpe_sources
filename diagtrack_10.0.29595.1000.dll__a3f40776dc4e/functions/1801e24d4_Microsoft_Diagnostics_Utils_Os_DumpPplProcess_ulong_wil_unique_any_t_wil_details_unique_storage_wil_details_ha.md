# Microsoft::Diagnostics::Utils::Os::DumpPplProcess(ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,ulong,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,unsigned __int64)

- ea: `0x1801e24d4`
- end: `0x1801e2986`
- name: `?DumpPplProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@KV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_K@Z`
- size: `1202`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801e4348`

## callees

- `0x180020150`
- `0x1800202a4`
- `0x18002110c`
- `0x18002b318`
- `0x18002b7c0`
- `0x18002b9c0`
- `0x18002df00`
- `0x1800346b0`
- `0x1800346dc`
- `0x180034c78`
- `0x180034e50`
- `0x1800501e4`
- `0x180064e6c`
- `0x180064e8c`
- `0x18008abf4`
- `0x1800bc658`
- `0x1800be65c`
- `0x1800be80c`
- `0x1800d1404`
- `0x1801b1214`
- `0x1801b18c0`
- `0x1801e24d4`
- `0x1801e2d68`
- `0x18020aac0`
- `0x18020bab8`
- `0x18026b6a4`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x1801e279d`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x1801e27b8`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x1801e279d`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z` at `0x1801e27b8`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x1801e2767`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x1801e2782`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x1801e2767`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x1801e2782`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1801e28d2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1801e28d2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1801e283f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1801e283f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801e2579`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801e2579`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801e268a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1801e268a`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1801e2672`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1801e2672`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1801e2620`
- `api-ms-win-core-wow64-l1-1-1!IsWow64Process2` at `0x1801e2620`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Diagnostics::Utils::Os::DumpPplProcess(
        unsigned int a1,
        _QWORD *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5)
{
  __int64 v8; // rax
  HANDLE v9; // rbx
  const char *v10; // r9
  DWORD LastError; // ebx
  __int64 v12; // rdi
  const char *v13; // r9
  __int64 v14; // rdx
  WCHAR *v15; // rcx
  UINT SystemWow64Directory2W; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  LPWSTR *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  BOOL v29; // ebx
  const char *v30; // r9
  HANDLE hProcess; // rbx
  int v32; // eax
  const char *v33; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  _WORD v37[2]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ExitCode[3]; // [rsp+54h] [rbp-ACh] BYREF
  __int128 v39; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  _QWORD v43[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v45; // [rsp+B0h] [rbp-50h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v47[2]; // [rsp+D0h] [rbp-30h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v49; // [rsp+148h] [rbp+48h]
  _BYTE v50[16]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v51[240]; // [rsp+160h] [rbp+60h] BYREF
  LPWSTR lpBuffer[2]; // [rsp+250h] [rbp+150h] BYREF
  UINT uSize[2]; // [rsp+260h] [rbp+160h]
  unsigned __int64 v54; // [rsp+268h] [rbp+168h]
  _BYTE v55[32]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  v40 = 0;
  _try_create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAA_NW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    &v40,
    0,
    0,
    &SecurityAttributes,
    0);
  v8 = std::wstring::wstring(v55);
  if ( *(_QWORD *)(v8 + 24) > 7u )
    v8 = *(_QWORD *)v8;
  v9 = CreateFileW((LPCWSTR)v8, 0x40000000u, 0, &SecurityAttributes, 1u, 0, 0);
  v45 = v9;
  std::wstring::_Tidy_deallocate(v55);
  if ( (((unsigned __int64)v9 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v12 = v40;
    v47[0] = v40;
    v47[1] = v9;
    *(_QWORD *)&v39 = v47;
    v39 = *(_OWORD *)gsl::span<void * const,-1>::span<void * const,-1>(v43, &v39);
    Microsoft::Diagnostics::Utils::Os::BuildInheritHandleAttributeList(v41, &v39);
    v37[0] = 0;
    std::wstring::wstring(lpBuffer, 260, 0);
    if ( !(unsigned int)IsWow64Process2(*a2, v37, 0) )
    {
      v14 = 1112;
LABEL_7:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v14,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                    v13);
LABEL_37:
      std::wstring::_Tidy_deallocate(lpBuffer);
      Microsoft::Diagnostics::Utils::Os::AttributeListAndMemory::~AttributeListAndMemory((Microsoft::Diagnostics::Utils::Os::AttributeListAndMemory *)v41);
      goto LABEL_38;
    }
    v15 = (WCHAR *)lpBuffer;
    if ( v37[0] )
    {
      if ( v54 > 7 )
        v15 = lpBuffer[0];
      SystemWow64Directory2W = GetSystemWow64Directory2W(v15, uSize[0]);
    }
    else
    {
      if ( v54 > 7 )
        v15 = lpBuffer[0];
      SystemWow64Directory2W = GetSystemDirectoryW(v15, uSize[0]);
    }
    if ( !SystemWow64Directory2W )
    {
      v14 = 1123;
      goto LABEL_7;
    }
    v17 = SystemWow64Directory2W;
    if ( (unsigned __int64)SystemWow64Directory2W >= *(_QWORD *)uSize )
    {
      LastError = -2147024774;
      v18 = 1124;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
        (const char *)LastError,
        dwCreationDisposition);
      goto LABEL_37;
    }
    v19 = lpBuffer;
    if ( v54 > 7 )
      v19 = (LPWSTR *)lpBuffer[0];
    if ( !*(_WORD *)v19 )
    {
      LastError = -2147024735;
      v18 = 1125;
      goto LABEL_19;
    }
    std::wstring::resize(lpBuffer, v17);
    *(_QWORD *)&v39 = L"werfaultsecure.exe";
    *((_QWORD *)&v39 + 1) = std::_WChar_traits<wchar_t>::length(L"werfaultsecure.exe");
    Microsoft::Diagnostics::Utils::String::AppendPath(lpBuffer, &v39);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpBuffer);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v50);
    v20 = std::operator<<<wchar_t>(v51, lpBuffer);
    v21 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v20, L" /h /s /pid ");
    v22 = std::wostream::operator<<(v21, a1);
    v23 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v22, L" /type ");
    v24 = std::wostream::operator<<(v23, a3);
    v25 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v24, L" /encfile ");
    v26 = std::wostream::operator<<(v25, v9);
    v27 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v26, L" /cancel ");
    std::wostream::operator<<(v27, v12);
    *(&StartupInfo.cb + 1) = 0;
    memset_0(&StartupInfo.lpReserved, 0, sizeof(struct _STARTUPINFOW));
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    StartupInfo.cb = 112;
    v49 = v42;
    v28 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v50, v55);
    if ( *(_QWORD *)(v28 + 24) > 7u )
      v28 = *(_QWORD *)v28;
    v29 = CreateProcessW(0, (LPWSTR)v28, 0, 0, 1, 0xC0000u, 0, 0, &StartupInfo, &ProcessInformation);
    std::wstring::_Tidy_deallocate(v55);
    if ( !v29 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x47F,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                    v30);
LABEL_36:
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v50);
      goto LABEL_37;
    }
    hProcess = ProcessInformation.hProcess;
    *(_QWORD *)&v39 = ProcessInformation.hProcess;
    v43[0] = ProcessInformation.hThread;
    if ( Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(ProcessInformation.hProcess, a5) )
    {
      ExitCode[0] = 0;
      if ( GetExitCodeProcess(hProcess, ExitCode) )
      {
        LastError = ExitCode[0];
        if ( (ExitCode[0] & 0x80000000) != 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x491,
            (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
            (const char *)ExitCode[0],
            dwCreationDispositiona);
        goto LABEL_35;
      }
      v32 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x490,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              v33);
    }
    else
    {
      _SetEvent___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ(&v40);
      v32 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x48B,
              (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
              (const char *)0x5B4,
              dwCreationDispositiona);
    }
    LastError = v32;
LABEL_35:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v43);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v39);
    goto LABEL_36;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x446,
                (unsigned int)"onecore\\base\\telemetry\\utc\\include\\OsUtils.h",
                v10);
LABEL_38:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v45);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v40);
  return LastError;
}

```

## disassembly

```asm
0x1801e24d4  push    rbp
0x1801e24d6  push    rbx
0x1801e24d7  push    rsi
0x1801e24d8  push    rdi
0x1801e24d9  push    r12
0x1801e24db  push    r14
0x1801e24dd  push    r15
0x1801e24df  lea     rbp, [rsp-1A0h]
0x1801e24e7  sub     rsp, 2A0h
0x1801e24ee  mov     rax, cs:__security_cookie
0x1801e24f5  xor     rax, rsp
0x1801e24f8  mov     [rbp+1D0h+var_40], rax
0x1801e24ff  mov     rbx, r9
0x1801e2502  mov     r15d, r8d
0x1801e2505  mov     rsi, rdx
0x1801e2508  mov     r14d, ecx
0x1801e250b  mov     qword ptr [rbp+1D0h+SecurityAttributes.nLength], 18h
0x1801e2513  xor     r12d, r12d
0x1801e2516  mov     [rbp+1D0h+SecurityAttributes.lpSecurityDescriptor], r12
0x1801e251a  mov     qword ptr [rbp+1D0h+SecurityAttributes.bInheritHandle], 1
0x1801e2522  mov     [rsp+2D0h+var_260], r12
0x1801e2527  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r12
0x1801e252c  lea     r9, [rbp+1D0h+SecurityAttributes]
0x1801e2530  xor     r8d, r8d
0x1801e2533  xor     edx, edx
0x1801e2535  lea     rcx, [rsp+2D0h+var_260]
0x1801e253a  call    ?try_create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAA_NW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1801e253f  mov     rdx, rbx
0x1801e2542  lea     rcx, [rbp+1D0h+var_60]
0x1801e2549  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1801e254e  cmp     qword ptr [rax+18h], 7
0x1801e2553  jbe     short loc_1801E2558
0x1801e2555  mov     rax, [rax]
0x1801e2558  mov     [rsp+2D0h+hTemplateFile], r12; hTemplateFile
0x1801e255d  mov     [rsp+2D0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1801e2562  mov     [rsp+2D0h+dwCreationDisposition], 1; int
0x1801e256a  lea     r9, [rbp+1D0h+SecurityAttributes]; lpSecurityAttributes
0x1801e256e  xor     r8d, r8d; dwShareMode
0x1801e2571  mov     edx, 40000000h; dwDesiredAccess
0x1801e2576  mov     rcx, rax; lpFileName
0x1801e2579  call    cs:__imp_CreateFileW
0x1801e257f  mov     rbx, rax
0x1801e2582  mov     [rbp+1D0h+var_220], rax
0x1801e2586  lea     rcx, [rbp+1D0h+var_60]
0x1801e258d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801e2592  lea     rax, [rbx+1]
0x1801e2596  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801e259c  jnz     short loc_1801E25BD
0x1801e259e  mov     rcx, [rbp+1D8h]; this
0x1801e25a5  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801e25ac  mov     edx, 446h; void *
0x1801e25b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e25b6  mov     ebx, eax
0x1801e25b8  jmp     loc_1801E294F
0x1801e25bd  mov     rdi, [rsp+2D0h+var_260]
0x1801e25c2  mov     [rbp+1D0h+var_200], rdi
0x1801e25c6  mov     [rbp+1D0h+var_1F8], rbx
0x1801e25ca  lea     rax, [rbp+1D0h+var_200]
0x1801e25ce  mov     qword ptr [rsp+2D0h+var_270], rax
0x1801e25d3  lea     rdx, [rsp+2D0h+var_270]
0x1801e25d8  lea     rcx, [rbp+1D0h+var_248]
0x1801e25dc  call    ??$?0QEAX$01$0?0$0A@@?$span@QEAX$0?0@gsl@@QEAA@AEBV?$span@QEAX$01@1@@Z; gsl::span<void * const,-1>::span<void * const,-1>(gsl::span<void * const,2> const &)
0x1801e25e1  movups  xmm0, xmmword ptr [rax]
0x1801e25e4  movdqu  [rsp+2D0h+var_270], xmm0
0x1801e25ea  lea     rdx, [rsp+2D0h+var_270]
0x1801e25ef  lea     rcx, [rsp+2D0h+var_258]
0x1801e25f4  call    ?BuildInheritHandleAttributeList@Os@Utils@Diagnostics@Microsoft@@CA?AUAttributeListAndMemory@1234@V?$span@QEAX$0?0@gsl@@@Z; Microsoft::Diagnostics::Utils::Os::BuildInheritHandleAttributeList(gsl::span<void * const,-1>)
0x1801e25f9  nop
0x1801e25fa  mov     [rsp+2D0h+var_280], r12w
0x1801e2600  xor     r8d, r8d
0x1801e2603  mov     edx, 104h
0x1801e2608  lea     rcx, [rbp+1D0h+lpBuffer]
0x1801e260f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1801e2614  nop
0x1801e2615  xor     r8d, r8d
0x1801e2618  lea     rdx, [rsp+2D0h+var_280]
0x1801e261d  mov     rcx, [rsi]
0x1801e2620  call    cs:__imp_IsWow64Process2
0x1801e2626  test    eax, eax
0x1801e2628  jnz     short loc_1801E2649
0x1801e262a  mov     edx, 458h; void *
0x1801e262f  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801e2636  mov     rcx, [rbp+1D8h]; this
0x1801e263d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e2642  mov     ebx, eax
0x1801e2644  jmp     loc_1801E2937
0x1801e2649  movzx   r8d, [rsp+2D0h+var_280]
0x1801e264f  lea     rcx, [rbp+1D0h+lpBuffer]
0x1801e2656  mov     edx, [rbp+1D0h+uSize]; uSize
0x1801e265c  test    r8w, r8w
0x1801e2660  jz      short loc_1801E267A
0x1801e2662  cmp     [rbp+1D0h+var_68], 7
0x1801e266a  cmova   rcx, [rbp+1D0h+lpBuffer]
0x1801e2672  call    cs:__imp_GetSystemWow64Directory2W
0x1801e2678  jmp     short loc_1801E2690
0x1801e267a  cmp     [rbp+1D0h+var_68], 7
0x1801e2682  cmova   rcx, [rbp+1D0h+lpBuffer]; lpBuffer
0x1801e268a  call    cs:__imp_GetSystemDirectoryW
0x1801e2690  test    eax, eax
0x1801e2692  jnz     short loc_1801E269B
0x1801e2694  mov     edx, 463h
0x1801e2699  jmp     short loc_1801E262F
0x1801e269b  mov     edx, eax
0x1801e269d  cmp     rdx, qword ptr [rbp+1D0h+uSize]
0x1801e26a4  jb      short loc_1801E26CB
0x1801e26a6  mov     ebx, 8007007Ah
0x1801e26ab  mov     edx, 464h; void *
0x1801e26b0  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801e26b7  mov     r9d, ebx; char *
0x1801e26ba  mov     rcx, [rbp+1D8h]; this
0x1801e26c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e26c6  jmp     loc_1801E2937
0x1801e26cb  lea     rax, [rbp+1D0h+lpBuffer]
0x1801e26d2  cmp     [rbp+1D0h+var_68], 7
0x1801e26da  cmova   rax, [rbp+1D0h+lpBuffer]
0x1801e26e2  cmp     [rax], r12w
0x1801e26e6  jnz     short loc_1801E26F4
0x1801e26e8  mov     ebx, 800700A1h
0x1801e26ed  mov     edx, 465h
0x1801e26f2  jmp     short loc_1801E26B0
0x1801e26f4  lea     rcx, [rbp+1D0h+lpBuffer]
0x1801e26fb  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1801e2700  lea     rcx, aWerfaultsecure; "werfaultsecure.exe"
0x1801e2707  mov     qword ptr [rsp+2D0h+var_270], rcx
0x1801e270c  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x1801e2711  mov     qword ptr [rsp+2D0h+var_270+8], rax
0x1801e2716  lea     rdx, [rsp+2D0h+var_270]
0x1801e271b  lea     rcx, [rbp+1D0h+lpBuffer]
0x1801e2722  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x1801e2727  xor     r8d, r8d
0x1801e272a  mov     dl, 1
0x1801e272c  lea     rcx, [rbp+1D0h+lpBuffer]; lpSrc
0x1801e2733  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1801e2738  lea     rcx, [rbp+1D0h+var_180]
0x1801e273c  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x1801e2741  nop
0x1801e2742  lea     rdx, [rbp+1D0h+lpBuffer]
0x1801e2749  lea     rcx, [rbp+1D0h+var_170]
0x1801e274d  call    ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x1801e2752  mov     rcx, rax
0x1801e2755  lea     rdx, aHSPid; " /h /s /pid "
0x1801e275c  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1801e2761  mov     edx, r14d
0x1801e2764  mov     rcx, rax
0x1801e2767  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x1801e276d  mov     rcx, rax
0x1801e2770  lea     rdx, aType_5; " /type "
0x1801e2777  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1801e277c  mov     edx, r15d
0x1801e277f  mov     rcx, rax
0x1801e2782  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x1801e2788  mov     rcx, rax
0x1801e278b  lea     rdx, aEncfile; " /encfile "
0x1801e2792  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1801e2797  mov     rdx, rbx
0x1801e279a  mov     rcx, rax
0x1801e279d  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x1801e27a3  mov     rcx, rax
0x1801e27a6  lea     rdx, aCancel_1; " /cancel "
0x1801e27ad  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1801e27b2  mov     rdx, rdi
0x1801e27b5  mov     rcx, rax
0x1801e27b8  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_K@Z; std::wostream::operator<<(unsigned __int64)
0x1801e27be  xor     eax, eax
0x1801e27c0  mov     dword ptr [rbp+1D0h+StartupInfo+4], eax
0x1801e27c3  xor     edx, edx; Val
0x1801e27c5  lea     r8d, [rax+68h]; Size
0x1801e27c9  lea     rcx, [rbp+1D0h+StartupInfo.lpReserved]; void *
0x1801e27cd  call    memset_0
0x1801e27d2  xorps   xmm0, xmm0
0x1801e27d5  xor     eax, eax
0x1801e27d7  movups  xmmword ptr [rbp+1D0h+ProcessInformation.hProcess], xmm0
0x1801e27db  mov     qword ptr [rbp+1D0h+ProcessInformation.dwProcessId], rax
0x1801e27df  mov     [rbp+1D0h+StartupInfo.cb], 70h ; 'p'
0x1801e27e6  mov     rax, [rbp+1D0h+var_250]
0x1801e27ea  mov     [rbp+1D0h+var_188], rax
0x1801e27ee  lea     rdx, [rbp+1D0h+var_60]
0x1801e27f5  lea     rcx, [rbp+1D0h+var_180]
0x1801e27f9  call    ?str@?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x1801e27fe  cmp     qword ptr [rax+18h], 7
0x1801e2803  jbe     short loc_1801E2808
0x1801e2805  mov     rax, [rax]
0x1801e2808  lea     rcx, [rbp+1D0h+ProcessInformation]
0x1801e280c  mov     [rsp+2D0h+lpProcessInformation], rcx; lpProcessInformation
0x1801e2811  lea     rcx, [rbp+1D0h+StartupInfo]
0x1801e2815  mov     [rsp+2D0h+lpStartupInfo], rcx; lpStartupInfo
0x1801e281a  mov     [rsp+2D0h+lpCurrentDirectory], r12; lpCurrentDirectory
0x1801e281f  mov     [rsp+2D0h+hTemplateFile], r12; lpEnvironment
0x1801e2824  mov     [rsp+2D0h+dwFlagsAndAttributes], 0C0000h; dwCreationFlags
0x1801e282c  mov     [rsp+2D0h+dwCreationDisposition], 1; int
0x1801e2834  xor     r9d, r9d; lpThreadAttributes
0x1801e2837  xor     r8d, r8d; lpProcessAttributes
0x1801e283a  mov     rdx, rax; lpCommandLine
0x1801e283d  xor     ecx, ecx; lpApplicationName
0x1801e283f  call    cs:__imp_CreateProcessW
0x1801e2845  mov     ebx, eax
0x1801e2847  lea     rcx, [rbp+1D0h+var_60]
0x1801e284e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801e2853  test    ebx, ebx
0x1801e2855  jnz     short loc_1801E2876
0x1801e2857  mov     rcx, [rbp+1D8h]; this
0x1801e285e  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801e2865  mov     edx, 47Fh; void *
0x1801e286a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e286f  mov     ebx, eax
0x1801e2871  jmp     loc_1801E292D
0x1801e2876  mov     rbx, [rbp+1D0h+ProcessInformation.hProcess]
0x1801e287a  mov     qword ptr [rsp+2D0h+var_270], rbx
0x1801e287f  mov     rax, [rbp+1D0h+ProcessInformation.hThread]
0x1801e2883  mov     [rbp+1D0h+var_248], rax
0x1801e2887  mov     edx, [rbp+1D0h+arg_20]; unsigned int
0x1801e288d  mov     rcx, rbx; void *
0x1801e2890  call    ?WaitOrTimeout@Os@Utils@Diagnostics@Microsoft@@SA_NPEAXK@Z; Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(void *,ulong)
0x1801e2895  test    al, al
0x1801e2897  jnz     short loc_1801E28C5
0x1801e2899  lea     rcx, [rsp+2D0h+var_260]
0x1801e289e  call    ?SetEvent@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBAXXZ
0x1801e28a3  mov     rcx, [rbp+1D8h]; this
0x1801e28aa  mov     r9d, 5B4h; char *
0x1801e28b0  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801e28b7  mov     edx, 48Bh; void *
0x1801e28bc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801e28c1  mov     ebx, eax
0x1801e28c3  jmp     short loc_1801E2919
0x1801e28c5  mov     [rsp+2D0h+ExitCode], r12d
0x1801e28ca  lea     rdx, [rsp+2D0h+ExitCode]; lpExitCode
0x1801e28cf  mov     rcx, rbx; hProcess
0x1801e28d2  call    cs:__imp_GetExitCodeProcess
0x1801e28d8  test    eax, eax
0x1801e28da  jnz     short loc_1801E28F6
0x1801e28dc  mov     rcx, [rbp+1D8h]; this
0x1801e28e3  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801e28ea  mov     edx, 490h; void *
0x1801e28ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801e28f4  jmp     short loc_1801E28C1
0x1801e28f6  mov     ebx, [rsp+2D0h+ExitCode]
0x1801e28fa  test    ebx, ebx
0x1801e28fc  jns     short loc_1801E2919
0x1801e28fe  mov     rcx, [rbp+1D8h]; this
0x1801e2905  mov     r9d, ebx; char *
0x1801e2908  lea     r8, aOnecoreBaseTel_240; "onecore\\base\\telemetry\\utc\\include"...
0x1801e290f  mov     edx, 491h; void *
0x1801e2914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2919  lea     rcx, [rbp+1D0h+var_248]
0x1801e291d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e2922  lea     rcx, [rsp+2D0h+var_270]
0x1801e2927  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e292c  nop
0x1801e292d  lea     rcx, [rbp+1D0h+var_180]
0x1801e2931  call    ??_D?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAXXZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(void)
0x1801e2936  nop
0x1801e2937  lea     rcx, [rbp+1D0h+lpBuffer]
0x1801e293e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801e2943  nop
0x1801e2944  lea     rcx, [rsp+2D0h+var_258]; this
0x1801e2949  call    ??1AttributeListAndMemory@Os@Utils@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::Utils::Os::AttributeListAndMemory::~AttributeListAndMemory(void)
0x1801e294e  nop
0x1801e294f  lea     rcx, [rbp+1D0h+var_220]
0x1801e2953  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801e2958  nop
0x1801e2959  lea     rcx, [rsp+2D0h+var_260]
0x1801e295e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801e2963  mov     eax, ebx
0x1801e2965  mov     rcx, [rbp+1D0h+var_40]
0x1801e296c  xor     rcx, rsp; StackCookie
0x1801e296f  call    __security_check_cookie
0x1801e2974  add     rsp, 2A0h
0x1801e297b  pop     r15
0x1801e297d  pop     r14
0x1801e297f  pop     r12
0x1801e2981  pop     rdi
0x1801e2982  pop     rsi
0x1801e2983  pop     rbx
0x1801e2984  pop     rbp
0x1801e2985  retn
```
