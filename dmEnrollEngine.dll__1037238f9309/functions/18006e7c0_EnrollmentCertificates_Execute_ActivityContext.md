# EnrollmentCertificates::Execute(ActivityContext *)

- ea: `0x18006e7c0`
- end: `0x18006ec5d`
- name: `?Execute@EnrollmentCertificates@@UEAAJPEAVActivityContext@@@Z`
- size: `1181`
- prototype: `int(EnrollmentCertificates *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180006950`
- `0x18000de50`
- `0x18000e0d0`
- `0x18000e508`
- `0x1800140b4`
- `0x180019e8c`
- `0x18001a86c`
- `0x18001ab40`
- `0x18001aec8`
- `0x18002e1a0`
- `0x18003ee54`
- `0x18004e6c8`
- `0x18004ec0c`
- `0x18006e7c0`
- `0x180073704`
- `0x180073b94`
- `0x180073c20`
- `0x180073edc`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e9dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ea9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006eb76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006e9dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006ea9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006eb76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e870`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e870`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e81b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e851`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e898`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ec36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e81b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e851`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e898`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006ec36`
- `OLEAUT32!__imp_SysFreeString` at `0x18006eb09`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ebde`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ebf4`
- `OLEAUT32!__imp_SysFreeString` at `0x18006eb09`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ebde`
- `OLEAUT32!__imp_SysFreeString` at `0x18006ebf4`
- `DMCmnUtils!BigStrcat` at `0x18006e9d2`
- `DMCmnUtils!BigStrcat` at `0x18006ea92`
- `DMCmnUtils!BigStrcat` at `0x18006eb6a`
- `DMCmnUtils!BigStrcat` at `0x18006e9d2`
- `DMCmnUtils!BigStrcat` at `0x18006ea92`
- `DMCmnUtils!BigStrcat` at `0x18006eb6a`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18006ea4d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18006eb22`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18006ea4d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18006eb22`

## string_xrefs

- `0x18006ea3f`: `RootCertAlreadyExisted`
- `0x18006eb14`: `IntermediateCertAlreadyExisted`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall EnrollmentCertificates::Execute(EnrollmentCertificates *this, struct ActivityContext *a2)
{
  signed int KeyAsString; // ebx
  HKEY v4; // rcx
  HKEY v6; // rcx
  LSTATUS v7; // eax
  int v8; // r14d
  CEnrollmentLogger *Logger; // rax
  EEDBManager *v10; // rcx
  unsigned __int16 *v11; // rbx
  const wchar_t *v12; // rdx
  CEnrollmentLogger *v13; // rax
  const unsigned __int16 *v14; // r12
  CEnrollmentLogger *v15; // rax
  OLECHAR *v16; // rcx
  const unsigned __int16 *v17; // r12
  CEnrollmentLogger *v18; // rax
  OLECHAR *v19; // rcx
  OLECHAR *v20; // rcx
  HKEY v21; // rcx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v23; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v25; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v26; // [rsp+54h] [rbp-ACh] BYREF
  BSTR v27; // [rsp+58h] [rbp-A8h] BYREF
  void *v28; // [rsp+60h] [rbp-A0h] BYREF
  struct IEnrollmentInfo *v29; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR *v30; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR *v31; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID v32; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR psz[40]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[40]; // [rsp+E0h] [rbp-20h] BYREF

  hKey = 0;
  v25 = 0;
  v26 = 0;
  KeyAsString = ActivityContext::get_KeyAsString(a2, SubKey);
  if ( KeyAsString < 0 )
  {
LABEL_2:
    v4 = hKey;
    hKey = 0;
    if ( v4 )
      RegCloseKey(v4);
    return (unsigned int)KeyAsString;
  }
  v23 = 0;
  KeyAsString = EEDBManager::OpenEnrollmentsHKEY(0x2001Fu, &v23);
  v6 = v23;
  if ( KeyAsString < 0 )
  {
    v23 = 0;
LABEL_7:
    if ( v6 )
      RegCloseKey(v6);
    goto LABEL_2;
  }
  v7 = RegOpenKeyExW(v23, SubKey, 0, 0x2001Fu, &hKey);
  KeyAsString = v7;
  if ( v7 > 0 )
    KeyAsString = (unsigned __int16)v7 | 0x80070000;
  v6 = v23;
  v23 = 0;
  if ( KeyAsString < 0 )
    goto LABEL_7;
  if ( v6 )
    RegCloseKey(v6);
  v8 = DeleteEnrollmentCertificates(hKey);
  if ( v8 < 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    Logger = CEnrollmentLogger::GetLogger();
    *(_OWORD *)bstrString = *(_OWORD *)((char *)a2 + 8);
    CEnrollmentLogger::LogUnenrollEnrollmentCertificatesFail(Logger, v8, (struct _GUID *)bstrString);
  }
  if ( ActivityContext::get_KeyAsString(a2, psz) >= 0 )
  {
    v31 = 0;
    *(_OWORD *)bstrString = *(_OWORD *)((char *)a2 + 8);
    EEDBManager::GetEnrollmentString((struct _GUID *)bstrString, L"ProviderID", &v31);
    v30 = 0;
    *(_OWORD *)bstrString = *(_OWORD *)((char *)a2 + 8);
    EEDBManager::GetEnrollmentString((struct _GUID *)bstrString, L"SID", &v30);
    v29 = 0;
    *(_OWORD *)bstrString = *(_OWORD *)((char *)a2 + 8);
    EEDBManager::GetEnrollmentInfo(v10, (struct _GUID *)bstrString, &v29);
    LODWORD(v23) = 0;
    *(_OWORD *)bstrString = *(_OWORD *)((char *)a2 + 8);
    EEDBManager::GetEnrollmentType((struct _GUID *)bstrString, (enum EnrollmentEnrollType *)&v23);
    v11 = 0;
    v28 = 0;
    v27 = 0;
    if ( v29 && (*(int (__fastcall **)(struct IEnrollmentInfo *, BSTR *))(*(_QWORD *)v29 + 80LL))(v29, &v27) >= 0 )
    {
      v12 = L"./Vendor/MSFT/CertificateStore/My/System/";
      if ( ((1LL << (char)v23) & 0x4000040) == 0 )
        v12 = L"./Vendor/MSFT/CertificateStore/My/User/";
      v11 = BigStrcat(2u, v12, v27);
      LocalFree(0);
      v28 = v11;
      if ( v11 )
      {
        v8 = CommonUnenrollCsp(psz, v31, v30, v11, 0, 1);
        if ( v8 < 0 )
        {
          v13 = CEnrollmentLogger::GetLogger();
          *(_OWORD *)bstrString = *(_OWORD *)((char *)a2 + 8);
          CEnrollmentLogger::LogUnenrollMyCertStoreFail(v13, v8, (struct _GUID *)bstrString);
        }
      }
    }
    if ( (int)OmaDmRegistryGetDWORD(hKey, 0, L"RootCertAlreadyExisted", &v25) < 0 || v25 != 1 )
    {
      bstrString[0] = 0;
      if ( (*(int (__fastcall **)(struct IEnrollmentInfo *, BSTR *))(*(_QWORD *)v29 + 72LL))(v29, bstrString) >= 0 )
      {
        v14 = BigStrcat(2u, L"./Vendor/MSFT/CertificateStore/Root/System/", bstrString[0]);
        LocalFree(v11);
        v11 = (unsigned __int16 *)v14;
        v28 = (void *)v14;
        if ( v14 )
        {
          v8 = CommonUnenrollCsp(psz, v31, v30, v14, 0, 1);
          if ( v8 < 0 )
          {
            v15 = CEnrollmentLogger::GetLogger();
            v32 = *(struct _GUID *)((char *)a2 + 8);
            CEnrollmentLogger::LogUnenrollRootCertStoreFail(v15, v8, &v32);
          }
        }
      }
      v16 = bstrString[0];
      bstrString[0] = 0;
      if ( v16 )
        SysFreeString(v16);
    }
    if ( (int)OmaDmRegistryGetDWORD(hKey, 0, L"IntermediateCertAlreadyExisted", &v26) < 0 || v26 != 1 )
    {
      bstrString[0] = 0;
      if ( (*(int (__fastcall **)(struct IEnrollmentInfo *, BSTR *))(*(_QWORD *)v29 + 128LL))(v29, bstrString) >= 0 )
      {
        v17 = BigStrcat(2u, L"./Vendor/MSFT/CertificateStore/CA/System/", bstrString[0]);
        LocalFree(v11);
        v28 = (void *)v17;
        if ( v17 )
        {
          v8 = CommonUnenrollCsp(psz, v31, v30, v17, 0, 1);
          if ( v8 < 0 )
          {
            v18 = CEnrollmentLogger::GetLogger();
            v32 = *(struct _GUID *)((char *)a2 + 8);
            CEnrollmentLogger::LogUnenrollIntermediateCertStoreFail(v18, v8, &v32);
          }
        }
      }
      v19 = bstrString[0];
      bstrString[0] = 0;
      if ( v19 )
        SysFreeString(v19);
    }
    v20 = v27;
    v27 = 0;
    if ( v20 )
      SysFreeString(v20);
    CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>(&v28);
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v29);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v30);
    CHeapMemPtr<unsigned short>::~CHeapMemPtr<unsigned short>((void **)&v31);
  }
  v21 = hKey;
  hKey = 0;
  if ( v21 )
    RegCloseKey(v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006e7c0  push    rbp
0x18006e7c2  push    rbx
0x18006e7c3  push    r12
0x18006e7c5  push    r13
0x18006e7c7  push    r14
0x18006e7c9  push    r15
0x18006e7cb  lea     rbp, [rsp-48h]
0x18006e7d0  sub     rsp, 148h
0x18006e7d7  mov     rax, cs:__security_cookie
0x18006e7de  xor     rax, rsp
0x18006e7e1  mov     [rbp+70h+var_40], rax
0x18006e7e5  mov     r15, rdx
0x18006e7e8  xor     r13d, r13d
0x18006e7eb  mov     [rsp+170h+hKey], r13
0x18006e7f0  mov     [rsp+170h+var_120], r13d
0x18006e7f5  mov     [rsp+170h+var_11C], r13d
0x18006e7fa  lea     rdx, [rbp+70h+SubKey]; unsigned __int16 *
0x18006e7fe  mov     rcx, r15; this
0x18006e801  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x18006e806  mov     ebx, eax
0x18006e808  test    eax, eax
0x18006e80a  jns     short loc_18006E828
0x18006e80c  mov     rcx, [rsp+170h+hKey]; hKey
0x18006e811  mov     [rsp+170h+hKey], r13
0x18006e816  test    rcx, rcx
0x18006e819  jz      short loc_18006E821
0x18006e81b  call    cs:__imp_RegCloseKey
0x18006e821  mov     eax, ebx
0x18006e823  jmp     loc_18006EC3F
0x18006e828  mov     [rsp+170h+var_138], r13
0x18006e82d  lea     rdx, [rsp+170h+var_138]; HKEY *
0x18006e832  mov     ecx, 2001Fh; unsigned int
0x18006e837  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x18006e83c  mov     ebx, eax
0x18006e83e  mov     rcx, [rsp+170h+var_138]; hKey
0x18006e843  test    eax, eax
0x18006e845  jns     short loc_18006E859
0x18006e847  mov     [rsp+170h+var_138], r13
0x18006e84c  test    rcx, rcx
0x18006e84f  jz      short loc_18006E80C
0x18006e851  call    cs:__imp_RegCloseKey
0x18006e857  jmp     short loc_18006E80C
0x18006e859  lea     rax, [rsp+170h+hKey]
0x18006e85e  mov     [rsp+170h+phkResult], rax; phkResult
0x18006e863  mov     r9d, 2001Fh; samDesired
0x18006e869  xor     r8d, r8d; ulOptions
0x18006e86c  lea     rdx, [rbp+70h+SubKey]; lpSubKey
0x18006e870  call    cs:__imp_RegOpenKeyExW
0x18006e876  mov     ebx, eax
0x18006e878  test    eax, eax
0x18006e87a  jle     short loc_18006E885
0x18006e87c  movzx   ebx, ax
0x18006e87f  or      ebx, 80070000h
0x18006e885  mov     rcx, [rsp+170h+var_138]; hKey
0x18006e88a  mov     [rsp+170h+var_138], r13
0x18006e88f  test    ebx, ebx
0x18006e891  js      short loc_18006E84C
0x18006e893  test    rcx, rcx
0x18006e896  jz      short loc_18006E89E
0x18006e898  call    cs:__imp_RegCloseKey
0x18006e89e  mov     rcx, [rsp+170h+hKey]; HKEY
0x18006e8a3  call    ?DeleteEnrollmentCertificates@@YAJPEAUHKEY__@@@Z; DeleteEnrollmentCertificates(HKEY__ *)
0x18006e8a8  mov     r14d, eax
0x18006e8ab  test    eax, eax
0x18006e8ad  jns     short loc_18006E8D4
0x18006e8af  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)")
0x18006e8b4  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006e8b9  movups  xmm0, xmmword ptr [r15+8]
0x18006e8be  movdqu  xmmword ptr [rsp+170h+bstrString], xmm0
0x18006e8c4  lea     r8, [rsp+170h+bstrString]; struct _GUID
0x18006e8c9  mov     edx, r14d; int
0x18006e8cc  mov     rcx, rax; this
0x18006e8cf  call    ?LogUnenrollEnrollmentCertificatesFail@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogUnenrollEnrollmentCertificatesFail(long,_GUID)
0x18006e8d4  lea     rdx, [rbp+70h+psz]; unsigned __int16 *
0x18006e8d8  mov     rcx, r15; this
0x18006e8db  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x18006e8e0  test    eax, eax
0x18006e8e2  js      loc_18006EC27
0x18006e8e8  mov     [rsp+170h+var_F8], r13
0x18006e8ed  movups  xmm0, xmmword ptr [r15+8]
0x18006e8f2  movdqu  xmmword ptr [rsp+170h+bstrString], xmm0
0x18006e8f8  lea     r8, [rsp+170h+var_F8]; unsigned __int16 **
0x18006e8fd  lea     rdx, aProviderid; "ProviderID"
0x18006e904  lea     rcx, [rsp+170h+bstrString]; struct _GUID
0x18006e909  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18006e90e  mov     [rsp+170h+var_100], r13
0x18006e913  movups  xmm0, xmmword ptr [r15+8]
0x18006e918  movdqu  xmmword ptr [rsp+170h+bstrString], xmm0
0x18006e91e  lea     r8, [rsp+170h+var_100]; unsigned __int16 **
0x18006e923  lea     rdx, aSid; "SID"
0x18006e92a  lea     rcx, [rsp+170h+bstrString]; struct _GUID
0x18006e92f  call    ?GetEnrollmentString@EEDBManager@@CAJU_GUID@@PEBGPEAPEAG@Z; EEDBManager::GetEnrollmentString(_GUID,ushort const *,ushort * *)
0x18006e934  mov     [rsp+170h+var_108], r13
0x18006e939  movups  xmm0, xmmword ptr [r15+8]
0x18006e93e  movdqu  xmmword ptr [rsp+170h+bstrString], xmm0
0x18006e944  lea     r8, [rsp+170h+var_108]; struct IEnrollmentInfo **
0x18006e949  lea     rdx, [rsp+170h+bstrString]; struct _GUID
0x18006e94e  call    ?GetEnrollmentInfo@EEDBManager@@QEAAJU_GUID@@PEAPEAUIEnrollmentInfo@@@Z; EEDBManager::GetEnrollmentInfo(_GUID,IEnrollmentInfo * *)
0x18006e953  mov     dword ptr [rsp+170h+var_138], r13d
0x18006e958  movups  xmm0, xmmword ptr [r15+8]
0x18006e95d  movdqu  xmmword ptr [rsp+170h+bstrString], xmm0
0x18006e963  lea     rdx, [rsp+170h+var_138]; enum EnrollmentEnrollType *
0x18006e968  lea     rcx, [rsp+170h+bstrString]; struct _GUID
0x18006e96d  call    ?GetEnrollmentType@EEDBManager@@SAJU_GUID@@PEAW4EnrollmentEnrollType@@@Z; EEDBManager::GetEnrollmentType(_GUID,EnrollmentEnrollType *)
0x18006e972  mov     rbx, r13
0x18006e975  mov     [rsp+170h+var_110], rbx
0x18006e97a  mov     [rsp+170h+var_118], r13
0x18006e97f  mov     rcx, [rsp+170h+var_108]
0x18006e984  test    rcx, rcx
0x18006e987  jz      loc_18006EA3A
0x18006e98d  mov     rax, [rcx]
0x18006e990  lea     rdx, [rsp+170h+var_118]
0x18006e995  mov     rax, [rax+50h]
0x18006e999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e99e  test    eax, eax
0x18006e9a0  js      loc_18006EA3A
0x18006e9a6  mov     ecx, dword ptr [rsp+170h+var_138]
0x18006e9aa  mov     eax, 1
0x18006e9af  shl     rax, cl
0x18006e9b2  mov     r8, [rsp+170h+var_118]
0x18006e9b7  mov     ecx, 2
0x18006e9bc  test    rax, 4000040h
0x18006e9c2  lea     rdx, aVendorMsftCert_5; "./Vendor/MSFT/CertificateStore/My/Syste"...
0x18006e9c9  jnz     short loc_18006E9D2
0x18006e9cb  lea     rdx, aVendorMsftCert; "./Vendor/MSFT/CertificateStore/My/User/"
0x18006e9d2  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18006e9d8  mov     rbx, rax
0x18006e9db  xor     ecx, ecx; hMem
0x18006e9dd  call    cs:__imp_LocalFree
0x18006e9e3  mov     rax, rbx
0x18006e9e6  mov     [rsp+170h+var_110], rbx
0x18006e9eb  test    rax, rax
0x18006e9ee  jz      short loc_18006EA3A
0x18006e9f0  mov     [rsp+170h+var_148], 1; int
0x18006e9f8  mov     dword ptr [rsp+170h+phkResult], r13d; int
0x18006e9fd  mov     r9, rbx; unsigned __int16 *
0x18006ea00  mov     r8, [rsp+170h+var_100]; OLECHAR *
0x18006ea05  mov     rdx, [rsp+170h+var_F8]; OLECHAR *
0x18006ea0a  lea     rcx, [rbp+70h+psz]; psz
0x18006ea0e  call    ?CommonUnenrollCsp@@YAJPEBG000HH@Z; CommonUnenrollCsp(ushort const *,ushort const *,ushort const *,ushort const *,int,int)
0x18006ea13  mov     r14d, eax
0x18006ea16  test    eax, eax
0x18006ea18  jns     short loc_18006EA3A
0x18006ea1a  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006ea1f  movups  xmm0, xmmword ptr [r15+8]
0x18006ea24  movdqu  xmmword ptr [rsp+170h+bstrString], xmm0
0x18006ea2a  lea     r8, [rsp+170h+bstrString]; struct _GUID
0x18006ea2f  mov     edx, r14d; int
0x18006ea32  mov     rcx, rax; this
0x18006ea35  call    ?LogUnenrollMyCertStoreFail@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogUnenrollMyCertStoreFail(long,_GUID)
0x18006ea3a  lea     r9, [rsp+170h+var_120]
0x18006ea3f  lea     r8, aRootcertalread; "RootCertAlreadyExisted"
0x18006ea46  xor     edx, edx
0x18006ea48  mov     rcx, [rsp+170h+hKey]
0x18006ea4d  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18006ea53  test    eax, eax
0x18006ea55  js      short loc_18006EA62
0x18006ea57  cmp     [rsp+170h+var_120], 1
0x18006ea5c  jz      loc_18006EB0F
0x18006ea62  mov     [rsp+170h+bstrString], r13
0x18006ea67  mov     rcx, [rsp+170h+var_108]
0x18006ea6c  mov     rax, [rcx]
0x18006ea6f  lea     rdx, [rsp+170h+bstrString]
0x18006ea74  mov     rax, [rax+48h]
0x18006ea78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ea7d  test    eax, eax
0x18006ea7f  js      short loc_18006EAFA
0x18006ea81  mov     r8, [rsp+170h+bstrString]
0x18006ea86  lea     rdx, aVendorMsftCert_4; "./Vendor/MSFT/CertificateStore/Root/Sys"...
0x18006ea8d  mov     ecx, 2
0x18006ea92  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18006ea98  mov     r12, rax
0x18006ea9b  mov     rcx, rbx; hMem
0x18006ea9e  call    cs:__imp_LocalFree
0x18006eaa4  mov     rbx, r12
0x18006eaa7  mov     [rsp+170h+var_110], rbx
0x18006eaac  test    r12, r12
0x18006eaaf  jz      short loc_18006EAFA
0x18006eab1  mov     [rsp+170h+var_148], 1; int
0x18006eab9  mov     dword ptr [rsp+170h+phkResult], r13d; int
0x18006eabe  mov     r9, r12; unsigned __int16 *
0x18006eac1  mov     r8, [rsp+170h+var_100]; OLECHAR *
0x18006eac6  mov     rdx, [rsp+170h+var_F8]; OLECHAR *
0x18006eacb  lea     rcx, [rbp+70h+psz]; psz
0x18006eacf  call    ?CommonUnenrollCsp@@YAJPEBG000HH@Z; CommonUnenrollCsp(ushort const *,ushort const *,ushort const *,ushort const *,int,int)
0x18006ead4  mov     r14d, eax
0x18006ead7  test    eax, eax
0x18006ead9  jns     short loc_18006EAFA
0x18006eadb  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006eae0  movups  xmm0, xmmword ptr [r15+8]
0x18006eae5  movdqu  xmmword ptr [rbp+70h+var_F0.Data1], xmm0
0x18006eaea  lea     r8, [rbp+70h+var_F0]; struct _GUID
0x18006eaee  mov     edx, r14d; int
0x18006eaf1  mov     rcx, rax; this
0x18006eaf4  call    ?LogUnenrollRootCertStoreFail@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogUnenrollRootCertStoreFail(long,_GUID)
0x18006eaf9  nop
0x18006eafa  mov     rcx, [rsp+170h+bstrString]; bstrString
0x18006eaff  mov     [rsp+170h+bstrString], r13
0x18006eb04  test    rcx, rcx
0x18006eb07  jz      short loc_18006EB0F
0x18006eb09  call    cs:__imp_SysFreeString
0x18006eb0f  lea     r9, [rsp+170h+var_11C]
0x18006eb14  lea     r8, aIntermediatece; "IntermediateCertAlreadyExisted"
0x18006eb1b  xor     edx, edx
0x18006eb1d  mov     rcx, [rsp+170h+hKey]
0x18006eb22  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18006eb28  test    eax, eax
0x18006eb2a  js      short loc_18006EB37
0x18006eb2c  cmp     [rsp+170h+var_11C], 1
0x18006eb31  jz      loc_18006EBE5
0x18006eb37  mov     [rsp+170h+bstrString], r13
0x18006eb3c  mov     rcx, [rsp+170h+var_108]
0x18006eb41  mov     rax, [rcx]
0x18006eb44  lea     rdx, [rsp+170h+bstrString]
0x18006eb49  mov     rax, [rax+80h]
0x18006eb50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eb55  test    eax, eax
0x18006eb57  js      short loc_18006EBCF
0x18006eb59  mov     r8, [rsp+170h+bstrString]
0x18006eb5e  lea     rdx, aVendorMsftCert_2; "./Vendor/MSFT/CertificateStore/CA/Syste"...
0x18006eb65  mov     ecx, 2
0x18006eb6a  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x18006eb70  mov     r12, rax
0x18006eb73  mov     rcx, rbx; hMem
0x18006eb76  call    cs:__imp_LocalFree
0x18006eb7c  mov     [rsp+170h+var_110], r12
0x18006eb81  test    r12, r12
0x18006eb84  jz      short loc_18006EBCF
0x18006eb86  mov     [rsp+170h+var_148], 1; int
0x18006eb8e  mov     dword ptr [rsp+170h+phkResult], r13d; int
0x18006eb93  mov     r9, r12; unsigned __int16 *
0x18006eb96  mov     r8, [rsp+170h+var_100]; OLECHAR *
0x18006eb9b  mov     rdx, [rsp+170h+var_F8]; OLECHAR *
0x18006eba0  lea     rcx, [rbp+70h+psz]; psz
0x18006eba4  call    ?CommonUnenrollCsp@@YAJPEBG000HH@Z; CommonUnenrollCsp(ushort const *,ushort const *,ushort const *,ushort const *,int,int)
0x18006eba9  mov     r14d, eax
0x18006ebac  test    eax, eax
0x18006ebae  jns     short loc_18006EBCF
0x18006ebb0  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18006ebb5  movups  xmm0, xmmword ptr [r15+8]
0x18006ebba  movdqu  xmmword ptr [rbp+70h+var_F0.Data1], xmm0
0x18006ebbf  lea     r8, [rbp+70h+var_F0]; struct _GUID
0x18006ebc3  mov     edx, r14d; int
0x18006ebc6  mov     rcx, rax; this
0x18006ebc9  call    ?LogUnenrollIntermediateCertStoreFail@CEnrollmentLogger@@QEAAXJU_GUID@@@Z; CEnrollmentLogger::LogUnenrollIntermediateCertStoreFail(long,_GUID)
0x18006ebce  nop
0x18006ebcf  mov     rcx, [rsp+170h+bstrString]; bstrString
0x18006ebd4  mov     [rsp+170h+bstrString], r13
0x18006ebd9  test    rcx, rcx
0x18006ebdc  jz      short loc_18006EBE5
0x18006ebde  call    cs:__imp_SysFreeString
0x18006ebe4  nop
0x18006ebe5  mov     rcx, [rsp+170h+var_118]; bstrString
0x18006ebea  mov     [rsp+170h+var_118], r13
0x18006ebef  test    rcx, rcx
0x18006ebf2  jz      short loc_18006EBFB
0x18006ebf4  call    cs:__imp_SysFreeString
0x18006ebfa  nop
0x18006ebfb  lea     rcx, [rsp+170h+var_110]
0x18006ec00  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x18006ec05  nop
0x18006ec06  lea     rcx, [rsp+170h+var_108]
0x18006ec0b  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x18006ec10  nop
0x18006ec11  lea     rcx, [rsp+170h+var_100]
0x18006ec16  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18006ec1b  nop
0x18006ec1c  lea     rcx, [rsp+170h+var_F8]
0x18006ec21  call    ??1?$CHeapMemPtr@G@@QEAA@XZ; CHeapMemPtr<ushort>::~CHeapMemPtr<ushort>(void)
0x18006ec26  nop
0x18006ec27  mov     rcx, [rsp+170h+hKey]; hKey
0x18006ec2c  mov     [rsp+170h+hKey], r13
0x18006ec31  test    rcx, rcx
0x18006ec34  jz      short loc_18006EC3C
0x18006ec36  call    cs:__imp_RegCloseKey
0x18006ec3c  mov     eax, r14d
0x18006ec3f  mov     rcx, [rbp+70h+var_40]
0x18006ec43  xor     rcx, rsp; StackCookie
0x18006ec46  call    __security_check_cookie
0x18006ec4b  add     rsp, 148h
0x18006ec52  pop     r15
0x18006ec54  pop     r14
0x18006ec56  pop     r13
0x18006ec58  pop     r12
0x18006ec5a  pop     rbx
0x18006ec5b  pop     rbp
0x18006ec5c  retn
```
