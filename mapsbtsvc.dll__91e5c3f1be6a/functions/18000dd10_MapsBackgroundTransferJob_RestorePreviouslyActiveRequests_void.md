# MapsBackgroundTransferJob::RestorePreviouslyActiveRequests(void)

- ea: `0x18000dd10`
- end: `0x18000e9ac`
- name: `?RestorePreviouslyActiveRequests@MapsBackgroundTransferJob@@AEAAJXZ`
- size: `3228`
- prototype: `__int64 __fastcall(MapsBackgroundTransferJob *__hidden this)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000cfec`
- `0x18000ea00`

## callees

- `0x180001e70`
- `0x180002924`
- `0x1800033d4`
- `0x1800043e4`
- `0x180004680`
- `0x1800047cc`
- `0x1800098e4`
- `0x180009b98`
- `0x180009d3c`
- `0x18000a460`
- `0x18000a6d8`
- `0x18000aab8`
- `0x18000ad70`
- `0x18000adf0`
- `0x18000ae58`
- `0x18000b070`
- `0x18000b3a4`
- `0x18000b3dc`
- `0x18000c99c`
- `0x18000dd10`
- `0x18001074c`
- `0x180010954`
- `0x180010d6c`
- `0x180010ed4`
- `0x18001357c`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000def9`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18000def9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e12a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e21d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e12a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e1c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e21d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000de24`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000debc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000de24`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000debc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd8a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dde2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dde2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000df8e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000df8e`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000dfb7`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000dfb7`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e458`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e4d4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e550`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e5cc`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e648`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e6c4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e740`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e7bc`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e838`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e8ce`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e8f1`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e458`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e4d4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e550`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e5cc`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e648`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e6c4`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e740`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e7bc`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e838`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e8ce`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000e8f1`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000e94c`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18000e94c`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::RestorePreviouslyActiveRequests(MapsBackgroundTransferJob *this)
{
  const WCHAR *v2; // rax
  int ValueW; // eax
  int v4; // r8d
  unsigned int v5; // esi
  unsigned __int64 v6; // rax
  char *v7; // rbx
  int v8; // r15d
  char *v9; // r14
  _WORD *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  unsigned int i; // r13d
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // r15
  __int64 (__fastcall *v21)(__int64, LPVOID *); // r12
  void *v22; // r14
  int v23; // eax
  int v24; // eax
  __int64 v25; // r15
  __int64 (__fastcall *v26)(__int64, LPVOID *); // r12
  void *v27; // r14
  int v28; // eax
  __int64 v29; // r15
  __int64 (__fastcall *v30)(__int64, unsigned int *, LPVOID *); // r12
  void *v31; // r14
  int v32; // eax
  int v33; // r14d
  _QWORD *v34; // rdx
  _QWORD *v35; // rax
  int v36; // r14d
  _QWORD *v37; // rax
  int v38; // ecx
  bool v40; // [rsp+50h] [rbp-1E8h] BYREF
  __int64 v41; // [rsp+58h] [rbp-1E0h] BYREF
  LPVOID v42; // [rsp+60h] [rbp-1D8h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-1D0h] BYREF
  LPVOID v44; // [rsp+70h] [rbp-1C8h] BYREF
  __int64 v45; // [rsp+78h] [rbp-1C0h] BYREF
  __int64 v46; // [rsp+80h] [rbp-1B8h] BYREF
  __int64 v47; // [rsp+88h] [rbp-1B0h] BYREF
  __int64 v48; // [rsp+90h] [rbp-1A8h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp-1A0h] BYREF
  unsigned int v50; // [rsp+9Ch] [rbp-19Ch] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-198h] BYREF
  unsigned int v52; // [rsp+A8h] [rbp-190h] BYREF
  __int64 v53; // [rsp+B0h] [rbp-188h] BYREF
  char *v54; // [rsp+B8h] [rbp-180h] BYREF
  char v55[8]; // [rsp+C0h] [rbp-178h] BYREF
  char v56[8]; // [rsp+C8h] [rbp-170h] BYREF
  char v57[8]; // [rsp+D0h] [rbp-168h] BYREF
  MapsBackgroundTransferJob *v58; // [rsp+D8h] [rbp-160h]
  char v59[8]; // [rsp+E0h] [rbp-158h] BYREF
  __int64 v60; // [rsp+E8h] [rbp-150h]
  __int64 v61; // [rsp+F0h] [rbp-148h]
  _BYTE v62[16]; // [rsp+120h] [rbp-118h] BYREF
  char v63[16]; // [rsp+130h] [rbp-108h] BYREF
  char v64[16]; // [rsp+140h] [rbp-F8h] BYREF
  char v65[16]; // [rsp+150h] [rbp-E8h] BYREF
  char v66[16]; // [rsp+160h] [rbp-D8h] BYREF
  _BYTE v67[32]; // [rsp+170h] [rbp-C8h] BYREF
  __int128 v68; // [rsp+190h] [rbp-A8h] BYREF
  __int64 v69; // [rsp+1A0h] [rbp-98h]
  int v70; // [rsp+1B0h] [rbp-88h]
  _QWORD v71[7]; // [rsp+1C0h] [rbp-78h] BYREF
  _QWORD *v72; // [rsp+1F8h] [rbp-40h]

  v58 = this;
  pcbData = 0;
  v54 = 0;
  std::unordered_map<std::wstring,unsigned long>::unordered_map<std::wstring,unsigned long>(v59);
  hKey = 0;
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 48);
  ValueW = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0, 0, 0x2001Bu, 0, &hKey, 0);
  if ( ValueW )
  {
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    v4 = 1189;
    goto LABEL_72;
  }
  ValueW = RegGetValueW(hKey, 0, L"ActiveRequests", 0x20u, 0, 0, &pcbData);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    v4 = 1202;
LABEL_72:
    v38 = ValueW;
    goto LABEL_73;
  }
  v5 = 0;
  if ( pcbData )
  {
    v6 = 2 * ((unsigned __int64)pcbData >> 1);
    if ( !is_mul_ok((unsigned __int64)pcbData >> 1, 2u) )
      v6 = -1;
    v7 = (char *)operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
    v54 = v7;
    if ( !v7 )
    {
      v4 = 1208;
      v38 = -2147024882;
LABEL_73:
      v5 = ZTraceReportOrigination(v38, "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests", v4, this);
      goto LABEL_74;
    }
    ValueW = RegGetValueW(hKey, 0, L"ActiveRequests", 0x20u, 0, v7, &pcbData);
    if ( ValueW )
    {
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      v4 = 1218;
      goto LABEL_72;
    }
    v8 = 0;
    v9 = v7;
    v10 = v7;
    while ( v9 < &v7[(pcbData & 0xFFFFFFFE) - 2] )
    {
      if ( *(_WORD *)v9 == 59 )
      {
        *(_WORD *)v9 = 0;
        v8 = _o__wtoi(v10);
        v10 = v9 + 2;
      }
      else if ( !*(_WORD *)v9 )
      {
        v11 = std::wstring::wstring(v67, v10);
        std::wstring::wstring(&v68, v11);
        v70 = v8;
        std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::emplace<std::pair<std::wstring,unsigned long>>(
          v59,
          v62,
          &v68);
        std::wstring::_Tidy_deallocate(&v68);
        std::wstring::_Tidy_deallocate(v67);
        v10 = v9 + 2;
        if ( !*((_WORD *)v9 + 1) )
          break;
      }
      v9 += 2;
    }
    v12 = RegDeleteValueW(hKey, L"ActiveRequests");
    if ( v12 )
    {
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      ZTraceReportIgnore(v12, "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests", 1254, this);
    }
    if ( v61 )
    {
      v45 = 0;
      v52 = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 3) + 40LL))(*((_QWORD *)this + 3), &v45);
      if ( v13 < 0 )
      {
        v5 = ZTraceReportPropagation(v13, "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests", 1262, this);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
      }
      else
      {
        v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v45 + 56LL))(v45, &v52);
        if ( v14 < 0 )
        {
          v5 = ZTraceReportPropagation(v14, "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests", 1263, this);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
        }
        else
        {
          for ( i = 0; i < v52; ++i )
          {
            v48 = 0;
            v41 = 0;
            v47 = 0;
            v46 = 0;
            v44 = 0;
            pv = 0;
            v42 = 0;
            v50 = 0;
            v68 = 0;
            v69 = 0;
            v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v45 + 24LL))(v45, 1, &v41);
            if ( v16 < 0 )
            {
              v5 = ZTraceReportPropagation(
                     v16,
                     "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests",
                     1277,
                     this);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
              std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v48);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
              goto LABEL_74;
            }
            v17 = ATL::CComPtrBase<IBackgroundCopyFile>::QueryInterface<IBackgroundCopyFile2>(&v41, &v47);
            if ( v17 < 0 )
            {
              v5 = ZTraceReportPropagation(
                     v17,
                     "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests",
                     1279,
                     this);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
              std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v48);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
              goto LABEL_74;
            }
            v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v41)(
                    v41,
                    &GUID_659cdeaa_489e_11d9_a9cd_000d56965251,
                    &v46);
            if ( v18 < 0 )
            {
              v5 = ZTraceReportPropagation(
                     v18,
                     "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests",
                     1280,
                     this);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
              std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v48);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
              goto LABEL_74;
            }
            v19 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v41 + 40LL))(v41, &v68);
            if ( v19 < 0 )
            {
              v5 = ZTraceReportPropagation(
                     v19,
                     "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests",
                     1283,
                     this);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
              std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v48);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
              goto LABEL_74;
            }
            v20 = v46;
            v21 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v46 + 64LL);
            v22 = pv;
            if ( pv )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v55);
              CoTaskMemFree(v22);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v55);
            }
            pv = 0;
            v23 = v21(v20, &pv);
            if ( v23 < 0 )
            {
              v5 = ZTraceReportPropagation(
                     v23,
                     "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests",
                     1285,
                     this);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
              std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v48);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
              goto LABEL_74;
            }
            v40 = 0;
            v24 = FileExists((const unsigned __int16 *)pv, &v40);
            if ( v24 < 0 )
            {
              v5 = ZTraceReportPropagation(
                     v24,
                     "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests",
                     1288,
                     this);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
              std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v48);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
              goto LABEL_74;
            }
            if ( *((_QWORD *)&v68 + 1) != (_QWORD)v68 || v40 )
            {
              v25 = v41;
              v26 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v41 + 24LL);
              v27 = v44;
              if ( v44 )
              {
                wil::last_error_context::last_error_context((wil::last_error_context *)v56);
                CoTaskMemFree(v27);
                wil::last_error_context::~last_error_context((wil::last_error_context *)v56);
              }
              v44 = 0;
              v28 = v26(v25, &v44);
              if ( v28 < 0 )
              {
                v5 = ZTraceReportPropagation(
                       v28,
                       "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests",
                       1298,
                       this);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
                std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v48);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
                goto LABEL_74;
              }
              v29 = v47;
              v30 = *(__int64 (__fastcall **)(__int64, unsigned int *, LPVOID *))(*(_QWORD *)v47 + 48LL);
              v31 = v42;
              if ( v42 )
              {
                wil::last_error_context::last_error_context((wil::last_error_context *)v57);
                CoTaskMemFree(v31);
                wil::last_error_context::~last_error_context((wil::last_error_context *)v57);
              }
              v42 = 0;
              v32 = v30(v29, &v50, &v42);
              if ( v32 < 0 )
              {
                v5 = ZTraceReportPropagation(
                       v32,
                       "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests",
                       1300,
                       this);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
                std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v48);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
                goto LABEL_74;
              }
              v53 = 0;
              v71[0] = off_1800162A8;
              v71[1] = v42;
              v72 = v71;
              v33 = MapsBackgroundTransferJob::GenerateRequestId(v44, v50, v71, &v53);
              if ( v72 )
              {
                v34 = v71;
                LOBYTE(v34) = v72 != v71;
                (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v72 + 32LL))(v72, v34);
              }
              if ( v33 < 0 )
              {
                v5 = ZTraceReportPropagation(
                       v33,
                       "MapsBackgroundTransferJob::RestorePreviouslyActiveRequests",
                       1313,
                       this);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
                std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v48);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
                goto LABEL_74;
              }
              v48 = v53;
              std::wstring::wstring(v67, v53);
              v35 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::find(
                                v59,
                                v62,
                                v67);
              if ( *v35 != v60 )
              {
                if ( *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Try_emplace<std::wstring const &,>(
                                              v59,
                                              v63,
                                              v67)
                               + 48LL) <= 1u )
                {
                  std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Erase<std::wstring>(
                    v59,
                    v67);
                }
                else
                {
                  v36 = *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Try_emplace<std::wstring const &,>(
                                                 v59,
                                                 v64,
                                                 v67)
                                  + 48LL)
                      - 1;
                  *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Try_emplace<std::wstring const &,>(
                                           v59,
                                           v65,
                                           v67)
                            + 48LL) = v36;
                }
                v37 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>>,0>>::_Try_emplace<std::wstring const &,>(
                                  (char *)this + 672,
                                  v66,
                                  v67);
                std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Emplace_back_internal<ATL::CComPtr<IBackgroundCopyFile>>(
                  *v37 + 48LL,
                  &v41);
              }
              std::wstring::_Tidy_deallocate(v67);
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v44);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v46);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
            std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v48);
          }
          std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::clear(v59);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
        }
      }
    }
  }
LABEL_74:
  std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>(v59);
  std::unique_ptr<_BG_FILE_RANGE [0]>::~unique_ptr<_BG_FILE_RANGE [0]>(&v54);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x18000dd10  mov     r11, rsp
0x18000dd13  mov     [r11+10h], rbx
0x18000dd17  mov     [r11+18h], rsi
0x18000dd1b  push    rdi
0x18000dd1c  push    r12
0x18000dd1e  push    r13
0x18000dd20  push    r14
0x18000dd22  push    r15
0x18000dd24  sub     rsp, 210h
0x18000dd2b  mov     rax, cs:__security_cookie
0x18000dd32  xor     rax, rsp
0x18000dd35  mov     [rsp+238h+var_38], rax
0x18000dd3d  mov     rdi, rcx
0x18000dd40  mov     [rsp+238h+var_160], rcx
0x18000dd48  xor     r12d, r12d
0x18000dd4b  mov     [r11-198h], r12
0x18000dd52  mov     [r11-1A0h], r12d
0x18000dd59  mov     [r11-180h], r12
0x18000dd60  lea     rcx, [r11-158h]
0x18000dd67  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KU?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,ulong>::unordered_map<std::wstring,ulong>(void)
0x18000dd6c  nop
0x18000dd6d  mov     rbx, [rsp+238h+hKey]
0x18000dd75  test    rbx, rbx
0x18000dd78  jz      short loc_18000DD9D
0x18000dd7a  lea     rcx, [rsp+238h+var_188]; this
0x18000dd82  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000dd87  mov     rcx, rbx; hKey
0x18000dd8a  call    cs:__imp_RegCloseKey
0x18000dd90  lea     rcx, [rsp+238h+var_188]; this
0x18000dd98  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000dd9d  mov     [rsp+238h+hKey], r12
0x18000dda5  lea     rcx, [rdi+30h]
0x18000dda9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000ddae  mov     [rsp+238h+lpdwDisposition], r12; lpdwDisposition
0x18000ddb3  lea     rcx, [rsp+238h+hKey]
0x18000ddbb  mov     [rsp+238h+phkResult], rcx; phkResult
0x18000ddc0  mov     [rsp+238h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18000ddc5  mov     [rsp+238h+samDesired], 2001Bh; samDesired
0x18000ddcd  mov     [rsp+238h+dwOptions], r12d; dwOptions
0x18000ddd2  xor     r9d, r9d; lpClass
0x18000ddd5  xor     r8d, r8d; Reserved
0x18000ddd8  mov     rdx, rax; lpSubKey
0x18000dddb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dde2  call    cs:__imp_RegCreateKeyExW
0x18000dde8  test    eax, eax
0x18000ddea  jnz     loc_18000E930
0x18000ddf0  lea     rax, [rsp+238h+pcbData]
0x18000ddf8  mov     [rsp+238h+lpSecurityAttributes], rax; pcbData
0x18000ddfd  mov     qword ptr [rsp+238h+samDesired], r12; pvData
0x18000de02  mov     qword ptr [rsp+238h+dwOptions], r12; pdwType
0x18000de07  mov     r14d, 20h ; ' '
0x18000de0d  mov     r9d, r14d; dwFlags
0x18000de10  lea     r13, ValueName; "ActiveRequests"
0x18000de17  mov     r8, r13; lpValue
0x18000de1a  xor     edx, edx; lpSubKey
0x18000de1c  mov     rcx, [rsp+238h+hKey]; hkey
0x18000de24  call    cs:__imp_RegGetValueW
0x18000de2a  test    eax, 0FFFFFFFDh
0x18000de2f  jz      short loc_18000DE48
0x18000de31  test    eax, eax
0x18000de33  jle     short loc_18000DE3D
0x18000de35  movzx   eax, ax
0x18000de38  or      eax, 80070000h
0x18000de3d  mov     r8d, 4B2h
0x18000de43  jmp     loc_18000E940
0x18000de48  mov     esi, r12d
0x18000de4b  mov     eax, [rsp+238h+pcbData]
0x18000de52  test    eax, eax
0x18000de54  jz      loc_18000E954
0x18000de5a  mov     ecx, eax
0x18000de5c  shr     rcx, 1
0x18000de5f  mov     eax, 2
0x18000de64  mul     rcx
0x18000de67  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000de6e  cmovb   rax, rcx
0x18000de72  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000de79  mov     rcx, rax; unsigned __int64
0x18000de7c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000de81  mov     rbx, rax
0x18000de84  mov     [rsp+238h+var_180], rax
0x18000de8c  test    rax, rax
0x18000de8f  jz      loc_18000E923
0x18000de95  lea     rax, [rsp+238h+pcbData]
0x18000de9d  mov     [rsp+238h+lpSecurityAttributes], rax; pcbData
0x18000dea2  mov     qword ptr [rsp+238h+samDesired], rbx; pvData
0x18000dea7  mov     qword ptr [rsp+238h+dwOptions], r12; pdwType
0x18000deac  mov     r9d, r14d; dwFlags
0x18000deaf  mov     r8, r13; lpValue
0x18000deb2  xor     edx, edx; lpSubKey
0x18000deb4  mov     rcx, [rsp+238h+hKey]; hkey
0x18000debc  call    cs:__imp_RegGetValueW
0x18000dec2  test    eax, eax
0x18000dec4  jnz     loc_18000E911
0x18000deca  mov     r15d, r12d
0x18000decd  mov     r14, rbx
0x18000ded0  mov     rcx, rbx
0x18000ded3  mov     eax, [rsp+238h+pcbData]
0x18000deda  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000dede  add     rax, 0FFFFFFFFFFFFFFFEh
0x18000dee2  add     rax, rbx
0x18000dee5  cmp     r14, rax
0x18000dee8  jnb     loc_18000DF83
0x18000deee  cmp     word ptr [r14], 3Bh ; ';'
0x18000def3  jnz     short loc_18000DF08
0x18000def5  mov     [r14], r12w
0x18000def9  call    cs:__imp__o__wtoi
0x18000deff  mov     r15d, eax
0x18000df02  lea     rcx, [r14+2]
0x18000df06  jmp     short loc_18000DF7A
0x18000df08  cmp     [r14], r12w
0x18000df0c  jnz     short loc_18000DF7A
0x18000df0e  mov     rdx, rcx
0x18000df11  lea     rcx, [rsp+238h+var_C8]
0x18000df19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000df1e  nop
0x18000df1f  mov     rdx, rax
0x18000df22  lea     rcx, [rsp+238h+var_A8]
0x18000df2a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000df2f  mov     [rsp+238h+var_88], r15d
0x18000df37  lea     r8, [rsp+238h+var_A8]
0x18000df3f  lea     rdx, [rsp+238h+var_118]
0x18000df47  lea     rcx, [rsp+238h+var_158]
0x18000df4f  call    ??$emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::emplace<std::pair<std::wstring,ulong>>(std::pair<std::wstring,ulong> &&)
0x18000df54  nop
0x18000df55  lea     rcx, [rsp+238h+var_A8]
0x18000df5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000df62  nop
0x18000df63  lea     rcx, [rsp+238h+var_C8]
0x18000df6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000df70  lea     rcx, [r14+2]
0x18000df74  cmp     [rcx], r12w
0x18000df78  jz      short loc_18000DF83
0x18000df7a  add     r14, 2
0x18000df7e  jmp     loc_18000DED3
0x18000df83  mov     rdx, r13; lpValueName
0x18000df86  mov     rcx, [rsp+238h+hKey]; hKey
0x18000df8e  call    cs:__imp_RegDeleteValueW
0x18000df94  test    eax, eax
0x18000df96  jz      short loc_18000DFBF
0x18000df98  jle     short loc_18000DFA2
0x18000df9a  movzx   eax, ax
0x18000df9d  or      eax, 80070000h
0x18000dfa2  mov     r9, rdi
0x18000dfa5  mov     r8d, 4E6h
0x18000dfab  lea     rbx, aMapsbackground_21; "MapsBackgroundTransferJob::RestorePrevi"...
0x18000dfb2  mov     rdx, rbx
0x18000dfb5  mov     ecx, eax
0x18000dfb7  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18000dfbd  jmp     short loc_18000DFC6
0x18000dfbf  lea     rbx, aMapsbackground_21; "MapsBackgroundTransferJob::RestorePrevi"...
0x18000dfc6  cmp     [rsp+238h+var_148], r12
0x18000dfce  jz      loc_18000E906
0x18000dfd4  mov     [rsp+238h+var_1C0], r12
0x18000dfd9  mov     [rsp+238h+var_190], r12d
0x18000dfe1  mov     rcx, [rdi+18h]
0x18000dfe5  mov     rax, [rcx]
0x18000dfe8  lea     rdx, [rsp+238h+var_1C0]
0x18000dfed  mov     rax, [rax+28h]
0x18000dff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dff6  test    eax, eax
0x18000dff8  js      loc_18000E8E3
0x18000dffe  mov     rcx, [rsp+238h+var_1C0]
0x18000e003  mov     rax, [rcx]
0x18000e006  lea     rdx, [rsp+238h+var_190]
0x18000e00e  mov     rax, [rax+38h]
0x18000e012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e017  test    eax, eax
0x18000e019  js      loc_18000E8C0
0x18000e01f  mov     r13d, r12d
0x18000e022  cmp     r13d, [rsp+238h+var_190]
0x18000e02a  jnb     loc_18000E8A6
0x18000e030  mov     [rsp+238h+var_1A8], r12
0x18000e038  mov     [rsp+238h+var_1E0], r12
0x18000e03d  mov     [rsp+238h+var_1B0], r12
0x18000e045  mov     [rsp+238h+var_1B8], r12
0x18000e04d  mov     [rsp+238h+var_1C8], r12
0x18000e052  mov     [rsp+238h+pv], r12
0x18000e057  mov     [rsp+238h+var_1D8], r12
0x18000e05c  mov     [rsp+238h+var_19C], r12d
0x18000e064  xorps   xmm0, xmm0
0x18000e067  xor     eax, eax
0x18000e069  movups  [rsp+238h+var_A8], xmm0
0x18000e071  mov     [rsp+238h+var_98], rax
0x18000e079  mov     rcx, [rsp+238h+var_1C0]
0x18000e07e  mov     rax, [rcx]
0x18000e081  xor     r9d, r9d
0x18000e084  lea     r8, [rsp+238h+var_1E0]
0x18000e089  lea     edx, [r9+1]
0x18000e08d  mov     rax, [rax+18h]
0x18000e091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e096  test    eax, eax
0x18000e098  js      loc_18000E82A
0x18000e09e  lea     rdx, [rsp+238h+var_1B0]
0x18000e0a6  lea     rcx, [rsp+238h+var_1E0]
0x18000e0ab  call    ??$QueryInterface@UIBackgroundCopyFile2@@@?$CComPtrBase@UIBackgroundCopyFile@@@ATL@@QEBAJPEAPEAUIBackgroundCopyFile2@@@Z; ATL::CComPtrBase<IBackgroundCopyFile>::QueryInterface<IBackgroundCopyFile2>(IBackgroundCopyFile2 * *)
0x18000e0b0  test    eax, eax
0x18000e0b2  js      loc_18000E7AE
0x18000e0b8  mov     rcx, [rsp+238h+var_1E0]
0x18000e0bd  mov     rax, [rcx]
0x18000e0c0  lea     r8, [rsp+238h+var_1B8]
0x18000e0c8  lea     rdx, _GUID_659cdeaa_489e_11d9_a9cd_000d56965251
0x18000e0cf  mov     rax, [rax]
0x18000e0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d7  nop
0x18000e0d8  test    eax, eax
0x18000e0da  js      loc_18000E732
0x18000e0e0  mov     rcx, [rsp+238h+var_1E0]
0x18000e0e5  mov     rax, [rcx]
0x18000e0e8  lea     rdx, [rsp+238h+var_A8]
0x18000e0f0  mov     rax, [rax+28h]
0x18000e0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0f9  test    eax, eax
0x18000e0fb  js      loc_18000E6B6
0x18000e101  mov     r15, [rsp+238h+var_1B8]
0x18000e109  mov     rax, [r15]
0x18000e10c  mov     r12, [rax+40h]
0x18000e110  mov     r14, [rsp+238h+pv]
0x18000e115  test    r14, r14
0x18000e118  jz      short loc_18000E13D
0x18000e11a  lea     rcx, [rsp+238h+var_178]; this
0x18000e122  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e127  mov     rcx, r14; pv
0x18000e12a  call    cs:__imp_CoTaskMemFree
0x18000e130  lea     rcx, [rsp+238h+var_178]; this
0x18000e138  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e13d  mov     [rsp+238h+pv], 0
0x18000e146  lea     rdx, [rsp+238h+pv]
0x18000e14b  mov     rcx, r15
0x18000e14e  mov     rax, r12
0x18000e151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e156  xor     r12d, r12d
0x18000e159  test    eax, eax
0x18000e15b  js      loc_18000E63A
0x18000e161  mov     [rsp+238h+var_1E8], r12b
0x18000e166  lea     rdx, [rsp+238h+var_1E8]; bool *
0x18000e16b  mov     rcx, [rsp+238h+pv]; unsigned __int16 *
0x18000e170  call    ?FileExists@@YAJPEBGPEA_N@Z; FileExists(ushort const *,bool *)
0x18000e175  test    eax, eax
0x18000e177  js      loc_18000E5BE
0x18000e17d  mov     rax, qword ptr [rsp+238h+var_A8]
0x18000e185  cmp     qword ptr [rsp+238h+var_A8+8], rax
0x18000e18d  jnz     short loc_18000E19A
0x18000e18f  cmp     [rsp+238h+var_1E8], r12b
0x18000e194  jz      loc_18000E3EC
0x18000e19a  mov     r15, [rsp+238h+var_1E0]
0x18000e19f  mov     rax, [r15]
0x18000e1a2  mov     r12, [rax+18h]
0x18000e1a6  mov     r14, [rsp+238h+var_1C8]
0x18000e1ab  test    r14, r14
0x18000e1ae  jz      short loc_18000E1D3
0x18000e1b0  lea     rcx, [rsp+238h+var_170]; this
0x18000e1b8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e1bd  mov     rcx, r14; pv
0x18000e1c0  call    cs:__imp_CoTaskMemFree
0x18000e1c6  lea     rcx, [rsp+238h+var_170]; this
0x18000e1ce  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e1d3  mov     [rsp+238h+var_1C8], 0
0x18000e1dc  lea     rdx, [rsp+238h+var_1C8]
0x18000e1e1  mov     rcx, r15
0x18000e1e4  mov     rax, r12
0x18000e1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1ec  test    eax, eax
0x18000e1ee  js      loc_18000E542
0x18000e1f4  mov     r15, [rsp+238h+var_1B0]
0x18000e1fc  mov     rax, [r15]
0x18000e1ff  mov     r12, [rax+30h]
0x18000e203  mov     r14, [rsp+238h+var_1D8]
0x18000e208  test    r14, r14
0x18000e20b  jz      short loc_18000E230
0x18000e20d  lea     rcx, [rsp+238h+var_168]; this
0x18000e215  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000e21a  mov     rcx, r14; pv
0x18000e21d  call    cs:__imp_CoTaskMemFree
0x18000e223  lea     rcx, [rsp+238h+var_168]; this
0x18000e22b  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000e230  mov     [rsp+238h+var_1D8], 0
0x18000e239  lea     r8, [rsp+238h+var_1D8]
0x18000e23e  lea     rdx, [rsp+238h+var_19C]
0x18000e246  mov     rcx, r15
0x18000e249  mov     rax, r12
0x18000e24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e251  xor     r12d, r12d
0x18000e254  test    eax, eax
0x18000e256  js      loc_18000E4C6
0x18000e25c  mov     [rsp+238h+var_188], r12
0x18000e264  mov     rax, [rsp+238h+var_1D8]
0x18000e269  lea     rcx, off_1800162A8
0x18000e270  mov     [rsp+238h+var_78], rcx
0x18000e278  mov     [rsp+238h+var_70], rax
0x18000e280  lea     rax, [rsp+238h+var_78]
0x18000e288  mov     [rsp+238h+var_40], rax
0x18000e290  lea     r9, [rsp+238h+var_188]
0x18000e298  lea     r8, [rsp+238h+var_78]
0x18000e2a0  mov     edx, [rsp+238h+var_19C]
0x18000e2a7  mov     rcx, [rsp+238h+var_1C8]
0x18000e2ac  call    ?GenerateRequestId@MapsBackgroundTransferJob@@CAJPEBGKAEBV?$function@$$A6AJKPEA_K0@Z@std@@PEAPEAG@Z; MapsBackgroundTransferJob::GenerateRequestId(ushort const *,ulong,std::function<long (ulong,unsigned __int64 *,unsigned __int64 *)> const &,ushort * *)
0x18000e2b1  mov     r14d, eax
0x18000e2b4  mov     rcx, [rsp+238h+var_40]
0x18000e2bc  test    rcx, rcx
0x18000e2bf  jz      short loc_18000E2DB
  ... truncated ...
```
