# Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)

- ea: `0x18012a958`
- end: `0x18012ac6b`
- name: `?GetEnrollmentId@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAJAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `787`
- prototype: ``
- caller_count: `10`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800fabb4`
- `0x180128138`
- `0x18012af58`
- `0x18012b988`
- `0x18012cf78`
- `0x18012f3b4`
- `0x1801324f4`
- `0x180133b9c`
- `0x1801398f4`
- `0x18013a39c`

## callees

- `0x1800eb1ac`
- `0x1800ed46c`
- `0x1800eef28`
- `0x1800fa810`
- `0x1800faa0c`
- `0x180129108`
- `0x180129dc4`
- `0x18012a958`
- `0x180193010`

## import_xrefs

- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x18012a9a1`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x18012a9a1`

## string_xrefs

- `0x18012a9e4`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012aa79`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012aae9`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`
- `0x18012ab93`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::GetEnrollmentId(_QWORD *a1, _QWORD *a2)
{
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // edi
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v8; // rax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v13; // rax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v14; // rax
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, __int64); // rdi
  __int64 v17; // rax
  int v18; // eax
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  std::_Ref_count_base *v22; // rcx
  Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals *v23; // rax
  std::_Ref_count_base *v24[2]; // [rsp+20h] [rbp-20h] BYREF
  int *v25; // [rsp+30h] [rbp-10h]
  char v26; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v28; // [rsp+70h] [rbp+30h] BYREF
  __int64 v29; // [rsp+80h] [rbp+40h] BYREF
  __int64 v30; // [rsp+88h] [rbp+48h] BYREF

  v28 = 0;
  v25 = &v28;
  v26 = 1;
  if ( !*a1 || !*(_QWORD *)*a1 )
  {
    v30 = 0;
    v29 = 0;
    DatabaseManagerInstance = GetDatabaseManagerInstance();
    v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
    v6 = v5(DatabaseManagerInstance, 222306401, &v30);
    v7 = v6;
    v28 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v6,
        (int)v24[0]);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
      if ( (int)(v28 + 0x80000000) >= 0 && v28 != -2147023728 )
      {
        v8 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v8, L"GetEnrollmentId failed", v28);
      }
      return v7;
    }
    v10 = v30;
    v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 24LL);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
    v12 = v11(v10, &v29);
    v7 = v12;
    v28 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v12,
        (int)v24[0]);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
      if ( (int)(v28 + 0x80000000) >= 0 && v28 != -2147023728 )
      {
        v13 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v13, L"GetEnrollmentId failed", v28);
      }
      return v7;
    }
    if ( v12 == 1 )
    {
      v28 = -2147023728;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)0x80070490LL,
        (int)v24[0]);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
      if ( (int)(v28 + 0x80000000) >= 0 && v28 != -2147023728 )
      {
        v14 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v14, L"GetEnrollmentId failed", v28);
      }
      return 2147943568LL;
    }
    v15 = v29;
    v16 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 32LL);
    *(_OWORD *)v24 = 0;
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
      a1,
      v24);
    if ( v24[1] )
      std::_Ref_count_base::_Decref(v24[1]);
    v17 = wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(a1);
    v18 = v16(v15, v17);
    v7 = v18;
    v28 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
        (const char *)(unsigned int)v18,
        (int)v24[0]);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
      if ( (int)(v28 + 0x80000000) >= 0 && v28 != -2147023728 )
      {
        v19 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
        Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v19, L"GetEnrollmentId failed", v28);
      }
      return v7;
    }
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v30);
  }
  v20 = a1[1];
  if ( v20 )
    _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
  v21 = a1[1];
  *a2 = *a1;
  v22 = (std::_Ref_count_base *)a2[1];
  a2[1] = v21;
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  if ( (int)(v28 + 0x80000000) >= 0 && v28 != -2147023728 )
  {
    v23 = Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance();
    Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(v23, L"GetEnrollmentId failed", v28);
  }
  return 0;
}

```

## disassembly

```asm
0x18012a958  push    rbp
0x18012a95a  push    rbx
0x18012a95b  push    rsi
0x18012a95c  push    rdi
0x18012a95d  push    r14
0x18012a95f  mov     rbp, rsp
0x18012a962  sub     rsp, 40h
0x18012a966  mov     r14, rdx
0x18012a969  mov     rsi, rcx
0x18012a96c  mov     [rbp+arg_0], 0
0x18012a973  lea     rax, [rbp+arg_0]
0x18012a977  mov     [rbp+var_10], rax
0x18012a97b  mov     [rbp+var_8], 1
0x18012a97f  mov     rax, [rcx]
0x18012a982  test    rax, rax
0x18012a985  jz      short loc_18012A991
0x18012a987  cmp     qword ptr [rax], 0
0x18012a98b  jnz     loc_18012AC02
0x18012a991  mov     [rbp+arg_18], 0
0x18012a999  mov     [rbp+arg_10], 0
0x18012a9a1  call    cs:__imp_GetDatabaseManagerInstance
0x18012a9a8  nop     dword ptr [rax+rax+00h]
0x18012a9ad  mov     rdi, rax
0x18012a9b0  mov     rcx, [rax]
0x18012a9b3  mov     rbx, [rcx+20h]
0x18012a9b7  lea     rcx, [rbp+arg_18]
0x18012a9bb  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012a9c0  lea     r8, [rbp+arg_18]
0x18012a9c4  mov     edx, 0D402061h
0x18012a9c9  mov     rcx, rdi
0x18012a9cc  mov     rax, rbx
0x18012a9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012a9d4  mov     edi, eax
0x18012a9d6  mov     [rbp+arg_0], eax
0x18012a9d9  test    eax, eax
0x18012a9db  jns     short loc_18012AA42
0x18012a9dd  mov     rcx, [rbp+28h]; this
0x18012a9e1  mov     r9d, eax; char *
0x18012a9e4  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012a9eb  mov     edx, 59h ; 'Y'; void *
0x18012a9f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012a9f5  nop
0x18012a9f6  lea     rcx, [rbp+arg_10]
0x18012a9fa  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012a9ff  nop
0x18012aa00  lea     rcx, [rbp+arg_18]
0x18012aa04  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012aa09  nop
0x18012aa0a  mov     edx, [rbp+arg_0]
0x18012aa0d  mov     ecx, 80000000h
0x18012aa12  lea     eax, [rdx+rcx]
0x18012aa15  test    ecx, eax
0x18012aa17  jnz     short loc_18012AA3B
0x18012aa19  mov     ebx, 80070490h
0x18012aa1e  cmp     edx, ebx
0x18012aa20  jz      short loc_18012AA3B
0x18012aa22  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012aa27  mov     r8d, [rbp+arg_0]; int
0x18012aa2b  lea     rdx, aGetenrollmenti; "GetEnrollmentId failed"
0x18012aa32  mov     rcx, rax; this
0x18012aa35  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18012aa3a  nop
0x18012aa3b  mov     eax, edi
0x18012aa3d  jmp     loc_18012AC5F
0x18012aa42  mov     rdi, [rbp+arg_18]
0x18012aa46  mov     rax, [rdi]
0x18012aa49  mov     rbx, [rax+18h]
0x18012aa4d  lea     rcx, [rbp+arg_10]
0x18012aa51  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012aa56  lea     rdx, [rbp+arg_10]
0x18012aa5a  mov     rcx, rdi
0x18012aa5d  mov     rax, rbx
0x18012aa60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012aa65  mov     edi, eax
0x18012aa67  mov     [rbp+arg_0], eax
0x18012aa6a  test    eax, eax
0x18012aa6c  jns     short loc_18012AAD5
0x18012aa6e  test    eax, eax
0x18012aa70  jns     short loc_18012AA8B
0x18012aa72  mov     rcx, [rbp+28h]; this
0x18012aa76  mov     r9d, eax; char *
0x18012aa79  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012aa80  mov     edx, 5Ch ; '\'; void *
0x18012aa85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012aa8a  nop
0x18012aa8b  lea     rcx, [rbp+arg_10]
0x18012aa8f  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012aa94  nop
0x18012aa95  lea     rcx, [rbp+arg_18]
0x18012aa99  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012aa9e  nop
0x18012aa9f  mov     edx, [rbp+arg_0]
0x18012aaa2  mov     ecx, 80000000h
0x18012aaa7  lea     eax, [rdx+rcx]
0x18012aaaa  test    ecx, eax
0x18012aaac  jnz     short loc_18012AAD0
0x18012aaae  mov     ebx, 80070490h
0x18012aab3  cmp     edx, ebx
0x18012aab5  jz      short loc_18012AAD0
0x18012aab7  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012aabc  mov     r8d, [rbp+arg_0]; int
0x18012aac0  lea     rdx, aGetenrollmenti; "GetEnrollmentId failed"
0x18012aac7  mov     rcx, rax; this
0x18012aaca  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18012aacf  nop
0x18012aad0  jmp     loc_18012AA3B
0x18012aad5  cmp     edi, 1
0x18012aad8  jnz     short loc_18012AB40
0x18012aada  mov     ebx, 80070490h
0x18012aadf  mov     [rbp+arg_0], ebx
0x18012aae2  mov     rcx, [rbp+28h]; this
0x18012aae6  mov     r9d, ebx; char *
0x18012aae9  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012aaf0  lea     edx, [rdi+5Ch]; void *
0x18012aaf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012aaf8  nop
0x18012aaf9  lea     rcx, [rbp+arg_10]
0x18012aafd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012ab02  nop
0x18012ab03  lea     rcx, [rbp+arg_18]
0x18012ab07  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012ab0c  nop
0x18012ab0d  mov     edx, [rbp+arg_0]
0x18012ab10  mov     ecx, 80000000h
0x18012ab15  lea     eax, [rdx+rcx]
0x18012ab18  test    ecx, eax
0x18012ab1a  jnz     short loc_18012AB39
0x18012ab1c  cmp     edx, ebx
0x18012ab1e  jz      short loc_18012AB39
0x18012ab20  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012ab25  mov     r8d, [rbp+arg_0]; int
0x18012ab29  lea     rdx, aGetenrollmenti; "GetEnrollmentId failed"
0x18012ab30  mov     rcx, rax; this
0x18012ab33  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18012ab38  nop
0x18012ab39  mov     eax, ebx
0x18012ab3b  jmp     loc_18012AC5F
0x18012ab40  mov     rbx, [rbp+arg_10]
0x18012ab44  mov     rax, [rbx]
0x18012ab47  mov     rdi, [rax+20h]
0x18012ab4b  xorps   xmm0, xmm0
0x18012ab4e  movdqu  xmmword ptr [rbp+var_20], xmm0
0x18012ab53  lea     rdx, [rbp+var_20]
0x18012ab57  mov     rcx, rsi
0x18012ab5a  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x18012ab5f  mov     rcx, [rbp+var_20+8]; this
0x18012ab63  test    rcx, rcx
0x18012ab66  jz      short loc_18012AB6D
0x18012ab68  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012ab6d  mov     rcx, rsi
0x18012ab70  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEAPEAGXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x18012ab75  mov     rdx, rax
0x18012ab78  mov     rcx, rbx
0x18012ab7b  mov     rax, rdi
0x18012ab7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ab83  mov     edi, eax
0x18012ab85  mov     [rbp+arg_0], eax
0x18012ab88  test    eax, eax
0x18012ab8a  jns     short loc_18012ABEF
0x18012ab8c  mov     rcx, [rbp+28h]; this
0x18012ab90  mov     r9d, eax; char *
0x18012ab93  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012ab9a  mov     edx, 5Fh ; '_'; void *
0x18012ab9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012aba4  nop
0x18012aba5  lea     rcx, [rbp+arg_10]
0x18012aba9  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012abae  nop
0x18012abaf  lea     rcx, [rbp+arg_18]
0x18012abb3  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012abb8  nop
0x18012abb9  mov     edx, [rbp+arg_0]
0x18012abbc  mov     ecx, 80000000h
0x18012abc1  lea     eax, [rdx+rcx]
0x18012abc4  test    ecx, eax
0x18012abc6  jnz     short loc_18012ABEA
0x18012abc8  mov     ebx, 80070490h
0x18012abcd  cmp     edx, ebx
0x18012abcf  jz      short loc_18012ABEA
0x18012abd1  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012abd6  mov     r8d, [rbp+arg_0]; int
0x18012abda  lea     rdx, aGetenrollmenti; "GetEnrollmentId failed"
0x18012abe1  mov     rcx, rax; this
0x18012abe4  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18012abe9  nop
0x18012abea  jmp     loc_18012AA3B
0x18012abef  lea     rcx, [rbp+arg_10]
0x18012abf3  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012abf8  nop
0x18012abf9  lea     rcx, [rbp+arg_18]
0x18012abfd  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x18012ac02  mov     rax, [rsi+8]
0x18012ac06  test    rax, rax
0x18012ac09  jz      short loc_18012AC0F
0x18012ac0b  lock inc dword ptr [rax+8]
0x18012ac0f  mov     rdx, [rsi+8]
0x18012ac13  mov     rax, [rsi]
0x18012ac16  mov     [r14], rax
0x18012ac19  mov     rcx, [r14+8]; this
0x18012ac1d  mov     [r14+8], rdx
0x18012ac21  test    rcx, rcx
0x18012ac24  jz      short loc_18012AC2C
0x18012ac26  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18012ac2b  nop
0x18012ac2c  mov     edx, [rbp+arg_0]
0x18012ac2f  mov     ecx, 80000000h
0x18012ac34  lea     eax, [rdx+rcx]
0x18012ac37  test    ecx, eax
0x18012ac39  jnz     short loc_18012AC5D
0x18012ac3b  mov     ebx, 80070490h
0x18012ac40  cmp     edx, ebx
0x18012ac42  jz      short loc_18012AC5D
0x18012ac44  call    ?AcquireInstance@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@SAAEAV12345@XZ; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AcquireInstance(void)
0x18012ac49  mov     r8d, [rbp+arg_0]; int
0x18012ac4d  lea     rdx, aGetenrollmenti; "GetEnrollmentId failed"
0x18012ac54  mov     rcx, rax; this
0x18012ac57  call    ?AddDebugMessage@Globals@MdmDiagnosticSource@Mdm@Windows@Microsoft@@QEAAXPEBGJ@Z; Microsoft::Windows::Mdm::MdmDiagnosticSource::Globals::AddDebugMessage(ushort const *,long)
0x18012ac5c  nop
0x18012ac5d  xor     eax, eax
0x18012ac5f  add     rsp, 40h
0x18012ac63  pop     r14
0x18012ac65  pop     rdi
0x18012ac66  pop     rsi
0x18012ac67  pop     rbx
0x18012ac68  pop     rbp
0x18012ac69  retn
```
