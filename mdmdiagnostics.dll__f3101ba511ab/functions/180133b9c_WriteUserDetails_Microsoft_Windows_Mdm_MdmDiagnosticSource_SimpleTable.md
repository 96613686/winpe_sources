# WriteUserDetails(Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable &)

- ea: `0x180133b9c`
- end: `0x180133f73`
- name: `?WriteUserDetails@@YAJAEAVSimpleTable@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@Z`
- size: `983`
- prototype: `__int64 __fastcall(struct Microsoft::Windows::Mdm::MdmDiagnosticSource::SimpleTable *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18012cf78`

## callees

- `0x180019080`
- `0x1800e4408`
- `0x1800e688c`
- `0x1800e68b0`
- `0x1800ed46c`
- `0x1800edd78`
- `0x1800eef08`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x1800fa538`
- `0x1800faa0c`
- `0x180105480`
- `0x18010562c`
- `0x180106b3c`
- `0x180106b6c`
- `0x180106dc8`
- `0x180106ee0`
- `0x18011273c`
- `0x18012988c`
- `0x18012a958`
- `0x18012b74c`
- `0x180133b9c`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180133e03`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180133e03`
- `RPCRT4!UuidFromStringW` at `0x180133c25`
- `RPCRT4!UuidFromStringW` at `0x180133c25`
- `DMCmnUtils!DmGetAadUserToken` at `0x180133d56`
- `DMCmnUtils!DmGetAadUserToken` at `0x180133d56`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180133c98`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180133c98`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x180133d0b`
- `dmEnrollEngine!GetEnrollmentAadResourceUrl` at `0x180133d0b`
- `dmEnrollEngine!GetEnrollmentSID` at `0x180133c63`
- `dmEnrollEngine!GetEnrollmentSID` at `0x180133c63`

## string_xrefs

- `0x180133bfb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180133cb1`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180133ebd`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x180133e37`: `User Token`

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
0x180133b9c  mov     [rsp-8+arg_8], rbx
0x180133ba1  mov     [rsp-8+arg_10], rdi
0x180133ba6  push    rbp
0x180133ba7  lea     rbp, [rsp-40h]
0x180133bac  sub     rsp, 140h
0x180133bb3  mov     rax, cs:__security_cookie
0x180133bba  xor     rax, rsp
0x180133bbd  mov     [rbp+40h+var_10], rax
0x180133bc1  mov     rdi, rcx
0x180133bc4  xorps   xmm0, xmm0
0x180133bc7  xorps   xmm1, xmm1
0x180133bca  movdqu  [rbp+40h+var_A0], xmm1
0x180133bcf  movups  xmmword ptr [rbp+40h+Uuid.Data1], xmm0
0x180133bd3  lea     rcx, [rbp+40h+var_90]
0x180133bd7  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180133bdc  nop
0x180133bdd  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x180133be2  lea     rdx, [rbp+40h+var_A0]
0x180133be6  mov     rcx, rax
0x180133be9  call    ?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x180133bee  mov     ebx, eax
0x180133bf0  test    eax, eax
0x180133bf2  jns     short loc_180133C11
0x180133bf4  mov     rcx, [rbp+48h]; this
0x180133bf8  mov     r9d, eax; char *
0x180133bfb  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180133c02  mov     edx, 420h; void *
0x180133c07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180133c0c  jmp     loc_180133F3C
0x180133c11  mov     rax, qword ptr [rbp+40h+var_A0]
0x180133c15  test    rax, rax
0x180133c18  jz      short loc_180133C1F
0x180133c1a  mov     rcx, [rax]
0x180133c1d  jmp     short loc_180133C21
0x180133c1f  xor     ecx, ecx; StringUuid
0x180133c21  lea     rdx, [rbp+40h+Uuid]; Uuid
0x180133c25  call    cs:__imp_UuidFromStringW
0x180133c2c  nop     dword ptr [rax+rax+00h]
0x180133c31  test    eax, eax
0x180133c33  jz      short loc_180133C3F
0x180133c35  mov     ebx, 80004005h
0x180133c3a  jmp     loc_180133F3C
0x180133c3f  mov     [rsp+140h+var_100], 0
0x180133c48  mov     [rsp+140h+var_F0], 0
0x180133c51  movaps  xmm0, xmmword ptr [rbp+40h+Uuid.Data1]
0x180133c55  movdqa  [rbp+40h+var_B0], xmm0
0x180133c5a  lea     rdx, [rsp+140h+var_F0]
0x180133c5f  lea     rcx, [rbp+40h+var_B0]
0x180133c63  call    cs:__imp_GetEnrollmentSID
0x180133c6a  nop     dword ptr [rax+rax+00h]
0x180133c6f  test    eax, eax
0x180133c71  js      short loc_180133C87
0x180133c73  mov     r8, [rsp+140h+var_F0]
0x180133c78  lea     rdx, aEnrolled; "Enrolled"
0x180133c7f  mov     rcx, rdi
0x180133c82  call    ListSIDTotable
0x180133c87  xor     edx, edx
0x180133c89  lea     rcx, [rsp+140h+var_100]
0x180133c8e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180133c93  lea     rcx, [rsp+140h+var_100]
0x180133c98  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x180133c9f  nop     dword ptr [rax+rax+00h]
0x180133ca4  mov     ebx, eax
0x180133ca6  test    eax, eax
0x180133ca8  jns     short loc_180133CDD
0x180133caa  mov     rcx, [rbp+48h]; this
0x180133cae  mov     r9d, eax; char *
0x180133cb1  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180133cb8  mov     edx, 42Fh; void *
0x180133cbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180133cc2  nop
0x180133cc3  lea     rcx, [rsp+140h+var_100]
0x180133cc8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180133ccd  nop
0x180133cce  lea     rcx, [rsp+140h+var_F0]
0x180133cd3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180133cd8  jmp     loc_180133F3C
0x180133cdd  mov     r8, [rsp+140h+var_100]
0x180133ce2  lea     rdx, aActive; "Active"
0x180133ce9  mov     rcx, rdi
0x180133cec  call    ListSIDTotable
0x180133cf1  nop
0x180133cf2  mov     qword ptr [rbp+40h+var_B0], 0
0x180133cfa  movaps  xmm0, xmmword ptr [rbp+40h+Uuid.Data1]
0x180133cfe  movdqa  [rbp+40h+var_C0], xmm0
0x180133d03  lea     rdx, [rbp+40h+var_B0]
0x180133d07  lea     rcx, [rbp+40h+var_C0]
0x180133d0b  call    cs:__imp_GetEnrollmentAadResourceUrl
0x180133d12  nop     dword ptr [rax+rax+00h]
0x180133d17  test    eax, eax
0x180133d19  js      loc_180133F1B
0x180133d1f  mov     [rsp+140h+var_F8], 0
0x180133d27  mov     qword ptr [rbp+40h+var_C0], 0
0x180133d2f  xor     edx, edx
0x180133d31  lea     rcx, [rbp+40h+var_C0]
0x180133d35  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180133d3a  lea     rax, [rsp+140h+var_F8]
0x180133d3f  mov     [rsp+140h+lpBuffer], rax
0x180133d44  lea     r9, [rbp+40h+var_C0]
0x180133d48  xor     r8d, r8d
0x180133d4b  mov     rdx, qword ptr [rbp+40h+var_B0]
0x180133d4f  lea     rcx, aDe50c81f5f8047; "de50c81f-5f80-4771-b66b-cebd28ccdfc1"
0x180133d56  call    cs:__imp_?DmGetAadUserToken@@YAJPEBG00PEAPEAGPEAH@Z; DmGetAadUserToken(ushort const *,ushort const *,ushort const *,ushort * *,int *)
0x180133d5d  nop     dword ptr [rax+rax+00h]
0x180133d62  mov     ebx, eax
0x180133d64  lea     rcx, [rbp+40h+var_78]
0x180133d68  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180133d6d  nop
0x180133d6e  test    ebx, ebx
0x180133d70  js      short loc_180133D87
0x180133d72  lea     rdx, aSucceeded; "Succeeded"
0x180133d79  lea     rcx, [rbp+40h+var_78]
0x180133d7d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180133d82  jmp     loc_180133E2C
0x180133d87  mov     r9d, ebx
0x180133d8a  lea     r8, aFailed0xX; "Failed 0x%x - "
0x180133d91  mov     edx, 16h; unsigned __int64
0x180133d96  lea     rcx, [rbp+40h+var_40]; unsigned __int16 *
0x180133d9a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180133d9f  mov     qword ptr [rsp+140h+Buffer], 0
0x180133da8  lea     rdx, [rbp+40h+var_40]
0x180133dac  lea     rcx, [rbp+40h+var_78]
0x180133db0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180133db5  cmp     [rsp+140h+var_F8], 0
0x180133dba  jz      short loc_180133DCC
0x180133dbc  lea     rdx, aUserInteration; " User Interation Required - "
0x180133dc3  lea     rcx, [rbp+40h+var_78]
0x180133dc7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180133dcc  xor     edx, edx
0x180133dce  lea     rcx, [rsp+140h+Buffer]
0x180133dd3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180133dd8  mov     [rsp+140h+Arguments], 0; Arguments
0x180133de1  mov     [rsp+140h+nSize], 0; nSize
0x180133de9  lea     rax, [rsp+140h+Buffer]
0x180133dee  mov     [rsp+140h+lpBuffer], rax; int
0x180133df3  mov     r9d, 400h; dwLanguageId
0x180133df9  mov     r8d, ebx; dwMessageId
0x180133dfc  xor     edx, edx; lpSource
0x180133dfe  mov     ecx, 1300h; dwFlags
0x180133e03  call    cs:__imp_FormatMessageW
0x180133e0a  nop     dword ptr [rax+rax+00h]
0x180133e0f  test    eax, eax
0x180133e11  jz      short loc_180133E22
0x180133e13  mov     rdx, qword ptr [rsp+140h+Buffer]
0x180133e18  lea     rcx, [rbp+40h+var_78]
0x180133e1c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180133e21  nop
0x180133e22  lea     rcx, [rsp+140h+Buffer]
0x180133e27  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180133e2c  lea     rcx, [rsp+140h+var_E0]
0x180133e31  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180133e36  nop
0x180133e37  lea     rdx, aUserToken; "User Token"
0x180133e3e  lea     rcx, [rbp+40h+var_40]
0x180133e42  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180133e47  nop
0x180133e48  mov     rdx, [rsp+140h+var_D8]
0x180133e4d  lea     rcx, [rsp+140h+var_E0]
0x180133e52  cmp     rdx, [rsp+140h+var_D0]
0x180133e57  jz      short loc_180133E64
0x180133e59  lea     rdx, [rbp+40h+var_40]
0x180133e5d  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x180133e62  jmp     short loc_180133E6E
0x180133e64  lea     r8, [rbp+40h+var_40]
0x180133e68  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180133e6d  nop
0x180133e6e  lea     rcx, [rbp+40h+var_40]
0x180133e72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180133e77  mov     rdx, [rsp+140h+var_D8]
0x180133e7c  lea     rcx, [rsp+140h+var_E0]
0x180133e81  cmp     rdx, [rsp+140h+var_D0]
0x180133e86  jz      short loc_180133E93
0x180133e88  lea     rdx, [rbp+40h+var_78]
0x180133e8c  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x180133e91  jmp     short loc_180133E9C
0x180133e93  lea     r8, [rbp+40h+var_78]
0x180133e97  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180133e9c  mov     rax, [rdi]
0x180133e9f  lea     rdx, [rsp+140h+var_E0]
0x180133ea4  mov     rcx, rdi
0x180133ea7  mov     rax, [rax+20h]
0x180133eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133eb0  mov     ebx, eax
0x180133eb2  test    eax, eax
0x180133eb4  jns     short loc_180133EFC
0x180133eb6  mov     rcx, [rbp+48h]; this
0x180133eba  mov     r9d, eax; char *
0x180133ebd  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180133ec4  mov     edx, 468h; void *
0x180133ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180133ece  nop
0x180133ecf  lea     rcx, [rsp+140h+var_E0]
0x180133ed4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180133ed9  nop
0x180133eda  lea     rcx, [rbp+40h+var_78]
0x180133ede  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180133ee3  nop
0x180133ee4  lea     rcx, [rbp+40h+var_C0]
0x180133ee8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180133eed  nop
0x180133eee  lea     rcx, [rbp+40h+var_B0]
0x180133ef2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180133ef7  jmp     loc_180133CC3
0x180133efc  lea     rcx, [rsp+140h+var_E0]
0x180133f01  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180133f06  nop
0x180133f07  lea     rcx, [rbp+40h+var_78]
0x180133f0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180133f10  nop
0x180133f11  lea     rcx, [rbp+40h+var_C0]
0x180133f15  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180133f1a  nop
0x180133f1b  lea     rcx, [rbp+40h+var_B0]
0x180133f1f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180133f24  nop
0x180133f25  lea     rcx, [rsp+140h+var_100]
0x180133f2a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180133f2f  nop
0x180133f30  lea     rcx, [rsp+140h+var_F0]
0x180133f35  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180133f3a  xor     ebx, ebx
0x180133f3c  lea     rcx, [rbp+40h+var_90]
0x180133f40  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180133f45  nop
0x180133f46  lea     rcx, [rbp+40h+var_A0]
0x180133f4a  call    ??1?$shared_ptr@VRedirectedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>::~shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::RedirectedPolicies>(void)
0x180133f4f  mov     eax, ebx
0x180133f51  mov     rcx, [rbp+40h+var_10]
0x180133f55  xor     rcx, rsp; StackCookie
0x180133f58  call    __security_check_cookie
0x180133f5d  lea     r11, [rsp+140h+var_s0]
0x180133f65  mov     rbx, [r11+18h]
0x180133f69  mov     rdi, [r11+20h]
0x180133f6d  mov     rsp, r11
0x180133f70  pop     rbp
0x180133f71  retn
```
