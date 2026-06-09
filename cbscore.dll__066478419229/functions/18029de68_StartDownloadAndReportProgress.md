# StartDownloadAndReportProgress

- ea: `0x18029de68`
- end: `0x18029ef95`
- name: `StartDownloadAndReportProgress`
- size: `4397`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18029fda0`

## callees

- `0x180010cc0`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800eb4c0`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800f19ec`
- `0x18029b8c0`
- `0x18029bb4c`
- `0x18029c9e4`
- `0x18029de68`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18029e87c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18029e87c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029e2a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029e2a3`
- `OLEAUT32!__imp_SysAllocString` at `0x18029e606`
- `OLEAUT32!__imp_SysAllocString` at `0x18029e606`
- `OLEAUT32!__imp_VariantInit` at `0x18029dea9`
- `OLEAUT32!__imp_VariantInit` at `0x18029ded3`
- `OLEAUT32!__imp_VariantInit` at `0x18029dea9`
- `OLEAUT32!__imp_VariantInit` at `0x18029ded3`
- `OLEAUT32!__imp_VariantClear` at `0x18029dfbd`
- `OLEAUT32!__imp_VariantClear` at `0x18029e054`
- `OLEAUT32!__imp_VariantClear` at `0x18029e19b`
- `OLEAUT32!__imp_VariantClear` at `0x18029e268`
- `OLEAUT32!__imp_VariantClear` at `0x18029e52b`
- `OLEAUT32!__imp_VariantClear` at `0x18029e645`
- `OLEAUT32!__imp_VariantClear` at `0x18029e9c5`
- `OLEAUT32!__imp_VariantClear` at `0x18029ece8`
- `OLEAUT32!__imp_VariantClear` at `0x18029edb7`
- `OLEAUT32!__imp_VariantClear` at `0x18029edef`
- `OLEAUT32!__imp_VariantClear` at `0x18029eec3`
- `OLEAUT32!__imp_VariantClear` at `0x18029ef5a`
- `OLEAUT32!__imp_VariantClear` at `0x18029dfbd`
- `OLEAUT32!__imp_VariantClear` at `0x18029e054`
- `OLEAUT32!__imp_VariantClear` at `0x18029e19b`
- `OLEAUT32!__imp_VariantClear` at `0x18029e268`
- `OLEAUT32!__imp_VariantClear` at `0x18029e52b`
- `OLEAUT32!__imp_VariantClear` at `0x18029e645`
- `OLEAUT32!__imp_VariantClear` at `0x18029e9c5`
- `OLEAUT32!__imp_VariantClear` at `0x18029ece8`
- `OLEAUT32!__imp_VariantClear` at `0x18029edb7`
- `OLEAUT32!__imp_VariantClear` at `0x18029edef`
- `OLEAUT32!__imp_VariantClear` at `0x18029eec3`
- `OLEAUT32!__imp_VariantClear` at `0x18029ef5a`

## string_xrefs

- `0x18029df61`: `No update specified`
- `0x18029dfa4`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029e182`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029e511`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029e623`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029e9ab`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029edce`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029eea2`: `onecore\base\cbs\wulib\windowsupdatedownload.cpp`
- `0x18029e342`: `Failed to add update to collection`
- `0x18029e2ca`: `Failed to create collection`
- `0x18029e3b7`: `Failed to call put_updates on downloader`
- `0x18029e13d`: `Failed to initialize complete callback`
- `0x18029df03`: `No update downloader specified`
- `0x18029e464`: `WU: PSF is available but not preferred for the update.`
- `0x18029e45b`: `WU: PSF is available and preferred for the update.`
- `0x18029e46d`: `WU: PSF is not available for the update.`
- `0x18029ebb9`: `DWLD: Failed to get update result`

## pseudocode

```c
__int64 __fastcall StartDownloadAndReportProgress(__int64 *a1, OLECHAR *a2, __int64 *a3, struct IWULibCallback *a4)
{
  unsigned int v7; // ebx
  int v8; // edx
  __int64 v9; // rdx
  int v10; // edx
  bool v11; // zf
  CUUPDownloadProgressCallBack *v13; // rax
  CUUPDownloadProgressCallBack *v14; // r15
  _QWORD *v15; // rax
  _QWORD *v16; // rsi
  __int64 v17; // rax
  int v18; // eax
  unsigned int v19; // r13d
  int v20; // edx
  __int64 v21; // rdx
  char *v22; // rcx
  char *v23; // rcx
  HRESULT v24; // eax
  int v25; // edx
  int v26; // eax
  int v27; // edx
  int v28; // eax
  int v29; // edx
  unsigned int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rbx
  const char *v33; // rdx
  __int64 InitPointer; // rax
  int v35; // eax
  int v36; // edx
  __int64 v37; // rdx
  char *v38; // rcx
  char *v39; // rcx
  char *v40; // rcx
  bool v41; // zf
  __int64 v42; // rax
  int v43; // eax
  int v44; // edx
  __int64 v45; // r10
  __int64 v46; // rax
  char *v47; // r8
  int v48; // eax
  int v49; // edx
  unsigned int v50; // eax
  DWORD v51; // eax
  int v52; // eax
  __int64 v53; // r8
  int v54; // edx
  __int64 v55; // rdx
  int v56; // edx
  int v57; // edx
  unsigned int v58; // eax
  __int64 (__fastcall *v59)(__int64 *, __int64, __int64); // rbx
  __int64 v60; // rax
  int v61; // eax
  int v62; // edx
  int v63; // eax
  int v64; // edx
  int v65; // eax
  int v66; // edx
  int v67; // edx
  char *v68; // rcx
  char *v69; // rcx
  char *v70; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-A1h]
  int v72[2]; // [rsp+30h] [rbp-91h] BYREF
  int *v73; // [rsp+38h] [rbp-89h] BYREF
  VARIANTARG v74; // [rsp+40h] [rbp-81h] BYREF
  int v75; // [rsp+60h] [rbp-61h] BYREF
  __int64 v76; // [rsp+68h] [rbp-59h] BYREF
  LPVOID v77; // [rsp+70h] [rbp-51h] BYREF
  __int64 v78; // [rsp+78h] [rbp-49h] BYREF
  __int64 *v79; // [rsp+80h] [rbp-41h] BYREF
  __int64 v80; // [rsp+88h] [rbp-39h] BYREF
  OLECHAR *psz; // [rsp+90h] [rbp-31h] BYREF
  VARIANTARG v82; // [rsp+98h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-11h] BYREF
  __int16 v84[2]; // [rsp+C8h] [rbp+7h] BYREF
  unsigned int v85; // [rsp+CCh] [rbp+Bh] BYREF
  int v86; // [rsp+D0h] [rbp+Fh] BYREF
  int v87; // [rsp+D4h] [rbp+13h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+57h]

  *(_QWORD *)v72 = a4;
  psz = a2;
  v84[0] = 0;
  VariantInit(&pvarg);
  v85 = 0;
  v86 = 0;
  v76 = 0;
  v80 = 0;
  v78 = 0;
  v77 = 0;
  v79 = 0;
  VariantInit(&v82);
  v87 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    v75 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No update downloader specified");
      psz = (OLECHAR *)&v75;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)&psz);
    }
    v9 = 801;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x80070057LL,
      (int)ppv);
    if ( v82.vt )
    {
      VariantClear(&v82);
      v82.vt = 0;
    }
    if ( v79 )
    {
      (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
      v79 = 0;
    }
    if ( v77 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
      v77 = 0;
    }
    if ( v78 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      v78 = 0;
    }
    if ( v80 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      v80 = 0;
    }
    if ( v76 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
      v76 = 0;
    }
    v11 = pvarg.vt == 0;
    goto LABEL_22;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
    v75 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No update specified");
      psz = (OLECHAR *)&v75;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v10,
        3,
        (unsigned int)": {}",
        (__int64)&psz);
    }
    v9 = 802;
    goto LABEL_9;
  }
  v13 = (CUUPDownloadProgressCallBack *)operator new(0x40u);
  if ( !v13 || (v14 = CUUPDownloadProgressCallBack::CUUPDownloadProgressCallBack(v13, a4)) == 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x325,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      (int)ppv);
    if ( v82.vt )
    {
      VariantClear(&v82);
      v82.vt = 0;
    }
    goto LABEL_177;
  }
  v15 = operator new(0x30u);
  v16 = v15;
  if ( !v15 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x328,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      (int)ppv);
    if ( v82.vt )
    {
      VariantClear(&v82);
      v82.vt = 0;
    }
    v70 = (char *)v14 + *(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v70 + 16LL))(v70);
LABEL_177:
    v41 = pvarg.vt == 0;
LABEL_178:
    if ( !v41 )
      VariantClear(&pvarg);
    return 2147942414LL;
  }
  v15[2] = 0;
  v15[3] = 0;
  v15[4] = 0;
  v15[1] = &CUUPDownloadCompleteCallBack::`vbtable';
  *v15 = &CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'};
  v15[5] = &CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `IDownloadCompletedCallback'};
  *((_DWORD *)v15 + 9) = 8;
  *v15 = &CUUPDownloadCompleteCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'};
  v17 = v15[1];
  *((_DWORD *)v16 + 4) = 1;
  *(_QWORD *)((char *)v16 + *(int *)(v17 + 4) + 8) = &CUUPDownloadCompleteCallBack::`vftable'{for `IDownloadCompletedCallback'};
  *(_DWORD *)((char *)v16 + *(int *)(v16[1] + 4LL) + 4) = 0;
  v16[3] = 0;
  v18 = CUUPDownloadCompleteCallBack::Initialize((CUUPDownloadCompleteCallBack *)v16);
  v19 = v18;
  if ( v18 < 0 )
  {
    v75 = v18;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to initialize complete callback");
      psz = (OLECHAR *)&v75;
      LOBYTE(v20) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v20,
        3,
        (unsigned int)": {}",
        (__int64)&psz);
    }
    v21 = 810;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)v19,
      (int)ppv);
    if ( v82.vt )
    {
      VariantClear(&v82);
      v82.vt = 0;
    }
    if ( v79 )
    {
      (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
      v79 = 0;
    }
    if ( v77 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
      v77 = 0;
    }
    if ( v78 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      v78 = 0;
    }
    if ( v80 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      v80 = 0;
    }
    if ( v76 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
      v76 = 0;
    }
    v22 = (char *)v16 + *(int *)(v16[1] + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
    v23 = (char *)v14 + *(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 16LL))(v23);
    if ( pvarg.vt )
      VariantClear(&pvarg);
    return v19;
  }
  if ( v77 )
    goto LABEL_181;
  v24 = CoCreateInstance(
          &GUID_13639463_00db_4646_803d_528026140d88,
          0,
          1u,
          &GUID_07f7438c_7709_4ca5_b518_91279288134e,
          &v77);
  v19 = v24;
  if ( v24 < 0 )
  {
    v75 = v24;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create collection");
      psz = (OLECHAR *)&v75;
      LOBYTE(v25) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v25,
        3,
        (unsigned int)": {}",
        (__int64)&psz);
    }
    v21 = 813;
    goto LABEL_32;
  }
  v26 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, int *))(*(_QWORD *)v77 + 96LL))(v77, a3, &v87);
  v19 = v26;
  if ( v26 < 0 )
  {
    v75 = v26;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add update to collection");
      psz = (OLECHAR *)&v75;
      LOBYTE(v27) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v27,
        3,
        (unsigned int)": {}",
        (__int64)&psz);
    }
    v21 = 815;
    goto LABEL_32;
  }
  v28 = (*(__int64 (__fastcall **)(__int64 *, LPVOID))(*a1 + 112))(a1, v77);
  v19 = v28;
  if ( v28 < 0 )
  {
    v75 = v28;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to call put_updates on downloader");
      psz = (OLECHAR *)&v75;
      LOBYTE(v29) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v29,
        3,
        (unsigned int)": {}",
        (__int64)&psz);
    }
    v21 = 817;
    goto LABEL_32;
  }
  v30 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*a3 + 104))(a3, v84);
  if ( v30 )
  {
    LogAdapter::TraceAtLevelIfFailed<long,>(3, v30, "WU:Failed to check whether psf is available.");
  }
  else
  {
    if ( v84[0] == -1 )
    {
      v31 = *a3;
      LOWORD(v75) = 0;
      v32 = (*(unsigned int (__fastcall **)(__int64 *, int *))(v31 + 112))(a3, &v75);
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v32, "WU: Failed to check whether PSF is preferred.");
      if ( (_DWORD)v32 )
        goto LABEL_69;
      if ( (_WORD)v75 == 0xFFFF )
        v33 = "WU: PSF is available and preferred for the update.";
      else
        v33 = "WU: PSF is available but not preferred for the update.";
    }
    else
    {
      v33 = "WU: PSF is not available for the update.";
    }
    LogAdapter::TraceAtLevel<>(1, v33);
  }
LABEL_69:
  InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v79);
  v35 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64))*a1)(
          a1,
          &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
          InitPointer);
  v7 = v35;
  if ( v35 < 0 )
  {
    v75 = v35;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to set client ID");
      psz = (OLECHAR *)&v75;
      LOBYTE(v36) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v36,
        3,
        (unsigned int)": {}",
        (__int64)&psz);
    }
    v37 = 856;
    goto LABEL_73;
  }
  v82.vt = 8;
  v82.llVal = (LONGLONG)SysAllocString(psz);
  if ( !v82.llVal )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35C,
      (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
      (const char *)0x8007000ELL,
      (int)ppv);
    if ( v82.vt )
    {
      VariantClear(&v82);
      v82.vt = 0;
    }
    if ( v79 )
    {
      (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
      v79 = 0;
    }
    if ( v77 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
      v77 = 0;
    }
    if ( v78 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
      v78 = 0;
    }
    if ( v80 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      v80 = 0;
    }
    if ( v76 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
      v76 = 0;
    }
    v39 = (char *)v16 + *(int *)(v16[1] + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v39 + 16LL))(v39);
    v40 = (char *)v14 + *(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v40 + 16LL))(v40);
    v41 = pvarg.vt == 0;
    goto LABEL_178;
  }
  v42 = *v79;
  v74 = v82;
  v43 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG *))(v42 + 32))(v79, 196621, &v74);
  v7 = v43;
  if ( v43 < 0 )
  {
    v75 = v43;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to set scan current product version only");
      psz = (OLECHAR *)&v75;
      LOBYTE(v44) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v44,
        3,
        (unsigned int)": {}",
        (__int64)&psz);
    }
    v37 = 862;
    goto LABEL_73;
  }
  if ( v76 )
    goto LABEL_181;
  v45 = *a1;
  v46 = *((_QWORD *)v14 + 1);
  v47 = (char *)v16 + *(int *)(v16[1] + 4LL) + 8;
  v74 = pvarg;
  ppv = (LPVOID *)&v76;
  v48 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *, VARIANTARG *))(v45 + 120))(
          a1,
          (__int64)v14 + *(int *)(v46 + 4) + 8,
          v47,
          &v74);
  v7 = v48;
  if ( v48 < 0 )
  {
    v75 = v48;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "DWLD: Failed calling begin download");
      psz = (OLECHAR *)&v75;
      LOBYTE(v49) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v49,
        3,
        (unsigned int)": {}",
        (__int64)&psz);
    }
    v37 = 867;
    goto LABEL_73;
  }
LABEL_109:
  v50 = v85;
  while ( (*((_BYTE *)v14 + 24) || v50 <= 0xDBBA0) && (*((int *)v14 + 8) >= 4 || v50 <= 0x2932E0) )
  {
    v51 = WaitForSingleObject((HANDLE)v16[3], 0x7D0u);
    if ( !v51 )
    {
      v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v76 + 80LL))(v76);
      LogAdapter::TraceAtLevelIfFailed<long,>(3, v58, "DWLD: Failed to call download job cleanup");
      v59 = *(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*a1 + 136);
      v60 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v80);
      v61 = v59(a1, v76, v60);
      v7 = v61;
      if ( v61 < 0 )
      {
        v75 = v61;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "DWLD: Failed to call end download");
          *(_QWORD *)v72 = &v75;
          LOBYTE(v62) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v62,
            3,
            (unsigned int)": {}",
            (__int64)v72);
        }
        v37 = 935;
        goto LABEL_73;
      }
      if ( !v78 )
      {
        v63 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v80 + 72LL))(v80, 0, &v78);
        v7 = v63;
        if ( v63 >= 0 )
        {
          v65 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v78 + 56LL))(v78, &v86);
          v7 = v65;
          if ( v65 >= 0 )
          {
            v7 = v86;
            if ( v86 < 0 )
            {
              LODWORD(psz) = v86;
              if ( LogAdapter::g_Logger )
              {
                v73 = &v86;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  0,
                  3,
                  (unsigned int)"DWLD: Download failed with {}",
                  (__int64)&v73);
                *(_QWORD *)v72 = &psz;
                LOBYTE(v67) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v67,
                  3,
                  (unsigned int)": {}",
                  (__int64)v72);
              }
              v55 = 946;
              goto LABEL_124;
            }
            if ( v82.vt )
            {
              VariantClear(&v82);
              v82.vt = 0;
            }
            if ( v79 )
            {
              (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
              v79 = 0;
            }
            if ( v77 )
            {
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
              v77 = 0;
            }
            if ( v78 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
              v78 = 0;
            }
            if ( v80 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
              v80 = 0;
            }
            if ( v76 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
              v76 = 0;
            }
            v68 = (char *)v16 + *(int *)(v16[1] + 4LL) + 8;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v68 + 16LL))(v68);
            v69 = (char *)v14 + *(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v69 + 16LL))(v69);
            if ( pvarg.vt )
              VariantClear(&pvarg);
            return 0;
          }
          v75 = v65;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "DWLD: Failed to get download hresult");
            *(_QWORD *)v72 = &v75;
            LOBYTE(v66) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v66,
              3,
              (unsigned int)": {}",
              (__int64)v72);
          }
          v37 = 944;
        }
        else
        {
          v75 = v63;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "DWLD: Failed to get update result");
            *(_QWORD *)v72 = &v75;
            LOBYTE(v64) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v64,
              3,
              (unsigned int)": {}",
              (__int64)v72);
          }
          v37 = 942;
        }
LABEL_73:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
          (const char *)v7,
          (int)ppv);
        if ( v82.vt )
        {
          VariantClear(&v82);
          v82.vt = 0;
        }
        if ( v79 )
        {
          (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
          v79 = 0;
        }
        if ( v77 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
          v77 = 0;
        }
        if ( v78 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
          v78 = 0;
        }
        if ( v80 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
          v80 = 0;
        }
        if ( v76 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
          v76 = 0;
        }
        goto LABEL_85;
      }
LABEL_181:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18029EF94LL);
    }
    if ( v51 != 258 )
    {
      v7 = -2147467259;
      v75 = -2147467259;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to query status of event, assuming failure.");
        *(_QWORD *)v72 = &v75;
        LOBYTE(v57) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v57,
          3,
          (unsigned int)": {}",
          (__int64)v72);
      }
      v55 = 911;
      goto LABEL_124;
    }
    v50 = v85 + 2000;
    v85 += 2000;
    if ( *(_QWORD *)v72 )
    {
      v52 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)v72 + 40LL))(
              *(_QWORD *)v72,
              *((unsigned int *)v14 + 7),
              100);
      if ( (unsigned int)(v52 + 2146498528) <= 1 )
      {
        LOBYTE(v53) = v52 == -2146498527;
        CancelDownload(v76, a1, v53);
        v7 = -2147467260;
        v75 = -2147467260;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "DWLD: Caller cancelled the download operation");
          *(_QWORD *)v72 = &v75;
          LOBYTE(v54) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v54,
            3,
            (unsigned int)": {}",
            (__int64)v72);
        }
        v55 = 905;
        goto LABEL_124;
      }
      goto LABEL_109;
    }
  }
  CancelDownload(v76, a1, 0);
  v7 = -2145124319;
  v75 = -2145124319;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<unsigned long>(
      (_DWORD)LogAdapter::g_Logger,
      0,
      3,
      (unsigned int)"DWLD: Timed out waiting on WU download for {} milliseconds.",
      (__int64)&v85);
    *(_QWORD *)v72 = &v75;
    LOBYTE(v56) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v56,
      3,
      (unsigned int)": {}",
      (__int64)v72);
  }
  v55 = 882;
LABEL_124:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v55,
    (unsigned int)"onecore\\base\\cbs\\wulib\\windowsupdatedownload.cpp",
    (const char *)v7,
    (int)ppv);
  if ( v82.vt )
  {
    VariantClear(&v82);
    v82.vt = 0;
  }
  if ( v79 )
  {
    (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
    v79 = 0;
  }
  if ( v77 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v77 + 16LL))(v77);
    v77 = 0;
  }
  if ( v78 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 16LL))(v78);
    v78 = 0;
  }
  if ( v80 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    v80 = 0;
  }
  if ( v76 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    v76 = 0;
  }
LABEL_85:
  v38 = (char *)v16 + *(int *)(v16[1] + 4LL) + 8;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v38 + 16LL))(v38);
  (*(void (**)(void))(*(_QWORD *)((char *)v14 + *(int *)(*((_QWORD *)v14 + 1) + 4LL) + 8) + 16LL))();
  v11 = pvarg.vt == 0;
LABEL_22:
  if ( !v11 )
    VariantClear(&pvarg);
  return v7;
}

```

## disassembly

```asm
0x18029de68  push    rbp
0x18029de6a  push    rbx
0x18029de6b  push    rsi
0x18029de6c  push    rdi
0x18029de6d  push    r12
0x18029de6f  push    r13
0x18029de71  push    r15
0x18029de73  lea     rbp, [rsp-1Fh]
0x18029de78  sub     rsp, 0E0h
0x18029de7f  mov     rax, cs:__security_cookie
0x18029de86  xor     rax, rsp
0x18029de89  mov     [rbp+4Fh+var_38], rax
0x18029de8d  mov     r12, rcx
0x18029de90  mov     qword ptr [rsp+110h+var_E0], r9
0x18029de95  xor     esi, esi
0x18029de97  mov     [rbp+4Fh+psz], rdx
0x18029de9b  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18029de9f  mov     [rbp+4Fh+var_48], si
0x18029dea3  mov     rdi, r9
0x18029dea6  mov     rbx, r8
0x18029dea9  call    cs:__imp_VariantInit
0x18029deb0  nop     dword ptr [rax+rax+00h]
0x18029deb5  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x18029deb9  mov     [rbp+4Fh+var_44], esi
0x18029debc  mov     [rbp+4Fh+var_40], esi
0x18029debf  mov     [rbp+4Fh+var_A8], rsi
0x18029dec3  mov     [rbp+4Fh+var_88], rsi
0x18029dec7  mov     [rbp+4Fh+var_98], rsi
0x18029decb  mov     [rbp+4Fh+var_A0], rsi
0x18029decf  mov     [rbp+4Fh+var_90], rsi
0x18029ded3  call    cs:__imp_VariantInit
0x18029deda  nop     dword ptr [rax+rax+00h]
0x18029dedf  mov     [rbp+4Fh+var_3C], esi
0x18029dee2  test    r12, r12
0x18029dee5  jnz     short loc_18029DF3F
0x18029dee7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029deee  mov     ebx, 80070057h
0x18029def3  mov     [rbp+4Fh+var_B0], ebx
0x18029def6  test    rcx, rcx
0x18029def9  jz      short loc_18029DF38
0x18029defb  lea     edi, [rsi+3]
0x18029defe  xor     edx, edx
0x18029df00  mov     r8d, edi
0x18029df03  lea     r9, aNoUpdateDownlo; "No update downloader specified"
0x18029df0a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029df0f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029df16  lea     rax, [rbp+4Fh+var_B0]
0x18029df1a  mov     [rbp+4Fh+psz], rax
0x18029df1e  lea     r9, asc_1802EE7AC; ": {}"
0x18029df25  lea     rax, [rbp+4Fh+psz]
0x18029df29  mov     r8d, edi
0x18029df2c  mov     dl, 1
0x18029df2e  mov     [rsp+110h+ppv], rax
0x18029df33  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029df38  mov     edx, 321h
0x18029df3d  jmp     short loc_18029DFA0
0x18029df3f  test    rbx, rbx
0x18029df42  jnz     loc_18029E067
0x18029df48  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029df4f  mov     ebx, 80070057h
0x18029df54  mov     [rbp+4Fh+var_B0], ebx
0x18029df57  test    rcx, rcx
0x18029df5a  jz      short loc_18029DF9B
0x18029df5c  mov     edi, 3
0x18029df61  lea     r9, aNoUpdateSpecif; "No update specified"
0x18029df68  mov     r8d, edi
0x18029df6b  xor     edx, edx
0x18029df6d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029df72  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029df79  lea     rax, [rbp+4Fh+var_B0]
0x18029df7d  mov     [rbp+4Fh+psz], rax
0x18029df81  lea     r9, asc_1802EE7AC; ": {}"
0x18029df88  lea     rax, [rbp+4Fh+psz]
0x18029df8c  mov     r8d, edi
0x18029df8f  mov     dl, 1
0x18029df91  mov     [rsp+110h+ppv], rax; int
0x18029df96  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029df9b  mov     edx, 322h; void *
0x18029dfa0  mov     rcx, [rbp+57h]; this
0x18029dfa4  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029dfab  mov     r9d, ebx; char *
0x18029dfae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029dfb3  cmp     word ptr [rbp+4Fh+var_78], si
0x18029dfb7  jz      short loc_18029DFCD
0x18029dfb9  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x18029dfbd  call    cs:__imp_VariantClear
0x18029dfc4  nop     dword ptr [rax+rax+00h]
0x18029dfc9  mov     word ptr [rbp+4Fh+var_78], si
0x18029dfcd  mov     rcx, [rbp+4Fh+var_90]
0x18029dfd1  test    rcx, rcx
0x18029dfd4  jz      short loc_18029DFE6
0x18029dfd6  mov     rax, [rcx]
0x18029dfd9  mov     rax, [rax+10h]
0x18029dfdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029dfe2  mov     [rbp+4Fh+var_90], rsi
0x18029dfe6  mov     rcx, [rbp+4Fh+var_A0]
0x18029dfea  test    rcx, rcx
0x18029dfed  jz      short loc_18029DFFF
0x18029dfef  mov     rax, [rcx]
0x18029dff2  mov     rax, [rax+10h]
0x18029dff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029dffb  mov     [rbp+4Fh+var_A0], rsi
0x18029dfff  mov     rcx, [rbp+4Fh+var_98]
0x18029e003  test    rcx, rcx
0x18029e006  jz      short loc_18029E018
0x18029e008  mov     rax, [rcx]
0x18029e00b  mov     rax, [rax+10h]
0x18029e00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e014  mov     [rbp+4Fh+var_98], rsi
0x18029e018  mov     rcx, [rbp+4Fh+var_88]
0x18029e01c  test    rcx, rcx
0x18029e01f  jz      short loc_18029E031
0x18029e021  mov     rax, [rcx]
0x18029e024  mov     rax, [rax+10h]
0x18029e028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e02d  mov     [rbp+4Fh+var_88], rsi
0x18029e031  mov     rcx, [rbp+4Fh+var_A8]
0x18029e035  test    rcx, rcx
0x18029e038  jz      short loc_18029E04A
0x18029e03a  mov     rax, [rcx]
0x18029e03d  mov     rax, [rax+10h]
0x18029e041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e046  mov     [rbp+4Fh+var_A8], rsi
0x18029e04a  cmp     word ptr [rbp+4Fh+pvarg], si
0x18029e04e  jz      short loc_18029E060
0x18029e050  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18029e054  call    cs:__imp_VariantClear
0x18029e05b  nop     dword ptr [rax+rax+00h]
0x18029e060  mov     eax, ebx
0x18029e062  jmp     loc_18029EF6B
0x18029e067  mov     ecx, 40h ; '@'; Size
0x18029e06c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18029e071  test    rax, rax
0x18029e074  jz      loc_18029EE9C
0x18029e07a  mov     rdx, rdi; struct IWULibCallback *
0x18029e07d  mov     rcx, rax; this
0x18029e080  call    ??0CUUPDownloadProgressCallBack@@QEAA@PEAVIWULibCallback@@@Z; CUUPDownloadProgressCallBack::CUUPDownloadProgressCallBack(IWULibCallback *)
0x18029e085  xor     edi, edi
0x18029e087  mov     r15, rax
0x18029e08a  test    rax, rax
0x18029e08d  jz      loc_18029EE9E
0x18029e093  lea     ecx, [rdi+30h]; Size
0x18029e096  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18029e09b  mov     rsi, rax
0x18029e09e  test    rax, rax
0x18029e0a1  jz      loc_18029EDCA
0x18029e0a7  mov     [rax+10h], rdi
0x18029e0ab  mov     [rax+18h], rdi
0x18029e0af  mov     [rax+20h], rdi
0x18029e0b3  lea     rax, ??_8CUUPDownloadCompleteCallBack@@7B@; const CUUPDownloadCompleteCallBack::`vbtable'
0x18029e0ba  mov     [rsi+8], rax
0x18029e0be  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@6B0@@; const CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'}
0x18029e0c5  mov     [rsi], rax
0x18029e0c8  lea     rax, ??_7?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@6BIDownloadCompletedCallback@@@; const CCbsIUnknownImpl<IDownloadCompletedCallback,>::`vftable'{for `IDownloadCompletedCallback'}
0x18029e0cf  mov     [rsi+28h], rax
0x18029e0d3  lea     rax, ??_7CUUPDownloadCompleteCallBack@@6B?$CCbsIUnknownImpl@UIDownloadCompletedCallback@@$$V@@@; const CUUPDownloadCompleteCallBack::`vftable'{for `CCbsIUnknownImpl<IDownloadCompletedCallback,>'}
0x18029e0da  movsxd  rdx, cs:dword_1802EBBD0
0x18029e0e1  lea     ecx, [rdx-18h]
0x18029e0e4  mov     [rdx+rsi+4], ecx
0x18029e0e8  mov     [rsi], rax
0x18029e0eb  mov     rax, [rsi+8]
0x18029e0ef  mov     dword ptr [rsi+10h], 1
0x18029e0f6  movsxd  rcx, dword ptr [rax+4]
0x18029e0fa  lea     rax, ??_7CUUPDownloadCompleteCallBack@@6BIDownloadCompletedCallback@@@; const CUUPDownloadCompleteCallBack::`vftable'{for `IDownloadCompletedCallback'}
0x18029e101  mov     [rcx+rsi+8], rax
0x18029e106  mov     rax, [rsi+8]
0x18029e10a  movsxd  rcx, dword ptr [rax+4]
0x18029e10e  mov     [rcx+rsi+4], edi
0x18029e112  mov     rcx, rsi; this
0x18029e115  mov     [rsi+18h], rdi
0x18029e119  call    ?Initialize@CUUPDownloadCompleteCallBack@@QEAAJXZ; CUUPDownloadCompleteCallBack::Initialize(void)
0x18029e11e  mov     r13d, eax
0x18029e121  test    eax, eax
0x18029e123  jns     loc_18029E27C
0x18029e129  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029e130  mov     [rbp+4Fh+var_B0], eax
0x18029e133  test    rcx, rcx
0x18029e136  jz      short loc_18029E179
0x18029e138  mov     edi, 3
0x18029e13d  lea     r9, aFailedToInitia_19; "Failed to initialize complete callback"
0x18029e144  mov     r8d, edi
0x18029e147  xor     edx, edx
0x18029e149  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029e14e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029e155  lea     rax, [rbp+4Fh+var_B0]
0x18029e159  mov     [rbp+4Fh+psz], rax
0x18029e15d  lea     r9, asc_1802EE7AC; ": {}"
0x18029e164  lea     rax, [rbp+4Fh+psz]
0x18029e168  mov     r8d, edi
0x18029e16b  mov     dl, 1
0x18029e16d  mov     [rsp+110h+ppv], rax; int
0x18029e172  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029e177  xor     edi, edi
0x18029e179  mov     edx, 32Ah; void *
0x18029e17e  mov     rcx, [rbp+57h]; this
0x18029e182  lea     r8, aOnecoreBaseCbs_91; "onecore\\base\\cbs\\wulib\\windowsupdat"...
0x18029e189  mov     r9d, r13d; char *
0x18029e18c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029e191  cmp     word ptr [rbp+4Fh+var_78], di
0x18029e195  jz      short loc_18029E1AB
0x18029e197  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x18029e19b  call    cs:__imp_VariantClear
0x18029e1a2  nop     dword ptr [rax+rax+00h]
0x18029e1a7  mov     word ptr [rbp+4Fh+var_78], di
0x18029e1ab  mov     rcx, [rbp+4Fh+var_90]
0x18029e1af  test    rcx, rcx
0x18029e1b2  jz      short loc_18029E1C4
0x18029e1b4  mov     rax, [rcx]
0x18029e1b7  mov     rax, [rax+10h]
0x18029e1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e1c0  mov     [rbp+4Fh+var_90], rdi
0x18029e1c4  mov     rcx, [rbp+4Fh+var_A0]
0x18029e1c8  test    rcx, rcx
0x18029e1cb  jz      short loc_18029E1DD
0x18029e1cd  mov     rax, [rcx]
0x18029e1d0  mov     rax, [rax+10h]
0x18029e1d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e1d9  mov     [rbp+4Fh+var_A0], rdi
0x18029e1dd  mov     rcx, [rbp+4Fh+var_98]
0x18029e1e1  test    rcx, rcx
0x18029e1e4  jz      short loc_18029E1F6
0x18029e1e6  mov     rax, [rcx]
0x18029e1e9  mov     rax, [rax+10h]
0x18029e1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e1f2  mov     [rbp+4Fh+var_98], rdi
0x18029e1f6  mov     rcx, [rbp+4Fh+var_88]
0x18029e1fa  test    rcx, rcx
0x18029e1fd  jz      short loc_18029E20F
0x18029e1ff  mov     rax, [rcx]
0x18029e202  mov     rax, [rax+10h]
0x18029e206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e20b  mov     [rbp+4Fh+var_88], rdi
0x18029e20f  mov     rcx, [rbp+4Fh+var_A8]
0x18029e213  test    rcx, rcx
0x18029e216  jz      short loc_18029E228
0x18029e218  mov     rax, [rcx]
0x18029e21b  mov     rax, [rax+10h]
0x18029e21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e224  mov     [rbp+4Fh+var_A8], rdi
0x18029e228  mov     rax, [rsi+8]
0x18029e22c  movsxd  rcx, dword ptr [rax+4]
0x18029e230  add     rcx, 8
0x18029e234  add     rcx, rsi
0x18029e237  mov     rax, [rcx]
0x18029e23a  mov     rax, [rax+10h]
0x18029e23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e243  mov     rax, [r15+8]
0x18029e247  movsxd  rcx, dword ptr [rax+4]
0x18029e24b  add     rcx, 8
0x18029e24f  add     rcx, r15
0x18029e252  mov     rax, [rcx]
0x18029e255  mov     rax, [rax+10h]
0x18029e259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029e25e  cmp     word ptr [rbp+4Fh+pvarg], di
0x18029e262  jz      short loc_18029E274
0x18029e264  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18029e268  call    cs:__imp_VariantClear
0x18029e26f  nop     dword ptr [rax+rax+00h]
0x18029e274  mov     eax, r13d
0x18029e277  jmp     loc_18029EF6B
0x18029e27c  cmp     [rbp+4Fh+var_A0], rdi
0x18029e280  jnz     loc_18029EF8A
0x18029e286  xor     edx, edx; pUnkOuter
0x18029e288  lea     rax, [rbp+4Fh+var_A0]
0x18029e28c  lea     r9, _GUID_07f7438c_7709_4ca5_b518_91279288134e; riid
0x18029e293  mov     [rsp+110h+ppv], rax; int
0x18029e298  lea     rcx, _GUID_13639463_00db_4646_803d_528026140d88; rclsid
0x18029e29f  lea     r8d, [rdx+1]; dwClsContext
0x18029e2a3  call    cs:__imp_CoCreateInstance
0x18029e2aa  nop     dword ptr [rax+rax+00h]
0x18029e2af  mov     r13d, eax
0x18029e2b2  test    eax, eax
0x18029e2b4  jns     short loc_18029E310
0x18029e2b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029e2bd  mov     [rbp+4Fh+var_B0], eax
0x18029e2c0  test    rcx, rcx
0x18029e2c3  jz      short loc_18029E306
0x18029e2c5  mov     edi, 3
0x18029e2ca  lea     r9, aFailedToCreate_37; "Failed to create collection"
0x18029e2d1  mov     r8d, edi
0x18029e2d4  xor     edx, edx
0x18029e2d6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18029e2db  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18029e2e2  lea     rax, [rbp+4Fh+var_B0]
0x18029e2e6  mov     [rbp+4Fh+psz], rax
0x18029e2ea  lea     r9, asc_1802EE7AC; ": {}"
0x18029e2f1  lea     rax, [rbp+4Fh+psz]
0x18029e2f5  mov     r8d, edi
0x18029e2f8  mov     dl, 1
0x18029e2fa  mov     [rsp+110h+ppv], rax
0x18029e2ff  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18029e304  xor     edi, edi
0x18029e306  mov     edx, 32Dh
0x18029e30b  jmp     loc_18029E17E
0x18029e310  mov     rcx, [rbp+4Fh+var_A0]
0x18029e314  lea     r8, [rbp+4Fh+var_3C]
0x18029e318  mov     rdx, rbx
0x18029e31b  mov     rax, [rcx]
0x18029e31e  mov     rax, [rax+60h]
0x18029e322  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
