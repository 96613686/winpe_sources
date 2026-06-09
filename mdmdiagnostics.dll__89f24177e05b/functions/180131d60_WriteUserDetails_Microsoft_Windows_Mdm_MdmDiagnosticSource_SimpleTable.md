# WriteUserDetails(Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable &)

- ea: `0x180131d60`
- end: `0x180132112`
- name: `?WriteUserDetails@@YAJAEAVSimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@Z`
- size: `946`
- prototype: `__int64 __fastcall(struct Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18012b354`

## callees

- `0x180019000`
- `0x1800e4348`
- `0x1800e66b8`
- `0x1800e66dc`
- `0x1800ece5c`
- `0x1800ed730`
- `0x1800ee878`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x1800f9558`
- `0x1800f9a0c`
- `0x180104270`
- `0x18010440c`
- `0x18010589c`
- `0x1801058cc`
- `0x180105b28`
- `0x180105c40`
- `0x18011129c`
- `0x180127da0`
- `0x180128e28`
- `0x180129b8c`
- `0x180131d60`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180131fa9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180131fa9`
- `RPCRT4!UuidFromStringW` at `0x180131de9`
- `RPCRT4!UuidFromStringW` at `0x180131de9`
- `DMCmnUtils!DmGetAadUserToken` at `0x180131f02`
- `DMCmnUtils!DmGetAadUserToken` at `0x180131f02`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180131e50`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180131e50`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x180131ebd`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x180131ebd`
- `dmEnrollEngine!GetEnrollmentSID` at `0x180131e21`
- `dmEnrollEngine!GetEnrollmentSID` at `0x180131e21`

## string_xrefs

- `0x180131dbf`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180131e63`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18013205d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180131fd7`: `User Token`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WriteUserDetails(struct Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *a1)
{
  struct Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v2; // rax
  int EnrollmentId; // eax
  unsigned int v4; // ebx
  unsigned __int16 *v5; // rcx
  int ActiveUserSid; // eax
  signed int AadUserToken; // ebx
  int v8; // eax
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  int lpBuffera; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v12; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[4]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v16[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h]
  __int64 v18; // [rsp+70h] [rbp-90h]
  UUID v19; // [rsp+80h] [rbp-80h] BYREF
  UUID v20; // [rsp+90h] [rbp-70h] BYREF
  __int128 v21; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v22[24]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v23[40]; // [rsp+C8h] [rbp-38h] BYREF
  UUID Uuid; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v25[24]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v21 = 0;
  Uuid = 0;
  std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v22);
  v2 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
  EnrollmentId = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(v2, &v21);
  v4 = EnrollmentId;
  if ( EnrollmentId >= 0 )
  {
    if ( (_QWORD)v21 )
      v5 = *(unsigned __int16 **)v21;
    else
      v5 = 0;
    if ( UuidFromStringW(v5, &Uuid) )
    {
      v4 = -2147467259;
      goto LABEL_31;
    }
    v12 = 0;
    v14 = 0;
    v20 = Uuid;
    if ( (int)GetEnrollmentSID(&v20, &v14) >= 0 )
      ListSIDTotable(a1, L"Enrolled", v14);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v12,
      0);
    ActiveUserSid = DmGetActiveUserSid(&v12);
    v4 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        lpBuffer);
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
      goto LABEL_31;
    }
    ListSIDTotable(a1, L"Active", v12);
    *(_QWORD *)&v20.Data1 = 0;
    v19 = Uuid;
    if ( (int)GetEnrollmentAadResourceUrl(&v19, &v20) >= 0 )
    {
      v13 = 0;
      *(_QWORD *)&v19.Data1 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v19,
        0);
      AadUserToken = DmGetAadUserToken(
                       L"de50c81f-5f80-4771-b66b-cebd28ccdfc1",
                       *(const unsigned __int16 **)&v20.Data1,
                       0,
                       (unsigned __int16 **)&v19,
                       &v13);
      std::wstring::wstring(v23);
      if ( AadUserToken < 0 )
      {
        StringCchPrintfW(v25, 0x16u, L"Failed 0x%x - ", (unsigned int)AadUserToken);
        *(_QWORD *)Buffer = 0;
        std::wstring::assign(v23, v25);
        if ( v13 )
          std::wstring::append(v23, L" User Interation Required - ");
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          Buffer,
          0);
        if ( FormatMessageW(0x1300u, 0, AadUserToken, 0x400u, Buffer, 0, 0) )
          std::wstring::append(v23, *(_QWORD *)Buffer);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Buffer);
      }
      else
      {
        std::wstring::assign(v23, L"Succeeded");
      }
      std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v16);
      std::wstring::wstring(v25, L"User Token");
      if ( v17 == v18 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v16, v17, v25);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v16, v25);
      std::wstring::_Tidy_deallocate(v25);
      if ( v17 == v18 )
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v16, v17, v23);
      else
        std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(v16, v23);
      v8 = (*(__int64 (__fastcall **)(struct Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *, _BYTE *))(*(_QWORD *)a1 + 32LL))(
             a1,
             v16);
      v4 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x468,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
          (const char *)(unsigned int)v8,
          lpBuffera);
        std::vector<std::wstring>::_Tidy(v16);
        std::wstring::_Tidy_deallocate(v23);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
        goto LABEL_12;
      }
      std::vector<std::wstring>::_Tidy(v16);
      std::wstring::_Tidy_deallocate(v23);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
    v4 = 0;
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x420,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
    (const char *)(unsigned int)EnrollmentId,
    lpBuffer);
LABEL_31:
  std::vector<std::wstring>::_Tidy(v22);
  std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(&v21);
  return v4;
}

```

## disassembly

```asm
0x180131d60  mov     [rsp-8+arg_8], rbx
0x180131d65  mov     [rsp-8+arg_10], rdi
0x180131d6a  push    rbp
0x180131d6b  lea     rbp, [rsp-40h]
0x180131d70  sub     rsp, 140h
0x180131d77  mov     rax, cs:__security_cookie
0x180131d7e  xor     rax, rsp
0x180131d81  mov     [rbp+40h+var_10], rax
0x180131d85  mov     rdi, rcx
0x180131d88  xorps   xmm0, xmm0
0x180131d8b  xorps   xmm1, xmm1
0x180131d8e  movdqu  [rbp+40h+var_A0], xmm1
0x180131d93  movups  xmmword ptr [rbp+40h+Uuid.Data1], xmm0
0x180131d97  lea     rcx, [rbp+40h+var_90]
0x180131d9b  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180131da0  nop
0x180131da1  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180131da6  lea     rdx, [rbp+40h+var_A0]
0x180131daa  mov     rcx, rax
0x180131dad  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x180131db2  mov     ebx, eax
0x180131db4  test    eax, eax
0x180131db6  jns     short loc_180131DD5
0x180131db8  mov     rcx, [rbp+48h]; this
0x180131dbc  mov     r9d, eax; char *
0x180131dbf  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180131dc6  mov     edx, 420h; void *
0x180131dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180131dd0  jmp     loc_1801320DC
0x180131dd5  mov     rax, qword ptr [rbp+40h+var_A0]
0x180131dd9  test    rax, rax
0x180131ddc  jz      short loc_180131DE3
0x180131dde  mov     rcx, [rax]
0x180131de1  jmp     short loc_180131DE5
0x180131de3  xor     ecx, ecx; StringUuid
0x180131de5  lea     rdx, [rbp+40h+Uuid]; Uuid
0x180131de9  call    cs:__imp_UuidFromStringW
0x180131def  test    eax, eax
0x180131df1  jz      short loc_180131DFD
0x180131df3  mov     ebx, 80004005h
0x180131df8  jmp     loc_1801320DC
0x180131dfd  mov     [rsp+140h+var_100], 0
0x180131e06  mov     [rsp+140h+var_F0], 0
0x180131e0f  movaps  xmm0, xmmword ptr [rbp+40h+Uuid.Data1]
0x180131e13  movdqa  [rbp+40h+var_B0], xmm0
0x180131e18  lea     rdx, [rsp+140h+var_F0]
0x180131e1d  lea     rcx, [rbp+40h+var_B0]
0x180131e21  call    cs:__imp_GetEnrollmentSID
0x180131e27  test    eax, eax
0x180131e29  js      short loc_180131E3F
0x180131e2b  mov     r8, [rsp+140h+var_F0]
0x180131e30  lea     rdx, aEnrolled; "Enrolled"
0x180131e37  mov     rcx, rdi
0x180131e3a  call    ListSIDTotable
0x180131e3f  xor     edx, edx
0x180131e41  lea     rcx, [rsp+140h+var_100]
0x180131e46  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180131e4b  lea     rcx, [rsp+140h+var_100]
0x180131e50  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180131e56  mov     ebx, eax
0x180131e58  test    eax, eax
0x180131e5a  jns     short loc_180131E8F
0x180131e5c  mov     rcx, [rbp+48h]; this
0x180131e60  mov     r9d, eax; char *
0x180131e63  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180131e6a  mov     edx, 42Fh; void *
0x180131e6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180131e74  nop
0x180131e75  lea     rcx, [rsp+140h+var_100]
0x180131e7a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180131e7f  nop
0x180131e80  lea     rcx, [rsp+140h+var_F0]
0x180131e85  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180131e8a  jmp     loc_1801320DC
0x180131e8f  mov     r8, [rsp+140h+var_100]
0x180131e94  lea     rdx, aActive; "Active"
0x180131e9b  mov     rcx, rdi
0x180131e9e  call    ListSIDTotable
0x180131ea3  nop
0x180131ea4  mov     qword ptr [rbp+40h+var_B0], 0
0x180131eac  movaps  xmm0, xmmword ptr [rbp+40h+Uuid.Data1]
0x180131eb0  movdqa  [rbp+40h+var_C0], xmm0
0x180131eb5  lea     rdx, [rbp+40h+var_B0]
0x180131eb9  lea     rcx, [rbp+40h+var_C0]
0x180131ebd  call    cs:__imp_GetEnrollmentAadResourceUrl
0x180131ec3  test    eax, eax
0x180131ec5  js      loc_1801320BB
0x180131ecb  mov     [rsp+140h+var_F8], 0
0x180131ed3  mov     qword ptr [rbp+40h+var_C0], 0
0x180131edb  xor     edx, edx
0x180131edd  lea     rcx, [rbp+40h+var_C0]
0x180131ee1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180131ee6  lea     rax, [rsp+140h+var_F8]
0x180131eeb  mov     [rsp+140h+lpBuffer], rax
0x180131ef0  lea     r9, [rbp+40h+var_C0]
0x180131ef4  xor     r8d, r8d
0x180131ef7  mov     rdx, qword ptr [rbp+40h+var_B0]
0x180131efb  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x180131f02  call    cs:__imp_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z; DmGetAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *,int *)
0x180131f08  mov     ebx, eax
0x180131f0a  lea     rcx, [rbp+40h+var_78]
0x180131f0e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180131f13  nop
0x180131f14  test    ebx, ebx
0x180131f16  js      short loc_180131F2D
0x180131f18  lea     rdx, aSucceeded; "Succeeded"
0x180131f1f  lea     rcx, [rbp+40h+var_78]
0x180131f23  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180131f28  jmp     loc_180131FCC
0x180131f2d  mov     r9d, ebx
0x180131f30  lea     r8, aFailed0xX; "Failed 0x%x - "
0x180131f37  mov     edx, 16h; unsigned __int64
0x180131f3c  lea     rcx, [rbp+40h+var_40]; unsigned __int16 *
0x180131f40  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180131f45  mov     qword ptr [rsp+140h+Buffer], 0
0x180131f4e  lea     rdx, [rbp+40h+var_40]
0x180131f52  lea     rcx, [rbp+40h+var_78]
0x180131f56  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180131f5b  cmp     [rsp+140h+var_F8], 0
0x180131f60  jz      short loc_180131F72
0x180131f62  lea     rdx, aUserInteration; " User Interation Required - "
0x180131f69  lea     rcx, [rbp+40h+var_78]
0x180131f6d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180131f72  xor     edx, edx
0x180131f74  lea     rcx, [rsp+140h+Buffer]
0x180131f79  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180131f7e  mov     [rsp+140h+Arguments], 0; Arguments
0x180131f87  mov     [rsp+140h+nSize], 0; nSize
0x180131f8f  lea     rax, [rsp+140h+Buffer]
0x180131f94  mov     [rsp+140h+lpBuffer], rax; int
0x180131f99  mov     r9d, 400h; dwLanguageId
0x180131f9f  mov     r8d, ebx; dwMessageId
0x180131fa2  xor     edx, edx; lpSource
0x180131fa4  mov     ecx, 1300h; dwFlags
0x180131fa9  call    cs:__imp_FormatMessageW
0x180131faf  test    eax, eax
0x180131fb1  jz      short loc_180131FC2
0x180131fb3  mov     rdx, qword ptr [rsp+140h+Buffer]
0x180131fb8  lea     rcx, [rbp+40h+var_78]
0x180131fbc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180131fc1  nop
0x180131fc2  lea     rcx, [rsp+140h+Buffer]
0x180131fc7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180131fcc  lea     rcx, [rsp+140h+var_E0]
0x180131fd1  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180131fd6  nop
0x180131fd7  lea     rdx, aUserToken; "User Token"
0x180131fde  lea     rcx, [rbp+40h+var_40]
0x180131fe2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180131fe7  nop
0x180131fe8  mov     rdx, [rsp+140h+var_D8]
0x180131fed  lea     rcx, [rsp+140h+var_E0]
0x180131ff2  cmp     rdx, [rsp+140h+var_D0]
0x180131ff7  jz      short loc_180132004
0x180131ff9  lea     rdx, [rbp+40h+var_40]
0x180131ffd  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x180132002  jmp     short loc_18013200E
0x180132004  lea     r8, [rbp+40h+var_40]
0x180132008  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18013200d  nop
0x18013200e  lea     rcx, [rbp+40h+var_40]
0x180132012  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132017  mov     rdx, [rsp+140h+var_D8]
0x18013201c  lea     rcx, [rsp+140h+var_E0]
0x180132021  cmp     rdx, [rsp+140h+var_D0]
0x180132026  jz      short loc_180132033
0x180132028  lea     rdx, [rbp+40h+var_78]
0x18013202c  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x180132031  jmp     short loc_18013203C
0x180132033  lea     r8, [rbp+40h+var_78]
0x180132037  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18013203c  mov     rax, [rdi]
0x18013203f  lea     rdx, [rsp+140h+var_E0]
0x180132044  mov     rcx, rdi
0x180132047  mov     rax, [rax+20h]
0x18013204b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180132050  mov     ebx, eax
0x180132052  test    eax, eax
0x180132054  jns     short loc_18013209C
0x180132056  mov     rcx, [rbp+48h]; this
0x18013205a  mov     r9d, eax; char *
0x18013205d  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180132064  mov     edx, 468h; void *
0x180132069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013206e  nop
0x18013206f  lea     rcx, [rsp+140h+var_E0]
0x180132074  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180132079  nop
0x18013207a  lea     rcx, [rbp+40h+var_78]
0x18013207e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180132083  nop
0x180132084  lea     rcx, [rbp+40h+var_C0]
0x180132088  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18013208d  nop
0x18013208e  lea     rcx, [rbp+40h+var_B0]
0x180132092  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180132097  jmp     loc_180131E75
0x18013209c  lea     rcx, [rsp+140h+var_E0]
0x1801320a1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801320a6  nop
0x1801320a7  lea     rcx, [rbp+40h+var_78]
0x1801320ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801320b0  nop
0x1801320b1  lea     rcx, [rbp+40h+var_C0]
0x1801320b5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801320ba  nop
0x1801320bb  lea     rcx, [rbp+40h+var_B0]
0x1801320bf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801320c4  nop
0x1801320c5  lea     rcx, [rsp+140h+var_100]
0x1801320ca  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801320cf  nop
0x1801320d0  lea     rcx, [rsp+140h+var_F0]
0x1801320d5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801320da  xor     ebx, ebx
0x1801320dc  lea     rcx, [rbp+40h+var_90]
0x1801320e0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801320e5  nop
0x1801320e6  lea     rcx, [rbp+40h+var_A0]
0x1801320ea  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x1801320ef  mov     eax, ebx
0x1801320f1  mov     rcx, [rbp+40h+var_10]
0x1801320f5  xor     rcx, rsp; StackCookie
0x1801320f8  call    __security_check_cookie
0x1801320fd  lea     r11, [rsp+140h+var_s0]
0x180132105  mov     rbx, [r11+18h]
0x180132109  mov     rdi, [r11+20h]
0x18013210d  mov     rsp, r11
0x180132110  pop     rbp
0x180132111  retn
```
