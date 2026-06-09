# Mso::Http::CHttpRequest_WinHttp::sendInternal(IStream *,uchar const *,unsigned __int64)

- ea: `0x1800e5728`
- end: `0x1800e70c8`
- name: `?sendInternal@CHttpRequest_WinHttp@Http@Mso@@AEAA?AUResult@23@PEAUIStream@@PEBE_K@Z`
- size: `6560`
- prototype: ``
- caller_count: `2`
- callee_count: `48`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e5670`
- `0x1800e7100`

## callees

- `0x18000adf0`
- `0x18000ffb0`
- `0x180010a84`
- `0x180012bf8`
- `0x180014300`
- `0x18001c6b4`
- `0x18001c760`
- `0x1800258b4`
- `0x180025de8`
- `0x18002acd8`
- `0x18002fc08`
- `0x180034f50`
- `0x18003aa9c`
- `0x18003e690`
- `0x180052e28`
- `0x1800823c0`
- `0x1800829d8`
- `0x1800bca98`
- `0x1800ca488`
- `0x1800ca9e4`
- `0x1800cd884`
- `0x1800d0198`
- `0x1800d0970`
- `0x1800d1094`
- `0x1800d113c`
- `0x1800d1198`
- `0x1800d6e88`
- `0x1800da9a8`
- `0x1800dade8`
- `0x1800dd858`
- `0x1800dd8d8`
- `0x1800de0ac`
- `0x1800de508`
- `0x1800de698`
- `0x1800de83c`
- `0x1800deab0`
- `0x1800dee5c`
- `0x1800df030`
- `0x1800dfbf4`
- `0x1800e133c`
- `0x1800e13a4`
- `0x1800e1474`
- `0x1800e18a8`
- `0x1800e4d80`
- `0x1800e5728`
- `0x1800ef930`
- `0x1801058e4`
- `0x180146090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e5cb0`
- `KERNEL32!GetLastError` at `0x1800e60df`
- `KERNEL32!GetLastError` at `0x1800e619a`
- `KERNEL32!GetLastError` at `0x1800e6561`
- `KERNEL32!GetLastError` at `0x1800e687c`
- `KERNEL32!GetLastError` at `0x1800e6d2f`
- `KERNEL32!GetLastError` at `0x1800e5cb0`
- `KERNEL32!GetLastError` at `0x1800e60df`
- `KERNEL32!GetLastError` at `0x1800e619a`
- `KERNEL32!GetLastError` at `0x1800e6561`
- `KERNEL32!GetLastError` at `0x1800e687c`
- `KERNEL32!GetLastError` at `0x1800e6d2f`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800e6528`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800e6528`
- `WINHTTP!WinHttpWriteData` at `0x1800e6061`
- `WINHTTP!WinHttpWriteData` at `0x1800e6061`
- `WINHTTP!WinHttpSendRequest` at `0x1800e5c68`
- `WINHTTP!WinHttpSendRequest` at `0x1800e5c68`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800e673a`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800e673a`
- `WINHTTP!WinHttpQueryOption` at `0x1800e6d21`
- `WINHTTP!WinHttpQueryOption` at `0x1800e6d21`

## string_xrefs

- `0x1800e58bc`: `Request already aborted`
- `0x1800e596d`: `Request already sent`
- `0x1800e5a08`: `Request already not open`
- `0x1800e620c`: `BytesToWrite`
- `0x1800e62a5`: `Failed to read bytes from the stream into a temporary buffer`
- `0x1800e614b`: `WinHttpWriteData failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Mso::Http::CHttpRequest_WinHttp::sendInternal(
        __int64 a1,
        __int64 a2,
        Mso::Stream *a3,
        void *a4,
        unsigned __int64 a5)
{
  __int64 v7; // rax
  __int64 v8; // r8
  struct IMsoMemHeap *v9; // r8
  int inited; // eax
  __int64 v11; // rdx
  int v12; // r9d
  __int64 v13; // rbx
  _QWORD *v14; // rax
  __int64 result; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  char v19; // bl
  DWORD LastError; // r12d
  unsigned __int64 v21; // r13
  char v22; // al
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rbx
  _QWORD *v27; // rax
  int v28; // r9d
  __int64 v29; // rbx
  _QWORD *v30; // rax
  __int64 v31; // rax
  int v32; // edx
  int v33; // r8d
  int v34; // r9d
  struct IStream *v35; // rdx
  int v36; // eax
  int v37; // r9d
  __int64 v38; // rax
  int (__fastcall *v39)(Mso::Stream *, __int64, _QWORD, DWORD *); // rbx
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rbx
  _QWORD *v43; // rax
  __int64 v44; // rbx
  _QWORD *v45; // rax
  DWORD v46; // ebx
  const void *v47; // rax
  char v48; // bl
  __int64 v49; // rax
  int v50; // edx
  int v51; // r8d
  int v52; // r9d
  __int128 *v53; // rcx
  __int64 v54; // rax
  int v55; // edx
  int v56; // r8d
  int v57; // r9d
  __int64 v58; // r13
  _QWORD *v59; // rax
  __int64 v60; // rax
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // rbx
  _QWORD *v64; // rax
  __int64 v65; // rbx
  _QWORD *v66; // rax
  __int64 v67; // rax
  int v68; // edx
  int v69; // r8d
  int v70; // r9d
  Mso::Http::Flights *v71; // rcx
  __int64 v72; // r13
  _QWORD *v73; // rax
  __int64 v74; // r8
  bool v75; // zf
  int v76; // edx
  int v77; // r9d
  _QWORD *v78; // rax
  const struct IMsoUrl *v79; // r8
  Mso::Http::Flights *v80; // rcx
  int v81; // r13d
  __int64 v82; // rax
  __m128i v83; // xmm1
  _QWORD *v84; // rbx
  __int64 v85; // rax
  int v86; // edx
  int v87; // r8d
  int v88; // r9d
  __int64 v89; // rax
  __m128i v90; // xmm1
  Mso::Http::ConnectionDataUsage *v91; // r12
  __int64 v92; // rax
  int v93; // edx
  int v94; // r8d
  int v95; // r9d
  struct IRequest *v96; // rdx
  __int64 v97; // rax
  __int64 v98; // rdx
  void *v99; // rcx
  __int64 v100; // rbx
  _QWORD *v101; // rax
  DWORD v102; // eax
  __int64 v103; // rax
  int v104; // r8d
  int v105; // r9d
  _QWORD *v106; // rcx
  __int64 v107; // rbx
  __int64 v108; // r8
  const wchar_t *v109; // rdx
  __int64 v110; // rbx
  _QWORD *v111; // rax
  __int64 v112; // rbx
  _QWORD *v113; // rax
  __int64 v114; // rbx
  _QWORD *v115; // rax
  __int64 *v116; // rdx
  const OException *v117; // rcx
  __int64 v118; // rax
  _QWORD *v119; // rax
  unsigned int ReturnCode; // eax
  bool dwOptionalLength; // [rsp+20h] [rbp-6C8h]
  struct IRequest *dwTotalLength; // [rsp+28h] [rbp-6C0h]
  const struct IMsoUrl *dwContext; // [rsp+30h] [rbp-6B8h]
  char v124; // [rsp+50h] [rbp-698h]
  bool v125[8]; // [rsp+58h] [rbp-690h] BYREF
  char v126[8]; // [rsp+60h] [rbp-688h] BYREF
  DWORD dwNumberOfBytesWritten[2]; // [rsp+68h] [rbp-680h] BYREF
  DWORD dwNumberOfBytesToWrite; // [rsp+70h] [rbp-678h] BYREF
  _BYTE v129[8]; // [rsp+78h] [rbp-670h] BYREF
  __int64 v130; // [rsp+80h] [rbp-668h]
  _BYTE v131[8]; // [rsp+88h] [rbp-660h] BYREF
  char v132; // [rsp+90h] [rbp-658h]
  unsigned int v133; // [rsp+98h] [rbp-650h]
  Mso::Stream *Buffer; // [rsp+A0h] [rbp-648h] BYREF
  _BYTE v135[8]; // [rsp+A8h] [rbp-640h] BYREF
  __int64 v136; // [rsp+B0h] [rbp-638h]
  _BYTE v137[8]; // [rsp+B8h] [rbp-630h] BYREF
  char v138; // [rsp+C0h] [rbp-628h]
  unsigned int v139; // [rsp+C8h] [rbp-620h]
  Mso::Http::ConnectionDataUsage *v140[2]; // [rsp+D0h] [rbp-618h] BYREF
  __int64 v141; // [rsp+E0h] [rbp-608h]
  const char *v142; // [rsp+E8h] [rbp-600h] BYREF
  __int64 v143; // [rsp+F0h] [rbp-5F8h]
  _BYTE v144[16]; // [rsp+F8h] [rbp-5F0h] BYREF
  LPVOID lpOptional; // [rsp+108h] [rbp-5E0h]
  const OException *v146; // [rsp+110h] [rbp-5D8h] BYREF
  _QWORD v147[2]; // [rsp+118h] [rbp-5D0h] BYREF
  _BYTE v148[16]; // [rsp+128h] [rbp-5C0h] BYREF
  _QWORD v149[2]; // [rsp+138h] [rbp-5B0h] BYREF
  _BYTE v150[24]; // [rsp+148h] [rbp-5A0h] BYREF
  void **v151; // [rsp+160h] [rbp-588h] BYREF
  const char *v152; // [rsp+168h] [rbp-580h]
  _QWORD *v153; // [rsp+170h] [rbp-578h]
  _BYTE v154[24]; // [rsp+178h] [rbp-570h] BYREF
  __int64 v155; // [rsp+190h] [rbp-558h]
  __int64 v156; // [rsp+198h] [rbp-550h]
  IRequest v157; // [rsp+1A0h] [rbp-548h] BYREF
  const char *v158; // [rsp+1A8h] [rbp-540h]
  _QWORD *v159; // [rsp+1B0h] [rbp-538h]
  __int16 v160; // [rsp+1B8h] [rbp-530h]
  __int128 v161; // [rsp+1C0h] [rbp-528h] BYREF
  __int64 v162; // [rsp+1D0h] [rbp-518h]
  __int64 v163; // [rsp+1D8h] [rbp-510h]
  __int128 v164; // [rsp+200h] [rbp-4E8h] BYREF
  __int64 v165; // [rsp+210h] [rbp-4D8h]
  __int128 v166; // [rsp+218h] [rbp-4D0h] BYREF
  __int64 v167; // [rsp+228h] [rbp-4C0h]
  __int64 v168; // [rsp+230h] [rbp-4B8h]
  void **v169; // [rsp+240h] [rbp-4A8h] BYREF
  const char *v170; // [rsp+248h] [rbp-4A0h]
  DWORD v171; // [rsp+250h] [rbp-498h]
  __int16 v172; // [rsp+254h] [rbp-494h]
  __int128 v173; // [rsp+258h] [rbp-490h] BYREF
  __int64 v174; // [rsp+268h] [rbp-480h]
  __int64 v175; // [rsp+270h] [rbp-478h]
  _OWORD v176[2]; // [rsp+278h] [rbp-470h] BYREF
  _BYTE v177[96]; // [rsp+2A0h] [rbp-448h] BYREF
  void **v178; // [rsp+300h] [rbp-3E8h] BYREF
  __int64 v179; // [rsp+308h] [rbp-3E0h] BYREF

  lpOptional = a4;
  Buffer = a3;
  v142 = (const char *)a1;
  v143 = a2;
  v7 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)v176);
  Measurements::MeasureElapsedTime::MeasureElapsedTime(
    v129,
    Measurements::MeasurementId::HttpCall::HttpRequestSendInternal,
    v8,
    v7);
  CProcessMsoUrl::CProcessMsoUrl((CProcessMsoUrl *)&v178, *(const struct IMsoUrl **)(a1 + 32), v9);
  inited = CProcessMsoUrl::HrInitCanonicalForm((CProcessMsoUrl *)&v178);
  if ( inited < 0 )
  {
    Mso::Http::Results::SyntaxError(a2, v11, 42497628);
    CProcessMsoUrl::~CProcessMsoUrl((CProcessMsoUrl *)&v178);
    if ( v129[0] )
    {
      v13 = sub_1800CA488((unsigned __int16)v133);
      if ( v13 )
      {
        if ( v132 )
        {
          v14 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v131);
          sub_1800CA9E4(*v14, v13);
          v132 = 0;
        }
        sub_1800CD884(v133, 0);
        sub_1800CA9E4(v130, v13);
        v129[0] = 0;
      }
    }
    return a2;
  }
  if ( *(_BYTE *)(a1 + 26) )
  {
    v16 = (_QWORD *)(a1 + 80);
    if ( *(_QWORD *)(a1 + 104) > 7u )
      v16 = (_QWORD *)*v16;
    v152 = "RequestId";
    v153 = v16;
    *(_WORD *)v154 = 256;
    *(_OWORD *)&v154[8] = 0;
    v155 = 0;
    v156 = 7;
    *(_WORD *)&v154[8] = 0;
    v151 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
    *(_QWORD *)dwNumberOfBytesWritten = "Request already aborted";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
      508139017,
      v11,
      15,
      v12,
      (__int64)dwNumberOfBytesWritten,
      (__int64)&v151);
    std::wstring::~wstring(&v154[8]);
  }
  if ( *(_BYTE *)(a1 + 25) )
  {
    v17 = (_QWORD *)(a1 + 80);
    if ( *(_QWORD *)(a1 + 104) > 7u )
      v17 = (_QWORD *)*v17;
    v152 = "RequestId";
    v153 = v17;
    *(_WORD *)v154 = 256;
    *(_OWORD *)&v154[8] = 0;
    v155 = 0;
    v156 = 7;
    *(_WORD *)&v154[8] = 0;
    v151 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
    *(_QWORD *)dwNumberOfBytesWritten = "Request already sent";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
      508139016,
      v11,
      15,
      v12,
      (__int64)dwNumberOfBytesWritten,
      (__int64)&v151);
    std::wstring::~wstring(&v154[8]);
  }
  if ( !*(_BYTE *)(a1 + 24) )
  {
    v18 = (_QWORD *)(a1 + 80);
    if ( *(_QWORD *)(a1 + 104) > 7u )
      v18 = (_QWORD *)*v18;
    v152 = "RequestId";
    v153 = v18;
    *(_WORD *)v154 = 256;
    *(_OWORD *)&v154[8] = 0;
    v155 = 0;
    v156 = 7;
    *(_WORD *)&v154[8] = 0;
    v151 = &Mso::Http::Logging::Structured::FirstScheme::`vftable';
    *(_QWORD *)dwNumberOfBytesWritten = "Request already not open";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
      508139015,
      v11,
      15,
      v12,
      (__int64)dwNumberOfBytesWritten,
      (__int64)&v151);
    std::wstring::~wstring(&v154[8]);
  }
  try
  {
    if ( *(_BYTE *)(a1 + 25) || !*(_BYTE *)(a1 + 24) || *(_BYTE *)(a1 + 26) )
    {
      Mso::Http::Results::InvalidStateError(a2, v11, 42497629);
      CProcessMsoUrl::~CProcessMsoUrl((CProcessMsoUrl *)&v178);
      if ( v129[0] )
      {
        v112 = sub_1800CA488((unsigned __int16)v133);
        if ( v112 )
        {
          if ( v132 )
          {
            v113 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v131);
            sub_1800CA9E4(*v113, v112);
            v132 = 0;
          }
          sub_1800CD884(v133, 0);
          sub_1800CA9E4(v130, v112);
          v129[0] = 0;
        }
      }
      return a2;
    }
    v124 = 0;
    v19 = 0;
    LastError = 0;
    v176[0] = 0;
    v176[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v176[0]) = 0;
    Mso::Http::CHttpRequest_WinHttp::processRequestSettings((Mso::Http::CHttpRequest_WinHttp *)a1);
    Mso::Http::HttpRequestTelemetry::Start((Mso::Http::HttpRequestTelemetry *)(a1 + 320));
    Mso::Http::HttpRequestTelemetry::Start((Mso::Http::HttpRequestTelemetry *)(a1 + 400));
    v21 = a5;
    *(_BYTE *)(a1 + 480) = a5 != 0;
LABEL_24:
    v22 = v124;
    while ( !v22 )
    {
      v23 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)&v164);
      Measurements::MeasureElapsedTime::MeasureElapsedTime(
        v135,
        Measurements::MeasurementId::HttpCall::HttpRequestSendInternalSendingRequest,
        v24,
        v23);
      std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v148, a1 + 232);
      if ( !*(_QWORD *)(a1 + 120) )
      {
        Mso::Http::Results::InvalidStateError(a2, v25, 42497630);
        std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v148);
        if ( v135[0] )
        {
          v26 = sub_1800CA488((unsigned __int16)v139);
          if ( v26 )
          {
            if ( v138 )
            {
              v27 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v137);
              sub_1800CA9E4(*v27, v26);
              v138 = 0;
            }
            sub_1800CD884(v139, 0);
            sub_1800CA9E4(v136, v26);
            v135[0] = 0;
          }
        }
        std::wstring::~wstring(v176);
        CProcessMsoUrl::~CProcessMsoUrl((CProcessMsoUrl *)&v178);
        if ( v129[0] )
        {
          v29 = sub_1800CA488((unsigned __int16)v133);
          if ( v29 )
          {
            if ( v132 )
            {
              v30 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v131);
              sub_1800CA9E4(*v30, v29);
              v132 = 0;
            }
            sub_1800CD884(v133, 0);
            sub_1800CA9E4(v130, v29);
            v129[0] = 0;
          }
        }
        return a2;
      }
      Mso::Http::Details::ResourceUsageNetworkMonitorTemplate<Mso::Http::Details::NetworkUsageProductionBase>::ReportRequestStart(a1 + 184);
      if ( v21 > 0xFFFFFFFF )
        __fastfail(5u);
      if ( WinHttpSendRequest(*(HINTERNET *)(a1 + 120), 0, 0, lpOptional, v21, v21, 0) )
      {
        v19 = 1;
        *(_DWORD *)(a1 + 200) += v21;
        std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(
          v147,
          a1 + 168);
        *(_DWORD *)(v147[0] + 16LL) += v21;
        std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v147);
      }
      else
      {
        v19 = 0;
        LastError = GetLastError();
        *((_QWORD *)&v164 + 1) = "SH_ErrorCode";
        LODWORD(v165) = LastError;
        WORD2(v165) = 4;
        v166 = 0;
        v167 = 0;
        v168 = 7;
        LOWORD(v166) = 0;
        *(_QWORD *)&v164 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
        v31 = Mso::Http::Logging::Structured::Url::Url(&v157);
        *(_QWORD *)dwNumberOfBytesWritten = "WinHttpSendRequest failed";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result,Mso::Http::Logging::Structured::RequestId>(
          17126301,
          v32,
          v33,
          v34,
          (__int64)dwNumberOfBytesWritten,
          v31,
          (__int64)&v164);
        Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(&v157);
        std::wstring::~wstring(&v166);
      }
      std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v148);
      if ( v19 && Buffer && v21 )
      {
        v36 = Mso::Stream::RewindStream(Buffer, v35);
        if ( v36 < 0 )
        {
          v152 = "HRESULT";
          LODWORD(v153) = v36;
          memset(v154, 0, sizeof(v154));
          v155 = 7;
          *(_WORD *)v154 = 0;
          LOWORD(v156) = 4;
          v151 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
          *(_QWORD *)dwNumberOfBytesWritten = "HttpWin sendInternal: MsoRewindStream failed";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
            18957960,
            831,
            15,
            v37,
            (__int64)dwNumberOfBytesWritten,
            (__int64)&v151);
          std::wstring::~wstring(v154);
        }
        v164 = 0;
        v165 = 0;
        _mm_lfence();
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v164);
        while ( 1 )
        {
          dwNumberOfBytesToWrite = 0;
          dwNumberOfBytesWritten[0] = 0;
          v38 = 0x2000;
          if ( v21 < 0x2000 )
            v38 = v21;
          *(_QWORD *)v125 = v38;
          v39 = *(int (__fastcall **)(Mso::Stream *, __int64, _QWORD, DWORD *))(*(_QWORD *)Buffer + 24LL);
          v40 = std::vector<unsigned char>::operator[](&v164, 0);
          if ( v39(Buffer, v40, *(unsigned int *)v125, &dwNumberOfBytesToWrite) < 0 )
            break;
          v19 = 1;
          if ( !dwNumberOfBytesToWrite )
            goto LABEL_74;
          v21 -= dwNumberOfBytesToWrite;
          std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v150, a1 + 232);
          if ( !*(_QWORD *)(a1 + 120) )
          {
            Mso::Http::Results::InvalidStateError(a2, v41, 42497631);
            std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v150);
            std::vector<unsigned char>::~vector<unsigned char>(&v164);
            if ( v135[0] )
            {
              v42 = sub_1800CA488((unsigned __int16)v139);
              if ( v42 )
              {
                if ( v138 )
                {
                  v43 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v137);
                  sub_1800CA9E4(*v43, v42);
                  v138 = 0;
                }
                sub_1800CD884(v139, 0);
                sub_1800CA9E4(v136, v42);
                v135[0] = 0;
              }
            }
            std::wstring::~wstring(v176);
            CProcessMsoUrl::~CProcessMsoUrl((CProcessMsoUrl *)&v178);
            if ( v129[0] )
            {
              v44 = sub_1800CA488((unsigned __int16)v133);
              if ( v44 )
              {
                if ( v132 )
                {
                  v45 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v131);
                  sub_1800CA9E4(*v45, v44);
                  v132 = 0;
                }
                sub_1800CD884(v133, 0);
                sub_1800CA9E4(v130, v44);
                v129[0] = 0;
              }
            }
            return a2;
          }
          v46 = dwNumberOfBytesToWrite;
          v47 = (const void *)std::vector<unsigned char>::operator[](&v164, 0);
          if ( WinHttpWriteData(*(HINTERNET *)(a1 + 120), v47, v46, dwNumberOfBytesWritten) )
          {
            v48 = 1;
            *(_DWORD *)(a1 + 200) += dwNumberOfBytesWritten[0];
            std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(
              v149,
              a1 + 168);
            *(_DWORD *)(v149[0] + 16LL) += dwNumberOfBytesWritten[0];
            std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v149);
          }
          else
          {
            v48 = 0;
          }
          std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v150);
          if ( !v48 || dwNumberOfBytesToWrite != dwNumberOfBytesWritten[0] )
          {
            v19 = 0;
            LastError = GetLastError();
            v170 = "SH_ErrorCode";
            v171 = LastError;
            v172 = 4;
            v173 = 0;
            v174 = 0;
            v175 = 7;
            LOWORD(v173) = 0;
            v169 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
            v49 = Mso::Http::Logging::Structured::Url::Url(&v157);
            *(_QWORD *)v125 = "WinHttpWriteData failed";
            Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result,Mso::Http::Logging::Structured::RequestId>(
              9208016,
              v50,
              v51,
              v52,
              (__int64)v125,
              v49,
              (__int64)&v169);
            Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(&v157);
            v53 = &v173;
LABEL_75:
            std::wstring::~wstring(v53);
LABEL_76:
            std::vector<unsigned char>::~vector<unsigned char>(&v164);
            goto LABEL_77;
          }
          v19 = 1;
          if ( !v21 )
            goto LABEL_76;
        }
        v19 = 0;
LABEL_74:
        LastError = GetLastError();
        v152 = "SH_ErrorCode";
        LODWORD(v153) = LastError;
        WORD2(v153) = 4;
        memset(v154, 0, sizeof(v154));
        v155 = 7;
        *(_WORD *)v154 = 0;
        v151 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
        v157.lpVtbl = (struct IRequestVtbl *)&Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>::`vftable';
        v158 = "BytesToWrite";
        v159 = (_QWORD *)dwNumberOfBytesToWrite;
        v160 = 4;
        v161 = 0;
        v162 = 0;
        v163 = 7;
        LOWORD(v161) = 0;
        v169 = &Mso::Diagnostics::ClassifiedStructuredObject<bool>::`vftable';
        v170 = "fSuccess";
        LOBYTE(v171) = v19;
        HIWORD(v171) = 4;
        v173 = 0;
        v174 = 0;
        v175 = 7;
        LOWORD(v173) = 0;
        v54 = Mso::Http::Logging::Structured::Url::Url(v177);
        *(_QWORD *)v125 = "Failed to read bytes from the stream into a temporary buffer";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Url,Mso::Diagnostics::ClassifiedStructuredObject<bool>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned __int64>,Mso::Diagnostics::ClassifiedStructuredErrorCode>(
          (unsigned int)&v169,
          v55,
          v56,
          v57,
          (__int64)v125,
          v54,
          (__int64)&v169,
          (__int64)&v157,
          (__int64)&v151);
        Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(v177);
        std::wstring::~wstring(&v173);
        std::wstring::~wstring(&v161);
        v53 = (__int128 *)v154;
        goto LABEL_75;
      }
LABEL_77:
      if ( v135[0] )
      {
        v58 = sub_1800CA488((unsigned __int16)v139);
        if ( v58 )
        {
          if ( v138 )
          {
            v59 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v137);
            sub_1800CA9E4(*v59, v58);
            v138 = 0;
          }
          sub_1800CD884(v139, 0);
          sub_1800CA9E4(v136, v58);
        }
      }
      if ( !v19 )
        goto LABEL_187;
      v60 = Measurements::Stopwatch::Stopwatch((Measurements::Stopwatch *)&v164);
      Measurements::MeasureElapsedTime::MeasureElapsedTime(
        v135,
        Measurements::MeasurementId::HttpCall::HttpRequestSendInternalReceivingResponse,
        v61,
        v60);
      std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v144, a1 + 232);
      if ( !*(_QWORD *)(a1 + 120) )
      {
        Mso::Http::Results::InvalidStateError(a2, v62, 42497632);
        std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v144);
        if ( v135[0] )
        {
          v63 = sub_1800CA488((unsigned __int16)v139);
          if ( v63 )
          {
            if ( v138 )
            {
              v64 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v137);
              sub_1800CA9E4(*v64, v63);
              v138 = 0;
            }
            sub_1800CD884(v139, 0);
            sub_1800CA9E4(v136, v63);
            v135[0] = 0;
          }
        }
        std::wstring::~wstring(v176);
        CProcessMsoUrl::~CProcessMsoUrl((CProcessMsoUrl *)&v178);
        if ( v129[0] )
        {
          v65 = sub_1800CA488((unsigned __int16)v133);
          if ( v65 )
          {
            if ( v132 )
            {
              v66 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v131);
              sub_1800CA9E4(*v66, v65);
              v132 = 0;
            }
            sub_1800CD884(v133, 0);
            sub_1800CA9E4(v130, v65);
            v129[0] = 0;
          }
        }
        return a2;
      }
      std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(
        v140,
        a1 + 168);
      Mso::Http::ConnectionDataUsage::EndRoundtrip(v140[0]);
      std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v140);
      if ( WinHttpReceiveResponse(*(HINTERNET *)(a1 + 120), 0) )
      {
        v19 = 1;
        v126[0] = 9;
        Mso::Http::HttpRequestWinTimings::SetTiming(
          (Mso::Http::HttpRequestWinTimings *)(a1 + 320),
          (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v126,
          1);
        Mso::Http::Details::ResourceUsageNetworkMonitorTemplate<Mso::Http::Details::NetworkUsageProductionBase>::ReportResponseReceived(a1 + 184);
      }
      else
      {
        v19 = 0;
        LastError = GetLastError();
        v152 = "SH_ErrorCode";
        LODWORD(v153) = LastError;
        WORD2(v153) = 4;
        memset(v154, 0, sizeof(v154));
        v155 = 7;
        *(_WORD *)v154 = 0;
        v151 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
        v67 = Mso::Http::Logging::Structured::Url::Url(v177);
        *(_QWORD *)v125 = "WinHttpReceiveResponse failed";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result,Mso::Http::Logging::Structured::RequestId>(
          9208017,
          v68,
          v69,
          v70,
          (__int64)v125,
          v67,
          (__int64)&v151);
        Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(v177);
        std::wstring::~wstring(v154);
      }
      std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v144);
      if ( v135[0] )
      {
        v72 = sub_1800CA488((unsigned __int16)v139);
        if ( v72 )
        {
          if ( v138 )
          {
            v73 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v137);
            sub_1800CA9E4(*v73, v72);
            v138 = 0;
          }
          sub_1800CD884(v139, 0);
          sub_1800CA9E4(v136, v72);
        }
      }
      if ( !v19 )
      {
LABEL_187:
        v21 = a5;
        v22 = v124;
        if ( LastError == 12032 )
          continue;
        if ( Mso::Http::Util::IsKnownProxyError((Mso::Http::Util *)LastError, (unsigned int)v35) )
        {
          v74 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(a1 + 8);
          v75 = (*(unsigned __int8 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v74 + 72LL))(v74, v176) == 0;
          v22 = v124;
          if ( !v75 )
            continue;
        }
      }
      if ( Mso::Http::Flights::IsRetryWithNtlmEnabled(v71) )
      {
        if ( *(_BYTE *)(a1 + 165) )
        {
          if ( v19 )
          {
            dwNumberOfBytesWritten[0] = 0;
            dwNumberOfBytesToWrite = 4;
            if ( WinHttpQueryHeaders(
                   *(HINTERNET *)(a1 + 120),
                   0x20000013u,
                   0,
                   dwNumberOfBytesWritten,
                   &dwNumberOfBytesToWrite,
                   0) )
            {
              if ( dwNumberOfBytesWritten[0] == 401 )
              {
                v78 = (_QWORD *)(a1 + 80);
                if ( *(_QWORD *)(a1 + 104) > 7u )
                  v78 = (_QWORD *)*v78;
                v158 = "RequestId";
                v159 = v78;
                v160 = 256;
                v161 = 0;
                v162 = 0;
                v163 = 7;
                LOWORD(v161) = 0;
                v157.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
                *(_QWORD *)v125 = "Got 401 response with Negotiate AuthScheme.  Retrying the request with NTLM";
                Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
                  42497633,
                  v76,
                  15,
                  v77,
                  (__int64)v125,
                  (__int64)&v157);
                std::wstring::~wstring(&v161);
                Mso::Http::CHttpRequest_WinHttp_Base::RetryWithNtlm(
                  (Mso::Http::CHttpRequest_WinHttp_Base *)a1,
                  *(void **)(a1 + 120),
                  v79);
                *(_BYTE *)(a1 + 165) = 0;
                v21 = a5;
                goto LABEL_24;
              }
            }
          }
        }
      }
      v22 = 1;
      v124 = 1;
      v21 = a5;
    }
    if ( v19 )
    {
      v126[0] = 10;
      Mso::Http::HttpRequestWinTimings::SetTiming(
        (Mso::Http::HttpRequestWinTimings *)(a1 + 320),
        (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v126,
        1);
    }
    *(_BYTE *)(a1 + 25) = v19;
    Mso::Http::CHttpRequest_WinHttp_Base::SetHttpProtocolUsed((Mso::Http::CHttpRequest_WinHttp_Base *)a1);
    v81 = 0;
    LODWORD(v140[0]) = 0;
    v140[1] = 0;
    LODWORD(v141) = 0;
    if ( *(_BYTE *)(a1 + 25) )
    {
      v91 = 0;
    }
    else
    {
      if ( !LastError )
        LastError = GetLastError();
      v82 = Mso::Http::ConvertDwToResult(&v164, LastError, 42497634);
      v83 = *(__m128i *)v82;
      v165 = *(_QWORD *)(v82 + 16);
      v81 = _mm_cvtsi128_si32(v83);
      LODWORD(v140[0]) = v81;
      v140[1] = (Mso::Http::ConnectionDataUsage *)_mm_srli_si128(v83, 8).m128i_u64[0];
      LODWORD(v141) = v165;
      v84 = (_QWORD *)(a1 + 80);
      if ( v81 )
      {
        v152 = "SH_ErrorCode";
        LODWORD(v153) = LastError;
        WORD2(v153) = 4;
        memset(v154, 0, sizeof(v154));
        v155 = 7;
        *(_WORD *)v154 = 0;
        v151 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
        v92 = Mso::Http::Logging::Structured::Url::Url(v177);
        if ( *(_QWORD *)(a1 + 104) > 7u )
          v84 = (_QWORD *)*v84;
        v158 = "RequestId";
        v159 = v84;
        v160 = 256;
        v161 = 0;
        v162 = 0;
        v163 = 7;
        LOWORD(v161) = 0;
        v157.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
        *(_QWORD *)v125 = "Failed to send request";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::RequestId,Mso::Http::Logging::Structured::Url,Mso::Diagnostics::ClassifiedStructuredErrorCode>(
          6062242,
          v93,
          v94,
          v95,
          (__int64)v125,
          (__int64)&v157,
          v92,
          (__int64)&v151);
        std::wstring::~wstring(&v161);
        Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(v177);
        std::wstring::~wstring(v154);
        v91 = v140[1];
      }
      else
      {
        v85 = Mso::Http::Logging::Structured::Url::Url(v177);
        if ( *(_QWORD *)(a1 + 104) > 7u )
          v84 = (_QWORD *)*v84;
        v158 = "RequestId";
        v159 = v84;
        v160 = 256;
        v161 = 0;
        v162 = 0;
        v163 = 7;
        LOWORD(v161) = 0;
        v157.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
        v152 = "SH_ErrorCode";
        LODWORD(v153) = LastError;
        WORD2(v153) = 4;
        memset(v154, 0, sizeof(v154));
        v155 = 7;
        *(_WORD *)v154 = 0;
        v151 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
        *(_QWORD *)v125 = "The request failed to send, but GetLastError returned Result::OK!";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredErrorCode,Mso::Http::Logging::Structured::RequestId,Mso::Http::Logging::Structured::Url>(
          (unsigned int)"The request failed to send, but GetLastError returned Result::OK!",
          v86,
          v87,
          v88,
          (__int64)v125,
          (__int64)&v151,
          (__int64)&v157,
          v85);
        std::wstring::~wstring(v154);
        std::wstring::~wstring(&v161);
        Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(v177);
        v89 = Mso::Http::Results::InternalError(&v164, LastError, 42497635);
        v90 = *(__m128i *)v89;
        v165 = *(_QWORD *)(v89 + 16);
        v81 = _mm_cvtsi128_si32(v90);
        LODWORD(v140[0]) = v81;
        v91 = (Mso::Http::ConnectionDataUsage *)_mm_srli_si128(v90, 8).m128i_u64[0];
        v140[1] = v91;
        LODWORD(v141) = v165;
      }
    }
    if ( *(_BYTE *)(a1 + 25) )
    {
      dwNumberOfBytesWritten[0] = 0;
      (*(void (__fastcall **)(__int64, __int128 *, DWORD *))(*(_QWORD *)a1 + 88LL))(a1, &v164, dwNumberOfBytesWritten);
      if ( dwNumberOfBytesWritten[0] == 302 )
      {
        if ( byte_18021CBB8 )
          Mso::Http::HandleRedirectTelemetry((Mso::Http *)a1, v96);
      }
    }
    if ( !Mso::Http::Flights::ShouldUseReauthRequestProxy(v80)
      && *(_BYTE *)(a1 + 25)
      && (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 248LL))(a1) )
    {
      v97 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 248LL))(a1);
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v97 + 40LL))(
        v97,
        *(_QWORD *)(a1 + 40),
        *(_QWORD *)(a1 + 32),
        a1);
    }
    if ( v81 == 7 )
    {
      Buffer = 0;
      std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v144, a1 + 232);
      v99 = *(void **)(a1 + 120);
      if ( !v99 )
      {
        Mso::Http::Results::InvalidStateError(a2, v98, 42497664);
        std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v144);
        std::wstring::~wstring(v176);
        CProcessMsoUrl::~CProcessMsoUrl((CProcessMsoUrl *)&v178);
        if ( v129[0] )
        {
          v100 = sub_1800CA488((unsigned __int16)v133);
          if ( v100 )
          {
            if ( v132 )
            {
              v101 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v131);
              sub_1800CA9E4(*v101, v100);
              v132 = 0;
            }
            sub_1800CD884(v133, 0);
            sub_1800CA9E4(v130, v100);
            v129[0] = 0;
          }
        }
        return a2;
      }
      dwNumberOfBytesWritten[0] = 8;
      if ( !WinHttpQueryOption(v99, 0x4Eu, &Buffer, dwNumberOfBytesWritten) )
      {
        v102 = GetLastError();
        v152 = "SH_ErrorCode";
        LODWORD(v153) = v102;
        WORD2(v153) = 4;
        memset(v154, 0, sizeof(v154));
        v155 = 7;
        *(_WORD *)v154 = 0;
        v151 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
        v103 = Mso::Http::Logging::Structured::Url::Url(v177);
        v106 = (_QWORD *)(a1 + 80);
        if ( *(_QWORD *)(a1 + 104) > 7u )
          v106 = (_QWORD *)*v106;
        v158 = "RequestId";
        v159 = v106;
        v160 = 256;
        v161 = 0;
        v162 = 0;
        v163 = 7;
        LOWORD(v161) = 0;
        v157.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
        *(_QWORD *)v125 = "An error occurred while querying for the Server Certification Context";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::RequestId,Mso::Http::Logging::Structured::Url,Mso::Diagnostics::ClassifiedStructuredErrorCode>(
          18093123,
          (unsigned int)"RequestId",
          v104,
          v105,
          (__int64)v125,
          (__int64)&v157,
          v103,
          (__int64)&v151);
        std::wstring::~wstring(&v161);
        Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(v177);
        std::wstring::~wstring(v154);
      }
      std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v144);
      if ( Buffer )
      {
        Mso::Make<Mso::Http::CCertificateContext_Win,Mso::Http::CCertificateContext_Win,_CERT_CONTEXT const * &>(
          v125,
          &Buffer);
        v107 = *(_QWORD *)v125;
        if ( *(_QWORD *)v125 )
        {
          v108 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(a1 + 8);
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v108 + 40LL))(v108, v107);
        }
        if ( v107 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v107 + 8LL))(v107);
      }
    }
    *(_DWORD *)(a1 + 56) = v81;
    *(_QWORD *)(a1 + 64) = v91;
    *(_DWORD *)(a1 + 72) = v141;
    if ( v81 == 7 )
      v140[1] = (Mso::Http::ConnectionDataUsage *)*(int *)(a1 + 484);
    v109 = (const wchar_t *)(a1 + 80);
    if ( *(_QWORD *)(a1 + 104) > 7u )
      v109 = *(const wchar_t **)v109;
    Mso::Http::HttpRequestWinTimings::EmitTimingsReport(
      (Mso::Http::HttpRequestWinTimings *)(a1 + 320),
      v109,
      (const struct Mso::Http::Result *)(a1 + 56),
      0,
      dwOptionalLength,
      dwTotalLength,
      dwContext);
    *(_OWORD *)a2 = *(_OWORD *)v140;
    *(_QWORD *)(a2 + 16) = v141;
    std::wstring::~wstring(v176);
    CProcessMsoUrl::~CProcessMsoUrl((CProcessMsoUrl *)&v178);
    if ( v129[0] )
    {
      v110 = sub_1800CA488((unsigned __int16)v133);
      if ( v110 )
      {
        if ( v132 )
        {
          v111 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v131);
          sub_1800CA9E4(*v111, v110);
          v132 = 0;
        }
        sub_1800CD884(v133, 0);
        sub_1800CA9E4(v130, v110);
        v129[0] = 0;
      }
    }
    result = a2;
  }
  catch ( const OException *v146 )
  {
    v178 = &Mso::Diagnostics::ToClassifiedStructured<OException>::`vftable';
    v117 = v146;
    v116 = &v179;
    v118 = 7;
    do
    {
      *(_OWORD *)v116 = *(_OWORD *)v117;
      *((_OWORD *)v116 + 1) = *((_OWORD *)v117 + 1);
      *((_OWORD *)v116 + 2) = *((_OWORD *)v117 + 2);
      *((_OWORD *)v116 + 3) = *((_OWORD *)v117 + 3);
      *((_OWORD *)v116 + 4) = *((_OWORD *)v117 + 4);
      *((_OWORD *)v116 + 5) = *((_OWORD *)v117 + 5);
      *((_OWORD *)v116 + 6) = *((_OWORD *)v117 + 6);
      v116 += 16;
      *((_OWORD *)v116 - 1) = *((_OWORD *)v117 + 7);
      v117 = (const OException *)((char *)v117 + 128);
      --v118;
    }
    while ( v118 );
    *v116 = *(_QWORD *)v117;
    *((_DWORD *)v116 + 2) = *((_DWORD *)v117 + 2);
    v119 = v142 + 80;
    if ( *((_QWORD *)v142 + 13) > 7u )
      v119 = (_QWORD *)*v119;
    v158 = "RequestId";
    v159 = v119;
    v160 = 256;
    v161 = 0;
    v162 = 0;
    v163 = 7;
    LOWORD(v161) = 0;
    v157.lpVtbl = (struct IRequestVtbl *)&Mso::Http::Logging::Structured::FirstScheme::`vftable';
    v142 = "Failed to send WinHttp request";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::RequestId,Mso::Http::Logging::Structured::Url>(
      6062243,
      (_DWORD)v116,
      15,
      v28,
      (__int64)&v142,
      (__int64)&v157,
      (__int64)&v178);
    std::wstring::~wstring(&v161);
    ReturnCode = OException::get_ReturnCode(v146);
    Mso::Http::ConvertDwToResult(v143, ReturnCode, 42497665);
    if ( v129[0] )
    {
      v114 = sub_1800CA488((unsigned __int16)v133);
      if ( v114 )
      {
        if ( v132 )
        {
          v115 = (_QWORD *)std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(v131);
          sub_1800CA9E4(*v115, v114);
          v132 = 0;
        }
        sub_1800CD884(v133, 0);
        sub_1800CA9E4(v130, v114);
      }
    }
    return v143;
  }
  return result;
}

```

## disassembly

```asm
0x1800e5728  push    rbx
0x1800e572a  push    rsi
0x1800e572b  push    rdi
0x1800e572c  push    r12
0x1800e572e  push    r13
0x1800e5730  push    r14
0x1800e5732  push    r15
0x1800e5734  sub     rsp, 6B0h
0x1800e573b  mov     rax, cs:__security_cookie
0x1800e5742  xor     rax, rsp
0x1800e5745  mov     [rsp+6E8h+var_48], rax
0x1800e574d  mov     [rsp+6E8h+lpOptional], r9
0x1800e5755  mov     [rsp+6E8h+Buffer], r8
0x1800e575d  mov     r15, rdx
0x1800e5760  mov     rsi, rcx
0x1800e5763  mov     [rsp+6E8h+var_600], rcx
0x1800e576b  mov     [rsp+6E8h+var_5F8], rdx
0x1800e5773  lea     rcx, [rsp+6E8h+var_470]; this
0x1800e577b  call    ??0Stopwatch@Measurements@@QEAA@XZ; Measurements::Stopwatch::Stopwatch(void)
0x1800e5780  mov     r9, rax
0x1800e5783  mov     edx, cs:?HttpRequestSendInternal@HttpCall@MeasurementId@Measurements@@3UMeasurementIdType@3@B; Measurements::MeasurementIdType const Measurements::MeasurementId::HttpCall::HttpRequestSendInternal
0x1800e5789  lea     rcx, [rsp+6E8h+var_670]
0x1800e578e  call    ??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z; Measurements::MeasureElapsedTime::MeasureElapsedTime(Measurements::MeasurementIdType,bool,Measurements::Stopwatch &&)
0x1800e5793  mov     rdx, [rsi+20h]; struct IMsoUrl *
0x1800e5797  lea     rcx, [rsp+6E8h+var_3E8]; this
0x1800e579f  call    ??0CProcessMsoUrl@@QEAA@AEBUIMsoUrl@@PEAUIMsoMemHeap@@@Z; CProcessMsoUrl::CProcessMsoUrl(IMsoUrl const &,IMsoMemHeap *)
0x1800e57a4  lea     rcx, [rsp+6E8h+var_3E8]; this
0x1800e57ac  call    ?HrInitCanonicalForm@CProcessMsoUrl@@QEAAJXZ; CProcessMsoUrl::HrInitCanonicalForm(void)
0x1800e57b1  xor     edi, edi
0x1800e57b3  test    eax, eax
0x1800e57b5  jns     loc_1800E5847
0x1800e57bb  mov     r8d, 288765Ch
0x1800e57c1  mov     rcx, r15
0x1800e57c4  call    ?SyntaxError@Results@Http@Mso@@YA?AUResult@23@_JI@Z; Mso::Http::Results::SyntaxError(__int64,uint)
0x1800e57c9  lea     rcx, [rsp+6E8h+var_3E8]; this
0x1800e57d1  call    ??1CProcessMsoUrl@@UEAA@XZ; CProcessMsoUrl::~CProcessMsoUrl(void)
0x1800e57d6  cmp     [rsp+6E8h+var_670], dil
0x1800e57db  jz      short loc_1800E583F
0x1800e57dd  movzx   ecx, word ptr [rsp+6E8h+var_650]
0x1800e57e5  call    sub_1800CA488
0x1800e57ea  mov     rbx, rax
0x1800e57ed  test    rax, rax
0x1800e57f0  jz      short loc_1800E583F
0x1800e57f2  cmp     [rsp+6E8h+var_658], dil
0x1800e57fa  jz      short loc_1800E581C
0x1800e57fc  lea     rcx, [rsp+6E8h+var_660]
0x1800e5804  call    ??D?$_Optional_construct_base@V?$time_point@Ufiletime_clock@Chrono@Mso@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@std@@QEGBAAEBV?$time_point@Ufiletime_clock@Chrono@Mso@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@1@XZ; std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(void)
0x1800e5809  mov     rdx, rbx
0x1800e580c  mov     rcx, [rax]
0x1800e580f  call    sub_1800CA9E4
0x1800e5814  mov     [rsp+6E8h+var_658], dil
0x1800e581c  xor     edx, edx
0x1800e581e  mov     ecx, [rsp+6E8h+var_650]
0x1800e5825  call    sub_1800CD884
0x1800e582a  mov     rdx, rbx
0x1800e582d  mov     rcx, [rsp+6E8h+var_668]
0x1800e5835  call    sub_1800CA9E4
0x1800e583a  mov     [rsp+6E8h+var_670], dil
0x1800e583f  mov     rax, r15
0x1800e5842  jmp     loc_1800E70A5
0x1800e5847  mov     r14d, 7
0x1800e584d  cmp     [rsi+1Ah], dil
0x1800e5851  jz      loc_1800E58FE
0x1800e5857  lea     rax, [rsi+50h]
0x1800e585b  cmp     [rax+18h], r14
0x1800e585f  jbe     short loc_1800E5864
0x1800e5861  mov     rax, [rax]
0x1800e5864  lea     rbx, aRequestid; "RequestId"
0x1800e586b  mov     [rsp+6E8h+var_580], rbx
0x1800e5873  mov     [rsp+6E8h+var_578], rax
0x1800e587b  mov     r13d, 100h
0x1800e5881  mov     word ptr [rsp+6E8h+var_570], r13w
0x1800e588a  xorps   xmm0, xmm0
0x1800e588d  movups  [rsp+6E8h+var_570+8], xmm0
0x1800e5895  mov     [rsp+6E8h+var_558], rdi
0x1800e589d  mov     [rsp+6E8h+var_550], r14
0x1800e58a5  mov     word ptr [rsp+6E8h+var_570+8], di
0x1800e58ad  lea     r12, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x1800e58b4  mov     [rsp+6E8h+var_588], r12
0x1800e58bc  lea     rax, aRequestAlready_1; "Request already aborted"
0x1800e58c3  mov     qword ptr [rsp+6E8h+dwNumberOfBytesWritten], rax
0x1800e58c8  lea     rax, [rsp+6E8h+var_588]
0x1800e58d0  mov     qword ptr [rsp+6E8h+dwTotalLength], rax
0x1800e58d5  lea     rax, [rsp+6E8h+dwNumberOfBytesWritten]
0x1800e58da  mov     qword ptr [rsp+6E8h+dwOptionalLength], rax
0x1800e58df  mov     ecx, 1E499609h
0x1800e58e4  mov     r8d, 0Fh
0x1800e58ea  call    ??$SendDiagnosticTrace@UResult@Structured@Logging@Http@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUResult@Structured@3Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Result &&)
0x1800e58ef  lea     rcx, [rsp+6E8h+var_570+8]; void *
0x1800e58f7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e58fc  jmp     short loc_1800E5912
0x1800e58fe  lea     rbx, aRequestid; "RequestId"
0x1800e5905  mov     r13d, 100h
0x1800e590b  lea     r12, ??_7FirstScheme@Structured@Logging@Http@Mso@@6B@; const Mso::Http::Logging::Structured::FirstScheme::`vftable'
0x1800e5912  cmp     [rsi+19h], dil
0x1800e5916  jz      loc_1800E59AD
0x1800e591c  lea     rax, [rsi+50h]
0x1800e5920  cmp     [rax+18h], r14
0x1800e5924  jbe     short loc_1800E5929
0x1800e5926  mov     rax, [rax]
0x1800e5929  mov     [rsp+6E8h+var_580], rbx
0x1800e5931  mov     [rsp+6E8h+var_578], rax
0x1800e5939  mov     word ptr [rsp+6E8h+var_570], r13w
0x1800e5942  xorps   xmm0, xmm0
0x1800e5945  movups  [rsp+6E8h+var_570+8], xmm0
0x1800e594d  mov     [rsp+6E8h+var_558], rdi
0x1800e5955  mov     [rsp+6E8h+var_550], r14
0x1800e595d  mov     word ptr [rsp+6E8h+var_570+8], di
0x1800e5965  mov     [rsp+6E8h+var_588], r12
0x1800e596d  lea     rax, aRequestAlready_0; "Request already sent"
0x1800e5974  mov     qword ptr [rsp+6E8h+dwNumberOfBytesWritten], rax
0x1800e5979  lea     rax, [rsp+6E8h+var_588]
0x1800e5981  mov     qword ptr [rsp+6E8h+dwTotalLength], rax
0x1800e5986  lea     rax, [rsp+6E8h+dwNumberOfBytesWritten]
0x1800e598b  mov     qword ptr [rsp+6E8h+dwOptionalLength], rax
0x1800e5990  mov     ecx, 1E499608h
0x1800e5995  mov     r8d, 0Fh
0x1800e599b  call    ??$SendDiagnosticTrace@UResult@Structured@Logging@Http@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUResult@Structured@3Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Result &&)
0x1800e59a0  lea     rcx, [rsp+6E8h+var_570+8]; void *
0x1800e59a8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e59ad  cmp     [rsi+18h], dil
0x1800e59b1  jnz     loc_1800E5A48
0x1800e59b7  lea     rax, [rsi+50h]
0x1800e59bb  cmp     [rax+18h], r14
0x1800e59bf  jbe     short loc_1800E59C4
0x1800e59c1  mov     rax, [rax]
0x1800e59c4  mov     [rsp+6E8h+var_580], rbx
0x1800e59cc  mov     [rsp+6E8h+var_578], rax
0x1800e59d4  mov     word ptr [rsp+6E8h+var_570], r13w
0x1800e59dd  xorps   xmm0, xmm0
0x1800e59e0  movups  [rsp+6E8h+var_570+8], xmm0
0x1800e59e8  mov     [rsp+6E8h+var_558], rdi
0x1800e59f0  mov     [rsp+6E8h+var_550], r14
0x1800e59f8  mov     word ptr [rsp+6E8h+var_570+8], di
0x1800e5a00  mov     [rsp+6E8h+var_588], r12
0x1800e5a08  lea     rax, aRequestAlready; "Request already not open"
0x1800e5a0f  mov     qword ptr [rsp+6E8h+dwNumberOfBytesWritten], rax
0x1800e5a14  lea     rax, [rsp+6E8h+var_588]
0x1800e5a1c  mov     qword ptr [rsp+6E8h+dwTotalLength], rax
0x1800e5a21  lea     rax, [rsp+6E8h+dwNumberOfBytesWritten]
0x1800e5a26  mov     qword ptr [rsp+6E8h+dwOptionalLength], rax
0x1800e5a2b  mov     ecx, 1E499607h
0x1800e5a30  mov     r8d, 0Fh
0x1800e5a36  call    ??$SendDiagnosticTrace@UResult@Structured@Logging@Http@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUResult@Structured@3Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Result &&)
0x1800e5a3b  lea     rcx, [rsp+6E8h+var_570+8]; void *
0x1800e5a43  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e5a48  cmp     [rsi+19h], dil
0x1800e5a4c  jnz     loc_1800E6FAE
0x1800e5a52  cmp     [rsi+18h], dil
0x1800e5a56  jz      loc_1800E6FAE
0x1800e5a5c  cmp     [rsi+1Ah], dil
0x1800e5a60  jnz     loc_1800E6FAE
0x1800e5a66  mov     [rsp+6E8h+var_698], dil
0x1800e5a6b  mov     bl, dil
0x1800e5a6e  mov     r12d, edi
0x1800e5a71  xorps   xmm0, xmm0
0x1800e5a74  movups  [rsp+6E8h+var_470], xmm0
0x1800e5a7c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800e5a84  movdqu  [rsp+6E8h+var_460], xmm1
0x1800e5a8d  mov     word ptr [rsp+6E8h+var_470], di
0x1800e5a95  mov     rcx, rsi; this
0x1800e5a98  call    ?processRequestSettings@CHttpRequest_WinHttp@Http@Mso@@AEAAXXZ; Mso::Http::CHttpRequest_WinHttp::processRequestSettings(void)
0x1800e5a9d  lea     rcx, [rsi+140h]; this
0x1800e5aa4  call    ?Start@HttpRequestTelemetry@Http@Mso@@QEAAXXZ; Mso::Http::HttpRequestTelemetry::Start(void)
0x1800e5aa9  lea     rcx, [rsi+190h]; this
0x1800e5ab0  call    ?Start@HttpRequestTelemetry@Http@Mso@@QEAAXXZ; Mso::Http::HttpRequestTelemetry::Start(void)
0x1800e5ab5  mov     r13, qword ptr [rsp+6E8h+arg_20]
0x1800e5abd  test    r13, r13
0x1800e5ac0  setnz   al
0x1800e5ac3  mov     [rsi+1E0h], al
0x1800e5ac9  mov     al, [rsp+6E8h+var_698]
0x1800e5acd  test    al, al
0x1800e5acf  jnz     loc_1800E682C
0x1800e5ad5  lea     rcx, [rsp+6E8h+var_4E8]; this
0x1800e5add  call    ??0Stopwatch@Measurements@@QEAA@XZ; Measurements::Stopwatch::Stopwatch(void)
0x1800e5ae2  mov     r9, rax
0x1800e5ae5  mov     edx, cs:?HttpRequestSendInternalSendingRequest@HttpCall@MeasurementId@Measurements@@3UMeasurementIdType@3@B; Measurements::MeasurementIdType const Measurements::MeasurementId::HttpCall::HttpRequestSendInternalSendingRequest
0x1800e5aeb  lea     rcx, [rsp+6E8h+var_640]
0x1800e5af3  call    ??0MeasureElapsedTime@Measurements@@QEAA@UMeasurementIdType@1@_N$$QEAVStopwatch@1@@Z; Measurements::MeasureElapsedTime::MeasureElapsedTime(Measurements::MeasurementIdType,bool,Measurements::Stopwatch &&)
0x1800e5af8  lea     rdx, [rsi+0E8h]
0x1800e5aff  lea     rcx, [rsp+6E8h+var_5C0]
0x1800e5b07  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x1800e5b0c  cmp     [rsi+78h], rdi
0x1800e5b10  jnz     loc_1800E5C2B
0x1800e5b16  mov     r8d, 288765Eh
0x1800e5b1c  mov     rcx, r15
0x1800e5b1f  call    ?InvalidStateError@Results@Http@Mso@@YA?AUResult@23@_JI@Z; Mso::Http::Results::InvalidStateError(__int64,uint)
0x1800e5b24  lea     rcx, [rsp+6E8h+var_5C0]
0x1800e5b2c  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x1800e5b31  cmp     [rsp+6E8h+var_640], dil
0x1800e5b39  jz      short loc_1800E5BA0
0x1800e5b3b  movzx   ecx, word ptr [rsp+6E8h+var_620]
0x1800e5b43  call    sub_1800CA488
0x1800e5b48  mov     rbx, rax
0x1800e5b4b  test    rax, rax
0x1800e5b4e  jz      short loc_1800E5BA0
0x1800e5b50  cmp     [rsp+6E8h+var_628], dil
0x1800e5b58  jz      short loc_1800E5B7A
0x1800e5b5a  lea     rcx, [rsp+6E8h+var_630]
0x1800e5b62  call    ??D?$_Optional_construct_base@V?$time_point@Ufiletime_clock@Chrono@Mso@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@std@@QEGBAAEBV?$time_point@Ufiletime_clock@Chrono@Mso@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@1@XZ; std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(void)
0x1800e5b67  mov     rdx, rbx
0x1800e5b6a  mov     rcx, [rax]
0x1800e5b6d  call    sub_1800CA9E4
0x1800e5b72  mov     [rsp+6E8h+var_628], dil
0x1800e5b7a  xor     edx, edx
0x1800e5b7c  mov     ecx, [rsp+6E8h+var_620]
0x1800e5b83  call    sub_1800CD884
0x1800e5b88  mov     rdx, rbx
0x1800e5b8b  mov     rcx, [rsp+6E8h+var_638]
0x1800e5b93  call    sub_1800CA9E4
0x1800e5b98  mov     [rsp+6E8h+var_640], dil
0x1800e5ba0  lea     rcx, [rsp+6E8h+var_470]; void *
0x1800e5ba8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e5bad  lea     rcx, [rsp+6E8h+var_3E8]; this
0x1800e5bb5  call    ??1CProcessMsoUrl@@UEAA@XZ; CProcessMsoUrl::~CProcessMsoUrl(void)
0x1800e5bba  cmp     [rsp+6E8h+var_670], dil
0x1800e5bbf  jz      short loc_1800E5C23
0x1800e5bc1  movzx   ecx, word ptr [rsp+6E8h+var_650]
0x1800e5bc9  call    sub_1800CA488
0x1800e5bce  mov     rbx, rax
0x1800e5bd1  test    rax, rax
0x1800e5bd4  jz      short loc_1800E5C23
0x1800e5bd6  cmp     [rsp+6E8h+var_658], dil
0x1800e5bde  jz      short loc_1800E5C00
0x1800e5be0  lea     rcx, [rsp+6E8h+var_660]
0x1800e5be8  call    ??D?$_Optional_construct_base@V?$time_point@Ufiletime_clock@Chrono@Mso@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@std@@@std@@QEGBAAEBV?$time_point@Ufiletime_clock@Chrono@Mso@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@chrono@1@XZ; std::_Optional_construct_base<std::chrono::time_point<Mso::Chrono::filetime_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>::operator*(void)
0x1800e5bed  mov     rdx, rbx
0x1800e5bf0  mov     rcx, [rax]
0x1800e5bf3  call    sub_1800CA9E4
0x1800e5bf8  mov     [rsp+6E8h+var_658], dil
0x1800e5c00  xor     edx, edx
0x1800e5c02  mov     ecx, [rsp+6E8h+var_650]
0x1800e5c09  call    sub_1800CD884
0x1800e5c0e  mov     rdx, rbx
0x1800e5c11  mov     rcx, [rsp+6E8h+var_668]
0x1800e5c19  call    sub_1800CA9E4
0x1800e5c1e  mov     [rsp+6E8h+var_670], dil
0x1800e5c23  mov     rax, r15
0x1800e5c26  jmp     loc_1800E70A5
0x1800e5c2b  lea     rcx, [rsi+0B8h]
0x1800e5c32  call    ?ReportRequestStart@?$ResourceUsageNetworkMonitorTemplate@VNetworkUsageProductionBase@Details@Http@Mso@@@Details@Http@Mso@@QEAAX_N@Z; Mso::Http::Details::ResourceUsageNetworkMonitorTemplate<Mso::Http::Details::NetworkUsageProductionBase>::ReportRequestStart(bool)
0x1800e5c37  mov     eax, 0FFFFFFFFh
0x1800e5c3c  cmp     r13, rax
0x1800e5c3f  jbe     short loc_1800E5C48
0x1800e5c41  mov     ecx, 5
0x1800e5c46  int     29h; Win8: RtlFailFast(ecx)
0x1800e5c48  mov     [rsp+6E8h+dwContext], rdi; dwContext
0x1800e5c4d  mov     [rsp+6E8h+dwTotalLength], r13d; dwTotalLength
0x1800e5c52  mov     [rsp+6E8h+dwOptionalLength], r13d; dwOptionalLength
0x1800e5c57  mov     r9, [rsp+6E8h+lpOptional]; lpOptional
0x1800e5c5f  xor     r8d, r8d; dwHeadersLength
0x1800e5c62  xor     edx, edx; lpszHeaders
0x1800e5c64  mov     rcx, [rsi+78h]; hRequest
0x1800e5c68  call    cs:__imp_WinHttpSendRequest
0x1800e5c6e  test    eax, eax
0x1800e5c70  jz      short loc_1800E5CAD
0x1800e5c72  mov     bl, 1
0x1800e5c74  add     [rsi+0C8h], r13d
0x1800e5c7b  lea     rdx, [rsi+0A8h]
0x1800e5c82  lea     rcx, [rsp+6E8h+var_5D0]
0x1800e5c8a  call    ??0?$shared_ptr@UIServiceRequestTelemetryActivity@OfficeWebServiceApi@Mso@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity> const &)
0x1800e5c8f  mov     rcx, [rsp+6E8h+var_5D0]
0x1800e5c97  add     [rcx+10h], r13d
0x1800e5c9b  lea     rcx, [rsp+6E8h+var_5D0]; void *
0x1800e5ca3  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800e5ca8  jmp     loc_1800E5D69
0x1800e5cad  mov     bl, dil
0x1800e5cb0  call    cs:__imp_GetLastError
0x1800e5cb6  mov     r12d, eax
0x1800e5cb9  lea     rax, aShErrorcode; "SH_ErrorCode"
0x1800e5cc0  mov     qword ptr [rsp+6E8h+var_4E8+8], rax
0x1800e5cc8  mov     dword ptr [rsp+6E8h+var_4D8], r12d
0x1800e5cd0  mov     eax, 4
0x1800e5cd5  mov     word ptr [rsp+6E8h+var_4D8+4], ax
0x1800e5cdd  xorps   xmm0, xmm0
0x1800e5ce0  movups  [rsp+6E8h+var_4D0], xmm0
0x1800e5ce8  mov     [rsp+6E8h+var_4C0], rdi
0x1800e5cf0  mov     [rsp+6E8h+var_4B8], r14
0x1800e5cf8  mov     word ptr [rsp+6E8h+var_4D0], di
0x1800e5d00  lea     rax, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x1800e5d07  mov     qword ptr [rsp+6E8h+var_4E8], rax
0x1800e5d0f  lea     rcx, [rsp+6E8h+var_548]
0x1800e5d17  call    ??0Url@Structured@Logging@Http@Mso@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Http::Logging::Structured::Url::Url(std::wstring const &)
0x1800e5d1c  lea     rcx, aWinhttpsendreq_1; "WinHttpSendRequest failed"
0x1800e5d23  mov     qword ptr [rsp+6E8h+dwNumberOfBytesWritten], rcx
0x1800e5d28  lea     rcx, [rsp+6E8h+var_4E8]
0x1800e5d30  mov     [rsp+6E8h+dwContext], rcx
0x1800e5d35  mov     qword ptr [rsp+6E8h+dwTotalLength], rax
0x1800e5d3a  lea     rax, [rsp+6E8h+dwNumberOfBytesWritten]
0x1800e5d3f  mov     qword ptr [rsp+6E8h+dwOptionalLength], rax
0x1800e5d44  mov     ecx, 105539Dh
0x1800e5d49  call    ??$SendDiagnosticTrace@UResult@Structured@Logging@Http@Mso@@URequestId@2345@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUResult@Structured@3Http@1@$$QEAURequestId@93Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result,Mso::Http::Logging::Structured::RequestId>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Result &&,Mso::Http::Logging::Structured::RequestId &&)
0x1800e5d4e  lea     rcx, [rsp+6E8h+var_548]
0x1800e5d56  call    ??1?$ClassifiedStructuredObject@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Diagnostics@Mso@@UEAA@XZ; Mso::Diagnostics::ClassifiedStructuredObject<std::wstring>::~ClassifiedStructuredObject<std::wstring>(void)
0x1800e5d5b  lea     rcx, [rsp+6E8h+var_4D0]; void *
0x1800e5d63  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e5d68  nop
0x1800e5d69  lea     rcx, [rsp+6E8h+var_5C0]
0x1800e5d71  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x1800e5d76  test    bl, bl
  ... truncated ...
```
