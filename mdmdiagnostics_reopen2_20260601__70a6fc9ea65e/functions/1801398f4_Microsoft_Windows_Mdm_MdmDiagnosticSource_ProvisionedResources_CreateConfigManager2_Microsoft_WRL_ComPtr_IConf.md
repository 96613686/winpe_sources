# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2(Microsoft::WRL::ComPtr<IConfigManager2> &)

- ea: `0x1801398f4`
- end: `0x180139dc7`
- name: `?CreateConfigManager2@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@@Z`
- size: `1235`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18013ac2c`
- `0x18013b590`
- `0x18013bbf8`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800eef08`
- `0x1800fa538`
- `0x1800faa0c`
- `0x18010562c`
- `0x180115ba0`
- `0x180129dc4`
- `0x18012a958`
- `0x18012af58`
- `0x1801398f4`
- `0x180193010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180139a33`
- `OLEAUT32!__imp_SysAllocString` at `0x180139c0c`
- `OLEAUT32!__imp_SysAllocString` at `0x180139cc5`
- `OLEAUT32!__imp_SysAllocString` at `0x180139a33`
- `OLEAUT32!__imp_SysAllocString` at `0x180139c0c`
- `OLEAUT32!__imp_SysAllocString` at `0x180139cc5`
- `OLEAUT32!__imp_VariantInit` at `0x180139a0b`
- `OLEAUT32!__imp_VariantInit` at `0x180139a0b`
- `OLEAUT32!__imp_VariantClear` at `0x180139a96`
- `OLEAUT32!__imp_VariantClear` at `0x180139b2d`
- `OLEAUT32!__imp_VariantClear` at `0x180139bb1`
- `OLEAUT32!__imp_VariantClear` at `0x180139c6e`
- `OLEAUT32!__imp_VariantClear` at `0x180139d27`
- `OLEAUT32!__imp_VariantClear` at `0x180139d70`
- `OLEAUT32!__imp_VariantClear` at `0x180139a96`
- `OLEAUT32!__imp_VariantClear` at `0x180139b2d`
- `OLEAUT32!__imp_VariantClear` at `0x180139bb1`
- `OLEAUT32!__imp_VariantClear` at `0x180139c6e`
- `OLEAUT32!__imp_VariantClear` at `0x180139d27`
- `OLEAUT32!__imp_VariantClear` at `0x180139d70`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180139a64`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180139a64`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1801399a1`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1801399a1`

## string_xrefs

- `0x180139cf1`: `OMADM::TargetedUserSID`
- `0x180139973`: `CreateConfigManager2 failed`
- `0x1801399f2`: `CreateConfigManager2 failed`
- `0x180139ac6`: `CreateConfigManager2 failed`
- `0x180139b5d`: `CreateConfigManager2 failed`
- `0x180139be1`: `CreateConfigManager2 failed`
- `0x180139c9e`: `CreateConfigManager2 failed`
- `0x180139d57`: `CreateConfigManager2 failed`
- `0x180139da0`: `CreateConfigManager2 failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2(LPVOID *a1)
{
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v2; // rax
  int EnrollmentId; // eax
  unsigned int v4; // ebx
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v5; // rax
  int ActiveUserSid; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v8; // rax
  const OLECHAR *v9; // rcx
  HRESULT Instance; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v11; // rax
  LPVOID v12; // rcx
  int v13; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v14; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v15; // rax
  int OmadmAccountInfo; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v17; // rax
  LPVOID v18; // rcx
  int v19; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v20; // rax
  LPVOID v21; // rcx
  int v22; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v23; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v24; // rax
  int ppv; // [rsp+20h] [rbp-29h]
  int ppva; // [rsp+20h] [rbp-29h]
  __int128 v27; // [rsp+30h] [rbp-19h] BYREF
  int *v28; // [rsp+40h] [rbp-9h]
  char v29; // [rsp+48h] [rbp-1h]
  VARIANTARG pvarg; // [rsp+50h] [rbp+7h] BYREF
  VARIANTARG v31[2]; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  int v33; // [rsp+B8h] [rbp+6Fh] BYREF
  OLECHAR *psz; // [rsp+C0h] [rbp+77h] BYREF
  struct tagOMADMACCTINFO *v35; // [rsp+C8h] [rbp+7Fh] BYREF

  v33 = 0;
  v28 = &v33;
  v29 = 1;
  v27 = 0;
  v2 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  EnrollmentId = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(v2, &v27);
  v4 = EnrollmentId;
  v33 = EnrollmentId;
  if ( EnrollmentId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
      (const char *)(unsigned int)EnrollmentId,
      ppv);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v27);
    if ( v33 < 0 )
    {
      v5 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v5, L"CreateConfigManager2 failed", v33);
    }
    return v4;
  }
  psz = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &psz,
    0);
  ActiveUserSid = DmGetActiveUserSid(&psz);
  v4 = ActiveUserSid;
  v33 = ActiveUserSid;
  if ( ActiveUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
      (const char *)(unsigned int)ActiveUserSid,
      ppv);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v27);
    if ( v33 < 0 )
    {
      v8 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v8, L"CreateConfigManager2 failed", v33);
    }
    return v4;
  }
  VariantInit(&pvarg);
  pvarg.vt = 8;
  if ( (_QWORD)v27 )
    v9 = *(const OLECHAR **)v27;
  else
    v9 = 0;
  pvarg.llVal = (LONGLONG)SysAllocString(v9);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(a1);
  Instance = CoCreateInstance(
               &GUID_66d0db14_5638_475f_a386_629522d8c461,
               0,
               1u,
               &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
               a1);
  v4 = Instance;
  v33 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v27);
    if ( v33 < 0 )
    {
      v11 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v11, L"CreateConfigManager2 failed", v33);
    }
    return v4;
  }
  v12 = *a1;
  v31[0] = pvarg;
  v13 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v12 + 104LL))(
          v12,
          L"OMADM::AccountID",
          v31);
  v4 = v13;
  v33 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
      (const char *)(unsigned int)v13,
      ppva);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v27);
    if ( v33 < 0 )
    {
      v14 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v14, L"CreateConfigManager2 failed", v33);
    }
    return v4;
  }
  v35 = 0;
  v15 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  OmadmAccountInfo = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetOmadmAccountInfo(v15, &v35);
  v4 = OmadmAccountInfo;
  v33 = OmadmAccountInfo;
  if ( OmadmAccountInfo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
      (const char *)(unsigned int)OmadmAccountInfo,
      ppva);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v27);
    if ( v33 < 0 )
    {
      v17 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v17, L"CreateConfigManager2 failed", v33);
    }
    return v4;
  }
  wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>::reset(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(*((const OLECHAR **)v35 + 3));
  v18 = *a1;
  v31[0] = pvarg;
  v19 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v18 + 104LL))(
          v18,
          L"OMADM::ServerID",
          v31);
  v4 = v19;
  v33 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
      (const char *)(unsigned int)v19,
      ppva);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v27);
    if ( v33 < 0 )
    {
      v20 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v20, L"CreateConfigManager2 failed", v33);
    }
    return v4;
  }
  wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>::reset(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  v21 = *a1;
  v31[0] = pvarg;
  v22 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, VARIANTARG *))(*(_QWORD *)v21 + 104LL))(
          v21,
          L"OMADM::TargetedUserSID",
          v31);
  v4 = v22;
  v33 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x152,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\erm.cpp",
      (const char *)(unsigned int)v22,
      ppva);
    VariantClear(&pvarg);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
    std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v27);
    if ( v33 < 0 )
    {
      v23 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
      Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v23, L"CreateConfigManager2 failed", v33);
    }
    return v4;
  }
  VariantClear(&pvarg);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psz);
  std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v27);
  if ( v33 < 0 )
  {
    v24 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v24, L"CreateConfigManager2 failed", v33);
  }
  return 0;
}

```

## disassembly

```asm
0x1801398f4  mov     [rsp-8+arg_0], rbx
0x1801398f9  push    rbp
0x1801398fa  push    rdi
0x1801398fb  push    r14
0x1801398fd  lea     rbp, [rsp-47h]
0x180139902  sub     rsp, 90h
0x180139909  mov     rdi, rcx
0x18013990c  mov     [rbp+57h+arg_8], 0
0x180139913  lea     rax, [rbp+57h+arg_8]
0x180139917  mov     [rbp+57h+var_60], rax
0x18013991b  mov     [rbp+57h+var_58], 1
0x18013991f  xorps   xmm1, xmm1
0x180139922  movdqu  [rbp+57h+var_70], xmm1
0x180139927  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013992c  lea     rdx, [rbp+57h+var_70]
0x180139930  mov     rcx, rax
0x180139933  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x180139938  mov     ebx, eax
0x18013993a  mov     [rbp+57h+arg_8], eax
0x18013993d  test    eax, eax
0x18013993f  jns     short loc_18013998A
0x180139941  mov     rcx, [rbp+5Fh]; this
0x180139945  mov     r9d, eax; char *
0x180139948  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013994f  mov     edx, 138h; void *
0x180139954  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139959  nop
0x18013995a  lea     rcx, [rbp+57h+var_70]
0x18013995e  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180139963  nop
0x180139964  cmp     [rbp+57h+arg_8], 0
0x180139968  jge     short loc_180139983
0x18013996a  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18013996f  mov     r8d, [rbp+57h+arg_8]; int
0x180139973  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x18013997a  mov     rcx, rax; this
0x18013997d  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180139982  nop
0x180139983  mov     eax, ebx
0x180139985  jmp     loc_180139DB2
0x18013998a  mov     [rbp+57h+psz], 0
0x180139992  xor     edx, edx
0x180139994  lea     rcx, [rbp+57h+psz]
0x180139998  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18013999d  lea     rcx, [rbp+57h+psz]
0x1801399a1  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1801399a8  nop     dword ptr [rax+rax+00h]
0x1801399ad  mov     ebx, eax
0x1801399af  mov     [rbp+57h+arg_8], eax
0x1801399b2  test    eax, eax
0x1801399b4  jns     short loc_180139A07
0x1801399b6  mov     rcx, [rbp+5Fh]; this
0x1801399ba  mov     r9d, eax; char *
0x1801399bd  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801399c4  mov     edx, 13Bh; void *
0x1801399c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801399ce  nop
0x1801399cf  lea     rcx, [rbp+57h+psz]
0x1801399d3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801399d8  nop
0x1801399d9  lea     rcx, [rbp+57h+var_70]
0x1801399dd  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1801399e2  nop
0x1801399e3  cmp     [rbp+57h+arg_8], 0
0x1801399e7  jge     short loc_180139A02
0x1801399e9  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801399ee  mov     r8d, [rbp+57h+arg_8]; int
0x1801399f2  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x1801399f9  mov     rcx, rax; this
0x1801399fc  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180139a01  nop
0x180139a02  jmp     loc_180139983
0x180139a07  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180139a0b  call    cs:__imp_VariantInit
0x180139a12  nop     dword ptr [rax+rax+00h]
0x180139a17  nop
0x180139a18  mov     r14d, 8
0x180139a1e  mov     word ptr [rbp+57h+pvarg], r14w
0x180139a23  mov     rax, qword ptr [rbp+57h+var_70]
0x180139a27  test    rax, rax
0x180139a2a  jz      short loc_180139A31
0x180139a2c  mov     rcx, [rax]
0x180139a2f  jmp     short loc_180139A33
0x180139a31  xor     ecx, ecx; psz
0x180139a33  call    cs:__imp_SysAllocString
0x180139a3a  nop     dword ptr [rax+rax+00h]
0x180139a3f  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180139a43  mov     rcx, rdi
0x180139a46  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180139a4b  mov     qword ptr [rsp+0A0h+ppv], rdi; int
0x180139a50  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x180139a57  xor     edx, edx; pUnkOuter
0x180139a59  lea     r8d, [rdx+1]; dwClsContext
0x180139a5d  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x180139a64  call    cs:__imp_CoCreateInstance
0x180139a6b  nop     dword ptr [rax+rax+00h]
0x180139a70  mov     ebx, eax
0x180139a72  mov     [rbp+57h+arg_8], eax
0x180139a75  test    eax, eax
0x180139a77  jns     short loc_180139ADB
0x180139a79  mov     rcx, [rbp+5Fh]; this
0x180139a7d  mov     r9d, eax; char *
0x180139a80  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139a87  mov     edx, 142h; void *
0x180139a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139a91  nop
0x180139a92  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180139a96  call    cs:__imp_VariantClear
0x180139a9d  nop     dword ptr [rax+rax+00h]
0x180139aa2  nop
0x180139aa3  lea     rcx, [rbp+57h+psz]
0x180139aa7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180139aac  nop
0x180139aad  lea     rcx, [rbp+57h+var_70]
0x180139ab1  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180139ab6  nop
0x180139ab7  cmp     [rbp+57h+arg_8], 0
0x180139abb  jge     short loc_180139AD6
0x180139abd  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180139ac2  mov     r8d, [rbp+57h+arg_8]; int
0x180139ac6  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x180139acd  mov     rcx, rax; this
0x180139ad0  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180139ad5  nop
0x180139ad6  jmp     loc_180139983
0x180139adb  mov     rcx, [rdi]
0x180139ade  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180139ae2  movaps  [rbp+57h+var_30], xmm0
0x180139ae6  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180139aeb  movsd   [rbp+57h+var_20], xmm1
0x180139af0  mov     rax, [rcx]
0x180139af3  lea     r8, [rbp+57h+var_30]
0x180139af7  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x180139afe  mov     rax, [rax+68h]
0x180139b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139b07  mov     ebx, eax
0x180139b09  mov     [rbp+57h+arg_8], eax
0x180139b0c  test    eax, eax
0x180139b0e  jns     short loc_180139B72
0x180139b10  mov     rcx, [rbp+5Fh]; this
0x180139b14  mov     r9d, eax; char *
0x180139b17  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139b1e  mov     edx, 143h; void *
0x180139b23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139b28  nop
0x180139b29  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180139b2d  call    cs:__imp_VariantClear
0x180139b34  nop     dword ptr [rax+rax+00h]
0x180139b39  nop
0x180139b3a  lea     rcx, [rbp+57h+psz]
0x180139b3e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180139b43  nop
0x180139b44  lea     rcx, [rbp+57h+var_70]
0x180139b48  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180139b4d  nop
0x180139b4e  cmp     [rbp+57h+arg_8], 0
0x180139b52  jge     short loc_180139B6D
0x180139b54  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180139b59  mov     r8d, [rbp+57h+arg_8]; int
0x180139b5d  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x180139b64  mov     rcx, rax; this
0x180139b67  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180139b6c  nop
0x180139b6d  jmp     loc_180139983
0x180139b72  mov     [rbp+57h+arg_18], 0
0x180139b7a  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180139b7f  lea     rdx, [rbp+57h+arg_18]; struct tagOMADMACCTINFO **
0x180139b83  mov     rcx, rax; this
0x180139b86  call    ?GetOmadmAccountInfo@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAPEBUtagOMADMACCTINFO@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetOmadmAccountInfo(tagOMADMACCTINFO const * &)
0x180139b8b  mov     ebx, eax
0x180139b8d  mov     [rbp+57h+arg_8], eax
0x180139b90  test    eax, eax
0x180139b92  jns     short loc_180139BF6
0x180139b94  mov     rcx, [rbp+5Fh]; this
0x180139b98  mov     r9d, eax; char *
0x180139b9b  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139ba2  mov     edx, 147h; void *
0x180139ba7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139bac  nop
0x180139bad  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180139bb1  call    cs:__imp_VariantClear
0x180139bb8  nop     dword ptr [rax+rax+00h]
0x180139bbd  nop
0x180139bbe  lea     rcx, [rbp+57h+psz]
0x180139bc2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180139bc7  nop
0x180139bc8  lea     rcx, [rbp+57h+var_70]
0x180139bcc  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180139bd1  nop
0x180139bd2  cmp     [rbp+57h+arg_8], 0
0x180139bd6  jge     short loc_180139BF1
0x180139bd8  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180139bdd  mov     r8d, [rbp+57h+arg_8]; int
0x180139be1  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x180139be8  mov     rcx, rax; this
0x180139beb  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180139bf0  nop
0x180139bf1  jmp     loc_180139983
0x180139bf6  lea     rcx, [rbp+57h+pvarg]
0x180139bfa  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x180139bff  mov     word ptr [rbp+57h+pvarg], r14w
0x180139c04  mov     rcx, [rbp+57h+arg_18]
0x180139c08  mov     rcx, [rcx+18h]; psz
0x180139c0c  call    cs:__imp_SysAllocString
0x180139c13  nop     dword ptr [rax+rax+00h]
0x180139c18  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180139c1c  mov     rcx, [rdi]
0x180139c1f  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180139c23  movaps  [rbp+57h+var_30], xmm0
0x180139c27  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180139c2c  movsd   [rbp+57h+var_20], xmm1
0x180139c31  mov     rax, [rcx]
0x180139c34  lea     r8, [rbp+57h+var_30]
0x180139c38  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x180139c3f  mov     rax, [rax+68h]
0x180139c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139c48  mov     ebx, eax
0x180139c4a  mov     [rbp+57h+arg_8], eax
0x180139c4d  test    eax, eax
0x180139c4f  jns     short loc_180139CB3
0x180139c51  mov     rcx, [rbp+5Fh]; this
0x180139c55  mov     r9d, eax; char *
0x180139c58  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139c5f  mov     edx, 14Ch; void *
0x180139c64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139c69  nop
0x180139c6a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180139c6e  call    cs:__imp_VariantClear
0x180139c75  nop     dword ptr [rax+rax+00h]
0x180139c7a  nop
0x180139c7b  lea     rcx, [rbp+57h+psz]
0x180139c7f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180139c84  nop
0x180139c85  lea     rcx, [rbp+57h+var_70]
0x180139c89  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180139c8e  nop
0x180139c8f  cmp     [rbp+57h+arg_8], 0
0x180139c93  jge     short loc_180139CAE
0x180139c95  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180139c9a  mov     r8d, [rbp+57h+arg_8]; int
0x180139c9e  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x180139ca5  mov     rcx, rax; this
0x180139ca8  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180139cad  nop
0x180139cae  jmp     loc_180139983
0x180139cb3  lea     rcx, [rbp+57h+pvarg]
0x180139cb7  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x180139cbc  mov     word ptr [rbp+57h+pvarg], r14w
0x180139cc1  mov     rcx, [rbp+57h+psz]; psz
0x180139cc5  call    cs:__imp_SysAllocString
0x180139ccc  nop     dword ptr [rax+rax+00h]
0x180139cd1  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180139cd5  mov     rcx, [rdi]
0x180139cd8  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180139cdc  movaps  [rbp+57h+var_30], xmm0
0x180139ce0  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180139ce5  movsd   [rbp+57h+var_20], xmm1
0x180139cea  mov     rax, [rcx]
0x180139ced  lea     r8, [rbp+57h+var_30]
0x180139cf1  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x180139cf8  mov     rax, [rax+68h]
0x180139cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139d01  mov     ebx, eax
0x180139d03  mov     [rbp+57h+arg_8], eax
0x180139d06  test    eax, eax
0x180139d08  jns     short loc_180139D6C
0x180139d0a  mov     rcx, [rbp+5Fh]; this
0x180139d0e  mov     r9d, eax; char *
0x180139d11  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180139d18  mov     edx, 152h; void *
0x180139d1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139d22  nop
0x180139d23  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180139d27  call    cs:__imp_VariantClear
0x180139d2e  nop     dword ptr [rax+rax+00h]
0x180139d33  nop
0x180139d34  lea     rcx, [rbp+57h+psz]
0x180139d38  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180139d3d  nop
0x180139d3e  lea     rcx, [rbp+57h+var_70]
0x180139d42  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180139d47  nop
0x180139d48  cmp     [rbp+57h+arg_8], 0
0x180139d4c  jge     short loc_180139D67
0x180139d4e  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180139d53  mov     r8d, [rbp+57h+arg_8]; int
0x180139d57  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x180139d5e  mov     rcx, rax; this
0x180139d61  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180139d66  nop
0x180139d67  jmp     loc_180139983
0x180139d6c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180139d70  call    cs:__imp_VariantClear
0x180139d77  nop     dword ptr [rax+rax+00h]
0x180139d7c  nop
0x180139d7d  lea     rcx, [rbp+57h+psz]
0x180139d81  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180139d86  nop
0x180139d87  lea     rcx, [rbp+57h+var_70]
0x180139d8b  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
  ... truncated ...
```
