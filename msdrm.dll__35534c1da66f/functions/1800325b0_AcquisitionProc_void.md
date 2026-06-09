# AcquisitionProc(void *)

- ea: `0x1800325b0`
- end: `0x180032f52`
- name: `?AcquisitionProc@@YAIPEAX@Z`
- size: `2466`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `29`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x1800046c8`
- `0x18001b080`
- `0x1800325b0`
- `0x180032f58`
- `0x1800331d8`
- `0x180034504`
- `0x180035cd8`
- `0x180037320`
- `0x180038ff0`
- `0x180039bb4`
- `0x180039c80`
- `0x18003a3f8`
- `0x18003ad20`
- `0x180047678`
- `0x1800476f0`
- `0x180047758`
- `0x180047c38`
- `0x180047c68`
- `0x180048764`
- `0x180048b20`
- `0x180048edc`
- `0x18004ab54`
- `0x18004ac50`
- `0x18004b218`
- `0x18005bd72`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003271e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032bdd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032c9c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032cb3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003271e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032bdd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032c9c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180032cb3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180032e41`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180032e41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032e50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032e50`

## string_xrefs

- `0x18003268a`: `http://microsoft.com/DRM/LicensingService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AcquisitionProc(void *a1)
{
  void *v2; // r8
  WCHAR **v3; // r14
  unsigned __int64 v4; // r12
  UINT v5; // r15d
  void (__fastcall *v6)(_QWORD, _QWORD, _QWORD, _QWORD); // r13
  const unsigned __int16 *v7; // rdx
  HRESULT Request; // ebx
  unsigned int v9; // r8d
  __int64 v10; // rdx
  __int64 v11; // rdx
  int v12; // edx
  HRESULT v13; // eax
  __int64 v14; // rdx
  bool v15; // sf
  WCHAR *v16; // rax
  UINT i; // edx
  UINT v18; // esi
  _QWORD *v19; // rbx
  UINT j; // r9d
  WCHAR *v21; // rax
  __int64 v22; // rdx
  unsigned int v23; // esi
  int v24; // eax
  int v25; // eax
  int v26; // r15d
  unsigned int v27; // r12d
  unsigned int v28; // r13d
  __int64 v29; // r14
  unsigned __int64 v30; // r15
  WCHAR *v31; // rax
  PWSTR v32; // rsi
  __int64 v33; // rbx
  unsigned __int16 *v34; // r14
  unsigned int v35; // esi
  void *v36; // rcx
  __int16 v37; // r11
  __int64 v38; // rax
  unsigned __int16 *v39; // rsi
  bool v40; // r8
  bool v41; // r9
  __int64 v42; // rdx
  HRESULT v43; // eax
  void **v44; // r14
  unsigned int v45; // esi
  unsigned int k; // r15d
  void **v47; // r15
  unsigned int v48; // esi
  UINT m; // r14d
  void *v50; // rcx
  void *v51; // rcx
  int v52; // ecx
  bool v53; // zf
  int v54; // ecx
  __int64 v55; // rdx
  void (__fastcall *v57)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+70h] [rbp-90h]
  void *Block; // [rsp+78h] [rbp-88h] BYREF
  PWSTR wszLicense; // [rsp+80h] [rbp-80h]
  int v60; // [rsp+88h] [rbp-78h]
  UINT v61; // [rsp+8Ch] [rbp-74h]
  unsigned __int16 *v62; // [rsp+90h] [rbp-70h] BYREF
  struct _DRM_CRYPTO_VERSION_PARAMETERS *v63; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v64; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v65; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v66; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v67; // [rsp+B8h] [rbp-48h] BYREF
  struct _DRM_CRYPTO_VERSION_PARAMETERS *v68; // [rsp+C0h] [rbp-40h] BYREF
  struct _DRM_CRYPTO_VERSION_PARAMETERS *v69; // [rsp+C8h] [rbp-38h] BYREF
  void *v70; // [rsp+D0h] [rbp-30h]
  void *v71; // [rsp+D8h] [rbp-28h]
  __int64 v72; // [rsp+E0h] [rbp-20h]
  __int64 v73; // [rsp+E8h] [rbp-18h]
  char v74[8]; // [rsp+F0h] [rbp-10h] BYREF
  void (__fastcall *v75)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+F8h] [rbp-8h]
  int v76; // [rsp+100h] [rbp+0h]
  __int64 v77; // [rsp+108h] [rbp+8h]
  __int64 v78; // [rsp+140h] [rbp+40h]
  UINT v79; // [rsp+250h] [rbp+150h] BYREF
  UINT pcCert; // [rsp+258h] [rbp+158h] BYREF
  unsigned int v81; // [rsp+260h] [rbp+160h] BYREF
  int v82; // [rsp+268h] [rbp+168h] BYREF

  v73 = -2;
  _RTLTRACE("[msdrm]:+AcquisitionProc");
  v82 = 0;
  CDRMSoapRequest::CDRMSoapRequest((CDRMSoapRequest *)v74);
  v81 = (unsigned int)v2;
  Block = v2;
  v62 = (unsigned __int16 *)v2;
  pcCert = (unsigned int)v2;
  v79 = (unsigned int)v2;
  v69 = (struct _DRM_CRYPTO_VERSION_PARAMETERS *)v2;
  v68 = (struct _DRM_CRYPTO_VERSION_PARAMETERS *)v2;
  v63 = (struct _DRM_CRYPTO_VERSION_PARAMETERS *)v2;
  v64 = (unsigned __int16 *)v2;
  v65 = (unsigned __int16 *)v2;
  v66 = (unsigned __int16 *)v2;
  v67 = (unsigned __int16 *)v2;
  if ( a1 )
  {
    v3 = (WCHAR **)(unsigned int)v2;
    v70 = v2;
    v60 = (int)v2;
    wszLicense = (PWSTR)v2;
    v4 = (unsigned int)v2;
    v71 = v2;
    v5 = (unsigned int)v2;
    v61 = (unsigned int)v2;
    v6 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)a1 + 10);
    v57 = v6;
    v72 = *((_QWORD *)a1 + 11);
    v75 = v6;
    v76 = 2;
    v77 = v72;
    v78 = *((_QWORD *)a1 + 12);
    Request = CDRMSoapRequest::CreateRequest(
                (CDRMSoapRequest *)v74,
                L"AcquireLicense",
                L"RequestParams",
                L"http://microsoft.com/DRM/LicensingService",
                1u);
    if ( Request < 0 )
      goto LABEL_79;
    Request = CDRMSoapRequest::CreateHeader((CDRMSoapRequest *)v74, v7, v9);
    if ( Request < 0 )
      goto LABEL_79;
    Request = CDRMSoapRequest::AddHeaderParameter(v74, v10, L"MinimumVersion");
    if ( Request < 0 )
      goto LABEL_79;
    Request = CDRMSoapRequest::AddHeaderParameter(v74, v11, L"MaximumVersion");
    if ( Request < 0 )
      goto LABEL_79;
    Request = CDRMSoapRequest::AddStruct((CDRMSoapRequest *)v74, v12, L"AcquireLicenseParams", (int)v4 + 7);
    if ( Request < 0 )
      goto LABEL_79;
    if ( !WaitForSingleObject(*((HANDLE *)a1 + 12), 0) )
    {
      Request = -2147168447;
      goto LABEL_79;
    }
    v13 = DRMDeconstructCertificateChain(*((PWSTR *)a1 + 5), 0, &pcCert, 0);
    v15 = v13 < 0;
    if ( !v13 )
    {
      v3 = (WCHAR **)operator new(8u);
      v70 = v3;
      if ( !v3 || (v16 = (WCHAR *)operator new(saturated_mul(pcCert + 1, 2u)), (*v3 = v16) == 0) )
      {
LABEL_11:
        Request = -2147024882;
        goto LABEL_79;
      }
      v13 = DRMDeconstructCertificateChain(*((PWSTR *)a1 + 5), 0, &pcCert, v16);
      v60 = 1;
      v15 = v13 < 0;
    }
    if ( v15 )
    {
      _RTLTRACE(" [msdrm]:AcquisitionProc  DRMDeconstructCertificateChain for User Cert returned hr = %x ", v13);
      Request = -2147168460;
      goto LABEL_79;
    }
    Request = CDRMSoapRequest::AddArray(v74, v14, L"AcquireLicenseParams", L"LicenseeCerts");
    if ( Request < 0 )
      goto LABEL_79;
    for ( i = 0; !DRMDeconstructCertificateChain(*((PWSTR *)a1 + 4), i, &v79, 0); i = v18 )
    {
      v18 = v5 + 1;
      v19 = operator new(saturated_mul(v5 + 1, 8u));
      if ( !v19 )
        goto LABEL_11;
      for ( j = 0; j < v5; ++j )
        v19[j] = *(_QWORD *)(v4 + 8LL * j);
      operator delete((void *)v4);
      v4 = (unsigned __int64)v19;
      v71 = v19;
      v21 = (WCHAR *)operator new(saturated_mul(v79 + 1, 2u));
      v19[v5] = v21;
      if ( !v21 )
        goto LABEL_11;
      Request = DRMDeconstructCertificateChain(*((PWSTR *)a1 + 4), v5, &v79, v21);
      if ( Request < 0 )
        goto LABEL_79;
      ++v5;
      v61 = v18;
    }
    Request = ParseHeaderInfo(*v3, 0, 0, 0, 0, 0, 0, &v66, &v67, 0, 0, 0, 0, &v63);
    if ( Request < 0
      || (Request = ParseHeaderInfo(*(unsigned __int16 **)v4, 0, 0, 0, 0, 0, 0, &v64, &v65, 0, 0, 0, 0, &v68),
          v23 = 0,
          Request < 0) )
    {
LABEL_79:
      operator delete(0);
      operator delete(Block);
      operator delete(wszLicense);
      operator delete(v62);
      operator delete(v64);
      operator delete(v65);
      operator delete(v66);
      operator delete(v67);
      v44 = (void **)v70;
      if ( v70 )
      {
        v45 = 0;
        for ( k = v60; v45 < k; ++v45 )
          operator delete(v44[v45]);
        operator delete(v44);
      }
      v47 = (void **)v71;
      if ( v71 )
      {
        v48 = 0;
        for ( m = v61; v48 < m; ++v48 )
          operator delete(v47[v48]);
        operator delete(v47);
      }
      v50 = (void *)*((_QWORD *)a1 + 13);
      if ( v50 )
        SetEvent(v50);
      v51 = (void *)*((_QWORD *)a1 + 12);
      if ( v51 )
        CloseHandle(v51);
      operator delete(*(void **)a1);
      operator delete(*((void **)a1 + 1));
      operator delete(*((void **)a1 + 2));
      operator delete(*((void **)a1 + 4));
      operator delete(*((void **)a1 + 5));
      operator delete(*((void **)a1 + 7));
      operator delete(*((void **)a1 + 6));
      operator delete(a1);
      if ( Request >= 0 )
      {
        v55 = 315140;
        goto LABEL_108;
      }
      if ( Request > -2147168440 )
      {
        if ( (unsigned int)(Request + 2147168438) > 0x12 || (v54 = 393221, !_bittest(&v54, Request + 2147168438)) )
        {
          if ( Request == -2147168304 )
          {
            Request = -2147168441;
          }
          else
          {
            if ( Request != -2147168300 )
            {
              v53 = Request == -2147024882;
LABEL_101:
              if ( !v53 )
                Request = -2147168460;
              goto LABEL_105;
            }
            Request = -2147168444;
          }
        }
      }
      else if ( (unsigned int)(Request + 2147168453) > 0xD || (v52 = 12879, !_bittest(&v52, Request + 2147168453)) )
      {
        v53 = Request == -2147168507;
        goto LABEL_101;
      }
LABEL_105:
      if ( !v6 )
      {
LABEL_109:
        _RTLTRACE("[msdrm]:-AcquisitionProc");
        goto LABEL_110;
      }
      v55 = (unsigned int)Request;
LABEL_108:
      v6(2, v55, 0, v72);
      goto LABEL_109;
    }
    if ( *(_DWORD *)v63 < *(_DWORD *)v68 )
    {
      _RTLTRACE(" [msdrm]:AcquisitionProc IL and GIC have different crypto modes. Checking if this is a crypto upgrade...");
      v24 = CheckForCryptoUpgrade(v66, v67, v64, v65);
      if ( v24 )
      {
        if ( v24 != 1 )
          goto LABEL_30;
      }
      else
      {
        DeleteAllV1LicensesForGIC(*v3);
      }
      Request = -2147168450;
      goto LABEL_79;
    }
LABEL_30:
    Request = CDRMSoapRequest::AddArray(v74, v22, L"AcquireLicenseParams", L"IssuanceLicense");
    if ( Request >= 0 )
    {
      Request = CDRMSoapRequest::AddParam(v74, 1, L"AcquireLicenseParams", L"ApplicationData", 3, *((_QWORD *)a1 + 6));
      if ( Request >= 0 )
      {
        v25 = PostServerRequest((struct CDRMSoapRequest *)v74, (const struct LicCallbackContext *)a1);
        Request = v25;
        if ( v25 == -2147168450 )
        {
          if ( CDRMSoapRequest::IsExceptionType(
                 (CDRMSoapRequest *)v74,
                 L"Microsoft.DigitalRightsManagement.Cryptography.UnsupportedCryptographicSetException") )
          {
            DeleteAllV1LicensesForGIC(*v3);
          }
        }
        else if ( v25 >= 0 )
        {
          Request = CDRMSoapRequest::GetParameterValueCount(
                      (CDRMSoapRequest *)v74,
                      L"AcquireLicenseResponse",
                      L"CertificateChain",
                      &v81);
          if ( Request >= 0 )
          {
            v26 = 0;
            v27 = -1;
            v28 = v81;
            if ( v81 )
            {
              while ( 1 )
              {
                operator delete(Block);
                Block = 0;
                Request = CDRMSoapRequest::GetParameterValue(
                            (CDRMSoapRequest *)v74,
                            L"AcquireLicenseResponse",
                            L"CertificateChain",
                            v23,
                            (unsigned __int16 **)&Block);
                if ( Request < 0 )
                  break;
                v29 = -1;
                do
                  ++v29;
                while ( *((_WORD *)Block + v29) );
                Request = IsEUL((unsigned __int16 *)Block, &v82);
                if ( Request < 0 )
                  break;
                v26 += v29;
                if ( v82 )
                  v27 = v23;
                if ( ++v23 >= v28 )
                  goto LABEL_47;
              }
            }
            else
            {
LABEL_47:
              v30 = (unsigned int)(v26 + 1);
              v31 = (WCHAR *)operator new(saturated_mul(v30, 2u));
              wszLicense = v31;
              if ( v31 )
              {
                memset_0(v31, 0, 2 * v30);
                Request = CDRMSoapRequest::GetParameterValue(
                            (CDRMSoapRequest *)v74,
                            L"AcquireLicenseResponse",
                            L"CertificateChain",
                            v27,
                            &v62);
                if ( Request >= 0 )
                {
                  v32 = wszLicense;
                  Request = StringCchCopyW(wszLicense, v30, v62);
                  if ( Request >= 0 )
                  {
                    v33 = -1;
                    do
                      ++v33;
                    while ( v62[v33] );
                    if ( !WaitForSingleObject(*((HANDLE *)a1 + 12), 0) )
                      goto LABEL_54;
                    v34 = &v32[v33];
                    v35 = 0;
                    if ( v28 )
                    {
                      v36 = Block;
                      do
                      {
                        if ( v35 != v27 )
                        {
                          operator delete(v36);
                          Block = 0;
                          Request = CDRMSoapRequest::GetParameterValue(
                                      (CDRMSoapRequest *)v74,
                                      L"AcquireLicenseResponse",
                                      L"CertificateChain",
                                      v35,
                                      (unsigned __int16 **)&Block);
                          if ( Request < 0 )
                            goto LABEL_78;
                          Request = StringCchCopyW(v34, v30 - (v34 - wszLicense), (const unsigned __int16 *)Block);
                          if ( Request < 0 )
                            goto LABEL_78;
                          v36 = Block;
                          v38 = -1;
                          do
                            ++v38;
                          while ( *((_WORD *)Block + v38) != v37 );
                          v34 += v38;
                        }
                      }
                      while ( ++v35 < v28 );
                    }
                    if ( WaitForSingleObject(*((HANDLE *)a1 + 12), 0) && WaitForSingleObject(*((HANDLE *)a1 + 12), 0) )
                    {
                      v39 = wszLicense;
                      Request = ParseHeaderInfo(wszLicense, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &v69);
                      if ( Request >= 0 )
                      {
                        if ( *(_DWORD *)v69 == *(_DWORD *)v63 )
                        {
                          Request = VerifyCertificateChain(v39, v69, v40, v41, 0);
                          if ( Request >= 0 )
                          {
                            if ( (unsigned int)IsLicenseExpired(v39) )
                            {
                              Request = -2147168436;
                            }
                            else
                            {
                              if ( (*((_BYTE *)a1 + 76) & 2) != 0 )
                                v43 = DRMAddLicense(*((_DWORD *)a1 + 16), 0, v39);
                              else
                                v43 = StoreAnyLicenseEx(2, v42, v39);
                              Request = v43;
                              if ( v43 >= 0 && (*((_BYTE *)a1 + 76) & 8) == 0 )
                                Request = FetchRevocationList(v62, 0, 0);
                            }
                          }
                        }
                        else
                        {
                          Request = -2147168492;
                        }
                      }
                    }
                    else
                    {
LABEL_54:
                      Request = -2147168447;
                    }
                  }
                }
              }
              else
              {
                Request = -2147024882;
              }
            }
LABEL_78:
            v6 = v57;
          }
        }
      }
    }
    goto LABEL_79;
  }
LABEL_110:
  CDRMSoapRequest::~CDRMSoapRequest((CDRMSoapRequest *)v74);
  return 0;
}

```

## disassembly

```asm
0x1800325b0  push    rbp
0x1800325b2  push    rbx
0x1800325b3  push    rsi
0x1800325b4  push    rdi
0x1800325b5  push    r12
0x1800325b7  push    r13
0x1800325b9  push    r14
0x1800325bb  push    r15
0x1800325bd  lea     rbp, [rsp-108h]
0x1800325c5  sub     rsp, 208h
0x1800325cc  mov     [rbp+140h+var_158], 0FFFFFFFFFFFFFFFEh
0x1800325d4  mov     rdi, rcx
0x1800325d7  lea     rcx, aMsdrmAcquisiti; "[msdrm]:+AcquisitionProc"
0x1800325de  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800325e3  xor     r8d, r8d
0x1800325e6  mov     [rbp+140h+arg_18], r8d
0x1800325ed  lea     rcx, [rbp+140h+var_150]; this
0x1800325f1  call    ??0CDRMSoapRequest@@QEAA@XZ; CDRMSoapRequest::CDRMSoapRequest(void)
0x1800325f6  nop
0x1800325f7  mov     [rbp+140h+arg_10], r8d
0x1800325fe  mov     [rsp+240h+Block], r8
0x180032603  mov     [rbp+140h+var_1B0], r8
0x180032607  mov     [rbp+140h+pcCert], r8d
0x18003260e  mov     [rbp+140h+arg_0], r8d
0x180032615  mov     [rbp+140h+var_178], r8
0x180032619  mov     [rbp+140h+var_180], r8
0x18003261d  mov     [rbp+140h+var_1A8], r8
0x180032621  mov     [rbp+140h+var_1A0], r8
0x180032625  mov     [rbp+140h+var_198], r8
0x180032629  mov     [rbp+140h+var_190], r8
0x18003262d  mov     [rbp+140h+var_188], r8
0x180032631  test    rdi, rdi
0x180032634  jz      loc_180032F33
0x18003263a  mov     r14d, r8d
0x18003263d  mov     [rbp+140h+var_170], r8
0x180032641  mov     esi, r8d
0x180032644  mov     [rbp+140h+var_1B8], r8d
0x180032648  mov     [rbp+140h+wszLicense], r8
0x18003264c  mov     r12d, r8d
0x18003264f  mov     [rbp+140h+var_168], r8
0x180032653  mov     r15d, r8d
0x180032656  mov     [rbp+140h+var_1B4], r8d
0x18003265a  mov     r13, [rdi+50h]
0x18003265e  mov     [rsp+240h+var_1D0], r13
0x180032663  mov     rax, [rdi+58h]
0x180032667  mov     [rbp+140h+var_160], rax
0x18003266b  mov     [rbp+140h+var_148], r13
0x18003266f  mov     [rbp+140h+var_140], 2
0x180032676  mov     [rbp+140h+var_138], rax
0x18003267a  mov     rax, [rdi+60h]
0x18003267e  mov     [rbp+140h+var_100], rax
0x180032682  mov     dword ptr [rsp+240h+var_220], 1; unsigned int
0x18003268a  lea     r9, ?g_wszLA_AcquireLicenseNamespace@@3QBGB; "http://microsoft.com/DRM/LicensingServi"...
0x180032691  lea     r8, ?g_wszLA_RequestParams@@3QBGB; "RequestParams"
0x180032698  lea     rdx, ?g_wszLA_AcquireLicenseMethod@@3QBGB; "AcquireLicense"
0x18003269f  lea     rcx, [rbp+140h+var_150]; this
0x1800326a3  call    ?CreateRequest@CDRMSoapRequest@@QEAAJPEBG00I@Z; CDRMSoapRequest::CreateRequest(ushort const *,ushort const *,ushort const *,uint)
0x1800326a8  mov     ebx, eax
0x1800326aa  test    eax, eax
0x1800326ac  js      loc_180032D91
0x1800326b2  lea     rcx, [rbp+140h+var_150]; this
0x1800326b6  call    ?CreateHeader@CDRMSoapRequest@@QEAAJPEBGI@Z; CDRMSoapRequest::CreateHeader(ushort const *,uint)
0x1800326bb  mov     ebx, eax
0x1800326bd  test    eax, eax
0x1800326bf  js      loc_180032D91
0x1800326c5  lea     r8, ?g_wszACT_MinimumVersion@@3QBGB; "MinimumVersion"
0x1800326cc  lea     rcx, [rbp+140h+var_150]
0x1800326d0  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x1800326d5  mov     ebx, eax
0x1800326d7  test    eax, eax
0x1800326d9  js      loc_180032D91
0x1800326df  lea     r8, ?g_wszACT_MaximumVersion@@3QBGB; "MaximumVersion"
0x1800326e6  lea     rcx, [rbp+140h+var_150]
0x1800326ea  call    ?AddHeaderParameter@CDRMSoapRequest@@QEAAJPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddHeaderParameter(ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x1800326ef  mov     ebx, eax
0x1800326f1  test    eax, eax
0x1800326f3  js      loc_180032D91
0x1800326f9  lea     r9d, [r12+7]; unsigned int
0x1800326fe  lea     r8, ?g_wszLA_AcquireLicenseStruct@@3QBGB; "AcquireLicenseParams"
0x180032705  lea     rcx, [rbp+140h+var_150]; this
0x180032709  call    ?AddStruct@CDRMSoapRequest@@IEAAJHPEBGI@Z; CDRMSoapRequest::AddStruct(int,ushort const *,uint)
0x18003270e  mov     ebx, eax
0x180032710  test    eax, eax
0x180032712  js      loc_180032D91
0x180032718  xor     edx, edx; dwMilliseconds
0x18003271a  mov     rcx, [rdi+60h]; hHandle
0x18003271e  call    cs:__imp_WaitForSingleObject
0x180032724  test    eax, eax
0x180032726  jnz     short loc_180032732
0x180032728  mov     ebx, 8004CF41h
0x18003272d  jmp     loc_180032D91
0x180032732  xor     r9d, r9d; wszCert
0x180032735  lea     r8, [rbp+140h+pcCert]; pcCert
0x18003273c  xor     edx, edx; iWhich
0x18003273e  mov     rcx, [rdi+28h]; wszChain
0x180032742  call    DRMDeconstructCertificateChain
0x180032747  test    eax, eax
0x180032749  jnz     short loc_1800327B3
0x18003274b  lea     ecx, [rax+8]; Size
0x18003274e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032753  mov     r14, rax
0x180032756  mov     [rbp+140h+var_170], rax
0x18003275a  test    rax, rax
0x18003275d  jnz     short loc_180032769
0x18003275f  mov     ebx, 8007000Eh
0x180032764  jmp     loc_180032D91
0x180032769  mov     ecx, [rbp+140h+pcCert]
0x18003276f  inc     ecx
0x180032771  mov     eax, 2
0x180032776  mul     rcx
0x180032779  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180032780  cmovb   rax, rcx
0x180032784  mov     rcx, rax; Size
0x180032787  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003278c  mov     [r14], rax
0x18003278f  test    rax, rax
0x180032792  jz      short loc_18003275F
0x180032794  mov     r9, rax; wszCert
0x180032797  lea     r8, [rbp+140h+pcCert]; pcCert
0x18003279e  xor     edx, edx; iWhich
0x1800327a0  mov     rcx, [rdi+28h]; wszChain
0x1800327a4  call    DRMDeconstructCertificateChain
0x1800327a9  mov     esi, 1
0x1800327ae  mov     [rbp+140h+var_1B8], esi
0x1800327b1  test    eax, eax
0x1800327b3  jns     short loc_1800327CD
0x1800327b5  mov     edx, eax
0x1800327b7  lea     rcx, aMsdrmAcquisiti_0; " [msdrm]:AcquisitionProc  DRMDeconstruc"...
0x1800327be  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800327c3  mov     ebx, 8004CF34h
0x1800327c8  jmp     loc_180032D91
0x1800327cd  mov     dword ptr [rsp+240h+var_208], esi
0x1800327d1  mov     [rsp+240h+var_210], r14
0x1800327d6  lea     r9, ?g_wszLA_ParamLicenseeCerts@@3QBGB; "LicenseeCerts"
0x1800327dd  lea     r8, ?g_wszLA_AcquireLicenseStruct@@3QBGB; "AcquireLicenseParams"
0x1800327e4  lea     rcx, [rbp+140h+var_150]
0x1800327e8  call    ?AddArray@CDRMSoapRequest@@IEAAJHPEBG00W4SOAP_DATA_TYPE@@PEAPEAGI@Z; CDRMSoapRequest::AddArray(int,ushort const *,ushort const *,ushort const *,SOAP_DATA_TYPE,ushort * *,uint)
0x1800327ed  mov     ebx, eax
0x1800327ef  test    eax, eax
0x1800327f1  js      loc_180032D91
0x1800327f7  xor     edx, edx
0x1800327f9  jmp     loc_1800328B2
0x1800327fe  lea     esi, [r15+1]
0x180032802  mov     ecx, esi
0x180032804  mov     eax, 8
0x180032809  mul     rcx
0x18003280c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180032813  cmovb   rax, rcx
0x180032817  mov     rcx, rax; Size
0x18003281a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003281f  mov     rbx, rax
0x180032822  xor     eax, eax
0x180032824  test    rbx, rbx
0x180032827  jz      loc_18003275F
0x18003282d  mov     r9d, eax
0x180032830  test    r15d, r15d
0x180032833  jz      short loc_180032848
0x180032835  mov     r8d, r9d
0x180032838  mov     rdx, [r12+r8*8]
0x18003283c  mov     [rbx+r8*8], rdx
0x180032840  inc     r9d
0x180032843  cmp     r9d, r15d
0x180032846  jb      short loc_180032835
0x180032848  mov     rcx, r12; Block
0x18003284b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032850  mov     r12, rbx
0x180032853  mov     [rbp+140h+var_168], rbx
0x180032857  mov     ecx, [rbp+140h+arg_0]
0x18003285d  inc     ecx
0x18003285f  mov     eax, 2
0x180032864  mul     rcx
0x180032867  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003286e  cmovb   rax, rcx
0x180032872  mov     rcx, rax; Size
0x180032875  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003287a  mov     ecx, r15d
0x18003287d  mov     [rbx+rcx*8], rax
0x180032881  test    rax, rax
0x180032884  jz      loc_18003275F
0x18003288a  mov     r9, rax; wszCert
0x18003288d  lea     r8, [rbp+140h+arg_0]; pcCert
0x180032894  mov     edx, r15d; iWhich
0x180032897  mov     rcx, [rdi+20h]; wszChain
0x18003289b  call    DRMDeconstructCertificateChain
0x1800328a0  mov     ebx, eax
0x1800328a2  test    eax, eax
0x1800328a4  js      loc_180032D91
0x1800328aa  mov     r15d, esi
0x1800328ad  mov     [rbp+140h+var_1B4], esi
0x1800328b0  mov     edx, esi; iWhich
0x1800328b2  xor     r9d, r9d; wszCert
0x1800328b5  lea     r8, [rbp+140h+arg_0]; pcCert
0x1800328bc  mov     rcx, [rdi+20h]; wszChain
0x1800328c0  call    DRMDeconstructCertificateChain
0x1800328c5  xor     ecx, ecx
0x1800328c7  test    eax, eax
0x1800328c9  jz      loc_1800327FE
0x1800328cf  lea     rax, [rbp+140h+var_1A8]
0x1800328d3  mov     [rsp+240h+var_1D8], rax; struct _DRM_CRYPTO_VERSION_PARAMETERS **
0x1800328d8  mov     [rsp+240h+var_1E0], rcx; unsigned __int16 **
0x1800328dd  mov     [rsp+240h+var_1E8], rcx; unsigned __int16 **
0x1800328e2  mov     [rsp+240h+var_1F0], rcx; unsigned __int16 **
0x1800328e7  mov     [rsp+240h+var_1F8], rcx; int *
0x1800328ec  lea     rax, [rbp+140h+var_188]
0x1800328f0  mov     [rsp+240h+var_200], rax; unsigned __int16 **
0x1800328f5  lea     rax, [rbp+140h+var_190]
0x1800328f9  mov     [rsp+240h+var_208], rax; unsigned __int16 **
0x1800328fe  mov     [rsp+240h+var_210], rcx; unsigned __int16 **
0x180032903  mov     [rsp+240h+var_218], rcx; unsigned __int16 **
0x180032908  mov     [rsp+240h+var_220], rcx; unsigned __int16 **
0x18003290d  xor     r9d, r9d; unsigned __int16 **
0x180032910  xor     r8d, r8d; unsigned __int16 **
0x180032913  xor     edx, edx; unsigned __int16 **
0x180032915  mov     rcx, [r14]; unsigned __int16 *
0x180032918  call    ?ParseHeaderInfo@@YAJPEAGPEAPEAG1111111PEAH111PEAPEBU_DRM_CRYPTO_VERSION_PARAMETERS@@@Z; ParseHeaderInfo(ushort *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,int *,ushort * *,ushort * *,ushort * *,_DRM_CRYPTO_VERSION_PARAMETERS const * *)
0x18003291d  mov     ebx, eax
0x18003291f  xor     ecx, ecx
0x180032921  test    eax, eax
0x180032923  js      loc_180032D91
0x180032929  lea     rax, [rbp+140h+var_180]
0x18003292d  mov     [rsp+240h+var_1D8], rax; struct _DRM_CRYPTO_VERSION_PARAMETERS **
0x180032932  mov     [rsp+240h+var_1E0], rcx; unsigned __int16 **
0x180032937  mov     [rsp+240h+var_1E8], rcx; unsigned __int16 **
0x18003293c  mov     [rsp+240h+var_1F0], rcx; unsigned __int16 **
0x180032941  mov     [rsp+240h+var_1F8], rcx; int *
0x180032946  lea     rax, [rbp+140h+var_198]
0x18003294a  mov     [rsp+240h+var_200], rax; unsigned __int16 **
0x18003294f  lea     rax, [rbp+140h+var_1A0]
0x180032953  mov     [rsp+240h+var_208], rax; unsigned __int16 **
0x180032958  mov     [rsp+240h+var_210], rcx; unsigned __int16 **
0x18003295d  mov     [rsp+240h+var_218], rcx; unsigned __int16 **
0x180032962  mov     [rsp+240h+var_220], rcx; unsigned __int16 **
0x180032967  xor     r9d, r9d; unsigned __int16 **
0x18003296a  xor     r8d, r8d; unsigned __int16 **
0x18003296d  xor     edx, edx; unsigned __int16 **
0x18003296f  mov     rcx, [r12]; unsigned __int16 *
0x180032973  call    ?ParseHeaderInfo@@YAJPEAGPEAPEAG1111111PEAH111PEAPEBU_DRM_CRYPTO_VERSION_PARAMETERS@@@Z; ParseHeaderInfo(ushort *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,int *,ushort * *,ushort * *,ushort * *,_DRM_CRYPTO_VERSION_PARAMETERS const * *)
0x180032978  mov     ebx, eax
0x18003297a  xor     esi, esi
0x18003297c  test    eax, eax
0x18003297e  js      loc_180032D91
0x180032984  mov     rax, [rbp+140h+var_180]
0x180032988  mov     ecx, [rax]
0x18003298a  mov     rax, [rbp+140h+var_1A8]
0x18003298e  cmp     [rax], ecx
0x180032990  jnb     short loc_1800329C4
0x180032992  lea     rcx, aMsdrmAcquisiti_2; " [msdrm]:AcquisitionProc IL and GIC hav"...
0x180032999  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x18003299e  mov     r9, [rbp+140h+var_198]
0x1800329a2  mov     r8, [rbp+140h+var_1A0]
0x1800329a6  mov     rdx, [rbp+140h+var_188]
0x1800329aa  mov     rcx, [rbp+140h+var_190]
0x1800329ae  call    ?CheckForCryptoUpgrade@@YA?AW4CRYPTO_UPGRADE_CHECK_RESULT@@PEAG000@Z; CheckForCryptoUpgrade(ushort *,ushort *,ushort *,ushort *)
0x1800329b3  test    eax, eax
0x1800329b5  jz      loc_180032A60
0x1800329bb  cmp     eax, 1
0x1800329be  jz      loc_180032A68
0x1800329c4  mov     dword ptr [rsp+240h+var_208], r15d
0x1800329c9  mov     [rsp+240h+var_210], r12
0x1800329ce  lea     r9, ?g_wszLA_ParamRightsLabel@@3QBGB; "IssuanceLicense"
0x1800329d5  lea     r8, ?g_wszLA_AcquireLicenseStruct@@3QBGB; "AcquireLicenseParams"
0x1800329dc  lea     rcx, [rbp+140h+var_150]
0x1800329e0  call    ?AddArray@CDRMSoapRequest@@IEAAJHPEBG00W4SOAP_DATA_TYPE@@PEAPEAGI@Z; CDRMSoapRequest::AddArray(int,ushort const *,ushort const *,ushort const *,SOAP_DATA_TYPE,ushort * *,uint)
0x1800329e5  mov     ebx, eax
0x1800329e7  test    eax, eax
0x1800329e9  js      loc_180032D91
0x1800329ef  mov     rax, [rdi+30h]
0x1800329f3  mov     [rsp+240h+var_218], rax
0x1800329f8  mov     dword ptr [rsp+240h+var_220], 3
0x180032a00  lea     r9, ?g_wszLA_ParamApplicationData@@3QBGB; "ApplicationData"
0x180032a07  lea     r8, ?g_wszLA_AcquireLicenseStruct@@3QBGB; "AcquireLicenseParams"
0x180032a0e  mov     edx, 1
0x180032a13  lea     rcx, [rbp+140h+var_150]
0x180032a17  call    ?AddParam@CDRMSoapRequest@@IEAAJHPEBG0W4SOAP_DATA_TYPE@@0@Z; CDRMSoapRequest::AddParam(int,ushort const *,ushort const *,SOAP_DATA_TYPE,ushort const *)
0x180032a1c  mov     ebx, eax
0x180032a1e  test    eax, eax
0x180032a20  js      loc_180032D91
0x180032a26  mov     rdx, rdi; struct LicCallbackContext *
0x180032a29  lea     rcx, [rbp+140h+var_150]; this
0x180032a2d  call    ?PostServerRequest@@YAJAEAVCDRMSoapRequest@@PEBULicCallbackContext@@@Z; PostServerRequest(CDRMSoapRequest &,LicCallbackContext const *)
0x180032a32  mov     ebx, eax
0x180032a34  cmp     eax, 8004CF3Eh
0x180032a39  jnz     short loc_180032A72
0x180032a3b  lea     rdx, ?g_wszACT_UnsupportedCryptoException@@3QBGB; "Microsoft.DigitalRightsManagement.Crypt"...
0x180032a42  lea     rcx, [rbp+140h+var_150]; this
0x180032a46  call    ?IsExceptionType@CDRMSoapRequest@@QEAAHPEBG@Z; CDRMSoapRequest::IsExceptionType(ushort const *)
0x180032a4b  test    eax, eax
0x180032a4d  jz      loc_180032D91
0x180032a53  mov     rcx, [r14]; unsigned __int16 *
0x180032a56  call    ?DeleteAllV1LicensesForGIC@@YAJPEBG@Z; DeleteAllV1LicensesForGIC(ushort const *)
0x180032a5b  jmp     loc_180032D91
0x180032a60  mov     rcx, [r14]; unsigned __int16 *
0x180032a63  call    ?DeleteAllV1LicensesForGIC@@YAJPEBG@Z; DeleteAllV1LicensesForGIC(ushort const *)
0x180032a68  mov     ebx, 8004CF3Eh
0x180032a6d  jmp     loc_180032D91
0x180032a72  xor     r14d, r14d
0x180032a75  test    eax, eax
0x180032a77  js      loc_180032D91
0x180032a7d  lea     r9, [rbp+140h+arg_10]; unsigned int *
0x180032a84  lea     r8, ?g_wszLA_ParamCertChain@@3QBGB; "CertificateChain"
  ... truncated ...
```
