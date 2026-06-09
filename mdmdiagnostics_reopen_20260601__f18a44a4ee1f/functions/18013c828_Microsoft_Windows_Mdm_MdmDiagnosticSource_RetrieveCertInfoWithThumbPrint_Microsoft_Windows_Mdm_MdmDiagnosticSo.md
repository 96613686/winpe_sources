# Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveCertInfoWithThumbPrint(Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo &)

- ea: `0x18013c828`
- end: `0x18013cdba`
- name: `?RetrieveCertInfoWithThumbPrint@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAVCertInfo@1234@@Z`
- size: `1426`
- prototype: `__int64 __fastcall(Microsoft::Windows::Mdm::MdmDiagnosticSource *__hidden this, struct Microsoft::Windows::Mdm::MdmDiagnosticSource::CertInfo *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18012b988`
- `0x18012cbf8`

## callees

- `0x180019080`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f9a94`
- `0x1800fa538`
- `0x1800faa0c`
- `0x18010562c`
- `0x180129d4c`
- `0x180129dc4`
- `0x18013c828`
- `0x18013cdc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18013c887`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18013c9ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18013c887`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18013c9ba`
- `CRYPT32!CertOpenStore` at `0x18013c9f5`
- `CRYPT32!CertOpenStore` at `0x18013c9f5`
- `CRYPT32!CertFindCertificateInStore` at `0x18013cc6d`
- `CRYPT32!CertFindCertificateInStore` at `0x18013cc6d`
- `CRYPT32!CertFreeCertificateContext` at `0x18013cd38`
- `CRYPT32!CertFreeCertificateContext` at `0x18013cd38`
- `CRYPT32!CertCloseStore` at `0x18013cad7`
- `CRYPT32!CertCloseStore` at `0x18013cb61`
- `CRYPT32!CertCloseStore` at `0x18013cc0b`
- `CRYPT32!CertCloseStore` at `0x18013ccce`
- `CRYPT32!CertCloseStore` at `0x18013cd5d`
- `CRYPT32!CertCloseStore` at `0x18013cad7`
- `CRYPT32!CertCloseStore` at `0x18013cb61`
- `CRYPT32!CertCloseStore` at `0x18013cc0b`
- `CRYPT32!CertCloseStore` at `0x18013ccce`
- `CRYPT32!CertCloseStore` at `0x18013cd5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ca0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013ca0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013cbf7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013ccba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013cd49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013cbf7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013ccba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18013cd49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013cb21`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18013cb21`
- `DMCmnUtils!HexStringToBinary` at `0x18013caa2`
- `DMCmnUtils!HexStringToBinary` at `0x18013cbc5`
- `DMCmnUtils!HexStringToBinary` at `0x18013caa2`
- `DMCmnUtils!HexStringToBinary` at `0x18013cbc5`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18013c8bb`
- `DMCmnUtils!DmGetActiveUserSid` at `0x18013c8bb`
- `DMCmnUtils!DmRevertToSelf` at `0x18013c8f9`
- `DMCmnUtils!DmRevertToSelf` at `0x18013c96b`
- `DMCmnUtils!DmRevertToSelf` at `0x18013ca4b`
- `DMCmnUtils!DmRevertToSelf` at `0x18013caea`
- `DMCmnUtils!DmRevertToSelf` at `0x18013cb74`
- `DMCmnUtils!DmRevertToSelf` at `0x18013cc1e`
- `DMCmnUtils!DmRevertToSelf` at `0x18013cce1`
- `DMCmnUtils!DmRevertToSelf` at `0x18013cd70`
- `DMCmnUtils!DmRevertToSelf` at `0x18013c8f9`
- `DMCmnUtils!DmRevertToSelf` at `0x18013c96b`
- `DMCmnUtils!DmRevertToSelf` at `0x18013ca4b`
- `DMCmnUtils!DmRevertToSelf` at `0x18013caea`
- `DMCmnUtils!DmRevertToSelf` at `0x18013cb74`
- `DMCmnUtils!DmRevertToSelf` at `0x18013cc1e`
- `DMCmnUtils!DmRevertToSelf` at `0x18013cce1`
- `DMCmnUtils!DmRevertToSelf` at `0x18013cd70`
- `DMCmnUtils!DmImpersonate` at `0x18013c92d`
- `DMCmnUtils!DmImpersonate` at `0x18013c92d`

## string_xrefs

- `0x18013c8d7`: `DmGetActiveUserSid failed`
- `0x18013c949`: `DmImpersonate failed`

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
0x18013c828  push    rbp
0x18013c82a  push    rbx
0x18013c82b  push    rsi
0x18013c82c  push    rdi
0x18013c82d  push    r14
0x18013c82f  push    r15
0x18013c831  lea     rbp, [rsp-2Fh]
0x18013c836  sub     rsp, 0C8h
0x18013c83d  mov     rax, cs:__security_cookie
0x18013c844  xor     rax, rsp
0x18013c847  mov     [rbp+57h+var_40], rax
0x18013c84b  mov     rbx, rcx
0x18013c84e  xor     r14d, r14d
0x18013c851  mov     [rbp+57h+var_BC], r14d
0x18013c855  mov     [rbp+57h+var_C0], r14b
0x18013c859  lea     rax, [rbp+57h+var_C0]
0x18013c85d  mov     [rbp+57h+var_78], rax
0x18013c861  lea     rax, [rbp+57h+var_BC]
0x18013c865  mov     [rbp+57h+var_70], rax
0x18013c869  lea     r15d, [r14+1]
0x18013c86d  mov     [rbp+57h+var_68], r15b
0x18013c871  lea     rsi, [rcx+20h]
0x18013c875  mov     rcx, rsi
0x18013c878  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013c87d  lea     rdx, aMy; "my"
0x18013c884  mov     rcx, rax
0x18013c887  call    cs:__imp__o__wcsicmp
0x18013c88e  nop     dword ptr [rax+rax+00h]
0x18013c893  test    eax, eax
0x18013c895  jnz     loc_18013C9A8
0x18013c89b  cmp     [rbx+0B0h], r14b
0x18013c8a2  jnz     loc_18013C9A8
0x18013c8a8  mov     [rbp+57h+var_A0], r14
0x18013c8ac  xor     edx, edx
0x18013c8ae  lea     rcx, [rbp+57h+var_A0]
0x18013c8b2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18013c8b7  lea     rcx, [rbp+57h+var_A0]
0x18013c8bb  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18013c8c2  nop     dword ptr [rax+rax+00h]
0x18013c8c7  mov     [rbp+57h+var_BC], eax
0x18013c8ca  test    eax, eax
0x18013c8cc  jns     short loc_18013C929
0x18013c8ce  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013c8d3  mov     r8d, [rbp+57h+var_BC]; int
0x18013c8d7  lea     rdx, aDmgetactiveuse; "DmGetActiveUserSid failed"
0x18013c8de  mov     rcx, rax; this
0x18013c8e1  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013c8e6  mov     ebx, [rbp+57h+var_BC]
0x18013c8e9  lea     rcx, [rbp+57h+var_A0]
0x18013c8ed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013c8f2  nop
0x18013c8f3  cmp     [rbp+57h+var_C0], r14b
0x18013c8f7  jz      short loc_18013C905
0x18013c8f9  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013c900  nop     dword ptr [rax+rax+00h]
0x18013c905  cmp     [rbp+57h+var_BC], r14d
0x18013c909  jge     short loc_18013C924
0x18013c90b  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013c910  mov     r8d, [rbp+57h+var_BC]; int
0x18013c914  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013c91b  mov     rcx, rax; this
0x18013c91e  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013c923  nop
0x18013c924  jmp     loc_18013CD9B
0x18013c929  mov     rcx, [rbp+57h+var_A0]
0x18013c92d  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x18013c934  nop     dword ptr [rax+rax+00h]
0x18013c939  mov     [rbp+57h+var_BC], eax
0x18013c93c  test    eax, eax
0x18013c93e  jns     short loc_18013C99B
0x18013c940  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013c945  mov     r8d, [rbp+57h+var_BC]; int
0x18013c949  lea     rdx, aDmimpersonateF; "DmImpersonate failed"
0x18013c950  mov     rcx, rax; this
0x18013c953  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013c958  mov     ebx, [rbp+57h+var_BC]
0x18013c95b  lea     rcx, [rbp+57h+var_A0]
0x18013c95f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013c964  nop
0x18013c965  cmp     [rbp+57h+var_C0], r14b
0x18013c969  jz      short loc_18013C977
0x18013c96b  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013c972  nop     dword ptr [rax+rax+00h]
0x18013c977  cmp     [rbp+57h+var_BC], r14d
0x18013c97b  jge     short loc_18013C996
0x18013c97d  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013c982  mov     r8d, [rbp+57h+var_BC]; int
0x18013c986  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013c98d  mov     rcx, rax; this
0x18013c990  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013c995  nop
0x18013c996  jmp     loc_18013CD9B
0x18013c99b  mov     [rbp+57h+var_C0], r15b
0x18013c99f  lea     rcx, [rbp+57h+var_A0]
0x18013c9a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013c9a8  mov     rcx, rsi
0x18013c9ab  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013c9b0  lea     rdx, aMy; "my"
0x18013c9b7  mov     rcx, rax
0x18013c9ba  call    cs:__imp__o__wcsicmp
0x18013c9c1  nop     dword ptr [rax+rax+00h]
0x18013c9c6  test    eax, eax
0x18013c9c8  jnz     short loc_18013C9D8
0x18013c9ca  cmp     [rbx+0B0h], r14b
0x18013c9d1  mov     edi, 1C000h
0x18013c9d6  jnz     short loc_18013C9DD
0x18013c9d8  mov     edi, 0AC000h
0x18013c9dd  mov     rcx, rsi
0x18013c9e0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013c9e5  mov     [rsp+0F0h+pvPara], rax; int
0x18013c9ea  mov     r9d, edi; dwFlags
0x18013c9ed  xor     r8d, r8d; hCryptProv
0x18013c9f0  xor     edx, edx; dwEncodingType
0x18013c9f2  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x18013c9f5  call    cs:__imp_CertOpenStore
0x18013c9fc  nop     dword ptr [rax+rax+00h]
0x18013ca01  mov     [rbp+57h+hCertStore], rax
0x18013ca05  test    rax, rax
0x18013ca08  jnz     short loc_18013CA7B
0x18013ca0a  call    cs:__imp_GetLastError
0x18013ca11  nop     dword ptr [rax+rax+00h]
0x18013ca16  mov     ebx, eax
0x18013ca18  test    eax, eax
0x18013ca1a  jle     short loc_18013CA25
0x18013ca1c  movzx   ebx, ax
0x18013ca1f  or      ebx, 80070000h
0x18013ca25  mov     [rbp+57h+var_BC], ebx
0x18013ca28  test    ebx, ebx
0x18013ca2a  jns     short loc_18013CA45
0x18013ca2c  mov     rcx, [rbp+5Fh]; this
0x18013ca30  mov     r9d, ebx; char *
0x18013ca33  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013ca3a  mov     edx, 0BAh; void *
0x18013ca3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ca44  nop
0x18013ca45  cmp     [rbp+57h+var_C0], r14b
0x18013ca49  jz      short loc_18013CA57
0x18013ca4b  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013ca52  nop     dword ptr [rax+rax+00h]
0x18013ca57  cmp     [rbp+57h+var_BC], r14d
0x18013ca5b  jge     short loc_18013CA76
0x18013ca5d  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013ca62  mov     r8d, [rbp+57h+var_BC]; int
0x18013ca66  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013ca6d  mov     rcx, rax; this
0x18013ca70  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013ca75  nop
0x18013ca76  jmp     loc_18013CD9B
0x18013ca7b  lea     rax, [rbp+57h+hCertStore]
0x18013ca7f  mov     [rbp+57h+var_A0], rax
0x18013ca83  mov     [rbp+57h+var_98], r15b
0x18013ca87  xorps   xmm0, xmm0
0x18013ca8a  movups  xmmword ptr [rbp+57h+uBytes], xmm0
0x18013ca8e  mov     rcx, rbx
0x18013ca91  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013ca96  mov     r9d, r15d
0x18013ca99  lea     r8, [rbp+57h+uBytes]
0x18013ca9d  xor     edx, edx
0x18013ca9f  mov     rcx, rax
0x18013caa2  call    cs:__imp_HexStringToBinary
0x18013caa9  nop     dword ptr [rax+rax+00h]
0x18013caae  mov     edi, eax
0x18013cab0  mov     [rbp+57h+var_BC], eax
0x18013cab3  test    eax, eax
0x18013cab5  jns     short loc_18013CB1C
0x18013cab7  mov     rcx, [rbp+5Fh]; this
0x18013cabb  mov     r9d, eax; char *
0x18013cabe  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013cac5  mov     edx, 0C4h; void *
0x18013caca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013cacf  nop
0x18013cad0  mov     edx, r15d; dwFlags
0x18013cad3  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18013cad7  call    cs:__imp_CertCloseStore
0x18013cade  nop     dword ptr [rax+rax+00h]
0x18013cae3  nop
0x18013cae4  cmp     [rbp+57h+var_C0], r14b
0x18013cae8  jz      short loc_18013CAF6
0x18013caea  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013caf1  nop     dword ptr [rax+rax+00h]
0x18013caf6  cmp     [rbp+57h+var_BC], r14d
0x18013cafa  jge     short loc_18013CB15
0x18013cafc  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013cb01  mov     r8d, [rbp+57h+var_BC]; int
0x18013cb05  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013cb0c  mov     rcx, rax; this
0x18013cb0f  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013cb14  nop
0x18013cb15  mov     eax, edi
0x18013cb17  jmp     loc_18013CD9D
0x18013cb1c  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x18013cb1f  xor     ecx, ecx; uFlags
0x18013cb21  call    cs:__imp_LocalAlloc
0x18013cb28  nop     dword ptr [rax+rax+00h]
0x18013cb2d  mov     rdi, rax
0x18013cb30  mov     [rbp+57h+uBytes+8], rax
0x18013cb34  test    rax, rax
0x18013cb37  jnz     short loc_18013CBA4
0x18013cb39  mov     ebx, 8007000Eh
0x18013cb3e  mov     [rbp+57h+var_BC], ebx
0x18013cb41  mov     rcx, [rbp+5Fh]; this
0x18013cb45  mov     r9d, ebx; char *
0x18013cb48  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013cb4f  mov     edx, 0C7h; void *
0x18013cb54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013cb59  nop
0x18013cb5a  mov     edx, r15d; dwFlags
0x18013cb5d  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18013cb61  call    cs:__imp_CertCloseStore
0x18013cb68  nop     dword ptr [rax+rax+00h]
0x18013cb6d  nop
0x18013cb6e  cmp     [rbp+57h+var_C0], r14b
0x18013cb72  jz      short loc_18013CB80
0x18013cb74  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013cb7b  nop     dword ptr [rax+rax+00h]
0x18013cb80  cmp     [rbp+57h+var_BC], r14d
0x18013cb84  jge     short loc_18013CB9F
0x18013cb86  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013cb8b  mov     r8d, [rbp+57h+var_BC]; int
0x18013cb8f  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013cb96  mov     rcx, rax; this
0x18013cb99  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013cb9e  nop
0x18013cb9f  jmp     loc_18013CD9B
0x18013cba4  lea     rax, [rbp+57h+uBytes]
0x18013cba8  mov     [rbp+57h+var_88], rax
0x18013cbac  mov     [rbp+57h+var_80], r15b
0x18013cbb0  mov     rcx, rbx
0x18013cbb3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013cbb8  mov     r9d, r15d
0x18013cbbb  lea     r8, [rbp+57h+uBytes]
0x18013cbbf  mov     rdx, rdi
0x18013cbc2  mov     rcx, rax
0x18013cbc5  call    cs:__imp_HexStringToBinary
0x18013cbcc  nop     dword ptr [rax+rax+00h]
0x18013cbd1  mov     edi, eax
0x18013cbd3  mov     [rbp+57h+var_BC], eax
0x18013cbd6  test    eax, eax
0x18013cbd8  jns     short loc_18013CC4E
0x18013cbda  mov     rcx, [rbp+5Fh]; this
0x18013cbde  mov     r9d, eax; char *
0x18013cbe1  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013cbe8  mov     edx, 0CEh; void *
0x18013cbed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013cbf2  nop
0x18013cbf3  mov     rcx, [rbp+57h+uBytes+8]; hMem
0x18013cbf7  call    cs:__imp_LocalFree
0x18013cbfe  nop     dword ptr [rax+rax+00h]
0x18013cc03  nop
0x18013cc04  mov     edx, r15d; dwFlags
0x18013cc07  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18013cc0b  call    cs:__imp_CertCloseStore
0x18013cc12  nop     dword ptr [rax+rax+00h]
0x18013cc17  nop
0x18013cc18  cmp     [rbp+57h+var_C0], r14b
0x18013cc1c  jz      short loc_18013CC2A
0x18013cc1e  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x18013cc25  nop     dword ptr [rax+rax+00h]
0x18013cc2a  cmp     [rbp+57h+var_BC], r14d
0x18013cc2e  jge     short loc_18013CC49
0x18013cc30  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013cc35  mov     r8d, [rbp+57h+var_BC]; int
0x18013cc39  lea     rdx, aRetrievecertin; "RetrieveCertInfoWithThumbPrint failed"
0x18013cc40  mov     rcx, rax; this
0x18013cc43  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18013cc48  nop
0x18013cc49  jmp     loc_18013CB15
0x18013cc4e  mov     [rsp+0F0h+pPrevCertContext], r14; pPrevCertContext
0x18013cc53  lea     rax, [rbp+57h+uBytes]
0x18013cc57  mov     [rsp+0F0h+pvPara], rax; pvFindPara
0x18013cc5c  mov     r9d, 10000h; dwFindType
0x18013cc62  xor     r8d, r8d; dwFindFlags
0x18013cc65  lea     edx, [r9+1]; dwCertEncodingType
0x18013cc69  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18013cc6d  call    cs:__imp_CertFindCertificateInStore
0x18013cc74  nop     dword ptr [rax+rax+00h]
0x18013cc79  mov     [rbp+57h+pCertContext], rax
0x18013cc7d  test    rax, rax
0x18013cc80  jnz     loc_18013CD16
0x18013cc86  mov     r8, rbx
0x18013cc89  lea     rdx, aCertstoreFails; "CertStore fails to find cert tracked by"...
0x18013cc90  lea     rcx, [rbp+57h+var_60]
0x18013cc94  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18013cc99  nop
0x18013cc9a  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013cc9f  lea     rdx, [rbp+57h+var_60]
0x18013cca3  mov     rcx, rax
0x18013cca6  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(std::wstring const &)
0x18013ccab  nop
0x18013ccac  lea     rcx, [rbp+57h+var_60]
0x18013ccb0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013ccb5  nop
0x18013ccb6  mov     rcx, [rbp+57h+uBytes+8]; hMem
0x18013ccba  call    cs:__imp_LocalFree
0x18013ccc1  nop     dword ptr [rax+rax+00h]
0x18013ccc6  nop
0x18013ccc7  mov     edx, r15d; dwFlags
0x18013ccca  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x18013ccce  call    cs:__imp_CertCloseStore
0x18013ccd5  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
