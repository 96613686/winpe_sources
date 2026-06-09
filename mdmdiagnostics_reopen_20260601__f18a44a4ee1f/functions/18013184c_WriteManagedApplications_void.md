# WriteManagedApplications(void)

- ea: `0x18013184c`
- end: `0x1801324eb`
- name: `?WriteManagedApplications@@YAJXZ`
- size: `3231`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180128138`

## callees

- `0x180019080`
- `0x1800e4408`
- `0x1800e5744`
- `0x1800e68b0`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x180105480`
- `0x180106b6c`
- `0x180106ee0`
- `0x18012269c`
- `0x180128854`
- `0x180128944`
- `0x180128c50`
- `0x1801293ec`
- `0x180129498`
- `0x180129aac`
- `0x180129ee0`
- `0x18013184c`
- `0x1801330e0`
- `0x180134e3c`
- `0x18013944c`
- `0x18013a39c`
- `0x18013ac2c`
- `0x18013b590`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013197a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180131a5e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180131b88`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180131c9f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180131d86`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801320ff`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132392`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801324b9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18013197a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180131a5e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180131b88`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180131c9f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180131d86`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801320ff`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180132392`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801324b9`

## string_xrefs

- `0x1801318d3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x1801319b6`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180131ab2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180131bc9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180131fe2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180132275`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

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
0x18013184c  push    rbx
0x18013184e  push    rsi
0x18013184f  push    rdi
0x180131850  push    r14
0x180131852  sub     rsp, 178h
0x180131859  mov     rax, cs:__security_cookie
0x180131860  xor     rax, rsp
0x180131863  mov     [rsp+198h+var_38], rax
0x18013186b  lea     rcx, [rsp+198h+var_178]; this
0x180131870  call    ??0ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::ProvisionedResources(void)
0x180131875  nop
0x180131876  lea     rcx, [rsp+198h+var_170]
0x18013187b  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180131880  nop
0x180131881  lea     rcx, [rsp+198h+var_C8]
0x180131889  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x18013188e  nop
0x18013188f  lea     rcx, [rsp+198h+var_140]
0x180131894  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180131899  nop
0x18013189a  lea     rcx, [rsp+198h+var_150]
0x18013189f  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x1801318a4  nop
0x1801318a5  lea     r9, [rsp+198h+var_150]
0x1801318aa  lea     r8, [rsp+198h+var_140]
0x1801318af  lea     rdx, aEnterprisemode_0; "EnterpriseModernAppManagement"
0x1801318b6  call    ?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(ushort const *,std::list<std::wstring> &,std::list<std::wstring> &)
0x1801318bb  mov     edi, eax
0x1801318bd  xor     r14d, r14d
0x1801318c0  test    eax, eax
0x1801318c2  jns     loc_18013198D
0x1801318c8  mov     rcx, [rsp+198h]; this
0x1801318d0  mov     r9d, eax; char *
0x1801318d3  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801318da  mov     edx, 835h; void *
0x1801318df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801318e4  nop
0x1801318e5  mov     rdx, [rsp+198h+var_150]
0x1801318ea  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801318ef  lea     ebx, [r14+30h]
0x1801318f3  mov     edx, ebx
0x1801318f5  mov     rcx, [rsp+198h+var_150]
0x1801318fa  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801318ff  nop
0x180131900  mov     rdx, [rsp+198h+var_140]
0x180131905  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x18013190a  mov     edx, ebx
0x18013190c  mov     rcx, [rsp+198h+var_140]
0x180131911  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131916  nop
0x180131917  lea     rcx, [rsp+198h+var_C8]
0x18013191f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180131924  nop
0x180131925  mov     rcx, [rsp+198h+var_170]; this
0x18013192a  test    rcx, rcx
0x18013192d  jz      short loc_180131973
0x18013192f  mov     rdx, qword ptr [rsp+198h+var_168]
0x180131934  call    ??$_Destroy_range@V?$allocator@UAppStatus@@@std@@@std@@YAXPEAUAppStatus@@QEAU1@AEAV?$allocator@UAppStatus@@@0@@Z; std::_Destroy_range<std::allocator<AppStatus>>(AppStatus *,AppStatus * const,std::allocator<AppStatus> &)
0x180131939  mov     rcx, [rsp+198h+var_170]
0x18013193e  mov     rax, qword ptr [rsp+198h+var_168+8]
0x180131943  sub     rax, rcx
0x180131946  sar     rax, 5
0x18013194a  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180131954  imul    rax, rdx
0x180131958  lea     rdx, [rax+rax*2]
0x18013195c  shl     rdx, 5
0x180131960  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131965  mov     [rsp+198h+var_170], r14
0x18013196a  xorps   xmm0, xmm0
0x18013196d  movdqu  [rsp+198h+var_168], xmm0
0x180131973  cmp     [rsp+198h+var_178], r14d
0x180131978  jz      short loc_180131986
0x18013197a  call    cs:__imp_CoUninitialize
0x180131981  nop     dword ptr [rax+rax+00h]
0x180131986  mov     eax, edi
0x180131988  jmp     loc_1801324CD
0x18013198d  lea     r9, [rsp+198h+var_170]
0x180131992  lea     r8, [rsp+198h+var_150]
0x180131997  lea     rdx, [rsp+198h+var_140]
0x18013199c  call    ?QueryEnterpriseModernAppNames@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0AEAV?$vector@UAppStatus@@V?$allocator@UAppStatus@@@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryEnterpriseModernAppNames(std::list<std::wstring> &,std::list<std::wstring> &,std::vector<AppStatus> &)
0x1801319a1  mov     edi, eax
0x1801319a3  test    eax, eax
0x1801319a5  jns     loc_180131A71
0x1801319ab  mov     rcx, [rsp+198h]; this
0x1801319b3  mov     r9d, eax; char *
0x1801319b6  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801319bd  mov     edx, 836h; void *
0x1801319c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801319c7  nop
0x1801319c8  mov     rdx, [rsp+198h+var_150]
0x1801319cd  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801319d2  mov     ebx, 30h ; '0'
0x1801319d7  mov     edx, ebx
0x1801319d9  mov     rcx, [rsp+198h+var_150]
0x1801319de  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801319e3  nop
0x1801319e4  mov     rdx, [rsp+198h+var_140]
0x1801319e9  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x1801319ee  mov     edx, ebx
0x1801319f0  mov     rcx, [rsp+198h+var_140]
0x1801319f5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801319fa  nop
0x1801319fb  lea     rcx, [rsp+198h+var_C8]
0x180131a03  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180131a08  nop
0x180131a09  mov     rcx, [rsp+198h+var_170]; this
0x180131a0e  test    rcx, rcx
0x180131a11  jz      short loc_180131A57
0x180131a13  mov     rdx, qword ptr [rsp+198h+var_168]
0x180131a18  call    ??$_Destroy_range@V?$allocator@UAppStatus@@@std@@@std@@YAXPEAUAppStatus@@QEAU1@AEAV?$allocator@UAppStatus@@@0@@Z; std::_Destroy_range<std::allocator<AppStatus>>(AppStatus *,AppStatus * const,std::allocator<AppStatus> &)
0x180131a1d  mov     rcx, [rsp+198h+var_170]
0x180131a22  mov     rax, qword ptr [rsp+198h+var_168+8]
0x180131a27  sub     rax, rcx
0x180131a2a  sar     rax, 5
0x180131a2e  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180131a38  imul    rax, rdx
0x180131a3c  lea     rdx, [rax+rax*2]
0x180131a40  shl     rdx, 5
0x180131a44  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131a49  mov     [rsp+198h+var_170], r14
0x180131a4e  xorps   xmm0, xmm0
0x180131a51  movdqu  [rsp+198h+var_168], xmm0
0x180131a57  cmp     [rsp+198h+var_178], r14d
0x180131a5c  jz      short loc_180131A6A
0x180131a5e  call    cs:__imp_CoUninitialize
0x180131a65  nop     dword ptr [rax+rax+00h]
0x180131a6a  mov     eax, edi
0x180131a6c  jmp     loc_1801324CD
0x180131a71  lea     rcx, [rsp+198h+var_120]
0x180131a76  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180131a7b  nop
0x180131a7c  lea     rcx, [rsp+198h+var_130]
0x180131a81  call    ??0?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::list<std::wstring>(void)
0x180131a86  nop
0x180131a87  lea     r9, [rsp+198h+var_130]
0x180131a8c  lea     r8, [rsp+198h+var_120]
0x180131a91  lea     rdx, aEnterprisedesk; "EnterpriseDesktopAppManagement"
0x180131a98  call    ?EnumerateResources@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::EnumerateResources(ushort const *,std::list<std::wstring> &,std::list<std::wstring> &)
0x180131a9d  mov     edi, eax
0x180131a9f  test    eax, eax
0x180131aa1  jns     loc_180131B9B
0x180131aa7  mov     rcx, [rsp+198h]; this
0x180131aaf  mov     r9d, eax; char *
0x180131ab2  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180131ab9  mov     edx, 83Ah; void *
0x180131abe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180131ac3  nop
0x180131ac4  mov     rdx, [rsp+198h+var_130]
0x180131ac9  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131ace  mov     ebx, 30h ; '0'
0x180131ad3  mov     edx, ebx
0x180131ad5  mov     rcx, [rsp+198h+var_130]
0x180131ada  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131adf  nop
0x180131ae0  mov     rdx, [rsp+198h+var_120]
0x180131ae5  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131aea  mov     edx, ebx
0x180131aec  mov     rcx, [rsp+198h+var_120]
0x180131af1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131af6  nop
0x180131af7  mov     rdx, [rsp+198h+var_150]
0x180131afc  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131b01  mov     edx, ebx
0x180131b03  mov     rcx, [rsp+198h+var_150]
0x180131b08  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131b0d  nop
0x180131b0e  mov     rdx, [rsp+198h+var_140]
0x180131b13  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131b18  mov     edx, ebx
0x180131b1a  mov     rcx, [rsp+198h+var_140]
0x180131b1f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131b24  nop
0x180131b25  lea     rcx, [rsp+198h+var_C8]
0x180131b2d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180131b32  nop
0x180131b33  mov     rcx, [rsp+198h+var_170]; this
0x180131b38  test    rcx, rcx
0x180131b3b  jz      short loc_180131B81
0x180131b3d  mov     rdx, qword ptr [rsp+198h+var_168]
0x180131b42  call    ??$_Destroy_range@V?$allocator@UAppStatus@@@std@@@std@@YAXPEAUAppStatus@@QEAU1@AEAV?$allocator@UAppStatus@@@0@@Z; std::_Destroy_range<std::allocator<AppStatus>>(AppStatus *,AppStatus * const,std::allocator<AppStatus> &)
0x180131b47  mov     rcx, [rsp+198h+var_170]
0x180131b4c  mov     rax, qword ptr [rsp+198h+var_168+8]
0x180131b51  sub     rax, rcx
0x180131b54  sar     rax, 5
0x180131b58  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180131b62  imul    rax, rdx
0x180131b66  lea     rdx, [rax+rax*2]
0x180131b6a  shl     rdx, 5
0x180131b6e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131b73  mov     [rsp+198h+var_170], r14
0x180131b78  xorps   xmm0, xmm0
0x180131b7b  movdqu  [rsp+198h+var_168], xmm0
0x180131b81  cmp     [rsp+198h+var_178], r14d
0x180131b86  jz      short loc_180131B94
0x180131b88  call    cs:__imp_CoUninitialize
0x180131b8f  nop     dword ptr [rax+rax+00h]
0x180131b94  mov     eax, edi
0x180131b96  jmp     loc_1801324CD
0x180131b9b  lea     r9, [rsp+198h+var_170]
0x180131ba0  lea     r8, [rsp+198h+var_130]
0x180131ba5  lea     rdx, [rsp+198h+var_120]
0x180131baa  lea     rcx, [rsp+198h+var_178]
0x180131baf  call    ?QueryEnterpriseDesktopAppNames@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0AEAV?$vector@UAppStatus@@V?$allocator@UAppStatus@@@std@@@7@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::QueryEnterpriseDesktopAppNames(std::list<std::wstring> &,std::list<std::wstring> &,std::vector<AppStatus> &)
0x180131bb4  mov     edi, eax
0x180131bb6  test    eax, eax
0x180131bb8  jns     loc_180131CB2
0x180131bbe  mov     rcx, [rsp+198h]; this
0x180131bc6  mov     r9d, eax; char *
0x180131bc9  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180131bd0  mov     edx, 83Bh; void *
0x180131bd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180131bda  nop
0x180131bdb  mov     rdx, [rsp+198h+var_130]
0x180131be0  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131be5  mov     ebx, 30h ; '0'
0x180131bea  mov     edx, ebx
0x180131bec  mov     rcx, [rsp+198h+var_130]
0x180131bf1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131bf6  nop
0x180131bf7  mov     rdx, [rsp+198h+var_120]
0x180131bfc  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131c01  mov     edx, ebx
0x180131c03  mov     rcx, [rsp+198h+var_120]
0x180131c08  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131c0d  nop
0x180131c0e  mov     rdx, [rsp+198h+var_150]
0x180131c13  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131c18  mov     edx, ebx
0x180131c1a  mov     rcx, [rsp+198h+var_150]
0x180131c1f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131c24  nop
0x180131c25  mov     rdx, [rsp+198h+var_140]
0x180131c2a  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131c2f  mov     edx, ebx
0x180131c31  mov     rcx, [rsp+198h+var_140]
0x180131c36  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131c3b  nop
0x180131c3c  lea     rcx, [rsp+198h+var_C8]
0x180131c44  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180131c49  nop
0x180131c4a  mov     rcx, [rsp+198h+var_170]; this
0x180131c4f  test    rcx, rcx
0x180131c52  jz      short loc_180131C98
0x180131c54  mov     rdx, qword ptr [rsp+198h+var_168]
0x180131c59  call    ??$_Destroy_range@V?$allocator@UAppStatus@@@std@@@std@@YAXPEAUAppStatus@@QEAU1@AEAV?$allocator@UAppStatus@@@0@@Z; std::_Destroy_range<std::allocator<AppStatus>>(AppStatus *,AppStatus * const,std::allocator<AppStatus> &)
0x180131c5e  mov     rcx, [rsp+198h+var_170]
0x180131c63  mov     rax, qword ptr [rsp+198h+var_168+8]
0x180131c68  sub     rax, rcx
0x180131c6b  sar     rax, 5
0x180131c6f  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180131c79  imul    rax, rdx
0x180131c7d  lea     rdx, [rax+rax*2]
0x180131c81  shl     rdx, 5
0x180131c85  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131c8a  mov     [rsp+198h+var_170], r14
0x180131c8f  xorps   xmm0, xmm0
0x180131c92  movdqu  [rsp+198h+var_168], xmm0
0x180131c98  cmp     [rsp+198h+var_178], r14d
0x180131c9d  jz      short loc_180131CAB
0x180131c9f  call    cs:__imp_CoUninitialize
0x180131ca6  nop     dword ptr [rax+rax+00h]
0x180131cab  mov     eax, edi
0x180131cad  jmp     loc_1801324CD
0x180131cb2  mov     rax, qword ptr [rsp+198h+var_168]
0x180131cb7  cmp     rax, [rsp+198h+var_170]
0x180131cbc  jnz     loc_180131D99
0x180131cc2  mov     rdx, [rsp+198h+var_130]
0x180131cc7  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131ccc  mov     ebx, 30h ; '0'
0x180131cd1  mov     edx, ebx
0x180131cd3  mov     rcx, [rsp+198h+var_130]
0x180131cd8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131cdd  nop
0x180131cde  mov     rdx, [rsp+198h+var_120]
0x180131ce3  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131ce8  mov     edx, ebx
0x180131cea  mov     rcx, [rsp+198h+var_120]
0x180131cef  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131cf4  nop
0x180131cf5  mov     rdx, [rsp+198h+var_150]
0x180131cfa  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131cff  mov     edx, ebx
0x180131d01  mov     rcx, [rsp+198h+var_150]
0x180131d06  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131d0b  nop
0x180131d0c  mov     rdx, [rsp+198h+var_140]
0x180131d11  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Free_non_head<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180131d16  mov     edx, ebx
0x180131d18  mov     rcx, [rsp+198h+var_140]
0x180131d1d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180131d22  nop
0x180131d23  lea     rcx, [rsp+198h+var_C8]
0x180131d2b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180131d30  nop
0x180131d31  mov     rcx, [rsp+198h+var_170]; this
0x180131d36  test    rcx, rcx
0x180131d39  jz      short loc_180131D7F
0x180131d3b  mov     rdx, qword ptr [rsp+198h+var_168]
0x180131d40  call    ??$_Destroy_range@V?$allocator@UAppStatus@@@std@@@std@@YAXPEAUAppStatus@@QEAU1@AEAV?$allocator@UAppStatus@@@0@@Z; std::_Destroy_range<std::allocator<AppStatus>>(AppStatus *,AppStatus * const,std::allocator<AppStatus> &)
0x180131d45  mov     rcx, [rsp+198h+var_170]
  ... truncated ...
```
