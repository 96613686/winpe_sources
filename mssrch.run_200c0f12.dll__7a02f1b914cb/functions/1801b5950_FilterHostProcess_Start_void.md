# FilterHostProcess::Start(void *)

- ea: `0x1801b5950`
- end: `0x1801b65d6`
- name: `?Start@FilterHostProcess@@UEAAJPEAX@Z`
- size: `3206`
- prototype: `__int64 __fastcall(FilterHostProcess *__hidden this, HANDLE hToken)`
- caller_count: `0`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000c760`
- `0x18000d15c`
- `0x18000f880`
- `0x1800269b0`
- `0x180026b58`
- `0x180027164`
- `0x18002bf00`
- `0x180052c14`
- `0x180054794`
- `0x180056610`
- `0x18005e788`
- `0x1800800f4`
- `0x18008a144`
- `0x18009aa14`
- `0x18009ae6c`
- `0x18009aec8`
- `0x18009f1f0`
- `0x1800b6f54`
- `0x1800bcaf0`
- `0x1800bd2f0`
- `0x1800db44c`
- `0x1800f8f24`
- `0x180106b9c`
- `0x180108ab8`
- `0x18010a494`
- `0x1801244c0`
- `0x18012540e`
- `0x1801aa5b4`
- `0x1801aaa78`
- `0x1801b4e68`
- `0x1801b504c`
- `0x1801b529c`
- `0x1801b590c`
- `0x1801b5950`
- `0x1801b6638`
- `0x1801b6674`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801b60e3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801b60e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801b60d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801b60d5`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1801b6226`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1801b6268`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1801b6226`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1801b6268`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1801b60a6`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1801b619d`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1801b60a6`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1801b619d`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801b61af`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801b6238`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801b627a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801b6361`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801b61af`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801b6238`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801b627a`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1801b6361`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801b6506`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1801b6506`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1801b62e6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1801b646d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1801b62e6`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1801b646d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801b5f8d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801b6169`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801b63fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801b5f8d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801b6169`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801b63fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801b6556`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801b6556`

## string_xrefs

- `0x1801b60fe`: `InitializeProcThreadAttributeList failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall FilterHostProcess::Start(FilterHostProcess *this, HANDLE hToken)
{
  void *v4; // rdx
  __int64 v5; // r8
  CSearchBinPathString *v7; // rdx
  int ProcessParam; // eax
  unsigned int v9; // ebx
  FilterHostProcess *v10; // rcx
  unsigned int v11; // r8d
  int v12; // eax
  unsigned int v13; // ebx
  FilterHostProcess *v14; // rcx
  unsigned int v15; // r8d
  int v16; // eax
  unsigned int v17; // ebx
  FilterHostProcess *v18; // rcx
  unsigned int v19; // r8d
  int v20; // eax
  unsigned int v21; // ebx
  FilterHostProcess *v22; // rcx
  unsigned int v23; // r8d
  __int64 v24; // r9
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  const wchar_t *v29; // rdx
  FilterHostUtils *v30; // rcx
  bool ShouldRunFilterHostInAppContainer; // si
  int IsSemanticIndexingAllowed; // eax
  const wchar_t *v33; // rdx
  int SearchFilterHostContainer; // eax
  unsigned int LastError; // ebx
  __int64 v36; // rdx
  const char *v37; // r9
  __int64 v38; // rdx
  unsigned int v39; // eax
  SIZE_T v40; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v42; // ebx
  __int64 v43; // rdx
  __int64 v44; // rax
  WCHAR *v45; // rax
  const char *v46; // r9
  HANDLE *v47; // rbx
  __int64 v48; // rcx
  DWORD v49; // ebx
  WCHAR *Buffer; // rax
  const char *v51; // r9
  __int64 v52; // rdx
  __int64 v53; // rcx
  int JobObjects; // eax
  void *v55; // rdx
  int v56; // esi
  HANDLE *cbSize; // [rsp+20h] [rbp-2F8h]
  int cbSizea; // [rsp+20h] [rbp-2F8h]
  int cbSizeb; // [rsp+20h] [rbp-2F8h]
  const char *lpPreviousValue; // [rsp+28h] [rbp-2F0h]
  char v61[8]; // [rsp+60h] [rbp-2B8h] BYREF
  int v62; // [rsp+68h] [rbp-2B0h] BYREF
  ULONG_PTR Size; // [rsp+70h] [rbp-2A8h] BYREF
  __int128 Value; // [rsp+78h] [rbp-2A0h] BYREF
  __int64 v65; // [rsp+88h] [rbp-290h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-288h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-268h] BYREF
  LPPROC_THREAD_ATTRIBUTE_LIST lpAttributeList; // [rsp+118h] [rbp-200h]
  _BYTE v69[56]; // [rsp+120h] [rbp-1F8h] BYREF
  __int64 v70; // [rsp+158h] [rbp-1C0h]
  _QWORD v71[2]; // [rsp+160h] [rbp-1B8h] BYREF
  __int64 v72; // [rsp+170h] [rbp-1A8h]
  __int16 v73; // [rsp+178h] [rbp-1A0h] BYREF
  _QWORD v74[3]; // [rsp+200h] [rbp-118h] BYREF
  wchar_t v75[68]; // [rsp+218h] [rbp-100h] BYREF
  HANDLE hTokena[2]; // [rsp+2A0h] [rbp-78h] BYREF
  struct _PROCESS_INFORMATION lpProcessInformation; // [rsp+2B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  wil::EnterCriticalSection(v61, (char *)this + 88);
  if ( (byte_1802DA181 & 8) != 0 )
  {
    cbSize = hTokena;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Search_Core_Context,
      &MSSearchTraceId_FilterHostStarting,
      v5,
      1);
  }
  if ( (unsigned __int64)(*((_QWORD *)this + 3) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_4;
  wil::details::ResetEvent(*((wil::details **)this + 6), v4);
  memset_0(&StartupInfo, 0, 0x70u);
  StartupInfo.cb = 112;
  v71[1] = &v73;
  v72 = 65;
  v73 = 0;
  v71[0] = &CCICommonPathString::`vftable';
  CLMString::CLMString((CLMString *)v74, 0x41u, v75, 0x22u, (unsigned int)cbSize);
  v74[0] = &CCICommonPathString::`vftable';
  TLMString<192,64,32767>::operator=(v71, v74);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(v74);
  v7 = CSearchBinPathString::CSearchBinPathString((CSearchBinPathString *)v74, L"SearchFilterHost.exe");
  CLMString::operator+=(v71, v7);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(v74);
  (*(void (__fastcall **)(_QWORD *, const char *, _QWORD, __int64))(v71[0] + 24LL))(
    v71,
    "\" ",
    HIDWORD(v72),
    0xFFFFFFFFLL);
  ProcessParam = CPhMultiArch::MarshalCreateProcessParam((CLMString *)v71);
  v9 = ProcessParam;
  if ( ProcessParam < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
      (const char *)(unsigned int)ProcessParam,
      cbSizea);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
    CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
    return v9;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix54451079>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_BugFix54451079>::GetImpl'::`2'::impl)
    && !g_pGatheringService )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
      (const char *)0x80040D23LL,
      cbSizea);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
    CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
    return 2147749155LL;
  }
  v12 = FilterHostProcess::PrintHandle(
          v10,
          (wchar_t *)&lpProcessInformation,
          v11,
          *((void **)g_pGatheringService + 519));
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
      (const char *)(unsigned int)v12,
      cbSizea);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
    CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
    return v13;
  }
  CLMString::Append((CLMString *)v71, (const wchar_t *)&lpProcessInformation, 0xFFFFFFFF);
  CLMString::Append((CLMString *)v71, L" ", 0xFFFFFFFF);
  v16 = FilterHostProcess::PrintHandle(v14, (wchar_t *)&lpProcessInformation, v15, *((void **)this + 6));
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
      (const char *)(unsigned int)v16,
      cbSizea);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
    CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
    return v17;
  }
  CLMString::Append((CLMString *)v71, (const wchar_t *)&lpProcessInformation, 0xFFFFFFFF);
  CLMString::Append((CLMString *)v71, L" ", 0xFFFFFFFF);
  v20 = FilterHostProcess::PrintHandle(v18, (wchar_t *)&lpProcessInformation, v19, *((void **)this + 5));
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
      (const char *)(unsigned int)v20,
      cbSizea);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
    CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
    return v21;
  }
  CLMString::Append((CLMString *)v71, (const wchar_t *)&lpProcessInformation, 0xFFFFFFFF);
  CLMString::Append((CLMString *)v71, L" ", 0xFFFFFFFF);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix54451079>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_BugFix54451079>::GetImpl'::`2'::impl) )
  {
    if ( !g_pGatheringService )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x182,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
        (const char *)0x80040D23LL,
        cbSizea);
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
      CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
      return 2147749155LL;
    }
    v24 = *((_QWORD *)g_pGatheringService + 500);
    if ( !v24 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
        (const char *)0x80040D23LL,
        cbSizea);
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
      CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
      return 2147749155LL;
    }
    v25 = FilterHostProcess::PrintHandle(v22, (wchar_t *)&lpProcessInformation, v23, *(void **)(v24 + 768));
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
        (const char *)(unsigned int)v25,
        cbSizea);
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
      CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
      return v26;
    }
  }
  else
  {
    v27 = FilterHostProcess::PrintHandle(
            v22,
            (wchar_t *)&lpProcessInformation,
            v23,
            *(void **)(*((_QWORD *)g_pGatheringService + 500) + 768LL));
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18A,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
        (const char *)(unsigned int)v27,
        cbSizea);
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
      CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
      return v28;
    }
  }
  CLMString::Append((CLMString *)v71, (const wchar_t *)&lpProcessInformation, 0xFFFFFFFF);
  CLMString::Append((CLMString *)v71, L" ", 0xFFFFFFFF);
  if ( *((_QWORD *)this + 25) <= 7u )
    v29 = (const wchar_t *)((char *)this + 176);
  else
    v29 = (const wchar_t *)*((_QWORD *)this + 22);
  CLMString::Append((CLMString *)v71, v29, 0xFFFFFFFF);
  ShouldRunFilterHostInAppContainer = FilterHostUtils::ShouldRunFilterHostInAppContainer(v30);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687629>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59687629>::GetImpl'::`2'::impl) )
  {
    if ( !ShouldRunFilterHostInAppContainer )
      goto LABEL_67;
    InitOnceExecuteOnce(
      &g_initOnceDedicatedFilterIsolationMode,
      _lambda_5d22c8c21337a65e6890c9366d96db22_::_lambda_invoker_cdecl_,
      0,
      0);
    if ( !g_isDedicatedFilterIsolationModeEnabled
      || (unsigned __int8)std::operator!=<wchar_t>((char *)this + 176, L"{1295340B-BF50-4A88-BB2F-287E0B9B0016}") )
    {
      ShouldRunFilterHostInAppContainer = 0;
    }
  }
  if ( !ShouldRunFilterHostInAppContainer )
  {
LABEL_67:
    StartupInfo.lpDesktop = (LPWSTR)((unsigned __int64)L"mssrestricteddesk" & -(__int64)(*((_BYTE *)this + 168) != 0));
    memset(&lpProcessInformation, 0, sizeof(lpProcessInformation));
    InitOnceExecuteOnce(
      &g_initOnceOnPerUserCatalogCheck,
      _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
      0,
      0);
    if ( g_isPerUserCatalogEnabled || (v49 = 524300, IsControlIndexingOnBatteryEnabled()) )
      v49 = 17301516;
    Buffer = CLMString::GetBuffer((CLMString *)v71, 0);
    if ( !CreateProcessAsUserW(hToken, 0, Buffer, 0, 0, 1, v49, 0, 0, &StartupInfo, &lpProcessInformation) )
    {
      v52 = 613;
      goto LABEL_78;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 24,
      lpProcessInformation.hProcess);
    *((_DWORD *)this + 20) = lpProcessInformation.dwProcessId;
    v47 = (HANDLE *)((char *)this + 32);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 32,
      lpProcessInformation.hThread);
    if ( (byte_1802DA181 & 8) != 0 )
      McTemplateU0q_EventWriteTransfer(v53, &MSSearchTraceId_FilterHostStarted, lpProcessInformation.dwProcessId);
LABEL_74:
    JobObjects = FilterHostProcess::CreateJobObjects(this);
    v56 = JobObjects;
    if ( JobObjects < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26E,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
        (const char *)(unsigned int)JobObjects,
        cbSizeb);
      LastError = v56;
      goto LABEL_79;
    }
    wil::details::ResetEvent(*((wil::details **)this + 5), v55);
    if ( ResumeThread(*v47) != -1 )
    {
      *((_DWORD *)this + 18) = GetTickCount();
      TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
      CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
LABEL_4:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
      return 0;
    }
    v52 = 628;
LABEL_78:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v52,
                  (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
                  v51);
    goto LABEL_79;
  }
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_CreateSearchFilterHostLPACTest_attributes,tip2::test_data_basic>>>((struct wil::details::IFailureCallback *)v69);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58104295>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_58104295>::GetImpl'::`2'::impl)
    && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59687629>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_59687629>::GetImpl'::`2'::impl) )
  {
    CLMString::Append((CLMString *)v71, L" ", 0xFFFFFFFF);
    IsSemanticIndexingAllowed = GetIsSemanticIndexingAllowed();
    v33 = L"1";
    if ( !IsSemanticIndexingAllowed )
      v33 = L"0";
    CLMString::Append((CLMString *)v71, v33, 0xFFFFFFFF);
  }
  SearchFilterHostContainer = FilterHostProcess::AddRequiredCapabilityAttributes(this);
  LastError = SearchFilterHostContainer;
  if ( SearchFilterHostContainer >= 0 )
  {
    SearchFilterHostContainer = FilterHostProcess::CreateSearchFilterHostContainer(this);
    LastError = SearchFilterHostContainer;
    if ( SearchFilterHostContainer < 0 )
    {
      v36 = 450;
      goto LABEL_43;
    }
    Value = 0;
    v65 = 0;
    Size = 0;
    v62 = 1;
    StartupInfo.cb = 112;
    if ( InitializeProcThreadAttributeList(0, 2u, 0, &Size) )
    {
      v38 = 460;
LABEL_46:
      v39 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)v38,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
              v37);
LABEL_47:
      LastError = v39;
      goto LABEL_63;
    }
    v40 = Size;
    ProcessHeap = GetProcessHeap();
    lpAttributeList = (LPPROC_THREAD_ATTRIBUTE_LIST)HeapAlloc(ProcessHeap, 0, v40);
    if ( !lpAttributeList )
    {
      v39 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x1D2,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
              (const char *)8,
              (unsigned int)"InitializeProcThreadAttributeList failed",
              lpPreviousValue);
      goto LABEL_47;
    }
    StartupInfo.lpDesktop = (LPWSTR)((unsigned __int64)L"mssrestricteddesk" & -(__int64)(*((_BYTE *)this + 168) != 0));
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    InitOnceExecuteOnce(
      &g_initOnceOnPerUserCatalogCheck,
      _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
      0,
      0);
    if ( g_isPerUserCatalogEnabled || (v42 = 524300, IsControlIndexingOnBatteryEnabled()) )
      v42 = 17301516;
    if ( !InitializeProcThreadAttributeList(lpAttributeList, 2u, 0, &Size) )
    {
      DeleteProcThreadAttributeList(lpAttributeList);
      v38 = 482;
      goto LABEL_46;
    }
    *(_QWORD *)&Value = *((_QWORD *)this + 28);
    v43 = (__int64)(*((_QWORD *)this + 30) - *((_QWORD *)this + 29)) >> 4;
    v44 = *((_QWORD *)&Value + 1);
    if ( v43 )
      v44 = *((_QWORD *)this + 29);
    *((_QWORD *)&Value + 1) = v44;
    LODWORD(v65) = v43;
    if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x20009u, &Value, 0x18u, 0, 0) )
    {
      DeleteProcThreadAttributeList(lpAttributeList);
      v38 = 502;
      goto LABEL_46;
    }
    if ( !UpdateProcThreadAttribute(lpAttributeList, 0, 0x2000Fu, &v62, 4u, 0, 0) )
    {
      DeleteProcThreadAttributeList(lpAttributeList);
      v38 = 521;
      goto LABEL_46;
    }
    hTokena[0] = 0;
    v45 = CLMString::GetBuffer((CLMString *)v71, 0);
    if ( !CreateProcessAsUserW(hTokena[0], 0, v45, 0, 0, 1, v42, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x242,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
                    v46);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hTokena);
      goto LABEL_63;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 24,
      ProcessInformation.hProcess);
    *((_DWORD *)this + 20) = ProcessInformation.dwProcessId;
    v47 = (HANDLE *)((char *)this + 32);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 32,
      ProcessInformation.hThread);
    DeleteProcThreadAttributeList(lpAttributeList);
    tip2::details::shared_data<0,0,1>::complete_without_lock(v70 + 8);
    if ( (byte_1802DA181 & 8) != 0 )
      McTemplateU0q_EventWriteTransfer(v48, &MSSearchTraceId_FilterHostStarted, ProcessInformation.dwProcessId);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(hTokena);
    tip2::test_watcher<tip2::details::merged_data<_tip_CreateSearchFilterHostLPACTest_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_CreateSearchFilterHostLPACTest_attributes,tip2::test_data_basic>>(v69);
    goto LABEL_74;
  }
  v36 = 449;
LABEL_43:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v36,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\filterhostprocess.cxx",
    (const char *)(unsigned int)SearchFilterHostContainer,
    cbSizea);
LABEL_63:
  tip2::test_watcher<tip2::details::merged_data<_tip_CreateSearchFilterHostLPACTest_attributes,tip2::test_data_basic>>::~test_watcher<tip2::details::merged_data<_tip_CreateSearchFilterHostLPACTest_attributes,tip2::test_data_basic>>(v69);
LABEL_79:
  TLMString<64,64,32767>::~TLMString<64,64,32767>(v71);
  CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper((CPhMultiArch::StartupInfoWrapper *)&StartupInfo);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(v61);
  return LastError;
}

```

## disassembly

```asm
0x1801b5950  mov     [rsp+arg_10], rbx
0x1801b5955  mov     [rsp+arg_18], rsi
0x1801b595a  push    rdi
0x1801b595b  push    r12
0x1801b595d  push    r13
0x1801b595f  push    r14
0x1801b5961  push    r15
0x1801b5963  sub     rsp, 2F0h
0x1801b596a  mov     rax, cs:__security_cookie
0x1801b5971  xor     rax, rsp
0x1801b5974  mov     [rsp+318h+var_38], rax
0x1801b597c  mov     r15, rdx
0x1801b597f  mov     rdi, rcx
0x1801b5982  lea     rdx, [rcx+58h]
0x1801b5986  lea     rcx, [rsp+318h+var_2B8]
0x1801b598b  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1801b5990  nop
0x1801b5991  test    cs:byte_1802DA181, 8
0x1801b5998  jz      short loc_1801B59C0
0x1801b599a  lea     rax, [rsp+318h+hToken]
0x1801b59a2  mov     [rsp+318h+cbSize], rax; int
0x1801b59a7  mov     r9d, 1
0x1801b59ad  lea     rdx, MSSearchTraceId_FilterHostStarting
0x1801b59b4  lea     rcx, Microsoft_Windows_Search_Core_Context
0x1801b59bb  call    McGenEventWrite_EventWriteTransfer
0x1801b59c0  lea     r14, [rdi+18h]
0x1801b59c4  mov     rax, [r14]
0x1801b59c7  dec     rax
0x1801b59ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801b59ce  ja      short loc_1801B59E1
0x1801b59d0  lea     rcx, [rsp+318h+var_2B8]
0x1801b59d5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1801b59da  xor     eax, eax
0x1801b59dc  jmp     loc_1801B65A9
0x1801b59e1  mov     rcx, [rdi+30h]; this
0x1801b59e5  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x1801b59ea  mov     ebx, 70h ; 'p'
0x1801b59ef  mov     r8d, ebx; Size
0x1801b59f2  xor     edx, edx; Val
0x1801b59f4  lea     rcx, [rsp+318h+StartupInfo]; void *
0x1801b59fc  call    memset_0
0x1801b5a01  mov     [rsp+318h+StartupInfo.cb], ebx
0x1801b5a08  lea     rax, [rsp+318h+var_1A0]
0x1801b5a10  mov     [rsp+318h+var_1B0], rax
0x1801b5a18  lea     edx, [rbx-2Fh]; unsigned int
0x1801b5a1b  mov     [rsp+318h+var_1A8], rdx
0x1801b5a23  xor     r12d, r12d
0x1801b5a26  mov     [rsp+318h+var_1A0], r12w
0x1801b5a2f  lea     rbx, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1801b5a36  mov     [rsp+318h+var_1B8], rbx
0x1801b5a3e  lea     r9d, [rdx-1Fh]; wchar_t
0x1801b5a42  lea     r8, [rsp+318h+var_100]; wchar_t *
0x1801b5a4a  lea     rcx, [rsp+318h+var_118]; this
0x1801b5a52  call    ??0CLMString@@IEAA@IPEA_W_WI@Z; CLMString::CLMString(uint,wchar_t *,wchar_t,uint)
0x1801b5a57  mov     [rsp+318h+var_118], rbx
0x1801b5a5f  lea     rdx, [rsp+318h+var_118]
0x1801b5a67  lea     rcx, [rsp+318h+var_1B8]
0x1801b5a6f  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x1801b5a74  nop
0x1801b5a75  lea     rcx, [rsp+318h+var_118]
0x1801b5a7d  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5a82  lea     rdx, aSearchfilterho; "SearchFilterHost.exe"
0x1801b5a89  lea     rcx, [rsp+318h+var_118]; this
0x1801b5a91  call    ??0CSearchBinPathString@@QEAA@PEB_W@Z; CSearchBinPathString::CSearchBinPathString(wchar_t const *)
0x1801b5a96  nop
0x1801b5a97  mov     rdx, rax
0x1801b5a9a  lea     rcx, [rsp+318h+var_1B8]
0x1801b5aa2  call    ??YCLMString@@QEAAXAEBV0@@Z; CLMString::operator+=(CLMString const &)
0x1801b5aa7  nop
0x1801b5aa8  lea     rcx, [rsp+318h+var_118]
0x1801b5ab0  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5ab5  mov     rax, [rsp+318h+var_1B8]
0x1801b5abd  or      r13d, 0FFFFFFFFh
0x1801b5ac1  mov     r9d, r13d
0x1801b5ac4  mov     r8d, dword ptr [rsp+318h+var_1A8+4]
0x1801b5acc  lea     rdx, asc_1802808F4; "\" "
0x1801b5ad3  lea     rcx, [rsp+318h+var_1B8]
0x1801b5adb  mov     rax, [rax+18h]
0x1801b5adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5ae4  lea     r8, [rdi+0D0h]
0x1801b5aeb  lea     rdx, [rsp+318h+StartupInfo]
0x1801b5af3  lea     rcx, [rsp+318h+var_1B8]; this
0x1801b5afb  call    ?MarshalCreateProcessParam@CPhMultiArch@@SAJAEAV?$TLMString@$0EA@$0EA@$0HPPP@@@PEAVStartupInfoWrapper@1@PEAG@Z; CPhMultiArch::MarshalCreateProcessParam(TLMString<64,64,32767> &,CPhMultiArch::StartupInfoWrapper *,ushort *)
0x1801b5b00  mov     ebx, eax
0x1801b5b02  test    eax, eax
0x1801b5b04  jns     short loc_1801B5B50
0x1801b5b06  mov     rcx, [rsp+318h]; this
0x1801b5b0e  mov     r9d, eax; char *
0x1801b5b11  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801b5b18  mov     edx, 167h; void *
0x1801b5b1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5b22  nop
0x1801b5b23  lea     rcx, [rsp+318h+var_1B8]
0x1801b5b2b  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5b30  nop
0x1801b5b31  lea     rcx, [rsp+318h+StartupInfo]; this
0x1801b5b39  call    ??1StartupInfoWrapper@CPhMultiArch@@QEAA@XZ; CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper(void)
0x1801b5b3e  nop
0x1801b5b3f  lea     rcx, [rsp+318h+var_2B8]
0x1801b5b44  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1801b5b49  mov     eax, ebx
0x1801b5b4b  jmp     loc_1801B65A9
0x1801b5b50  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix54451079@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix54451079@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix54451079> `wil::Feature<__WilFeatureTraits_Feature_BugFix54451079>::GetImpl(void)'::`2'::impl
0x1801b5b57  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix54451079@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix54451079>::__private_IsEnabled(void)
0x1801b5b5c  mov     r9, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1801b5b63  test    al, al
0x1801b5b65  jz      short loc_1801B5BBB
0x1801b5b67  test    r9, r9
0x1801b5b6a  jnz     short loc_1801B5BBB
0x1801b5b6c  mov     rcx, [rsp+318h]; this
0x1801b5b74  mov     ebx, 80040D23h
0x1801b5b79  mov     r9d, ebx; char *
0x1801b5b7c  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801b5b83  mov     edx, 16Dh; void *
0x1801b5b88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5b8d  nop
0x1801b5b8e  lea     rcx, [rsp+318h+var_1B8]
0x1801b5b96  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5b9b  nop
0x1801b5b9c  lea     rcx, [rsp+318h+StartupInfo]; this
0x1801b5ba4  call    ??1StartupInfoWrapper@CPhMultiArch@@QEAA@XZ; CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper(void)
0x1801b5ba9  nop
0x1801b5baa  lea     rcx, [rsp+318h+var_2B8]
0x1801b5baf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1801b5bb4  mov     eax, ebx
0x1801b5bb6  jmp     loc_1801B65A9
0x1801b5bbb  mov     r9, [r9+1038h]; void *
0x1801b5bc2  lea     rdx, [rsp+318h+var_68]; wchar_t *
0x1801b5bca  call    ?PrintHandle@FilterHostProcess@@AEAAJPEA_WKPEAX@Z; FilterHostProcess::PrintHandle(wchar_t *,ulong,void *)
0x1801b5bcf  mov     ebx, eax
0x1801b5bd1  test    eax, eax
0x1801b5bd3  jns     short loc_1801B5C1F
0x1801b5bd5  mov     rcx, [rsp+318h]; this
0x1801b5bdd  mov     r9d, eax; char *
0x1801b5be0  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801b5be7  mov     edx, 171h; void *
0x1801b5bec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5bf1  nop
0x1801b5bf2  lea     rcx, [rsp+318h+var_1B8]
0x1801b5bfa  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5bff  nop
0x1801b5c00  lea     rcx, [rsp+318h+StartupInfo]; this
0x1801b5c08  call    ??1StartupInfoWrapper@CPhMultiArch@@QEAA@XZ; CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper(void)
0x1801b5c0d  nop
0x1801b5c0e  lea     rcx, [rsp+318h+var_2B8]
0x1801b5c13  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1801b5c18  mov     eax, ebx
0x1801b5c1a  jmp     loc_1801B65A9
0x1801b5c1f  mov     r8d, r13d; unsigned int
0x1801b5c22  lea     rdx, [rsp+318h+var_68]; wchar_t *
0x1801b5c2a  lea     rcx, [rsp+318h+var_1B8]; this
0x1801b5c32  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801b5c37  mov     r8d, r13d; unsigned int
0x1801b5c3a  lea     rsi, asc_180280A20; " "
0x1801b5c41  mov     rdx, rsi; wchar_t *
0x1801b5c44  lea     rcx, [rsp+318h+var_1B8]; this
0x1801b5c4c  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801b5c51  mov     r9, [rdi+30h]; void *
0x1801b5c55  lea     rdx, [rsp+318h+var_68]; wchar_t *
0x1801b5c5d  call    ?PrintHandle@FilterHostProcess@@AEAAJPEA_WKPEAX@Z; FilterHostProcess::PrintHandle(wchar_t *,ulong,void *)
0x1801b5c62  mov     ebx, eax
0x1801b5c64  test    eax, eax
0x1801b5c66  jns     short loc_1801B5CB2
0x1801b5c68  mov     rcx, [rsp+318h]; this
0x1801b5c70  mov     r9d, eax; char *
0x1801b5c73  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801b5c7a  mov     edx, 176h; void *
0x1801b5c7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5c84  nop
0x1801b5c85  lea     rcx, [rsp+318h+var_1B8]
0x1801b5c8d  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5c92  nop
0x1801b5c93  lea     rcx, [rsp+318h+StartupInfo]; this
0x1801b5c9b  call    ??1StartupInfoWrapper@CPhMultiArch@@QEAA@XZ; CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper(void)
0x1801b5ca0  nop
0x1801b5ca1  lea     rcx, [rsp+318h+var_2B8]
0x1801b5ca6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1801b5cab  mov     eax, ebx
0x1801b5cad  jmp     loc_1801B65A9
0x1801b5cb2  mov     r8d, r13d; unsigned int
0x1801b5cb5  lea     rdx, [rsp+318h+var_68]; wchar_t *
0x1801b5cbd  lea     rcx, [rsp+318h+var_1B8]; this
0x1801b5cc5  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801b5cca  mov     r8d, r13d; unsigned int
0x1801b5ccd  mov     rdx, rsi; wchar_t *
0x1801b5cd0  lea     rcx, [rsp+318h+var_1B8]; this
0x1801b5cd8  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801b5cdd  mov     r9, [rdi+28h]; void *
0x1801b5ce1  lea     rdx, [rsp+318h+var_68]; wchar_t *
0x1801b5ce9  call    ?PrintHandle@FilterHostProcess@@AEAAJPEA_WKPEAX@Z; FilterHostProcess::PrintHandle(wchar_t *,ulong,void *)
0x1801b5cee  mov     ebx, eax
0x1801b5cf0  test    eax, eax
0x1801b5cf2  jns     short loc_1801B5D3E
0x1801b5cf4  mov     rcx, [rsp+318h]; this
0x1801b5cfc  mov     r9d, eax; char *
0x1801b5cff  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801b5d06  mov     edx, 17Bh; void *
0x1801b5d0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5d10  nop
0x1801b5d11  lea     rcx, [rsp+318h+var_1B8]
0x1801b5d19  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5d1e  nop
0x1801b5d1f  lea     rcx, [rsp+318h+StartupInfo]; this
0x1801b5d27  call    ??1StartupInfoWrapper@CPhMultiArch@@QEAA@XZ; CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper(void)
0x1801b5d2c  nop
0x1801b5d2d  lea     rcx, [rsp+318h+var_2B8]
0x1801b5d32  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1801b5d37  mov     eax, ebx
0x1801b5d39  jmp     loc_1801B65A9
0x1801b5d3e  mov     r8d, r13d; unsigned int
0x1801b5d41  lea     rdx, [rsp+318h+var_68]; wchar_t *
0x1801b5d49  lea     rcx, [rsp+318h+var_1B8]; this
0x1801b5d51  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801b5d56  mov     r8d, r13d; unsigned int
0x1801b5d59  mov     rdx, rsi; wchar_t *
0x1801b5d5c  lea     rcx, [rsp+318h+var_1B8]; this
0x1801b5d64  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1801b5d69  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix54451079@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix54451079@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix54451079> `wil::Feature<__WilFeatureTraits_Feature_BugFix54451079>::GetImpl(void)'::`2'::impl
0x1801b5d70  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix54451079@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix54451079>::__private_IsEnabled(void)
0x1801b5d75  test    al, al
0x1801b5d77  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1801b5d7e  jz      loc_1801B5E9B
0x1801b5d84  test    rax, rax
0x1801b5d87  jnz     short loc_1801B5DD8
0x1801b5d89  mov     rcx, [rsp+318h]; this
0x1801b5d91  mov     ebx, 80040D23h
0x1801b5d96  mov     r9d, ebx; char *
0x1801b5d99  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801b5da0  mov     edx, 182h; void *
0x1801b5da5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5daa  nop
0x1801b5dab  lea     rcx, [rsp+318h+var_1B8]
0x1801b5db3  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5db8  nop
0x1801b5db9  lea     rcx, [rsp+318h+StartupInfo]; this
0x1801b5dc1  call    ??1StartupInfoWrapper@CPhMultiArch@@QEAA@XZ; CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper(void)
0x1801b5dc6  nop
0x1801b5dc7  lea     rcx, [rsp+318h+var_2B8]
0x1801b5dcc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1801b5dd1  mov     eax, ebx
0x1801b5dd3  jmp     loc_1801B65A9
0x1801b5dd8  mov     r9, [rax+0FA0h]
0x1801b5ddf  test    r9, r9
0x1801b5de2  jnz     short loc_1801B5E33
0x1801b5de4  mov     rcx, [rsp+318h]; this
0x1801b5dec  mov     ebx, 80040D23h
0x1801b5df1  mov     r9d, ebx; char *
0x1801b5df4  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801b5dfb  mov     edx, 184h; void *
0x1801b5e00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5e05  nop
0x1801b5e06  lea     rcx, [rsp+318h+var_1B8]
0x1801b5e0e  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5e13  nop
0x1801b5e14  lea     rcx, [rsp+318h+StartupInfo]; this
0x1801b5e1c  call    ??1StartupInfoWrapper@CPhMultiArch@@QEAA@XZ; CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper(void)
0x1801b5e21  nop
0x1801b5e22  lea     rcx, [rsp+318h+var_2B8]
0x1801b5e27  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1801b5e2c  mov     eax, ebx
0x1801b5e2e  jmp     loc_1801B65A9
0x1801b5e33  mov     r9, [r9+300h]; void *
0x1801b5e3a  lea     rdx, [rsp+318h+var_68]; wchar_t *
0x1801b5e42  call    ?PrintHandle@FilterHostProcess@@AEAAJPEA_WKPEAX@Z; FilterHostProcess::PrintHandle(wchar_t *,ulong,void *)
0x1801b5e47  mov     ebx, eax
0x1801b5e49  test    eax, eax
0x1801b5e4b  jns     loc_1801B5F06
0x1801b5e51  mov     rcx, [rsp+318h]; this
0x1801b5e59  mov     r9d, eax; char *
0x1801b5e5c  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801b5e63  mov     edx, 185h; void *
0x1801b5e68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5e6d  nop
0x1801b5e6e  lea     rcx, [rsp+318h+var_1B8]
0x1801b5e76  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5e7b  nop
0x1801b5e7c  lea     rcx, [rsp+318h+StartupInfo]; this
0x1801b5e84  call    ??1StartupInfoWrapper@CPhMultiArch@@QEAA@XZ; CPhMultiArch::StartupInfoWrapper::~StartupInfoWrapper(void)
0x1801b5e89  nop
0x1801b5e8a  lea     rcx, [rsp+318h+var_2B8]
0x1801b5e8f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1801b5e94  mov     eax, ebx
0x1801b5e96  jmp     loc_1801B65A9
0x1801b5e9b  mov     r9, [rax+0FA0h]
0x1801b5ea2  mov     r9, [r9+300h]; void *
0x1801b5ea9  lea     rdx, [rsp+318h+var_68]; wchar_t *
0x1801b5eb1  call    ?PrintHandle@FilterHostProcess@@AEAAJPEA_WKPEAX@Z; FilterHostProcess::PrintHandle(wchar_t *,ulong,void *)
0x1801b5eb6  mov     ebx, eax
0x1801b5eb8  test    eax, eax
0x1801b5eba  jns     short loc_1801B5F06
0x1801b5ebc  mov     rcx, [rsp+318h]; this
0x1801b5ec4  mov     r9d, eax; char *
0x1801b5ec7  lea     r8, aOnecoreuapBase_53; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801b5ece  mov     edx, 18Ah; void *
0x1801b5ed3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5ed8  nop
0x1801b5ed9  lea     rcx, [rsp+318h+var_1B8]
0x1801b5ee1  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x1801b5ee6  nop
0x1801b5ee7  lea     rcx, [rsp+318h+StartupInfo]; this
  ... truncated ...
```
