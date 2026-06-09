# CCbsStoreRepairExecutionObject::GetRepairableProducts(BUCL::CVector<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>,BUCL::Rtl::CCallDisposition> *)

- ea: `0x18018df84`
- end: `0x18018ebea`
- name: `?GetRepairableProducts@CCbsStoreRepairExecutionObject@@IEAAJPEAV?$CVector@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@VCCallDisposition@Rtl@BUCL@@@BUCL@@@Z`
- size: `3174`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18018add4`

## callees

- `0x180010cc0`
- `0x180012fe4`
- `0x180013250`
- `0x1800150c0`
- `0x180028e24`
- `0x18002de30`
- `0x18002e0d0`
- `0x180049ec0`
- `0x180059a00`
- `0x18005ec58`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800d2650`
- `0x1800d26c8`
- `0x1800eb920`
- `0x18018df84`
- `0x1801c1498`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18018e423`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18018e4a7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18018e423`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18018e4a7`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18018e194`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18018e194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018e0dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018e0dd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18018e0b8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18018e0b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e50d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e528`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e5a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e5bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e67f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e6b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e6ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018ea39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018eabd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e50d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e528`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e5a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e5bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e67f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e6b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018e6ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018ea39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018eabd`

## string_xrefs

- `0x18018e9a6`: `Failed to get task allocator.`
- `0x18018e063`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018e15d`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018e667`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018e7ce`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018e889`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018e8f4`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018ea1b`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018eb67`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018e3ce`: `Repairable`
- `0x18018e329`: `Failed to get installed product count`
- `0x18018e2b7`: `Failed to enumerate installed product`
- `0x18018e7f6`: `Failed to get Repairable product name.`
- `0x18018e84b`: `Failed to get value of Repairable`
- `0x18018e074`: `system32\ProductEnumerator.dll`
- `0x18018e094`: `system32\ProductEnumerator.dll`
- `0x18018eb29`: `Offline retrieval of repairable products is not currently supported.`
- `0x18018e237`: `Failed to create product enumerator`
- `0x18018e18d`: `PE_CreateProductEnumerator`
- `0x18018e0fc`: `Failed to load ProductEnumerator.dll.`
- `0x18018e926`: `Repairable primary OS product not found.`

## pseudocode

```c
__int64 __fastcall CCbsStoreRepairExecutionObject::GetRepairableProducts(__int64 a1, __int64 a2)
{
  CCbsSession *v2; // rcx
  CCbsSession *v4; // rcx
  _BYTE *v5; // r8
  CCbsSession *v6; // rcx
  int OfflineWindowsDirectory; // eax
  int v8; // ebx
  int v9; // edx
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  int v12; // eax
  int WindowsDirectory; // eax
  HMODULE LibraryW; // rax
  signed int LastError; // ebx
  int v16; // edx
  unsigned int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  void (*v20)(void); // rax
  FARPROC ProcAddress; // rbx
  int v22; // edx
  __int64 v23; // rax
  int v24; // eax
  int v25; // edx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64); // rbx
  __int64 v28; // rax
  int v29; // eax
  int v30; // edx
  int v31; // eax
  int v32; // edx
  char v33; // r15
  unsigned int v34; // esi
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, _QWORD, __int64); // rbx
  __int64 v37; // rax
  __int64 v38; // rdi
  int (__fastcall *v39)(__int64, const wchar_t *, __int64); // rbx
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, __int64); // rbx
  __int64 v43; // rax
  __int64 v44; // rdi
  int (__fastcall *v45)(__int64, const wchar_t *, __int64); // rbx
  __int64 v46; // rax
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, __int64); // rbx
  __int64 v49; // rax
  __int64 v50; // rdi
  __int64 (__fastcall *v51)(__int64, __int64); // rbx
  __int64 v52; // rax
  int *v53; // rax
  __int64 v54; // rdi
  __int64 (__fastcall *v55)(__int64, __int64); // rbx
  __int64 v56; // rax
  int *v57; // rax
  __int64 v59; // rdx
  int v60; // edx
  int v61; // edx
  __int64 v62; // rdx
  int v63; // edx
  int v64; // edx
  int v65; // edx
  int v66; // edx
  __int64 InitPointer; // rax
  int TaskAllocator; // eax
  int v69; // edx
  unsigned __int64 v70; // r9
  __int64 v71; // rdx
  __int64 v72; // rbx
  __int64 v73; // rax
  int v74; // eax
  void (*v75)(void); // rax
  int *v76; // rax
  int v77; // edx
  unsigned int v78; // [rsp+20h] [rbp-59h]
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-49h] BYREF
  int v80[2]; // [rsp+38h] [rbp-41h] BYREF
  LPVOID v81; // [rsp+40h] [rbp-39h] BYREF
  HMODULE hModule; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v83[8]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v84; // [rsp+58h] [rbp-21h] BYREF
  __int64 v85; // [rsp+60h] [rbp-19h] BYREF
  __int64 v86; // [rsp+68h] [rbp-11h] BYREF
  __int64 v87; // [rsp+70h] [rbp-9h] BYREF
  LPVOID v88; // [rsp+78h] [rbp-1h] BYREF
  __int64 v89; // [rsp+80h] [rbp+7h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+Fh] BYREF
  LPVOID v91; // [rsp+90h] [rbp+17h] BYREF
  __int64 v92; // [rsp+98h] [rbp+1Fh] BYREF
  int v93; // [rsp+A0h] [rbp+27h] BYREF
  unsigned int v94; // [rsp+A4h] [rbp+2Bh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = *(CCbsSession **)(a1 + 48);
  hModule = 0;
  v85 = 0;
  v84 = 0;
  lpLibFileName = 0;
  v94 = 0;
  if ( (unsigned int)CCbsSession::IsOffline(v2) )
  {
    if ( !*v5 )
    {
      v8 = -2147024846;
      v93 = -2147024846;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Offline retrieval of repairable products is not currently supported.");
        *(_QWORD *)v80 = &v93;
        LOBYTE(v77) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v77,
          3,
          (unsigned int)": {}",
          (__int64)v80);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC02,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)0x80070032LL,
        v78);
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
      if ( v84 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
        v84 = 0;
      }
      if ( !v85 )
        goto LABEL_136;
      v75 = *(void (**)(void))(*(_QWORD *)v85 + 16LL);
      goto LABEL_135;
    }
LABEL_107:
    v81 = 0;
    v86 = 0;
    InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v86);
    TaskAllocator = GetTaskAllocator(InitPointer);
    v8 = TaskAllocator;
    if ( TaskAllocator >= 0 )
    {
      v72 = v86;
      v73 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v81);
      v74 = SczPublicAllocFromSz(v73, v72, &qword_1802EB518);
      v8 = v74;
      if ( v74 >= 0 )
      {
        v76 = (int *)BUCL::CVector<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>,BUCL::Rtl::CCallDisposition>::SwapOntoBack(
                       a2,
                       v83,
                       &v81);
        v8 = *v76 | 0x10000000;
        if ( *v76 >= 0 )
        {
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v86);
          if ( v81 )
          {
            CoTaskMemFree(v81);
            v81 = 0;
          }
          goto LABEL_124;
        }
        v70 = (unsigned int)v8;
        v71 = 3065;
      }
      else
      {
        v70 = (unsigned int)v74;
        v71 = 3063;
      }
    }
    else
    {
      v93 = TaskAllocator;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get task allocator.");
        *(_QWORD *)v80 = &v93;
        LOBYTE(v69) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v69,
          3,
          (unsigned int)": {}",
          (__int64)v80);
      }
      v70 = (unsigned int)v8;
      v71 = 3061;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v71,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
      (const char *)v70,
      v78);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v86);
    if ( v81 )
    {
      CoTaskMemFree(v81);
      v81 = 0;
    }
LABEL_115:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
    if ( v84 )
    {
      v20 = *(void (**)(void))(*(_QWORD *)v84 + 16LL);
      goto LABEL_117;
    }
    goto LABEL_118;
  }
  if ( *v5 )
    goto LABEL_107;
  if ( (unsigned int)CCbsSession::IsOffline(v4) )
  {
    OfflineWindowsDirectory = CCbsSession::GetOfflineWindowsDirectory(v6, (wchar_t **)&lpLibFileName);
    v8 = OfflineWindowsDirectory;
    if ( OfflineWindowsDirectory < 0 )
    {
      LODWORD(v86) = OfflineWindowsDirectory;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get offline windir");
        pv = &v86;
        LOBYTE(v9) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v9,
          3,
          (unsigned int)": {}",
          (__int64)&pv);
      }
      v10 = 3081;
LABEL_8:
      v11 = (unsigned int)v8;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)v11,
        v78);
      goto LABEL_115;
    }
    v12 = SczAllocConcatSz(&lpLibFileName, L"system32\\ProductEnumerator.dll");
    v8 = v12;
    if ( v12 < 0 )
    {
      v11 = (unsigned int)v12;
      v10 = 3083;
      goto LABEL_9;
    }
  }
  else
  {
    WindowsDirectory = PathGetWindowsDirectory(&lpLibFileName, L"system32\\ProductEnumerator.dll");
    v8 = WindowsDirectory;
    if ( WindowsDirectory < 0 )
    {
      v11 = (unsigned int)WindowsDirectory;
      v10 = 3087;
      goto LABEL_9;
    }
  }
  LibraryW = LoadLibraryW(lpLibFileName);
  Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hModule, LibraryW);
  if ( !hModule )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to load ProductEnumerator.dll.");
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      else
        v17 = LastError;
      LODWORD(v86) = v17;
      LOBYTE(v16) = 1;
      pv = &v86;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {0}",
        (__int64)&pv);
    }
    if ( LastError )
    {
      v18 = (unsigned int)LastError;
      v19 = 3091;
      goto LABEL_22;
    }
LABEL_124:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
    if ( v84 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
      v84 = 0;
    }
    if ( v85 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
      v85 = 0;
    }
    v8 = 0;
    goto LABEL_136;
  }
  ProcAddress = GetProcAddress(hModule, "PE_CreateProductEnumerator");
  if ( !ProcAddress )
  {
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Product enumeration not supported on this platform.");
      pv = &v86;
      LOBYTE(v22) = 1;
      LODWORD(v86) = -2147024846;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v22,
        3,
        (unsigned int)": {0}",
        (__int64)&pv);
    }
    v18 = 50;
    v19 = 3097;
LABEL_22:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v19,
           (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
           (const char *)v18,
           v78);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
    if ( v84 )
    {
      v20 = *(void (**)(void))(*(_QWORD *)v84 + 16LL);
LABEL_117:
      v20();
      v84 = 0;
    }
LABEL_118:
    if ( !v85 )
    {
LABEL_136:
      Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
      return (unsigned int)v8;
    }
    v75 = *(void (**)(void))(*(_QWORD *)v85 + 16LL);
LABEL_135:
    v75();
    v85 = 0;
    goto LABEL_136;
  }
  v23 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v85);
  v24 = ((__int64 (__fastcall *)(__int64))ProcAddress)(v23);
  v8 = v24;
  if ( v24 < 0 )
  {
    LODWORD(v86) = v24;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create product enumerator");
      pv = &v86;
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v25,
        3,
        (unsigned int)": {}",
        (__int64)&pv);
    }
    v10 = 3100;
    goto LABEL_8;
  }
  v26 = v85;
  v27 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v85 + 24LL);
  v28 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v84);
  v29 = v27(v26, v28);
  v8 = v29;
  if ( v29 < 0 )
  {
    LODWORD(v86) = v29;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to enumerate installed product");
      pv = &v86;
      LOBYTE(v30) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v30,
        3,
        (unsigned int)": {}",
        (__int64)&pv);
    }
    v10 = 3103;
    goto LABEL_8;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v84 + 24LL))(v84, &v94);
  v8 = v31;
  if ( v31 < 0 )
  {
    LODWORD(v86) = v31;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get installed product count");
      *(_QWORD *)v80 = &v86;
      LOBYTE(v32) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v32,
        3,
        (unsigned int)": {}",
        (__int64)v80);
    }
    v10 = 3105;
    goto LABEL_8;
  }
  v33 = 0;
  v34 = 0;
  if ( !v94 )
  {
LABEL_103:
    v8 = -2146498223;
    v93 = -2146498223;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Repairable primary OS product not found.");
      *(_QWORD *)v80 = &v93;
      LOBYTE(v66) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v66,
        3,
        (unsigned int)": {}",
        (__int64)v80);
    }
    v10 = 3164;
    goto LABEL_8;
  }
  do
  {
    v35 = v84;
    v87 = 0;
    v89 = 0;
    v88 = 0;
    v36 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v84 + 32LL);
    v37 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v87);
    v8 = v36(v35, v34, v37);
    if ( v8 < 0 )
    {
      LODWORD(v86) = v8;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get product object");
        *(_QWORD *)v80 = &v86;
        LOBYTE(v65) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v65,
          3,
          (unsigned int)": {}",
          (__int64)v80);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC2B,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)(unsigned int)v8,
        v78);
      goto LABEL_80;
    }
    v38 = v87;
    v39 = *(int (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v87 + 40LL);
    v40 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v89);
    if ( v39(v38, L"Repairable", v40) < 0 )
      goto LABEL_60;
    v41 = v89;
    v91 = 0;
    v42 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v89 + 32LL);
    v43 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v91);
    v8 = v42(v41, v43);
    if ( v8 < 0 )
    {
      LODWORD(v86) = v8;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get value of Repairable");
        *(_QWORD *)v80 = &v86;
        LOBYTE(v64) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v64,
          3,
          (unsigned int)": {}",
          (__int64)v80);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC32,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)(unsigned int)v8,
        v78);
LABEL_78:
      if ( v91 )
      {
        CoTaskMemFree(v91);
        v91 = 0;
      }
LABEL_80:
      if ( v88 )
      {
        CoTaskMemFree(v88);
        v88 = 0;
      }
      if ( v89 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
        v89 = 0;
      }
      if ( v87 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
        v87 = 0;
      }
      goto LABEL_115;
    }
    if ( !(unsigned int)_o__wcsicmp(v91, L"1") )
    {
      v44 = v87;
      v92 = 0;
      v45 = *(int (__fastcall **)(__int64, const wchar_t *, __int64))(*(_QWORD *)v87 + 40LL);
      v46 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v92);
      if ( v45(v44, L"PrimaryOSProduct", v46) >= 0 )
      {
        v47 = v92;
        pv = 0;
        v48 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 32LL);
        v49 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&pv);
        v8 = v48(v47, v49);
        if ( v8 < 0 )
        {
          LODWORD(v86) = v8;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get value of PrimaryOSProduct");
            *(_QWORD *)v80 = &v86;
            LOBYTE(v61) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v61,
              3,
              (unsigned int)": {}",
              (__int64)v80);
          }
          v59 = 3139;
LABEL_74:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v59,
            (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
            (const char *)(unsigned int)v8,
            v78);
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          goto LABEL_76;
        }
        if ( !(unsigned int)_o__wcsicmp(pv, L"1") )
        {
          v50 = v87;
          v51 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 24LL);
          v52 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v88);
          v8 = v51(v50, v52);
          if ( v8 < 0 )
          {
            LODWORD(v86) = v8;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "Failed to get primary OS product's name.");
              *(_QWORD *)v80 = &v86;
              LOBYTE(v60) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v60,
                3,
                (unsigned int)": {}",
                (__int64)v80);
            }
            v59 = 3143;
          }
          else
          {
            v53 = (int *)BUCL::CVector<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>,BUCL::Rtl::CCallDisposition>::SwapOntoFront(
                           a2,
                           &v81,
                           &v88);
            v8 = *v53 | 0x10000000;
            if ( *v53 >= 0 )
            {
              v33 = 1;
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              goto LABEL_56;
            }
            v59 = 3147;
          }
          goto LABEL_74;
        }
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
      }
      v54 = v87;
      v55 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 24LL);
      v56 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v88);
      v8 = v55(v54, v56);
      if ( v8 < 0 )
      {
        LODWORD(v86) = v8;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get Repairable product name.");
          *(_QWORD *)v80 = &v86;
          LOBYTE(v63) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v63,
            3,
            (unsigned int)": {}",
            (__int64)v80);
        }
        v62 = 3156;
      }
      else
      {
        v57 = (int *)BUCL::CVector<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>,BUCL::Rtl::CCallDisposition>::SwapOntoBack(
                       a2,
                       v83,
                       &v88);
        v8 = *v57 | 0x10000000;
        if ( *v57 >= 0 )
        {
LABEL_56:
          if ( v92 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
            v92 = 0;
          }
          goto LABEL_58;
        }
        v62 = 3158;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v62,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)(unsigned int)v8,
        v78);
LABEL_76:
      if ( v92 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
        v92 = 0;
      }
      goto LABEL_78;
    }
LABEL_58:
    if ( v91 )
    {
      CoTaskMemFree(v91);
      v91 = 0;
    }
LABEL_60:
    if ( v88 )
    {
      CoTaskMemFree(v88);
      v88 = 0;
    }
    if ( v89 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
      v89 = 0;
    }
    if ( v87 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
      v87 = 0;
    }
    ++v34;
  }
  while ( v34 < v94 );
  if ( !v33 )
    goto LABEL_103;
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
  if ( v84 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
    v84 = 0;
  }
  if ( v85 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
    v85 = 0;
  }
  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
  return 0;
}

```

## disassembly

```asm
0x18018df84  mov     [rsp-8+arg_10], rbx
0x18018df89  mov     [rsp-8+arg_18], rsi
0x18018df8e  push    rbp
0x18018df8f  push    rdi
0x18018df90  push    r12
0x18018df92  push    r13
0x18018df94  push    r15
0x18018df96  lea     rbp, [rsp-37h]
0x18018df9b  sub     rsp, 0B0h
0x18018dfa2  mov     rax, cs:__security_cookie
0x18018dfa9  xor     rax, rsp
0x18018dfac  mov     [rbp+57h+var_28], rax
0x18018dfb0  mov     r9, [rcx+30h]
0x18018dfb4  lea     r8, [rcx+16Dh]
0x18018dfbb  xor     r13d, r13d
0x18018dfbe  mov     rcx, r9; this
0x18018dfc1  mov     r12, rdx
0x18018dfc4  mov     [rbp+57h+hModule], r13
0x18018dfc8  mov     [rbp+57h+var_70], r13
0x18018dfcc  mov     [rbp+57h+var_78], r13
0x18018dfd0  mov     [rbp+57h+lpLibFileName], r13
0x18018dfd4  mov     [rbp+57h+var_2C], r13d
0x18018dfd8  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x18018dfdd  test    eax, eax
0x18018dfdf  jnz     loc_18018E96A
0x18018dfe5  cmp     [r8], r13b
0x18018dfe8  jnz     loc_18018E973
0x18018dfee  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x18018dff3  test    eax, eax
0x18018dff5  jz      loc_18018E094
0x18018dffb  lea     rdx, [rbp+57h+lpLibFileName]; wchar_t **
0x18018dfff  call    ?GetOfflineWindowsDirectory@CCbsSession@@QEBAJPEAPEA_W@Z; CCbsSession::GetOfflineWindowsDirectory(wchar_t * *)
0x18018e004  mov     ebx, eax
0x18018e006  test    eax, eax
0x18018e008  jns     short loc_18018E074
0x18018e00a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e011  mov     dword ptr [rbp+57h+var_68], eax
0x18018e014  test    rcx, rcx
0x18018e017  jz      short loc_18018E057
0x18018e019  lea     edi, [r13+3]
0x18018e01d  xor     edx, edx
0x18018e01f  mov     r8d, edi
0x18018e022  lea     r9, aFailedToGetOff_11; "Failed to get offline windir"
0x18018e029  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018e02e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e035  lea     rax, [rbp+57h+var_68]
0x18018e039  mov     [rbp+57h+pv], rax
0x18018e03d  lea     r9, asc_1802EE7AC; ": {}"
0x18018e044  lea     rax, [rbp+57h+pv]
0x18018e048  mov     r8d, edi
0x18018e04b  mov     dl, 1
0x18018e04d  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18018e052  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018e057  mov     edx, 0C09h; void *
0x18018e05c  mov     r9d, ebx; char *
0x18018e05f  mov     rcx, [rbp+5Fh]; this
0x18018e063  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x18018e06a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018e06f  jmp     loc_18018EA49
0x18018e074  lea     rdx, aSystem32Produc; "system32\\ProductEnumerator.dll"
0x18018e07b  lea     rcx, [rbp+57h+lpLibFileName]
0x18018e07f  call    SczAllocConcatSz
0x18018e084  mov     ebx, eax
0x18018e086  test    eax, eax
0x18018e088  jns     short loc_18018E0B4
0x18018e08a  mov     r9d, eax
0x18018e08d  mov     edx, 0C0Bh
0x18018e092  jmp     short loc_18018E05F
0x18018e094  lea     rdx, aSystem32Produc; "system32\\ProductEnumerator.dll"
0x18018e09b  lea     rcx, [rbp+57h+lpLibFileName]
0x18018e09f  call    PathGetWindowsDirectory
0x18018e0a4  mov     ebx, eax
0x18018e0a6  test    eax, eax
0x18018e0a8  jns     short loc_18018E0B4
0x18018e0aa  mov     r9d, eax
0x18018e0ad  mov     edx, 0C0Fh
0x18018e0b2  jmp     short loc_18018E05F
0x18018e0b4  mov     rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x18018e0b8  call    cs:__imp_LoadLibraryW
0x18018e0bf  nop     dword ptr [rax+rax+00h]
0x18018e0c4  mov     rdx, rax
0x18018e0c7  lea     rcx, [rbp+57h+hModule]
0x18018e0cb  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x18018e0d0  mov     rcx, [rbp+57h+hModule]; hModule
0x18018e0d4  test    rcx, rcx
0x18018e0d7  jnz     loc_18018E18D
0x18018e0dd  call    cs:__imp_GetLastError
0x18018e0e4  nop     dword ptr [rax+rax+00h]
0x18018e0e9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e0f0  mov     ebx, eax
0x18018e0f2  test    rcx, rcx
0x18018e0f5  jz      short loc_18018E149
0x18018e0f7  mov     edi, 3
0x18018e0fc  lea     r9, aFailedToLoadPr; "Failed to load ProductEnumerator.dll."
0x18018e103  mov     r8d, edi
0x18018e106  xor     edx, edx
0x18018e108  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018e10d  test    ebx, ebx
0x18018e10f  jg      short loc_18018E115
0x18018e111  mov     eax, ebx
0x18018e113  jmp     short loc_18018E11D
0x18018e115  movzx   eax, bx
0x18018e118  or      eax, 80070000h
0x18018e11d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e124  lea     r9, a0; ": {0}"
0x18018e12b  mov     dword ptr [rbp+57h+var_68], eax
0x18018e12e  mov     r8d, edi
0x18018e131  lea     rax, [rbp+57h+var_68]
0x18018e135  mov     dl, 1
0x18018e137  mov     [rbp+57h+pv], rax
0x18018e13b  lea     rax, [rbp+57h+pv]
0x18018e13f  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x18018e144  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018e149  test    ebx, ebx
0x18018e14b  jz      loc_18018EACD
0x18018e151  mov     r9d, ebx; char *
0x18018e154  mov     edx, 0C13h; void *
0x18018e159  mov     rcx, [rbp+5Fh]; this
0x18018e15d  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x18018e164  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18018e169  lea     rcx, [rbp+57h+lpLibFileName]
0x18018e16d  mov     ebx, eax
0x18018e16f  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18018e174  mov     rcx, [rbp+57h+var_78]
0x18018e178  test    rcx, rcx
0x18018e17b  jz      loc_18018EA6B
0x18018e181  mov     rdx, [rcx]
0x18018e184  mov     rax, [rdx+10h]
0x18018e188  jmp     loc_18018EA62
0x18018e18d  lea     rdx, aPeCreateproduc; "PE_CreateProductEnumerator"
0x18018e194  call    cs:__imp_GetProcAddress
0x18018e19b  nop     dword ptr [rax+rax+00h]
0x18018e1a0  mov     rbx, rax
0x18018e1a3  test    rax, rax
0x18018e1a6  jnz     short loc_18018E209
0x18018e1a8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e1af  test    rcx, rcx
0x18018e1b2  jz      short loc_18018E1F9
0x18018e1b4  lea     edi, [rax+3]
0x18018e1b7  xor     edx, edx
0x18018e1b9  mov     r8d, edi
0x18018e1bc  lea     r9, aProductEnumera; "Product enumeration not supported on th"...
0x18018e1c3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018e1c8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e1cf  lea     rax, [rbp+57h+var_68]
0x18018e1d3  mov     [rbp+57h+pv], rax
0x18018e1d7  lea     r9, a0; ": {0}"
0x18018e1de  lea     rax, [rbp+57h+pv]
0x18018e1e2  mov     ebx, 80070032h
0x18018e1e7  mov     r8d, edi
0x18018e1ea  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18018e1ef  mov     dl, 1
0x18018e1f1  mov     dword ptr [rbp+57h+var_68], ebx
0x18018e1f4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018e1f9  mov     r9d, 32h ; '2'
0x18018e1ff  mov     edx, 0C19h
0x18018e204  jmp     loc_18018E159
0x18018e209  lea     rcx, [rbp+57h+var_70]
0x18018e20d  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18018e212  mov     rcx, rax
0x18018e215  mov     rax, rbx
0x18018e218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e21d  mov     ebx, eax
0x18018e21f  test    eax, eax
0x18018e221  jns     short loc_18018E27B
0x18018e223  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e22a  mov     dword ptr [rbp+57h+var_68], eax
0x18018e22d  test    rcx, rcx
0x18018e230  jz      short loc_18018E271
0x18018e232  mov     edi, 3
0x18018e237  lea     r9, aFailedToCreate_113; "Failed to create product enumerator"
0x18018e23e  mov     r8d, edi
0x18018e241  xor     edx, edx
0x18018e243  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018e248  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e24f  lea     rax, [rbp+57h+var_68]
0x18018e253  mov     [rbp+57h+pv], rax
0x18018e257  lea     r9, asc_1802EE7AC; ": {}"
0x18018e25e  lea     rax, [rbp+57h+pv]
0x18018e262  mov     r8d, edi
0x18018e265  mov     dl, 1
0x18018e267  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18018e26c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018e271  mov     edx, 0C1Ch
0x18018e276  jmp     loc_18018E05C
0x18018e27b  mov     rdi, [rbp+57h+var_70]
0x18018e27f  lea     rcx, [rbp+57h+var_78]
0x18018e283  mov     rax, [rdi]
0x18018e286  mov     rbx, [rax+18h]
0x18018e28a  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18018e28f  mov     rdx, rax
0x18018e292  mov     rcx, rdi
0x18018e295  mov     rax, rbx
0x18018e298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e29d  mov     ebx, eax
0x18018e29f  test    eax, eax
0x18018e2a1  jns     short loc_18018E2FB
0x18018e2a3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e2aa  mov     dword ptr [rbp+57h+var_68], eax
0x18018e2ad  test    rcx, rcx
0x18018e2b0  jz      short loc_18018E2F1
0x18018e2b2  mov     edi, 3
0x18018e2b7  lea     r9, aFailedToEnumer_11; "Failed to enumerate installed product"
0x18018e2be  mov     r8d, edi
0x18018e2c1  xor     edx, edx
0x18018e2c3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018e2c8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e2cf  lea     rax, [rbp+57h+var_68]
0x18018e2d3  mov     [rbp+57h+pv], rax
0x18018e2d7  lea     r9, asc_1802EE7AC; ": {}"
0x18018e2de  lea     rax, [rbp+57h+pv]
0x18018e2e2  mov     r8d, edi
0x18018e2e5  mov     dl, 1
0x18018e2e7  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18018e2ec  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018e2f1  mov     edx, 0C1Fh
0x18018e2f6  jmp     loc_18018E05C
0x18018e2fb  mov     rcx, [rbp+57h+var_78]
0x18018e2ff  lea     rdx, [rbp+57h+var_2C]
0x18018e303  mov     rax, [rcx]
0x18018e306  mov     rax, [rax+18h]
0x18018e30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e30f  mov     ebx, eax
0x18018e311  test    eax, eax
0x18018e313  jns     short loc_18018E36D
0x18018e315  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e31c  mov     dword ptr [rbp+57h+var_68], eax
0x18018e31f  test    rcx, rcx
0x18018e322  jz      short loc_18018E363
0x18018e324  mov     edi, 3
0x18018e329  lea     r9, aFailedToGetIns_0; "Failed to get installed product count"
0x18018e330  mov     r8d, edi
0x18018e333  xor     edx, edx
0x18018e335  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018e33a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18018e341  lea     rax, [rbp+57h+var_68]
0x18018e345  mov     qword ptr [rbp+57h+var_98], rax
0x18018e349  lea     r9, asc_1802EE7AC; ": {}"
0x18018e350  lea     rax, [rbp+57h+var_98]
0x18018e354  mov     r8d, edi
0x18018e357  mov     dl, 1
0x18018e359  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18018e35e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018e363  mov     edx, 0C21h
0x18018e368  jmp     loc_18018E05C
0x18018e36d  mov     r15b, r13b
0x18018e370  mov     esi, r13d
0x18018e373  cmp     [rbp+57h+var_2C], r13d
0x18018e377  jbe     loc_18018E90D
0x18018e37d  mov     rdi, [rbp+57h+var_78]
0x18018e381  lea     rcx, [rbp+57h+var_60]
0x18018e385  mov     [rbp+57h+var_60], r13
0x18018e389  mov     [rbp+57h+var_50], r13
0x18018e38d  mov     [rbp+57h+var_58], r13
0x18018e391  mov     rax, [rdi]
0x18018e394  mov     rbx, [rax+20h]
0x18018e398  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18018e39d  mov     r8, rax
0x18018e3a0  mov     edx, esi
0x18018e3a2  mov     rax, rbx
0x18018e3a5  mov     rcx, rdi
0x18018e3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e3ad  mov     ebx, eax
0x18018e3af  test    eax, eax
0x18018e3b1  js      loc_18018E8A2
0x18018e3b7  mov     rdi, [rbp+57h+var_60]
0x18018e3bb  lea     rcx, [rbp+57h+var_50]
0x18018e3bf  mov     rax, [rdi]
0x18018e3c2  mov     rbx, [rax+28h]
0x18018e3c6  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18018e3cb  mov     r8, rax
0x18018e3ce  lea     rdx, aRepairable; "Repairable"
0x18018e3d5  mov     rax, rbx
0x18018e3d8  mov     rcx, rdi
0x18018e3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e3e0  test    eax, eax
0x18018e3e2  js      loc_18018E5B4
0x18018e3e8  mov     rdi, [rbp+57h+var_50]
0x18018e3ec  lea     rcx, [rbp+57h+var_40]
0x18018e3f0  mov     [rbp+57h+var_40], r13
0x18018e3f4  mov     rax, [rdi]
0x18018e3f7  mov     rbx, [rax+20h]
0x18018e3fb  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18018e400  mov     rdx, rax
0x18018e403  mov     rcx, rdi
0x18018e406  mov     rax, rbx
0x18018e409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e40e  mov     ebx, eax
0x18018e410  test    eax, eax
0x18018e412  js      loc_18018E837
0x18018e418  mov     rcx, [rbp+57h+var_40]
0x18018e41c  lea     rdx, a1; "1"
0x18018e423  call    cs:__imp__o__wcsicmp
0x18018e42a  nop     dword ptr [rax+rax+00h]
0x18018e42f  test    eax, eax
0x18018e431  jnz     loc_18018E59B
0x18018e437  mov     rdi, [rbp+57h+var_60]
0x18018e43b  lea     rcx, [rbp+57h+var_38]
0x18018e43f  mov     [rbp+57h+var_38], r13
0x18018e443  mov     rax, [rdi]
  ... truncated ...
```
