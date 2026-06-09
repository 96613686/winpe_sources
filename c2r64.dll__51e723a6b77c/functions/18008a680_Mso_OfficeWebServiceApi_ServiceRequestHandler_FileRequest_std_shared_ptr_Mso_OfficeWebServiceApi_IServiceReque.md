# Mso::OfficeWebServiceApi::ServiceRequestHandler::FileRequest(std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity> const &,Mso::TCntPtr<Mso::OfficeWebServiceApi::IUrlBuilder> const &,Mso::OfficeWebServiceApi::AServiceRequestCallback *,unsigned __int64,uint,std::optional<_GUID> const &)

- ea: `0x18008a680`
- end: `0x18008ad99`
- name: `?FileRequest@ServiceRequestHandler@OfficeWebServiceApi@Mso@@UEAA?AW4Flags@Status@23@AEBV?$shared_ptr@UIServiceRequestTelemetryActivity@OfficeWebServiceApi@Mso@@@std@@AEBV?$TCntPtr@UIUrlBuilder@OfficeWebServiceApi@Mso@@@3@PEAVAServiceRequestCallback@23@_KIAEBV?$optional@U_GUID@@@7@@Z`
- size: `1817`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000adf0`
- `0x18000c2dc`
- `0x180010414`
- `0x180010a84`
- `0x180012bf8`
- `0x18001c760`
- `0x180025854`
- `0x1800293a0`
- `0x180029dc0`
- `0x18002acd8`
- `0x18003aa9c`
- `0x18003e690`
- `0x180052e28`
- `0x180063814`
- `0x180074db0`
- `0x18007e710`
- `0x18007eba4`
- `0x180085af0`
- `0x180087560`
- `0x180087f44`
- `0x1800884f0`
- `0x180089498`
- `0x180089524`
- `0x180089548`
- `0x18008a1a4`
- `0x18008a680`
- `0x18008b0a4`
- `0x1800a41e4`
- `0x180146090`

## string_xrefs

- `0x18008abbb`: `[ServiceRequest] Cache Data Found and Callback for data requested`
- `0x18008a8e0`: `[ServiceRequest] Cache Record Found`
- `0x18008aabe`: `[ServiceRequest] Cache Update Required`
- `0x18008a7b6`: `[ServiceRequest] Callback is used | Callback SetIsCachingEnabled(true)`
- `0x18008a8bc`: `CacheKey`
- `0x18008aa9a`: `CacheKey`
- `0x18008ab97`: `CacheKey`
- `0x18008ac6b`: `CacheKey`
- `0x18008a711`: `[ServiceRequest] Failed due to invalid call | UrlBuilder is nullptr`
- `0x18008a77e`: `[ServiceRequest] Failed due to invalid call | UrlBuilder is invalid`
- `0x18008ac8f`: `[ServiceRequest] Cache Data Found | [FileRequest] Succeed`

## pseudocode

```c
__int64 __fastcall Mso::OfficeWebServiceApi::ServiceRequestHandler::FileRequest(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7)
{
  __int64 v10; // rbx
  unsigned int v11; // r15d
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  __int64 v14; // r9
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rax
  int v25; // r9d
  _QWORD *v26; // rdx
  __int64 v27; // r14
  Mso::Async *v28; // rcx
  struct Mso::Async::IDispatchQueue *v29; // rax
  __int64 v30; // rax
  int v31; // r9d
  char Data; // al
  __int64 v33; // rcx
  bool v34; // zf
  void (__fastcall *v35)(__int64, __int64); // rax
  __int64 v36; // rdx
  __int64 v37; // rax
  int v38; // edx
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rdx
  void (__fastcall *v42)(__int64, __int64, _QWORD); // r13
  __int128 v43; // kr00_16
  __int64 v44; // rax
  int v45; // r9d
  char v46; // [rsp+40h] [rbp-C0h]
  char v47; // [rsp+41h] [rbp-BFh]
  const char *v48; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v53; // [rsp+70h] [rbp-90h]
  __int128 v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+88h] [rbp-78h]
  __int64 v56; // [rsp+90h] [rbp-70h]
  _QWORD v57[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v58; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-48h]
  _BYTE v60[24]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v61; // [rsp+D8h] [rbp-28h]
  _BYTE v62[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v63[96]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v64[32]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v65[20]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v66[6]; // [rsp+240h] [rbp+140h] BYREF

  v56 = a1;
  v50 = a7;
  v10 = 0;
  if ( *(_BYTE *)(a7 + 16) )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 24LL))(*a2, a5);
  v11 = 1;
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 32LL))(*a2, 1);
  if ( !*a3 )
  {
    FileTime = (struct _FILETIME)"[ServiceRequest] Failed due to invalid call | UrlBuilder is nullptr";
    Mso::Diagnostics::SendDiagnosticTrace<>(507540565, 823, 15, 2, (__int64)&FileTime);
    v12 = 507540564;
LABEL_5:
    v13 = a2;
    v14 = 2;
    return Mso::OfficeWebServiceApi::SetAndReturn(v12, v13, a4, v14);
  }
  v16 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(a3);
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v16 + 104LL))(v16) )
  {
    FileTime = (struct _FILETIME)"[ServiceRequest] Failed due to invalid call | UrlBuilder is invalid";
    Mso::Diagnostics::SendDiagnosticTrace<>(507540563, 823, 15, 2, (__int64)&FileTime);
    v12 = 507540562;
    goto LABEL_5;
  }
  if ( a4 )
  {
    FileTime = (struct _FILETIME)"[ServiceRequest] Callback is used | Callback SetIsCachingEnabled(true)";
    Mso::Diagnostics::SendDiagnosticTrace<>(507540560, 823, 50, 2, (__int64)&FileTime);
    LOBYTE(v17) = 1;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 104LL))(a4, v17);
  }
  v47 = sub_18008B0A4(a5);
  v51 = 0;
  v18 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(a3);
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 128LL))(v18, 0) )
  {
    v27 = v50;
    goto LABEL_45;
  }
  Mso::OfficeWebServiceApi::ServiceCacheRecord::ServiceCacheRecord(
    (Mso::OfficeWebServiceApi::ServiceCacheRecord *)v64,
    0);
  v19 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(a3);
  v20 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 160LL))(v19);
  std::wstring::wstring(v62, v20);
  v21 = Mso::OfficeWebServiceApi::ServiceCacheRecord::Populate((Mso::OfficeWebServiceApi::ServiceCacheRecord *)v64);
  if ( !v21 )
  {
    FileTime = (struct _FILETIME)"CacheKey";
    v24 = Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::ClassifiedStructuredObject<std::wstring>(
            v57,
            &FileTime,
            v62,
            16);
    FileTime = (struct _FILETIME)"[ServiceRequest] Cache Record Found";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
      507540559,
      823,
      50,
      v25,
      (__int64)&FileTime,
      v24);
    Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(v57);
    v46 = 0;
    if ( a4 )
    {
      v26 = v65;
      if ( v65[3] > 7u )
        v26 = (_QWORD *)v65[0];
      (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)a4 + 120LL))(a4, v26);
    }
    (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*a2 + 120LL))(*a2, v66);
    if ( v47 )
      goto LABEL_32;
    v48 = (const char *)v66[0];
    v51 = v66[0];
    FileTime = 0;
    v52 = v66[1];
    Mso::RecordDateTime::SetCurrent(&FileTime);
    if ( !v51 || a6 )
    {
      v53 = 600000000LL * a6 + __PAIR64__(HIDWORD(v48), v51);
      v52 = v53;
    }
    if ( !Mso::RecordDateTime::IsLater((Mso::RecordDateTime *)&FileTime, (const struct Mso::RecordDateTime *)&v52) )
    {
LABEL_32:
      v27 = v50;
    }
    else
    {
      if ( (a5 & 0x200000) == 0 )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a2 + 104LL))(*a2, 2);
        v48 = "CacheKey";
        v30 = Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::ClassifiedStructuredObject<std::wstring>(
                v57,
                &v48,
                v62,
                16);
        v48 = "[ServiceRequest] Cache Update Required";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
          507540558,
          823,
          50,
          v31,
          (__int64)&v48,
          v30);
        Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(v57);
        goto LABEL_31;
      }
      v46 = 1;
      std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(
        v57,
        a2);
      Mso::TCntPtr<Mso::Http::IRequest>::TCntPtr<Mso::Http::IRequest>(&v58, a3);
      v59 = a5;
      *(_QWORD *)v60 = v51;
      v27 = v50;
      *(_OWORD *)&v60[8] = *(_OWORD *)v50;
      LODWORD(v61) = *(_DWORD *)(v50 + 16);
      v52 = sub_180089498(v57);
      v29 = Mso::Async::ConcurrentIdleQueue(v28);
      Mso::Async::PostIdle<Mso::Async::IDispatchQueue &>(v29, &v52);
      Mso::TCntPtr<Mso::Async::ICancellationListener>::Clear(&v52);
      sub_18008A1A4(v57);
    }
    v54 = 0;
    v55 = 0;
    Data = Mso::OfficeWebServiceApi::ServiceCacheRecord::GetData(v64, &v54);
    v33 = *a2;
    v34 = Data == 0;
    v35 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)*a2 + 104LL);
    if ( !v34 )
    {
      if ( v46 )
        v36 = 4;
      else
        v36 = 0;
      v35(v33, v36);
      if ( a4 )
      {
        v57[0] = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
        v57[1] = "DataSize";
        v58 = *((_QWORD *)&v54 + 1) - v54;
        LOWORD(v59) = 4;
        memset(v60, 0, sizeof(v60));
        v61 = 7;
        *(_WORD *)v60 = 0;
        v48 = "CacheKey";
        v37 = Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::ClassifiedStructuredObject<std::wstring>(
                v63,
                &v48,
                v62,
                16);
        v48 = "[ServiceRequest] Cache Data Found and Callback for data requested";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>>(
          (unsigned int)v57,
          v38,
          v39,
          v40,
          (__int64)&v48,
          v37,
          (__int64)v57);
        Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(v63);
        std::wstring::~wstring(v60);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a4 + 80LL))(a4, 0);
        LOBYTE(v41) = 1;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 88LL))(a4, v41);
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a4 + 136LL))(a4, *a3);
        v42 = *(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a4 + 24LL);
        v43 = v54;
        if ( (_QWORD)v54 != *((_QWORD *)&v54 + 1) )
          v10 = std::vector<unsigned char>::operator[](&v54, 0);
        v42(a4, v10, *((_QWORD *)&v43 + 1) - v43);
      }
      v48 = "CacheKey";
      v44 = Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::ClassifiedStructuredObject<std::wstring>(
              v63,
              &v48,
              v62,
              16);
      v48 = "[ServiceRequest] Cache Data Found | [FileRequest] Succeed";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
        507540556,
        823,
        50,
        v45,
        (__int64)&v48,
        v44);
      Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(v63);
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*a2 + 8LL))(*a2, 507540555, 0);
      std::vector<unsigned char>::~vector<unsigned char>(&v54);
      std::wstring::~wstring(v62);
      Mso::OfficeWebServiceApi::ServiceCacheRecord::~ServiceCacheRecord((Mso::OfficeWebServiceApi::ServiceCacheRecord *)v64);
      return 0;
    }
    v35(v33, 3);
    std::vector<unsigned char>::~vector<unsigned char>(&v54);
    goto LABEL_43;
  }
  v22 = v21 - 2;
  if ( !v22 )
    goto LABEL_17;
  v23 = v22 - 1;
  if ( v23 )
  {
    if ( v23 != 1 )
    {
      v11 = -1;
      goto LABEL_18;
    }
LABEL_17:
    v11 = 3;
  }
LABEL_18:
  (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a2 + 104LL))(*a2, v11);
LABEL_31:
  v27 = v50;
LABEL_43:
  std::wstring::~wstring(v62);
  Mso::OfficeWebServiceApi::ServiceCacheRecord::~ServiceCacheRecord((Mso::OfficeWebServiceApi::ServiceCacheRecord *)v64);
LABEL_45:
  v13 = a2;
  if ( v47 )
  {
    v14 = 0x400000;
    v12 = 507540554;
    return Mso::OfficeWebServiceApi::SetAndReturn(v12, v13, a4, v14);
  }
  return Mso::OfficeWebServiceApi::ServiceRequestHandler::FileRequestInternal(
           v56,
           (_DWORD)a2,
           (_DWORD)a3,
           a4,
           a5,
           v51,
           v27);
}

```

## disassembly

```asm
0x18008a680  push    rbp
0x18008a682  push    rbx
0x18008a683  push    rsi
0x18008a684  push    rdi
0x18008a685  push    r13
0x18008a687  push    r14
0x18008a689  push    r15
0x18008a68b  lea     rbp, [rsp-180h]
0x18008a693  sub     rsp, 280h
0x18008a69a  mov     rax, cs:__security_cookie
0x18008a6a1  xor     rax, rsp
0x18008a6a4  mov     [rbp+1B0h+var_40], rax
0x18008a6ab  mov     rdi, r9
0x18008a6ae  mov     r13, r8
0x18008a6b1  mov     rsi, rdx
0x18008a6b4  mov     [rbp+1B0h+var_220], rcx
0x18008a6b8  mov     rdx, [rbp+1B0h+arg_30]
0x18008a6bf  mov     [rsp+2B0h+var_258], rdx
0x18008a6c4  xor     ebx, ebx
0x18008a6c6  cmp     [rdx+10h], bl
0x18008a6c9  jz      short loc_18008A6DB
0x18008a6cb  mov     rcx, [rsi]
0x18008a6ce  mov     rax, [rcx]
0x18008a6d1  mov     rax, [rax+10h]
0x18008a6d5  call    cs:__guard_dispatch_icall_fptr
0x18008a6db  mov     rcx, [rsi]
0x18008a6de  mov     rax, [rcx]
0x18008a6e1  mov     rdx, [rbp+1B0h+arg_20]
0x18008a6e8  mov     rax, [rax+18h]
0x18008a6ec  call    cs:__guard_dispatch_icall_fptr
0x18008a6f2  mov     rcx, [rsi]
0x18008a6f5  mov     rax, [rcx]
0x18008a6f8  mov     r15d, 1
0x18008a6fe  mov     edx, r15d
0x18008a701  mov     rax, [rax+20h]
0x18008a705  call    cs:__guard_dispatch_icall_fptr
0x18008a70b  cmp     [r13+0], rbx
0x18008a70f  jnz     short loc_18008A759
0x18008a711  lea     rax, aServicerequest_2; "[ServiceRequest] Failed due to invalid "...
0x18008a718  mov     qword ptr [rsp+2B0h+FileTime.dwLowDateTime], rax
0x18008a71d  lea     r14d, [r15+1]
0x18008a721  mov     r9d, r14d
0x18008a724  lea     rax, [rsp+2B0h+FileTime]
0x18008a729  mov     [rsp+2B0h+var_290], rax
0x18008a72e  mov     edx, 337h
0x18008a733  mov     ecx, 1E407455h
0x18008a738  lea     r8d, [r15+0Eh]
0x18008a73c  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x18008a741  mov     ecx, 1E407454h
0x18008a746  mov     rdx, rsi
0x18008a749  mov     r9d, r14d
0x18008a74c  mov     r8, rdi
0x18008a74f  call    ?SetAndReturn@OfficeWebServiceApi@Mso@@YA?AW4Flags@Status@12@VMsoReserveTag@@AEBV?$shared_ptr@UIServiceRequestTelemetryActivity@OfficeWebServiceApi@Mso@@@std@@PEBVAServiceRequestCallback@12@W43412@@Z; Mso::OfficeWebServiceApi::SetAndReturn(MsoReserveTag,std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity> const &,Mso::OfficeWebServiceApi::AServiceRequestCallback const *,Mso::OfficeWebServiceApi::Status::Flags)
0x18008a754  jmp     loc_18008AD78
0x18008a759  mov     rcx, r13
0x18008a75c  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x18008a761  mov     rdx, rax
0x18008a764  mov     rcx, [rax]
0x18008a767  mov     rax, [rcx+68h]
0x18008a76b  mov     rcx, rdx
0x18008a76e  call    cs:__guard_dispatch_icall_fptr
0x18008a774  mov     r14d, 2
0x18008a77a  test    al, al
0x18008a77c  jnz     short loc_18008A7B1
0x18008a77e  lea     rax, aServicerequest_15; "[ServiceRequest] Failed due to invalid "...
0x18008a785  mov     qword ptr [rsp+2B0h+FileTime.dwLowDateTime], rax
0x18008a78a  mov     r9d, r14d
0x18008a78d  lea     rax, [rsp+2B0h+FileTime]
0x18008a792  mov     [rsp+2B0h+var_290], rax
0x18008a797  mov     edx, 337h
0x18008a79c  mov     ecx, 1E407453h
0x18008a7a1  lea     r8d, [r14+0Dh]
0x18008a7a5  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x18008a7aa  mov     ecx, 1E407452h
0x18008a7af  jmp     short loc_18008A746
0x18008a7b1  test    rdi, rdi
0x18008a7b4  jz      short loc_18008A7F7
0x18008a7b6  lea     rax, aServicerequest_0; "[ServiceRequest] Callback is used | Cal"...
0x18008a7bd  mov     qword ptr [rsp+2B0h+FileTime.dwLowDateTime], rax
0x18008a7c2  mov     r9d, r14d
0x18008a7c5  lea     rax, [rsp+2B0h+FileTime]
0x18008a7ca  mov     [rsp+2B0h+var_290], rax
0x18008a7cf  mov     edx, 337h
0x18008a7d4  mov     ecx, 1E407450h
0x18008a7d9  mov     r8d, 32h ; '2'
0x18008a7df  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x18008a7e4  mov     rax, [rdi]
0x18008a7e7  mov     dl, r15b
0x18008a7ea  mov     rcx, rdi
0x18008a7ed  mov     rax, [rax+68h]
0x18008a7f1  call    cs:__guard_dispatch_icall_fptr
0x18008a7f7  mov     rcx, [rbp+1B0h+arg_20]
0x18008a7fe  call    sub_18008B0A4
0x18008a803  mov     [rsp+2B0h+var_26F], al
0x18008a807  mov     [rsp+2B0h+var_250], rbx
0x18008a80c  mov     rcx, r13
0x18008a80f  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x18008a814  mov     r8, rax
0x18008a817  mov     rcx, [rax]
0x18008a81a  mov     rax, [rcx+80h]
0x18008a821  xor     edx, edx
0x18008a823  mov     rcx, r8
0x18008a826  call    cs:__guard_dispatch_icall_fptr
0x18008a82c  test    eax, eax
0x18008a82e  jnz     loc_18008AD2F
0x18008a834  xor     edx, edx; struct _msoreg *
0x18008a836  lea     rcx, [rbp+1B0h+var_130]; this
0x18008a83d  call    ??0ServiceCacheRecord@OfficeWebServiceApi@Mso@@QEAA@PEBU_msoreg@@@Z; Mso::OfficeWebServiceApi::ServiceCacheRecord::ServiceCacheRecord(_msoreg const *)
0x18008a842  mov     rcx, r13
0x18008a845  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x18008a84a  mov     rdx, rax
0x18008a84d  mov     rcx, [rax]
0x18008a850  mov     rax, [rcx+0A0h]
0x18008a857  mov     rcx, rdx
0x18008a85a  call    cs:__guard_dispatch_icall_fptr
0x18008a860  mov     rdx, rax
0x18008a863  lea     rcx, [rbp+1B0h+var_1B0]
0x18008a867  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18008a86c  xor     r8d, r8d
0x18008a86f  lea     rdx, [rbp+1B0h+var_1B0]
0x18008a873  lea     rcx, [rbp+1B0h+var_130]; this
0x18008a87a  call    ?Populate@ServiceCacheRecord@OfficeWebServiceApi@Mso@@QEAA?AW4Enum@CacheRecordPopulateStatus@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEBVAServiceRequestCallback@23@@Z; Mso::OfficeWebServiceApi::ServiceCacheRecord::Populate(std::wstring const &,bool,Mso::OfficeWebServiceApi::AServiceRequestCallback const *)
0x18008a87f  test    eax, eax
0x18008a881  jz      short loc_18008A8BC
0x18008a883  mov     r8, [rsi]
0x18008a886  mov     rcx, [r8]
0x18008a889  mov     r9, [rcx+68h]
0x18008a88d  sub     eax, r14d
0x18008a890  jz      short loc_18008A8A2
0x18008a892  sub     eax, r15d
0x18008a895  jz      short loc_18008A8A8
0x18008a897  cmp     eax, r15d
0x18008a89a  jz      short loc_18008A8A2
0x18008a89c  or      r15d, 0FFFFFFFFh
0x18008a8a0  jmp     short loc_18008A8A8
0x18008a8a2  mov     r15d, 3
0x18008a8a8  mov     edx, r15d
0x18008a8ab  mov     rcx, r8
0x18008a8ae  mov     rax, r9
0x18008a8b1  call    cs:__guard_dispatch_icall_fptr
0x18008a8b7  jmp     loc_18008AAF7
0x18008a8bc  lea     rax, aCachekey; "CacheKey"
0x18008a8c3  mov     qword ptr [rsp+2B0h+FileTime.dwLowDateTime], rax
0x18008a8c8  mov     r9d, 10h
0x18008a8ce  lea     r8, [rbp+1B0h+var_1B0]
0x18008a8d2  lea     rdx, [rsp+2B0h+FileTime]
0x18008a8d7  lea     rcx, [rbp+1B0h+var_210]
0x18008a8db  call    ??0?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Diagnostics@Mso@@QEAA@AEBV?$StringLiteral@D@StringLiterals@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4DataClassifications@Logging@2@@Z; Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::ClassifiedStructuredObject<std::wstring>(Mso::StringLiterals::StringLiteral<char> const &,std::wstring const &,Mso::Logging::DataClassifications)
0x18008a8e0  lea     rcx, aServicerequest_10; "[ServiceRequest] Cache Record Found"
0x18008a8e7  mov     qword ptr [rsp+2B0h+FileTime.dwLowDateTime], rcx
0x18008a8ec  mov     [rsp+2B0h+var_288], rax
0x18008a8f1  lea     rax, [rsp+2B0h+FileTime]
0x18008a8f6  mov     [rsp+2B0h+var_290], rax
0x18008a8fb  mov     edx, 337h
0x18008a900  mov     ecx, 1E40744Fh
0x18008a905  mov     r8d, 32h ; '2'
0x18008a90b  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x18008a910  lea     rcx, [rbp+1B0h+var_210]
0x18008a914  call    ??1?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Diagnostics@Mso@@UEAA@XZ; Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(void)
0x18008a919  mov     [rsp+2B0h+var_270], bl
0x18008a91d  test    rdi, rdi
0x18008a920  jz      short loc_18008A949
0x18008a922  mov     rax, [rdi]
0x18008a925  lea     rdx, [rbp+1B0h+var_110]
0x18008a92c  cmp     [rbp+1B0h+var_F8], 7
0x18008a934  cmova   rdx, [rbp+1B0h+var_110]
0x18008a93c  mov     rcx, rdi
0x18008a93f  mov     rax, [rax+78h]
0x18008a943  call    cs:__guard_dispatch_icall_fptr
0x18008a949  mov     rcx, [rsi]
0x18008a94c  mov     rax, [rcx]
0x18008a94f  lea     rdx, [rbp+1B0h+var_70]
0x18008a956  mov     rax, [rax+78h]
0x18008a95a  call    cs:__guard_dispatch_icall_fptr
0x18008a960  cmp     [rsp+2B0h+var_26F], bl
0x18008a964  jnz     loc_18008AB01
0x18008a96a  mov     rax, [rbp+1B0h+var_70]
0x18008a971  mov     [rsp+2B0h+var_268], rax
0x18008a976  mov     [rsp+2B0h+var_250], rax
0x18008a97b  xor     eax, eax
0x18008a97d  mov     qword ptr [rsp+2B0h+FileTime.dwLowDateTime], rax
0x18008a982  mov     rax, [rbp+1B0h+var_68]
0x18008a989  mov     [rsp+2B0h+var_248], rax
0x18008a98e  lea     rcx, [rsp+2B0h+FileTime]; lpFileTime
0x18008a993  call    ?SetCurrent@RecordDateTime@Mso@@QEAAXXZ; Mso::RecordDateTime::SetCurrent(void)
0x18008a998  mov     eax, dword ptr [rsp+2B0h+var_250]
0x18008a99c  cmp     dword ptr [rsp+2B0h+var_250+4], ebx
0x18008a9a0  jnz     short loc_18008A9A6
0x18008a9a2  test    eax, eax
0x18008a9a4  jz      short loc_18008A9AE
0x18008a9a6  cmp     [rbp+1B0h+arg_28], ebx
0x18008a9ac  jbe     short loc_18008A9E9
0x18008a9ae  mov     dword ptr [rsp+2B0h+var_240], eax
0x18008a9b2  mov     rax, [rsp+2B0h+var_268]
0x18008a9b7  shr     rax, 20h
0x18008a9bb  mov     dword ptr [rsp+2B0h+var_240+4], eax
0x18008a9bf  mov     eax, [rbp+1B0h+arg_28]
0x18008a9c5  imul    rcx, rax, 23C34600h
0x18008a9cc  mov     rax, [rsp+2B0h+var_240]
0x18008a9d1  add     rax, rcx
0x18008a9d4  mov     [rsp+2B0h+var_240], rax
0x18008a9d9  mov     ecx, dword ptr [rsp+2B0h+var_240]
0x18008a9dd  mov     dword ptr [rsp+2B0h+var_248], ecx
0x18008a9e1  shr     rax, 20h
0x18008a9e5  mov     dword ptr [rsp+2B0h+var_248+4], eax
0x18008a9e9  lea     rdx, [rsp+2B0h+var_248]; struct Mso::RecordDateTime *
0x18008a9ee  lea     rcx, [rsp+2B0h+FileTime]; this
0x18008a9f3  call    ?IsLater@RecordDateTime@Mso@@QEBA_NAEBV12@@Z; Mso::RecordDateTime::IsLater(Mso::RecordDateTime const &)
0x18008a9f8  test    al, al
0x18008a9fa  jz      loc_18008AB01
0x18008aa00  test    [rbp+1B0h+arg_20], 200000h
0x18008aa0b  jz      short loc_18008AA87
0x18008aa0d  mov     [rsp+2B0h+var_270], r15b
0x18008aa12  mov     rdx, rsi
0x18008aa15  lea     rcx, [rbp+1B0h+var_210]
0x18008aa19  call    ??0?$shared_ptr@UIServiceRequestTelemetryActivity@OfficeWebServiceApi@Mso@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity> const &)
0x18008aa1e  mov     rdx, r13
0x18008aa21  lea     rcx, [rbp+1B0h+var_200]
0x18008aa25  call    ??0?$TCntPtr@VIRequest@Http@Mso@@@Mso@@QEAA@AEBV01@@Z; Mso::TCntPtr<Mso::Http::IRequest>::TCntPtr<Mso::Http::IRequest>(Mso::TCntPtr<Mso::Http::IRequest> const &)
0x18008aa2a  mov     rax, [rbp+1B0h+arg_20]
0x18008aa31  mov     [rbp+1B0h+var_1F8], rax
0x18008aa35  mov     rax, [rsp+2B0h+var_250]
0x18008aa3a  mov     qword ptr [rbp+1B0h+var_1F0], rax
0x18008aa3e  mov     r14, [rsp+2B0h+var_258]
0x18008aa43  movups  xmm0, xmmword ptr [r14]
0x18008aa47  movups  [rbp+1B0h+var_1F0+8], xmm0
0x18008aa4b  mov     eax, [r14+10h]
0x18008aa4f  mov     dword ptr [rbp+1B0h+var_1D8], eax
0x18008aa52  lea     rcx, [rbp+1B0h+var_210]
0x18008aa56  call    sub_180089498
0x18008aa5b  mov     [rsp+2B0h+var_248], rax
0x18008aa60  call    ?ConcurrentIdleQueue@Async@Mso@@YAAEAVIDispatchQueue@12@XZ; Mso::Async::ConcurrentIdleQueue(void)
0x18008aa65  mov     rcx, rax
0x18008aa68  lea     rdx, [rsp+2B0h+var_248]
0x18008aa6d  call    ??$PostIdle@AEAVIDispatchQueue@Async@Mso@@@Async@Mso@@YAXAEAVIDispatchQueue@01@$$QEAV?$Functor@$$A6AXXZ@1@@Z; Mso::Async::PostIdle<Mso::Async::IDispatchQueue &>(Mso::Async::IDispatchQueue &,Mso::Functor<void (void)> &&)
0x18008aa72  lea     rcx, [rsp+2B0h+var_248]
0x18008aa77  call    ?Clear@?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEAAXXZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::Clear(void)
0x18008aa7c  lea     rcx, [rbp+1B0h+var_210]
0x18008aa80  call    sub_18008A1A4
0x18008aa85  jmp     short loc_18008AB06
0x18008aa87  mov     rcx, [rsi]
0x18008aa8a  mov     rax, [rcx]
0x18008aa8d  mov     edx, r14d
0x18008aa90  mov     rax, [rax+68h]
0x18008aa94  call    cs:__guard_dispatch_icall_fptr
0x18008aa9a  lea     rax, aCachekey; "CacheKey"
0x18008aaa1  mov     [rsp+2B0h+var_268], rax
0x18008aaa6  mov     r9d, 10h
0x18008aaac  lea     r8, [rbp+1B0h+var_1B0]
0x18008aab0  lea     rdx, [rsp+2B0h+var_268]
0x18008aab5  lea     rcx, [rbp+1B0h+var_210]
0x18008aab9  call    ??0?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Diagnostics@Mso@@QEAA@AEBV?$StringLiteral@D@StringLiterals@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4DataClassifications@Logging@2@@Z; Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::ClassifiedStructuredObject<std::wstring>(Mso::StringLiterals::StringLiteral<char> const &,std::wstring const &,Mso::Logging::DataClassifications)
0x18008aabe  lea     rcx, aServicerequest_1; "[ServiceRequest] Cache Update Required"
0x18008aac5  mov     [rsp+2B0h+var_268], rcx
0x18008aaca  mov     [rsp+2B0h+var_288], rax
0x18008aacf  lea     rax, [rsp+2B0h+var_268]
0x18008aad4  mov     [rsp+2B0h+var_290], rax
0x18008aad9  mov     edx, 337h
0x18008aade  mov     ecx, 1E40744Eh
0x18008aae3  mov     r8d, 32h ; '2'
0x18008aae9  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x18008aaee  lea     rcx, [rbp+1B0h+var_210]
0x18008aaf2  call    ??1?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Diagnostics@Mso@@UEAA@XZ; Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(void)
0x18008aaf7  mov     r14, [rsp+2B0h+var_258]
0x18008aafc  jmp     loc_18008AD18
0x18008ab01  mov     r14, [rsp+2B0h+var_258]
0x18008ab06  xorps   xmm0, xmm0
0x18008ab09  movdqu  [rsp+2B0h+var_238], xmm0
0x18008ab0f  mov     [rbp+1B0h+var_228], rbx
0x18008ab13  lea     rdx, [rsp+2B0h+var_238]
0x18008ab18  lea     rcx, [rbp+1B0h+var_130]
0x18008ab1f  call    ?GetData@ServiceCacheRecord@OfficeWebServiceApi@Mso@@QEAA_NAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; Mso::OfficeWebServiceApi::ServiceCacheRecord::GetData(std::vector<uchar> &)
0x18008ab24  mov     rcx, [rsi]
0x18008ab27  test    al, al
0x18008ab29  mov     rax, [rcx]
0x18008ab2c  mov     rax, [rax+68h]
0x18008ab30  jz      loc_18008AD03
0x18008ab36  mov     r14d, 4
0x18008ab3c  cmp     [rsp+2B0h+var_270], bl
0x18008ab40  jz      short loc_18008AB47
0x18008ab42  mov     edx, r14d
0x18008ab45  jmp     short loc_18008AB49
0x18008ab47  xor     edx, edx
0x18008ab49  call    cs:__guard_dispatch_icall_fptr
0x18008ab4f  test    rdi, rdi
0x18008ab52  jz      loc_18008AC6B
0x18008ab58  lea     rax, ??_7?$ClassifiedStructuredObject@_K@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable'
0x18008ab5f  mov     [rbp+1B0h+var_210], rax
0x18008ab63  lea     rax, aDatasize; "DataSize"
0x18008ab6a  mov     [rbp+1B0h+var_208], rax
0x18008ab6e  mov     rax, qword ptr [rbp+1B0h+var_238+8]
0x18008ab72  sub     rax, qword ptr [rsp+2B0h+var_238]
0x18008ab77  mov     [rbp+1B0h+var_200], rax
0x18008ab7b  mov     word ptr [rbp+1B0h+var_1F8], r14w
0x18008ab80  xorps   xmm0, xmm0
0x18008ab83  movups  [rbp+1B0h+var_1F0], xmm0
0x18008ab87  mov     [rbp+1B0h+var_1E0], rbx
0x18008ab8b  mov     [rbp+1B0h+var_1D8], 7
0x18008ab93  mov     word ptr [rbp+1B0h+var_1F0], bx
0x18008ab97  lea     rax, aCachekey; "CacheKey"
  ... truncated ...
```
