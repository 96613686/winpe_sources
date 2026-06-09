# Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetFolderData(Microsoft::WRL::ComPtr<ITaskFolder>)

- ea: `0x180118554`
- end: `0x180118e39`
- name: `?GetFolderData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJV?$ComPtr@UITaskFolder@@@WRL@5@@Z`
- size: `2277`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180118e40`

## callees

- `0x180019080`
- `0x18001a054`
- `0x1800e7d84`
- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800f1b68`
- `0x180118554`
- `0x180119524`
- `0x180119570`
- `0x180119600`
- `0x180193010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801187d2`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801187d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180118ae0`
- `OLEAUT32!__imp_SysFreeString` at `0x180118b20`
- `OLEAUT32!__imp_SysFreeString` at `0x180118b79`
- `OLEAUT32!__imp_SysFreeString` at `0x180118bb6`
- `OLEAUT32!__imp_SysFreeString` at `0x180118bc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180118ae0`
- `OLEAUT32!__imp_SysFreeString` at `0x180118b20`
- `OLEAUT32!__imp_SysFreeString` at `0x180118b79`
- `OLEAUT32!__imp_SysFreeString` at `0x180118bb6`
- `OLEAUT32!__imp_SysFreeString` at `0x180118bc7`
- `OLEAUT32!__imp_VariantClear` at `0x18011871a`
- `OLEAUT32!__imp_VariantClear` at `0x18011871a`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180118804`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1801188c8`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x180118804`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1801188c8`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18011883b`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1801188fa`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18011883b`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1801188fa`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x18011886a`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180118929`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x18011886a`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180118929`

## string_xrefs

- `0x1801185ef`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x180118667`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x180118763`: `TaskName`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetFolderData(
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *this,
        __int64 *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, unsigned __int16 **); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, __int64 **); // rbx
  int v11; // r14d
  int v12; // eax
  __int64 v13; // rdx
  LONG v14; // r13d
  __int64 *v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, unsigned __int16 **); // rbx
  __int64 v19; // rdi
  void (__fastcall *v20)(__int64, __int64 *); // rbx
  __int64 v21; // rdi
  int (__fastcall *v22)(__int64, __int64 *); // rbx
  OLECHAR *v23; // rcx
  __int64 v24; // rdi
  void (__fastcall *v25)(__int64, _QWORD, unsigned __int16 **); // rbx
  unsigned __int16 *v26; // rdi
  void (__fastcall *v27)(unsigned __int16 *, __int64 *); // rbx
  const unsigned __int16 *v28; // r8
  __int64 v29; // rdi
  void (__fastcall *v30)(__int64, __int64 *); // rbx
  __int64 v31; // rdi
  void (__fastcall *v32)(__int64, __int64, _QWORD); // rbx
  void (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v34)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v35; // rbx
  void (__fastcall *v36)(__int64, unsigned __int16 **); // rdi
  __int64 v37; // rdi
  void (__fastcall *v38)(__int64, unsigned __int16 **); // rbx
  int lpDateStr; // [rsp+28h] [rbp-E0h]
  __int64 v41; // [rsp+48h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int16 *v43; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A8h] BYREF
  __int64 *v45; // [rsp+68h] [rbp-A0h] BYREF
  int v46; // [rsp+70h] [rbp-98h] BYREF
  LONG v47; // [rsp+74h] [rbp-94h] BYREF
  __int64 v48; // [rsp+78h] [rbp-90h] BYREF
  __int64 v49; // [rsp+80h] [rbp-88h] BYREF
  __int64 v50; // [rsp+88h] [rbp-80h] BYREF
  __int64 v51; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int16 *v52; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v53; // [rsp+A0h] [rbp-68h] BYREF
  int v54; // [rsp+A4h] [rbp-64h] BYREF
  int v55; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v56; // [rsp+B0h] [rbp-58h] BYREF
  DOUBLE vtime; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v58; // [rsp+C0h] [rbp-48h] BYREF
  void (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int16 *v60; // [rsp+D0h] [rbp-38h] BYREF
  BSTR v61; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v62; // [rsp+E0h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+E8h] [rbp-20h] BYREF
  __int64 *v64; // [rsp+100h] [rbp-8h]
  __int64 v65; // [rsp+108h] [rbp+0h]
  VARIANTARG v66; // [rsp+118h] [rbp+10h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+138h] [rbp+30h] BYREF
  WCHAR DateStr[256]; // [rsp+148h] [rbp+40h] BYREF
  WCHAR TimeStr[256]; // [rsp+348h] [rbp+240h] BYREF
  unsigned __int16 v70[264]; // [rsp+548h] [rbp+440h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7B0h] [rbp+6A8h]

  v64 = a2;
  v60 = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)*a2 + 56LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v60,
    0);
  v6 = v5(v4, &v60);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 177;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\schedulesdiagdata.cpp",
      (const char *)(unsigned int)v6,
      lpDateStr);
    goto LABEL_41;
  }
  v6 = Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteStartElement(this, L"Folder");
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 179;
    goto LABEL_5;
  }
  v6 = Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
         this,
         L"FolderName",
         v60);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 180;
    goto LABEL_5;
  }
  v45 = 0;
  v9 = *a2;
  v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64 **))(*(_QWORD *)*a2 + 112LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
  v11 = 1;
  v12 = v10(v9, 1, &v45);
  v7 = v12;
  if ( v12 >= 0 )
  {
    v47 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, LONG *))(*v45 + 56))(v45, &v47);
    v7 = v12;
    if ( v12 >= 0 )
    {
      v14 = 0;
      while ( v14 < v47 )
      {
        v44 = 0;
        v15 = v45;
        v16 = *v45;
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
        ++v14;
        pvarg.vt = 3;
        pvarg.lVal = v14;
        v66 = pvarg;
        (*(void (__fastcall **)(__int64 *, VARIANTARG *, __int64 *))(v16 + 64))(v15, &v66, &v44);
        VariantClear(&pvarg);
        v52 = 0;
        v17 = v44;
        v18 = *(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v44 + 56LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v52,
          0);
        v18(v17, &v52);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteStartElement(this, L"Task");
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
          this,
          L"TaskName",
          v52);
        vtime = 0.0;
        (*(void (__fastcall **)(__int64, DOUBLE *))(*(_QWORD *)v44 + 120LL))(v44, &vtime);
        v53 = 0;
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v44 + 128LL))(v44, &v53);
        memset_0(v70, 0, 0x208u);
        _o__itow_s(v53, v70, 260, 10);
        Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
          this,
          L"LastResult",
          v70);
        SystemTime = 0;
        if ( VariantTimeToSystemTime(vtime, &SystemTime) )
        {
          if ( GetDateFormatEx(0, 1u, &SystemTime, 0, DateStr, 255, 0) )
          {
            if ( GetTimeFormatEx(0, 0, &SystemTime, 0, TimeStr, 255) )
            {
              Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
                this,
                L"LastRunDate",
                DateStr);
              Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
                this,
                L"LastRunTime",
                TimeStr);
              (*(void (__fastcall **)(__int64, DOUBLE *))(*(_QWORD *)v44 + 144LL))(v44, &vtime);
              if ( VariantTimeToSystemTime(vtime, &SystemTime) )
              {
                if ( GetDateFormatEx(0, 1u, &SystemTime, 0, DateStr, 255, 0)
                  && GetTimeFormatEx(0, 0, &SystemTime, 0, TimeStr, 255) )
                {
                  Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
                    this,
                    L"NextRunDate",
                    DateStr);
                  Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
                    this,
                    L"NextRunTime",
                    TimeStr);
                  v51 = 0;
                  v19 = v44;
                  v20 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 152LL);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v51);
                  v20(v19, &v51);
                  v50 = 0;
                  v62 = 0;
                  v65 = 0;
                  v21 = v51;
                  v22 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 72LL);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v50);
                  if ( v22(v21, &v50) >= 0 )
                  {
                    v46 = 0;
                    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v50 + 56LL))(v50, &v46) >= 0 )
                    {
                      v61 = 0;
                      v23 = 0;
                      bstrString = 0;
                      if ( v46 + 1 > 1 )
                      {
                        do
                        {
                          v43 = 0;
                          v24 = v50;
                          v25 = *(void (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)v50 + 64LL);
                          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
                          v25(v24, (unsigned int)v11, &v43);
                          v54 = 0;
                          (*(void (__fastcall **)(unsigned __int16 *, int *))(*(_QWORD *)v43 + 56LL))(v43, &v54);
                          if ( v54 == 1 )
                          {
                            (*(void (__fastcall **)(unsigned __int16 *, BSTR *))(*(_QWORD *)v43 + 112LL))(v43, &v61);
                            Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
                              this,
                              L"StartBoundary",
                              v61);
                            v48 = 0;
                            v26 = v43;
                            v27 = *(void (__fastcall **)(unsigned __int16 *, __int64 *))(*(_QWORD *)v43 + 80LL);
                            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v48);
                            v27(v26, &v48);
                            if ( v48 )
                            {
                              (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v48 + 72LL))(v48, &bstrString);
                              Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
                                this,
                                L"RepetitionDuration",
                                bstrString);
                              SysFreeString(bstrString);
                              bstrString = 0;
                              (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v48 + 56LL))(v48, &bstrString);
                              Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
                                this,
                                L"RepetitionInterval",
                                bstrString);
                              SysFreeString(bstrString);
                              bstrString = 0;
                              LOWORD(v41) = 0;
                              (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 88LL))(v48, &v41);
                              v28 = L"True";
                              if ( !(_WORD)v41 )
                                v28 = L"False";
                              Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
                                this,
                                L"RepetitionStopAtDurationEnd",
                                v28);
                              SysFreeString(bstrString);
                              bstrString = 0;
                            }
                            Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v48);
                          }
                          Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v43);
                          ++v11;
                        }
                        while ( v11 < v46 + 1 );
                        v23 = bstrString;
                      }
                      SysFreeString(v23);
                      SysFreeString(v61);
                      v11 = 1;
                    }
                  }
                  v49 = 0;
                  v29 = v51;
                  v30 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 136LL);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
                  v30(v29, &v49);
                  v55 = 0;
                  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 56LL))(v49, &v55);
                  if ( v55 != 1 )
                  {
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v50);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v51);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
                    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
                    v7 = -2147467259;
                    goto LABEL_41;
                  }
                  v59 = 0;
                  v31 = v49;
                  v32 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v49 + 64LL);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v59);
                  v32(v31, 1, &v59);
                  v56 = 0;
                  v33 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
                  v34 = **v59;
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v56);
                  v34(v33, &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047, &v56);
                  v35 = v56;
                  if ( v56 )
                  {
                    v43 = 0;
                    v36 = *(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v56 + 80LL);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                      &v43,
                      0);
                    v36(v35, &v43);
                    Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
                      this,
                      L"Executable",
                      v43);
                    v58 = 0;
                    v37 = v56;
                    v38 = *(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v56 + 96LL);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                      &v58,
                      0);
                    v38(v37, &v58);
                    Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(
                      this,
                      L"Parameters",
                      v58);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v43);
                  }
                  Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteEndElement(this);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v56);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v59);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v49);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v62);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v50);
                  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v51);
                }
              }
            }
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v52);
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v44);
      }
      v12 = Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteEndElement(this);
      v7 = v12;
      if ( v12 >= 0 )
      {
        Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
        v7 = 0;
        goto LABEL_41;
      }
      v13 = 347;
    }
    else
    {
      v13 = 186;
    }
  }
  else
  {
    v13 = 183;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\schedulesdiagdata.cpp",
    (const char *)(unsigned int)v12,
    lpDateStr);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v45);
LABEL_41:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v60);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a2);
  return v7;
}

```

## disassembly

```asm
0x180118554  mov     rax, rsp
0x180118557  mov     [rax+18h], rbx
0x18011855b  push    rbp
0x18011855c  push    rsi
0x18011855d  push    rdi
0x18011855e  push    r12
0x180118560  push    r13
0x180118562  push    r14
0x180118564  push    r15
0x180118566  lea     rbp, [rax-6A8h]
0x18011856d  sub     rsp, 770h
0x180118574  movaps  xmmword ptr [rax-48h], xmm6
0x180118578  mov     rax, cs:__security_cookie
0x18011857f  xor     rax, rsp
0x180118582  mov     [rbp+6A0h+var_50], rax
0x180118589  mov     r15, rdx
0x18011858c  mov     rsi, rcx
0x18011858f  mov     [rbp+6A0h+var_6A8], rdx
0x180118593  xor     r12d, r12d
0x180118596  mov     [rbp+6A0h+var_6D8], r12
0x18011859a  mov     rdi, [rdx]
0x18011859d  mov     rax, [rdi]
0x1801185a0  mov     rbx, [rax+38h]
0x1801185a4  xor     edx, edx
0x1801185a6  lea     rcx, [rbp+6A0h+var_6D8]
0x1801185aa  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801185af  lea     rdx, [rbp+6A0h+var_6D8]
0x1801185b3  mov     rcx, rdi
0x1801185b6  mov     rax, rbx
0x1801185b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801185be  mov     ebx, eax
0x1801185c0  test    eax, eax
0x1801185c2  jns     short loc_1801185CB
0x1801185c4  mov     edx, 0B1h
0x1801185c9  jmp     short loc_1801185E5
0x1801185cb  lea     rdx, aFolder; "Folder"
0x1801185d2  mov     rcx, rsi; this
0x1801185d5  call    ?WriteStartElement@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteStartElement(ushort const *)
0x1801185da  mov     ebx, eax
0x1801185dc  test    eax, eax
0x1801185de  jns     short loc_180118600
0x1801185e0  mov     edx, 0B3h; void *
0x1801185e5  mov     rcx, [rbp+6A8h]; this
0x1801185ec  mov     r9d, eax; char *
0x1801185ef  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801185f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801185fb  jmp     loc_180118DF5
0x180118600  mov     r8, [rbp+6A0h+var_6D8]; unsigned __int16 *
0x180118604  lea     rdx, aFoldername; "FolderName"
0x18011860b  mov     rcx, rsi; this
0x18011860e  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180118613  mov     ebx, eax
0x180118615  test    eax, eax
0x180118617  jns     short loc_180118620
0x180118619  mov     edx, 0B4h
0x18011861e  jmp     short loc_1801185E5
0x180118620  mov     [rsp+7A0h+var_740], r12
0x180118625  mov     rdi, [r15]
0x180118628  mov     rax, [rdi]
0x18011862b  mov     rbx, [rax+70h]
0x18011862f  lea     rcx, [rsp+7A0h+var_740]
0x180118634  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180118639  lea     r8, [rsp+7A0h+var_740]
0x18011863e  mov     r14d, 1
0x180118644  mov     edx, r14d
0x180118647  mov     rcx, rdi
0x18011864a  mov     rax, rbx
0x18011864d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118652  mov     ebx, eax
0x180118654  test    eax, eax
0x180118656  jns     short loc_180118683
0x180118658  mov     edx, 0B7h; void *
0x18011865d  mov     rcx, [rbp+6A8h]; this
0x180118664  mov     r9d, eax; char *
0x180118667  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18011866e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180118673  nop
0x180118674  lea     rcx, [rsp+7A0h+var_740]
0x180118679  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011867e  jmp     loc_180118DF5
0x180118683  mov     dword ptr [rsp+7A0h+var_738+4], r12d
0x180118688  mov     rcx, [rsp+7A0h+var_740]
0x18011868d  mov     rax, [rcx]
0x180118690  lea     rdx, [rsp+7A0h+var_738+4]
0x180118695  mov     rax, [rax+38h]
0x180118699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011869e  mov     ebx, eax
0x1801186a0  test    eax, eax
0x1801186a2  jns     short loc_1801186AB
0x1801186a4  mov     edx, 0BAh
0x1801186a9  jmp     short loc_18011865D
0x1801186ab  mov     r13d, r12d
0x1801186ae  cmp     dword ptr [rsp+7A0h+var_738+4], r12d
0x1801186b3  jle     loc_180118D81
0x1801186b9  xorps   xmm6, xmm6
0x1801186bc  mov     [rsp+7A0h+var_748], r12
0x1801186c1  mov     rdi, [rsp+7A0h+var_740]
0x1801186c6  mov     rbx, [rdi]
0x1801186c9  lea     rcx, [rsp+7A0h+var_748]
0x1801186ce  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801186d3  inc     r13d
0x1801186d6  mov     eax, 3
0x1801186db  mov     word ptr [rbp+6A0h+pvarg], ax
0x1801186df  mov     word ptr [rbp+6A0h+pvarg+8], r13w
0x1801186e4  mov     ecx, r13d
0x1801186e7  sar     ecx, 10h
0x1801186ea  mov     word ptr [rbp+6A0h+pvarg+0Ah], cx
0x1801186ee  movups  xmm0, xmmword ptr [rbp+6A0h+pvarg]
0x1801186f2  movaps  [rbp+6A0h+var_690], xmm0
0x1801186f6  movsd   xmm1, qword ptr [rbp+6A0h+pvarg+10h]
0x1801186fb  movsd   [rbp+6A0h+var_680], xmm1
0x180118700  lea     r8, [rsp+7A0h+var_748]
0x180118705  lea     rdx, [rbp+6A0h+var_690]
0x180118709  mov     rcx, rdi
0x18011870c  mov     rax, [rbx+40h]
0x180118710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118715  nop
0x180118716  lea     rcx, [rbp+6A0h+pvarg]; pvarg
0x18011871a  call    cs:__imp_VariantClear
0x180118721  nop     dword ptr [rax+rax+00h]
0x180118726  mov     [rbp+6A0h+var_710], r12
0x18011872a  mov     rdi, [rsp+7A0h+var_748]
0x18011872f  mov     rax, [rdi]
0x180118732  mov     rbx, [rax+38h]
0x180118736  xor     edx, edx
0x180118738  lea     rcx, [rbp+6A0h+var_710]
0x18011873c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180118741  lea     rdx, [rbp+6A0h+var_710]
0x180118745  mov     rcx, rdi
0x180118748  mov     rax, rbx
0x18011874b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118750  lea     rdx, aTask; "Task"
0x180118757  mov     rcx, rsi; this
0x18011875a  call    ?WriteStartElement@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteStartElement(ushort const *)
0x18011875f  mov     r8, [rbp+6A0h+var_710]; unsigned __int16 *
0x180118763  lea     rdx, aTaskname; "TaskName"
0x18011876a  mov     rcx, rsi; this
0x18011876d  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180118772  movsd   [rbp+6A0h+vtime], xmm6
0x180118777  mov     rcx, [rsp+7A0h+var_748]
0x18011877c  mov     rax, [rcx]
0x18011877f  lea     rdx, [rbp+6A0h+vtime]
0x180118783  mov     rax, [rax+78h]
0x180118787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011878c  mov     [rbp+6A0h+var_708], r12d
0x180118790  mov     rcx, [rsp+7A0h+var_748]
0x180118795  mov     rax, [rcx]
0x180118798  lea     rdx, [rbp+6A0h+var_708]
0x18011879c  mov     rax, [rax+80h]
0x1801187a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801187a8  xor     edx, edx; Val
0x1801187aa  mov     r8d, 208h; Size
0x1801187b0  lea     rcx, [rbp+6A0h+var_260]; void *
0x1801187b7  call    memset_0
0x1801187bc  mov     r9d, 0Ah
0x1801187c2  mov     r8d, 104h
0x1801187c8  lea     rdx, [rbp+6A0h+var_260]
0x1801187cf  mov     ecx, [rbp+6A0h+var_708]
0x1801187d2  call    cs:__imp__o__itow_s
0x1801187d9  nop     dword ptr [rax+rax+00h]
0x1801187de  lea     r8, [rbp+6A0h+var_260]; unsigned __int16 *
0x1801187e5  lea     rdx, aLastresult; "LastResult"
0x1801187ec  mov     rcx, rsi; this
0x1801187ef  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x1801187f4  xorps   xmm0, xmm0
0x1801187f7  movups  xmmword ptr [rbp+6A0h+SystemTime.wYear], xmm0
0x1801187fb  lea     rdx, [rbp+6A0h+SystemTime]; lpSystemTime
0x1801187ff  movsd   xmm0, [rbp+6A0h+vtime]; vtime
0x180118804  call    cs:__imp_VariantTimeToSystemTime
0x18011880b  nop     dword ptr [rax+rax+00h]
0x180118810  test    eax, eax
0x180118812  jz      loc_180118D62
0x180118818  mov     [rsp+7A0h+lpCalendar], r12; lpCalendar
0x18011881d  mov     ebx, 0FFh
0x180118822  mov     [rsp+7A0h+cchDate], ebx; cchDate
0x180118826  lea     rax, [rbp+6A0h+DateStr]
0x18011882a  mov     [rsp+7A0h+lpDateStr], rax; lpDateStr
0x18011882f  xor     r9d, r9d; lpFormat
0x180118832  lea     r8, [rbp+6A0h+SystemTime]; lpDate
0x180118836  mov     edx, r14d; dwFlags
0x180118839  xor     ecx, ecx; lpLocaleName
0x18011883b  call    cs:__imp_GetDateFormatEx
0x180118842  nop     dword ptr [rax+rax+00h]
0x180118847  test    eax, eax
0x180118849  jz      loc_180118D62
0x18011884f  mov     [rsp+7A0h+cchDate], ebx; cchTime
0x180118853  lea     rax, [rbp+6A0h+TimeStr]
0x18011885a  mov     [rsp+7A0h+lpDateStr], rax; lpTimeStr
0x18011885f  xor     r9d, r9d; lpFormat
0x180118862  lea     r8, [rbp+6A0h+SystemTime]; lpTime
0x180118866  xor     edx, edx; dwFlags
0x180118868  xor     ecx, ecx; lpLocaleName
0x18011886a  call    cs:__imp_GetTimeFormatEx
0x180118871  nop     dword ptr [rax+rax+00h]
0x180118876  test    eax, eax
0x180118878  jz      loc_180118D62
0x18011887e  lea     r8, [rbp+6A0h+DateStr]; unsigned __int16 *
0x180118882  lea     rdx, aLastrundate; "LastRunDate"
0x180118889  mov     rcx, rsi; this
0x18011888c  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180118891  lea     r8, [rbp+6A0h+TimeStr]; unsigned __int16 *
0x180118898  lea     rdx, aLastruntime; "LastRunTime"
0x18011889f  mov     rcx, rsi; this
0x1801188a2  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x1801188a7  mov     rcx, [rsp+7A0h+var_748]
0x1801188ac  mov     rax, [rcx]
0x1801188af  lea     rdx, [rbp+6A0h+vtime]
0x1801188b3  mov     rax, [rax+90h]
0x1801188ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801188bf  lea     rdx, [rbp+6A0h+SystemTime]; lpSystemTime
0x1801188c3  movsd   xmm0, [rbp+6A0h+vtime]; vtime
0x1801188c8  call    cs:__imp_VariantTimeToSystemTime
0x1801188cf  nop     dword ptr [rax+rax+00h]
0x1801188d4  test    eax, eax
0x1801188d6  jz      loc_180118D62
0x1801188dc  mov     [rsp+7A0h+lpCalendar], r12; lpCalendar
0x1801188e1  mov     [rsp+7A0h+cchDate], ebx; cchDate
0x1801188e5  lea     rax, [rbp+6A0h+DateStr]
0x1801188e9  mov     [rsp+7A0h+lpDateStr], rax; lpDateStr
0x1801188ee  xor     r9d, r9d; lpFormat
0x1801188f1  lea     r8, [rbp+6A0h+SystemTime]; lpDate
0x1801188f5  mov     edx, r14d; dwFlags
0x1801188f8  xor     ecx, ecx; lpLocaleName
0x1801188fa  call    cs:__imp_GetDateFormatEx
0x180118901  nop     dword ptr [rax+rax+00h]
0x180118906  test    eax, eax
0x180118908  jz      loc_180118D62
0x18011890e  mov     [rsp+7A0h+cchDate], ebx; cchTime
0x180118912  lea     rax, [rbp+6A0h+TimeStr]
0x180118919  mov     [rsp+7A0h+lpDateStr], rax; lpTimeStr
0x18011891e  xor     r9d, r9d; lpFormat
0x180118921  lea     r8, [rbp+6A0h+SystemTime]; lpTime
0x180118925  xor     edx, edx; dwFlags
0x180118927  xor     ecx, ecx; lpLocaleName
0x180118929  call    cs:__imp_GetTimeFormatEx
0x180118930  nop     dword ptr [rax+rax+00h]
0x180118935  test    eax, eax
0x180118937  jz      loc_180118D62
0x18011893d  lea     r8, [rbp+6A0h+DateStr]; unsigned __int16 *
0x180118941  lea     rdx, aNextrundate; "NextRunDate"
0x180118948  mov     rcx, rsi; this
0x18011894b  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180118950  lea     r8, [rbp+6A0h+TimeStr]; unsigned __int16 *
0x180118957  lea     rdx, aNextruntime; "NextRunTime"
0x18011895e  mov     rcx, rsi; this
0x180118961  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180118966  mov     [rbp+6A0h+var_718], r12
0x18011896a  mov     rdi, [rsp+7A0h+var_748]
0x18011896f  mov     rax, [rdi]
0x180118972  mov     rbx, [rax+98h]
0x180118979  lea     rcx, [rbp+6A0h+var_718]
0x18011897d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180118982  lea     rdx, [rbp+6A0h+var_718]
0x180118986  mov     rcx, rdi
0x180118989  mov     rax, rbx
0x18011898c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118991  mov     [rbp+6A0h+var_720], r12
0x180118995  mov     [rbp+6A0h+var_6C8], r12
0x180118999  mov     [rbp+6A0h+var_6A0], r12
0x18011899d  mov     rdi, [rbp+6A0h+var_718]
0x1801189a1  mov     rax, [rdi]
0x1801189a4  mov     rbx, [rax+48h]
0x1801189a8  lea     rcx, [rbp+6A0h+var_720]
0x1801189ac  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801189b1  lea     rdx, [rbp+6A0h+var_720]
0x1801189b5  mov     rcx, rdi
0x1801189b8  mov     rax, rbx
0x1801189bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801189c0  test    eax, eax
0x1801189c2  js      loc_180118BD9
0x1801189c8  mov     dword ptr [rsp+7A0h+var_738], r12d
0x1801189cd  mov     rcx, [rbp+6A0h+var_720]
0x1801189d1  mov     rax, [rcx]
0x1801189d4  lea     rdx, [rsp+7A0h+var_738]
0x1801189d9  mov     rax, [rax+38h]
0x1801189dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801189e2  test    eax, eax
0x1801189e4  js      loc_180118BD9
0x1801189ea  mov     [rbp+6A0h+var_6D0], r12
0x1801189ee  mov     rcx, r12
0x1801189f1  mov     [rsp+7A0h+bstrString], rcx
0x1801189f6  mov     eax, dword ptr [rsp+7A0h+var_738]
0x1801189fa  inc     eax
0x1801189fc  cmp     eax, 1
0x1801189ff  jle     loc_180118BB6
0x180118a05  mov     [rsp+7A0h+var_750], r12
0x180118a0a  mov     rdi, [rbp+6A0h+var_720]
0x180118a0e  mov     rax, [rdi]
0x180118a11  mov     rbx, [rax+40h]
0x180118a15  lea     rcx, [rsp+7A0h+var_750]
0x180118a1a  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180118a1f  lea     r8, [rsp+7A0h+var_750]
0x180118a24  mov     edx, r14d
0x180118a27  mov     rcx, rdi
0x180118a2a  mov     rax, rbx
0x180118a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118a32  mov     [rbp+6A0h+var_704], r12d
0x180118a36  mov     rcx, [rsp+7A0h+var_750]
0x180118a3b  mov     rax, [rcx]
0x180118a3e  lea     rdx, [rbp+6A0h+var_704]
  ... truncated ...
```
