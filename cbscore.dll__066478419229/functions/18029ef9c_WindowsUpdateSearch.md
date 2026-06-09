# WindowsUpdateSearch

- ea: `0x18029ef9c`
- end: `0x18029fd97`
- name: `WindowsUpdateSearch`
- size: `3579`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18029fda0`

## callees

- `0x180010cc0`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800fa3ec`
- `0x1801255f4`
- `0x18029b1b0`
- `0x18029bc90`
- `0x18029c6cc`
- `0x18029d570`
- `0x18029d6cc`
- `0x18029ef9c`
- `0x1802d5010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18029f35b`
- `OLEAUT32!__imp_SysAllocString` at `0x18029f35b`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f089`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f1ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f8b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f980`
- `OLEAUT32!__imp_SysFreeString` at `0x18029fc45`
- `OLEAUT32!__imp_SysFreeString` at `0x18029fd12`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f089`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f1ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f8b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18029f980`
- `OLEAUT32!__imp_SysFreeString` at `0x18029fc45`
- `OLEAUT32!__imp_SysFreeString` at `0x18029fd12`
- `OLEAUT32!__imp_VariantInit` at `0x18029f343`
- `OLEAUT32!__imp_VariantInit` at `0x18029f343`
- `OLEAUT32!__imp_VariantClear` at `0x18029f39c`
- `OLEAUT32!__imp_VariantClear` at `0x18029f45f`
- `OLEAUT32!__imp_VariantClear` at `0x18029f480`
- `OLEAUT32!__imp_VariantClear` at `0x18029f39c`
- `OLEAUT32!__imp_VariantClear` at `0x18029f45f`
- `OLEAUT32!__imp_VariantClear` at `0x18029f480`

## string_xrefs

- `0x18029f10a`: `No update result specified`
- `0x18029f058`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f1bd`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f374`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f43c`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f781`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f95f`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029fa4d`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029fc0f`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029fcc3`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029f17a`: `Failed to create searcher`
- `0x18029f01a`: `No update session specified`
- `0x18029f49b`: `Not able to show current windows update server configuration`
- `0x18029fbc8`: `DLWD: Expecting search returns 1 update, actual:{}`
- `0x18029fb48`: `Failed to get update count`

## pseudocode

```c
__int64 __fastcall WindowsUpdateSearch(char a1, __int64 a2, const OLECHAR *a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // ebx
  int v9; // edx
  __int64 v10; // rdx
  void (*v11)(void); // rax
  int v13; // edx
  int v14; // eax
  int v15; // edx
  __int64 v16; // rdx
  void (*v17)(void); // rax
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64); // rbx
  __int64 InitPointer; // rax
  int v20; // eax
  int v21; // edx
  int v22; // eax
  int v23; // edx
  __int64 v24; // rax
  int v25; // eax
  int v26; // edx
  unsigned int updated; // eax
  _QWORD *v28; // rax
  int UUPSearchCriteria; // eax
  int v30; // edx
  int v31; // eax
  int v32; // edx
  int v33; // eax
  int v34; // edx
  int v35; // edx
  int v36; // edx
  int v37; // r14d
  __int64 v38; // rbx
  int v39; // eax
  int v40; // edx
  int v41; // edx
  __int64 v42; // rdx
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, __int64); // rbx
  __int64 v45; // rax
  int v46; // edx
  int v47; // r8d
  int v48; // r9d
  OLECHAR *v49; // rcx
  int v50; // edx
  int v51; // edx
  __int64 v52; // rdx
  int v53; // edx
  const char *v54; // rdx
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, __int64); // rbx
  __int64 v57; // rax
  int v58; // eax
  int v59; // edx
  int v60; // eax
  int v61; // edx
  int v62; // edx
  int v63; // eax
  int v64; // [rsp+20h] [rbp-E0h]
  char v65[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v66[2]; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v67; // [rsp+50h] [rbp-B0h] BYREF
  int *v68; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v69; // [rsp+60h] [rbp-A0h] BYREF
  int v70; // [rsp+80h] [rbp-80h] BYREF
  __int64 v71; // [rsp+88h] [rbp-78h] BYREF
  __int64 (__fastcall ***v72)(_QWORD, GUID *, __int64); // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v74; // [rsp+A0h] [rbp-60h] BYREF
  BSTR v75; // [rsp+A8h] [rbp-58h] BYREF
  int v76; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v77; // [rsp+B8h] [rbp-48h] BYREF
  int v78; // [rsp+C0h] [rbp-40h] BYREF
  int v79; // [rsp+C4h] [rbp-3Ch] BYREF
  __int64 v80; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-30h] BYREF
  int v82; // [rsp+D8h] [rbp-28h] BYREF
  int v83; // [rsp+DCh] [rbp-24h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v77 = 0;
  v72 = 0;
  v74 = 0;
  bstrString = 0;
  v71 = 0;
  v83 = 0;
  v82 = 0;
  v65[0] = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
    v70 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No update session specified");
      v75 = (BSTR)&v70;
      LOBYTE(v9) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v9,
        3,
        (unsigned int)": {}",
        (__int64)&v75);
    }
    v10 = 552;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v8,
      v64);
LABEL_6:
    if ( v71 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      v71 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64 *))(*v74 + 16))(v74);
      v74 = 0;
    }
    if ( v72 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v72)[2])(v72);
      v72 = 0;
    }
    if ( !v77 )
      return v8;
    v11 = *(void (**)(void))(*(_QWORD *)v77 + 16LL);
LABEL_16:
    v11();
    return v8;
  }
  if ( !a5 )
  {
    v8 = -2147467261;
    v70 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No update result specified");
      v75 = (BSTR)&v70;
      LOBYTE(v13) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v13,
        3,
        (unsigned int)": {}",
        (__int64)&v75);
    }
    v10 = 553;
    goto LABEL_5;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)a2 + 96LL))(
          a2,
          &v72);
  v8 = v14;
  if ( v14 < 0 )
  {
    v70 = v14;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create searcher");
      v75 = (BSTR)&v70;
      LOBYTE(v15) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v15,
        3,
        (unsigned int)": {}",
        (__int64)&v75);
    }
    v16 = 555;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v8,
      v64);
    goto LABEL_27;
  }
  v18 = v72;
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v74);
  v20 = (**v18)(v18, &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b, InitPointer);
  v8 = v20;
  if ( v20 < 0 )
  {
    v70 = v20;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to set client ID");
      v75 = (BSTR)&v70;
      LOBYTE(v21) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v21,
        3,
        (unsigned int)": {}",
        (__int64)&v75);
    }
    v16 = 560;
    goto LABEL_26;
  }
  v22 = SetDefaultSearchProperties(v72);
  v8 = v22;
  if ( v22 < 0 )
  {
    v70 = v22;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "DWLD:Failed to set default search properties");
      v75 = (BSTR)&v70;
      LOBYTE(v23) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v23,
        3,
        (unsigned int)": {}",
        (__int64)&v75);
    }
    v16 = 562;
    goto LABEL_26;
  }
  if ( a3 )
  {
    VariantInit(&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(a3);
    if ( !pvarg.llVal )
    {
      v8 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x239,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)0x8007000ELL,
        v64);
      if ( pvarg.vt )
      {
        VariantClear(&pvarg);
        pvarg.vt = 0;
      }
      goto LABEL_6;
    }
    v24 = *v74;
    v69 = pvarg;
    v25 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v24 + 32))(v74, 1, &v69);
    v8 = v25;
    if ( v25 < 0 )
    {
      v70 = v25;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to set correlation vector");
        v75 = (BSTR)&v70;
        LOBYTE(v26) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v26,
          3,
          (unsigned int)": {}",
          (__int64)&v75);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23D,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)v8,
        v64);
      if ( pvarg.vt )
      {
        VariantClear(&pvarg);
        pvarg.vt = 0;
      }
      goto LABEL_27;
    }
    if ( pvarg.vt )
      VariantClear(&pvarg);
  }
  updated = ShowWindowsUpdateServerConfiguration(v65);
  LogAdapter::TraceAtLevelIfFailed<long,>(3, updated, "Not able to show current windows update server configuration");
  DumpWindowsInsiderSettings();
  v28 = (_QWORD *)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&bstrString);
  UUPSearchCriteria = CreateUUPSearchCriteria(a1, a4, v28);
  v8 = UUPSearchCriteria;
  if ( UUPSearchCriteria < 0 )
  {
    v70 = UUPSearchCriteria;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get search criteria.");
      v75 = (BSTR)&v70;
      LOBYTE(v30) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v30,
        3,
        (unsigned int)": {}",
        (__int64)&v75);
    }
    v16 = 592;
    goto LABEL_26;
  }
  if ( v71 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18029FD96LL);
  }
  v31 = (*v72)[19](v72, (GUID *)bstrString, (__int64)&v71);
  v8 = v31;
  if ( v31 < 0 )
  {
    v70 = v31;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "DLWD:WU search failed");
      v75 = (BSTR)&v70;
      LOBYTE(v32) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v32,
        3,
        (unsigned int)": {}",
        (__int64)&v75);
    }
    v16 = 594;
    goto LABEL_26;
  }
  v33 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v71 + 56LL))(v71, &v83);
  v8 = v33;
  if ( v33 < 0 )
  {
    v70 = v33;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get download hresult");
      v75 = (BSTR)&v70;
      LOBYTE(v34) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v34,
        3,
        (unsigned int)": {}",
        (__int64)&v75);
    }
    v16 = 596;
    goto LABEL_26;
  }
  if ( v83 == 4 )
  {
    v8 = -2146498289;
    v78 = -2146498289;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "DWLD: Search failed with");
      v75 = (BSTR)&v78;
      LOBYTE(v35) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v35,
        3,
        (unsigned int)": {}",
        (__int64)&v75);
    }
    v10 = 602;
    goto LABEL_5;
  }
  if ( v83 == 5 )
  {
    v8 = -2147467260;
    v78 = -2147467260;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "DWLD: WU cancelled the search operation");
      v75 = (BSTR)&v78;
      LOBYTE(v36) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v36,
        3,
        (unsigned int)": {}",
        (__int64)&v75);
    }
    v10 = 606;
    goto LABEL_5;
  }
  v37 = 0;
  if ( v83 == 3 )
  {
    LogAdapter::TraceAtLevel<>(1, "DWLD: WU search succeeded with errors");
    v78 = 0;
    v80 = 0;
    v38 = (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v71 + 80LL))(v71, &v80);
    LogAdapter::TraceAtLevelIfFailed<long,>(3, v38, "DWLD: Unable to get WU warnings list");
    if ( (int)v38 >= 0 )
    {
      v39 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v80 + 72LL))(v80, &v78);
      v8 = v39;
      if ( v39 < 0 )
      {
        v70 = v39;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "DWLD: Unable to get WU warnings count");
          v75 = (BSTR)&v70;
          LOBYTE(v41) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v41,
            3,
            (unsigned int)": {}",
            (__int64)&v75);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26C,
          (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
          (const char *)v8,
          v64);
        goto LABEL_84;
      }
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v40) = 1;
        LogAdapter::Logger::LogNumObjects<long>(
          (_DWORD)LogAdapter::g_Logger,
          v40,
          1,
          (unsigned int)"DWLD: WU search warnings: {}",
          (__int64)&v78);
      }
    }
    v79 = 0;
    if ( v78 > 0 )
    {
      v42 = 0;
      while ( 1 )
      {
        v81 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v80 + 56LL))(v80, v42, &v81);
        if ( (v8 & 0x80000000) != 0 )
          break;
        v70 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v81 + 64LL))(v81, &v70);
        if ( (v8 & 0x80000000) != 0 )
        {
          v76 = v8;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<long>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"DWLD: Unable to get WU warning hr {}",
              (__int64)&v79);
            *(_QWORD *)v66 = &v76;
            LOBYTE(v51) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v51,
              3,
              (unsigned int)": {}",
              (__int64)v66);
          }
          v52 = 630;
LABEL_114:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v52,
            (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
            (const char *)v8,
            v64);
          goto LABEL_115;
        }
        v43 = v81;
        v75 = 0;
        v44 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 56LL);
        v45 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v75);
        v8 = v44(v43, v45);
        if ( (v8 & 0x80000000) != 0 )
        {
          v76 = v8;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<long>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"DWLD: Unable to get WU warning message {}",
              (__int64)&v79);
            *(_QWORD *)v66 = &v76;
            LOBYTE(v50) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v50,
              3,
              (unsigned int)": {}",
              (__int64)v66);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x279,
            (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
            (const char *)v8,
            v64);
          if ( v75 )
          {
            SysFreeString(v75);
            v75 = 0;
          }
LABEL_115:
          if ( v81 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
            v81 = 0;
          }
LABEL_84:
          if ( v80 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
            v80 = 0;
          }
LABEL_27:
          if ( v71 )
          {
            v17 = *(void (**)(void))(*(_QWORD *)v71 + 16LL);
            goto LABEL_29;
          }
          goto LABEL_30;
        }
        v49 = v75;
        v68 = &v70;
        v67 = v75;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<long,Windows::WCP::Rtl::FormatHResultWrapper<long>,wchar_t *>(
            (_DWORD)LogAdapter::g_Logger,
            v46,
            v47,
            v48,
            (__int64)&v79,
            (__int64)&v68,
            (__int64)&v67);
          v49 = v75;
        }
        if ( v37 >= 0 )
          v37 = v70;
        if ( v49 )
        {
          SysFreeString(v49);
          v75 = 0;
        }
        if ( v81 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
        v42 = (unsigned int)(v79 + 1);
        v79 = v42;
        if ( (int)v42 >= v78 )
          goto LABEL_102;
      }
      v76 = v8;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<long>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"DWLD: Unable to get WU warning {}",
          (__int64)&v79);
        *(_QWORD *)v66 = &v76;
        LOBYTE(v53) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v53,
          3,
          (unsigned int)": {}",
          (__int64)v66);
      }
      v52 = 627;
      goto LABEL_114;
    }
LABEL_102:
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
  }
  else
  {
    if ( v83 == 2 )
    {
      v76 = 2;
      v54 = "DWLD: WU search succeeded with WU result code {}";
    }
    else
    {
      v76 = v83;
      v54 = "DWLD: WU search failed with WU result code {}";
    }
    LogAdapter::TraceAtLevel<int>(1, v54, &v76);
  }
  v55 = v71;
  v56 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 72LL);
  v57 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v77);
  v58 = v56(v55, v57);
  v8 = v58;
  if ( v58 < 0 )
  {
    v76 = v58;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get search collection.");
      *(_QWORD *)v66 = &v76;
      LOBYTE(v59) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v59,
        3,
        (unsigned int)": {}",
        (__int64)v66);
    }
    v16 = 648;
    goto LABEL_26;
  }
  v60 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v77 + 80LL))(v77, &v82);
  v8 = v60;
  if ( v60 < 0 )
  {
    v76 = v60;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get update count");
      *(_QWORD *)v66 = &v76;
      LOBYTE(v61) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v61,
        3,
        (unsigned int)": {}",
        (__int64)v66);
    }
    v16 = 653;
    goto LABEL_26;
  }
  if ( v82 == 1 )
  {
    v63 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v77 + 56LL))(v77, 0, a5);
    v8 = v63;
    if ( v63 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x297,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v63,
        v64);
      if ( v71 )
      {
        v17 = *(void (**)(void))(*(_QWORD *)v71 + 16LL);
LABEL_29:
        v17();
        v71 = 0;
      }
LABEL_30:
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      if ( v74 )
      {
        (*(void (__fastcall **)(__int64 *))(*v74 + 16))(v74);
        v74 = 0;
      }
      if ( v72 )
      {
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v72)[2])(v72);
        v72 = 0;
      }
      if ( !v77 )
        return v8;
      v11 = *(void (**)(void))(*(_QWORD *)v77 + 16LL);
      goto LABEL_16;
    }
    if ( v71 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      v71 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64 *))(*v74 + 16))(v74);
      v74 = 0;
    }
    if ( v72 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v72)[2])(v72);
      v72 = 0;
    }
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    return 0;
  }
  else
  {
    if ( v37 >= 0 )
      v37 = v65[0] != 0 ? -2146498220 : -2146498224;
    v70 = v37;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<long>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"DLWD: Expecting search returns 1 update, actual:{}",
        (__int64)&v82);
      *(_QWORD *)v66 = &v70;
      LOBYTE(v62) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v62,
        3,
        (unsigned int)": {}",
        (__int64)v66);
    }
    if ( v37 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x294,
        (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
        (const char *)(unsigned int)v37,
        v64);
    if ( v71 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
      v71 = 0;
    }
    if ( bstrString )
    {
      SysFreeString(bstrString);
      bstrString = 0;
    }
    if ( v74 )
    {
      (*(void (__fastcall **)(__int64 *))(*v74 + 16))(v74);
      v74 = 0;
    }
    if ( v72 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v72)[2])(v72);
      v72 = 0;
    }
    if ( v77 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
    return (unsigned int)v37;
  }
}

```

## disassembly

```asm
0x18029ef9c  push    rbp
0x18029ef9e  push    rbx
0x18029ef9f  push    rsi
0x18029efa0  push    rdi
0x18029efa1  push    r12
0x18029efa3  push    r13
0x18029efa5  push    r14
0x18029efa7  push    r15
0x18029efa9  lea     rbp, [rsp-8]
0x18029efae  sub     rsp, 108h
0x18029efb5  mov     rax, cs:__security_cookie
0x18029efbc  xor     rax, rsp
0x18029efbf  mov     [rbp+40h+var_48], rax
0x18029efc3  mov     r12, [rbp+40h+arg_20]
0x18029efc7  xor     r13d, r13d
0x18029efca  mov     [rbp+40h+var_88], r13
0x18029efce  mov     rdi, r8
0x18029efd1  mov     [rbp+40h+var_B0], r13
0x18029efd5  mov     r15, r9
0x18029efd8  mov     [rbp+40h+var_A0], r13
0x18029efdc  mov     r8, rdx
0x18029efdf  mov     [rbp+40h+bstrString], r13
0x18029efe3  mov     r14d, ecx
0x18029efe6  mov     [rbp+40h+var_B8], r13
0x18029efea  mov     [rbp+40h+var_64], r13d
0x18029efee  mov     [rbp+40h+var_68], r13d
0x18029eff2  mov     [rsp+140h+var_100], r13b
0x18029eff7  test    rdx, rdx
0x18029effa  jnz     loc_18029F0E7
0x18029f000  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f007  mov     ebx, 80070057h
0x18029f00c  mov     [rbp+40h+var_C0], ebx
0x18029f00f  test    rcx, rcx
0x18029f012  jz      short loc_18029F04F
0x18029f014  lea     esi, [rdx+3]
0x18029f017  mov     r8d, esi
0x18029f01a  lea     r9, aNoUpdateSessio; "No update session specified"
0x18029f021  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f026  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f02d  lea     rax, [rbp+40h+var_C0]
0x18029f031  mov     [rbp+40h+var_98], rax
0x18029f035  lea     r9, asc_1802EE7AC; ": {}"
0x18029f03c  lea     rax, [rbp+40h+var_98]
0x18029f040  mov     r8d, esi
0x18029f043  mov     dl, 1
0x18029f045  mov     qword ptr [rsp+140h+var_120], rax; int
0x18029f04a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f04f  mov     edx, 228h; void *
0x18029f054  mov     rcx, [rbp+48h]; this
0x18029f058  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029f05f  mov     r9d, ebx; char *
0x18029f062  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029f067  mov     rcx, [rbp+40h+var_B8]
0x18029f06b  test    rcx, rcx
0x18029f06e  jz      short loc_18029F080
0x18029f070  mov     rax, [rcx]
0x18029f073  mov     rax, [rax+10h]
0x18029f077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f07c  mov     [rbp+40h+var_B8], r13
0x18029f080  mov     rcx, [rbp+40h+bstrString]; bstrString
0x18029f084  test    rcx, rcx
0x18029f087  jz      short loc_18029F099
0x18029f089  call    cs:__imp_SysFreeString
0x18029f090  nop     dword ptr [rax+rax+00h]
0x18029f095  mov     [rbp+40h+bstrString], r13
0x18029f099  mov     rcx, [rbp+40h+var_A0]
0x18029f09d  test    rcx, rcx
0x18029f0a0  jz      short loc_18029F0B2
0x18029f0a2  mov     rax, [rcx]
0x18029f0a5  mov     rax, [rax+10h]
0x18029f0a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f0ae  mov     [rbp+40h+var_A0], r13
0x18029f0b2  mov     rcx, [rbp+40h+var_B0]
0x18029f0b6  test    rcx, rcx
0x18029f0b9  jz      short loc_18029F0CB
0x18029f0bb  mov     rax, [rcx]
0x18029f0be  mov     rax, [rax+10h]
0x18029f0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f0c7  mov     [rbp+40h+var_B0], r13
0x18029f0cb  mov     rcx, [rbp+40h+var_88]
0x18029f0cf  test    rcx, rcx
0x18029f0d2  jz      short loc_18029F0E0
0x18029f0d4  mov     rdx, [rcx]
0x18029f0d7  mov     rax, [rdx+10h]
0x18029f0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f0e0  mov     eax, ebx
0x18029f0e2  jmp     loc_18029FD6B
0x18029f0e7  test    r12, r12
0x18029f0ea  jnz     short loc_18029F149
0x18029f0ec  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f0f3  mov     ebx, 80004003h
0x18029f0f8  mov     [rbp+40h+var_C0], ebx
0x18029f0fb  test    rcx, rcx
0x18029f0fe  jz      short loc_18029F13F
0x18029f100  lea     esi, [r12+3]
0x18029f105  xor     edx, edx
0x18029f107  mov     r8d, esi
0x18029f10a  lea     r9, aNoUpdateResult; "No update result specified"
0x18029f111  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f116  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f11d  lea     rax, [rbp+40h+var_C0]
0x18029f121  mov     [rbp+40h+var_98], rax
0x18029f125  lea     r9, asc_1802EE7AC; ": {}"
0x18029f12c  lea     rax, [rbp+40h+var_98]
0x18029f130  mov     r8d, esi
0x18029f133  mov     dl, 1
0x18029f135  mov     qword ptr [rsp+140h+var_120], rax
0x18029f13a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f13f  mov     edx, 229h
0x18029f144  jmp     loc_18029F054
0x18029f149  mov     rax, [rdx]
0x18029f14c  mov     rcx, r8
0x18029f14f  lea     rdx, [rbp+40h+var_B0]
0x18029f153  mov     rax, [rax+60h]
0x18029f157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f15c  mov     ebx, eax
0x18029f15e  test    eax, eax
0x18029f160  jns     loc_18029F249
0x18029f166  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f16d  mov     [rbp+40h+var_C0], eax
0x18029f170  test    rcx, rcx
0x18029f173  jz      short loc_18029F1B4
0x18029f175  mov     esi, 3
0x18029f17a  lea     r9, aFailedToCreate_83; "Failed to create searcher"
0x18029f181  mov     r8d, esi
0x18029f184  xor     edx, edx
0x18029f186  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f18b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f192  lea     rax, [rbp+40h+var_C0]
0x18029f196  mov     [rbp+40h+var_98], rax
0x18029f19a  lea     r9, asc_1802EE7AC; ": {}"
0x18029f1a1  lea     rax, [rbp+40h+var_98]
0x18029f1a5  mov     r8d, esi
0x18029f1a8  mov     dl, 1
0x18029f1aa  mov     qword ptr [rsp+140h+var_120], rax; int
0x18029f1af  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f1b4  mov     edx, 22Bh; void *
0x18029f1b9  mov     rcx, [rbp+48h]; this
0x18029f1bd  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029f1c4  mov     r9d, ebx; char *
0x18029f1c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029f1cc  mov     rcx, [rbp+40h+var_B8]
0x18029f1d0  test    rcx, rcx
0x18029f1d3  jz      short loc_18029F1E5
0x18029f1d5  mov     rax, [rcx]
0x18029f1d8  mov     rax, [rax+10h]
0x18029f1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f1e1  mov     [rbp+40h+var_B8], r13
0x18029f1e5  mov     rcx, [rbp+40h+bstrString]; bstrString
0x18029f1e9  test    rcx, rcx
0x18029f1ec  jz      short loc_18029F1FE
0x18029f1ee  call    cs:__imp_SysFreeString
0x18029f1f5  nop     dword ptr [rax+rax+00h]
0x18029f1fa  mov     [rbp+40h+bstrString], r13
0x18029f1fe  mov     rcx, [rbp+40h+var_A0]
0x18029f202  test    rcx, rcx
0x18029f205  jz      short loc_18029F217
0x18029f207  mov     rax, [rcx]
0x18029f20a  mov     rax, [rax+10h]
0x18029f20e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f213  mov     [rbp+40h+var_A0], r13
0x18029f217  mov     rcx, [rbp+40h+var_B0]
0x18029f21b  test    rcx, rcx
0x18029f21e  jz      short loc_18029F230
0x18029f220  mov     rax, [rcx]
0x18029f223  mov     rax, [rax+10h]
0x18029f227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f22c  mov     [rbp+40h+var_B0], r13
0x18029f230  mov     rcx, [rbp+40h+var_88]
0x18029f234  test    rcx, rcx
0x18029f237  jz      loc_18029F0E0
0x18029f23d  mov     rax, [rcx]
0x18029f240  mov     rax, [rax+10h]
0x18029f244  jmp     loc_18029F0DB
0x18029f249  mov     rbx, [rbp+40h+var_B0]
0x18029f24d  lea     rcx, [rbp+40h+var_A0]
0x18029f251  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18029f256  mov     rcx, [rbx]
0x18029f259  lea     rdx, _GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b
0x18029f260  mov     r8, rax
0x18029f263  mov     r9, [rcx]
0x18029f266  mov     rcx, rbx
0x18029f269  mov     rax, r9
0x18029f26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f271  mov     ebx, eax
0x18029f273  test    eax, eax
0x18029f275  jns     short loc_18029F2CF
0x18029f277  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f27e  mov     [rbp+40h+var_C0], eax
0x18029f281  test    rcx, rcx
0x18029f284  jz      short loc_18029F2C5
0x18029f286  mov     esi, 3
0x18029f28b  lea     r9, aFailedToSetCli; "Failed to set client ID"
0x18029f292  mov     r8d, esi
0x18029f295  xor     edx, edx
0x18029f297  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f29c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f2a3  lea     rax, [rbp+40h+var_C0]
0x18029f2a7  mov     [rbp+40h+var_98], rax
0x18029f2ab  lea     r9, asc_1802EE7AC; ": {}"
0x18029f2b2  lea     rax, [rbp+40h+var_98]
0x18029f2b6  mov     r8d, esi
0x18029f2b9  mov     dl, 1
0x18029f2bb  mov     qword ptr [rsp+140h+var_120], rax
0x18029f2c0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f2c5  mov     edx, 230h
0x18029f2ca  jmp     loc_18029F1B9
0x18029f2cf  mov     rcx, [rbp+40h+var_B0]
0x18029f2d3  call    SetDefaultSearchProperties
0x18029f2d8  mov     ebx, eax
0x18029f2da  test    eax, eax
0x18029f2dc  jns     short loc_18029F336
0x18029f2de  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f2e5  mov     [rbp+40h+var_C0], eax
0x18029f2e8  test    rcx, rcx
0x18029f2eb  jz      short loc_18029F32C
0x18029f2ed  mov     esi, 3
0x18029f2f2  lea     r9, aDwldFailedToSe_1; "DWLD:Failed to set default search prope"...
0x18029f2f9  mov     r8d, esi
0x18029f2fc  xor     edx, edx
0x18029f2fe  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f303  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f30a  lea     rax, [rbp+40h+var_C0]
0x18029f30e  mov     [rbp+40h+var_98], rax
0x18029f312  lea     r9, asc_1802EE7AC; ": {}"
0x18029f319  lea     rax, [rbp+40h+var_98]
0x18029f31d  mov     r8d, esi
0x18029f320  mov     dl, 1
0x18029f322  mov     qword ptr [rsp+140h+var_120], rax
0x18029f327  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f32c  mov     edx, 232h
0x18029f331  jmp     loc_18029F1B9
0x18029f336  test    rdi, rdi
0x18029f339  jz      loc_18029F48C
0x18029f33f  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18029f343  call    cs:__imp_VariantInit
0x18029f34a  nop     dword ptr [rax+rax+00h]
0x18029f34f  mov     eax, 8
0x18029f354  mov     rcx, rdi; psz
0x18029f357  mov     word ptr [rbp+40h+pvarg], ax
0x18029f35b  call    cs:__imp_SysAllocString
0x18029f362  nop     dword ptr [rax+rax+00h]
0x18029f367  mov     qword ptr [rbp+40h+pvarg+8], rax
0x18029f36b  test    rax, rax
0x18029f36e  jnz     short loc_18029F3B2
0x18029f370  mov     rcx, [rbp+48h]; this
0x18029f374  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029f37b  mov     ebx, 8007000Eh
0x18029f380  mov     edx, 239h; void *
0x18029f385  mov     r9d, ebx; char *
0x18029f388  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029f38d  cmp     word ptr [rbp+40h+pvarg], r13w
0x18029f392  jz      loc_18029F067
0x18029f398  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18029f39c  call    cs:__imp_VariantClear
0x18029f3a3  nop     dword ptr [rax+rax+00h]
0x18029f3a8  mov     word ptr [rbp+40h+pvarg], r13w
0x18029f3ad  jmp     loc_18029F067
0x18029f3b2  mov     rcx, [rbp+40h+var_A0]
0x18029f3b6  lea     r8, [rsp+140h+var_E0]
0x18029f3bb  movups  xmm0, xmmword ptr [rbp+40h+pvarg]
0x18029f3bf  mov     edx, 1
0x18029f3c4  movsd   xmm1, qword ptr [rbp+40h+pvarg+10h]
0x18029f3c9  mov     rax, [rcx]
0x18029f3cc  movaps  [rsp+140h+var_E0], xmm0
0x18029f3d1  movsd   [rsp+140h+var_D0], xmm1
0x18029f3d7  mov     rax, [rax+20h]
0x18029f3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029f3e0  mov     ebx, eax
0x18029f3e2  test    eax, eax
0x18029f3e4  jns     loc_18029F475
0x18029f3ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f3f1  mov     [rbp+40h+var_C0], eax
0x18029f3f4  test    rcx, rcx
0x18029f3f7  jz      short loc_18029F438
0x18029f3f9  mov     esi, 3
0x18029f3fe  lea     r9, aFailedToSetCor; "Failed to set correlation vector"
0x18029f405  mov     r8d, esi
0x18029f408  xor     edx, edx
0x18029f40a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029f40f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029f416  lea     rax, [rbp+40h+var_C0]
0x18029f41a  mov     [rbp+40h+var_98], rax
0x18029f41e  lea     r9, asc_1802EE7AC; ": {}"
0x18029f425  lea     rax, [rbp+40h+var_98]
0x18029f429  mov     r8d, esi
0x18029f42c  mov     dl, 1
0x18029f42e  mov     qword ptr [rsp+140h+var_120], rax; int
0x18029f433  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029f438  mov     rcx, [rbp+48h]; this
0x18029f43c  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029f443  mov     r9d, ebx; char *
0x18029f446  mov     edx, 23Dh; void *
0x18029f44b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029f450  cmp     word ptr [rbp+40h+pvarg], r13w
0x18029f455  jz      loc_18029F1CC
0x18029f45b  lea     rcx, [rbp+40h+pvarg]; pvarg
0x18029f45f  call    cs:__imp_VariantClear
0x18029f466  nop     dword ptr [rax+rax+00h]
0x18029f46b  mov     word ptr [rbp+40h+pvarg], r13w
  ... truncated ...
```
