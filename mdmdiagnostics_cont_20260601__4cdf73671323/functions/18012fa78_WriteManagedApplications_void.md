# WriteManagedApplications(void)

- ea: `0x18012fa78`
- end: `0x1801306e7`
- name: `?WriteManagedApplications@@YAJXZ`
- size: `3183`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801266fc`

## callees

- `0x180019000`
- `0x1800e4348`
- `0x1800e5594`
- `0x1800e66dc`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x180104270`
- `0x1801058cc`
- `0x180105c40`
- `0x180120ce0`
- `0x180126e00`
- `0x180126ee8`
- `0x1801271ec`
- `0x180127908`
- `0x1801279ac`
- `0x180127fa8`
- `0x1801283b0`
- `0x18012fa78`
- `0x1801312d0`
- `0x180132f88`
- `0x1801373b8`
- `0x18013826c`
- `0x180138aa4`
- `0x1801393c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012fba6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012fc84`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012fda8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012feb9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012ff9a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013030d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013059a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801306bb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012fba6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012fc84`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012fda8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012feb9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18012ff9a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013030d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013059a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801306bb`

## string_xrefs

- `0x18012faff`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012fbdc`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012fcd2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012fde3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801301f0`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18013047d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 WriteManagedApplications(void)
{
  __int64 v0; // rcx
  int v1; // eax
  __int64 v2; // rcx
  unsigned int v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rcx
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // edi
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // edi
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  _DWORD *v28; // rdx
  _DWORD *v29; // rdx
  int v30; // eax
  unsigned int v31; // edi
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  AppStatus *v36; // rbx
  AppStatus *v37; // rsi
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  int v41; // eax
  unsigned int v42; // edi
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  int v51; // [rsp+20h] [rbp-178h] BYREF
  AppStatus *v52; // [rsp+28h] [rbp-170h] BYREF
  __int128 v53; // [rsp+30h] [rbp-168h]
  int v54; // [rsp+40h] [rbp-158h] BYREF
  _QWORD v55[2]; // [rsp+48h] [rbp-150h] BYREF
  _QWORD v56[2]; // [rsp+58h] [rbp-140h] BYREF
  _QWORD v57[2]; // [rsp+68h] [rbp-130h] BYREF
  _QWORD v58[2]; // [rsp+78h] [rbp-120h] BYREF
  _BYTE v59[8]; // [rsp+88h] [rbp-110h] BYREF
  _DWORD *v60; // [rsp+90h] [rbp-108h]
  _DWORD *v61; // [rsp+98h] [rbp-100h]
  _BYTE v62[8]; // [rsp+A0h] [rbp-F8h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-F0h]
  __int64 v64; // [rsp+B0h] [rbp-E8h]
  _BYTE v65[8]; // [rsp+B8h] [rbp-E0h] BYREF
  __int64 v66; // [rsp+C0h] [rbp-D8h]
  __int64 v67; // [rsp+C8h] [rbp-D0h]
  _BYTE v68[24]; // [rsp+D0h] [rbp-C8h] BYREF
  _BYTE v69[40]; // [rsp+E8h] [rbp-B0h] BYREF
  _QWORD v70[10]; // [rsp+110h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources((Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources *)&v51);
  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(&v52);
  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v68);
  std::list<std::wstring>::list<std::wstring>(v56);
  std::list<std::wstring>::list<std::wstring>(v55);
  v1 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(
         v0,
         (__int64)L"EnterpriseModernAppManagement",
         (int)v56,
         (int)v55);
  v3 = v1;
  if ( v1 >= 0 )
  {
    v7 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryEnterpriseModernAppNames(
           v2,
           v56,
           v55,
           &v52);
    v8 = v7;
    if ( v7 >= 0 )
    {
      std::list<std::wstring>::list<std::wstring>(v58);
      std::list<std::wstring>::list<std::wstring>(v57);
      v12 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(
              v11,
              (__int64)L"EnterpriseDesktopAppManagement",
              (int)v58,
              (int)v57);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v18 = Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryEnterpriseDesktopAppNames(
                &v51,
                v58,
                v57,
                &v52);
        v20 = v18;
        if ( v18 >= 0 )
        {
          if ( (AppStatus *)v53 == v52 )
          {
            std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
              v19,
              v57[0]);
            std::_Deallocate<16>(v57[0], 48);
            std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
              v25,
              v58[0]);
            std::_Deallocate<16>(v58[0], 48);
            std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
              v26,
              v55[0]);
            std::_Deallocate<16>(v55[0], 48);
            std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
              v27,
              v56[0]);
            std::_Deallocate<16>(v56[0], 48);
            std::vector<std::wstring>::_Tidy(v68);
            if ( v52 )
            {
              std::_Destroy_range<std::allocator<AppStatus>>(v52);
              std::_Deallocate<16>(v52, 32 * ((__int64)(*((_QWORD *)&v53 + 1) - (_QWORD)v52) >> 5));
              v52 = 0;
              v53 = 0;
            }
            if ( v51 )
              CoUninitialize();
            return 0;
          }
          else
          {
            std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v62);
            std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v65);
            std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v59);
            std::wstring::wstring(v69, L"Name");
            if ( v66 == v67 )
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v65, v66, v69);
            else
              std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v65, v69);
            std::wstring::_Tidy_deallocate(v69);
            std::wstring::wstring(v69, L"Status");
            if ( v66 == v67 )
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v65, v66, v69);
            else
              std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v65, v69);
            std::wstring::_Tidy_deallocate(v69);
            std::wstring::wstring(v69, L"Last Error");
            if ( v66 == v67 )
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v65, v66, v69);
            else
              std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v65, v69);
            std::wstring::_Tidy_deallocate(v69);
            v54 = 45;
            if ( v60 == v61 )
            {
              std::vector<enum TpmCapabilityPT>::_Emplace_reallocate<enum TpmCapabilityPT>(v59, v60, &v54);
              v28 = v60;
            }
            else
            {
              *v60 = 45;
              v28 = ++v60;
            }
            v54 = 40;
            if ( v28 == v61 )
            {
              std::vector<enum TpmCapabilityPT>::_Emplace_reallocate<enum TpmCapabilityPT>(v59, v28, &v54);
              v29 = v60;
            }
            else
            {
              *v28 = 40;
              v29 = ++v60;
            }
            v54 = 15;
            if ( v29 == v61 )
            {
              std::vector<enum TpmCapabilityPT>::_Emplace_reallocate<enum TpmCapabilityPT>(v59, v29, &v54);
            }
            else
            {
              *v29 = 15;
              ++v60;
            }
            Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::TableWithColumnHeaders(
              (Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders *)v70,
              L"Managed applications",
              L"ManagedApplicationsTable");
            v30 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::WriteSectionHeaderForTable(
                    v70,
                    0,
                    v65,
                    v59);
            v31 = v30;
            if ( v30 >= 0 )
            {
              v36 = v52;
              v37 = (AppStatus *)v53;
              while ( v36 != v37 )
              {
                std::vector<std::wstring>::clear(v62);
                v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
                std::wstring::wstring(v69, v38);
                if ( v63 == v64 )
                  std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v62, v63, v69);
                else
                  std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v62, v69);
                std::wstring::_Tidy_deallocate(v69);
                v39 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v36 + 32);
                std::wstring::wstring(v69, v39);
                if ( v63 == v64 )
                  std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v62, v63, v69);
                else
                  std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v62, v69);
                std::wstring::_Tidy_deallocate(v69);
                v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v36 + 64);
                std::wstring::wstring(v69, v40);
                if ( v63 == v64 )
                  std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v62, v63, v69);
                else
                  std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v62, v69);
                std::wstring::_Tidy_deallocate(v69);
                v41 = Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::AddTableRow(v70, v62);
                v42 = v41;
                if ( v41 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x85C,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
                    (const char *)(unsigned int)v41,
                    v51);
                  v70[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
                  Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v70);
                  std::vector<enum TpmCapabilityPT>::_Tidy(v59);
                  std::vector<std::wstring>::_Tidy(v65);
                  std::vector<std::wstring>::_Tidy(v62);
                  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                    v43,
                    v57[0]);
                  std::_Deallocate<16>(v57[0], 48);
                  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                    v44,
                    v58[0]);
                  std::_Deallocate<16>(v58[0], 48);
                  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                    v45,
                    v55[0]);
                  std::_Deallocate<16>(v55[0], 48);
                  std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                    v46,
                    v56[0]);
                  std::_Deallocate<16>(v56[0], 48);
                  std::vector<std::wstring>::_Tidy(v68);
                  if ( v52 )
                  {
                    std::_Destroy_range<std::allocator<AppStatus>>(v52);
                    std::_Deallocate<16>(v52, 32 * ((__int64)(*((_QWORD *)&v53 + 1) - (_QWORD)v52) >> 5));
                    v52 = 0;
                    v53 = 0;
                  }
                  if ( v51 )
                    CoUninitialize();
                  return v42;
                }
                v36 = (AppStatus *)((char *)v36 + 96);
              }
              v70[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
              Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v70);
              std::vector<enum TpmCapabilityPT>::_Tidy(v59);
              std::vector<std::wstring>::_Tidy(v65);
              std::vector<std::wstring>::_Tidy(v62);
              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                v47,
                v57[0]);
              std::_Deallocate<16>(v57[0], 48);
              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                v48,
                v58[0]);
              std::_Deallocate<16>(v58[0], 48);
              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                v49,
                v55[0]);
              std::_Deallocate<16>(v55[0], 48);
              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                v50,
                v56[0]);
              std::_Deallocate<16>(v56[0], 48);
              std::vector<std::wstring>::_Tidy(v68);
              if ( v52 )
              {
                std::_Destroy_range<std::allocator<AppStatus>>(v52);
                std::_Deallocate<16>(v52, 32 * ((__int64)(*((_QWORD *)&v53 + 1) - (_QWORD)v52) >> 5));
                v52 = 0;
                v53 = 0;
              }
              if ( v51 )
                CoUninitialize();
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x853,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
                (const char *)(unsigned int)v30,
                v51);
              v70[0] = &Microsoft::Windows::Mdm::MdmDiagnosticSource::TableWithColumnHeaders::`vftable';
              Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable::~SimpleTable((Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)v70);
              std::vector<enum TpmCapabilityPT>::_Tidy(v59);
              std::vector<std::wstring>::_Tidy(v65);
              std::vector<std::wstring>::_Tidy(v62);
              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                v32,
                v57[0]);
              std::_Deallocate<16>(v57[0], 48);
              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                v33,
                v58[0]);
              std::_Deallocate<16>(v58[0], 48);
              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                v34,
                v55[0]);
              std::_Deallocate<16>(v55[0], 48);
              std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
                v35,
                v56[0]);
              std::_Deallocate<16>(v56[0], 48);
              std::vector<std::wstring>::_Tidy(v68);
              if ( v52 )
              {
                std::_Destroy_range<std::allocator<AppStatus>>(v52);
                std::_Deallocate<16>(v52, 32 * ((__int64)(*((_QWORD *)&v53 + 1) - (_QWORD)v52) >> 5));
                v52 = 0;
                v53 = 0;
              }
              if ( v51 )
                CoUninitialize();
              return v31;
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x83B,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
            (const char *)(unsigned int)v18,
            v51);
          std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
            v21,
            v57[0]);
          std::_Deallocate<16>(v57[0], 48);
          std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
            v22,
            v58[0]);
          std::_Deallocate<16>(v58[0], 48);
          std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
            v23,
            v55[0]);
          std::_Deallocate<16>(v55[0], 48);
          std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
            v24,
            v56[0]);
          std::_Deallocate<16>(v56[0], 48);
          std::vector<std::wstring>::_Tidy(v68);
          if ( v52 )
          {
            std::_Destroy_range<std::allocator<AppStatus>>(v52);
            std::_Deallocate<16>(v52, 32 * ((__int64)(*((_QWORD *)&v53 + 1) - (_QWORD)v52) >> 5));
            v52 = 0;
            v53 = 0;
          }
          if ( v51 )
            CoUninitialize();
          return v20;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x83A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v12,
          v51);
        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
          v14,
          v57[0]);
        std::_Deallocate<16>(v57[0], 48);
        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
          v15,
          v58[0]);
        std::_Deallocate<16>(v58[0], 48);
        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
          v16,
          v55[0]);
        std::_Deallocate<16>(v55[0], 48);
        std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
          v17,
          v56[0]);
        std::_Deallocate<16>(v56[0], 48);
        std::vector<std::wstring>::_Tidy(v68);
        if ( v52 )
        {
          std::_Destroy_range<std::allocator<AppStatus>>(v52);
          std::_Deallocate<16>(v52, 32 * ((__int64)(*((_QWORD *)&v53 + 1) - (_QWORD)v52) >> 5));
          v52 = 0;
          v53 = 0;
        }
        if ( v51 )
          CoUninitialize();
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x836,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v7,
        v51);
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
        v9,
        v55[0]);
      std::_Deallocate<16>(v55[0], 48);
      std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
        v10,
        v56[0]);
      std::_Deallocate<16>(v56[0], 48);
      std::vector<std::wstring>::_Tidy(v68);
      if ( v52 )
      {
        std::_Destroy_range<std::allocator<AppStatus>>(v52);
        std::_Deallocate<16>(v52, 32 * ((__int64)(*((_QWORD *)&v53 + 1) - (_QWORD)v52) >> 5));
        v52 = 0;
        v53 = 0;
      }
      if ( v51 )
        CoUninitialize();
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x835,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
      (const char *)(unsigned int)v1,
      v51);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v4,
      v55[0]);
    std::_Deallocate<16>(v55[0], 48);
    std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(
      v5,
      v56[0]);
    std::_Deallocate<16>(v56[0], 48);
    std::vector<std::wstring>::_Tidy(v68);
    if ( v52 )
    {
      std::_Destroy_range<std::allocator<AppStatus>>(v52);
      std::_Deallocate<16>(v52, 32 * ((__int64)(*((_QWORD *)&v53 + 1) - (_QWORD)v52) >> 5));
      v52 = 0;
      v53 = 0;
    }
    if ( v51 )
      CoUninitialize();
    return v3;
  }
}

```

## disassembly

```asm
0x18012fa78  push    rbx
0x18012fa7a  push    rsi
0x18012fa7b  push    rdi
0x18012fa7c  push    r14
0x18012fa7e  sub     rsp, 178h
0x18012fa85  mov     rax, cs:__security_cookie
0x18012fa8c  xor     rax, rsp
0x18012fa8f  mov     [rsp+198h+var_38], rax
0x18012fa97  lea     rcx, [rsp+198h+var_178]; this
0x18012fa9c  call    ??0ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources(void)
0x18012faa1  nop
0x18012faa2  lea     rcx, [rsp+198h+var_170]
0x18012faa7  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012faac  nop
0x18012faad  lea     rcx, [rsp+198h+var_C8]
0x18012fab5  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18012faba  nop
0x18012fabb  lea     rcx, [rsp+198h+var_140]
0x18012fac0  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x18012fac5  nop
0x18012fac6  lea     rcx, [rsp+198h+var_150]
0x18012facb  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x18012fad0  nop
0x18012fad1  lea     r9, [rsp+198h+var_150]
0x18012fad6  lea     r8, [rsp+198h+var_140]
0x18012fadb  lea     rdx, aEnterprisemode_0; "EnterpriseModernAppManagement"
0x18012fae2  call    ?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(ushort const *,std::list<std::wstring> &,std::list<std::wstring> &)
0x18012fae7  mov     edi, eax
0x18012fae9  xor     r14d, r14d
0x18012faec  test    eax, eax
0x18012faee  jns     loc_18012FBB3
0x18012faf4  mov     rcx, [rsp+198h]; this
0x18012fafc  mov     r9d, eax; char *
0x18012faff  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012fb06  mov     edx, 835h; void *
0x18012fb0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fb10  nop
0x18012fb11  mov     rdx, [rsp+198h+var_150]
0x18012fb16  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fb1b  lea     ebx, [r14+30h]
0x18012fb1f  mov     edx, ebx
0x18012fb21  mov     rcx, [rsp+198h+var_150]
0x18012fb26  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fb2b  nop
0x18012fb2c  mov     rdx, [rsp+198h+var_140]
0x18012fb31  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fb36  mov     edx, ebx
0x18012fb38  mov     rcx, [rsp+198h+var_140]
0x18012fb3d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fb42  nop
0x18012fb43  lea     rcx, [rsp+198h+var_C8]
0x18012fb4b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012fb50  nop
0x18012fb51  mov     rcx, [rsp+198h+var_170]; this
0x18012fb56  test    rcx, rcx
0x18012fb59  jz      short loc_18012FB9F
0x18012fb5b  mov     rdx, qword ptr [rsp+198h+var_168]
0x18012fb60  call    ??$_Destroy_range@V?$allocator@UAppStatus@@@std@@@std@@YAXPEAUAppStatus@@QEAU1@AEAV?$allocator@UAppStatus@@@0@@Z; std::_Destroy_range<std::allocator<AppStatus>>(AppStatus *,AppStatus * const,std::allocator<AppStatus> &)
0x18012fb65  mov     rcx, [rsp+198h+var_170]
0x18012fb6a  mov     rax, qword ptr [rsp+198h+var_168+8]
0x18012fb6f  sub     rax, rcx
0x18012fb72  sar     rax, 5
0x18012fb76  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18012fb80  imul    rax, rdx
0x18012fb84  lea     rdx, [rax+rax*2]
0x18012fb88  shl     rdx, 5
0x18012fb8c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fb91  mov     [rsp+198h+var_170], r14
0x18012fb96  xorps   xmm0, xmm0
0x18012fb99  movdqu  [rsp+198h+var_168], xmm0
0x18012fb9f  cmp     [rsp+198h+var_178], r14d
0x18012fba4  jz      short loc_18012FBAC
0x18012fba6  call    cs:__imp_CoUninitialize
0x18012fbac  mov     eax, edi
0x18012fbae  jmp     loc_1801306C9
0x18012fbb3  lea     r9, [rsp+198h+var_170]
0x18012fbb8  lea     r8, [rsp+198h+var_150]
0x18012fbbd  lea     rdx, [rsp+198h+var_140]
0x18012fbc2  call    ?QueryEnterpriseModernAppNames@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0AEAV?$vector@UAppStatus@@V?$allocator@UAppStatus@@@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryEnterpriseModernAppNames(std::list<std::wstring> &,std::list<std::wstring> &,std::vector<AppStatus> &)
0x18012fbc7  mov     edi, eax
0x18012fbc9  test    eax, eax
0x18012fbcb  jns     loc_18012FC91
0x18012fbd1  mov     rcx, [rsp+198h]; this
0x18012fbd9  mov     r9d, eax; char *
0x18012fbdc  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012fbe3  mov     edx, 836h; void *
0x18012fbe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fbed  nop
0x18012fbee  mov     rdx, [rsp+198h+var_150]
0x18012fbf3  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fbf8  mov     ebx, 30h ; '0'
0x18012fbfd  mov     edx, ebx
0x18012fbff  mov     rcx, [rsp+198h+var_150]
0x18012fc04  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fc09  nop
0x18012fc0a  mov     rdx, [rsp+198h+var_140]
0x18012fc0f  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fc14  mov     edx, ebx
0x18012fc16  mov     rcx, [rsp+198h+var_140]
0x18012fc1b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fc20  nop
0x18012fc21  lea     rcx, [rsp+198h+var_C8]
0x18012fc29  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012fc2e  nop
0x18012fc2f  mov     rcx, [rsp+198h+var_170]; this
0x18012fc34  test    rcx, rcx
0x18012fc37  jz      short loc_18012FC7D
0x18012fc39  mov     rdx, qword ptr [rsp+198h+var_168]
0x18012fc3e  call    ??$_Destroy_range@V?$allocator@UAppStatus@@@std@@@std@@YAXPEAUAppStatus@@QEAU1@AEAV?$allocator@UAppStatus@@@0@@Z; std::_Destroy_range<std::allocator<AppStatus>>(AppStatus *,AppStatus * const,std::allocator<AppStatus> &)
0x18012fc43  mov     rcx, [rsp+198h+var_170]
0x18012fc48  mov     rax, qword ptr [rsp+198h+var_168+8]
0x18012fc4d  sub     rax, rcx
0x18012fc50  sar     rax, 5
0x18012fc54  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18012fc5e  imul    rax, rdx
0x18012fc62  lea     rdx, [rax+rax*2]
0x18012fc66  shl     rdx, 5
0x18012fc6a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fc6f  mov     [rsp+198h+var_170], r14
0x18012fc74  xorps   xmm0, xmm0
0x18012fc77  movdqu  [rsp+198h+var_168], xmm0
0x18012fc7d  cmp     [rsp+198h+var_178], r14d
0x18012fc82  jz      short loc_18012FC8A
0x18012fc84  call    cs:__imp_CoUninitialize
0x18012fc8a  mov     eax, edi
0x18012fc8c  jmp     loc_1801306C9
0x18012fc91  lea     rcx, [rsp+198h+var_120]
0x18012fc96  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x18012fc9b  nop
0x18012fc9c  lea     rcx, [rsp+198h+var_130]
0x18012fca1  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x18012fca6  nop
0x18012fca7  lea     r9, [rsp+198h+var_130]
0x18012fcac  lea     r8, [rsp+198h+var_120]
0x18012fcb1  lea     rdx, aEnterprisedesk; "EnterpriseDesktopAppManagement"
0x18012fcb8  call    ?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(ushort const *,std::list<std::wstring> &,std::list<std::wstring> &)
0x18012fcbd  mov     edi, eax
0x18012fcbf  test    eax, eax
0x18012fcc1  jns     loc_18012FDB5
0x18012fcc7  mov     rcx, [rsp+198h]; this
0x18012fccf  mov     r9d, eax; char *
0x18012fcd2  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012fcd9  mov     edx, 83Ah; void *
0x18012fcde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fce3  nop
0x18012fce4  mov     rdx, [rsp+198h+var_130]
0x18012fce9  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fcee  mov     ebx, 30h ; '0'
0x18012fcf3  mov     edx, ebx
0x18012fcf5  mov     rcx, [rsp+198h+var_130]
0x18012fcfa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fcff  nop
0x18012fd00  mov     rdx, [rsp+198h+var_120]
0x18012fd05  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fd0a  mov     edx, ebx
0x18012fd0c  mov     rcx, [rsp+198h+var_120]
0x18012fd11  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fd16  nop
0x18012fd17  mov     rdx, [rsp+198h+var_150]
0x18012fd1c  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fd21  mov     edx, ebx
0x18012fd23  mov     rcx, [rsp+198h+var_150]
0x18012fd28  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fd2d  nop
0x18012fd2e  mov     rdx, [rsp+198h+var_140]
0x18012fd33  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fd38  mov     edx, ebx
0x18012fd3a  mov     rcx, [rsp+198h+var_140]
0x18012fd3f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fd44  nop
0x18012fd45  lea     rcx, [rsp+198h+var_C8]
0x18012fd4d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012fd52  nop
0x18012fd53  mov     rcx, [rsp+198h+var_170]; this
0x18012fd58  test    rcx, rcx
0x18012fd5b  jz      short loc_18012FDA1
0x18012fd5d  mov     rdx, qword ptr [rsp+198h+var_168]
0x18012fd62  call    ??$_Destroy_range@V?$allocator@UAppStatus@@@std@@@std@@YAXPEAUAppStatus@@QEAU1@AEAV?$allocator@UAppStatus@@@0@@Z; std::_Destroy_range<std::allocator<AppStatus>>(AppStatus *,AppStatus * const,std::allocator<AppStatus> &)
0x18012fd67  mov     rcx, [rsp+198h+var_170]
0x18012fd6c  mov     rax, qword ptr [rsp+198h+var_168+8]
0x18012fd71  sub     rax, rcx
0x18012fd74  sar     rax, 5
0x18012fd78  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18012fd82  imul    rax, rdx
0x18012fd86  lea     rdx, [rax+rax*2]
0x18012fd8a  shl     rdx, 5
0x18012fd8e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fd93  mov     [rsp+198h+var_170], r14
0x18012fd98  xorps   xmm0, xmm0
0x18012fd9b  movdqu  [rsp+198h+var_168], xmm0
0x18012fda1  cmp     [rsp+198h+var_178], r14d
0x18012fda6  jz      short loc_18012FDAE
0x18012fda8  call    cs:__imp_CoUninitialize
0x18012fdae  mov     eax, edi
0x18012fdb0  jmp     loc_1801306C9
0x18012fdb5  lea     r9, [rsp+198h+var_170]
0x18012fdba  lea     r8, [rsp+198h+var_130]
0x18012fdbf  lea     rdx, [rsp+198h+var_120]
0x18012fdc4  lea     rcx, [rsp+198h+var_178]
0x18012fdc9  call    ?QueryEnterpriseDesktopAppNames@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0AEAV?$vector@UAppStatus@@V?$allocator@UAppStatus@@@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryEnterpriseDesktopAppNames(std::list<std::wstring> &,std::list<std::wstring> &,std::vector<AppStatus> &)
0x18012fdce  mov     edi, eax
0x18012fdd0  test    eax, eax
0x18012fdd2  jns     loc_18012FEC6
0x18012fdd8  mov     rcx, [rsp+198h]; this
0x18012fde0  mov     r9d, eax; char *
0x18012fde3  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012fdea  mov     edx, 83Bh; void *
0x18012fdef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fdf4  nop
0x18012fdf5  mov     rdx, [rsp+198h+var_130]
0x18012fdfa  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fdff  mov     ebx, 30h ; '0'
0x18012fe04  mov     edx, ebx
0x18012fe06  mov     rcx, [rsp+198h+var_130]
0x18012fe0b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fe10  nop
0x18012fe11  mov     rdx, [rsp+198h+var_120]
0x18012fe16  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fe1b  mov     edx, ebx
0x18012fe1d  mov     rcx, [rsp+198h+var_120]
0x18012fe22  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fe27  nop
0x18012fe28  mov     rdx, [rsp+198h+var_150]
0x18012fe2d  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fe32  mov     edx, ebx
0x18012fe34  mov     rcx, [rsp+198h+var_150]
0x18012fe39  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fe3e  nop
0x18012fe3f  mov     rdx, [rsp+198h+var_140]
0x18012fe44  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fe49  mov     edx, ebx
0x18012fe4b  mov     rcx, [rsp+198h+var_140]
0x18012fe50  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fe55  nop
0x18012fe56  lea     rcx, [rsp+198h+var_C8]
0x18012fe5e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012fe63  nop
0x18012fe64  mov     rcx, [rsp+198h+var_170]; this
0x18012fe69  test    rcx, rcx
0x18012fe6c  jz      short loc_18012FEB2
0x18012fe6e  mov     rdx, qword ptr [rsp+198h+var_168]
0x18012fe73  call    ??$_Destroy_range@V?$allocator@UAppStatus@@@std@@@std@@YAXPEAUAppStatus@@QEAU1@AEAV?$allocator@UAppStatus@@@0@@Z; std::_Destroy_range<std::allocator<AppStatus>>(AppStatus *,AppStatus * const,std::allocator<AppStatus> &)
0x18012fe78  mov     rcx, [rsp+198h+var_170]
0x18012fe7d  mov     rax, qword ptr [rsp+198h+var_168+8]
0x18012fe82  sub     rax, rcx
0x18012fe85  sar     rax, 5
0x18012fe89  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18012fe93  imul    rax, rdx
0x18012fe97  lea     rdx, [rax+rax*2]
0x18012fe9b  shl     rdx, 5
0x18012fe9f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fea4  mov     [rsp+198h+var_170], r14
0x18012fea9  xorps   xmm0, xmm0
0x18012feac  movdqu  [rsp+198h+var_168], xmm0
0x18012feb2  cmp     [rsp+198h+var_178], r14d
0x18012feb7  jz      short loc_18012FEBF
0x18012feb9  call    cs:__imp_CoUninitialize
0x18012febf  mov     eax, edi
0x18012fec1  jmp     loc_1801306C9
0x18012fec6  mov     rax, qword ptr [rsp+198h+var_168]
0x18012fecb  cmp     rax, [rsp+198h+var_170]
0x18012fed0  jnz     loc_18012FFA7
0x18012fed6  mov     rdx, [rsp+198h+var_130]
0x18012fedb  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fee0  mov     ebx, 30h ; '0'
0x18012fee5  mov     edx, ebx
0x18012fee7  mov     rcx, [rsp+198h+var_130]
0x18012feec  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012fef1  nop
0x18012fef2  mov     rdx, [rsp+198h+var_120]
0x18012fef7  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012fefc  mov     edx, ebx
0x18012fefe  mov     rcx, [rsp+198h+var_120]
0x18012ff03  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012ff08  nop
0x18012ff09  mov     rdx, [rsp+198h+var_150]
0x18012ff0e  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012ff13  mov     edx, ebx
0x18012ff15  mov     rcx, [rsp+198h+var_150]
0x18012ff1a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012ff1f  nop
0x18012ff20  mov     rdx, [rsp+198h+var_140]
0x18012ff25  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18012ff2a  mov     edx, ebx
0x18012ff2c  mov     rcx, [rsp+198h+var_140]
0x18012ff31  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18012ff36  nop
0x18012ff37  lea     rcx, [rsp+198h+var_C8]
0x18012ff3f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18012ff44  nop
0x18012ff45  mov     rcx, [rsp+198h+var_170]; this
0x18012ff4a  test    rcx, rcx
0x18012ff4d  jz      short loc_18012FF93
0x18012ff4f  mov     rdx, qword ptr [rsp+198h+var_168]
0x18012ff54  call    ??$_Destroy_range@V?$allocator@UAppStatus@@@std@@@std@@YAXPEAUAppStatus@@QEAU1@AEAV?$allocator@UAppStatus@@@0@@Z; std::_Destroy_range<std::allocator<AppStatus>>(AppStatus *,AppStatus * const,std::allocator<AppStatus> &)
0x18012ff59  mov     rcx, [rsp+198h+var_170]
0x18012ff5e  mov     rax, qword ptr [rsp+198h+var_168+8]
0x18012ff63  sub     rax, rcx
0x18012ff66  sar     rax, 5
0x18012ff6a  mov     rdx, 0AAAAAAAAAAAAAAABh
  ... truncated ...
```
