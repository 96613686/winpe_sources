# Mso::Http::CHttpRequest_WinHttp_Async::WinHttpCallback(void * const,ulong,void const *,ulong)

- ea: `0x1800e8ef8`
- end: `0x1800ea005`
- name: `?WinHttpCallback@CHttpRequest_WinHttp_Async@Http@Mso@@AEAAXQEAXKPEBXK@Z`
- size: `4365`
- prototype: `void __usercall(Mso::Http::CHttpRequest_WinHttp_Async *__hidden this@<rcx>, void *const@<rdx>, unsigned int@<r8d>, const void *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `41`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ea010`

## callees

- `0x18000adf0`
- `0x18000ffb0`
- `0x180010a84`
- `0x180011618`
- `0x180012bf8`
- `0x1800258b4`
- `0x1800264b4`
- `0x18002fd94`
- `0x18003bec8`
- `0x18003e690`
- `0x180052e28`
- `0x1800d0970`
- `0x1800d1198`
- `0x1800d4b44`
- `0x1800d5b50`
- `0x1800d5ba0`
- `0x1800d5cc0`
- `0x1800d5dc0`
- `0x1800d5ed0`
- `0x1800d5f20`
- `0x1800da628`
- `0x1800da8bc`
- `0x1800dab54`
- `0x1800dbaac`
- `0x1800dbcac`
- `0x1800dbd98`
- `0x1800dd8d8`
- `0x1800de0ac`
- `0x1800de508`
- `0x1800dfbf4`
- `0x1800e1474`
- `0x1800e7d64`
- `0x1800e7f1c`
- `0x1800e7fbc`
- `0x1800e85e0`
- `0x1800e8744`
- `0x1800e8e04`
- `0x1800e8e88`
- `0x1800e8ef8`
- `0x1800ee89c`
- `0x180146090`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1800e919a`
- `KERNEL32!SetEvent` at `0x1800e919a`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800e9db6`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800e9db6`

## string_xrefs

- `0x1800e99f5`: `Received WINHTTP_CALLBACK_STATUS_WRITE_COMPLETE`
- `0x1800e91bd`: `m_pRequestBroker is null`
- `0x1800e96cd`: `Received WINHTTP_CALLBACK_STATUS_SENDREQUEST_COMPLETE`
- `0x1800e9a9d`: `Received WINHTTP_CALLBACK_STATUS_READ_COMPLETE`
- `0x1800e9f68`: `SecurityError`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Mso::Http::CHttpRequest_WinHttp_Async::WinHttpCallback(
        Mso::Http::CHttpRequest_WinHttp_Async *this,
        void *const a2,
        unsigned int a3,
        int *a4,
        unsigned int a5)
{
  _QWORD *v7; // rdi
  unsigned int v8; // r8d
  unsigned int v9; // r8d
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  _QWORD *v14; // r13
  char *v15; // rax
  int v16; // r9d
  _QWORD *v17; // rax
  __int64 v18; // rdx
  int v19; // r9d
  int v20; // ecx
  __int64 v21; // r14
  const char *v22; // rax
  int v23; // ecx
  int v24; // r8d
  _QWORD *v25; // rdi
  int v26; // r9d
  _QWORD *v27; // rax
  __int64 v28; // rax
  int v29; // r9d
  _QWORD *v30; // rax
  __int64 v31; // rax
  Mso::Http::HttpRequestWinTimings *v32; // rbx
  int v33; // r9d
  _QWORD *v34; // rax
  int v35; // r9d
  _QWORD *v36; // rax
  char *v37; // r13
  char *v38; // rax
  unsigned int v39; // edx
  int v40; // r9d
  Mso::Http::Util *v41; // rcx
  const char *v42; // rax
  int v43; // ecx
  char *v44; // rax
  __int64 DataAvailable; // rax
  int *v46; // r8
  Mso::Http::ConnectionDataUsage **v47; // rdx
  char *v48; // rax
  char *v49; // rax
  const wchar_t *v50; // rdx
  int v51; // r9d
  char *v52; // rax
  __int64 v53; // rax
  int v54; // r9d
  char *v55; // r13
  char *v56; // rax
  Mso::Http::Flights *v57; // rcx
  int v58; // r9d
  char *v59; // rax
  const struct IMsoUrl *v60; // r8
  int v61; // edx
  int v62; // r8d
  int v63; // r9d
  _QWORD *v64; // rcx
  _QWORD *v65; // rax
  bool lpdwBufferLength; // [rsp+20h] [rbp-E0h]
  struct IRequest *lpdwIndex; // [rsp+28h] [rbp-D8h]
  const struct IMsoUrl *v68; // [rsp+30h] [rbp-D0h]
  char v69[8]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwBufferLength[2]; // [rsp+48h] [rbp-B8h] BYREF
  Mso::Http::ConnectionDataUsage *v71[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v72; // [rsp+60h] [rbp-A0h]
  const char *Buffer; // [rsp+70h] [rbp-90h] BYREF
  int v74; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v75; // [rsp+80h] [rbp-80h]
  _BYTE v76[32]; // [rsp+90h] [rbp-70h] BYREF
  void **v77; // [rsp+B0h] [rbp-50h] BYREF
  const char *v78; // [rsp+B8h] [rbp-48h]
  _QWORD *v79; // [rsp+C0h] [rbp-40h]
  _BYTE v80[24]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v81; // [rsp+E0h] [rbp-20h]
  __int64 v82; // [rsp+E8h] [rbp-18h]
  struct IRequest v83; // [rsp+F0h] [rbp-10h] BYREF
  const char *v84; // [rsp+F8h] [rbp-8h]
  char *v85; // [rsp+100h] [rbp+0h]
  __int16 v86; // [rsp+108h] [rbp+8h]
  __int128 v87; // [rsp+110h] [rbp+10h] BYREF
  __int64 v88; // [rsp+120h] [rbp+20h]
  __int64 v89; // [rsp+128h] [rbp+28h]
  void **v90; // [rsp+130h] [rbp+30h] BYREF
  const char *v91; // [rsp+138h] [rbp+38h]
  _QWORD *v92; // [rsp+140h] [rbp+40h]
  __int16 v93; // [rsp+148h] [rbp+48h]
  __int128 v94; // [rsp+150h] [rbp+50h] BYREF
  __int64 v95; // [rsp+160h] [rbp+60h]
  __int64 v96; // [rsp+168h] [rbp+68h]

  *(_QWORD *)dwBufferLength = a4;
  if ( a2 != *((void *const *)this + 15) )
  {
    v7 = (_QWORD *)((char *)this + 80);
    if ( *((_QWORD *)this + 13) > 7u )
      v7 = (_QWORD *)*v7;
    v78 = "RequestId";
    v79 = v7;
    *(_WORD *)v80 = 256;
    *(_OWORD *)&v80[8] = 0;
    v81 = 0;
    v82 = 7;
    *(_WORD *)&v80[8] = 0;
    v77 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
    *(_QWORD *)dwBufferLength = "HINTERNET passed to WinHttp callback does not match HINTERNET stored on IRequest";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
      17409627,
      (_DWORD)a2,
      10,
      (_DWORD)a4,
      (__int64)dwBufferLength,
      (__int64)&v77);
    goto LABEL_31;
  }
  if ( a3 > 0x4000 )
  {
    switch ( a3 )
    {
      case 0x10000u:
        Mso::Http::Results::SecurityError(&v74, 0, 42296773);
        v64 = (_QWORD *)*a4;
        v75 = v64;
        v65 = (_QWORD *)((char *)this + 80);
        if ( *((_QWORD *)this + 13) > 7u )
          v65 = (_QWORD *)*v65;
        v90 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
        v91 = "RequestId";
        v92 = v65;
        v93 = 256;
        v94 = 0;
        v95 = 0;
        v96 = 7;
        LOWORD(v94) = 0;
        v83.lpVtbl = (struct IRequestVtbl *)&Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
        v84 = "SecurityError";
        v85 = (char *)v64;
        v86 = 4;
        v87 = 0;
        v88 = 0;
        v89 = 7;
        LOWORD(v87) = 0;
        v71[0] = (Mso::Http::ConnectionDataUsage *)"Received WINHTTP_CALLBACK_STATUS_SECURE_FAILURE";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
          (_DWORD)v64,
          v61,
          v62,
          v63,
          (__int64)v71,
          (__int64)&v83,
          (__int64)&v90);
        std::wstring::~wstring(&v87);
        std::wstring::~wstring(&v94);
        goto LABEL_124;
      case 0x20000u:
        v69[0] = 9;
        Mso::Http::HttpRequestWinTimings::SetTiming(
          (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
          (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
          1);
        v55 = (char *)this + 80;
        v56 = (char *)this + 80;
        if ( *((_QWORD *)this + 13) > 7u )
          v56 = *(char **)v55;
        v83.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
        v84 = "RequestId";
        v85 = v56;
        v86 = 256;
        v87 = 0;
        v88 = 0;
        v89 = 7;
        LOWORD(v87) = 0;
        *(_QWORD *)dwBufferLength = "Received WINHTTP_CALLBACK_STATUS_HEADERS_AVAILABLE";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
          508139042,
          831,
          100,
          v54,
          (__int64)dwBufferLength,
          (__int64)&v83);
        std::wstring::~wstring(&v87);
        if ( Mso::Http::Flights::IsRetryWithNtlmEnabled(v57) && *((_BYTE *)this + 165) )
        {
          LODWORD(Buffer) = 0;
          dwBufferLength[0] = 4;
          if ( WinHttpQueryHeaders(*((HINTERNET *)this + 15), 0x20000013u, 0, &Buffer, dwBufferLength, 0) )
          {
            if ( (_DWORD)Buffer == 401 )
            {
              v59 = (char *)this + 80;
              if ( *((_QWORD *)this + 13) > 7u )
                v59 = *(char **)v59;
              v83.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
              v84 = "RequestId";
              v85 = v59;
              v86 = 256;
              v87 = 0;
              v88 = 0;
              v89 = 7;
              LOWORD(v87) = 0;
              v71[0] = (Mso::Http::ConnectionDataUsage *)"Got a login failure with Negotiate. Retrying with NTLM";
              Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
                508139041,
                831,
                100,
                v58,
                (__int64)v71,
                (__int64)&v83);
              std::wstring::~wstring(&v87);
              Mso::Http::CHttpRequest_WinHttp_Base::RetryWithNtlm(this, *((void **)this + 15), v60);
              *((_BYTE *)this + 165) = 0;
              goto LABEL_116;
            }
          }
          else
          {
            if ( *((_QWORD *)this + 13) > 7u )
              v55 = *(char **)v55;
            v83.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
            v84 = "RequestId";
            v85 = v55;
            v86 = 256;
            v87 = 0;
            v88 = 0;
            v89 = 7;
            LOWORD(v87) = 0;
            v71[0] = (Mso::Http::ConnectionDataUsage *)"WinHttpQueryHeaders failed";
            Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
              508139040,
              831,
              100,
              v58,
              (__int64)v71,
              (__int64)&v83);
            std::wstring::~wstring(&v87);
          }
        }
        Mso::Http::CHttpRequest_WinHttp_Async::SetRequestSent(this);
        Mso::Http::RequestSinkProxy::onHeadersAvailable(
          (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 224),
          (struct IRequest *)this);
        DataAvailable = Mso::Http::AsyncResponseHelper::QueryDataAvailable(*((_QWORD *)this + 38), v76);
        break;
      case 0x40000u:
        std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(
          v71,
          (char *)this + 168);
        Mso::Http::ConnectionDataUsage::EndRoundtrip(v71[0]);
        std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v71);
        v69[0] = 10;
        Mso::Http::HttpRequestWinTimings::SetTiming(
          (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
          (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
          1);
        v52 = (char *)this + 80;
        if ( *((_QWORD *)this + 13) > 7u )
          v52 = *(char **)v52;
        v83.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
        v84 = "RequestId";
        v85 = v52;
        v86 = 256;
        v87 = 0;
        v88 = 0;
        v89 = 7;
        LOWORD(v87) = 0;
        Buffer = "Received WINHTTP_CALLBACK_STATUS_DATA_AVAILABLE";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
          508139039,
          831,
          100,
          v51,
          (__int64)&Buffer,
          (__int64)&v83);
        std::wstring::~wstring(&v87);
        *(_QWORD *)dwBufferLength = 0;
        v53 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->((char *)this + 16);
        (*(void (__fastcall **)(__int64, int *, __int64, DWORD *))(*(_QWORD *)v53 + 64LL))(
          v53,
          &v74,
          10,
          dwBufferLength);
        if ( !v74 && *(_QWORD *)dwBufferLength )
          (*(void (__fastcall **)(_QWORD, Mso::Http::CHttpRequest_WinHttp_Async *))(**(_QWORD **)dwBufferLength + 24LL))(
            *(_QWORD *)dwBufferLength,
            this);
        Mso::Http::AsyncResponseHelper::DataAvailable(*((_QWORD *)this + 38), v76, (unsigned int)*a4);
        v46 = (int *)v76;
        v47 = v71;
        goto LABEL_125;
      case 0x80000u:
        v49 = (char *)this + 80;
        if ( *((_QWORD *)this + 13) > 7u )
          v49 = *(char **)v49;
        v83.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
        v84 = "RequestId";
        v85 = v49;
        v86 = 256;
        v87 = 0;
        v88 = 0;
        v89 = 7;
        LOWORD(v87) = 0;
        *(_QWORD *)dwBufferLength = "Received WINHTTP_CALLBACK_STATUS_READ_COMPLETE";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
          508139038,
          831,
          100,
          (_DWORD)a4,
          (__int64)dwBufferLength,
          (__int64)&v83);
        std::wstring::~wstring(&v87);
        v69[0] = 0;
        Mso::Http::AsyncResponseHelper::ReadComplete(*((_QWORD *)this + 38), v71, a5, v69);
        if ( !LODWORD(v71[0]) )
          Mso::Http::RequestSinkProxy::onDataAvailable(
            (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 224),
            (struct IRequest *)this,
            *((struct ISequentialStream **)this + 36));
        Mso::Http::CHttpRequest_WinHttp_Async::HandleResult(this, v76, v71);
        if ( v69[0] )
        {
          sub_1800E7D64((char *)this + 352);
          v50 = (const wchar_t *)((char *)this + 80);
          if ( *((_QWORD *)this + 13) > 7u )
            v50 = *(const wchar_t **)v50;
          Mso::Http::HttpRequestWinTimings::EmitTimingsReport(
            (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
            v50,
            (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 56),
            1,
            lpdwBufferLength,
            lpdwIndex,
            v68);
          Mso::Http::RequestSinkProxy::onResponseReceived(
            (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 224),
            (struct IRequest *)this,
            *((struct ISequentialStream **)this + 36));
        }
        else
        {
          Mso::Http::AsyncResponseHelper::QueryDataAvailable(*((_QWORD *)this + 38), v76);
        }
        return;
      case 0x100000u:
        v48 = (char *)this + 80;
        if ( *((_QWORD *)this + 13) > 7u )
          v48 = *(char **)v48;
        v83.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
        v84 = "RequestId";
        v85 = v48;
        v86 = 256;
        v87 = 0;
        v88 = 0;
        v89 = 7;
        LOWORD(v87) = 0;
        *(_QWORD *)dwBufferLength = "Received WINHTTP_CALLBACK_STATUS_WRITE_COMPLETE";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
          508139072,
          831,
          100,
          (_DWORD)a4,
          (__int64)dwBufferLength,
          (__int64)&v83);
        std::wstring::~wstring(&v87);
        if ( a4 )
          Mso::Http::RequestSinkProxy::onRequestDataReceived(
            (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 224),
            (struct IRequest *)this,
            (unsigned int)*a4);
LABEL_69:
        Mso::Http::SendRequestHelper::ContinueSend(*((_QWORD *)this + 37), &v74);
LABEL_124:
        v47 = (Mso::Http::ConnectionDataUsage **)v76;
        v46 = &v74;
        goto LABEL_125;
      case 0x200000u:
        v37 = (char *)this + 80;
        if ( a4 )
        {
          v38 = (char *)this + 80;
          if ( *((_QWORD *)this + 13) > 7u )
            v38 = *(char **)v37;
          v83.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
          v84 = "RequestId";
          v85 = v38;
          v86 = 256;
          v87 = 0;
          v88 = 0;
          v89 = 7;
          LOWORD(v87) = 0;
          v90 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
          v91 = "Result";
          v92 = *(_QWORD **)a4;
          v93 = 4;
          v94 = 0;
          v95 = 0;
          v96 = 7;
          LOWORD(v94) = 0;
          v77 = &Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>::`vftable';
          v78 = "Error";
          LODWORD(v79) = a4[2];
          WORD2(v79) = 4;
          memset(v80, 0, sizeof(v80));
          v81 = 7;
          *(_WORD *)v80 = 0;
          Buffer = "Received WINHTTP_CALLBACK_STATUS_REQUEST_ERROR";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
            (_DWORD)a4,
            4,
            0x200000,
            (_DWORD)a4,
            (__int64)&Buffer,
            (__int64)&v77,
            (__int64)&v90,
            (__int64)&v83);
          std::wstring::~wstring(v80);
          std::wstring::~wstring(&v94);
          std::wstring::~wstring(&v87);
          v41 = (Mso::Http::Util *)*(unsigned int *)(*(_QWORD *)dwBufferLength + 8LL);
          if ( (_DWORD)v41 == 12032 )
          {
            if ( *((_QWORD *)v37 + 3) > 7u )
              v37 = *(char **)v37;
            v85 = v37;
            v42 = "Got a ERROR_WINHTTP_RESEND_REQUEST - Resending the request now";
            v43 = 508139035;
LABEL_77:
            *(_QWORD *)dwBufferLength = v42;
            v87 = 0;
            LOWORD(v87) = 0;
            v89 = 7;
            v88 = 0;
            v86 = 256;
            v84 = "RequestId";
            v83.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
            Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
              v43,
              831,
              15,
              v40,
              (__int64)dwBufferLength,
              (__int64)&v83);
            std::wstring::~wstring(&v87);
LABEL_116:
            Mso::Http::CHttpRequest_WinHttp_Async::ResendRequest(this);
            return;
          }
          if ( Mso::Http::Util::IsKnownProxyError(v41, v39) && Mso::Http::CHttpRequest_WinHttp_Async::AdvanceProxy(this) )
          {
            v44 = (char *)this + 80;
            if ( *((_QWORD *)this + 13) > 7u )
              v44 = *(char **)v44;
            v85 = v44;
            v42 = "Got a proxy error, but found a fallback proxy - Resending the request with new proxy";
            v43 = 508139034;
            goto LABEL_77;
          }
          DataAvailable = Mso::Http::ConvertDwToResult(
                            v76,
                            *(unsigned int *)(*(_QWORD *)dwBufferLength + 8LL),
                            42296774);
        }
        else
        {
          if ( *((_QWORD *)this + 13) > 7u )
            v37 = *(char **)v37;
          v83.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
          v84 = "RequestId";
          v85 = v37;
          v86 = 256;
          v87 = 0;
          v88 = 0;
          v89 = 7;
          LOWORD(v87) = 0;
          *(_QWORD *)dwBufferLength = "Received WINHTTP_CALLBACK_STATUS_REQUEST_ERROR with no WINHTTP_ASYNC_RESULT";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
            508139033,
            831,
            15,
            0,
            (__int64)dwBufferLength,
            (__int64)&v83);
          std::wstring::~wstring(&v87);
          MsoShipAssertTagProc(5861667);
          DataAvailable = Mso::Http::Results::InvalidObject(v76, 0, 42296775);
        }
        break;
      case 0x400000u:
        v69[0] = 12;
        Mso::Http::HttpRequestWinTimings::SetTiming(
          (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
          (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
          0);
        v36 = (_QWORD *)((char *)this + 80);
        if ( *((_QWORD *)this + 13) > 7u )
          v36 = (_QWORD *)*v36;
        v77 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
        v78 = "RequestId";
        v79 = v36;
        *(_WORD *)v80 = 256;
        *(_OWORD *)&v80[8] = 0;
        v81 = 0;
        v82 = 7;
        *(_WORD *)&v80[8] = 0;
        *(_QWORD *)dwBufferLength = "Received WINHTTP_CALLBACK_STATUS_SENDREQUEST_COMPLETE";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
          508139043,
          831,
          100,
          v35,
          (__int64)dwBufferLength,
          (__int64)&v77);
        std::wstring::~wstring(&v80[8]);
        goto LABEL_69;
      default:
        return;
    }
    v46 = (int *)DataAvailable;
    v47 = (Mso::Http::ConnectionDataUsage **)&v74;
LABEL_125:
    Mso::Http::CHttpRequest_WinHttp_Async::HandleResult(this, v47, v46);
    return;
  }
  if ( a3 == 0x4000 )
  {
    v69[0] = 0;
    v32 = (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352);
    Mso::Http::HttpRequestWinTimings::SetTiming(
      (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
      (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
      0);
    v69[0] = 1;
    Mso::Http::HttpRequestWinTimings::SetTiming(v32, (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69, 1);
    v34 = (_QWORD *)((char *)this + 80);
    if ( *((_QWORD *)this + 13) > 7u )
      v34 = (_QWORD *)*v34;
    v77 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
    v78 = "RequestId";
    v79 = v34;
    *(_WORD *)v80 = 256;
    *(_OWORD *)&v80[8] = 0;
    v81 = 0;
    v82 = 7;
    *(_WORD *)&v80[8] = 0;
    *(_QWORD *)dwBufferLength = "Received WINHTTP_CALLBACK_STATUS_REDIRECT";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
      508139029,
      831,
      100,
      v33,
      (__int64)dwBufferLength,
      (__int64)&v77);
    std::wstring::~wstring(&v80[8]);
    if ( !Mso::Http::RequestSinkProxy::onRedirect(
            (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 224),
            (struct IRequest *)this,
            (const wchar_t *)a4) )
      (*(void (__fastcall **)(Mso::Http::CHttpRequest_WinHttp_Async *, _BYTE *))(*(_QWORD *)this + 136LL))(this, v76);
  }
  else
  {
    v8 = a3 - 1;
    if ( !v8 )
    {
      v69[0] = 3;
      Mso::Http::HttpRequestWinTimings::SetTiming(
        (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
        (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
        1);
      v25 = (_QWORD *)((char *)this + 80);
      if ( v25[3] > 7u )
        v25 = (_QWORD *)*v25;
      v22 = "Received WINHTTP_CALLBACK_STATUS_RESOLVING_NAME";
      v23 = 508139028;
      goto LABEL_54;
    }
    v9 = v8 - 1;
    if ( !v9 )
    {
      v69[0] = 4;
      Mso::Http::HttpRequestWinTimings::SetTiming(
        (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
        (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
        1);
      v25 = (_QWORD *)((char *)this + 80);
      if ( v25[3] > 7u )
        v25 = (_QWORD *)*v25;
      v22 = "Received WINHTTP_CALLBACK_STATUS_NAME_RESOLVED";
      v23 = 508139027;
      goto LABEL_54;
    }
    v10 = v9 - 2;
    if ( v10 )
    {
      v11 = v10 - 4;
      if ( v11 )
      {
        v12 = v11 - 8;
        if ( v12 )
        {
          v13 = v12 - 16;
          if ( !v13 )
          {
            v69[0] = 11;
            Mso::Http::HttpRequestWinTimings::SetTiming(
              (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
              (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
              1);
            return;
          }
          if ( v13 != 2016 )
            return;
          v14 = (_QWORD *)((char *)this + 80);
          v15 = (char *)this + 80;
          if ( *((_QWORD *)this + 13) > 7u )
            v15 = (char *)*v14;
          v77 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
          v78 = "RequestId";
          v79 = v15;
          *(_WORD *)v80 = 256;
          *(_OWORD *)&v80[8] = 0;
          v81 = 0;
          v82 = 7;
          *(_WORD *)&v80[8] = 0;
          *(_QWORD *)dwBufferLength = "Received WINHTTP_CALLBACK_STATUS_HANDLE_CLOSING";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
            508139032,
            831,
            100,
            (_DWORD)a4,
            (__int64)dwBufferLength,
            (__int64)&v77);
          std::wstring::~wstring(&v80[8]);
          if ( !*((_BYTE *)this + 26) )
          {
            v17 = v14;
            if ( v14[3] > 7u )
              v17 = (_QWORD *)*v14;
            v77 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
            v78 = "RequestId";
            v79 = v17;
            *(_WORD *)v80 = 256;
            *(_OWORD *)&v80[8] = 0;
            v81 = 0;
            v82 = 7;
            *(_WORD *)&v80[8] = 0;
            *(_QWORD *)dwBufferLength = "WinHttpCallback: handle is being closed without aborting";
            Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
              19715107,
              831,
              10,
              v16,
              (__int64)dwBufferLength,
              (__int64)&v77);
            std::wstring::~wstring(&v80[8]);
          }
          *((_QWORD *)this + 15) = 0;
          v18 = Mso::Http::Results::Aborted(v76, 0, 42296776);
          v20 = *((_DWORD *)this + 64);
          if ( v20 != 2 && v20 != 4 )
          {
            *(_OWORD *)v71 = *(_OWORD *)v18;
            v72 = *(_QWORD *)(v18 + 16);
            Mso::Http::RequestSinkProxy::onError((char *)this + 224, *((_QWORD *)this + 31), v71);
          }
          if ( *((_QWORD *)this + 39) )
          {
            v21 = Mso::TCntRef<Mso::Http::IRequestFactory const>::operator->((char *)this + 312);
            std::_Mutex_base::lock((std::_Mutex_base *)(v21 + 80));
            *(_QWORD *)dwBufferLength = this;
            std::_Hash<std::_Umap_traits<Mso::Http::IRequest const *,Mso::TCntPtr<Mso::Http::IRequest>,std::_Uhash_compare<Mso::Http::IRequest const *,std::hash<Mso::Http::IRequest const *>,std::equal_to<Mso::Http::IRequest const *>>,std::allocator<std::pair<Mso::Http::IRequest const * const,Mso::TCntPtr<Mso::Http::IRequest>>>,0>>::_Erase<Mso::Http::IRequest const *>(
              (_QWORD *)(v21 + 16),
              (const unsigned __int8 *)dwBufferLength);
            if ( !*(_QWORD *)(v21 + 32) )
              SetEvent(*(HANDLE *)(v21 + 160));
            Mtx_unlock((_Mtx_t)(v21 + 80));
            return;
          }
          if ( v14[3] > 7u )
            v14 = (_QWORD *)*v14;
          v79 = v14;
          v22 = "m_pRequestBroker is null";
          v23 = 40449366;
          v24 = 10;
LABEL_30:
          *(_QWORD *)dwBufferLength = v22;
          *(_OWORD *)&v80[8] = 0;
          *(_WORD *)&v80[8] = 0;
          v82 = 7;
          v81 = 0;
          *(_WORD *)v80 = 256;
          v78 = "RequestId";
          v77 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
            v23,
            831,
            v24,
            v19,
            (__int64)dwBufferLength,
            (__int64)&v77);
LABEL_31:
          std::wstring::~wstring(&v80[8]);
          return;
        }
        if ( *((_DWORD *)this + 94) != -1 )
        {
          v69[0] = 7;
          Mso::Http::HttpRequestWinTimings::SetTiming(
            (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
            (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
            1);
        }
        v69[0] = 8;
        Mso::Http::HttpRequestWinTimings::SetTiming(
          (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
          (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
          1);
        v25 = (_QWORD *)((char *)this + 80);
        if ( v25[3] > 7u )
          v25 = (_QWORD *)*v25;
        v22 = "Received WINHTTP_CALLBACK_STATUS_SENDING_REQUEST";
        v23 = 508139026;
LABEL_54:
        v79 = v25;
        v24 = 100;
        goto LABEL_30;
      }
      v69[0] = 6;
      Mso::Http::HttpRequestWinTimings::SetTiming(
        (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
        (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
        1);
      v27 = (_QWORD *)((char *)this + 80);
      if ( *((_QWORD *)this + 13) > 7u )
        v27 = (_QWORD *)*v27;
      v77 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
      v78 = "RequestId";
      v79 = v27;
      *(_WORD *)v80 = 256;
      *(_OWORD *)&v80[8] = 0;
      v81 = 0;
      v82 = 7;
      *(_WORD *)&v80[8] = 0;
      Buffer = "Received WINHTTP_CALLBACK_STATUS_CONNECTED_TO_SERVER";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
        508139030,
        831,
        100,
        v26,
        (__int64)&Buffer,
        (__int64)&v77);
      std::wstring::~wstring(&v80[8]);
      *(_QWORD *)dwBufferLength = 0;
      v28 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->((char *)this + 16);
      (*(void (__fastcall **)(__int64, int *, __int64, DWORD *))(*(_QWORD *)v28 + 64LL))(v28, &v74, 10, dwBufferLength);
      if ( !v74 && *(_QWORD *)dwBufferLength )
        (*(void (__fastcall **)(_QWORD, Mso::Http::CHttpRequest_WinHttp_Async *, int *))(**(_QWORD **)dwBufferLength
                                                                                       + 32LL))(
          *(_QWORD *)dwBufferLength,
          this,
          a4);
    }
    else
    {
      v69[0] = 5;
      Mso::Http::HttpRequestWinTimings::SetTiming(
        (Mso::Http::CHttpRequest_WinHttp_Async *)((char *)this + 352),
        (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v69,
        0);
      v30 = (_QWORD *)((char *)this + 80);
      if ( *((_QWORD *)this + 13) > 7u )
        v30 = (_QWORD *)*v30;
      v77 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
      v78 = "RequestId";
      v79 = v30;
      *(_WORD *)v80 = 256;
      *(_OWORD *)&v80[8] = 0;
      v81 = 0;
      v82 = 7;
      *(_WORD *)&v80[8] = 0;
      Buffer = "Received WINHTTP_CALLBACK_STATUS_CONNECTING_TO_SERVER";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
        508139031,
        831,
        100,
        v29,
        (__int64)&Buffer,
        (__int64)&v77);
      std::wstring::~wstring(&v80[8]);
      *(_QWORD *)dwBufferLength = 0;
      v31 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->((char *)this + 16);
      (*(void (__fastcall **)(__int64, int *, __int64, DWORD *))(*(_QWORD *)v31 + 64LL))(v31, &v74, 10, dwBufferLength);
      if ( !v74 && *(_QWORD *)dwBufferLength )
        (*(void (__fastcall **)(_QWORD, Mso::Http::CHttpRequest_WinHttp_Async *, int *))(**(_QWORD **)dwBufferLength
                                                                                       + 16LL))(
          *(_QWORD *)dwBufferLength,
          this,
          a4);
    }
  }
}

```

## disassembly

```asm
0x1800e8ef8  mov     [rsp-8+arg_8], rbx
0x1800e8efd  push    rbp
0x1800e8efe  push    rsi
0x1800e8eff  push    rdi
0x1800e8f00  push    r12
0x1800e8f02  push    r13
0x1800e8f04  push    r14
0x1800e8f06  push    r15
0x1800e8f08  lea     rbp, [rsp-80h]
0x1800e8f0d  sub     rsp, 180h
0x1800e8f14  mov     rax, cs:__security_cookie
0x1800e8f1b  xor     rax, rsp
0x1800e8f1e  mov     [rbp+0B0h+var_40], rax
0x1800e8f22  mov     r13, r9
0x1800e8f25  mov     qword ptr [rsp+1B0h+dwBufferLength], r9
0x1800e8f2a  mov     rdi, rcx
0x1800e8f2d  cmp     rdx, [rcx+78h]
0x1800e8f31  jz      short loc_1800E8FB1
0x1800e8f33  add     rdi, 50h ; 'P'
0x1800e8f37  mov     ebx, 7
0x1800e8f3c  cmp     [rdi+18h], rbx
0x1800e8f40  jbe     short loc_1800E8F45
0x1800e8f42  mov     rdi, [rdi]
0x1800e8f45  lea     r14, aRequestid; "RequestId"
0x1800e8f4c  mov     [rbp+0B0h+var_F8], r14
0x1800e8f50  mov     [rbp+0B0h+var_F0], rdi
0x1800e8f54  mov     r15d, 100h
0x1800e8f5a  mov     word ptr [rbp+0B0h+var_E8], r15w
0x1800e8f5f  xorps   xmm0, xmm0
0x1800e8f62  movups  [rbp+0B0h+var_E8+8], xmm0
0x1800e8f66  xor     esi, esi
0x1800e8f68  mov     [rbp+0B0h+var_D0], rsi
0x1800e8f6c  mov     [rbp+0B0h+var_C8], rbx
0x1800e8f70  mov     word ptr [rbp+0B0h+var_E8+8], si
0x1800e8f74  lea     rax, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x1800e8f7b  mov     [rbp+0B0h+var_100], rax
0x1800e8f7f  lea     rax, aHinternetPasse; "HINTERNET passed to WinHttp callback do"...
0x1800e8f86  mov     qword ptr [rsp+1B0h+dwBufferLength], rax
0x1800e8f8b  lea     rax, [rbp+0B0h+var_100]
0x1800e8f8f  mov     [rsp+1B0h+lpdwIndex], rax
0x1800e8f94  lea     rax, [rsp+1B0h+dwBufferLength]
0x1800e8f99  mov     [rsp+1B0h+lpdwBufferLength], rax
0x1800e8f9e  mov     ecx, 109A65Bh
0x1800e8fa3  lea     r8d, [rsi+0Ah]
0x1800e8fa7  call    ??$SendDiagnosticTrace@UResult@Structured@Logging@Http@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUResult@Structured@3Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Result &&)
0x1800e8fac  jmp     loc_1800E9211
0x1800e8fb1  mov     eax, 4000h
0x1800e8fb6  cmp     r8d, eax
0x1800e8fb9  ja      loc_1800E960D
0x1800e8fbf  jz      loc_1800E951F
0x1800e8fc5  sub     r8d, 1
0x1800e8fc9  jz      loc_1800E94C5
0x1800e8fcf  sub     r8d, 1
0x1800e8fd3  jz      loc_1800E948C
0x1800e8fd9  sub     r8d, 2
0x1800e8fdd  jz      loc_1800E938D
0x1800e8fe3  sub     r8d, 4
0x1800e8fe7  jz      loc_1800E929A
0x1800e8fed  sub     r8d, 8
0x1800e8ff1  jz      loc_1800E923D
0x1800e8ff7  sub     r8d, 10h
0x1800e8ffb  jz      loc_1800E921F
0x1800e9001  cmp     r8d, 7E0h
0x1800e9008  jnz     loc_1800E9FDE
0x1800e900e  lea     r13, [rcx+50h]
0x1800e9012  mov     rax, r13
0x1800e9015  mov     ebx, 7
0x1800e901a  cmp     [r13+18h], rbx
0x1800e901e  jbe     short loc_1800E9024
0x1800e9020  mov     rax, [r13+0]
0x1800e9024  lea     r12, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x1800e902b  mov     [rbp+0B0h+var_100], r12
0x1800e902f  lea     r14, aRequestid; "RequestId"
0x1800e9036  mov     [rbp+0B0h+var_F8], r14
0x1800e903a  mov     [rbp+0B0h+var_F0], rax
0x1800e903e  mov     r15d, 100h
0x1800e9044  mov     word ptr [rbp+0B0h+var_E8], r15w
0x1800e9049  xorps   xmm0, xmm0
0x1800e904c  movups  [rbp+0B0h+var_E8+8], xmm0
0x1800e9050  xor     esi, esi
0x1800e9052  mov     [rbp+0B0h+var_D0], rsi
0x1800e9056  mov     [rbp+0B0h+var_C8], rbx
0x1800e905a  mov     word ptr [rbp+0B0h+var_E8+8], si
0x1800e905e  lea     rax, aReceivedWinhtt; "Received WINHTTP_CALLBACK_STATUS_HANDLE"...
0x1800e9065  mov     qword ptr [rsp+1B0h+dwBufferLength], rax
0x1800e906a  lea     rax, [rbp+0B0h+var_100]
0x1800e906e  mov     [rsp+1B0h+lpdwIndex], rax
0x1800e9073  lea     rax, [rsp+1B0h+dwBufferLength]
0x1800e9078  mov     [rsp+1B0h+lpdwBufferLength], rax
0x1800e907d  mov     edx, 33Fh
0x1800e9082  mov     ecx, 1E499618h
0x1800e9087  lea     r8d, [rsi+64h]
0x1800e908b  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x1800e9090  lea     rcx, [rbp+0B0h+var_E8+8]; void *
0x1800e9094  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e9099  cmp     [rdi+1Ah], sil
0x1800e909d  jnz     short loc_1800E910D
0x1800e909f  mov     rax, r13
0x1800e90a2  cmp     [r13+18h], rbx
0x1800e90a6  jbe     short loc_1800E90AC
0x1800e90a8  mov     rax, [r13+0]
0x1800e90ac  mov     [rbp+0B0h+var_100], r12
0x1800e90b0  mov     [rbp+0B0h+var_F8], r14
0x1800e90b4  mov     [rbp+0B0h+var_F0], rax
0x1800e90b8  mov     word ptr [rbp+0B0h+var_E8], r15w
0x1800e90bd  xorps   xmm0, xmm0
0x1800e90c0  movups  [rbp+0B0h+var_E8+8], xmm0
0x1800e90c4  mov     [rbp+0B0h+var_D0], rsi
0x1800e90c8  mov     [rbp+0B0h+var_C8], rbx
0x1800e90cc  mov     word ptr [rbp+0B0h+var_E8+8], si
0x1800e90d0  lea     rax, aWinhttpcallbac; "WinHttpCallback: handle is being closed"...
0x1800e90d7  mov     qword ptr [rsp+1B0h+dwBufferLength], rax
0x1800e90dc  lea     rax, [rbp+0B0h+var_100]
0x1800e90e0  mov     [rsp+1B0h+lpdwIndex], rax
0x1800e90e5  lea     rax, [rsp+1B0h+dwBufferLength]
0x1800e90ea  mov     [rsp+1B0h+lpdwBufferLength], rax
0x1800e90ef  mov     edx, 33Fh
0x1800e90f4  mov     ecx, 12CD423h
0x1800e90f9  mov     r8d, 0Ah
0x1800e90ff  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x1800e9104  lea     rcx, [rbp+0B0h+var_E8+8]; void *
0x1800e9108  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e910d  mov     [rdi+78h], rsi
0x1800e9111  xor     edx, edx
0x1800e9113  mov     r8d, 28565C8h
0x1800e9119  lea     rcx, [rbp+0B0h+var_120]
0x1800e911d  call    ?Aborted@Results@Http@Mso@@YA?AUResult@23@_JI@Z; Mso::Http::Results::Aborted(__int64,uint)
0x1800e9122  mov     rdx, rax
0x1800e9125  lea     rax, [rdi+0E0h]
0x1800e912c  mov     ecx, [rax+20h]
0x1800e912f  cmp     ecx, 2
0x1800e9132  jz      short loc_1800E915D
0x1800e9134  cmp     ecx, 4
0x1800e9137  jz      short loc_1800E915D
0x1800e9139  movups  xmm0, xmmword ptr [rdx]
0x1800e913c  movaps  xmmword ptr [rsp+1B0h+var_160], xmm0
0x1800e9141  movsd   xmm1, qword ptr [rdx+10h]
0x1800e9146  movsd   [rsp+1B0h+var_150], xmm1
0x1800e914c  lea     r8, [rsp+1B0h+var_160]
0x1800e9151  mov     rdx, [rax+18h]
0x1800e9155  mov     rcx, rax
0x1800e9158  call    ?onError@RequestSinkProxy@Http@Mso@@UEAAXAEAVIRequest@23@UResult@23@@Z; Mso::Http::RequestSinkProxy::onError(Mso::Http::IRequest &,Mso::Http::Result)
0x1800e915d  lea     rcx, [rdi+138h]
0x1800e9164  cmp     [rcx], rsi
0x1800e9167  jz      short loc_1800E91AF
0x1800e9169  call    ??C?$TCntRef@$$CBVIRequestFactory@Http@Mso@@@Mso@@QEBAPEBVIRequestFactory@Http@1@XZ; Mso::TCntRef<Mso::Http::IRequestFactory const>::operator->(void)
0x1800e916e  mov     r14, rax
0x1800e9171  lea     rcx, [rax+50h]; this
0x1800e9175  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800e917a  mov     qword ptr [rsp+1B0h+dwBufferLength], rdi
0x1800e917f  lea     rcx, [r14+10h]
0x1800e9183  lea     rdx, [rsp+1B0h+dwBufferLength]
0x1800e9188  call    ??$_Erase@PEBVIRequest@Http@Mso@@@?$_Hash@V?$_Umap_traits@PEBVIRequest@Http@Mso@@V?$TCntPtr@VIRequest@Http@Mso@@@3@V?$_Uhash_compare@PEBVIRequest@Http@Mso@@U?$hash@PEBVIRequest@Http@Mso@@@std@@U?$equal_to@PEBVIRequest@Http@Mso@@@5@@std@@V?$allocator@U?$pair@QEBVIRequest@Http@Mso@@V?$TCntPtr@VIRequest@Http@Mso@@@3@@std@@@6@$0A@@std@@@std@@AEAA_KAEBQEBVIRequest@Http@Mso@@@Z; std::_Hash<std::_Umap_traits<Mso::Http::IRequest const *,Mso::TCntPtr<Mso::Http::IRequest>,std::_Uhash_compare<Mso::Http::IRequest const *,std::hash<Mso::Http::IRequest const *>,std::equal_to<Mso::Http::IRequest const *>>,std::allocator<std::pair<Mso::Http::IRequest const * const,Mso::TCntPtr<Mso::Http::IRequest>>>,0>>::_Erase<Mso::Http::IRequest const *>(Mso::Http::IRequest const * const &)
0x1800e918d  cmp     [r14+20h], rsi
0x1800e9191  jnz     short loc_1800E91A0
0x1800e9193  mov     rcx, [r14+0A0h]; hEvent
0x1800e919a  call    cs:__imp_SetEvent
0x1800e91a0  lea     rcx, [r14+50h]; _Mtx_t
0x1800e91a4  call    _Mtx_unlock
0x1800e91a9  nop
0x1800e91aa  jmp     loc_1800E9FDE
0x1800e91af  cmp     [r13+18h], rbx
0x1800e91b3  jbe     short loc_1800E91B9
0x1800e91b5  mov     r13, [r13+0]
0x1800e91b9  mov     [rbp+0B0h+var_F0], r13
0x1800e91bd  lea     rax, aMPrequestbroke; "m_pRequestBroker is null"
0x1800e91c4  mov     ecx, 2693556h
0x1800e91c9  mov     r8d, 0Ah
0x1800e91cf  mov     qword ptr [rsp+1B0h+dwBufferLength], rax
0x1800e91d4  lea     rax, [rbp+0B0h+var_100]
0x1800e91d8  mov     [rsp+1B0h+lpdwIndex], rax
0x1800e91dd  xorps   xmm0, xmm0
0x1800e91e0  lea     rax, [rsp+1B0h+dwBufferLength]
0x1800e91e5  movups  [rbp+0B0h+var_E8+8], xmm0
0x1800e91e9  mov     edx, 33Fh
0x1800e91ee  mov     [rsp+1B0h+lpdwBufferLength], rax
0x1800e91f3  mov     word ptr [rbp+0B0h+var_E8+8], si
0x1800e91f7  mov     [rbp+0B0h+var_C8], rbx
0x1800e91fb  mov     [rbp+0B0h+var_D0], rsi
0x1800e91ff  mov     word ptr [rbp+0B0h+var_E8], r15w
0x1800e9204  mov     [rbp+0B0h+var_F8], r14
0x1800e9208  mov     [rbp+0B0h+var_100], r12
0x1800e920c  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x1800e9211  lea     rcx, [rbp+0B0h+var_E8+8]; void *
0x1800e9215  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e921a  jmp     loc_1800E9FDE
0x1800e921f  mov     [rsp+1B0h+var_170], 0Bh
0x1800e9224  add     rcx, 160h; this
0x1800e922b  mov     r8b, 1; bool
0x1800e922e  lea     rdx, [rsp+1B0h+var_170]; enum Mso::Http::HttpRequestWinTimings::TimingEvent *
0x1800e9233  call    ?SetTiming@HttpRequestWinTimings@Http@Mso@@QEAAXAEBW4TimingEvent@123@_N@Z; Mso::Http::HttpRequestWinTimings::SetTiming(Mso::Http::HttpRequestWinTimings::TimingEvent const &,bool)
0x1800e9238  jmp     loc_1800E9FDE
0x1800e923d  mov     ebx, 7
0x1800e9242  cmp     dword ptr [rcx+178h], 0FFFFFFFFh
0x1800e9249  jz      short loc_1800E9263
0x1800e924b  mov     [rsp+1B0h+var_170], bl
0x1800e924f  add     rcx, 160h; this
0x1800e9256  mov     r8b, 1; bool
0x1800e9259  lea     rdx, [rsp+1B0h+var_170]; enum Mso::Http::HttpRequestWinTimings::TimingEvent *
0x1800e925e  call    ?SetTiming@HttpRequestWinTimings@Http@Mso@@QEAAXAEBW4TimingEvent@123@_N@Z; Mso::Http::HttpRequestWinTimings::SetTiming(Mso::Http::HttpRequestWinTimings::TimingEvent const &,bool)
0x1800e9263  mov     [rsp+1B0h+var_170], 8
0x1800e9268  lea     rcx, [rdi+160h]; this
0x1800e926f  mov     r8b, 1; bool
0x1800e9272  lea     rdx, [rsp+1B0h+var_170]; enum Mso::Http::HttpRequestWinTimings::TimingEvent *
0x1800e9277  call    ?SetTiming@HttpRequestWinTimings@Http@Mso@@QEAAXAEBW4TimingEvent@123@_N@Z; Mso::Http::HttpRequestWinTimings::SetTiming(Mso::Http::HttpRequestWinTimings::TimingEvent const &,bool)
0x1800e927c  add     rdi, 50h ; 'P'
0x1800e9280  cmp     [rdi+18h], rbx
0x1800e9284  jbe     short loc_1800E9289
0x1800e9286  mov     rdi, [rdi]
0x1800e9289  lea     rax, aReceivedWinhtt_10; "Received WINHTTP_CALLBACK_STATUS_SENDIN"...
0x1800e9290  mov     ecx, 1E499612h
0x1800e9295  jmp     loc_1800E94FC
0x1800e929a  mov     [rsp+1B0h+var_170], 6
0x1800e929f  add     rcx, 160h; this
0x1800e92a6  mov     r8b, 1; bool
0x1800e92a9  lea     rdx, [rsp+1B0h+var_170]; enum Mso::Http::HttpRequestWinTimings::TimingEvent *
0x1800e92ae  call    ?SetTiming@HttpRequestWinTimings@Http@Mso@@QEAAXAEBW4TimingEvent@123@_N@Z; Mso::Http::HttpRequestWinTimings::SetTiming(Mso::Http::HttpRequestWinTimings::TimingEvent const &,bool)
0x1800e92b3  lea     rax, [rdi+50h]
0x1800e92b7  mov     ebx, 7
0x1800e92bc  cmp     [rax+18h], rbx
0x1800e92c0  jbe     short loc_1800E92C5
0x1800e92c2  mov     rax, [rax]
0x1800e92c5  lea     r12, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x1800e92cc  mov     [rbp+0B0h+var_100], r12
0x1800e92d0  lea     r14, aRequestid; "RequestId"
0x1800e92d7  mov     [rbp+0B0h+var_F8], r14
0x1800e92db  mov     [rbp+0B0h+var_F0], rax
0x1800e92df  mov     r15d, 100h
0x1800e92e5  mov     word ptr [rbp+0B0h+var_E8], r15w
0x1800e92ea  xorps   xmm0, xmm0
0x1800e92ed  movups  [rbp+0B0h+var_E8+8], xmm0
0x1800e92f1  xor     esi, esi
0x1800e92f3  mov     [rbp+0B0h+var_D0], rsi
0x1800e92f7  mov     [rbp+0B0h+var_C8], rbx
0x1800e92fb  mov     word ptr [rbp+0B0h+var_E8+8], si
0x1800e92ff  lea     rax, aReceivedWinhtt_12; "Received WINHTTP_CALLBACK_STATUS_CONNEC"...
0x1800e9306  mov     [rsp+1B0h+Buffer], rax
0x1800e930b  lea     rax, [rbp+0B0h+var_100]
0x1800e930f  mov     [rsp+1B0h+lpdwIndex], rax
0x1800e9314  lea     rax, [rsp+1B0h+Buffer]
0x1800e9319  mov     [rsp+1B0h+lpdwBufferLength], rax
0x1800e931e  mov     edx, 33Fh
0x1800e9323  mov     ecx, 1E499616h
0x1800e9328  lea     r8d, [rsi+64h]
0x1800e932c  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x1800e9331  lea     rcx, [rbp+0B0h+var_E8+8]; void *
0x1800e9335  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e933a  mov     qword ptr [rsp+1B0h+dwBufferLength], rsi
0x1800e933f  lea     rcx, [rdi+10h]
0x1800e9343  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x1800e9348  mov     r10, rax
0x1800e934b  mov     rcx, [rax]
0x1800e934e  mov     rax, [rcx+40h]
0x1800e9352  lea     r9, [rsp+1B0h+dwBufferLength]
0x1800e9357  lea     r8d, [rsi+0Ah]
0x1800e935b  lea     rdx, [rsp+1B0h+var_138]
0x1800e9360  mov     rcx, r10
0x1800e9363  call    cs:__guard_dispatch_icall_fptr
0x1800e9369  cmp     [rsp+1B0h+var_138], esi
0x1800e936d  jnz     loc_1800E9FDE
0x1800e9373  mov     rcx, qword ptr [rsp+1B0h+dwBufferLength]
0x1800e9378  test    rcx, rcx
0x1800e937b  jz      loc_1800E9FDE
0x1800e9381  mov     rax, [rcx]
0x1800e9384  mov     rax, [rax+20h]
0x1800e9388  jmp     loc_1800E947B
0x1800e938d  mov     [rsp+1B0h+var_170], 5
0x1800e9392  add     rcx, 160h; this
0x1800e9399  xor     r8d, r8d; bool
0x1800e939c  lea     rdx, [rsp+1B0h+var_170]; enum Mso::Http::HttpRequestWinTimings::TimingEvent *
0x1800e93a1  call    ?SetTiming@HttpRequestWinTimings@Http@Mso@@QEAAXAEBW4TimingEvent@123@_N@Z; Mso::Http::HttpRequestWinTimings::SetTiming(Mso::Http::HttpRequestWinTimings::TimingEvent const &,bool)
0x1800e93a6  lea     rax, [rdi+50h]
0x1800e93aa  mov     ebx, 7
0x1800e93af  cmp     [rax+18h], rbx
0x1800e93b3  jbe     short loc_1800E93B8
0x1800e93b5  mov     rax, [rax]
0x1800e93b8  lea     r12, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x1800e93bf  mov     [rbp+0B0h+var_100], r12
0x1800e93c3  lea     r14, aRequestid; "RequestId"
0x1800e93ca  mov     [rbp+0B0h+var_F8], r14
0x1800e93ce  mov     [rbp+0B0h+var_F0], rax
0x1800e93d2  mov     r15d, 100h
0x1800e93d8  mov     word ptr [rbp+0B0h+var_E8], r15w
0x1800e93dd  xorps   xmm0, xmm0
0x1800e93e0  movups  [rbp+0B0h+var_E8+8], xmm0
0x1800e93e4  xor     esi, esi
0x1800e93e6  mov     [rbp+0B0h+var_D0], rsi
0x1800e93ea  mov     [rbp+0B0h+var_C8], rbx
0x1800e93ee  mov     word ptr [rbp+0B0h+var_E8+8], si
0x1800e93f2  lea     rax, aReceivedWinhtt_9; "Received WINHTTP_CALLBACK_STATUS_CONNEC"...
0x1800e93f9  mov     [rsp+1B0h+Buffer], rax
0x1800e93fe  lea     rax, [rbp+0B0h+var_100]
0x1800e9402  mov     [rsp+1B0h+lpdwIndex], rax
0x1800e9407  lea     rax, [rsp+1B0h+Buffer]
0x1800e940c  mov     [rsp+1B0h+lpdwBufferLength], rax
0x1800e9411  mov     edx, 33Fh
0x1800e9416  mov     ecx, 1E499617h
0x1800e941b  lea     r8d, [rsi+64h]
0x1800e941f  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x1800e9424  lea     rcx, [rbp+0B0h+var_E8+8]; void *
  ... truncated ...
```
