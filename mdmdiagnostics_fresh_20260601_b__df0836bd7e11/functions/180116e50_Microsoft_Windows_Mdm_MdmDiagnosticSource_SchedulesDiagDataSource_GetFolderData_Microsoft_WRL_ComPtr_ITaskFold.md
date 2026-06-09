# Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::GetFolderData(Microsoft::WRL::ComPtr<ITaskFolder>)

- ea: `0x180116e50`
- end: `0x1801176e6`
- name: `?GetFolderData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJV?$ComPtr@UITaskFolder@@@WRL@5@@Z`
- size: `2198`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801176ec`

## callees

- `0x180019000`
- `0x180019fc4`
- `0x1800e7bac`
- `0x1800ead14`
- `0x1800ece5c`
- `0x1800f1218`
- `0x180116e50`
- `0x180117d7c`
- `0x180117dc8`
- `0x180117e58`
- `0x180191010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801170c8`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1801170c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1801173ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1801173e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180117439`
- `OLEAUT32!__imp_SysFreeString` at `0x180117470`
- `OLEAUT32!__imp_SysFreeString` at `0x18011747b`
- `OLEAUT32!__imp_SysFreeString` at `0x1801173ac`
- `OLEAUT32!__imp_SysFreeString` at `0x1801173e6`
- `OLEAUT32!__imp_SysFreeString` at `0x180117439`
- `OLEAUT32!__imp_SysFreeString` at `0x180117470`
- `OLEAUT32!__imp_SysFreeString` at `0x18011747b`
- `OLEAUT32!__imp_VariantClear` at `0x180117016`
- `OLEAUT32!__imp_VariantClear` at `0x180117016`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1801170f4`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1801171a6`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1801170f4`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x1801171a6`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180117125`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1801171d2`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x180117125`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x1801171d2`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x18011714e`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1801171fb`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x18011714e`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x1801171fb`

## string_xrefs

- `0x180116eeb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x180116f63`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\schedulesdiagdata.cpp`
- `0x180117059`: `TaskName`

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
0x180116e50  mov     rax, rsp
0x180116e53  mov     [rax+18h], rbx
0x180116e57  push    rbp
0x180116e58  push    rsi
0x180116e59  push    rdi
0x180116e5a  push    r12
0x180116e5c  push    r13
0x180116e5e  push    r14
0x180116e60  push    r15
0x180116e62  lea     rbp, [rax-6A8h]
0x180116e69  sub     rsp, 770h
0x180116e70  movaps  xmmword ptr [rax-48h], xmm6
0x180116e74  mov     rax, cs:__security_cookie
0x180116e7b  xor     rax, rsp
0x180116e7e  mov     [rbp+6A0h+var_50], rax
0x180116e85  mov     r15, rdx
0x180116e88  mov     rsi, rcx
0x180116e8b  mov     [rbp+6A0h+var_6A8], rdx
0x180116e8f  xor     r12d, r12d
0x180116e92  mov     [rbp+6A0h+var_6D8], r12
0x180116e96  mov     rdi, [rdx]
0x180116e99  mov     rax, [rdi]
0x180116e9c  mov     rbx, [rax+38h]
0x180116ea0  xor     edx, edx
0x180116ea2  lea     rcx, [rbp+6A0h+var_6D8]
0x180116ea6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180116eab  lea     rdx, [rbp+6A0h+var_6D8]
0x180116eaf  mov     rcx, rdi
0x180116eb2  mov     rax, rbx
0x180116eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116eba  mov     ebx, eax
0x180116ebc  test    eax, eax
0x180116ebe  jns     short loc_180116EC7
0x180116ec0  mov     edx, 0B1h
0x180116ec5  jmp     short loc_180116EE1
0x180116ec7  lea     rdx, aFolder; "Folder"
0x180116ece  mov     rcx, rsi; this
0x180116ed1  call    ?WriteStartElement@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteStartElement(ushort const *)
0x180116ed6  mov     ebx, eax
0x180116ed8  test    eax, eax
0x180116eda  jns     short loc_180116EFC
0x180116edc  mov     edx, 0B3h; void *
0x180116ee1  mov     rcx, [rbp+6A8h]; this
0x180116ee8  mov     r9d, eax; char *
0x180116eeb  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180116ef2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116ef7  jmp     loc_1801176A3
0x180116efc  mov     r8, [rbp+6A0h+var_6D8]; unsigned __int16 *
0x180116f00  lea     rdx, aFoldername; "FolderName"
0x180116f07  mov     rcx, rsi; this
0x180116f0a  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180116f0f  mov     ebx, eax
0x180116f11  test    eax, eax
0x180116f13  jns     short loc_180116F1C
0x180116f15  mov     edx, 0B4h
0x180116f1a  jmp     short loc_180116EE1
0x180116f1c  mov     [rsp+7A0h+var_740], r12
0x180116f21  mov     rdi, [r15]
0x180116f24  mov     rax, [rdi]
0x180116f27  mov     rbx, [rax+70h]
0x180116f2b  lea     rcx, [rsp+7A0h+var_740]
0x180116f30  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180116f35  lea     r8, [rsp+7A0h+var_740]
0x180116f3a  mov     r14d, 1
0x180116f40  mov     edx, r14d
0x180116f43  mov     rcx, rdi
0x180116f46  mov     rax, rbx
0x180116f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116f4e  mov     ebx, eax
0x180116f50  test    eax, eax
0x180116f52  jns     short loc_180116F7F
0x180116f54  mov     edx, 0B7h; void *
0x180116f59  mov     rcx, [rbp+6A8h]; this
0x180116f60  mov     r9d, eax; char *
0x180116f63  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180116f6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180116f6f  nop
0x180116f70  lea     rcx, [rsp+7A0h+var_740]
0x180116f75  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180116f7a  jmp     loc_1801176A3
0x180116f7f  mov     dword ptr [rsp+7A0h+var_738+4], r12d
0x180116f84  mov     rcx, [rsp+7A0h+var_740]
0x180116f89  mov     rax, [rcx]
0x180116f8c  lea     rdx, [rsp+7A0h+var_738+4]
0x180116f91  mov     rax, [rax+38h]
0x180116f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116f9a  mov     ebx, eax
0x180116f9c  test    eax, eax
0x180116f9e  jns     short loc_180116FA7
0x180116fa0  mov     edx, 0BAh
0x180116fa5  jmp     short loc_180116F59
0x180116fa7  mov     r13d, r12d
0x180116faa  cmp     dword ptr [rsp+7A0h+var_738+4], r12d
0x180116faf  jle     loc_18011762F
0x180116fb5  xorps   xmm6, xmm6
0x180116fb8  mov     [rsp+7A0h+var_748], r12
0x180116fbd  mov     rdi, [rsp+7A0h+var_740]
0x180116fc2  mov     rbx, [rdi]
0x180116fc5  lea     rcx, [rsp+7A0h+var_748]
0x180116fca  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180116fcf  inc     r13d
0x180116fd2  mov     eax, 3
0x180116fd7  mov     word ptr [rbp+6A0h+pvarg], ax
0x180116fdb  mov     word ptr [rbp+6A0h+pvarg+8], r13w
0x180116fe0  mov     ecx, r13d
0x180116fe3  sar     ecx, 10h
0x180116fe6  mov     word ptr [rbp+6A0h+pvarg+0Ah], cx
0x180116fea  movups  xmm0, xmmword ptr [rbp+6A0h+pvarg]
0x180116fee  movaps  [rbp+6A0h+var_690], xmm0
0x180116ff2  movsd   xmm1, qword ptr [rbp+6A0h+pvarg+10h]
0x180116ff7  movsd   [rbp+6A0h+var_680], xmm1
0x180116ffc  lea     r8, [rsp+7A0h+var_748]
0x180117001  lea     rdx, [rbp+6A0h+var_690]
0x180117005  mov     rcx, rdi
0x180117008  mov     rax, [rbx+40h]
0x18011700c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117011  nop
0x180117012  lea     rcx, [rbp+6A0h+pvarg]; pvarg
0x180117016  call    cs:__imp_VariantClear
0x18011701c  mov     [rbp+6A0h+var_710], r12
0x180117020  mov     rdi, [rsp+7A0h+var_748]
0x180117025  mov     rax, [rdi]
0x180117028  mov     rbx, [rax+38h]
0x18011702c  xor     edx, edx
0x18011702e  lea     rcx, [rbp+6A0h+var_710]
0x180117032  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180117037  lea     rdx, [rbp+6A0h+var_710]
0x18011703b  mov     rcx, rdi
0x18011703e  mov     rax, rbx
0x180117041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117046  lea     rdx, aTask; "Task"
0x18011704d  mov     rcx, rsi; this
0x180117050  call    ?WriteStartElement@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteStartElement(ushort const *)
0x180117055  mov     r8, [rbp+6A0h+var_710]; unsigned __int16 *
0x180117059  lea     rdx, aTaskname; "TaskName"
0x180117060  mov     rcx, rsi; this
0x180117063  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180117068  movsd   [rbp+6A0h+vtime], xmm6
0x18011706d  mov     rcx, [rsp+7A0h+var_748]
0x180117072  mov     rax, [rcx]
0x180117075  lea     rdx, [rbp+6A0h+vtime]
0x180117079  mov     rax, [rax+78h]
0x18011707d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117082  mov     [rbp+6A0h+var_708], r12d
0x180117086  mov     rcx, [rsp+7A0h+var_748]
0x18011708b  mov     rax, [rcx]
0x18011708e  lea     rdx, [rbp+6A0h+var_708]
0x180117092  mov     rax, [rax+80h]
0x180117099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011709e  xor     edx, edx; Val
0x1801170a0  mov     r8d, 208h; Size
0x1801170a6  lea     rcx, [rbp+6A0h+var_260]; void *
0x1801170ad  call    memset_0
0x1801170b2  mov     r9d, 0Ah
0x1801170b8  mov     r8d, 104h
0x1801170be  lea     rdx, [rbp+6A0h+var_260]
0x1801170c5  mov     ecx, [rbp+6A0h+var_708]
0x1801170c8  call    cs:__imp__o__itow_s
0x1801170ce  lea     r8, [rbp+6A0h+var_260]; unsigned __int16 *
0x1801170d5  lea     rdx, aLastresult; "LastResult"
0x1801170dc  mov     rcx, rsi; this
0x1801170df  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x1801170e4  xorps   xmm0, xmm0
0x1801170e7  movups  xmmword ptr [rbp+6A0h+SystemTime.wYear], xmm0
0x1801170eb  lea     rdx, [rbp+6A0h+SystemTime]; lpSystemTime
0x1801170ef  movsd   xmm0, [rbp+6A0h+vtime]; vtime
0x1801170f4  call    cs:__imp_VariantTimeToSystemTime
0x1801170fa  test    eax, eax
0x1801170fc  jz      loc_180117610
0x180117102  mov     [rsp+7A0h+lpCalendar], r12; lpCalendar
0x180117107  mov     ebx, 0FFh
0x18011710c  mov     [rsp+7A0h+cchDate], ebx; cchDate
0x180117110  lea     rax, [rbp+6A0h+DateStr]
0x180117114  mov     [rsp+7A0h+lpDateStr], rax; lpDateStr
0x180117119  xor     r9d, r9d; lpFormat
0x18011711c  lea     r8, [rbp+6A0h+SystemTime]; lpDate
0x180117120  mov     edx, r14d; dwFlags
0x180117123  xor     ecx, ecx; lpLocaleName
0x180117125  call    cs:__imp_GetDateFormatEx
0x18011712b  test    eax, eax
0x18011712d  jz      loc_180117610
0x180117133  mov     [rsp+7A0h+cchDate], ebx; cchTime
0x180117137  lea     rax, [rbp+6A0h+TimeStr]
0x18011713e  mov     [rsp+7A0h+lpDateStr], rax; lpTimeStr
0x180117143  xor     r9d, r9d; lpFormat
0x180117146  lea     r8, [rbp+6A0h+SystemTime]; lpTime
0x18011714a  xor     edx, edx; dwFlags
0x18011714c  xor     ecx, ecx; lpLocaleName
0x18011714e  call    cs:__imp_GetTimeFormatEx
0x180117154  test    eax, eax
0x180117156  jz      loc_180117610
0x18011715c  lea     r8, [rbp+6A0h+DateStr]; unsigned __int16 *
0x180117160  lea     rdx, aLastrundate; "LastRunDate"
0x180117167  mov     rcx, rsi; this
0x18011716a  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x18011716f  lea     r8, [rbp+6A0h+TimeStr]; unsigned __int16 *
0x180117176  lea     rdx, aLastruntime; "LastRunTime"
0x18011717d  mov     rcx, rsi; this
0x180117180  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180117185  mov     rcx, [rsp+7A0h+var_748]
0x18011718a  mov     rax, [rcx]
0x18011718d  lea     rdx, [rbp+6A0h+vtime]
0x180117191  mov     rax, [rax+90h]
0x180117198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011719d  lea     rdx, [rbp+6A0h+SystemTime]; lpSystemTime
0x1801171a1  movsd   xmm0, [rbp+6A0h+vtime]; vtime
0x1801171a6  call    cs:__imp_VariantTimeToSystemTime
0x1801171ac  test    eax, eax
0x1801171ae  jz      loc_180117610
0x1801171b4  mov     [rsp+7A0h+lpCalendar], r12; lpCalendar
0x1801171b9  mov     [rsp+7A0h+cchDate], ebx; cchDate
0x1801171bd  lea     rax, [rbp+6A0h+DateStr]
0x1801171c1  mov     [rsp+7A0h+lpDateStr], rax; lpDateStr
0x1801171c6  xor     r9d, r9d; lpFormat
0x1801171c9  lea     r8, [rbp+6A0h+SystemTime]; lpDate
0x1801171cd  mov     edx, r14d; dwFlags
0x1801171d0  xor     ecx, ecx; lpLocaleName
0x1801171d2  call    cs:__imp_GetDateFormatEx
0x1801171d8  test    eax, eax
0x1801171da  jz      loc_180117610
0x1801171e0  mov     [rsp+7A0h+cchDate], ebx; cchTime
0x1801171e4  lea     rax, [rbp+6A0h+TimeStr]
0x1801171eb  mov     [rsp+7A0h+lpDateStr], rax; lpTimeStr
0x1801171f0  xor     r9d, r9d; lpFormat
0x1801171f3  lea     r8, [rbp+6A0h+SystemTime]; lpTime
0x1801171f7  xor     edx, edx; dwFlags
0x1801171f9  xor     ecx, ecx; lpLocaleName
0x1801171fb  call    cs:__imp_GetTimeFormatEx
0x180117201  test    eax, eax
0x180117203  jz      loc_180117610
0x180117209  lea     r8, [rbp+6A0h+DateStr]; unsigned __int16 *
0x18011720d  lea     rdx, aNextrundate; "NextRunDate"
0x180117214  mov     rcx, rsi; this
0x180117217  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x18011721c  lea     r8, [rbp+6A0h+TimeStr]; unsigned __int16 *
0x180117223  lea     rdx, aNextruntime; "NextRunTime"
0x18011722a  mov     rcx, rsi; this
0x18011722d  call    ?WriteSingleLineData@SchedulesDiagDataSource@MdmDiagnosticSource@Mdm@Windows@Microsoft@@AEAAJPEBG0@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::SchedulesDiagDataSource::WriteSingleLineData(ushort const *,ushort const *)
0x180117232  mov     [rbp+6A0h+var_718], r12
0x180117236  mov     rdi, [rsp+7A0h+var_748]
0x18011723b  mov     rax, [rdi]
0x18011723e  mov     rbx, [rax+98h]
0x180117245  lea     rcx, [rbp+6A0h+var_718]
0x180117249  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011724e  lea     rdx, [rbp+6A0h+var_718]
0x180117252  mov     rcx, rdi
0x180117255  mov     rax, rbx
0x180117258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011725d  mov     [rbp+6A0h+var_720], r12
0x180117261  mov     [rbp+6A0h+var_6C8], r12
0x180117265  mov     [rbp+6A0h+var_6A0], r12
0x180117269  mov     rdi, [rbp+6A0h+var_718]
0x18011726d  mov     rax, [rdi]
0x180117270  mov     rbx, [rax+48h]
0x180117274  lea     rcx, [rbp+6A0h+var_720]
0x180117278  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18011727d  lea     rdx, [rbp+6A0h+var_720]
0x180117281  mov     rcx, rdi
0x180117284  mov     rax, rbx
0x180117287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011728c  test    eax, eax
0x18011728e  js      loc_180117487
0x180117294  mov     dword ptr [rsp+7A0h+var_738], r12d
0x180117299  mov     rcx, [rbp+6A0h+var_720]
0x18011729d  mov     rax, [rcx]
0x1801172a0  lea     rdx, [rsp+7A0h+var_738]
0x1801172a5  mov     rax, [rax+38h]
0x1801172a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801172ae  test    eax, eax
0x1801172b0  js      loc_180117487
0x1801172b6  mov     [rbp+6A0h+var_6D0], r12
0x1801172ba  mov     rcx, r12
0x1801172bd  mov     [rsp+7A0h+bstrString], rcx
0x1801172c2  mov     eax, dword ptr [rsp+7A0h+var_738]
0x1801172c6  inc     eax
0x1801172c8  cmp     eax, 1
0x1801172cb  jle     loc_180117470
0x1801172d1  mov     [rsp+7A0h+var_750], r12
0x1801172d6  mov     rdi, [rbp+6A0h+var_720]
0x1801172da  mov     rax, [rdi]
0x1801172dd  mov     rbx, [rax+40h]
0x1801172e1  lea     rcx, [rsp+7A0h+var_750]
0x1801172e6  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1801172eb  lea     r8, [rsp+7A0h+var_750]
0x1801172f0  mov     edx, r14d
0x1801172f3  mov     rcx, rdi
0x1801172f6  mov     rax, rbx
0x1801172f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801172fe  mov     [rbp+6A0h+var_704], r12d
0x180117302  mov     rcx, [rsp+7A0h+var_750]
0x180117307  mov     rax, [rcx]
0x18011730a  lea     rdx, [rbp+6A0h+var_704]
0x18011730e  mov     rax, [rax+38h]
0x180117312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180117317  cmp     [rbp+6A0h+var_704], 1
0x18011731b  jnz     loc_18011744F
0x180117321  mov     rcx, [rsp+7A0h+var_750]
0x180117326  mov     rax, [rcx]
0x180117329  lea     rdx, [rbp+6A0h+var_6D0]
0x18011732d  mov     rax, [rax+70h]
  ... truncated ...
```
