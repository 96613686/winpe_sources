# EnrollmentProc(void *)

- ea: `0x1800338a0`
- end: `0x180034143`
- name: `?EnrollmentProc@@YAIPEAX@Z`
- size: `2211`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x1800046c8`
- `0x180017210`
- `0x1800338a0`
- `0x18003414c`
- `0x180035cd8`
- `0x180038764`
- `0x180038ff0`
- `0x1800472d4`
- `0x180047678`
- `0x1800476f0`
- `0x180047758`
- `0x180047c38`
- `0x180048764`
- `0x180048b20`
- `0x180048edc`
- `0x180049250`
- `0x18004a92c`
- `0x18004aa40`
- `0x18004ab54`
- `0x18004ac50`
- `0x18004b218`
- `0x18004ba58`
- `0x18005bd72`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033a32`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033de5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033f8e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033a32`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033de5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180033f8e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800340c5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800340c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800340d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800340d4`

## string_xrefs

- `0x180033c8a`: `PublishingService`
- `0x180033957`: `http://microsoft.com/DRM/PublishingService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnrollmentProc(void *a1)
{
  void *v1; // rdi
  UINT v2; // r13d
  unsigned __int16 *v3; // r14
  void (__fastcall *v4)(_QWORD, _QWORD, _QWORD, _QWORD); // r12
  const unsigned __int16 *v5; // rdx
  HRESULT Request; // ebx
  unsigned int v7; // r8d
  __int64 v8; // rdx
  __int64 v9; // rdx
  int v10; // edx
  __int64 v11; // rdx
  const unsigned __int16 **v12; // r14
  unsigned __int16 *v13; // r15
  unsigned __int16 *v14; // rsi
  void *v15; // rax
  UINT v16; // esi
  void **v17; // rdi
  int v18; // ecx
  bool v19; // zf
  UINT v20; // esi
  _QWORD *v21; // rbx
  UINT v22; // r8d
  _QWORD *i; // rcx
  WCHAR *v24; // r9
  __int64 v25; // rax
  unsigned __int64 v26; // rsi
  void *v27; // rax
  const unsigned __int16 *v28; // r9
  int v29; // eax
  int v30; // r14d
  unsigned int v31; // esi
  unsigned int v32; // r15d
  unsigned __int16 *v33; // rcx
  __int64 v34; // rax
  unsigned __int64 v35; // r12
  unsigned __int16 *v36; // rax
  unsigned __int16 *v37; // rbx
  unsigned int v38; // esi
  unsigned __int16 *v39; // r14
  unsigned __int16 *v40; // rcx
  unsigned __int16 *v41; // r11
  __int64 v42; // rax
  int v43; // eax
  unsigned __int16 *v44; // rax
  int v45; // eax
  void *v46; // rcx
  void *v47; // rcx
  unsigned __int16 *v49; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v50; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v51; // [rsp+50h] [rbp-B0h] BYREF
  void (__fastcall *v52)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+58h] [rbp-A8h]
  void *v53; // [rsp+60h] [rbp-A0h]
  void *v54; // [rsp+68h] [rbp-98h]
  void *Block; // [rsp+70h] [rbp-90h]
  __int64 v56; // [rsp+78h] [rbp-88h]
  __int64 v57; // [rsp+80h] [rbp-80h]
  char v58[8]; // [rsp+90h] [rbp-70h] BYREF
  void (__fastcall *v59)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+98h] [rbp-68h]
  int v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h]
  __int64 v62; // [rsp+E0h] [rbp-20h]
  UINT pcCert; // [rsp+1F8h] [rbp+F8h] BYREF
  unsigned __int16 *v65; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 *v66; // [rsp+208h] [rbp+108h] BYREF

  v57 = -2;
  v1 = a1;
  _RTLTRACE("[msdrm]:+EnrollmentProc");
  CDRMSoapRequest::CDRMSoapRequest((CDRMSoapRequest *)v58);
  LODWORD(v65) = 0;
  v51 = 0;
  v54 = 0;
  pcCert = 0;
  v66 = 0;
  v49 = 0;
  if ( !v1 )
    goto LABEL_107;
  Block = 0;
  v2 = 0;
  v53 = 0;
  v3 = 0;
  v50 = 0;
  v4 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)v1 + 3);
  v52 = v4;
  v56 = *((_QWORD *)v1 + 4);
  v59 = v4;
  v60 = 5;
  v61 = v56;
  v62 = *((_QWORD *)v1 + 5);
  Request = CDRMSoapRequest::CreateRequest(
              (CDRMSoapRequest *)v58,
              L"GetClientLicensorCert",
              L"RequestParams",
              L"http://microsoft.com/DRM/PublishingService",
              1u);
  if ( Request < 0 )
    goto LABEL_12;
  Request = CDRMSoapRequest::CreateHeader((CDRMSoapRequest *)v58, v5, v7);
  if ( Request < 0 )
    goto LABEL_12;
  Request = CDRMSoapRequest::AddHeaderParameter(v58, v8, L"MinimumVersion");
  if ( Request < 0 )
    goto LABEL_12;
  Request = CDRMSoapRequest::AddHeaderParameter(v58, v9, L"MaximumVersion");
  if ( Request < 0 )
    goto LABEL_12;
  Request = CDRMSoapRequest::AddStruct((CDRMSoapRequest *)v58, v10, L"GetClientLicensorCertParams", 1u);
  if ( Request < 0 )
    goto LABEL_12;
  if ( !DRMDeconstructCertificateChain(*((PWSTR *)v1 + 1), 0, &pcCert, 0) )
  {
    while ( 1 )
    {
      v20 = v2 + 1;
      v21 = operator new(saturated_mul(v2 + 1, 8u));
      if ( !v21 )
        break;
      v22 = 0;
      for ( i = v53; v22 < v2; ++v22 )
        v21[v22] = i[v22];
      operator delete(i);
      v53 = v21;
      v24 = (WCHAR *)operator new(saturated_mul(pcCert + 1, 2u));
      v21[v2] = v24;
      if ( !v24 )
        break;
      Request = DRMDeconstructCertificateChain(*((PWSTR *)v1 + 1), v2, &pcCert, v24);
      if ( Request < 0 )
        goto LABEL_12;
      ++v2;
      if ( DRMDeconstructCertificateChain(*((PWSTR *)v1 + 1), v20, &pcCert, 0) )
        goto LABEL_8;
    }
    Request = -2147024882;
    goto LABEL_12;
  }
LABEL_8:
  v12 = (const unsigned __int16 **)v53;
  Request = CDRMSoapRequest::AddArray(v58, v11, L"GetClientLicensorCertParams", L"PersonaCerts");
  if ( Request < 0 )
    goto LABEL_11;
  if ( !WaitForSingleObject(*((HANDLE *)v1 + 5), 0) )
  {
LABEL_10:
    Request = -2147168447;
LABEL_11:
    v3 = v50;
LABEL_12:
    v13 = v49;
    v14 = v66;
    goto LABEL_13;
  }
  v25 = -1;
  do
    ++v25;
  while ( *(_WORD *)(*(_QWORD *)v1 + 2 * v25) );
  v26 = v25 + 14;
  v27 = operator new(saturated_mul(v25 + 14, 2u));
  Block = v27;
  if ( !v27 )
  {
    Request = -2147024882;
    goto LABEL_11;
  }
  Request = StringCchCopyW((unsigned __int16 *)v27, v26, *(const unsigned __int16 **)v1);
  if ( Request < 0 )
    goto LABEL_11;
  Request = StringCchCatW((unsigned __int16 *)Block, v26, L"/publish.asmx");
  if ( Request < 0 )
    goto LABEL_11;
  Request = CHttpBase::SetServerInfo(
              (CHttpBase *)v58,
              (const unsigned __int16 *)Block,
              *((_DWORD *)v1 + 12) & 0x10,
              v28);
  if ( Request < 0 )
    goto LABEL_11;
  Request = CDRMSoapRequest::SetServerMethod((CDRMSoapRequest *)v58, L"PublishingService", L"GetClientLicensorCert");
  if ( Request < 0 )
    goto LABEL_11;
  v29 = CDRMSoapRequest::DispatchRequest((CDRMSoapRequest *)v58, 0, 0);
  Request = v29;
  if ( v29 != -2147168300 )
  {
    if ( v29 < 0 )
    {
      _RTLTRACE("[msdrm]: FAILED : %x ", v29);
      goto LABEL_11;
    }
    if ( !WaitForSingleObject(*((HANDLE *)v1 + 5), 0) )
      goto LABEL_10;
    Request = CDRMSoapRequest::GetParameterValueCount(
                (CDRMSoapRequest *)v58,
                L"GetClientLicensorCertResponse",
                L"CertificateChain",
                (unsigned int *)&v65);
    if ( Request < 0 )
      goto LABEL_11;
    v30 = 0;
    v31 = 0;
    v32 = (unsigned int)v65;
    if ( (_DWORD)v65 )
    {
      v33 = v51;
      while ( 1 )
      {
        operator delete(v33);
        v51 = 0;
        Request = CDRMSoapRequest::GetParameterValue(
                    (CDRMSoapRequest *)v58,
                    L"GetClientLicensorCertResponse",
                    L"CertificateChain",
                    v31,
                    &v51);
        if ( Request < 0 )
          break;
        v33 = v51;
        v34 = -1;
        do
          ++v34;
        while ( v51[v34] );
        v30 += v34;
        if ( ++v31 >= v32 )
          goto LABEL_66;
      }
      v3 = 0;
      goto LABEL_12;
    }
LABEL_66:
    v35 = (unsigned int)(v30 + 1);
    v36 = (unsigned __int16 *)operator new(saturated_mul(v35, 2u));
    v37 = v36;
    v54 = v36;
    v65 = v36;
    v38 = 0;
    if ( v36 )
    {
      memset_0(v36, 0, 2 * v35);
      if ( v32 )
      {
        v39 = v37;
        v40 = v51;
        while ( 1 )
        {
          operator delete(v40);
          v51 = 0;
          Request = CDRMSoapRequest::GetParameterValue(
                      (CDRMSoapRequest *)v58,
                      L"GetClientLicensorCertResponse",
                      L"CertificateChain",
                      v38,
                      &v51);
          v41 = 0;
          if ( Request < 0 )
            break;
          Request = StringCchCopyW(v39, v35 - (((char *)v39 - (_BYTE *)v54) >> 1), v51);
          if ( Request < 0 )
            break;
          v40 = v51;
          v42 = -1;
          do
            ++v42;
          while ( v51[v42] != (_WORD)v41 );
          v39 += v42;
          if ( ++v38 >= v32 )
          {
            v37 = (unsigned __int16 *)v54;
            goto LABEL_78;
          }
        }
        v3 = v41;
        goto LABEL_69;
      }
LABEL_78:
      if ( WaitForSingleObject(*((HANDLE *)v1 + 5), 0) )
      {
        if ( (*((_BYTE *)v1 + 48) & 2) != 0 )
        {
          pcCert = 0;
          v43 = ConstructCertificateChain(1u, &v65, &pcCert, 0);
          Request = v43;
          if ( v43 < 0 )
          {
            _RTLTRACE("[msdrm]:EnrollmentProc: ConstructCertificateChain FAILED %x", v43);
            goto LABEL_68;
          }
          v44 = (unsigned __int16 *)operator new(saturated_mul(pcCert + 1, 2u));
          v3 = v44;
          if ( !v44 )
          {
            Request = -2147024882;
            goto LABEL_69;
          }
          v45 = ConstructCertificateChain(1u, &v65, &pcCert, v44);
          Request = v45;
          if ( v45 < 0 )
          {
            _RTLTRACE("[msdrm]:EnrollmentProc: ConstructCertificateChain FAILED %x", v45);
            goto LABEL_69;
          }
        }
        else
        {
          Request = StoreEnrollmentCert(v37, *(unsigned __int16 **)v53);
          v3 = v50;
          if ( Request < 0 )
            goto LABEL_69;
        }
        Request = 315140;
        goto LABEL_69;
      }
      Request = -2147168447;
    }
    else
    {
      Request = -2147024882;
    }
LABEL_68:
    v3 = v50;
LABEL_69:
    v4 = v52;
    goto LABEL_12;
  }
  CDRMSoapRequest::GetFaultCode((CDRMSoapRequest *)v58, &v66);
  CDRMSoapRequest::GetFaultString((CDRMSoapRequest *)v58, &v49);
  v13 = v49;
  v14 = v66;
  _RTLTRACE("[msdrm]:EnrollmentProc  FaultCode = %S , FaultString = %S ", v66, v49);
  if ( CDRMSoapRequest::IsExceptionType(
         (CDRMSoapRequest *)v58,
         L"Microsoft.DigitalRightsManagement.Licensing.UserIsExcludedException")
    || CDRMSoapRequest::IsExceptionType(
         (CDRMSoapRequest *)v58,
         L"Microsoft.DigitalRightsManagement.Licensing.DrmacIsExcludedException")
    || CDRMSoapRequest::IsExceptionType(
         (CDRMSoapRequest *)v58,
         L"Microsoft.DigitalRightsManagement.Licensing.InvalidPersonaCertTimeException")
    || CDRMSoapRequest::IsExceptionType(
         (CDRMSoapRequest *)v58,
         L"Microsoft.DigitalRightsManagement.Licensing.InvalidPersonaCertSignatureException")
    || CDRMSoapRequest::IsExceptionType(
         (CDRMSoapRequest *)v58,
         L"Microsoft.DigitalRightsManagement.Licensing.UntrustedPersonaCertException")
    || CDRMSoapRequest::IsExceptionType(
         (CDRMSoapRequest *)v58,
         L"Microsoft.DigitalRightsManagement.Licensing.UnexpectedPersonaCertException") )
  {
LABEL_53:
    Request = -2147168450;
    goto LABEL_54;
  }
  if ( !CDRMSoapRequest::IsExceptionType(
          (CDRMSoapRequest *)v58,
          L"Microsoft.DigitalRightsManagement.Licensing.BlackBoxIsInvalidException") )
  {
    if ( !CDRMSoapRequest::IsExceptionType(
            (CDRMSoapRequest *)v58,
            L"Microsoft.DigitalRightsManagement.Cryptography.UnsupportedCryptographicSetException") )
    {
      Request = -2147168444;
      goto LABEL_54;
    }
    DeleteAllV1LicensesForGIC(*v12);
    goto LABEL_53;
  }
  Request = -2147168451;
LABEL_54:
  v3 = v50;
LABEL_13:
  operator delete(Block);
  operator delete(v51);
  operator delete(v54);
  operator delete(0);
  operator delete(v14);
  operator delete(v13);
  v15 = v53;
  if ( v53 )
  {
    v16 = 0;
    if ( v2 )
    {
      v17 = (void **)v53;
      do
        operator delete(v17[v16++]);
      while ( v16 < v2 );
      v1 = a1;
      v15 = v53;
    }
    operator delete(v15);
  }
  if ( Request >= 0 )
    goto LABEL_100;
  if ( Request <= -2147168436 )
  {
    if ( (unsigned int)(Request + 2147168453) <= 0x11 )
    {
      v18 = 131149;
      if ( _bittest(&v18, Request + 2147168453) )
        goto LABEL_100;
    }
    if ( Request != -2147168444 )
    {
      if ( Request != -2147168441 )
      {
        v19 = Request == -2147168438;
        goto LABEL_96;
      }
      goto LABEL_99;
    }
LABEL_98:
    Request = -2147168444;
    goto LABEL_100;
  }
  if ( (unsigned int)(Request + 2147168421) > 1 )
  {
    if ( Request == -2147168304 )
    {
LABEL_99:
      Request = -2147168441;
      goto LABEL_100;
    }
    if ( Request == -2147168300 )
      goto LABEL_98;
    if ( Request != -2147024882 )
    {
      v19 = Request == -2147024809;
LABEL_96:
      if ( !v19 )
        Request = -2147168460;
    }
  }
LABEL_100:
  v46 = (void *)*((_QWORD *)v1 + 7);
  if ( v46 )
    SetEvent(v46);
  v47 = (void *)*((_QWORD *)v1 + 5);
  if ( v47 )
    CloseHandle(v47);
  operator delete(*(void **)v1);
  operator delete(*((void **)v1 + 1));
  operator delete(v1);
  if ( v4 )
    v4(5, (unsigned int)Request, v3, v56);
  operator delete(v3);
  _RTLTRACE("[msdrm]:-EnrollmentProc");
LABEL_107:
  CDRMSoapRequest::~CDRMSoapRequest((CDRMSoapRequest *)v58);
  return 0;
}

```

## disassembly

```asm
0x1800338a0  mov     [rsp-8+arg_0], rcx
0x1800338a5  push    rbp
0x1800338a6  push    rbx
0x1800338a7  push    rsi
0x1800338a8  push    rdi
0x1800338a9  push    r12
0x1800338ab  push    r13
0x1800338ad  push    r14
0x1800338af  push    r15
0x1800338b1  lea     rbp, [rsp-0A8h]
0x1800338b9  sub     rsp, 1A8h
0x1800338c0  mov     [rbp+0E0h+var_160], 0FFFFFFFFFFFFFFFEh
0x1800338c8  mov     rdi, rcx
0x1800338cb  lea     rcx, aMsdrmEnrollmen_0; "[msdrm]:+EnrollmentProc"
0x1800338d2  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800338d7  lea     rcx, [rbp+0E0h+var_150]; this
0x1800338db  call    ??0CDRMSoapRequest@@QEAA@XZ; CDRMSoapRequest::CDRMSoapRequest(void)
0x1800338e0  nop
0x1800338e1  xor     r15d, r15d
0x1800338e4  mov     dword ptr [rbp+0E0h+arg_10], r15d
0x1800338eb  mov     [rsp+1E0h+var_190], r15
0x1800338f0  mov     [rsp+1E0h+var_178], r15
0x1800338f5  mov     [rbp+0E0h+pcCert], r15d
0x1800338fc  mov     [rbp+0E0h+arg_18], r15
0x180033903  mov     [rsp+1E0h+var_1A0], r15
0x180033908  test    rdi, rdi
0x18003390b  jz      loc_180034124
0x180033911  mov     [rsp+1E0h+Block], r15
0x180033916  mov     r13d, r15d
0x180033919  mov     [rsp+1E0h+var_180], r15
0x18003391e  mov     r14d, r15d
0x180033921  mov     [rsp+1E0h+var_198], r15
0x180033926  mov     r12, [rdi+18h]
0x18003392a  mov     [rsp+1E0h+var_188], r12
0x18003392f  mov     rax, [rdi+20h]
0x180033933  mov     [rsp+1E0h+var_168], rax
0x180033938  mov     [rbp+0E0h+var_148], r12
0x18003393c  mov     [rbp+0E0h+var_140], 5
0x180033943  mov     [rbp+0E0h+var_138], rax
0x180033947  mov     rax, [rdi+28h]
0x18003394b  mov     [rbp+0E0h+var_100], rax
0x18003394f  lea     esi, [r15+1]
0x180033953  mov     dword ptr [rsp+1E0h+var_1C0], esi; unsigned int
0x180033957  lea     r9, ?g_wszPUB_PublishingServiceNamespace@@3QBGB; "http://microsoft.com/DRM/PublishingServ"...
0x18003395e  lea     r8, ?g_wszLA_RequestParams@@3QBGB; "RequestParams"
0x180033965  lea     rdx, ?g_wszPUB_GetClientLicensorCert@@3QBGB; "GetClientLicensorCert"
0x18003396c  lea     rcx, [rbp+0E0h+var_150]; this
0x180033970  call    ?CreateRequest@CDRMSoapRequest@@QEAAJPEBG00I@Z; CDRMSoapRequest::CreateRequest(ushort const *,ushort const *,ushort const *,uint)
0x180033975  mov     ebx, eax
0x180033977  test    eax, eax
0x180033979  js      loc_180033A4A
0x18003397f  lea     rcx, [rbp+0E0h+var_150]; this
0x180033983  call    ?CreateHeader@CDRMSoapRequest@@QEAAJPEBGI@Z; CDRMSoapRequest::CreateHeader(ushort const *,uint)
0x180033988  mov     ebx, eax
0x18003398a  test    eax, eax
0x18003398c  js      loc_180033A4A
0x180033992  lea     r8, ?g_wszACT_MinimumVersion@@3QBGB; "MinimumVersion"
0x180033999  lea     rcx, [rbp+0E0h+var_150]
0x18003399d  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x1800339a2  mov     ebx, eax
0x1800339a4  test    eax, eax
0x1800339a6  js      loc_180033A4A
0x1800339ac  lea     r8, ?g_wszACT_MaximumVersion@@3QBGB; "MaximumVersion"
0x1800339b3  lea     rcx, [rbp+0E0h+var_150]
0x1800339b7  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x1800339bc  mov     ebx, eax
0x1800339be  test    eax, eax
0x1800339c0  js      loc_180033A4A
0x1800339c6  mov     r9d, esi; unsigned int
0x1800339c9  lea     r8, ?g_wszPUB_GetClientLicensorParams@@3QBGB; "GetClientLicensorCertParams"
0x1800339d0  lea     rcx, [rbp+0E0h+var_150]; this
0x1800339d4  call    ?AddStruct@CDRMSoapRequest@@IEAAJHPEBGI@Z; CDRMSoapRequest::AddStruct(int,ushort const *,uint)
0x1800339d9  mov     ebx, eax
0x1800339db  test    eax, eax
0x1800339dd  js      short loc_180033A4A
0x1800339df  xor     r9d, r9d; wszCert
0x1800339e2  lea     r8, [rbp+0E0h+pcCert]; pcCert
0x1800339e9  xor     edx, edx; iWhich
0x1800339eb  mov     rcx, [rdi+8]; wszChain
0x1800339ef  call    DRMDeconstructCertificateChain
0x1800339f4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800339f8  test    eax, eax
0x1800339fa  jz      loc_180033B1E
0x180033a00  mov     [rsp+1E0h+var_1A8], r13d
0x180033a05  mov     r14, [rsp+1E0h+var_180]
0x180033a0a  mov     [rsp+1E0h+var_1B0], r14
0x180033a0f  lea     r9, ?g_wszPUB_PersonaCerts@@3QBGB; "PersonaCerts"
0x180033a16  lea     r8, ?g_wszPUB_GetClientLicensorParams@@3QBGB; "GetClientLicensorCertParams"
0x180033a1d  lea     rcx, [rbp+0E0h+var_150]
0x180033a21  call    ?AddArray@CDRMSoapRequest@@IEAAJHPEBG00W4SOAP_DATA_TYPE@@PEAPEAGI@Z; CDRMSoapRequest::AddArray(int,ushort const *,ushort const *,ushort const *,SOAP_DATA_TYPE,ushort * *,uint)
0x180033a26  mov     ebx, eax
0x180033a28  test    eax, eax
0x180033a2a  js      short loc_180033A45
0x180033a2c  xor     edx, edx; dwMilliseconds
0x180033a2e  mov     rcx, [rdi+28h]; hHandle
0x180033a32  call    cs:__imp_WaitForSingleObject
0x180033a38  test    eax, eax
0x180033a3a  jnz     loc_180033BEC
0x180033a40  mov     ebx, 8004CF41h
0x180033a45  mov     r14, [rsp+1E0h+var_198]
0x180033a4a  mov     r15, [rsp+1E0h+var_1A0]
0x180033a4f  mov     rsi, [rbp+0E0h+arg_18]
0x180033a56  mov     rcx, [rsp+1E0h+Block]; Block
0x180033a5b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033a60  mov     rcx, [rsp+1E0h+var_190]; Block
0x180033a65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033a6a  mov     rcx, [rsp+1E0h+var_178]; Block
0x180033a6f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033a74  xor     ecx, ecx; Block
0x180033a76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033a7b  mov     rcx, rsi; Block
0x180033a7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033a83  mov     rcx, r15; Block
0x180033a86  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033a8b  mov     rax, [rsp+1E0h+var_180]
0x180033a90  xor     r15d, r15d
0x180033a93  test    rax, rax
0x180033a96  jz      short loc_180033AC9
0x180033a98  mov     esi, r15d
0x180033a9b  test    r13d, r13d
0x180033a9e  jz      short loc_180033AC1
0x180033aa0  mov     rdi, rax
0x180033aa3  mov     ecx, esi
0x180033aa5  mov     rcx, [rdi+rcx*8]; Block
0x180033aa9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033aae  inc     esi
0x180033ab0  cmp     esi, r13d
0x180033ab3  jb      short loc_180033AA3
0x180033ab5  mov     rdi, [rbp+0E0h+arg_0]
0x180033abc  mov     rax, [rsp+1E0h+var_180]
0x180033ac1  mov     rcx, rax; Block
0x180033ac4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033ac9  test    ebx, ebx
0x180033acb  jns     loc_1800340BC
0x180033ad1  mov     edx, 8004CF47h
0x180033ad6  cmp     ebx, 8004CF4Ch
0x180033adc  jg      loc_180034081
0x180033ae2  lea     eax, [rbx+7FFB30C5h]
0x180033ae8  cmp     eax, 11h
0x180033aeb  ja      short loc_180033AFB
0x180033aed  mov     ecx, 2004Dh
0x180033af2  bt      ecx, eax
0x180033af5  jb      loc_1800340BC
0x180033afb  cmp     ebx, 8004CF44h
0x180033b01  jz      loc_1800340B3
0x180033b07  cmp     ebx, edx
0x180033b09  jz      loc_1800340BA
0x180033b0f  cmp     ebx, 8004CF4Ah
0x180033b15  jmp     loc_1800340AA
0x180033b1a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180033b1e  lea     esi, [r13+1]
0x180033b22  mov     ecx, esi
0x180033b24  mov     eax, 8
0x180033b29  mul     rcx
0x180033b2c  cmovb   rax, r8
0x180033b30  mov     rcx, rax; Size
0x180033b33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033b38  mov     rbx, rax
0x180033b3b  test    rax, rax
0x180033b3e  jz      loc_180033BE2
0x180033b44  mov     r8d, r15d
0x180033b47  mov     rcx, [rsp+1E0h+var_180]; Block
0x180033b4c  test    r13d, r13d
0x180033b4f  jz      short loc_180033B64
0x180033b51  mov     edx, r8d
0x180033b54  mov     rax, [rcx+rdx*8]
0x180033b58  mov     [rbx+rdx*8], rax
0x180033b5c  inc     r8d
0x180033b5f  cmp     r8d, r13d
0x180033b62  jb      short loc_180033B51
0x180033b64  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180033b69  mov     [rsp+1E0h+var_180], rbx
0x180033b6e  mov     ecx, [rbp+0E0h+pcCert]
0x180033b74  inc     ecx
0x180033b76  mov     eax, 2
0x180033b7b  mul     rcx
0x180033b7e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180033b85  cmovb   rax, rcx
0x180033b89  mov     rcx, rax; Size
0x180033b8c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033b91  mov     r9, rax; wszCert
0x180033b94  mov     eax, r13d
0x180033b97  mov     [rbx+rax*8], r9
0x180033b9b  test    r9, r9
0x180033b9e  jz      short loc_180033BE2
0x180033ba0  lea     r8, [rbp+0E0h+pcCert]; pcCert
0x180033ba7  mov     edx, r13d; iWhich
0x180033baa  mov     rcx, [rdi+8]; wszChain
0x180033bae  call    DRMDeconstructCertificateChain
0x180033bb3  mov     ebx, eax
0x180033bb5  test    eax, eax
0x180033bb7  js      loc_180033A4A
0x180033bbd  mov     r13d, esi
0x180033bc0  xor     r9d, r9d; wszCert
0x180033bc3  lea     r8, [rbp+0E0h+pcCert]; pcCert
0x180033bca  mov     edx, esi; iWhich
0x180033bcc  mov     rcx, [rdi+8]; wszChain
0x180033bd0  call    DRMDeconstructCertificateChain
0x180033bd5  test    eax, eax
0x180033bd7  jz      loc_180033B1A
0x180033bdd  jmp     loc_180033A00
0x180033be2  mov     ebx, 8007000Eh
0x180033be7  jmp     loc_180033A4A
0x180033bec  mov     rcx, [rdi]
0x180033bef  or      r8, 0FFFFFFFFFFFFFFFFh
0x180033bf3  mov     rax, r8
0x180033bf6  inc     rax
0x180033bf9  cmp     [rcx+rax*2], r15w
0x180033bfe  jnz     short loc_180033BF6
0x180033c00  lea     rsi, [rax+0Eh]
0x180033c04  mov     eax, 2
0x180033c09  mul     rsi
0x180033c0c  cmovb   rax, r8
0x180033c10  mov     rcx, rax; Size
0x180033c13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033c18  mov     [rsp+1E0h+Block], rax
0x180033c1d  test    rax, rax
0x180033c20  jnz     short loc_180033C2C
0x180033c22  mov     ebx, 8007000Eh
0x180033c27  jmp     loc_180033A45
0x180033c2c  mov     r8, [rdi]; unsigned __int16 *
0x180033c2f  mov     rdx, rsi; unsigned __int64
0x180033c32  mov     rcx, rax; unsigned __int16 *
0x180033c35  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033c3a  mov     ebx, eax
0x180033c3c  test    eax, eax
0x180033c3e  js      loc_180033A45
0x180033c44  lea     r8, ?g_wszPUB_PublishingServicePadding@@3QBGB; "/publish.asmx"
0x180033c4b  mov     rdx, rsi; unsigned __int64
0x180033c4e  mov     rsi, [rsp+1E0h+Block]
0x180033c53  mov     rcx, rsi; unsigned __int16 *
0x180033c56  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033c5b  mov     ebx, eax
0x180033c5d  test    eax, eax
0x180033c5f  js      loc_180033A45
0x180033c65  mov     r8d, [rdi+30h]
0x180033c69  and     r8d, 10h; unsigned int
0x180033c6d  mov     rdx, rsi; unsigned __int16 *
0x180033c70  lea     rcx, [rbp+0E0h+var_150]; this
0x180033c74  call    ?SetServerInfo@CHttpBase@@QEAAJPEBGI0@Z; CHttpBase::SetServerInfo(ushort const *,uint,ushort const *)
0x180033c79  mov     ebx, eax
0x180033c7b  test    eax, eax
0x180033c7d  js      loc_180033A45
0x180033c83  lea     r8, ?g_wszPUB_GetClientLicensorCert@@3QBGB; "GetClientLicensorCert"
0x180033c8a  lea     rdx, ?g_wszPUB_PublishingService@@3QBGB; "PublishingService"
0x180033c91  lea     rcx, [rbp+0E0h+var_150]; this
0x180033c95  call    ?SetServerMethod@CDRMSoapRequest@@QEAAJPEBG0@Z; CDRMSoapRequest::SetServerMethod(ushort const *,ushort const *)
0x180033c9a  mov     ebx, eax
0x180033c9c  test    eax, eax
0x180033c9e  js      loc_180033A45
0x180033ca4  xor     r8d, r8d; unsigned int
0x180033ca7  xor     edx, edx; unsigned __int8 *
0x180033ca9  lea     rcx, [rbp+0E0h+var_150]; this
0x180033cad  call    ?DispatchRequest@CDRMSoapRequest@@UEAAJPEAEI@Z; CDRMSoapRequest::DispatchRequest(uchar *,uint)
0x180033cb2  mov     ebx, eax
0x180033cb4  cmp     eax, 8004CFD4h
0x180033cb9  jnz     loc_180033DC8
0x180033cbf  lea     rdx, [rbp+0E0h+arg_18]; unsigned __int16 **
0x180033cc6  lea     rcx, [rbp+0E0h+var_150]; this
0x180033cca  call    ?GetFaultCode@CDRMSoapRequest@@QEAAJPEAPEAG@Z; CDRMSoapRequest::GetFaultCode(ushort * *)
0x180033ccf  lea     rdx, [rsp+1E0h+var_1A0]; unsigned __int16 **
0x180033cd4  lea     rcx, [rbp+0E0h+var_150]; this
0x180033cd8  call    ?GetFaultString@CDRMSoapRequest@@QEAAJPEAPEAG@Z; CDRMSoapRequest::GetFaultString(ushort * *)
0x180033cdd  mov     r15, [rsp+1E0h+var_1A0]
0x180033ce2  mov     r8, r15
0x180033ce5  mov     rsi, [rbp+0E0h+arg_18]
0x180033cec  mov     rdx, rsi
0x180033cef  lea     rcx, aMsdrmEnrollmen; "[msdrm]:EnrollmentProc  FaultCode = %S "...
0x180033cf6  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180033cfb  lea     rdx, ?g_wszACT_UserIsExcludedException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x180033d02  lea     rcx, [rbp+0E0h+var_150]; this
0x180033d06  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x180033d0b  test    eax, eax
0x180033d0d  jnz     loc_180033DB2
0x180033d13  lea     rdx, ?g_wszACT_DrmacIsExcludedException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x180033d1a  lea     rcx, [rbp+0E0h+var_150]; this
0x180033d1e  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x180033d23  test    eax, eax
0x180033d25  jnz     loc_180033DB2
0x180033d2b  lea     rdx, ?g_wszACT_InvalidPersonaCertTimeException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x180033d32  lea     rcx, [rbp+0E0h+var_150]; this
0x180033d36  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x180033d3b  test    eax, eax
0x180033d3d  jnz     short loc_180033DB2
0x180033d3f  lea     rdx, ?g_wszACT_InvalidPersonaCertSignatureException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x180033d46  lea     rcx, [rbp+0E0h+var_150]; this
0x180033d4a  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x180033d4f  test    eax, eax
0x180033d51  jnz     short loc_180033DB2
0x180033d53  lea     rdx, ?g_wszACT_UntrustedPersonaCertException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x180033d5a  lea     rcx, [rbp+0E0h+var_150]; this
0x180033d5e  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x180033d63  test    eax, eax
0x180033d65  jnz     short loc_180033DB2
0x180033d67  lea     rdx, ?g_wszACT_UnexpectedPersonaCertException@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
0x180033d6e  lea     rcx, [rbp+0E0h+var_150]; this
0x180033d72  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x180033d77  test    eax, eax
0x180033d79  jnz     short loc_180033DB2
0x180033d7b  lea     rdx, ?g_wszACT_BlackboxIsInvalidExclusion@@3QBGB; "Microsoft.DigitalRightsManagement.Licen"...
  ... truncated ...
```
