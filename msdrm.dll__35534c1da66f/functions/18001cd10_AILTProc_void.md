# AILTProc(void *)

- ea: `0x18001cd10`
- end: `0x18001d90b`
- name: `?AILTProc@@YAIPEAX@Z`
- size: `3067`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `31`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x180001244`
- `0x180001284`
- `0x18000321c`
- `0x18000329c`
- `0x180004654`
- `0x1800046c8`
- `0x180017210`
- `0x18001cd10`
- `0x18001dc2c`
- `0x18001dd08`
- `0x18001dde4`
- `0x18001dfb8`
- `0x18001e034`
- `0x18001f610`
- `0x180035aa0`
- `0x180036b9c`
- `0x1800472d4`
- `0x180047678`
- `0x1800476f0`
- `0x180047c38`
- `0x180047c68`
- `0x180048958`
- `0x180048b20`
- `0x180048edc`
- `0x180049250`
- `0x18004a898`
- `0x18004ab54`
- `0x18004b218`
- `0x18004ba58`
- `0x18004bfe0`
- `0x18005f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18001d1e6`
- `msvcrt!_wtoi` at `0x18001d1e6`
- `msvcrt!wcsstr` at `0x18001d3b1`
- `msvcrt!wcsstr` at `0x18001d3cb`
- `msvcrt!wcsstr` at `0x18001d50c`
- `msvcrt!wcsstr` at `0x18001d3b1`
- `msvcrt!wcsstr` at `0x18001d3cb`
- `msvcrt!wcsstr` at `0x18001d50c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d0a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d6d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d0a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d6d0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001cf37`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001cf37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cf46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001cf46`

## string_xrefs

- `0x18001d838`: `Template`
- `0x18001d598`: `AcquireTemplates`
- `0x18001d5d2`: `AcquireTemplates`
- `0x18001d0d5`: `System.UnauthorizedAccessException`
- `0x18001d8c9`: `System.UnauthorizedAccessException`
- `0x18001d030`: `http://microsoft.com/DRM/TemplateDistributionService`
- `0x18001d5c4`: `http://microsoft.com/DRM/TemplateDistributionService`
- `0x18001d00e`: `TemplateDistributionService`
- `0x18001d59f`: `TemplateDistributionService`
- `0x18001d007`: `AcquireTemplateInformation`
- `0x18001d03a`: `AcquireTemplateInformation`
- `0x18001cfc5`: `/templatedistribution.asmx`

## pseudocode

```c
__int64 __fastcall AILTProc(void *a1)
{
  unsigned int v2; // r14d
  unsigned int v3; // r12d
  const unsigned __int16 **v4; // r13
  void (__fastcall *v5)(_QWORD, _QWORD, _QWORD, _QWORD); // r15
  __int64 v6; // rax
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // rax
  int Request; // edi
  char *v10; // r13
  void *v11; // rcx
  void *v12; // rcx
  unsigned __int16 *v14; // r11
  const unsigned __int16 *v15; // r9
  const unsigned __int16 *v16; // rdx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  int PersistedLicense; // eax
  unsigned int v23; // eax
  unsigned __int16 **v24; // rdx
  __int64 v25; // rbx
  __int64 v26; // rax
  unsigned __int64 v27; // kr10_8
  bool v28; // cf
  size_t v29; // rax
  _QWORD *v30; // rax
  const unsigned __int16 *v31; // rdx
  unsigned int v32; // r15d
  unsigned int v33; // r14d
  unsigned int v34; // ebx
  unsigned __int16 **v35; // r13
  const unsigned __int16 *v36; // rdx
  int v37; // eax
  int v38; // r13d
  unsigned int v39; // r15d
  const unsigned __int16 **v40; // rax
  __int64 v41; // rbx
  unsigned int v42; // r14d
  wchar_t *v43; // rdi
  wchar_t *v44; // rax
  bool v45; // zf
  const struct _DRM_CRYPTO_VERSION_PARAMETERS *v46; // rax
  int v47; // r14d
  unsigned __int16 **v48; // r12
  const wchar_t *v49; // r15
  unsigned int v50; // ebx
  unsigned int v51; // ebx
  const unsigned __int16 *v52; // r9
  const unsigned __int16 *v53; // rdx
  unsigned int v54; // r8d
  __int64 v55; // rdx
  __int64 v56; // rdx
  int v57; // r15d
  unsigned int v58; // r12d
  unsigned int v59; // eax
  __int64 v60; // rbx
  int v61; // eax
  unsigned __int64 v62; // r15
  __int64 v63; // rax
  size_t v64; // rax
  unsigned __int64 *v65; // rax
  const unsigned __int16 *v66; // rdx
  unsigned int v67; // ebx
  unsigned __int16 **v68; // r13
  const unsigned __int16 *v69; // rdx
  const unsigned __int16 *v70; // rdx
  char *v71; // [rsp+40h] [rbp-C0h]
  void (__fastcall *v72)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+48h] [rbp-B8h]
  const unsigned __int16 **v73; // [rsp+50h] [rbp-B0h]
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v75; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v76; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 **v77; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 **v78; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 **v79; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v80; // [rsp+88h] [rbp-78h]
  unsigned __int16 **v81; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 **v82; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 **v83; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v84; // [rsp+A8h] [rbp-58h]
  __int64 v85; // [rsp+B0h] [rbp-50h]
  unsigned __int64 *v86; // [rsp+B8h] [rbp-48h]
  char v87[8]; // [rsp+C0h] [rbp-40h] BYREF
  void (__fastcall *v88)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+C8h] [rbp-38h]
  int v89; // [rsp+D0h] [rbp-30h]
  __int64 v90; // [rsp+D8h] [rbp-28h]
  __int64 v91; // [rsp+110h] [rbp+10h]
  unsigned int v92; // [rsp+1B8h] [rbp+B8h]
  _BYTE v93[248]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v94; // [rsp+2C8h] [rbp+1C8h]
  unsigned int v95; // [rsp+330h] [rbp+230h] BYREF
  unsigned int v96; // [rsp+338h] [rbp+238h] BYREF
  unsigned int v97; // [rsp+340h] [rbp+240h]
  _QWORD *v98; // [rsp+348h] [rbp+248h]

  v85 = -2;
  CDRMSoapRequest::CDRMSoapRequest((CDRMSoapRequest *)v87);
  CDRMSoapRequest::CDRMSoapRequest((CDRMSoapRequest *)v93);
  Block = 0;
  v75 = 0;
  v76 = 0;
  v2 = 0;
  v95 = 0;
  v77 = 0;
  v82 = 0;
  v81 = 0;
  v3 = 0;
  v96 = 0;
  v78 = 0;
  v83 = 0;
  v79 = 0;
  if ( !a1 )
    goto LABEL_17;
  v4 = 0;
  v73 = 0;
  v71 = 0;
  v5 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)a1 + 1);
  v72 = v5;
  v84 = *((_QWORD *)a1 + 2);
  v88 = v5;
  v89 = 6;
  v90 = v84;
  v91 = *((_QWORD *)a1 + 5);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(*((_QWORD *)a1 + 3) + 2 * v6) );
  v7 = v6 + 27;
  v8 = (unsigned __int16 *)operator new(saturated_mul(v6 + 27, 2u));
  v80 = v8;
  if ( v8 )
  {
    Request = StringCchCopyW(v8, v7, *((const unsigned __int16 **)a1 + 3));
    if ( Request < 0 )
      goto LABEL_6;
    Request = StringCchCatW(v14, v7, L"/templatedistribution.asmx");
    if ( Request < 0 )
      goto LABEL_6;
    Request = CHttpBase::SetServerInfo((CHttpBase *)v87, v80, 16 * ((*((_DWORD *)a1 + 12) & 1) == 0), v15);
    if ( Request < 0 )
      goto LABEL_6;
    Request = CDRMSoapRequest::SetServerMethod(
                (CDRMSoapRequest *)v87,
                L"TemplateDistributionService",
                L"AcquireTemplateInformation");
    if ( Request < 0 )
      goto LABEL_6;
    Request = CDRMSoapRequest::CreateRequest(
                (CDRMSoapRequest *)v87,
                L"AcquireTemplateInformation",
                0,
                L"http://microsoft.com/DRM/TemplateDistributionService",
                1u);
    if ( Request < 0 )
      goto LABEL_6;
    Request = CDRMSoapRequest::CreateHeader((CDRMSoapRequest *)v87, v16, v17);
    if ( Request < 0 )
      goto LABEL_6;
    Request = CDRMSoapRequest::AddHeaderParameter(v87, v18, L"MinimumVersion");
    if ( Request < 0 )
      goto LABEL_6;
    Request = CDRMSoapRequest::AddHeaderParameter(v87, v19, L"MaximumVersion");
    if ( Request < 0 )
      goto LABEL_6;
    if ( !WaitForSingleObject(*((HANDLE *)a1 + 5), 0) )
    {
      Request = -2147168447;
      goto LABEL_6;
    }
    v20 = CDRMSoapRequest::DispatchRequest((CDRMSoapRequest *)v87, 0, 0);
    Request = v20;
    if ( v20 == -2147168300 )
    {
      PrintFaultCode((struct CDRMSoapRequest *)v87);
      Request = -(CDRMSoapRequest::IsExceptionType((CDRMSoapRequest *)v87, L"System.UnauthorizedAccessException") != 0)
              - 2147168444;
      goto LABEL_6;
    }
    if ( v20 < 0 )
    {
      _RTLTRACE("[msdrm]: AILTProc FAILED : %x ", v20);
      goto LABEL_6;
    }
    Request = CDRMSoapRequest::GetParameterValue((CDRMSoapRequest *)v87, 0, L"ServerPublicKey", 0, &v75);
    if ( Request < 0 )
      goto LABEL_6;
    Request = CDRMSoapRequest::GetParameterValue(
                (CDRMSoapRequest *)v87,
                0,
                L"GuidHashCount",
                0,
                (unsigned __int16 **)&Block);
    if ( Request < 0 )
      goto LABEL_6;
    Request = CreateDigest(v75, &v76);
    if ( Request < 0 )
      goto LABEL_6;
    PersistedLicense = GetPersistedLicenseEx(5, v21, 1, &v76, 0, &v95, &v77, &v82);
    Request = 0;
    if ( PersistedLicense != -2147168454 )
      Request = PersistedLicense;
    v2 = v95;
    if ( Request < 0 )
      goto LABEL_6;
    Request = GetUnMaskedFileNames(v95, v77, &v81);
    if ( Request < 0 )
      goto LABEL_6;
    v23 = _wtoi((const wchar_t *)Block);
    v97 = v23;
    if ( (v23 & 0x80000000) != 0 )
    {
      Request = -2147168444;
      v10 = 0;
      goto LABEL_7;
    }
    if ( v23 )
    {
      v25 = v23;
      v27 = v23;
      v26 = 32LL * v23;
      if ( !is_mul_ok(v27, 0x20u) )
        v26 = -1;
      v28 = __CFADD__(v26, 8);
      v29 = v26 + 8;
      if ( v28 )
        v29 = -1;
      v30 = operator new(v29);
      v98 = v30;
      if ( v30 )
      {
        *v30 = v25;
        v4 = (const unsigned __int16 **)(v30 + 1);
        v73 = (const unsigned __int16 **)(v30 + 1);
        `eh vector constructor iterator'(
          v30 + 1,
          0x20u,
          (unsigned int)v25,
          (void (*)(void *))TemplateGuidData::TemplateGuidData,
          (void (*)(void *))TemplateGuidData::~TemplateGuidData);
      }
      else
      {
        v4 = 0;
        v73 = 0;
      }
      if ( !v4 )
      {
        Request = -2147024882;
        v2 = v95;
        v10 = 0;
        goto LABEL_7;
      }
      v32 = v92;
      v33 = 0;
      v34 = 2;
      if ( v92 > 2 )
      {
        while ( 1 )
        {
          v35 = (unsigned __int16 **)&v4[4 * v33];
          Request = CDRMSoapRequest::GetElementValue((CDRMSoapRequest *)v87, v31, L"Guid", v34, v35);
          if ( Request < 0 )
            goto LABEL_139;
          Request = CDRMSoapRequest::GetElementValue((CDRMSoapRequest *)v87, v36, L"Hash", v34, v35 + 1);
          if ( Request < 0 )
            goto LABEL_139;
          ++v33;
          v4 = v73;
          if ( v33 != v97 && ++v34 < v32 )
            continue;
          break;
        }
      }
      v37 = GetPersistedLicenseEx(5, v31, 1, 0, 0, &v96, &v78, &v83);
      Request = 0;
      if ( v37 != -2147168454 )
        Request = v37;
      v3 = v96;
      if ( Request < 0 )
      {
LABEL_78:
        v10 = 0;
LABEL_79:
        v2 = v95;
        v5 = v72;
        goto LABEL_7;
      }
      if ( v96 )
      {
        Request = GetUnMaskedFileNames(v96, v78, &v79);
        if ( Request < 0 )
          goto LABEL_78;
        v38 = 0;
        v39 = 0;
        v40 = v73;
        while ( 1 )
        {
          v41 = 4LL * v39;
          Request = 0;
          v42 = 0;
          if ( v3 )
          {
            while ( 1 )
            {
              v43 = wcsstr(v79[v42], v40[v41 + 1]);
              v44 = wcsstr(v79[v42], v73[v41]);
              if ( v43 && v44 )
              {
                v40 = v73;
                LODWORD(v73[v41 + 3]) = 1;
                v3 = v96;
                goto LABEL_72;
              }
              if ( v44 && !v43 )
                break;
              ++v42;
              v3 = v96;
              v40 = v73;
              if ( v42 >= v96 )
                goto LABEL_72;
            }
            LODWORD(v73[v41 + 3]) = 2;
            Request = DeleteTemplate(v78[v42], v24);
            v40 = v73;
            v3 = v96;
          }
          if ( Request < 0 )
            goto LABEL_139;
LABEL_72:
          if ( LODWORD(v40[v41 + 3]) == 1 )
            ++v38;
          if ( ++v39 >= v97 )
          {
            v45 = v38 == 0;
            v4 = v73;
            if ( v45 )
            {
              v46 = UDGetCryptoVersionFromEncodedHash(v73[1]);
              if ( !v46 )
              {
                Request = -2147024846;
                goto LABEL_78;
              }
              if ( *(_DWORD *)v46 > 0x400u )
              {
                Request = DeleteAllV1License(5);
                if ( Request < 0 )
                  goto LABEL_139;
                Request = DeleteAllV1License(1);
                if ( Request < 0 )
                  goto LABEL_139;
                Request = DeleteAllV1License(3);
                if ( Request < 0 )
                  goto LABEL_78;
              }
            }
            break;
          }
        }
      }
      v23 = v97;
    }
    v47 = 0;
    if ( v95 )
    {
      v48 = v81;
      while ( 1 )
      {
        v49 = v48[v47];
        v50 = 0;
        if ( v23 )
        {
          while ( !wcsstr(v49, v4[4 * v50]) )
          {
            if ( ++v50 >= v97 )
              goto LABEL_91;
          }
        }
        else
        {
LABEL_91:
          Request = DeleteTemplate(v77[v47], v24);
          if ( Request < 0 )
          {
            v3 = v96;
            goto LABEL_78;
          }
        }
        if ( ++v47 >= v95 )
          break;
        v23 = v97;
      }
    }
    v51 = v97;
    if ( v97 )
    {
      LODWORD(v98) = 0;
      while ( 1 )
      {
        CDRMSoapRequest::CleanRequest((CDRMSoapRequest *)v93);
        Request = CHttpBase::SetServerInfo((CHttpBase *)v93, v80, 16 * ((*((_DWORD *)a1 + 12) & 1) == 0), v52);
        if ( Request < 0 )
          break;
        Request = CDRMSoapRequest::SetServerMethod(
                    (CDRMSoapRequest *)v93,
                    L"TemplateDistributionService",
                    L"AcquireTemplates");
        if ( Request < 0 )
          break;
        Request = CDRMSoapRequest::CreateRequest(
                    (CDRMSoapRequest *)v93,
                    L"AcquireTemplates",
                    L"guids",
                    L"http://microsoft.com/DRM/TemplateDistributionService",
                    1u);
        if ( Request < 0 )
          break;
        Request = CDRMSoapRequest::CreateHeader((CDRMSoapRequest *)v93, v53, v54);
        if ( Request < 0 )
          break;
        Request = CDRMSoapRequest::AddHeaderParameter(v93, v55, L"MinimumVersion");
        if ( Request < 0 )
          break;
        Request = CDRMSoapRequest::AddHeaderParameter(v93, v56, L"MaximumVersion");
        if ( Request < 0 )
          break;
        v57 = 0;
        v58 = 0;
        if ( !v51 )
          goto LABEL_131;
        v59 = v97;
        do
        {
          if ( v57 == 25 )
            break;
          v60 = 4LL * v58;
          if ( LODWORD(v4[v60 + 3]) != 1 )
          {
            Request = CDRMSoapRequest::AddParam(v93, 1, 0, L"string", 3, v4[v60]);
            if ( Request < 0 )
              goto LABEL_138;
            LODWORD(v4[v60 + 3]) = 1;
            LODWORD(v98) = (_DWORD)v98 + 1;
            ++v57;
            v59 = v97;
          }
          ++v58;
        }
        while ( v58 < v59 );
        if ( !v57 )
          goto LABEL_131;
        if ( !WaitForSingleObject(*((HANDLE *)a1 + 5), 0) )
        {
          Request = -2147168447;
          break;
        }
        v61 = CDRMSoapRequest::DispatchRequest((CDRMSoapRequest *)v93, 0, 0);
        Request = v61;
        if ( v61 == -2147168300 )
        {
          PrintFaultCode((struct CDRMSoapRequest *)v93);
          Request = -(CDRMSoapRequest::IsExceptionType((CDRMSoapRequest *)v93, L"System.UnauthorizedAccessException") != 0)
                  - 2147168444;
          break;
        }
        if ( v61 < 0 )
        {
          _RTLTRACE("[msdrm]: AILTProc FAILED : %x ", v61);
          break;
        }
        v62 = (unsigned int)v94;
        if ( !(_DWORD)v94 )
          goto LABEL_131;
        if ( (unsigned int)v94 > 0x19 )
        {
          Request = -2147168441;
          break;
        }
        if ( v71 )
        {
          `eh vector destructor iterator'(
            v71,
            0x20u,
            *((_QWORD *)v71 - 1),
            (void (*)(void *))TemplateGuidData::~TemplateGuidData);
          operator delete(v71 - 8);
        }
        v63 = 32 * v62;
        if ( !is_mul_ok(v62, 0x20u) )
          v63 = -1;
        v28 = __CFADD__(v63, 8);
        v64 = v63 + 8;
        if ( v28 )
          v64 = -1;
        v65 = (unsigned __int64 *)operator new(v64);
        v86 = v65;
        if ( v65 )
        {
          *v65 = v62;
          v10 = (char *)(v65 + 1);
          v71 = (char *)(v65 + 1);
          `eh vector constructor iterator'(
            v65 + 1,
            0x20u,
            v62,
            (void (*)(void *))TemplateGuidData::TemplateGuidData,
            (void (*)(void *))TemplateGuidData::~TemplateGuidData);
        }
        else
        {
          v10 = 0;
          v71 = 0;
        }
        if ( !v10 )
        {
          Request = -2147024882;
LABEL_133:
          v3 = v96;
          goto LABEL_79;
        }
        v67 = 0;
        if ( (_DWORD)v62 )
        {
          do
          {
            v68 = (unsigned __int16 **)&v10[32 * v67];
            Request = CDRMSoapRequest::GetElementValue((CDRMSoapRequest *)v93, v66, L"Guid", v67, v68);
            if ( Request < 0 )
              goto LABEL_138;
            Request = CDRMSoapRequest::GetElementValue((CDRMSoapRequest *)v93, v69, L"Hash", v67, v68 + 1);
            if ( Request == -2147024882 )
              goto LABEL_138;
            Request = CDRMSoapRequest::GetElementValue((CDRMSoapRequest *)v93, v70, L"Template", v67, v68 + 2);
            if ( Request == -2147024882 )
              goto LABEL_138;
            Request = StoreTemplate((struct TemplateGuidData *)v68, v76);
            v10 = v71;
            if ( Request < 0 )
              goto LABEL_133;
          }
          while ( ++v67 < (unsigned int)v62 );
        }
        v51 = v97;
        v4 = v73;
        if ( (_DWORD)v98 == v97 )
          goto LABEL_131;
      }
    }
    else
    {
LABEL_131:
      Request = 315140;
    }
LABEL_138:
    v3 = v96;
LABEL_139:
    v10 = v71;
    goto LABEL_79;
  }
  Request = -2147024882;
  v2 = v95;
LABEL_6:
  v10 = 0;
LABEL_7:
  operator delete(Block);
  Block = 0;
  operator delete(v80);
  operator delete(v75);
  v75 = 0;
  operator delete(v76);
  if ( v73 )
  {
    `eh vector destructor iterator'(
      v73,
      0x20u,
      (unsigned __int64)*(v73 - 1),
      (void (*)(void *))TemplateGuidData::~TemplateGuidData);
    operator delete(v73 - 1);
  }
  if ( v10 )
  {
    `eh vector destructor iterator'(
      v10,
      0x20u,
      *((_QWORD *)v10 - 1),
      (void (*)(void *))TemplateGuidData::~TemplateGuidData);
    operator delete(v10 - 8);
  }
  v95 = v2;
  CDRMCBase::DeleteArrayofString(&v77, &v95);
  v95 = v2;
  CDRMCBase::DeleteArrayofString(&v82, &v95);
  v95 = v2;
  CDRMCBase::DeleteArrayofString(&v81, &v95);
  v95 = v3;
  CDRMCBase::DeleteArrayofString(&v78, &v95);
  v95 = v3;
  CDRMCBase::DeleteArrayofString(&v83, &v95);
  v95 = v3;
  CDRMCBase::DeleteArrayofString(&v79, &v95);
  v11 = (void *)*((_QWORD *)a1 + 4);
  if ( v11 )
    SetEvent(v11);
  v12 = (void *)*((_QWORD *)a1 + 5);
  if ( v12 )
    CloseHandle(v12);
  operator delete(*((void **)a1 + 3));
  *((_QWORD *)a1 + 3) = 0;
  operator delete(a1);
  if ( v5 )
    v5(6, (unsigned int)Request, 0, v84);
LABEL_17:
  CDRMSoapRequest::~CDRMSoapRequest((CDRMSoapRequest *)v93);
  CDRMSoapRequest::~CDRMSoapRequest((CDRMSoapRequest *)v87);
  return 0;
}

```

## disassembly

```asm
0x18001cd10  push    rbp
0x18001cd12  push    rbx
0x18001cd13  push    rsi
0x18001cd14  push    rdi
0x18001cd15  push    r12
0x18001cd17  push    r13
0x18001cd19  push    r14
0x18001cd1b  push    r15
0x18001cd1d  lea     rbp, [rsp-1E8h]
0x18001cd25  sub     rsp, 2E8h
0x18001cd2c  mov     [rbp+220h+var_270], 0FFFFFFFFFFFFFFFEh
0x18001cd34  mov     rsi, rcx
0x18001cd37  lea     rcx, [rbp+220h+var_260]; this
0x18001cd3b  call    ??0CDRMSoapRequest@@QEAA@XZ; CDRMSoapRequest::CDRMSoapRequest(void)
0x18001cd40  nop
0x18001cd41  lea     rcx, [rbp+220h+var_150]; this
0x18001cd48  call    ??0CDRMSoapRequest@@QEAA@XZ; CDRMSoapRequest::CDRMSoapRequest(void)
0x18001cd4d  nop
0x18001cd4e  xor     edi, edi
0x18001cd50  mov     [rsp+320h+Block], rdi
0x18001cd55  mov     [rsp+320h+var_2C0], rdi
0x18001cd5a  mov     [rsp+320h+var_2B8], rdi
0x18001cd5f  mov     r14d, edi
0x18001cd62  mov     [rbp+220h+arg_0], edi
0x18001cd68  mov     [rsp+320h+var_2B0], rdi
0x18001cd6d  mov     [rbp+220h+var_288], rdi
0x18001cd71  mov     [rbp+220h+var_290], rdi
0x18001cd75  mov     r12d, edi
0x18001cd78  mov     [rbp+220h+arg_8], edi
0x18001cd7e  mov     [rsp+320h+var_2A8], rdi
0x18001cd83  mov     [rbp+220h+var_280], rdi
0x18001cd87  mov     [rbp+220h+var_2A0], rdi
0x18001cd8b  test    rsi, rsi
0x18001cd8e  jz      loc_18001CF80
0x18001cd94  mov     r13d, edi
0x18001cd97  mov     [rsp+320h+var_2D0], rdi
0x18001cd9c  mov     [rsp+320h+var_2E0], rdi
0x18001cda1  mov     r15, [rsi+8]
0x18001cda5  mov     [rsp+320h+var_2D8], r15
0x18001cdaa  mov     rax, [rsi+10h]
0x18001cdae  mov     [rbp+220h+var_278], rax
0x18001cdb2  mov     [rbp+220h+var_258], r15
0x18001cdb6  mov     [rbp+220h+var_250], 6
0x18001cdbd  mov     [rbp+220h+var_248], rax
0x18001cdc1  mov     rax, [rsi+28h]
0x18001cdc5  mov     [rbp+220h+var_210], rax
0x18001cdc9  mov     rcx, [rsi+18h]
0x18001cdcd  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001cdd1  mov     rax, r8
0x18001cdd4  inc     rax
0x18001cdd7  cmp     [rcx+rax*2], di
0x18001cddb  jnz     short loc_18001CDD4
0x18001cddd  lea     rbx, [rax+1Bh]
0x18001cde1  mov     eax, 2
0x18001cde6  mul     rbx
0x18001cde9  cmovb   rax, r8
0x18001cded  mov     rcx, rax; Size
0x18001cdf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cdf5  mov     r11, rax
0x18001cdf8  mov     [rbp+220h+var_298], rax
0x18001cdfc  test    rax, rax
0x18001cdff  jnz     loc_18001CFAC
0x18001ce05  mov     edi, 8007000Eh
0x18001ce0a  mov     r14d, [rbp+220h+arg_0]
0x18001ce11  mov     r13, r12
0x18001ce14  mov     rcx, [rsp+320h+Block]; Block
0x18001ce19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ce1e  mov     [rsp+320h+Block], 0
0x18001ce27  mov     rcx, [rbp+220h+var_298]; Block
0x18001ce2b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ce30  mov     rcx, [rsp+320h+var_2C0]; Block
0x18001ce35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ce3a  mov     [rsp+320h+var_2C0], 0
0x18001ce43  mov     rcx, [rsp+320h+var_2B8]; Block
0x18001ce48  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ce4d  mov     rax, [rsp+320h+var_2D0]
0x18001ce52  test    rax, rax
0x18001ce55  jz      short loc_18001CE7B
0x18001ce57  lea     rbx, [rax-8]
0x18001ce5b  lea     r9, ??1TemplateGuidData@@QEAA@XZ; void (*)(void *)
0x18001ce62  mov     r8, [rbx]; unsigned __int64
0x18001ce65  mov     edx, 20h ; ' '; unsigned __int64
0x18001ce6a  mov     rcx, rax; void *
0x18001ce6d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001ce72  mov     rcx, rbx; Block
0x18001ce75  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ce7a  nop
0x18001ce7b  test    r13, r13
0x18001ce7e  jz      short loc_18001CEA2
0x18001ce80  lea     r9, ??1TemplateGuidData@@QEAA@XZ; void (*)(void *)
0x18001ce87  mov     r8, [r13-8]; unsigned __int64
0x18001ce8b  mov     edx, 20h ; ' '; unsigned __int64
0x18001ce90  mov     rcx, r13; void *
0x18001ce93  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001ce98  lea     rcx, [r13-8]; Block
0x18001ce9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cea1  nop
0x18001cea2  mov     [rbp+220h+arg_0], r14d
0x18001cea9  lea     rdx, [rbp+220h+arg_0]; unsigned int *
0x18001ceb0  lea     rcx, [rsp+320h+var_2B0]; unsigned __int16 ***
0x18001ceb5  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x18001ceba  mov     [rbp+220h+arg_0], r14d
0x18001cec1  lea     rdx, [rbp+220h+arg_0]; unsigned int *
0x18001cec8  lea     rcx, [rbp+220h+var_288]; unsigned __int16 ***
0x18001cecc  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x18001ced1  mov     [rbp+220h+arg_0], r14d
0x18001ced8  lea     rdx, [rbp+220h+arg_0]; unsigned int *
0x18001cedf  lea     rcx, [rbp+220h+var_290]; unsigned __int16 ***
0x18001cee3  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x18001cee8  mov     [rbp+220h+arg_0], r12d
0x18001ceef  lea     rdx, [rbp+220h+arg_0]; unsigned int *
0x18001cef6  lea     rcx, [rsp+320h+var_2A8]; unsigned __int16 ***
0x18001cefb  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x18001cf00  mov     [rbp+220h+arg_0], r12d
0x18001cf07  lea     rdx, [rbp+220h+arg_0]; unsigned int *
0x18001cf0e  lea     rcx, [rbp+220h+var_280]; unsigned __int16 ***
0x18001cf12  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x18001cf17  mov     [rbp+220h+arg_0], r12d
0x18001cf1e  lea     rdx, [rbp+220h+arg_0]; unsigned int *
0x18001cf25  lea     rcx, [rbp+220h+var_2A0]; unsigned __int16 ***
0x18001cf29  call    ?DeleteArrayofString@CDRMCBase@@SAJPEAPEAPEAGPEAI@Z; CDRMCBase::DeleteArrayofString(ushort * * *,uint *)
0x18001cf2e  mov     rcx, [rsi+20h]; hEvent
0x18001cf32  test    rcx, rcx
0x18001cf35  jz      short loc_18001CF3D
0x18001cf37  call    cs:__imp_SetEvent
0x18001cf3d  mov     rcx, [rsi+28h]; hObject
0x18001cf41  test    rcx, rcx
0x18001cf44  jz      short loc_18001CF4C
0x18001cf46  call    cs:__imp_CloseHandle
0x18001cf4c  mov     rcx, [rsi+18h]; Block
0x18001cf50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cf55  mov     qword ptr [rsi+18h], 0
0x18001cf5d  mov     rcx, rsi; Block
0x18001cf60  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cf65  test    r15, r15
0x18001cf68  jz      short loc_18001CF80
0x18001cf6a  mov     r9, [rbp+220h+var_278]
0x18001cf6e  xor     r8d, r8d
0x18001cf71  mov     edx, edi
0x18001cf73  lea     ecx, [r8+6]
0x18001cf77  mov     rax, r15
0x18001cf7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf7f  nop
0x18001cf80  lea     rcx, [rbp+220h+var_150]; this
0x18001cf87  call    ??1CDRMSoapRequest@@UEAA@XZ; CDRMSoapRequest::~CDRMSoapRequest(void)
0x18001cf8c  nop
0x18001cf8d  lea     rcx, [rbp+220h+var_260]; this
0x18001cf91  call    ??1CDRMSoapRequest@@UEAA@XZ; CDRMSoapRequest::~CDRMSoapRequest(void)
0x18001cf96  xor     eax, eax
0x18001cf98  add     rsp, 2E8h
0x18001cf9f  pop     r15
0x18001cfa1  pop     r14
0x18001cfa3  pop     r13
0x18001cfa5  pop     r12
0x18001cfa7  pop     rdi
0x18001cfa8  pop     rsi
0x18001cfa9  pop     rbx
0x18001cfaa  pop     rbp
0x18001cfab  retn
0x18001cfac  mov     r8, [rsi+18h]; unsigned __int16 *
0x18001cfb0  mov     rdx, rbx; unsigned __int64
0x18001cfb3  mov     rcx, r11; unsigned __int16 *
0x18001cfb6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001cfbb  mov     edi, eax
0x18001cfbd  test    eax, eax
0x18001cfbf  js      loc_18001CE11
0x18001cfc5  lea     r8, ?g_wszAILT_GetAcquireTemplatesPadding@@3QBGB; "/templatedistribution.asmx"
0x18001cfcc  mov     rdx, rbx; unsigned __int64
0x18001cfcf  mov     rcx, r11; unsigned __int16 *
0x18001cfd2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001cfd7  mov     edi, eax
0x18001cfd9  test    eax, eax
0x18001cfdb  js      loc_18001CE11
0x18001cfe1  mov     r8d, [rsi+30h]
0x18001cfe5  not     r8d
0x18001cfe8  and     r8d, 1
0x18001cfec  shl     r8d, 4; unsigned int
0x18001cff0  mov     rdx, [rbp+220h+var_298]; unsigned __int16 *
0x18001cff4  lea     rcx, [rbp+220h+var_260]; this
0x18001cff8  call    ?SetServerInfo@CHttpBase@@QEAAJPEBGI0@Z; CHttpBase::SetServerInfo(ushort const *,uint,ushort const *)
0x18001cffd  mov     edi, eax
0x18001cfff  test    eax, eax
0x18001d001  js      loc_18001CE11
0x18001d007  lea     r8, ?g_wszAILT_GetAcquireTemplatesInformation@@3QBGB; "AcquireTemplateInformation"
0x18001d00e  lea     rdx, ?g_wszAILTTemplateDistributionService@@3QBGB; "TemplateDistributionService"
0x18001d015  lea     rcx, [rbp+220h+var_260]; this
0x18001d019  call    ?SetServerMethod@CDRMSoapRequest@@QEAAJPEBG0@Z; CDRMSoapRequest::SetServerMethod(ushort const *,ushort const *)
0x18001d01e  mov     edi, eax
0x18001d020  test    eax, eax
0x18001d022  js      loc_18001CE11
0x18001d028  mov     dword ptr [rsp+320h+var_300], 1; unsigned int
0x18001d030  lea     r9, ?g_wszAILTTemplateDistributionServiceNameSpace@@3QBGB; "http://microsoft.com/DRM/TemplateDistri"...
0x18001d037  xor     r8d, r8d; unsigned __int16 *
0x18001d03a  lea     rdx, ?g_wszAILT_GetAcquireTemplatesInformation@@3QBGB; "AcquireTemplateInformation"
0x18001d041  lea     rcx, [rbp+220h+var_260]; this
0x18001d045  call    ?CreateRequest@CDRMSoapRequest@@QEAAJPEBG00I@Z; CDRMSoapRequest::CreateRequest(ushort const *,ushort const *,ushort const *,uint)
0x18001d04a  mov     edi, eax
0x18001d04c  test    eax, eax
0x18001d04e  js      loc_18001CE11
0x18001d054  lea     rcx, [rbp+220h+var_260]; this
0x18001d058  call    ?CreateHeader@CDRMSoapRequest@@QEAAJPEBGI@Z; CDRMSoapRequest::CreateHeader(ushort const *,uint)
0x18001d05d  mov     edi, eax
0x18001d05f  test    eax, eax
0x18001d061  js      loc_18001CE11
0x18001d067  lea     r8, ?g_wszACT_MinimumVersion@@3QBGB; "MinimumVersion"
0x18001d06e  lea     rcx, [rbp+220h+var_260]
0x18001d072  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x18001d077  mov     edi, eax
0x18001d079  test    eax, eax
0x18001d07b  js      loc_18001CE11
0x18001d081  lea     r8, ?g_wszACT_MaximumVersion@@3QBGB; "MaximumVersion"
0x18001d088  lea     rcx, [rbp+220h+var_260]
0x18001d08c  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x18001d091  mov     edi, eax
0x18001d093  test    eax, eax
0x18001d095  js      loc_18001CE11
0x18001d09b  xor     edx, edx; dwMilliseconds
0x18001d09d  mov     rcx, [rsi+28h]; hHandle
0x18001d0a1  call    cs:__imp_WaitForSingleObject
0x18001d0a7  test    eax, eax
0x18001d0a9  jnz     short loc_18001D0B5
0x18001d0ab  mov     edi, 8004CF41h
0x18001d0b0  jmp     loc_18001CE11
0x18001d0b5  xor     r8d, r8d; unsigned int
0x18001d0b8  xor     edx, edx; unsigned __int8 *
0x18001d0ba  lea     rcx, [rbp+220h+var_260]; this
0x18001d0be  call    ?DispatchRequest@CDRMSoapRequest@@UEAAJPEAEI@Z; CDRMSoapRequest::DispatchRequest(uchar *,uint)
0x18001d0c3  mov     edi, eax
0x18001d0c5  cmp     eax, 8004CFD4h
0x18001d0ca  jnz     short loc_18001D0F4
0x18001d0cc  lea     rcx, [rbp+220h+var_260]; this
0x18001d0d0  call    ?PrintFaultCode@@YAXPEAVCDRMSoapRequest@@@Z; PrintFaultCode(CDRMSoapRequest *)
0x18001d0d5  lea     rdx, ?g_wszACT_UnauthAccessException@@3QBGB; "System.UnauthorizedAccessException"
0x18001d0dc  lea     rcx, [rbp+220h+var_260]; this
0x18001d0e0  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x18001d0e5  neg     eax
0x18001d0e7  sbb     edi, edi
0x18001d0e9  add     edi, 8004CF44h
0x18001d0ef  jmp     loc_18001CE11
0x18001d0f4  test    eax, eax
0x18001d0f6  jns     short loc_18001D10B
0x18001d0f8  mov     edx, eax
0x18001d0fa  lea     rcx, aMsdrmAiltprocF; "[msdrm]: AILTProc FAILED : %x "
0x18001d101  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18001d106  jmp     loc_18001CE11
0x18001d10b  lea     rax, [rsp+320h+var_2C0]
0x18001d110  mov     [rsp+320h+var_300], rax; unsigned __int16 **
0x18001d115  xor     r9d, r9d; unsigned int
0x18001d118  lea     r8, aServerpublicke; "ServerPublicKey"
0x18001d11f  xor     edx, edx; unsigned __int16 *
0x18001d121  lea     rcx, [rbp+220h+var_260]; this
0x18001d125  call    ?GetParameterValue@CDRMSoapRequest@@QEAAJPEBG0IPEAPEAG@Z; CDRMSoapRequest::GetParameterValue(ushort const *,ushort const *,uint,ushort * *)
0x18001d12a  mov     edi, eax
0x18001d12c  test    eax, eax
0x18001d12e  js      loc_18001CE11
0x18001d134  lea     rax, [rsp+320h+Block]
0x18001d139  mov     [rsp+320h+var_300], rax; unsigned __int16 **
0x18001d13e  xor     r9d, r9d; unsigned int
0x18001d141  lea     r8, aGuidhashcount; "GuidHashCount"
0x18001d148  xor     edx, edx; unsigned __int16 *
0x18001d14a  lea     rcx, [rbp+220h+var_260]; this
0x18001d14e  call    ?GetParameterValue@CDRMSoapRequest@@QEAAJPEBG0IPEAPEAG@Z; CDRMSoapRequest::GetParameterValue(ushort const *,ushort const *,uint,ushort * *)
0x18001d153  mov     edi, eax
0x18001d155  test    eax, eax
0x18001d157  js      loc_18001CE11
0x18001d15d  lea     rdx, [rsp+320h+var_2B8]; unsigned __int16 **
0x18001d162  mov     rcx, [rsp+320h+var_2C0]; unsigned __int16 *
0x18001d167  call    ?CreateDigest@@YAJPEBGPEAPEAG@Z; CreateDigest(ushort const *,ushort * *)
0x18001d16c  mov     edi, eax
0x18001d16e  test    eax, eax
0x18001d170  js      loc_18001CE11
0x18001d176  lea     rax, [rbp+220h+var_288]
0x18001d17a  mov     [rsp+320h+var_2E8], rax
0x18001d17f  lea     rax, [rsp+320h+var_2B0]
0x18001d184  mov     [rsp+320h+var_2F0], rax
0x18001d189  lea     rax, [rbp+220h+arg_0]
0x18001d190  mov     [rsp+320h+var_2F8], rax
0x18001d195  mov     dword ptr [rsp+320h+var_300], r12d
0x18001d19a  lea     r9, [rsp+320h+var_2B8]
0x18001d19f  mov     ecx, 5
0x18001d1a4  lea     r8d, [rcx-4]
0x18001d1a8  call    ?GetPersistedLicenseEx@@YAJW4DRM_LICENSE_TYPE@@HIPEAPEAGIPEAIPEAPEAPEAG3@Z; GetPersistedLicenseEx(DRM_LICENSE_TYPE,int,uint,ushort * *,uint,uint *,ushort * * *,ushort * * *)
0x18001d1ad  xor     edi, edi
0x18001d1af  cmp     eax, 8004CF3Ah
0x18001d1b4  cmovnz  edi, eax
0x18001d1b7  mov     r14d, [rbp+220h+arg_0]
0x18001d1be  test    edi, edi
0x18001d1c0  js      loc_18001CE11
0x18001d1c6  lea     r8, [rbp+220h+var_290]; unsigned __int16 ***
0x18001d1ca  mov     rdx, [rsp+320h+var_2B0]; unsigned __int16 **
0x18001d1cf  mov     ecx, r14d; unsigned int
0x18001d1d2  call    ?GetUnMaskedFileNames@@YAJIPEAPEAGPEAPEAPEAG@Z; GetUnMaskedFileNames(uint,ushort * *,ushort * * *)
0x18001d1d7  mov     edi, eax
0x18001d1d9  test    eax, eax
0x18001d1db  js      loc_18001CE11
0x18001d1e1  mov     rcx, [rsp+320h+Block]; String
0x18001d1e6  call    cs:__imp__wtoi
0x18001d1ec  mov     [rbp+220h+arg_10], eax
0x18001d1f2  xor     ecx, ecx
0x18001d1f4  test    eax, eax
  ... truncated ...
```
