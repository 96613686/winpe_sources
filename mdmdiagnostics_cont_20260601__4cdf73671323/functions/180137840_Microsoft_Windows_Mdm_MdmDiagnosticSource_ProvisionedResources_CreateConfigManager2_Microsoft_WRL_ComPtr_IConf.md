# Microsoft::Windows::Mdm::MdmDiagnosticSource::ProvisionedResources::CreateConfigManager2(Microsoft::WRL::ComPtr<IConfigManager2> &)

- ea: `0x180137840`
- end: `0x180137cc7`
- name: `?CreateConfigManager2@ProvisionedResources@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAJAEAV?$ComPtr@UIConfigManager2@@@WRL@5@@Z`
- size: `1159`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180138aa4`
- `0x1801393c8`
- `0x180139a0c`

## callees

- `0x1800ead14`
- `0x1800ece5c`
- `0x1800ee878`
- `0x1800f9558`
- `0x1800f9a0c`
- `0x18010440c`
- `0x1801145f8`
- `0x1801282b0`
- `0x180128e28`
- `0x1801293f4`
- `0x180137840`
- `0x180191010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180137970`
- `OLEAUT32!__imp_SysAllocString` at `0x180137b2b`
- `OLEAUT32!__imp_SysAllocString` at `0x180137bd8`
- `OLEAUT32!__imp_SysAllocString` at `0x180137970`
- `OLEAUT32!__imp_SysAllocString` at `0x180137b2b`
- `OLEAUT32!__imp_SysAllocString` at `0x180137bd8`
- `OLEAUT32!__imp_VariantInit` at `0x18013794e`
- `OLEAUT32!__imp_VariantInit` at `0x18013794e`
- `OLEAUT32!__imp_VariantClear` at `0x1801379c7`
- `OLEAUT32!__imp_VariantClear` at `0x180137a58`
- `OLEAUT32!__imp_VariantClear` at `0x180137ad6`
- `OLEAUT32!__imp_VariantClear` at `0x180137b87`
- `OLEAUT32!__imp_VariantClear` at `0x180137c34`
- `OLEAUT32!__imp_VariantClear` at `0x180137c77`
- `OLEAUT32!__imp_VariantClear` at `0x1801379c7`
- `OLEAUT32!__imp_VariantClear` at `0x180137a58`
- `OLEAUT32!__imp_VariantClear` at `0x180137ad6`
- `OLEAUT32!__imp_VariantClear` at `0x180137b87`
- `OLEAUT32!__imp_VariantClear` at `0x180137c34`
- `OLEAUT32!__imp_VariantClear` at `0x180137c77`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18013799b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18013799b`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1801378ed`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1801378ed`

## string_xrefs

- `0x180137bfe`: `OMADM::TargetedUserSID`
- `0x1801378bf`: `CreateConfigManager2 failed`
- `0x180137938`: `CreateConfigManager2 failed`
- `0x1801379f1`: `CreateConfigManager2 failed`
- `0x180137a82`: `CreateConfigManager2 failed`
- `0x180137b00`: `CreateConfigManager2 failed`
- `0x180137bb1`: `CreateConfigManager2 failed`
- `0x180137c5e`: `CreateConfigManager2 failed`
- `0x180137ca1`: `CreateConfigManager2 failed`

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
0x180137840  mov     [rsp-8+arg_0], rbx
0x180137845  push    rbp
0x180137846  push    rdi
0x180137847  push    r14
0x180137849  lea     rbp, [rsp-47h]
0x18013784e  sub     rsp, 90h
0x180137855  mov     rdi, rcx
0x180137858  mov     [rbp+57h+arg_8], 0
0x18013785f  lea     rax, [rbp+57h+arg_8]
0x180137863  mov     [rbp+57h+var_60], rax
0x180137867  mov     [rbp+57h+var_58], 1
0x18013786b  xorps   xmm1, xmm1
0x18013786e  movdqu  [rbp+57h+var_70], xmm1
0x180137873  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180137878  lea     rdx, [rbp+57h+var_70]
0x18013787c  mov     rcx, rax
0x18013787f  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x180137884  mov     ebx, eax
0x180137886  mov     [rbp+57h+arg_8], eax
0x180137889  test    eax, eax
0x18013788b  jns     short loc_1801378D6
0x18013788d  mov     rcx, [rbp+5Fh]; this
0x180137891  mov     r9d, eax; char *
0x180137894  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013789b  mov     edx, 138h; void *
0x1801378a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801378a5  nop
0x1801378a6  lea     rcx, [rbp+57h+var_70]
0x1801378aa  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1801378af  nop
0x1801378b0  cmp     [rbp+57h+arg_8], 0
0x1801378b4  jge     short loc_1801378CF
0x1801378b6  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801378bb  mov     r8d, [rbp+57h+arg_8]; int
0x1801378bf  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x1801378c6  mov     rcx, rax; this
0x1801378c9  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x1801378ce  nop
0x1801378cf  mov     eax, ebx
0x1801378d1  jmp     loc_180137CB3
0x1801378d6  mov     [rbp+57h+psz], 0
0x1801378de  xor     edx, edx
0x1801378e0  lea     rcx, [rbp+57h+psz]
0x1801378e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801378e9  lea     rcx, [rbp+57h+psz]
0x1801378ed  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1801378f3  mov     ebx, eax
0x1801378f5  mov     [rbp+57h+arg_8], eax
0x1801378f8  test    eax, eax
0x1801378fa  jns     short loc_18013794A
0x1801378fc  mov     rcx, [rbp+5Fh]; this
0x180137900  mov     r9d, eax; char *
0x180137903  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18013790a  mov     edx, 13Bh; void *
0x18013790f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137914  nop
0x180137915  lea     rcx, [rbp+57h+psz]
0x180137919  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013791e  nop
0x18013791f  lea     rcx, [rbp+57h+var_70]
0x180137923  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180137928  nop
0x180137929  cmp     [rbp+57h+arg_8], 0
0x18013792d  jge     short loc_180137948
0x18013792f  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180137934  mov     r8d, [rbp+57h+arg_8]; int
0x180137938  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x18013793f  mov     rcx, rax; this
0x180137942  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180137947  nop
0x180137948  jmp     short loc_1801378CF
0x18013794a  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18013794e  call    cs:__imp_VariantInit
0x180137954  nop
0x180137955  mov     r14d, 8
0x18013795b  mov     word ptr [rbp+57h+pvarg], r14w
0x180137960  mov     rax, qword ptr [rbp+57h+var_70]
0x180137964  test    rax, rax
0x180137967  jz      short loc_18013796E
0x180137969  mov     rcx, [rax]
0x18013796c  jmp     short loc_180137970
0x18013796e  xor     ecx, ecx; psz
0x180137970  call    cs:__imp_SysAllocString
0x180137976  mov     qword ptr [rbp+57h+pvarg+8], rax
0x18013797a  mov     rcx, rdi
0x18013797d  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x180137982  mov     qword ptr [rsp+0A0h+ppv], rdi; int
0x180137987  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x18013798e  xor     edx, edx; pUnkOuter
0x180137990  lea     r8d, [rdx+1]; dwClsContext
0x180137994  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x18013799b  call    cs:__imp_CoCreateInstance
0x1801379a1  mov     ebx, eax
0x1801379a3  mov     [rbp+57h+arg_8], eax
0x1801379a6  test    eax, eax
0x1801379a8  jns     short loc_180137A06
0x1801379aa  mov     rcx, [rbp+5Fh]; this
0x1801379ae  mov     r9d, eax; char *
0x1801379b1  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801379b8  mov     edx, 142h; void *
0x1801379bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801379c2  nop
0x1801379c3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1801379c7  call    cs:__imp_VariantClear
0x1801379cd  nop
0x1801379ce  lea     rcx, [rbp+57h+psz]
0x1801379d2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801379d7  nop
0x1801379d8  lea     rcx, [rbp+57h+var_70]
0x1801379dc  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1801379e1  nop
0x1801379e2  cmp     [rbp+57h+arg_8], 0
0x1801379e6  jge     short loc_180137A01
0x1801379e8  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x1801379ed  mov     r8d, [rbp+57h+arg_8]; int
0x1801379f1  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x1801379f8  mov     rcx, rax; this
0x1801379fb  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180137a00  nop
0x180137a01  jmp     loc_1801378CF
0x180137a06  mov     rcx, [rdi]
0x180137a09  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180137a0d  movaps  [rbp+57h+var_30], xmm0
0x180137a11  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180137a16  movsd   [rbp+57h+var_20], xmm1
0x180137a1b  mov     rax, [rcx]
0x180137a1e  lea     r8, [rbp+57h+var_30]
0x180137a22  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x180137a29  mov     rax, [rax+68h]
0x180137a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137a32  mov     ebx, eax
0x180137a34  mov     [rbp+57h+arg_8], eax
0x180137a37  test    eax, eax
0x180137a39  jns     short loc_180137A97
0x180137a3b  mov     rcx, [rbp+5Fh]; this
0x180137a3f  mov     r9d, eax; char *
0x180137a42  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137a49  mov     edx, 143h; void *
0x180137a4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137a53  nop
0x180137a54  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180137a58  call    cs:__imp_VariantClear
0x180137a5e  nop
0x180137a5f  lea     rcx, [rbp+57h+psz]
0x180137a63  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180137a68  nop
0x180137a69  lea     rcx, [rbp+57h+var_70]
0x180137a6d  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180137a72  nop
0x180137a73  cmp     [rbp+57h+arg_8], 0
0x180137a77  jge     short loc_180137A92
0x180137a79  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180137a7e  mov     r8d, [rbp+57h+arg_8]; int
0x180137a82  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x180137a89  mov     rcx, rax; this
0x180137a8c  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180137a91  nop
0x180137a92  jmp     loc_1801378CF
0x180137a97  mov     [rbp+57h+arg_18], 0
0x180137a9f  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180137aa4  lea     rdx, [rbp+57h+arg_18]; struct tagOMADMACCTINFO **
0x180137aa8  mov     rcx, rax; this
0x180137aab  call    ?GetOmadmAccountInfo@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAPEBUtagOMADMACCTINFO@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetOmadmAccountInfo(tagOMADMACCTINFO const * &)
0x180137ab0  mov     ebx, eax
0x180137ab2  mov     [rbp+57h+arg_8], eax
0x180137ab5  test    eax, eax
0x180137ab7  jns     short loc_180137B15
0x180137ab9  mov     rcx, [rbp+5Fh]; this
0x180137abd  mov     r9d, eax; char *
0x180137ac0  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137ac7  mov     edx, 147h; void *
0x180137acc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137ad1  nop
0x180137ad2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180137ad6  call    cs:__imp_VariantClear
0x180137adc  nop
0x180137add  lea     rcx, [rbp+57h+psz]
0x180137ae1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180137ae6  nop
0x180137ae7  lea     rcx, [rbp+57h+var_70]
0x180137aeb  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180137af0  nop
0x180137af1  cmp     [rbp+57h+arg_8], 0
0x180137af5  jge     short loc_180137B10
0x180137af7  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180137afc  mov     r8d, [rbp+57h+arg_8]; int
0x180137b00  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x180137b07  mov     rcx, rax; this
0x180137b0a  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180137b0f  nop
0x180137b10  jmp     loc_1801378CF
0x180137b15  lea     rcx, [rbp+57h+pvarg]
0x180137b19  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x180137b1e  mov     word ptr [rbp+57h+pvarg], r14w
0x180137b23  mov     rcx, [rbp+57h+arg_18]
0x180137b27  mov     rcx, [rcx+18h]; psz
0x180137b2b  call    cs:__imp_SysAllocString
0x180137b31  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180137b35  mov     rcx, [rdi]
0x180137b38  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180137b3c  movaps  [rbp+57h+var_30], xmm0
0x180137b40  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180137b45  movsd   [rbp+57h+var_20], xmm1
0x180137b4a  mov     rax, [rcx]
0x180137b4d  lea     r8, [rbp+57h+var_30]
0x180137b51  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x180137b58  mov     rax, [rax+68h]
0x180137b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137b61  mov     ebx, eax
0x180137b63  mov     [rbp+57h+arg_8], eax
0x180137b66  test    eax, eax
0x180137b68  jns     short loc_180137BC6
0x180137b6a  mov     rcx, [rbp+5Fh]; this
0x180137b6e  mov     r9d, eax; char *
0x180137b71  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137b78  mov     edx, 14Ch; void *
0x180137b7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137b82  nop
0x180137b83  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180137b87  call    cs:__imp_VariantClear
0x180137b8d  nop
0x180137b8e  lea     rcx, [rbp+57h+psz]
0x180137b92  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180137b97  nop
0x180137b98  lea     rcx, [rbp+57h+var_70]
0x180137b9c  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180137ba1  nop
0x180137ba2  cmp     [rbp+57h+arg_8], 0
0x180137ba6  jge     short loc_180137BC1
0x180137ba8  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180137bad  mov     r8d, [rbp+57h+arg_8]; int
0x180137bb1  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x180137bb8  mov     rcx, rax; this
0x180137bbb  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180137bc0  nop
0x180137bc1  jmp     loc_1801378CF
0x180137bc6  lea     rcx, [rbp+57h+pvarg]
0x180137bca  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x180137bcf  mov     word ptr [rbp+57h+pvarg], r14w
0x180137bd4  mov     rcx, [rbp+57h+psz]; psz
0x180137bd8  call    cs:__imp_SysAllocString
0x180137bde  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180137be2  mov     rcx, [rdi]
0x180137be5  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180137be9  movaps  [rbp+57h+var_30], xmm0
0x180137bed  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180137bf2  movsd   [rbp+57h+var_20], xmm1
0x180137bf7  mov     rax, [rcx]
0x180137bfa  lea     r8, [rbp+57h+var_30]
0x180137bfe  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x180137c05  mov     rax, [rax+68h]
0x180137c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137c0e  mov     ebx, eax
0x180137c10  mov     [rbp+57h+arg_8], eax
0x180137c13  test    eax, eax
0x180137c15  jns     short loc_180137C73
0x180137c17  mov     rcx, [rbp+5Fh]; this
0x180137c1b  mov     r9d, eax; char *
0x180137c1e  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137c25  mov     edx, 152h; void *
0x180137c2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137c2f  nop
0x180137c30  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180137c34  call    cs:__imp_VariantClear
0x180137c3a  nop
0x180137c3b  lea     rcx, [rbp+57h+psz]
0x180137c3f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180137c44  nop
0x180137c45  lea     rcx, [rbp+57h+var_70]
0x180137c49  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180137c4e  nop
0x180137c4f  cmp     [rbp+57h+arg_8], 0
0x180137c53  jge     short loc_180137C6E
0x180137c55  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180137c5a  mov     r8d, [rbp+57h+arg_8]; int
0x180137c5e  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x180137c65  mov     rcx, rax; this
0x180137c68  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180137c6d  nop
0x180137c6e  jmp     loc_1801378CF
0x180137c73  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180137c77  call    cs:__imp_VariantClear
0x180137c7d  nop
0x180137c7e  lea     rcx, [rbp+57h+psz]
0x180137c82  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180137c87  nop
0x180137c88  lea     rcx, [rbp+57h+var_70]
0x180137c8c  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180137c91  nop
0x180137c92  cmp     [rbp+57h+arg_8], 0
0x180137c96  jge     short loc_180137CB1
0x180137c98  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180137c9d  mov     r8d, [rbp+57h+arg_8]; int
0x180137ca1  lea     rdx, aCreateconfigma; "CreateConfigManager2 failed"
0x180137ca8  mov     rcx, rax; this
0x180137cab  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x180137cb0  nop
0x180137cb1  xor     eax, eax
0x180137cb3  mov     rbx, [rsp+0A0h+arg_0]
0x180137cbb  add     rsp, 90h
  ... truncated ...
```
