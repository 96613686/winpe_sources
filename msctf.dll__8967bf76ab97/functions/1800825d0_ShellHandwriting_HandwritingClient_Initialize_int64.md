# ShellHandwriting::HandwritingClient::Initialize(__int64)

- ea: `0x1800825d0`
- end: `0x180082c4c`
- name: `?Initialize@HandwritingClient@ShellHandwriting@@UEAAX_J@Z`
- size: `1660`
- prototype: `void __fastcall(ShellHandwriting::HandwritingClient *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800788a0`
- `0x180078f60`
- `0x180079854`
- `0x18007a428`
- `0x18007db8c`
- `0x18007dd28`
- `0x1800825d0`
- `0x18008b1a8`
- `0x18008b22c`
- `0x18008b2b0`
- `0x18008b334`
- `0x18008e300`
- `0x18008f584`
- `0x18008ff70`
- `0x18008ffa0`
- `0x180091e60`
- `0x1800ef540`
- `0x1800ef8a0`
- `0x1800ef91c`
- `0x1800f04d8`
- `0x1800f0c80`
- `0x1800f7768`
- `0x1800f8904`
- `0x1800f9da0`
- `0x1800fb6cc`
- `0x1800fb96c`
- `0x1800fbad4`
- `0x1800fc578`
- `0x1800fc978`
- `0x1800fcdb0`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180082b68`
- `msvcrt!_wtoi` at `0x180082b68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008263f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008263f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800829ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800829ce`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180082654`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180082654`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18008268a`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x18008268a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18008262d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18008262d`
- `USER32!GetKeyboardLayout` at `0x180082613`
- `USER32!GetKeyboardLayout` at `0x180082613`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180082763`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800827c3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180082763`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800827c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180082aba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180082aba`

## string_xrefs

- `0x18008273b`: `Windows.Internal.ApplicationTargetedFeatureDatabase.ApplicationTargetedFeatureConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
void __fastcall ShellHandwriting::HandwritingClient::Initialize(
        ShellHandwriting::HandwritingClient *this,
        unsigned int a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE v5; // rax
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  int ActivationFactory; // esi
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rdx
  __int64 *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, char *); // r14
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // r14
  __int64 (__fastcall *v25)(__int64, _QWORD, __int64, char *); // r15
  __int64 v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // r8
  PCWSTR StringRawBuffer; // rax
  __int64 v35; // rdx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  const wchar_t *p_String; // rcx
  __int64 v40; // rdx
  __int64 v41; // [rsp+30h] [rbp-418h] BYREF
  _QWORD *v42; // [rsp+38h] [rbp-410h] BYREF
  __int64 v43; // [rsp+40h] [rbp-408h] BYREF
  HANDLE hProcess; // [rsp+48h] [rbp-400h] BYREF
  UINT32 length; // [rsp+50h] [rbp-3F8h] BYREF
  LARGE_INTEGER Frequency; // [rsp+58h] [rbp-3F0h] BYREF
  HSTRING v47[2]; // [rsp+60h] [rbp-3E8h] BYREF
  _BYTE v48[256]; // [rsp+70h] [rbp-3D8h] BYREF
  HSTRING_HEADER String; // [rsp+170h] [rbp-2D8h] BYREF
  unsigned __int64 v50; // [rsp+188h] [rbp-2C0h]
  _QWORD v51[4]; // [rsp+190h] [rbp-2B8h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+1B0h] [rbp-298h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1E0h] [rbp-268h] BYREF
  HSTRING string; // [rsp+1F8h] [rbp-250h]
  WCHAR Filename[264]; // [rsp+200h] [rbp-248h] BYREF

  v47[1] = (HSTRING)this;
  wil::com_ptr_t<IUIAutomationElement,wil::err_returncode_policy>::reset((char *)this + 40);
  ShellHandwriting::InputTraceLogging::ShellHandwriting::Client::RegistrationRequested(a2);
  *((_WORD *)this + 116) = (unsigned __int16)GetKeyboardLayout(0);
  Frequency.QuadPart = 0;
  QueryPerformanceFrequency(&Frequency);
  *((LARGE_INTEGER *)this + 31) = Frequency;
  CurrentProcessId = GetCurrentProcessId();
  hProcess = 0;
  v5 = OpenProcess(0x410u, 0, CurrentProcessId);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hProcess,
    v5);
  if ( (char *)hProcess - 1 > (char *)0xFFFFFFFFFFFFFFFDLL || !K32GetModuleFileNameExW(hProcess, 0, Filename, 0x104u) )
  {
LABEL_43:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
    return;
  }
  std::wstring::wstring(v51, Filename);
  v6 = std::char_traits<unsigned short>::length(L"msedge.exe");
  if ( std::wstring::find(v51, L"msedge.exe", v7, v6) != -1 )
    *((_BYTE *)this + 116) = 1;
  LOBYTE(v9) = 3;
  LOBYTE(v8) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ATFOI_Test>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ATFOI_Test>::GetImpl'::`2'::impl,
    v8,
    v9);
  v43 = 0;
  v41 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbShSAFI>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MTestAbShSAFI>::GetImpl'::`2'::impl) )
  {
    v14 = (__int64 *)wil::GetActivationFactory<Windows::Internal::ApplicationTargetedFeatureDatabase::IApplicationTargetedFeatureConfigStatics>(&v42);
    v15 = *v14;
    *v14 = 0;
    v16 = v43;
    v43 = v15;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v42);
    v17 = (__int64 *)wil::GetActivationFactory<Windows::Internal::ApplicationTargetedFeatureDatabase::IApplicationTargetedFeatureQueryFactory>(&v42);
    v18 = *v17;
    *v17 = 0;
    v19 = v41;
    v41 = v18;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v42);
    goto LABEL_16;
  }
  v43 = 0;
  v50 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &String,
    L"Windows.Internal.ApplicationTargetedFeatureDatabase.ApplicationTargetedFeatureConfig",
    0x55u,
    0x54u);
  ActivationFactory = RoGetActivationFactory(v50, &GUID_7729cc91_abf4_56b1_99f0_ba2b6368b13e, &v43);
  v41 = 0;
  v50 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &String,
    L"Windows.Internal.ApplicationTargetedFeatureDatabase.ApplicationTargetedFeatureQuery",
    0x54u,
    0x53u);
  v11 = RoGetActivationFactory(v50, &GUID_fcc6aa4e_a393_5a0f_bbf3_6287d15539a1, &v41);
  v12 = v11;
  if ( ActivationFactory >= 0 && v11 >= 0 )
  {
LABEL_16:
    v20 = v43;
    if ( v43 && v41 )
    {
      v21 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v43 + 48LL);
      v22 = *((_QWORD *)this + 24);
      *((_QWORD *)this + 24) = 0;
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v23 = v21(v20, (char *)this + 192);
      if ( v23 >= 0 )
      {
        v24 = v41;
        v25 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, char *))(*(_QWORD *)v41 + 48LL);
        v26 = *((_QWORD *)this + 25);
        *((_QWORD *)this + 25) = 0;
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        v27 = v51;
        if ( v51[3] >= 8u )
          v27 = (_QWORD *)v51[0];
        v42 = v27;
        v28 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&SystemInfo, &v42) + 24);
        v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&String, &off_180113190);
        v23 = v25(v24, *(_QWORD *)(v29 + 24), v28, (char *)this + 200);
      }
      ShellHandwriting::InputTraceLogging::ShellHandwriting::Client::ApplicationTargetedFeatureConfigInitialized(v23);
    }
    if ( !*((_BYTE *)this + 33) && ShellHandwriting::HandwritingClient::IsApplicationOptedOut(this) )
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbShAOOLU>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MTestAbShAOOLU>::GetImpl'::`2'::impl)
        || (memset(&SystemInfo, 0, sizeof(SystemInfo)),
            GetSystemInfo(&SystemInfo),
            SystemInfo.wProcessorArchitecture != 12)
        || (v30 = std::char_traits<unsigned short>::length(L"whatsapp.exe"),
            std::wstring::find(v51, L"whatsapp.exe", v31, v30) == -1)
        && (v32 = std::char_traits<unsigned short>::length(L"messenger.exe"),
            std::wstring::find(v51, L"messenger.exe", v33, v32) == -1) )
      {
        ShellHandwriting::HandwritingClient::SetHandwritingStateImpl(this, 1);
      }
    }
    string = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &lParam, 1u, 0);
    v47[0] = string;
    v50 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&String, L"SupportedLanguages", 0x13u, 0x12u);
    if ( (int)ShellHandwriting::HandwritingClient::QueryTargetedFeatureData(this, &String, v47) >= 0 )
    {
      length = WindowsGetStringLen(string);
      StringRawBuffer = WindowsGetStringRawBuffer(v47[0], &length);
      std::wstring::wstring(&SystemInfo, StringRawBuffer);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
        v48,
        &SystemInfo);
      LOBYTE(v35) = 1;
      std::wstring::_Tidy(&SystemInfo, v35, 0);
      v50 = 7;
      *(_QWORD *)&String.Reserved.Reserved2[16] = 0;
      LOWORD(String.Reserved.Reserved1) = 0;
      while ( 1 )
      {
        v36 = std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v48, &String);
        v37 = *(int *)(*(_QWORD *)v36 + 4LL);
        v38 = v37 + v36;
        if ( (*(_BYTE *)(v38 + 16) & 6) != 0 || !v38 )
          break;
        p_String = (const wchar_t *)&String;
        if ( v50 >= 8 )
          p_String = (const wchar_t *)String.Reserved.Reserved1;
        LODWORD(v42) = _wtoi(p_String);
        std::vector<int>::push_back((char *)this + 208, &v42);
      }
      LOBYTE(v37) = 1;
      std::wstring::_Tidy(&String, v37, 0);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v48);
    }
    *((_BYTE *)this + 234) = ShellHandwriting::HandwritingClient::IsKeyboardFocusOverridenForApp(this);
    *((_BYTE *)this + 235) = ShellHandwriting::HandwritingClient::IsReadOnlyOverridenForApp(this);
    *((_BYTE *)this + 236) = ShellHandwriting::HandwritingClient::IsSearchUIAGroupForEditEnabledForApp(this);
    *((_BYTE *)this + 237) = ShellHandwriting::HandwritingClient::IsEarlyInputCaptureOnAsyncClientResponseNeeded(this);
    *((_BYTE *)this + 238) = ShellHandwriting::HandwritingClient::IsSearchUIAAutocompleteEnabled(this);
    string = 0;
    wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v41);
    wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v43);
    LOBYTE(v40) = 1;
    std::wstring::_Tidy(v51, v40, 0);
    goto LABEL_43;
  }
  ShellHandwriting::HandwritingClient::SetHandwritingStateImpl(this, 1);
  if ( ActivationFactory < 0 )
    v12 = ActivationFactory;
  ShellHandwriting::InputTraceLogging::ShellHandwriting::Client::ApplicationTargetedFeatureConfigInitialized(v12);
  wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v41);
  wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(&v43);
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(v51, v13, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
}

```

## disassembly

```asm
0x1800825d0  mov     [rsp+arg_10], rbx
0x1800825d5  push    rsi
0x1800825d6  push    rdi
0x1800825d7  push    r12
0x1800825d9  push    r14
0x1800825db  push    r15
0x1800825dd  sub     rsp, 420h
0x1800825e4  mov     rax, cs:__security_cookie
0x1800825eb  xor     rax, rsp
0x1800825ee  mov     [rsp+448h+var_38], rax
0x1800825f6  mov     rbx, rdx
0x1800825f9  mov     rdi, rcx
0x1800825fc  mov     [rsp+448h+var_3E0], rcx
0x180082601  add     rcx, 28h ; '('
0x180082605  call    ?reset@?$com_ptr_t@UIUIAutomationElement@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUIAutomationElement,wil::err_returncode_policy>::reset(void)
0x18008260a  mov     ecx, ebx; unsigned int
0x18008260c  call    ?RegistrationRequested@Client@ShellHandwriting@InputTraceLogging@2@SAXI@Z; ShellHandwriting::InputTraceLogging::ShellHandwriting::Client::RegistrationRequested(uint)
0x180082611  xor     ecx, ecx; idThread
0x180082613  call    cs:__imp_GetKeyboardLayout
0x180082619  mov     [rdi+0E8h], ax
0x180082620  xor     r12d, r12d
0x180082623  mov     qword ptr [rsp+448h+Frequency], r12
0x180082628  lea     rcx, [rsp+448h+Frequency]; lpFrequency
0x18008262d  call    cs:__imp_QueryPerformanceFrequency
0x180082633  mov     rax, qword ptr [rsp+448h+Frequency]
0x180082638  mov     [rdi+0F8h], rax
0x18008263f  call    cs:__imp_GetCurrentProcessId
0x180082645  mov     [rsp+448h+hProcess], r12
0x18008264a  mov     r8d, eax; dwProcessId
0x18008264d  xor     edx, edx; bInheritHandle
0x18008264f  mov     ecx, 410h; dwDesiredAccess
0x180082654  call    cs:__imp_OpenProcess
0x18008265a  mov     rdx, rax
0x18008265d  lea     rcx, [rsp+448h+hProcess]
0x180082662  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180082667  mov     rcx, [rsp+448h+hProcess]; hProcess
0x18008266c  lea     rax, [rcx-1]
0x180082670  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180082674  ja      loc_180082C19
0x18008267a  mov     r9d, 104h; nSize
0x180082680  lea     r8, [rsp+448h+Filename]; lpFilename
0x180082688  xor     edx, edx; hModule
0x18008268a  call    cs:__imp_K32GetModuleFileNameExW
0x180082690  test    eax, eax
0x180082692  jz      loc_180082C19
0x180082698  lea     rdx, [rsp+448h+Filename]
0x1800826a0  lea     rcx, [rsp+448h+var_2B8]
0x1800826a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800826ad  nop
0x1800826ae  lea     rcx, aMsedgeExe; "msedge.exe"
0x1800826b5  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800826ba  mov     r9, rax
0x1800826bd  lea     rdx, aMsedgeExe; "msedge.exe"
0x1800826c4  lea     rcx, [rsp+448h+var_2B8]
0x1800826cc  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x1800826d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800826d5  jz      short loc_1800826DB
0x1800826d7  mov     byte ptr [rdi+74h], 1
0x1800826db  mov     r8b, 3
0x1800826de  mov     dl, 1
0x1800826e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ATFOI_Test@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ATFOI_Test@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ATFOI_Test> `wil::Feature<__WilFeatureTraits_Feature_ATFOI_Test>::GetImpl(void)'::`2'::impl
0x1800826e7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ATFOI_Test@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ATFOI_Test>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800826ec  nop
0x1800826ed  mov     [rsp+448h+var_408], r12
0x1800826f2  mov     [rsp+448h+var_418], r12
0x1800826f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MTestAbShSAFI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MTestAbShSAFI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbShSAFI> `wil::Feature<__WilFeatureTraits_Feature_MTestAbShSAFI>::GetImpl(void)'::`2'::impl
0x1800826fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MTestAbShSAFI@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbShSAFI>::__private_IsEnabled(void)
0x180082703  test    al, al
0x180082705  jz      loc_180082829
0x18008270b  mov     rcx, [rsp+448h+var_408]
0x180082710  mov     [rsp+448h+var_408], r12
0x180082715  test    rcx, rcx
0x180082718  jz      short loc_180082727
0x18008271a  mov     rax, [rcx]
0x18008271d  mov     rax, [rax+10h]
0x180082721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082726  nop
0x180082727  mov     [rsp+448h+var_2C0], r12
0x18008272f  mov     ebx, 54h ; 'T'
0x180082734  mov     r9d, ebx; unsigned int
0x180082737  lea     r8d, [rbx+1]; unsigned int
0x18008273b  lea     rdx, ?RuntimeClass_Windows_Internal_ApplicationTargetedFeatureDatabase_ApplicationTargetedFeatureConfig@@3QBGB; "Windows.Internal.ApplicationTargetedFea"...
0x180082742  lea     rcx, [rsp+448h+String]; hstringHeader
0x18008274a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18008274f  lea     r8, [rsp+448h+var_408]
0x180082754  lea     rdx, _GUID_7729cc91_abf4_56b1_99f0_ba2b6368b13e
0x18008275b  mov     rcx, [rsp+448h+var_2C0]
0x180082763  call    cs:__imp_RoGetActivationFactory
0x180082769  mov     esi, eax
0x18008276b  mov     rdx, [rsp+448h+var_418]
0x180082770  mov     [rsp+448h+var_418], r12
0x180082775  test    rdx, rdx
0x180082778  jz      short loc_18008278A
0x18008277a  mov     rcx, [rdx]
0x18008277d  mov     rax, [rcx+10h]
0x180082781  mov     rcx, rdx
0x180082784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082789  nop
0x18008278a  mov     [rsp+448h+var_2C0], r12
0x180082792  mov     r9d, 53h ; 'S'; unsigned int
0x180082798  mov     r8d, ebx; unsigned int
0x18008279b  lea     rdx, ?RuntimeClass_Windows_Internal_ApplicationTargetedFeatureDatabase_ApplicationTargetedFeatureQuery@@3QBGB; "Windows.Internal.ApplicationTargetedFea"...
0x1800827a2  lea     rcx, [rsp+448h+String]; hstringHeader
0x1800827aa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800827af  lea     r8, [rsp+448h+var_418]
0x1800827b4  lea     rdx, _GUID_fcc6aa4e_a393_5a0f_bbf3_6287d15539a1
0x1800827bb  mov     rcx, [rsp+448h+var_2C0]
0x1800827c3  call    cs:__imp_RoGetActivationFactory
0x1800827c9  mov     ebx, eax
0x1800827cb  test    esi, esi
0x1800827cd  js      short loc_1800827D7
0x1800827cf  test    eax, eax
0x1800827d1  jns     loc_180082895
0x1800827d7  mov     edx, 1
0x1800827dc  mov     rcx, rdi
0x1800827df  call    ?SetHandwritingStateImpl@HandwritingClient@ShellHandwriting@@AEAAJW4TfHandwritingState@@@Z; ShellHandwriting::HandwritingClient::SetHandwritingStateImpl(TfHandwritingState)
0x1800827e4  test    esi, esi
0x1800827e6  cmovs   ebx, esi
0x1800827e9  mov     ecx, ebx; int
0x1800827eb  call    ?ApplicationTargetedFeatureConfigInitialized@Client@ShellHandwriting@InputTraceLogging@2@SAXJ@Z; ShellHandwriting::InputTraceLogging::ShellHandwriting::Client::ApplicationTargetedFeatureConfigInitialized(long)
0x1800827f0  nop
0x1800827f1  lea     rcx, [rsp+448h+var_418]
0x1800827f6  call    ??1?$com_ptr_t@UITfContextView@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(void)
0x1800827fb  nop
0x1800827fc  lea     rcx, [rsp+448h+var_408]
0x180082801  call    ??1?$com_ptr_t@UITfContextView@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(void)
0x180082806  nop
0x180082807  xor     r8d, r8d
0x18008280a  mov     dl, 1
0x18008280c  lea     rcx, [rsp+448h+var_2B8]
0x180082814  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180082819  nop
0x18008281a  lea     rcx, [rsp+448h+hProcess]
0x18008281f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180082824  jmp     loc_180082C24
0x180082829  lea     rcx, [rsp+448h+var_410]
0x18008282e  call    ??$GetActivationFactory@UIApplicationTargetedFeatureConfigStatics@ApplicationTargetedFeatureDatabase@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIApplicationTargetedFeatureConfigStatics@ApplicationTargetedFeatureDatabase@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::ApplicationTargetedFeatureDatabase::IApplicationTargetedFeatureConfigStatics>(ushort const *)
0x180082833  mov     rdx, [rax]
0x180082836  mov     [rax], r12
0x180082839  mov     rcx, [rsp+448h+var_408]
0x18008283e  mov     [rsp+448h+var_408], rdx
0x180082843  test    rcx, rcx
0x180082846  jz      short loc_180082855
0x180082848  mov     rax, [rcx]
0x18008284b  mov     rax, [rax+10h]
0x18008284f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082854  nop
0x180082855  lea     rcx, [rsp+448h+var_410]
0x18008285a  call    ??1?$com_ptr_t@UITfContextView@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(void)
0x18008285f  lea     rcx, [rsp+448h+var_410]
0x180082864  call    ??$GetActivationFactory@UIApplicationTargetedFeatureQueryFactory@ApplicationTargetedFeatureDatabase@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIApplicationTargetedFeatureQueryFactory@ApplicationTargetedFeatureDatabase@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::ApplicationTargetedFeatureDatabase::IApplicationTargetedFeatureQueryFactory>(ushort const *)
0x180082869  mov     rdx, [rax]
0x18008286c  mov     [rax], r12
0x18008286f  mov     rcx, [rsp+448h+var_418]
0x180082874  mov     [rsp+448h+var_418], rdx
0x180082879  test    rcx, rcx
0x18008287c  jz      short loc_18008288B
0x18008287e  mov     rax, [rcx]
0x180082881  mov     rax, [rax+10h]
0x180082885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008288a  nop
0x18008288b  lea     rcx, [rsp+448h+var_410]
0x180082890  call    ??1?$com_ptr_t@UITfContextView@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITfContextView,wil::err_returncode_policy>::~com_ptr_t<ITfContextView,wil::err_returncode_policy>(void)
0x180082895  mov     rbx, [rsp+448h+var_408]
0x18008289a  test    rbx, rbx
0x18008289d  jz      loc_18008297D
0x1800828a3  cmp     [rsp+448h+var_418], r12
0x1800828a8  jz      loc_18008297D
0x1800828ae  mov     rax, [rbx]
0x1800828b1  mov     r14, [rax+30h]
0x1800828b5  lea     rsi, [rdi+0C0h]
0x1800828bc  mov     rcx, [rsi]
0x1800828bf  mov     [rsi], r12
0x1800828c2  test    rcx, rcx
0x1800828c5  jz      short loc_1800828D4
0x1800828c7  mov     r8, [rcx]
0x1800828ca  mov     rax, [r8+10h]
0x1800828ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800828d3  nop
0x1800828d4  mov     rdx, rsi
0x1800828d7  mov     rcx, rbx
0x1800828da  mov     rax, r14
0x1800828dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800828e2  test    eax, eax
0x1800828e4  js      loc_180082976
0x1800828ea  mov     r14, [rsp+448h+var_418]
0x1800828ef  mov     rax, [r14]
0x1800828f2  mov     r15, [rax+30h]
0x1800828f6  lea     rsi, [rdi+0C8h]
0x1800828fd  mov     rcx, [rsi]
0x180082900  mov     [rsi], r12
0x180082903  test    rcx, rcx
0x180082906  jz      short loc_180082915
0x180082908  mov     rax, [rcx]
0x18008290b  mov     rax, [rax+10h]
0x18008290f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082914  nop
0x180082915  lea     rax, [rsp+448h+var_2B8]
0x18008291d  cmp     [rsp+448h+var_2A0], 8
0x180082926  cmovnb  rax, [rsp+448h+var_2B8]
0x18008292f  mov     [rsp+448h+var_410], rax
0x180082934  lea     rdx, [rsp+448h+var_410]
0x180082939  lea     rcx, [rsp+448h+SystemInfo]
0x180082941  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180082946  nop
0x180082947  mov     rbx, [rax+18h]
0x18008294b  lea     rdx, off_180113190; "Shell::ShellHandwriting::InkAnywhere"
0x180082952  lea     rcx, [rsp+448h+String]
0x18008295a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008295f  nop
0x180082960  mov     r9, rsi
0x180082963  mov     r8, rbx
0x180082966  mov     rdx, [rax+18h]
0x18008296a  mov     rcx, r14
0x18008296d  mov     rax, r15
0x180082970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082975  nop
0x180082976  mov     ecx, eax; int
0x180082978  call    ?ApplicationTargetedFeatureConfigInitialized@Client@ShellHandwriting@InputTraceLogging@2@SAXJ@Z; ShellHandwriting::InputTraceLogging::ShellHandwriting::Client::ApplicationTargetedFeatureConfigInitialized(long)
0x18008297d  cmp     [rdi+21h], r12b
0x180082981  jnz     loc_180082A3E
0x180082987  mov     rcx, rdi; this
0x18008298a  call    ?IsApplicationOptedOut@HandwritingClient@ShellHandwriting@@AEAA_NXZ; ShellHandwriting::HandwritingClient::IsApplicationOptedOut(void)
0x18008298f  test    al, al
0x180082991  jz      loc_180082A3E
0x180082997  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MTestAbShAOOLU@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MTestAbShAOOLU@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbShAOOLU> `wil::Feature<__WilFeatureTraits_Feature_MTestAbShAOOLU>::GetImpl(void)'::`2'::impl
0x18008299e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MTestAbShAOOLU@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbShAOOLU>::__private_IsEnabled(void)
0x1800829a3  test    al, al
0x1800829a5  jz      loc_180082A31
0x1800829ab  xorps   xmm0, xmm0
0x1800829ae  movups  xmmword ptr [rsp+448h+SystemInfo], xmm0
0x1800829b6  movups  xmmword ptr [rsp+448h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800829be  movups  xmmword ptr [rsp+448h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800829c6  lea     rcx, [rsp+448h+SystemInfo]; lpSystemInfo
0x1800829ce  call    cs:__imp_GetSystemInfo
0x1800829d4  cmp     word ptr [rsp+448h+SystemInfo], 0Ch
0x1800829dd  jnz     short loc_180082A31
0x1800829df  lea     rcx, aWhatsappExe; "whatsapp.exe"
0x1800829e6  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800829eb  mov     r9, rax
0x1800829ee  lea     rdx, aWhatsappExe; "whatsapp.exe"
0x1800829f5  lea     rcx, [rsp+448h+var_2B8]
0x1800829fd  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x180082a02  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180082a06  jnz     short loc_180082A3E
0x180082a08  lea     rcx, aMessengerExe; "messenger.exe"
0x180082a0f  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180082a14  mov     r9, rax
0x180082a17  lea     rdx, aMessengerExe; "messenger.exe"
0x180082a1e  lea     rcx, [rsp+448h+var_2B8]
0x180082a26  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::find(ushort const *,unsigned __int64,unsigned __int64)
0x180082a2b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180082a2f  jnz     short loc_180082A3E
0x180082a31  mov     edx, 1
0x180082a36  mov     rcx, rdi
0x180082a39  call    ?SetHandwritingStateImpl@HandwritingClient@ShellHandwriting@@AEAAJW4TfHandwritingState@@@Z; ShellHandwriting::HandwritingClient::SetHandwritingStateImpl(TfHandwritingState)
0x180082a3e  mov     [rsp+448h+string], r12
0x180082a46  xor     r9d, r9d; unsigned int
0x180082a49  lea     r8d, [r9+1]; unsigned int
0x180082a4d  lea     rdx, lParam; sourceString
0x180082a54  lea     rcx, [rsp+448h+hstringHeader]; hstringHeader
0x180082a5c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180082a61  nop
0x180082a62  mov     rax, [rsp+448h+string]
0x180082a6a  mov     [rsp+448h+var_3E8], rax
0x180082a6f  mov     [rsp+448h+var_2C0], r12
0x180082a77  mov     r9d, 12h; unsigned int
0x180082a7d  lea     r8d, [r9+1]; unsigned int
0x180082a81  lea     rdx, aSupportedlangu; "SupportedLanguages"
0x180082a88  lea     rcx, [rsp+448h+String]; hstringHeader
0x180082a90  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180082a95  lea     r8, [rsp+448h+var_3E8]
0x180082a9a  lea     rdx, [rsp+448h+String]
0x180082aa2  mov     rcx, rdi
0x180082aa5  call    ?QueryTargetedFeatureData@HandwritingClient@ShellHandwriting@@AEAAJVHStringReference@Wrappers@WRL@Microsoft@@PEAPEAUHSTRING__@@@Z; ShellHandwriting::HandwritingClient::QueryTargetedFeatureData(Microsoft::WRL::Wrappers::HStringReference,HSTRING__ * *)
0x180082aaa  test    eax, eax
0x180082aac  js      loc_180082BA2
0x180082ab2  mov     rcx, [rsp+448h+string]; string
0x180082aba  call    cs:__imp_WindowsGetStringLen
0x180082ac0  mov     [rsp+448h+length], eax
0x180082ac4  lea     rdx, [rsp+448h+length]; length
0x180082ac9  mov     rcx, [rsp+448h+var_3E8]; string
0x180082ace  call    cs:__imp_WindowsGetStringRawBuffer
0x180082ad4  mov     rdx, rax
0x180082ad7  lea     rcx, [rsp+448h+SystemInfo]
0x180082adf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180082ae4  nop
0x180082ae5  lea     rdx, [rsp+448h+SystemInfo]
0x180082aed  lea     rcx, [rsp+448h+var_3D8]
0x180082af2  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::wstring const &,int)
0x180082af7  nop
0x180082af8  xor     r8d, r8d
0x180082afb  mov     dl, 1
0x180082afd  lea     rcx, [rsp+448h+SystemInfo]
0x180082b05  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180082b0a  mov     [rsp+448h+var_2C0], 7
0x180082b16  mov     [rsp+448h+var_2C8], r12
0x180082b1e  mov     word ptr [rsp+448h+String], r12w
0x180082b27  lea     rdx, [rsp+448h+String]
0x180082b2f  lea     rcx, [rsp+448h+var_3D8]
  ... truncated ...
```
