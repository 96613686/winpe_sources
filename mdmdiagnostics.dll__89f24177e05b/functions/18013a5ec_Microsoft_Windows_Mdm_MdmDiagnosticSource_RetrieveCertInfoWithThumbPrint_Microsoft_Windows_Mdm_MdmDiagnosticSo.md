# Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &)

- ea: `0x18013a5ec`
- end: `0x18013aad4`
- name: `?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@@Z`
- size: `1256`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource *__hidden this, struct Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180129dc8`
- `0x18012afd8`

## callees

- `0x180019000`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800f8aa0`
- `0x1800f9558`
- `0x1800f9a0c`
- `0x18010440c`
- `0x180128238`
- `0x1801282b0`
- `0x18013a5ec`
- `0x18013aadc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18013a64b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18013a760`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18013a64b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18013a760`
- `CRYPT32!CertOpenStore` at `0x18013a795`
- `CRYPT32!CertOpenStore` at `0x18013a795`
- `CRYPT32!CertFindCertificateInStore` at `0x18013a9bf`
- `CRYPT32!CertFindCertificateInStore` at `0x18013a9bf`
- `CRYPT32!CertFreeCertificateContext` at `0x18013aa6b`
- `CRYPT32!CertFreeCertificateContext` at `0x18013aa6b`
- `CRYPT32!CertCloseStore` at `0x18013a85f`
- `CRYPT32!CertCloseStore` at `0x18013a8d7`
- `CRYPT32!CertCloseStore` at `0x18013a969`
- `CRYPT32!CertCloseStore` at `0x18013aa10`
- `CRYPT32!CertCloseStore` at `0x18013aa84`
- `CRYPT32!CertCloseStore` at `0x18013a85f`
- `CRYPT32!CertCloseStore` at `0x18013a8d7`
- `CRYPT32!CertCloseStore` at `0x18013a969`
- `CRYPT32!CertCloseStore` at `0x18013aa10`
- `CRYPT32!CertCloseStore` at `0x18013aa84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a7a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013a7a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013a95b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013aa02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013aa76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013a95b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013aa02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013aa76`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013a89d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013a89d`
- `DMCmnUtils!HexStringToBinary` at `0x18013a830`
- `DMCmnUtils!HexStringToBinary` at `0x18013a92f`
- `DMCmnUtils!HexStringToBinary` at `0x18013a830`
- `DMCmnUtils!HexStringToBinary` at `0x18013a92f`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18013a679`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18013a679`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a6b1`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a717`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a7df`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a86c`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a8e4`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a976`
- `DMCmnUtils!DmRevertToSelf` at `0x18013aa1d`
- `DMCmnUtils!DmRevertToSelf` at `0x18013aa91`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a6b1`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a717`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a7df`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a86c`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a8e4`
- `DMCmnUtils!DmRevertToSelf` at `0x18013a976`
- `DMCmnUtils!DmRevertToSelf` at `0x18013aa1d`
- `DMCmnUtils!DmRevertToSelf` at `0x18013aa91`
- `DMCmnUtils!DmImpersonate` at `0x18013a6df`
- `DMCmnUtils!DmImpersonate` at `0x18013a6df`

## string_xrefs

- `0x18013a68f`: `DmGetActiveUserSid failed`
- `0x18013a6f5`: `DmImpersonate failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(
        Microsoft::Windows::Mdm::MdmDiagnosticSource *this,
        struct Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo *a2)
{
  char *v3; // rsi
  __int64 v4; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v5; // rax
  unsigned int CertInfoWithThumbPrint; // ebx
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v7; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v8; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v9; // rax
  __int64 v10; // rax
  DWORD v11; // edi
  const void *v12; // rax
  signed int LastError; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v14; // rax
  __int64 v15; // rax
  int v16; // eax
  unsigned int v17; // edi
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v18; // rax
  HLOCAL v20; // rdi
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v21; // rax
  __int64 v22; // rax
  int v23; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v24; // rax
  CERT_CONTEXT *CertificateInStore; // rax
  const struct _CERT_CONTEXT *v26; // r8
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v27; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v28; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v29; // rax
  int pvPara; // [rsp+20h] [rbp-79h]
  char v31; // [rsp+30h] [rbp-69h] BYREF
  int ActiveUserSid; // [rsp+34h] [rbp-65h] BYREF
  HCERTSTORE hCertStore; // [rsp+38h] [rbp-61h] BYREF
  SIZE_T uBytes[2]; // [rsp+40h] [rbp-59h] BYREF
  HCERTSTORE *p_hCertStore; // [rsp+50h] [rbp-49h] BYREF
  char v36; // [rsp+58h] [rbp-41h]
  PCCERT_CONTEXT pCertContext[2]; // [rsp+60h] [rbp-39h] BYREF
  char v38; // [rsp+70h] [rbp-29h]
  char *v39; // [rsp+78h] [rbp-21h]
  int *v40; // [rsp+80h] [rbp-19h]
  char v41; // [rsp+88h] [rbp-11h]
  PCCERT_CONTEXT *v42; // [rsp+90h] [rbp-9h] BYREF
  char v43; // [rsp+98h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  ActiveUserSid = 0;
  v31 = 0;
  v39 = &v31;
  v40 = &ActiveUserSid;
  v41 = 1;
  v3 = (char *)this + 32;
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
  if ( !(unsigned int)_o__wcsicmp(v4, L"my") && !*((_BYTE *)this + 176) )
  {
    p_hCertStore = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &p_hCertStore,
      0);
    ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&p_hCertStore);
    if ( ActiveUserSid < 0 )
    {
      v5 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(
        v5,
        L"DmGetActiveUserSid failed",
        ActiveUserSid);
      CertInfoWithThumbPrint = ActiveUserSid;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&p_hCertStore);
      if ( v31 )
        DmRevertToSelf();
      if ( ActiveUserSid < 0 )
      {
        v7 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(
          v7,
          L"RetrieveCertInfoWithThumbPrint failed",
          ActiveUserSid);
      }
      return CertInfoWithThumbPrint;
    }
    ActiveUserSid = DmImpersonate((const unsigned __int16 *)p_hCertStore);
    if ( ActiveUserSid < 0 )
    {
      v8 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v8, L"DmImpersonate failed", ActiveUserSid);
      CertInfoWithThumbPrint = ActiveUserSid;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&p_hCertStore);
      if ( v31 )
        DmRevertToSelf();
      if ( ActiveUserSid < 0 )
      {
        v9 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(
          v9,
          L"RetrieveCertInfoWithThumbPrint failed",
          ActiveUserSid);
      }
      return CertInfoWithThumbPrint;
    }
    v31 = 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&p_hCertStore);
  }
  v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3);
  if ( (unsigned int)_o__wcsicmp(v10, L"my") || (v11 = 114688, !*((_BYTE *)this + 176)) )
    v11 = 704512;
  v12 = (const void *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3);
  hCertStore = CertOpenStore((LPCSTR)0xD, 0, 0, v11, v12);
  if ( !hCertStore )
  {
    LastError = GetLastError();
    CertInfoWithThumbPrint = LastError;
    if ( LastError > 0 )
      CertInfoWithThumbPrint = (unsigned __int16)LastError | 0x80070000;
    ActiveUserSid = CertInfoWithThumbPrint;
    if ( (CertInfoWithThumbPrint & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\cert.cpp",
        (const char *)CertInfoWithThumbPrint,
        pvPara);
    if ( v31 )
      DmRevertToSelf();
    if ( ActiveUserSid < 0 )
    {
      v14 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(
        v14,
        L"RetrieveCertInfoWithThumbPrint failed",
        ActiveUserSid);
    }
    return CertInfoWithThumbPrint;
  }
  p_hCertStore = &hCertStore;
  v36 = 1;
  *(_OWORD *)uBytes = 0;
  v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
  v16 = HexStringToBinary(v15, 0, uBytes, 1);
  v17 = v16;
  ActiveUserSid = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\cert.cpp",
      (const char *)(unsigned int)v16,
      pvPara);
    CertCloseStore(hCertStore, 1u);
    if ( v31 )
      DmRevertToSelf();
    if ( ActiveUserSid < 0 )
    {
      v18 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(
        v18,
        L"RetrieveCertInfoWithThumbPrint failed",
        ActiveUserSid);
    }
    return v17;
  }
  v20 = LocalAlloc(0, LODWORD(uBytes[0]));
  uBytes[1] = (SIZE_T)v20;
  if ( !v20 )
  {
    CertInfoWithThumbPrint = -2147024882;
    ActiveUserSid = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\cert.cpp",
      (const char *)0x8007000ELL,
      pvPara);
    CertCloseStore(hCertStore, 1u);
    if ( v31 )
      DmRevertToSelf();
    if ( ActiveUserSid < 0 )
    {
      v21 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(
        v21,
        L"RetrieveCertInfoWithThumbPrint failed",
        ActiveUserSid);
    }
    return CertInfoWithThumbPrint;
  }
  pCertContext[1] = (PCCERT_CONTEXT)uBytes;
  v38 = 1;
  v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
  v23 = HexStringToBinary(v22, v20, uBytes, 1);
  v17 = v23;
  ActiveUserSid = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\cert.cpp",
      (const char *)(unsigned int)v23,
      pvPara);
    LocalFree((HLOCAL)uBytes[1]);
    CertCloseStore(hCertStore, 1u);
    if ( v31 )
      DmRevertToSelf();
    if ( ActiveUserSid < 0 )
    {
      v24 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(
        v24,
        L"RetrieveCertInfoWithThumbPrint failed",
        ActiveUserSid);
    }
    return v17;
  }
  CertificateInStore = (CERT_CONTEXT *)CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x10000u, uBytes, 0);
  pCertContext[0] = CertificateInStore;
  if ( CertificateInStore )
  {
    v42 = pCertContext;
    v43 = 1;
    CertInfoWithThumbPrint = Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(
                               this,
                               CertificateInStore,
                               v26);
    if ( pCertContext[0] )
      CertFreeCertificateContext(pCertContext[0]);
    LocalFree((HLOCAL)uBytes[1]);
    CertCloseStore(hCertStore, 1u);
    if ( v31 )
      DmRevertToSelf();
    if ( ActiveUserSid < 0 )
    {
      v29 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(
        v29,
        L"RetrieveCertInfoWithThumbPrint failed",
        ActiveUserSid);
    }
    return CertInfoWithThumbPrint;
  }
  std::operator+<unsigned short>(&v42, L"CertStore fails to find cert tracked by Resource Manager. Thumbprint: ", this);
  v27 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v27, &v42);
  std::wstring::_Tidy_deallocate(&v42);
  LocalFree((HLOCAL)uBytes[1]);
  CertCloseStore(hCertStore, 1u);
  if ( v31 )
    DmRevertToSelf();
  if ( ActiveUserSid < 0 )
  {
    v28 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(
      v28,
      L"RetrieveCertInfoWithThumbPrint failed",
      ActiveUserSid);
  }
  return 2147943568LL;
}

```

## disassembly

```asm
0x18013a5ec  push    rbp
0x18013a5ee  push    rbx
0x18013a5ef  push    rsi
0x18013a5f0  push    rdi
0x18013a5f1  push    r14
0x18013a5f3  push    r15
0x18013a5f5  lea     rbp, [rsp-2Fh]
0x18013a5fa  sub     rsp, 0C8h
0x18013a601  mov     rax, cs:__security_cookie
0x18013a608  xor     rax, rsp
0x18013a60b  mov     [rbp+57h+var_40], rax
0x18013a60f  mov     rbx, rcx
0x18013a612  xor     r14d, r14d
0x18013a615  mov     [rbp+57h+var_BC], r14d
0x18013a619  mov     [rbp+57h+var_C0], r14b
0x18013a61d  lea     rax, [rbp+57h+var_C0]
0x18013a621  mov     [rbp+57h+var_78], rax
0x18013a625  lea     rax, [rbp+57h+var_BC]
0x18013a629  mov     [rbp+57h+var_70], rax
0x18013a62d  lea     r15d, [r14+1]
0x18013a631  mov     [rbp+57h+var_68], r15b
0x18013a635  lea     rsi, [rcx+20h]
0x18013a639  mov     rcx, rsi
0x18013a63c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013a641  lea     rdx, aMy; "my"
0x18013a648  mov     rcx, rax
0x18013a64b  call    cs:__imp__o__wcsicmp
0x18013a651  test    eax, eax
0x18013a653  jnz     loc_18013A74E
0x18013a659  cmp     [rbx+0B0h], r14b
0x18013a660  jnz     loc_18013A74E
0x18013a666  mov     [rbp+57h+var_A0], r14
0x18013a66a  xor     edx, edx
0x18013a66c  lea     rcx, [rbp+57h+var_A0]
0x18013a670  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18013a675  lea     rcx, [rbp+57h+var_A0]
0x18013a679  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18013a67f  mov     [rbp+57h+var_BC], eax
0x18013a682  test    eax, eax
0x18013a684  jns     short loc_18013A6DB
0x18013a686  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013a68b  mov     r8d, [rbp+57h+var_BC]; int
0x18013a68f  lea     rdx, aDmgetactiveuse; "DmGetActiveUserSid failed"
0x18013a696  mov     rcx, rax; this
0x18013a699  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013a69e  mov     ebx, [rbp+57h+var_BC]
0x18013a6a1  lea     rcx, [rbp+57h+var_A0]
0x18013a6a5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013a6aa  nop
0x18013a6ab  cmp     [rbp+57h+var_C0], r14b
0x18013a6af  jz      short loc_18013A6B7
0x18013a6b1  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013a6b7  cmp     [rbp+57h+var_BC], r14d
0x18013a6bb  jge     short loc_18013A6D6
0x18013a6bd  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013a6c2  mov     r8d, [rbp+57h+var_BC]; int
0x18013a6c6  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013a6cd  mov     rcx, rax; this
0x18013a6d0  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013a6d5  nop
0x18013a6d6  jmp     loc_18013AAB6
0x18013a6db  mov     rcx, [rbp+57h+var_A0]
0x18013a6df  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18013a6e5  mov     [rbp+57h+var_BC], eax
0x18013a6e8  test    eax, eax
0x18013a6ea  jns     short loc_18013A741
0x18013a6ec  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013a6f1  mov     r8d, [rbp+57h+var_BC]; int
0x18013a6f5  lea     rdx, aDmimpersonateF; "DmImpersonate failed"
0x18013a6fc  mov     rcx, rax; this
0x18013a6ff  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013a704  mov     ebx, [rbp+57h+var_BC]
0x18013a707  lea     rcx, [rbp+57h+var_A0]
0x18013a70b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013a710  nop
0x18013a711  cmp     [rbp+57h+var_C0], r14b
0x18013a715  jz      short loc_18013A71D
0x18013a717  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013a71d  cmp     [rbp+57h+var_BC], r14d
0x18013a721  jge     short loc_18013A73C
0x18013a723  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013a728  mov     r8d, [rbp+57h+var_BC]; int
0x18013a72c  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013a733  mov     rcx, rax; this
0x18013a736  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013a73b  nop
0x18013a73c  jmp     loc_18013AAB6
0x18013a741  mov     [rbp+57h+var_C0], r15b
0x18013a745  lea     rcx, [rbp+57h+var_A0]
0x18013a749  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013a74e  mov     rcx, rsi
0x18013a751  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013a756  lea     rdx, aMy; "my"
0x18013a75d  mov     rcx, rax
0x18013a760  call    cs:__imp__o__wcsicmp
0x18013a766  test    eax, eax
0x18013a768  jnz     short loc_18013A778
0x18013a76a  cmp     [rbx+0B0h], r14b
0x18013a771  mov     edi, 1C000h
0x18013a776  jnz     short loc_18013A77D
0x18013a778  mov     edi, 0AC000h
0x18013a77d  mov     rcx, rsi
0x18013a780  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013a785  mov     [rsp+0F0h+pvPara], rax; int
0x18013a78a  mov     r9d, edi; dwFlags
0x18013a78d  xor     r8d, r8d; hCryptProv
0x18013a790  xor     edx, edx; dwEncodingType
0x18013a792  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x18013a795  call    cs:__imp_CertOpenStore
0x18013a79b  mov     [rbp+57h+hCertStore], rax
0x18013a79f  test    rax, rax
0x18013a7a2  jnz     short loc_18013A809
0x18013a7a4  call    cs:__imp_GetLastError
0x18013a7aa  mov     ebx, eax
0x18013a7ac  test    eax, eax
0x18013a7ae  jle     short loc_18013A7B9
0x18013a7b0  movzx   ebx, ax
0x18013a7b3  or      ebx, 80070000h
0x18013a7b9  mov     [rbp+57h+var_BC], ebx
0x18013a7bc  test    ebx, ebx
0x18013a7be  jns     short loc_18013A7D9
0x18013a7c0  mov     rcx, [rbp+5Fh]; this
0x18013a7c4  mov     r9d, ebx; char *
0x18013a7c7  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a7ce  mov     edx, 0BAh; void *
0x18013a7d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a7d8  nop
0x18013a7d9  cmp     [rbp+57h+var_C0], r14b
0x18013a7dd  jz      short loc_18013A7E5
0x18013a7df  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013a7e5  cmp     [rbp+57h+var_BC], r14d
0x18013a7e9  jge     short loc_18013A804
0x18013a7eb  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013a7f0  mov     r8d, [rbp+57h+var_BC]; int
0x18013a7f4  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013a7fb  mov     rcx, rax; this
0x18013a7fe  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013a803  nop
0x18013a804  jmp     loc_18013AAB6
0x18013a809  lea     rax, [rbp+57h+hCertStore]
0x18013a80d  mov     [rbp+57h+var_A0], rax
0x18013a811  mov     [rbp+57h+var_98], r15b
0x18013a815  xorps   xmm0, xmm0
0x18013a818  movups  xmmword ptr [rbp+57h+uBytes], xmm0
0x18013a81c  mov     rcx, rbx
0x18013a81f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013a824  mov     r9d, r15d
0x18013a827  lea     r8, [rbp+57h+uBytes]
0x18013a82b  xor     edx, edx
0x18013a82d  mov     rcx, rax
0x18013a830  call    cs:__imp_HexStringToBinary
0x18013a836  mov     edi, eax
0x18013a838  mov     [rbp+57h+var_BC], eax
0x18013a83b  test    eax, eax
0x18013a83d  jns     short loc_18013A898
0x18013a83f  mov     rcx, [rbp+5Fh]; this
0x18013a843  mov     r9d, eax; char *
0x18013a846  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a84d  mov     edx, 0C4h; void *
0x18013a852  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a857  nop
0x18013a858  mov     edx, r15d; dwFlags
0x18013a85b  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18013a85f  call    cs:__imp_CertCloseStore
0x18013a865  nop
0x18013a866  cmp     [rbp+57h+var_C0], r14b
0x18013a86a  jz      short loc_18013A872
0x18013a86c  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013a872  cmp     [rbp+57h+var_BC], r14d
0x18013a876  jge     short loc_18013A891
0x18013a878  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013a87d  mov     r8d, [rbp+57h+var_BC]; int
0x18013a881  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013a888  mov     rcx, rax; this
0x18013a88b  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013a890  nop
0x18013a891  mov     eax, edi
0x18013a893  jmp     loc_18013AAB8
0x18013a898  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x18013a89b  xor     ecx, ecx; uFlags
0x18013a89d  call    cs:__imp_LocalAlloc
0x18013a8a3  mov     rdi, rax
0x18013a8a6  mov     [rbp+57h+uBytes+8], rax
0x18013a8aa  test    rax, rax
0x18013a8ad  jnz     short loc_18013A90E
0x18013a8af  mov     ebx, 8007000Eh
0x18013a8b4  mov     [rbp+57h+var_BC], ebx
0x18013a8b7  mov     rcx, [rbp+5Fh]; this
0x18013a8bb  mov     r9d, ebx; char *
0x18013a8be  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a8c5  mov     edx, 0C7h; void *
0x18013a8ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a8cf  nop
0x18013a8d0  mov     edx, r15d; dwFlags
0x18013a8d3  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18013a8d7  call    cs:__imp_CertCloseStore
0x18013a8dd  nop
0x18013a8de  cmp     [rbp+57h+var_C0], r14b
0x18013a8e2  jz      short loc_18013A8EA
0x18013a8e4  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013a8ea  cmp     [rbp+57h+var_BC], r14d
0x18013a8ee  jge     short loc_18013A909
0x18013a8f0  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013a8f5  mov     r8d, [rbp+57h+var_BC]; int
0x18013a8f9  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013a900  mov     rcx, rax; this
0x18013a903  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013a908  nop
0x18013a909  jmp     loc_18013AAB6
0x18013a90e  lea     rax, [rbp+57h+uBytes]
0x18013a912  mov     [rbp+57h+var_88], rax
0x18013a916  mov     [rbp+57h+var_80], r15b
0x18013a91a  mov     rcx, rbx
0x18013a91d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013a922  mov     r9d, r15d
0x18013a925  lea     r8, [rbp+57h+uBytes]
0x18013a929  mov     rdx, rdi
0x18013a92c  mov     rcx, rax
0x18013a92f  call    cs:__imp_HexStringToBinary
0x18013a935  mov     edi, eax
0x18013a937  mov     [rbp+57h+var_BC], eax
0x18013a93a  test    eax, eax
0x18013a93c  jns     short loc_18013A9A0
0x18013a93e  mov     rcx, [rbp+5Fh]; this
0x18013a942  mov     r9d, eax; char *
0x18013a945  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013a94c  mov     edx, 0CEh; void *
0x18013a951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013a956  nop
0x18013a957  mov     rcx, [rbp+57h+uBytes+8]; hMem
0x18013a95b  call    cs:__imp_LocalFree
0x18013a961  nop
0x18013a962  mov     edx, r15d; dwFlags
0x18013a965  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18013a969  call    cs:__imp_CertCloseStore
0x18013a96f  nop
0x18013a970  cmp     [rbp+57h+var_C0], r14b
0x18013a974  jz      short loc_18013A97C
0x18013a976  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013a97c  cmp     [rbp+57h+var_BC], r14d
0x18013a980  jge     short loc_18013A99B
0x18013a982  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013a987  mov     r8d, [rbp+57h+var_BC]; int
0x18013a98b  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013a992  mov     rcx, rax; this
0x18013a995  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013a99a  nop
0x18013a99b  jmp     loc_18013A891
0x18013a9a0  mov     [rsp+0F0h+pPrevCertContext], r14; pPrevCertContext
0x18013a9a5  lea     rax, [rbp+57h+uBytes]
0x18013a9a9  mov     [rsp+0F0h+pvPara], rax; pvFindPara
0x18013a9ae  mov     r9d, 10000h; dwFindType
0x18013a9b4  xor     r8d, r8d; dwFindFlags
0x18013a9b7  lea     edx, [r9+1]; dwCertEncodingType
0x18013a9bb  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18013a9bf  call    cs:__imp_CertFindCertificateInStore
0x18013a9c5  mov     [rbp+57h+pCertContext], rax
0x18013a9c9  test    rax, rax
0x18013a9cc  jnz     short loc_18013AA49
0x18013a9ce  mov     r8, rbx
0x18013a9d1  lea     rdx, aCertstoreFails; "CertStore fails to find cert tracked by"...
0x18013a9d8  lea     rcx, [rbp+57h+var_60]
0x18013a9dc  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18013a9e1  nop
0x18013a9e2  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013a9e7  lea     rdx, [rbp+57h+var_60]
0x18013a9eb  mov     rcx, rax
0x18013a9ee  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x18013a9f3  nop
0x18013a9f4  lea     rcx, [rbp+57h+var_60]
0x18013a9f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013a9fd  nop
0x18013a9fe  mov     rcx, [rbp+57h+uBytes+8]; hMem
0x18013aa02  call    cs:__imp_LocalFree
0x18013aa08  nop
0x18013aa09  mov     edx, r15d; dwFlags
0x18013aa0c  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18013aa10  call    cs:__imp_CertCloseStore
0x18013aa16  nop
0x18013aa17  cmp     [rbp+57h+var_C0], r14b
0x18013aa1b  jz      short loc_18013AA23
0x18013aa1d  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013aa23  cmp     [rbp+57h+var_BC], r14d
0x18013aa27  jge     short loc_18013AA42
0x18013aa29  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013aa2e  mov     r8d, [rbp+57h+var_BC]; int
0x18013aa32  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013aa39  mov     rcx, rax; this
0x18013aa3c  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013aa41  nop
0x18013aa42  mov     eax, 80070490h
0x18013aa47  jmp     short loc_18013AAB8
0x18013aa49  lea     rcx, [rbp+57h+pCertContext]
0x18013aa4d  mov     [rbp+57h+var_60], rcx
0x18013aa51  mov     [rbp+57h+var_58], r15b
0x18013aa55  mov     rdx, rax; struct _CERT_CONTEXT *
0x18013aa58  mov     rcx, rbx; this
0x18013aa5b  call    ?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@PEBU_CERT_CONTEXT@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &,_CERT_CONTEXT const *)
0x18013aa60  mov     ebx, eax
0x18013aa62  mov     rcx, [rbp+57h+pCertContext]; pCertContext
  ... truncated ...
```
